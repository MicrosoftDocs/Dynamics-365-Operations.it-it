---
title: Linee guida per la distribuzione dei registratori di cassa per la Norvegia
description: Questo articolo fornisce indicazioni su come abilitare la funzionalità del registratore di cassa per la localizzazione Microsoft Dynamics 365 Commerce per la Norvegia.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 0e66ef93e65fecaca23f0434c386507a0672d251
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631317"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Linee guida per la distribuzione dei registratori di cassa per la Norvegia

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Devi implementare i passaggi descritti in questo articolo solo se stai utilizzando Microsoft Dynamics 365 Commerce versione 10.0.29 o successiva. In Commerce versione 10.0.28 o precedente, devi utilizzare la versione precedente di Retail SDK in una macchina virtuale per sviluppatori (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedi [Linee guida per la distribuzione dei registratori di cassa per la Norvegia (legacy)](./emea-nor-loc-deployment-guidelines.md). Se stai utilizzando Commerce versione 10.0.28 o precedente e stai migrando a Commerce versione 10.0.29 o successiva, devi seguire i passaggi in [Migrare da una funzionalità legacy di Commerce per la Norvegia](./emea-nor-fi-migration.md).

Questo articolo fornisce indicazioni su come abilitare la funzionalità del registratore di cassa per la localizzazione di Commerce per la Norvegia. La localizzazione consiste di vari estensioni del componente che ti consentono di eseguire azioni come stampare campi personalizzati sulle ricevute, registrare ulteriori eventi di controllo, transazioni di vendita e transazioni di pagamento in Point of Sale (POS), firma digitale delle transazioni di vendita e stampa di report in formati locali. Per ulteriori informazioni sulla localizzazione per la Norvegia, vedi [Funzionalità del registratore di cassa per la Norvegia](./emea-nor-cash-registers.md). Per ulteriori informazioni su come configurare Commerce per la Norvegia, vedi [Configurare Commerce per la Norvegia](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

## <a name="set-up-fiscal-registration-for-norway"></a>Configurare la registrazione fiscale per la Norvegia

L'esempio di registrazione fiscale per la Norvegia si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Commerce SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\SequentialSignatureNorway** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). L'[esempio](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) consiste di un provider di documenti fiscali e di un connettore fiscale, che sono estensioni di Commerce Runtime (CRT). Per ulteriori informazioni su come utilizzare Commerce SDK, vedi [Scaricare esempi di Commerce SDK e pacchetti di riferimento da GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

Completa la procedura di configurazione della registrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di Commerce](./setting-up-fiscal-integration-for-retail-channel.md):

1. [Configurare un processo di registrazione fiscale](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Assicurati di prendere nota delle impostazioni del processo di registrazione fiscale che sono [specifiche per la Norvegia](#configure-the-fiscal-registration-process).
1. [Configurare le impostazioni di gestione degli errori](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Abilitare l'esecuzione manuale della registrazione fiscale differita](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Configura i componenti del canale](#configure-channel-components).

### <a name="configure-the-fiscal-registration-process"></a>Configurare il processo di registrazione fiscale

Segui questi passaggi per abilitare il processo di registrazione fiscale per la Norvegia in Commerce headquarters.

1. Scarica i file di configurazione per il provider di documenti fiscali e il connettore fiscale da Commerce SDK:

    1. Apri il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Apri l'ultimo ramo di rilascio disponibile.
    1. Apri **src \> FiscalIntegration \> SequentialSignatureNorway \> CommerceRuntime**.
    1. Scarica il file di configurazione del provider di documenti fiscali in **DocumentProvider.SequentialSignNorway \> Configuration \> DocumentProviderSequentialSignatureNorwaySample.xml**.
    1. Scarica il file di configurazione del connettore fiscale in **Connector.SequentialSignNorway \> Configuration \> ConnectorSequentialSignatureNorwaySample.xml**.

1. Accedi a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi**. Nella Scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**, e carica il file di configurazione del connettore fiscale che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Provider di documenti fiscali**, e carica il file di configurazione del provider di documenti fiscali che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**. Crea un nuovo profilo funzionale del connettore, quindi seleziona il provider di documenti e il connettore caricati in precedenza.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**. Crea un nuovo profilo tecnico del connettore, quindi seleziona il connettore caricato in precedenza. Imposta il tipo di connettore su **Interno**.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**, crea un nuovo gruppo di connettori fiscali per il profilo funzionale del connettore creato in precedenza.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**. Crea un nuovo processo di registrazione fiscale e un passaggio del processo di registrazione fiscale e seleziona il gruppo di connettori fiscali creato in precedenza.
1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. Seleziona il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Nella scheda Dettaglio **Processo di registrazione fiscale**, seleziona il processo di registrazione fiscale creato precedentemente. Nella scheda Dettaglio **Servizi fiscali**, seleziona il profilo tecnico del connettore creato in precedenza. 
1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**. Apri la programmazione della distribuzione e seleziona i processi **1070** e **1090** per trasferire i dati ai database del canale.

### <a name="configure-the-digital-signature-parameters"></a>Configurare i parametri della firma digitale

È necessario configurare i certificati che verranno utilizzati per la firma digitale delle transazioni di vendita in un negozio. Per eseguire la firma viene usato un certificato digitale archiviato in Azure Key Vault. Per la modalità offline di Modern POS, la firma può essere eseguita anche utilizzando un certificato digitale archiviato nell'archivio locale della macchina su cui è installato Modern POS.

Prima di poter utilizzare un certificato digitale archiviato nell'archivio Key Vault, è necessario completare i passaggi seguenti.

1. È necessario creare l'archivio Key Vault. Consigliamo di distribuire l'archivio nella stessa area geografica di Commerce Scale Unit.
1. Il certificato deve essere caricato nell'archivio Key Vault come segreto in stringa base64.
1. L'applicazione Application Object Server (AOS) deve essere autorizzata a leggere i segreti dall'archivio Key Vault.

Per ulteriori informazioni su come lavorare con Key Vault, vedi [Introduzione ad Azure Key Vault](/azure/key-vault/key-vault-get-started).

Successivamente, nella pagina **Parametri Key Vault** è necessario specificare i parametri per accedere all'archivio Key Vault:

- **Nome** e **Descrizione** – Il nome e la descrizione dell'archivio Key Vault.
- **URL Key Vault** – L'URL dell'archivio Key Vault.
- **Client Key Vault** – Un ID client interattivo dell'applicazione Azure Active Directory (Azure AD) associata a un archivio key vault per scopi di autenticazione. Questo client deve avere accesso per leggere i segreti dall'archivio.
- **Chiave segreta Key Vault** – Una chiave segreta associata all'applicazione Azure AD utilizzata per l'autenticazione nell'archivio Key Vault.
- **Nome**, **Descrizione**, e **Riferimento segreto** – Il nome, la descrizione e il riferimento segreto del certificato.

Successivamente, è necessario configurare un connettore per i certificati archiviati in Key Vault o nell'archivio certificati locale. Questo connettore viene utilizzato per la firma lato canale.

1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**.
1. Nella Scheda dettaglio **Impostazioni** specifica i seguenti parametri per le firme digitali:

    - **Nome segreto** – Seleziona il nome segreto che hai configurato in precedenza nella pagina **Parametri Key Vault**.
    - **Identificazione personale del certificato locale** – Fornisci un'identificazione personale per un certificato archiviato localmente.
    - **Algoritmo hash** – Specifica uno degli algoritmi di hash crittografici supportati da Microsoft .NET, ad esempio **SHA1**.
    - **Nome archivio certificati** – Questo campo è facoltativo. Usalo per specificare un nome di punto vendita predefinito che deve essere usato per cercare certificati locali.
    - **Posizione archivio certificati** – Questo campo è facoltativo. Usalo per specificare un'ubicazione di punto vendita predefinita che deve essere usata per cercare certificati locali.
    - **Prova prima il certificato locale** – Seleziona questa opzione per utilizzare il certificato dell'archivio locale per impostazione predefinita per la firma dei dati, invece del certificato del Key Vault.
    - **Attiva verifica integrità** – Per ulteriori informazioni sulla funzionalità di verifica integrità, vedi [Verifica integrità della registrazione fiscale](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - Solo l'algoritmo hash di crittografia **SHA1** è attualmente accettabile per la Norvegia.
> - Il nome e l'ubicazione del punto vendita predefiniti vengono aggiunti per semplificare il processo di ricerca dei certificati locali in CRT. X509StoreProvider ha un elenco di cartelle in cui sono archiviati i certificati. Se il nome e l'ubicazione del punto vendita predefiniti non sono specificati, X509StoreProvider prova a trovare un certificato nelle altre cartelle del relativo elenco.

### <a name="configure-channel-components"></a>Configurare i componenti del canale

#### <a name="development-environment"></a>Ambiente di sviluppo

Segui questi passaggi per configurare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

1. Clona o scarica il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione. Per altre informazioni, vedi [Scaricare esempi di Commerce SDK e pacchetti di riferimento da GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Apri la soluzione **SequentialSignatureNorway.sln** in **Dynamics365Commerce.Solutions\\FiscalIntegration\\SequentialSignatureNorway**, e compila.
1. Installa le estensioni CRT:

    1. Trova il programma di installazione dell'estensione CRT:

        - **Commerce Scale Unit:** Nella directory **SequentialSignatureNorway\\ScaleUnit\\ScaleUnit.SequentialSignNorway.Installer\\bin\\Debug\\net461** trova il programma di installazione **ScaleUnit.SequentialSignNorway.Installer**.
        - **CRT locale su POS moderno:** Nella cartella **SequentialSignatureNorway\\ModernPOS\\ModernPos.SequentialSignNorway.Installer\\bin\\Debug\\net461** trova il programma di installazione **ModernPos.SequentialSignNorway.Installer**.

    1. Avvia il programma di installazione dell'estensione CRT dalla riga di comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **CRT locale su Modern POS:**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Ambiente di produzione

Segui i passaggi in [Configurare una pipeline di compilazione per un esempio di integrazione fiscale](fiscal-integration-sample-build-pipeline.md) per generare e rilasciare Cloud Scale Unit e pacchetti distribuibili self-service per l'esempio di integrazione fiscale. Il file YAML del modello **SequentialSignatureNorway build-pipeline.yaml** è disponibile nella cartella **Pipeline\\YAML_Files** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Abilitare la firma digitale in modalità offline per Modern POS

Per abilitare la firma digitale in modalità offline per Modern POS, devi seguire questi passaggi dopo aver attivato Modern POS su un nuovo dispositivo.

1. Accedere a POS.
1. Nella pagina **Stato della connessione al database** assicurati che il database offline sia completamente sincronizzato. Quando il valore del campo **Download sospesi** è **0** (zero), il database è completamente sincronizzato.
1. Esci da POS.
1. Attendi finché il database offline sia completamente sincronizzato.
1. Accedere a POS.
1. Nella pagina **Stato della connessione al database** assicurati che il database offline sia completamente sincronizzato. Quando il valore del campo **Transazioni in sospeso nel database offline** è **0** (zero), il database è completamente sincronizzato.
1. Riapri Modern POS.
