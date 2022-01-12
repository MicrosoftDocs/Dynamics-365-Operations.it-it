---
title: Esempio di integrazione di un'unità di controllo per la Svezia
description: In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per la Svezia in Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: 32c2cf31d82d17d3391536e7a9f1722e1462c336
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944768"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Esempio di integrazione di un'unità di controllo per la Svezia

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per la Svezia in Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Questa funzionalità di integrazione fiscale di esempio sostituisce il precedente [esempio di integrazione POS con unità di controllo per la Svezia](retail-sdk-control-unit-sample.md). L'esempio precedente non sfrutta il [framework di integrazione fiscale](./fiscal-integration-for-retail-channel.md) e diventerà obsoleto negli aggiornamenti successivi. Per informazioni su come migrare dall'esempio precedente all'esempio che corrisponde a Dynamics 365 Commerce versione **10.0.22 e versioni precedenti**, vedi [Migrazione dal precedente esempio di integrazione](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

La funzionalità Commerce per la Svezia include un esempio di integrazione del punto vendita (POS) con dispositivi fiscali specifici per la Svezia noti come *unità di controllo*. Questo esempio estende la [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md). Si presume che un'unità di controllo sia fisicamente collegata a una stazione hardware a cui è associato il POS. Questo esempio utilizza l'API dell'unità di controllo [CleanCash tipo A](https://www.retailinnovation.se/produkter) di Retail Innovation HTT AB. Viene utilizzata la versione 1.1.4 dell'API CleanCash.

L'esempio viene fornito sotto forma di codice sorgente e fa parte del kit SDK.

Microsoft non rilascia hardware, software o documentazione di Retail Innovation HTT AB. Per informazioni su come ottenere l'unità di controllo e utilizzarla, contatta [Retail Innovation HTT AB](https://www.retailinnovation.se/).

## <a name="scenarios"></a>Scenari

L'esempio di integrazione dell'unità di controllo per la Svezia include le seguenti funzionalità:

- Le copie di vendite, resi e ricevute vengono registrate automaticamente in un'unità di controllo collegata alla stazione hardware abbinata al POS.
- Il codice di controllo e il numero di produzione dell'unità di controllo per una transazione registrata vengono acquisiti dall'unità di controllo e salvati nella transazione. Questi dati sono anche indicati come *risposta fiscale*. La risposta fiscale è visionabile sulla pagina **Transazioni punto vendita**.
- I campi personalizzati per il codice di controllo e il numero di produzione dell'unità di controllo possono essere aggiunti a un layout di ricevuta. In questo modo è possibile stampare sulla ricevuta la risposta fiscale di una transazione.
- La risposta fiscale per una transazione è mostrata sul report del canale **Giornale di registrazione elettronico (Svezia)**.
- Sono disponibili diverse opzioni di gestione degli errori. Di seguito sono riportati alcuni esempi.

    - Riprova la registrazione fiscale, se è possibile riprovare. Puoi riprovare la registrazione fiscale se, ad esempio, l'unità di controllo non è collegata, non è pronta o non risponde.
    - Posticipare la registrazione fiscale.
    - Ignorare la registrazione fiscale, o contrassegnare la transazione come registrata, e includere i codici informativi per acquisire il motivo dell'errore e ulteriori informazioni.
    - Verifica la disponibilità dell'unità di controllo prima dell'apertura di una nuova transazione di vendita o della finalizzazione di una transazione di vendita.

### <a name="limitations-of-the-sample"></a>Limitazioni dell'esempio

L'esempio di integrazione dell'unità di controllo per la Svezia non supporta attualmente gli scenari di ordini cliente.

## <a name="setting-up-the-integration-with-control-units"></a>Impostazione dell'integrazione con unità di controllo

Per ulteriori informazioni sulla configurazione richiesta per la Svezia, vedi [Impostazione di Commerce per la Svezia](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

### <a name="configuring-swedenspecific-receipts"></a>Configurazione delle ricevute specifiche per la Svezia

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurare i campi personalizzati in modo che possano essere utilizzati nei formati per ricevute di vendita

È possibile configurare il testo della lingua e i campi personalizzati utilizzati nei formati di ricevuta POS. La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua. In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.

Nella pagina **Testo lingua** aggiungi i record seguenti per le etichette dei campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi. È possibile modificarli in base alle esigenze. Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.

Aggiungi le seguenti etichette POS nella sezione **POS** della pagina **Testo in lingua**.

| ID lingua | ID testo | Testo                  |
|-------------|---------|-----------------------|
| en-US       | 900001  | Codice di controllo registro |
| en-US       | 900002  | Dispositivo registro       |

Nella pagina **Campi personalizzati**, aggiungi i record seguenti per i campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**.

| Name                         | Tipo    | ID testo didascalia |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Ricevimento | 900001          |
| SE_FISCALREGISTERID          | Ricevimento | 900002          |

> [!NOTE]
> È importante specificare i nomi dei campi personalizzati corretti, come elencato nella tabella sopra. Un nome di campo personalizzato errato causerà la mancanza di dati nelle ricevute.

#### <a name="configure-receipt-formats"></a>Configurare i formati di ricevuta

Per tutti i formati di ricevuta richiesti, modifica il valore del campo **Comportamento stampa** su **Stampa sempre**.

Nella progettazione formato ricevuta, aggiungi i seguenti campi personalizzati alla sezione **piè di pagina**. Tieni presente che i nomi dei campi corrispondono ai testi in lingua definiti nella sezione precedente di questo argomento.

- **Codice di controllo registro** – Questo campo stampa il codice di controllo.
- **Dispositivo registro** – In questo campo viene stampato il numero di produzione dell'unità di controllo.

Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedere [Modelli e stampa di ricevute](../receipt-templates-printing.md)

### <a name="set-up-fiscal-integration-for-sweden"></a>Impostare l'integrazione fiscale per la Svezia

L'esempio di integrazione dell'unità di controllo per la Svezia si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\CleanCash** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) di un provider di documenti fiscali, che è un'estensione di Commerce Runtime (CRT) e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione dell'unità di controllo per la Svezia (legacy)](emea-swe-fi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

Completa la procedura di configurazione dell'integrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Inoltre, prendi nota delle impostazioni per il processo di registrazione fiscale che sono [specifiche dell'esempio di integrazione dell'unità di controllo](#set-up-the-registration-process).
1. [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configura i componenti del canale](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Impostare il processo di registrazione

Per abilitare il processo di registrazione, segui questi passaggi per configurare Commerce headquarters. Per ulteriori informazioni vedi [Impostare l'integrazione fiscale per i canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Scarica i file di configurazione per il provider di documenti fiscali e il connettore fiscale:

    1. Apri il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione (ad esempio, **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Apri **src \> FiscalIntegration \> CleanCash**.
    1. Scarica il file di configurazione del provider di documenti fiscali in **CommerceRuntime \> DocumentProvider.CleanCashSample \> Configuration \> DocumentProviderFiscalCleanCashSample.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)).
    1. Scarica il file di configurazione del connettore fiscale in **HardwareStation \> Connector.CleanCashSample \> Configuration \> ConnectorCleanCashSample.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)).

    > [!WARNING]
    > A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. I file di configurazione per questo esempio di integrazione fiscale si trovano nelle seguenti cartelle di Retail SDK su una macchina virtuale per sviluppatori in LCS:
    >
    > - **File di configurazione provider documenti fiscali:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml
    > - **File di configurazione connettore fiscale:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml
    > 
    > Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di commercio**. Nella Scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Provider di documenti fiscali**, e carica il file di configurazione del provider di documenti fiscali che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**, e carica il file di configurazione del connettore fiscale che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**. Crea un nuovo profilo funzionale del connettore. Seleziona il provider di documenti e il connettore che hai caricato in precedenza. Aggiorna le [impostazioni di mapping dei dati](#default-data-mapping) se necessario.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**. Crea un nuovo profilo tecnico del connettore, quindi seleziona il connettore fiscale caricato in precedenza. Aggiorna le [impostazioni del connettore](#fiscal-connector-settings) se necessario.
6. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**. Crea un nuovo gruppo di connettori fiscali per il profilo funzionale del connettore che hai creato in precedenza.
7. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**. Crea un nuovo processo di registrazione fiscale e un passaggio del processo di registrazione fiscale e seleziona il gruppo di connettori fiscali creato in precedenza.
8. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. Seleziona il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Nella scheda Dettaglio **Processo di registrazione fiscale**, seleziona il processo di registrazione fiscale creato precedentemente.
9. Andare a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**. Seleziona un profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata. Nella scheda Dettaglio **Periferiche fiscali**, seleziona il profilo tecnico del connettore creato in precedenza.
10. Aprire la programmazione della distribuzione (**Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**) e selezionare i processi **1070** e **1090** per trasferire i dati al database del canale.

#### <a name="default-data-mapping"></a>Mapping dei dati predefiniti

Il mapping dei dati predefiniti seguente è incluso nella configurazione di provider di documenti fiscali fornita nell'esempio di integrazione fiscale:

- **Mapping del codice dell'imposta sul valore aggiunto (IVA)** – Questo mapping imposta i codici IVA (IVA) specifici del dispositivo sui codici IVA corrispondenti. Il mapping del codice IVA deve avere il seguente formato:

    ```
    1 : code1 ; 2 : code2
    ```

    Di seguito è riportata una spiegazione di questo formato:

    - *1* e *2* sono codici IVA specifici del dispositivo.
    - Un punto e virgola (;) viene utilizzato come separatore.
    - *codice1* e *codice2* sono codici IVA configurati in Commerce headquarters. È necessario modificare il mapping di esempio in base ai codici imposta configurati nell'applicazione.

    Le unità di controllo supportano fino a quattro diversi codici IVA. Pertanto, il mapping del codice IVA può essere impostato nel seguente modo:

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > È possibile mappare più codici IVA allo stesso codice IVA specifico del dispositivo.

#### <a name="fiscal-connector-settings"></a>Impostazioni del connettore fiscale

Le seguenti impostazioni sono incluse nella configurazione del connettore fiscale fornita nell'esempio di integrazione fiscale:

- **Stringa di connessione** – Le impostazioni di connessione dell'unità di controllo.
- **Timeout** – La quantità di tempo, in millisecondi, che il driver trascorre in attesa di una risposta dall'unità di controllo.

### <a name="configure-channel-components"></a>Configurare i componenti del canale

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione dell'unità di controllo per la Svezia (legacy)](emea-swe-fi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

#### <a name="set-up-the-development-environment"></a>Impostare un ambiente di sviluppo

Segui questi passaggi per impostare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

1. Clona o scarica il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione. Per altre informazioni vedi [Scaricare gli esempi Retail SDK e i pacchetti di riferimento da GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Apri la soluzione di integrazione dell'unità di controllo in **Dynamics365Commerce.Solutions\\FiscalIntegration\\CleanCash\\CleanCash.sln** e compila.
1. Installa le estensioni CRT:

    1. Trova il programma di installazione dell'estensione CRT:

        - **Commerce Scale Unit:** Nella directory **CleanCash\\ScaleUnit\\ScaleUnit.CleanCash.Installer\\bin\\Debug\\net461** trova il programma di installazione **ScaleUnit.CleanCash.Installer**.
        - **CRT locale su POS moderno:** Nella cartella **CleanCash\\ModernPOS\\ModernPOS.CleanCash.Installer\\bin\\Debug\\net461** trova il programma di installazione **ModernPOS.CleanCash.Installer**.

    2. Avvia il programma di installazione dell'estensione CRT dalla riga di comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **CRT locale su Modern POS:**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Installa le estensioni stazione hardware:

    1. Nella cartella **CleanCash\\HardwareStation\\HardwareStation.CleanCash.Installer\\bin\\Debug\\net461** trova il programma di installazione **HardwareStation.CleanCash.Installer**.
    1. Avvia il programma di installazione dell'estensione dalla riga di comando:

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Ambiente di produzione

Segui i passaggi in [Configurare una pipeline di compilazione per un esempio di integrazione fiscale](fiscal-integration-sample-build-pipeline.md) per generare e rilasciare Cloud Scale Unit e pacchetti distribuibili self-service per l'esempio di integrazione fiscale. Il file YAML del modello **CleanCash build-pipeline.yml** è disponibile nella cartella **Pipeline\\YAML_Files** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-the-extensions"></a>Progettazione delle estensioni

L'esempio di integrazione dell'unità di controllo per la Svezia si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\CleanCash** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) di un provider di documenti fiscali, che è un'estensione di CRT e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione dell'unità di controllo per la Svezia (legacy)](emea-swe-fi-sample-sdk.md). Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

### <a name="crt-extension-design"></a>Progettazione delle estensioni CRT

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per il servizio e di gestire le risposte dall'unità di controllo.

#### <a name="request-handler"></a>Gestore richieste

È disponibile un solo gestore di richiesta **DocumentProviderCleanCash** per il provider di documenti. Questo gestore viene utilizzato per generare documenti fiscali per l'unità di controllo.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico del servizio che deve essere registrato nell'unità di controllo.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente sono supportati gli eventi di vendita e gli eventi di controllo.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il provider di documenti fiscali si trova in **src\\FiscalIntegration\\CleanCash\\CommerceRuntime\\DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo di questo file è di consentire la configurazione delle impostazioni per il provider di documenti da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con l'unità di controllo. Utilizza il protocollo HTTP per inviare documenti generati dall'estensione CRT per l'unità di controllo. Gestisce inoltre le risposte ricevute dall'unità di controllo.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **CleanCashHandler** è il punto di ingresso per la trasmissione delle richieste all'unità di controllo.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti alle unità di controllo e restituisce la risposta.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità dell'unità di controllo.
- **InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione dell'unità di controllo.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il connettore fiscale si trova in **src\\FiscalIntegration\\CleanCash\\HardwareStation\\Connector.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore fiscale da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
