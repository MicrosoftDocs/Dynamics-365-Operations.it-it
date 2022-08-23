---
title: Configurare l'integrazione diretta di FatturaPA italiana con SDI
description: Questo articolo fornisce informazioni che ti aiuteranno a iniziare con la fatturazione elettronica per l'Italia e impostare l'integrazione diretta di FatturaPA italiana con il sistema di Exchange (SDI).
author: gionoder
ms.date: 01/15/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: e050d3896b2ba10433e166995d6fc405996cf0b2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267158"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Configurare l'integrazione diretta di FatturaPA italiana con SDI

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> La fatturazione elettronica per l'Italia potrebbe attualmente non supportare tutte le funzioni disponibili per le fatture elettroniche in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.

Questo articolo fornisce informazioni introduttive sulla fatturazione elettronica per l'Italia in Finance e Supply Chain Management. Ti guida attraverso i passaggi di configurazione che dipendono dal paese/area geografica in Regulatory Configuration Services (RCS). Questi passaggi completano i passaggi descritti in [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Prerequisiti

Prima di completare i passaggi in questo articolo, è necessario soddisfare i seguenti requisiti:

- Completa i passaggi in [Introduzione all'amministrazione dei servizi per la fatturazione elettronica](e-invoicing-get-started.md).
- Importa la funzionalità di fatturazione elettronica **FatturaPA italiana (IT)** in RCS dal repository Globale. Per ulteriori informazioni, vedi la sezione [Importare una funzionalità di fatturazione elettronica dal provider di configurazione Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) dell'articolo "Introduzione alla fatturazione elettronica" precedentemente menzionato.
- Aggiungi i collegamenti dai certificati richiesti all'ambiente del servizio. I certificati richiesti includono il certificato di firma digitale, il certificato dell'autorità di certificazione (CA) e il certificato dei client. Per ulteriori informazioni, vedi la sezione [Creare un segreto del certificato digitale](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) dell'articolo "Introduzione all'amministrazione dei servizi per la fatturazione elettronica".

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Configurazione specifica del paese per la funzionalità di fatturazione elettronica FatturaPA italiana (IT)

Completa le seguenti procedure prima di distribuire la configurazione dell'applicazione all'app Finance o Supply Chain Management connessa.

Questa sezione è a complemento della sezione [Configurazione specifica del paese dell'impostazione dell'applicazione](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) nell'articolo "Introduzione alla fatturazione elettronica".

### <a name="create-a-new-feature"></a>Crea una nuova funzionalità

1. Accedere a RCS.
2. Nell'area di lavoro **Creazione di report elettronici** nella sezione **Provider di configurazione**, contrassegna il provider di configurazione della tua azienda come attivo.
3. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
4. Nella pagina **Funzionalità per la fatturazione elettronica** seleziona **Aggiungi** \> **Basato su funzionalità esistente**.
5. In **Provider di configurazione Microsoft**, seleziona **FatturaPA italiana (IT)** come funzionalità di base, inserisci un nome, quindi seleziona **Crea funzionalità**.

### <a name="set-up-application-specific-parameters"></a>Configurare parametri specifici dell'applicazione

1. Nella pagina **Funzionalità per la fatturazione elettronica** seleziona la funzionalità da modificare.
2. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
3. Seleziona una configurazione nella scheda **Configurazioni** e seleziona **parametri specifici dell'applicazione**.
4. Nella sezione **Ricerche** assicurati che la ricerca **Elenco delle sottocategorie reverse charge Natura** sia selezionata.
5. Nella sezione **Condizioni**, seleziona **Aggiungi**.
6. Aggiungi condizioni specifiche per ogni sottocategoria definita nel sistema, quindi salva le modifiche.

    > [!NOTE]
    > Nella colonna **Nome** puoi selezionare il segnaposto **\*Vuoto\*** o **\*Non vuoto\*** invece di un valore specifico.

### <a name="configure-a-processing-pipeline-for-export"></a>Configurare una pipeline di elaborazione per l'esportazione

1. Nella pagina **Funzionalità per la fatturazione elettronica** seleziona la funzionalità da modificare.
2. Nella scheda **Impostazioni**, seleziona **Fatture di vendita**, quindi seleziona **Modifica**.
3. Nella sezione **Pipeline di elaborazione** passa alle azioni e imposta tutti i campi richiesti:

    - Per l'azione **Firma documento** nel campo **Nome certificato** specifica il Certificato di firma digitale.
    - Per l'azione **Invia** imposta i campi **Indirizzo URL** e **Certificati**. Il valore del campo **Certificati** è una catena di certificati, il primo dei quali è il certificato CA radice (caentrate.cer) e il secondo è il certificato client.

4. Nella sezione **Regole di applicabilità**, esamina le singole clausole e rivedi o imposta i campi obbligatori:
    - Rivedi la clausola **LegalEntityID** e aggiornala con il valore corretto della persona giuridica.

5. Seleziona **Convalida** per garantire che tutti i campi necessari siano stati impostati.
6. Salva le modifiche e chiudi la pagina.
7. Nella scheda **Impostazioni**, seleziona **Fatture di progetto**, quindi seleziona **Modifica**.
8. Ripeti i passaggi da 3 a 6 per le fatture di progetto.

### <a name="configure-the-processing-pipeline-for-import"></a>Configurare la pipeline di elaborazione per l'importazione

1. Nella pagina **Funzionalità per la fatturazione elettronica** seleziona la funzionalità da modificare.
2. Nella scheda **Impostazioni**, seleziona **Fatture di importazione**, quindi seleziona **Modifica**.
3. Nella sezione **Canale dati** della scheda **Parametri**, nel campo **Canale dati**, immetti un valore di stringa.
4. Nella scheda **Regole di applicabilità** imposta i campi per l'impostazione. Puoi usare la clausola predefinita **Canale** passando il valore che hai impostato per il campo **Canale dati** nel passaggio precedente al campo **Valore**.

    ![Impostazione delle regole di applicabilità.](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Seleziona **Convalida** per garantire che tutti i campi necessari siano stati impostati.

### <a name="deploy-the-feature"></a>Distribuire la funzionalità

1. Completa, pubblica e distribuisci la funzionalità nell'ambiente del servizio. Per ulteriori informazioni, vedi la sezione [Distribuire la funzionalità di fatturazione elettronica nell'ambiente del servizio](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) dell'articolo "Introduzione alla fatturazione elettronica" precedentemente menzionato.
2. Distribuisci la funzionalità nell'applicazione connessa. Per ulteriori informazioni, vedi la sezione [Distribuire la funzionalità di fatturazione elettronica nell'applicazione connessa](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) dell'articolo "Introduzione alla fatturazione elettronica" precedentemente menzionato.

### <a name="set-up-finance"></a>Impostare Finance

1. Accedi all'ambiente Finance.
2. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Provider di configurazione**, selezionare **Provider di configurazione**.
3. Seleziona **Repository** \> **Globale** \> **Apri**.
4. Seleziona e importa le configurazioni **Modello contesto fattura cliente** e **Importazione fatture fornitore (IT)**.
5. Vai a **Amministrazione organizzazione** \> **Impostazione** \> **Parametri documento elettronico**.
6. Nella scheda **Funzionalità** trova e seleziona la funzionalità **Fattura elettronica italiana**, quindi seleziona la casella di controllo **Abilita**.
7. Nella scheda **Documento elettronico** assicurati che i campi per **Giornale di registrazione fatture cliente** e **Fattura di progetto** siano impostati in base alle informazioni in [Configurare l'impostazione dell'applicazione](e-invoicing-get-started.md#configure-the-application-setup).

### <a name="set-up-vendor-invoice-import"></a>Configurare l'importazione di fatture fornitore 

1. In Finance, nell'area di lavoro **Creazione di report elettronici** nella sezione **Provider di configurazione**, contrassegna il provider di configurazione della tua azienda come attivo.
2. Selezionare **Configurazioni report**.
3. Seleziona **Modello contesto fattura cliente**, e quindi **Crea configurazione**.
4. Seleziona **Deriva da nome: Contesto fattura cliente, Microsoft** per creare una configurazione derivata.
5. Nella versione **Bozza**, seleziona **Progettazione**.
6. Nell'albero **Modello di dati**, seleziona **Mappa modello a origine dati**.
7. Nell'albero **Definizioni**, seleziona **DataChannel** e quindi seleziona **Progettazione**.
8. Nell'albero **Origine dati**, espandi il contenitore **\$Context\_Channel**.
9. Nel campo **Valore**, seleziona **Modifica**. 
10. Immetti il nome del canale dati. Il nome deve contenere un massimo di 10 caratteri. Deve corrispondere al valore del parametro **Canale dati** del canale dati per la funzionalità di fatturazione elettronica in RCS.
11. Salva le modifiche e poi vai a **Configurazioni report** \> **Versione configurazione completata**.
12. Nella scheda **Canali esterni**, nella sezione **Canali**, seleziona **Aggiungi**.
13. Nel campo **Canale** immetti il valore **\$Context Channel**.
14. Immetti i valori nei campi **Descrizione** e **Società**.
15. Nel campo **Contesto documento**, seleziona la nuova configurazione derivata da **Modello contesto fattura cliente**. La descrizione del mapping dovrebbe essere **Contesto canale dati**.
16. Nella scheda **Importa origini**, seleziona **Aggiungi** e quindi imposta i seguenti valori:

    - **Nome:** OutputFile
    - **Nome entità dati:** Intestazione fattura fornitore (**Entità dati:** VendorInvoiceHeaderEntity)
    - **Mapping modello:** Importazione fattura fornitore (IT)

> [!NOTE]
> Se si importano fatture fornitore da origini diverse, è possibile creare diversi canali esterni e diverse configurazioni derivate che hanno differenti valori **\$Context Channel**. Ad esempio, potresti voler importare fatture fornitore per diverse persone giuridiche.

## <a name="proxy-server-setup"></a>Configurazione del server proxy

Questa sezione fornisce informazioni che ti aiuteranno a impostare e configurare il servizio proxy per la comunicazione tra il Sistema Exchange (SDI) e il servizio di Fatturazione elettronica.

### <a name="create-an-app-registration"></a>Creare una registrazione app

1. Usa lo script di Windows PowerShell seguente per creare un certificato autofirmato per l'autenticazione da servizio a servizio (S2S).

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. Salva il file del certificato .pfx nel key vault, quindi elimina la copia locale.
3. Accedi al [portale di Azure](https://portal.azure.com) come amministratore.
4. Crea una registrazione app per il servizio proxy SDI.

    1. Vai a **Registrazioni app**, crea una registrazione, quindi imposta i seguenti valori:

        - **Nome:** Client proxy SDI
        - **Tipi di account supportati:** Account solo in questa directory organizzativa (tenant singolo)

    2. Seleziona **Registra**, quindi seleziona la registrazione app appena creata.
    3. Vai ad **Autorizzazioni API** e seleziona **Concedi il consenso dell'amministratore**.
    4. Vai a **Certificati e segreti**, seleziona **Carica certificato** e carica il file del certificato .cer per l'autenticazione S2S.
    5. Vai ad **Applicazioni aziendali** e seleziona l'app che hai creato.
    6. Salva i valori **ID applicazione** (ID cliente) e **ID oggetto** per l'app.
    7. Il team del servizio di fatturazione deve concedere all'app l'accesso al servizio. Invia i valori dei seguenti parametri a <D365EInvoiceSupport@microsoft.com>:

        - ID tenant AAD
        - ID ambiente LCS
        - ID applicazione
        - ID oggetto

5. In RCS, aggiungi l'app all'elenco delle applicazioni per il tuo ambiente del servizio.

    1. Vai a **Funzionalità di globalizzazione** \> **Ambienti** \> **Fatturazione elettronica** \> **Ambienti del servizio** e seleziona il tuo ambiente.
    2. Nella sezione **Applicazioni** aggiungi una riga alla griglia e inserisci il nome e l'ID oggetto dell'app.

        ![Aggiunta dell'applicazione all'ambiente del servizio.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Seleziona **Salva** e quindi **Pubblica**.

### <a name="create-an-azure-virtual-machine"></a>Creare una macchina virtuale di Azure

1. Nel [portale di Azure](https://portal.azure.com), passa a **Macchine virtuali**, quindi seleziona **Crea nuovo**.
2. Nella scheda **Nozioni di base** seleziona l'abbonamento e il gruppo di risorse. I valori devono essere la sottoscrizione e il gruppo di risorse in cui si trovano il key vault e l'archivio BLOB.
3. Seleziona l'area. Questo valore deve essere l'area geografica in cui è distribuito l'ambiente Finance.
4. Aggiungi il nome utente e la password dell'amministratore e salvali nel key vault.
5. Nel campo **Seleziona porte in entrata** seleziona **HTTPS (443)** e **RPD (3389)**.

    > [!NOTE]
    > Ti consigliamo di disabilitare la porta **RDP (3389)** quando il sistema va in produzione. È possibile riattivarla se è necessario connettersi alla macchina virtuale (VM) per la risoluzione dei problemi.

    ![Impostazione dei campi nella scheda Nozioni di base per creare una macchina virtuale di Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. Nella scheda **Dischi** della scheda dettagli **Avanzate** seleziona la casella di controllo **Usa dischi gestiti**. Lascia la casella di controllo **Disco del sistema operativo effimero** deselezionata.

    ![Impostazione dei campi nella scheda Dischi per creare una macchina virtuale di Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. Nella scheda **Rete** sotto il campo **IP pubblico** seleziona **Crea nuovo**.

    ![Impostazione dei campi nella scheda Rete per creare una macchina virtuale di Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. Nella finestra di dialogo **Crea indirizzo IP pubblico**, nel gruppo di campi **Unità di stockkeeping** seleziona l'opzione **Standard**. Nel gruppo di campi **Assegnazione**, seleziona l'opzione **Statico**.

    ![Creazione di un indirizzo IP pubblico.](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. Nella scheda **Gestione** deseleziona la casella di controllo **Spegnimento automatico** per disabilitare lo spegnimento automatico.
10. Imposta il campo **Aggiornamenti del sistema operativo guest** su **Manuale**, quindi imposta eventuali altri criteri.
11. Rivedi e crea la VM.
12. Nella nuova VM, vai a **Identità** \> **Sistema assegnato**, e imposta l'opzione **Stato** su **Attivato**.
13. Concedi alla VM l'accesso al key vault.

    1. Nel key vault, vai a **Controllo accessi (IAM)** \> **Assegnazioni ruolo**.
    2. Seleziona **Aggiungi assegnazione ruolo** e imposta i seguenti campi:

        1. Nel campo **Ruolo** specifica **Segreti key vault utente**.
        2. Nel campo **Assegna accesso a** specifica **Macchina virtuale**.
        3. Nel campo **Sottoscrizione** specifica la tua sottoscrizione.
        4. Nel campo **Seleziona** specifica la tua VM.

    3. Vai a **Criteri di accesso**.
    4. Seleziona **Aggiungi criteri di accesso** e imposta i seguenti campi:

        1. Nel campo **Entità selezionata**, seleziona la tua VM.
        2. Nella sezione **Certificato** seleziona le autorizzazioni **Elenco** e **Ottieni**.

14. Nel [Portale di Azure](https://portal.azure.com), vai a **Indirizzi IP pubblici** e seleziona l'indirizzo IP che è stato creato nella macchina virtuale.
15. Vai a **Configurazione** e imposta il nome DNS (Domain Name System).

### <a name="prepare-the-proxy-service-environment"></a>Preparare l'ambiente del servizio proxy

Segui questi passaggi sulla macchina in cui è ospitato il servizio proxy.

1. Connettiti alla macchina virtuale utilizzando Connessione desktop remoto.
2. Apri lo snap-in Certificato computer locale. Per ulteriori informazioni, vedi [Procedura: visualizzare i certificati con lo snap-in MMC](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).
3. Importa il certificato **canentrate.cer** per la produzione e il certificato **CAEntratetest.cer** per il test nello [store delle autorità di certificazione radice attendibili](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). **CAEntratetest.cer** è il certificato CA radice fornito dall'autorità.
4. Nel Pannello di controllo, apri **Attiva o disattiva le funzionalità di Windows**, o vai a **Gestione server** \> **Aggiungi ruoli e funzionalità** per il sistema operativo (SO) del server e attiva le funzionalità di Internet Information Services (IIS):

    - Strumenti di gestione web
        - Console di gestione IIS
    - Servizi World Wide Web
        - Funzionalità di sviluppo di applicazioni
            - Estensibilità .NET 4.7 (o 4.8)
            - ASP
            - ASP.NET 4.7 (o 4.8)
            - CGI
            - Estensioni ISAPI
            - Filtri ISAPI
        - Funzionalità HTTP comuni
            - Documento predefinito
            - Navigazione nella directory
            - Errori HTTP
            - Contenuto statico
        - Integrità e diagnostica
            - Registrazione HTTP
            - Tracciatura
        - Funzionalità delle prestazioni
            - Compressione del contenuto statico
        - Sicurezza
            - Filtro delle richieste

    ![Attivazione delle funzionalità IIS.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Configurare il servizio Proxy SDI in IIS

1. In Microsoft Dynamics Lifecycle Services (LCS), vai alla raccolta Risorse condivise e seleziona il tipo di cespite **Pacchetto dati**.
2. Trova **Proxy SDI del servizio di fatturazione elettronica** e scaricalo nella VM.
3. Configura il servizio.

    1. Decomprimi la cartella di archivio **Proxy SDI del servizio di fatturazione elettronica** che hai scaricato.
    2. Nella cartella **src\\FattureService** apri il file **appsettings.json** e imposta i seguenti parametri:

        - **KeyVaultUri** – Specifica l'indirizzo del key vault che archivia il certificato client per il servizio di fatturazione.
        - **TenantId** – Specifica l'identificatore univoco globale (GUID) del tenant del cliente.
        - **EnvironmentId** – Specifica l'ID dell'ambiente LCS.
        - **ClientId** – Specifica l'ID app della registrazione dell'app dei servizi intermedi nel tenant del cliente.
        - **ClientCertificateName** – Specifica il nome del certificato S2S nel key vault.
        - **SecurityServiceClientOptions.Endpoint** – Specifica l'URL del servizio di sicurezza.
        - **SecurityServiceClientOptions.Resource** – Specifica l'ambito per cui ottenere il token.
        - **InvoicingServiceClientOptions.Endpoint** – Specifica l'endpoint del servizio di fatturazione. Questo valore deve essere lo stesso endpoint utilizzato per RCS e Finance.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** – Specifica il nome dell'ambiente di servizio. Questo valore deve essere il nome del tuo ambiente Finance.
        - **NotificationsFolder** – Specifica la cartella in cui salvare i file di notifica in arrivo.

    3. Nel file **web.config** trova la riga seguente e aggiungi l'identificazione personale del certificato del server proxy.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > Quando il sistema va in produzione, è possibile modificare alcuni valori nel file web.config per ridurre la quantità di informazioni di registro raccolte e risparmiare spazio su disco. Nel nodo **\<system.diagnostics\>\<source\>** modifica il valore di **switchValue** su **Critical,Error**. Per ulteriori informazioni, vedi [Visualizzatore di tracce del servizio MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Apri Gestione IIS. Nell'albero a sinistra, rimani nel nodo radice. A destra, seleziona **Certificati del server**.

    ![Selezione dei certificati di servizio in Gestione IIS.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Apri il menu e seleziona **Importa**.
6. Nella finestra di dialogo **Importa certificato**, nel campo **File di certificato (.pfx)** specifica il percorso del file .pfx del certificato del server proxy.

    ![Specifica del file del certificato del servizio proxy.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Seleziona e tieni premuto (o fai clic con il tasto destro del mouse) **Siti**, quindi seleziona **Aggiungi sito Web**.
8. Nella finestra di dialogo **Aggiungi sito Web**, nel campo **Nome sito** immetti un nome per il sito.
9. Nel campo **Percorso fisico** indica la cartella **src\\FattureService**.
10. Nel campo **Tipo di associazione** seleziona **https**.
11. Nel campo **Nome host** , specifica il nome host.
12. Lascia i campi **Indirizzo IP** e **Porta** impostati sui valori predefiniti.
13. Assicurati che la casella di controllo **Richiedi indicazione nome server** sia deselezionata, poiché SDI non supporta tale tecnologia.
14. Nel campo **Certificato SSL** seleziona il certificato del server proxy che hai importato.
15. Nel campo **Pool di applicazioni** specifica un pool per il sito e prendi nota del suo nome (ad esempio, **SdiAppPool**).

    ![Aggiunta di un sito web.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. Dopo aver terminato la creazione del sito Web, apri il menu per **Impostazioni SSL**.

    ![Apertura del menu per Impostazioni SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Seleziona la casella di controllo **Richiedi SSL** e poi, nel gruppo di campi **Certificati client** seleziona l'opzione **Richiedi**.

    ![Configurazione delle impostazioni SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Apri **Esplorazione directory** e seleziona **Abilita**.
19. In qualsiasi browser web, vai a **serverDNS/TrasmissioneFatture.svc**. Deve apparire una pagina standard sul servizio.

    ![Controllo del servizio in un browser.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Crea le seguenti cartelle per archiviare log e file:

    - **C:\\Logs\\** – Memorizza i file di log qui. Questi file possono essere visualizzati da [Visualizzatore di tracce del servizio MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).
    - **C:\\Files\\** – Memorizza qui tutti i file di risposta.

21. In Esplora file, concedi **SERVIZIO DI RETE** e **IIS AppPool\\SdiAppPool** (o **IIS AppPool\\DefaultAppPool** se stai usando il pool predefinito) l'accesso alle cartelle **Registri** e **File**.

    1. Seleziona e tieni premuta (o fai clic con il tasto destro del mouse) una cartella, quindi seleziona **Proprietà**.
    2. Nella finestra di dialogo **Proprietà** nella scheda **Sicurezza** seleziona **Modifica**.
    3. Aggiungi gli utenti se non sono elencati.
    4. Ripeti i passaggi da 1 a 3 per l'altra cartella.

    ![Aggiunta di autorizzazioni all'utente del servizio.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Informativa sulla privacy 

L'abilitazione della funzionalità **Fattura elettronica italiana** potrebbe richiedere l'invio di dati limitati. Questi dati includono l'ID di registrazione fiscale dell'organizzazione. Un amministratore può abilitare e disabilitare la funzionalità fattura elettronica italiana. Per disabilitare la funzionalità segui la procedura seguente.

1. Vai a **Amministrazione organizzazione** \> **Impostazione** \> **Parametri documento elettronico**.
2. Nella scheda **Funzionalità** seleziona le righe contenenti la funzionalità **Fattura elettronica italiana**, quindi seleziona **Disabilita ora**.

I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Per ulteriori informazioni consulta la sezione "Informativa sulla privacy" nella documentazione delle funzionalità specifiche del paese/area geografica.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica della fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione all'amministrazione dei servizi per la fatturazione elettronica](e-invoicing-get-started-service-administration.md)
- [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
