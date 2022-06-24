---
title: Firmare il file .appx MPOS con un certificato di firma del codice
description: Questo articolo spiega come firmare MPOS con un certificato di firma del codice.
author: mugunthanm
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 28021
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2019-09-2019
ms.openlocfilehash: 7e998514081cad1c7302aacb1cd74373f896f2d0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865971"
---
# <a name="sign-the-mpos-appx-file-with-a-code-signing-certificate"></a>Firmare il file .appx MPOS con un certificato di firma del codice

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Per installare Modern POS (MPOS) è necessario firmare l'app MPOS con un certificato di firma del codice di un provider attendibile e installare lo stesso certificato su tutte le macchine in cui è installato MPOS nella cartella radice attendibile per l'utente corrente.

Per firmare l'app MPOS con un certificato, utilizza una di queste opzioni nel file **Retail SDK\\ Strumento di costruzione\\Customization.settings**:

- Aggiungi la parte dell'attività Proteggi file dei passaggi di creazione di Azure DevOps e carica il certificato per proteggere l'attività del file. Utilizza la variabile del percorso di output dell'attività Proteggi file come parametro nel file Customization.settings.

    > [!NOTE]
    > L'attività Proteggi file non supporta un certificato protetto da password. È necessario rimuovere la password prima di caricare questa attività. Poiché il certificato viene caricato nell'attività di sistema Proteggi file in Azure, è possibile rimuovere la password solo per questo passaggio. Tuttavia, è consigliabile discutere la rimozione della password con i tuoi esperti di sicurezza per determinare se questa è l'azione corretta per il tuo progetto. Non rimuovere la password del certificato per altri scenari.
- Utilizza un certificato che si trova nel file system. Per fare ciò, scarica o genera un certificato e inseriscilo nel file system in cui è in esecuzione la build. L'agente ospitato da Microsoft o l'utente build dovrebbe avere accesso a questo percorso e file.
- Utilizza l'identificazione personale per cercare il certificato nell'archivio e accedere con quel certificato.

## <a name="use-a-secure-file-task-for-universal-windows-platform-app-signing"></a>Utilizza un'attività Proteggi file per la firma dell'app della piattaforma UWP (Universal Windows Platform)

> [!NOTE]
> È anche possibile usare Azure Key Vault per archiviare il certificato e usare lo strumento di firma di Azure per firmare il file con estensione appx di Modern POS e i programmi di installazione self-service. Per script di pipeline di esempio e informazioni aggiuntive, vedere [Configurare una pipeline di compilazione in Azure DevOps per generare pacchetti self-service al dettaglio](build-pipeline.md#set-up-a-build-pipeline-in-azure-devops-to-generate-retail-self-service-packages).

L'uso di un'attività Proteggi file è l'approccio consigliato per la firma dell'app UWP (Universal Windows Platform). Per ulteriori informazioni sulla firma del pacchetto, vedere [Configurare la firma del pacchetto](/windows/uwp/packaging/auto-build-package-uwp-apps#configure-package-signing). Questo processo è mostrato nell'immagine seguente.

![Flusso di firma dell'app MPOS.](media/POSSigningFlow.png)

> [!NOTE]
> Attualmente la creazione di pacchetti OOB supporta la firma solo del file .appx, i diversi programmi di installazione self-service come MPOIS, RSSU e HWS non vengono firmati da questo processo. È necessario firmarlo manualmente utilizzando SignTool o altri strumenti di firma. Il certificato utilizzato per la firma del file .appx deve essere installato nel computer in cui è installato Modern POS.

## <a name="steps-to-configure-the-certificate-for-signing-in-azure-pipelines"></a>Passaggi per configurare il certificato per l'accesso ad Azure Pipelines

### <a name="certificate-in-the-file-systemsecure-location"></a>Certificato nel file system/percorso protetto

Scarica l'[attività DownloadFile](/visualstudio/msbuild/downloadfile-task) e aggiungila come primo passaggio nel processo di compilazione. Il vantaggio dell'utilizzo dell'attività Proteggi file è che il file viene crittografato e inserito nel disco durante la compilazione, indipendentemente dal fatto che la pipeline di compilazione abbia esito positivo, negativo o venga annullata. Il file viene eliminato dal percorso di download al termine del processo di compilazione.

1. Scarica e aggiungi l'attività Proteggi file come primo passaggio nella pipeline di compilazione di Azure. È possibile scaricare l'attività Proteggi file da [DownloadFile](https://marketplace.visualstudio.com/items?itemName=automagically.DownloadFile).
1. Carica il certificato nell'attività Proteggi file e imposta il Nome di riferimento in Variabili di output, come mostrato nell'immagine seguente.
    > [!div class="mx-imgBorder"]
    > ![Attività Proteggi file.](media/SecureFile.png)
1. Crea una nuova variabile in Azure Pipelines selezionando **Nuova variabile** nella scheda **Variabili**.
1. Fornisci un nome per la variabile nel campo del valore, ad esempio **MySigningCert**.
1. Salva la variabile.
1. Apri il file **Customization.settings** file da **RetailSDK\\BuildTools** e aggiorna **ModernPOSPackageCertificateKeyFile** con il nome della variabile creata nella pipeline (passaggio 3). Ad esempio:

    ```Xml
    <ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(MySigningCert)</ModernPOSPackageCertificateKeyFile>
    ```
    Questo passaggio è obbligatorio se il certificato non è protetto da password. Se il certificato è protetto da password, continua con i passaggi seguenti.
    
1. Se desideri eseguire il timestamp del file MPOS .appx quando lo firmi con un certificato, apri il file **Retail SDK\\Build tool\\Customization.settings** e aggiorna la variabile **ModernPOSPackageCertificateTimestamp** con il provider del timestamp (ad esempio, `http://timestamp.digicert.com`).
1. Nella scheda **Variabili** della pipeline, aggiungi una nuova variabile secure-text. Imposta il nome su **MySigningCert.secret** e imposta il valore della password per il certificato. Seleziona l'icona del lucchetto per proteggere la variabile.
1. Aggiungi un'attività **Script Powershell** alla pipeline (dopo il download del file protetto e prima del passaggio di compilazione). Specifica il nome **Visualizza** e imposta il tipo come **In linea**. Copia e incolla quanto segue nella sezione dello script.

    ```powershell
    Write-Host "Start adding the PFX file to the certificate store."
    $pfxpath = '$(MySigningCert.secureFilePath)'
    $secureString = ConvertTo-SecureString "$(MySigningCert.secret)" -AsPlainText -Force
    Import-PfxCertificate -FilePath $pfxpath -CertStoreLocation Cert:\CurrentUser\My -Password $secureString
    ```

1. Apri il file **Customization.settings** file da **RetailSDK\\BuildTools** e aggiorna **ModernPOSPackageCertificateThumbprint** con il valore di identificazione personale del certificato.

    ```Xml
       <ModernPOSPackageCertificateThumbprint Condition="'$(ModernPOSPackageCertificateThumbprint)' == ''"></ModernPOSPackageCertificateThumbprint>
    ```
 
Per i dettagli su come ottenere l'identificazione personale per un certificato, vedere [recuperare l'identificazione personale di un certificato](/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate#to-retrieve-a-certificates-thumbprint). 

## <a name="download-or-generate-a-certificate-to-sign-the-mpos-app-manually-using-msbuild-in-sdk"></a>Scarica o genera un certificato per firmare manualmente l'app MPOS utilizzando msbuild in SDK

Se un certificato scaricato o generato viene utilizzato per firmare l'app MPOS, aggiorna il nodo **ModernPOSPackageCertificateKeyFile** nel file **BuildTools\\Customization.settings** per puntare al percorso del file pfx (**$(SdkReferencesPath)\\appxsignkey.pfx**). Ad esempio:

```xml
<ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(SdkReferencesPath)\appxsignkey.pfx</ModernPOSPackageCertificateKeyFile>
```

In questo caso, il nome del file del certificato è **appxsignkey.pfx** e si trova nella cartella **Retail SDK\\Riferimento**.

## <a name="use-thumbprint-to-sign-the-mpos-app"></a>Utilizzare l'identificazione personale per firmare l'app MPOS

Se utilizzi l'identificazione personale per firmare l'app MPOS, installa il certificato in locale. Aggiorna il valore dell'identificazione personale nel nodo **ModernPOSPackageCertificateThumbprint** nel file **BuildTools\\Customization.settings** file.

Questa opzione funzionerà se l'utente di creazione è un utente locale. Tuttavia, se stai usando gli agenti Azure DevOps per generare la build, l'agente potrebbe non disporre dell'autorizzazione per accedere all'archivio certificati per utilizzare il certificato per la firma o il computer di compilazione non avrà il certificato installato. In questo caso, la soluzione consiste nel modificare l'utente di compilazione in utente locale e installare il certificato nella casella. Tuttavia, questa opzione non funzionerà se non disponi dell'accesso come amministratore alla casella.

> [!NOTE]
> Se il file .pfx o l'opzione dell'attività Proteggi file viene utilizzata per firmare l'app, lascia il nodo **ModernPOSPackageCertificateThumbprint** in **Customization.settings**. Se viene utilizzata l'opzione di identificazione personale, lascia **ModernPOSPackageCertificateKeyFile** vuoto. Se entrambi i valori vengono aggiornati, la compilazione avrà esito negativo.

### <a name="certification-renewal"></a>Rinnovo della certificazione

### <a name="renew-a-certificate-from-trusted-ca"></a>Rinnova un certificato da un'autorità di certificazione attendibile

Contatta la tua autorità di certificazione per il processo di rinnovo del certificato. Per un certificato attendibile, non è richiesta alcuna azione sul lato MPOS.

### <a name="renew-a-self-signed-certificate"></a>Rinnovare un certificato autofirmato

Non utilizzare il certificato di esempio disponibile in Retail SDK per la produzione. Può essere utilizzato solo per scopi di sviluppo. Il certificato di esempio Contoso non può essere rinnovato e il certificato di esempio incluso in Retail SDK versione 10.0.16 o precedente scadrà il 31 dicembre 2020. Se questo certificato, o un certificato autofirmato, è stato utilizzato per firmare un'app Modern POS personalizzata, esiste una forte possibilità che Modern POS non funzioni correttamente dopo questa data.
 
### <a name="impact"></a>Impatto
 
Se quanto sopra è vero per te, il problema che incontrerai è che il programma di installazione non sarà in grado di essere eseguito dopo il 31 dicembre 2020. A seconda dei criteri IT aziendali utilizzati, Modern POS potrebbe non essere in grado di funzionare. È fondamentale verificarlo modificando temporaneamente la data in una data futura, per determinare l'impatto sulla tua organizzazione.
 
### <a name="steps-to-determine-the-issue"></a>Passaggi per determinare il problema
 
1.  Utilizza le impostazioni di Windows per modificare l'orologio del computer in una data e un'ora nell'anno 2021.
2.  Verifica che Modern POS possa essere aperto, che possa essere effettuato l'accesso e che una transazione possa essere completata.
3.  Verifica che il programma di installazione self-service di Modern POS possa essere eseguito e, in tal caso, l'installazione verrà completata correttamente.
4.  Riporta le impostazioni dell'orologio di Windows alla data e all'ora corrette.
 
Se riesci a completare tutti questi passaggi senza problemi, sarai in grado di operare con il certificato attuale dopo il 31 dicembre 2020.  
 
### <a name="steps-going-forward"></a>Passaggi successivi 

È fortemente consigliato rinnovare il certificato utilizzato in precedenza. È consigliabile ottenere un nuovo certificato. Per fare ciò, devi eseguire una delle azioni riportate di seguito:
 
- **Preferita** - Ottieni un certificato di firma del codice da un'autorità di certificazione attendibile.

- **Non preferita** - Genera un certificato di firma del codice autofirmato da utilizzare. In genere viene utilizzato solo per scopi di sviluppo all'interno di un dominio e non è consigliato per la produzione. 

- **Disponibile come soluzione temporanea** - Usa il certificato di firma del codice Contoso rinnovato. Viene in genere utilizzato a scopo di test, quindi non è consigliabile distribuirlo in produzione.
 
Quindi, genera un nuovo pacchetto POS moderno personalizzato che viene firmato utilizzando questo certificato ottenuto da una delle azioni precedenti. A seconda del certificato, segui uno dei passaggi seguenti:
 
- Se utilizzi un nuovo certificato attendibile (o un nuovo certificato autofirmato), ti verrà richiesto di installare un nuovo certificato su ogni dispositivo. Successivamente, è necessario prendere il pacchetto Modern POS appena creato (programma di installazione), disinstallare l'applicazione esistente e quindi reinstallare il nuovo pacchetto Modern POS. Dovrai eseguire un'attivazione del dispositivo di Modern POS su ogni dispositivo.

- Se si utilizza il certificato Contoso rinnovato, sarà necessario installare il nuovo certificato su ogni dispositivo e installare il pacchetto Modern POS (programma di installazione). Non è necessario disinstallare, tuttavia è necessario reinstallare sul dispositivo. Tieni presente che l'attivazione del dispositivo Modern POS non sarà obbligatoria. Questa opzione è una soluzione temporanea. Utilizza questa opzione solo per evitare la riattivazione e risolvere il problema prima di ottenere un nuovo certificato attendibile.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
