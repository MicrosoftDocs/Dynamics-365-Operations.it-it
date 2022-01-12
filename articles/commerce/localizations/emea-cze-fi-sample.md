---
title: Esempio di integrazione del servizio di registrazione fiscale per la Repubblica Ceca
description: In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per la Repubblica Ceca in Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-4-1
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 0a04ebb7685ff0b72207d9268b4aea980679572e
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944991"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Esempio di integrazione del servizio di registrazione fiscale per la Repubblica Ceca

[!include[banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per la Repubblica Ceca in Microsoft Dynamics 365 Commerce.

Per soddisfare i requisiti fiscali locali per i registratori di cassa in Repubblica Ceca, la funzionalità Dynamics 365 Commerce per la Repubblica Ceca include un esempio di integrazione del point of sale (POS) con un servizio di registrazione fiscale esterno. L'esempio estende la [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md). Si basa sulla soluzione [EFR (Registro Fiscale Elettronico)](https://efsta.org/sicherheitsloesungen/) di [EFSTA](https://efsta.org/) e consente la comunicazione con il servizio EFR tramite il protocollo HTTPS. Il servizio EFR garantisce la registrazione elettronica delle vendite (EET - Elektronická evidence tržeb), ovvero la trasmissione online dei dati di vendita a un servizio web fiscale delle autorità fiscali.

Il servizio EFR deve essere ospitato sulla stazione hardware Commerce o su una macchina separata a cui è possibile connettersi dalla stazione hardware. L'esempio viene fornito sotto forma di codice sorgente e fa parte del kit SDK.

Microsoft non rilascia hardware, software o documentazione di EFSTA. Per informazioni su come ottenere la soluzione EFR e utilizzarla, contatta [EFSTA](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Scenari

Gli scenari seguenti sono coperti dall'esempio di integrazione di servizio di registrazione fiscale per la Repubblica Ceca:

- Registrazione delle transazioni di cassa nel servizio di registrazione fiscale.

    - Invia i dati dettagliati della transazione al servizio di registrazione fiscale. Questi dati includono informazioni sulla riga di vendita e informazioni su sconti, pagamenti e imposte. Il servizio di registrazione fiscale invia inoltre i dati al servizio web delle autorità fiscali e ne riceve una conferma che include il codice di idenficazione fiscale della transazione.
    - Acquisisci una risposta dal servizio di registrazione fiscale. Questa risposta include dati fiscali come il codice di identificazione fiscale e il codice di sicurezza della transazione, ecc.
    - Stampa sulla ricevuta i dati fiscali di una transazione registrata.

- Registrazione delle operazioni gift card e depositi dei clienti nel servizio di registrazione fiscale.

    - Emetti o aggiungi denaro a una gift card.
    - Registra un deposito conto cliente.
    - Crea un ordine cliente e registra un deposito per l'ordine.
    - Modifica un ordine cliente e sostituisci il deposito per l'ordine.
    - Annulla un ordine cliente e rimborsa il deposito per l'ordine.

- Gestione degli errori, ad esempio le seguenti opzioni.

    - Riprova la registrazione fiscale se è possibile riprova, ad esempio se il servizio di registrazione fiscale non è disponibile, non è pronto o non risponde.
    - Posticipare la registrazione fiscale.
    - Ignorare la registrazione fiscale, o contrassegnare la transazione come registrata, e includere i codici informativi per acquisire il motivo dell'errore e ulteriori informazioni.
    - Verifica la disponibilità del servizio di registrazione fiscale prima dell'apertura di una nuova transazione di vendita o della finalizzazione di una transazione di vendita.

### <a name="gift-cards"></a>Gift card

L'esempio di integrazione del servizio di registrazione fiscale implementa le seguenti regole relative alle gift card.

- Le righe di vendita relative alle operazioni *Emetti gift card* o *Aggiungi a gift card* in una transazione di vendita sono contrassegnate con un attributo speciale quando la transazione viene registrata nel servizio di registrazione fiscale.
- Un pagamento con gift card è considerato un pagamento regolare e contrassegnato da un attributo speciale quando la transazione viene registrata nel servizio di registrazione fiscale.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Depositi conto cliente e depositi ordine cliente

L'esempio di integrazione del servizio di registrazione fiscale implementa le seguenti regole relative a depositi conto cliente e a depositi ordine cliente.

- Una transazione correlata a un deposito su un conto cliente o a un deposito su ordine cliente viene registrata nel servizio di registrazione fiscale come transazione a riga singola ed è contrassegnata da un attributo speciale. Il gruppo IVA di deposito è specificato in questa riga.
- Quando viene creato un ordine cliente ibrido, ovvero un ordine cliente che contiene prodotti che possono essere prelevati dal negozio dal cliente, nonché prodotti che verranno ritirati o spediti successivamente, la transazione registrata nel servizio di registrazione fiscale contiene righe per i prodotti che vengono prelevati, nonché una riga per il deposito dell'ordine.
- Un pagamento con conto cliente è considerato un pagamento regolare e contrassegnato da un attributo speciale quando la transazione viene registrata nel servizio di registrazione fiscale.
- L'importo del deposito dell'ordine cliente applicato a un'operazione *Preleva* dell'ordine cliente è considerata un pagamento regolare e contrassegnata da un attributo speciale quando la transazione viene registrata nel servizio di registrazione fiscale.

### <a name="offline-registration"></a>Registrazione offline

Se il servizio di registrazione fiscale non riesce a trasmettere i dati della transazione al servizio web fiscale delle autorità fiscali (ad esempio, a causa del timeout della risposta) e a ricevere una conferma dal servizio web (ovvero il codice di identificazione fiscale della transazione), genera una firma locale per la transazione e la include con un codice di errore speciale nella risposta. Il servizio di registrazione fiscale reinvia le transazioni nell'ordine originale in background non appena viene ripristinata la connessione di rete.

### <a name="limitations-of-the-sample"></a>Limitazioni dell'esempio

Il servizio di registrazione fiscale supporta solo gli scenari in cui l'IVA è inclusa nel prezzo. Di conseguenza, l'opzione **Prezzi IVA inclusa** deve essere impostata su **Sì** per i punti vendita e i clienti.

## <a name="set-up-commerce-for-the-czech-republic"></a>Impostare Commerce per la Repubblica Ceca

Questa sezione descrive le impostazioni di Commerce specifiche e consigliate per la Repubblica Ceca. Per ulteriori informazioni, vedi [Home page di Commerce](../index.md).

Per utilizzare la funzionalità specifica per la Repubblica Ceca, è necessario specificare le seguenti impostazioni.

- Imposta il campo **Paese/area geografica** su **CZE** (Repubblica Ceca) nell'indirizzo principale della persona giuridica.
- Imposta il campo **Codice ISO** su **CZ** (Repubblica Ceca) nel profilo della funzionalità POS di ogni negozio che si trova in Repubblica Ceca.

È inoltre necessario specificare le seguenti impostazioni per la Repubblica Ceca. Tieni presente che è necessario eseguire i processi di distribuzione appropriati dopo aver completato l'impostazione.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Impostare l'IVA per i requisiti della Repubblica Ceca


È necessario creare codici IVA, fasce IVA e fasce IVA articoli. È inoltre necessario impostare le informazioni sull'IVA per prodotti e servizi. Per ulteriori informazioni su come impostare e usare le funzionalità dell'IVA vedi [Panoramica dell'IVA](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Impostare i punti vendita

Nella pagina **Tutti i punti vendita** aggiorna i dettagli del punto vendita. In specifico, imposta i seguenti parametri.

- Nel campo **Fascia IVA**, specifica la fascia IVA da utilizzare per le vendite per il cliente predefinito.
- Imposta l'opzione **Prezzi IVA inclusa** su **Sì**.
- Imposta il campo **Nome** sul nome della società. Questa modifica aiuta a garantire che il nome della società venga visualizzato su una ricevuta di vendita. In alternativa, puoi aggiungere il nome della società al layout della ricevuta di vendita come testo in formato libero.
- Imposta il campo **Codice di identificazione fiscale (TIN)** sul numero di identificazione della società. Questa modifica aiuta a garantire che il numero identificativo della società venga visualizzato su una ricevuta di vendita. In alternativa, puoi aggiungere il numero di identificazione della società al layout della ricevuta di vendita come testo in formato libero.

### <a name="set-up-functionality-profiles"></a>Impostare i profili della funzionalità

Imposta i profili della funzionalità POS.

- Nella scheda dettaglio **Numerazione ricevuta** imposta la numerazione delle ricevute creando o aggiornando i record per i tipi di transazione con ricevuta di **Vendita**, **Ordine cliente**, e **Reso**.

### <a name="set-up-registration-numbers"></a>Impostare i numeri di registrazione

1. Vai a **Amministrazione organizzazione \> Rubrica globale \> Tipi di registrazione \> Tipi di registrazione**. Crea un nuovo tipo di registrazione. Specifica il campo **Paese/Area geografica** su **CZE** (Repubblica Ceca) e limita per Organizzazione.
2. Vai a **Amministrazione organizzazione \> Rubrica globale \> Tipi di registrazione \> Categorie di registrazione**. Crea una nuova categoria di registrazione. Seleziona il tipo di registrazione dal passaggio precedente e imposta **Categoria di registrazione** su **ID sede aziendale**.
3. Selezionare **Amministrazione organizzazione \> Organizzazioni \> Unità operative**. Per ogni negozio situato nella Repubblica Ceca, seleziona l'unità relativa al negozio. Nella Scheda dettaglio **Indirizzo**, espandi l'elenco a discesa **Altre opzioni** e quindi seleziona **Avanzate**. 
4. Nella pagina **Gestisci indirizzi** aperta è necessario specificare la seguente impostazione.

    - Nella scheda dettaglio **Indirizzo** imposta il campo **Paese/Area geografica** su **CZE**.
    - Nella Scheda dettaglio **ID registrazione** crea un nuovo record. Seleziona il tipo di registrazione creato in precedenza e imposta il numero di registrazione.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurare i campi personalizzati in modo che possano essere utilizzati nei formati per ricevute di vendita

È possibile configurare il testo della lingua e i campi personalizzati utilizzati nei formati di ricevuta POS. La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua. In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.

Nella pagina **Testo lingua** aggiungi i record seguenti per le etichette dei campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi. È possibile modificarli in base alle esigenze. Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.

Aggiungi le seguenti etichette POS alla sezione **POS** di **Testo in lingua** dalla tabella:

| ID lingua | ID testo | Testo                   |
|-------------|---------|------------------------|
| en-US       | 900001  | ID provozovny/pokladny |
| en-US       | 900002  | BKP                    |
| en-US       | 900003  | PKP                    |
| en-US       | 900004  | FIK                    |
| en-US       | 900005  | Informazioni                   |
| en-US       | 900006  | Numero progressivo        |

Nella pagina **Campi personalizzati**, aggiungi i record seguenti per i campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**:

| Name                 | Tipo    | ID testo didascalia |
|----------------------|---------|-----------------|
| TLT                  | Ricevimento | 900001          |
| SEC                  | Ricevimento | 900002          |
| SIGN                 | Ricevimento | 900003          |
| FISCAL               | Ricevimento | 900004          |
| INFO                 | Ricevimento | 900005          |
| CONTINUOUSNUMBER     | Ricevimento | 900006          |

> [!NOTE]
> È importante specificare i nomi dei campi personalizzati corretti, come elencato nella tabella precedente. Un nome di campo personalizzato errato causerà la mancanza di dati nelle ricevute.

### <a name="configure-receipt-formats"></a>Configurare i formati di ricevuta

Per tutti i formati di ricevuta richiesti, modifica il valore del campo **Comportamento stampa** su **Stampa sempre**.

Nella progettazione formato ricevuta, aggiungi i seguenti campi personalizzati alle sezioni ricevuta appropriate. Tieni presente che i nomi dei campi corrispondono ai testi in lingua definiti nella sezione precedente.

- **Intestazione:** Aggiungi i seguenti campi.

    - I campi **Nome del negozio** e **Codice di identificazione fiscale**, che vengono utilizzati per stampare il nome della società e il numero di identità sulle ricevute. In alternativa, puoi aggiungere il nome della società e il numero di identità al layout come testo in formato libero.
    - **Indirizzo del negozio**, **Data**, **Orario 24H**, **Numero di ricevuta**, e **Numero di registro**.
    - **Numero sequenziale**: questo campo identifica il numero della transazione in contanti nel servizio di registrazione fiscale.

- **Righe:** Aggiungi i seguenti campi.

    - **Nome articolo**
    - **Quantità**
    - **Prezzo totale con imposte**

- **Piè di pagina:** Aggiungi i seguenti campi.

    - Campi di pagamento, in modo che vengano stampati gli importi di pagamento per ciascun metodo di pagamento. Ad esempio, aggiungi i campi **Nome offerta** e **Importo offerta** su una riga del layout.
    - **ID provozovny/pokladny**: questo campo stampa gli identificativi delle sedi commerciali e del registratore di cassa.
    - **BKP**: in questo campo viene stampato il codice di sicurezza del contribuente che viene assegnato dal servizio di registrazione fiscale.
    - **FIK**: in questo campo viene stampato il codice di identificazione fiscale dell'operazione che viene assegnato dal servizio web delle autorità fiscali in caso di avvenuta registrazione online.
    - **PKP**: questo campo stampa il codice della firma del contribuente che viene generato dal servizio di registrazione fiscale in caso di registrazione offline.
    - **Info**: questo campo stampa le informazioni aggiuntive del servizio di registrazione fiscale.

Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedi [Impostare e progettare formati di ricevute](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Impostare l'integrazione fiscale per la Repubblica Ceca

L'esempio di integrazione del servizio di registrazione fiscale per la Repubblica Ceca si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\Efr** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) di un provider di documenti fiscali, che è un'estensione di Commerce Runtime (CRT) e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per la Repubblica Ceca (legacy)](emea-cze-fi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

Completare la procedura di configurazione dell'integrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md):

1. [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Inoltre, prendi nota delle impostazioni per il processo di registrazione fiscale che sono [specifiche dell'esempio di integrazione del servizio di registrazione fiscale](#set-up-the-registration-process).
1. [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configura i componenti del canale](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Impostare il processo di registrazione

Per abilitare il processo di registrazione, segui questi passaggi per configurare Commerce headquarters. Per ulteriori informazioni vedi [Impostare l'integrazione fiscale per i canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Scarica i file di configurazione per il provider di documenti fiscali e il connettore fiscale:

    1. Apri il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione (ad esempio, **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Apri **src \> FiscalIntegration \> Efr**.
    1. Scarica il file di configurazione del provider di documenti fiscali in **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleCzech.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleCzech.xml)).
    1. Scarica il file di configurazione del connettore in **Configurations \> Connectors \> ConnectorEFRSample.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. I file di configurazione per questo esempio di integrazione fiscale si trovano nelle seguenti cartelle di Retail SDK su una macchina virtuale per sviluppatori in LCS:
    >
    > - **File di configurazione provider documenti fiscali:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleCzech.xml
    > - **File di configurazione connettore fiscale:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml
    > 
    > Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di commercio**. Nella Scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Provider di documenti fiscali**, e carica il file di configurazione del provider di documenti fiscali che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**, e carica il file di configurazione del connettore fiscale che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**. Crea un nuovo profilo funzionale del connettore. Seleziona il provider di documenti e il connettore che hai caricato in precedenza. Aggiorna le [impostazioni di mapping dei dati](#default-data-mapping) se necessario.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**. Crea un nuovo profilo tecnico del connettore, quindi seleziona il connettore fiscale caricato in precedenza. Aggiorna le [impostazioni del connettore](#fiscal-connector-settings) se necessario.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**. Crea un nuovo gruppo di connettori fiscali per il profilo funzionale del connettore che hai creato in precedenza.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**. Crea un nuovo processo di registrazione fiscale e un passaggio del processo di registrazione fiscale e seleziona il gruppo di connettori fiscali creato in precedenza.
1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. Seleziona il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Nella scheda Dettaglio **Processo di registrazione fiscale**, seleziona il processo di registrazione fiscale creato precedentemente.
1. Andare a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**. Seleziona un profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata. Nella scheda Dettaglio **Periferiche fiscali**, seleziona il profilo tecnico del connettore creato in precedenza.
1. Aprire la programmazione della distribuzione (**Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**) e selezionare i processi **1070** e **1090** per trasferire i dati al database del canale.

#### <a name="default-data-mapping"></a>Mapping dei dati predefiniti

Il mapping dei dati predefiniti seguente è incluso nella configurazione di provider di documenti fiscali fornita nell'esempio di integrazione fiscale:

- **Mapping delle aliquote IVA** – Il mapping dei valori delle percentuali di imposta impostati per i codici IVA sui valori dell'attributo **TaxG** (gruppo di imposte) nelle richieste inviate al servizio fiscale. Ecco il mapping predefinito:

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    Il primo componente in ogni coppia rappresenta il gruppo IVA supportato dal servizio di registrazione fiscale EFR. Il secondo componente rappresenta l'aliquota IVA corrispondente. Per ulteriori informazioni sui gruppi di imposte IVA supportati da EFR per la Repubblica Ceca, vedi il [Riferimento EFR](https://public.efsta.net/efr/).

- **Mappin predefinita del gruppo IVA** – Eventuali importi IVA che non possono essere mappati a uno dei gruppi IVA predeterminati verranno attribuiti al gruppo IVA predefinito (di base). Ecco il mapping predefinito:

    ```
    A
    ```

- **Mapping del gruppo IVA deposito** – Gli importi di deposito del cliente e gli importi di deposito dell'ordine cliente saranno attribuiti al gruppo IVA di deposito. Ecco il mapping predefinito:

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Impostazioni del connettore fiscale

Le seguenti impostazioni sono incluse nella configurazione del connettore fiscale fornita nell'esempio di integrazione fiscale:

- **Indirizzo dell'endpoint** – L'URL del servizio di registrazione fiscale.
- **Timeout** – La quantità di tempo, in millisecondi che il connettore fiscale trascorre in attesa di una risposta dal servizio di registrazione fiscale.

### <a name="configure-channel-components"></a>Configurare i componenti del canale

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per la Repubblica Ceca (legacy)](emea-cze-fi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

#### <a name="set-up-the-development-environment"></a>Impostare un ambiente di sviluppo

Segui questi passaggi per impostare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

1. Clona o scarica il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione. Per altre informazioni vedi [Scaricare gli esempi Retail SDK e i pacchetti di riferimento da GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Apri la soluzione EFR in **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln**, e compilala.
1. Installa le estensioni CRT:

    1. Trova il programma di installazione dell'estensione CRT:

        - **Commerce Scale Unit:** Nella directory **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461** trova il programma di installazione **ScaleUnit.EFR.Installer**.
        - **CRT locale su POS moderno:** Nella cartella **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461** trova il programma di installazione **ModernPOS.EFR.Installer**.

    1. Avvia il programma di installazione dell'estensione CRT dalla riga di comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **CRT locale su Modern POS:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Installa le estensioni stazione hardware:

    1. Nella cartella **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461** trova il programma di installazione **HardwareStation.EFR.Installer**.
    1. Avvia il programma di installazione dell'estensione dalla riga di comando:

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Ambiente di produzione

Segui i passaggi in [Configurare una pipeline di compilazione per un esempio di integrazione fiscale](fiscal-integration-sample-build-pipeline.md) per generare e rilasciare Cloud Scale Unit e pacchetti distribuibili self-service per l'esempio di integrazione fiscale. Il file YAML del modello **EFR build-pipeline.yml** è disponibile nella cartella **Pipeline\\YAML_Files** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

L'esempio di integrazione del servizio di registrazione fiscale per la Repubblica Ceca si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\Efr** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) di un provider di documenti fiscali, che è un'estensione di CRT e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per la Repubblica Ceca (legacy)](emea-cze-fi-sample-sdk.md). Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per il servizio e di gestire le risposte dal servizio di registrazione fiscale.

#### <a name="request-handler"></a>Gestore richieste

C'è un singolo gestore richieste **DocumentProviderEFRFiscalCZE** per provider documenti, che è utilizzato per generare documenti fiscali per il servizio di registrazione fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste.

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico del servizio che deve essere registrato nel servizio di registrazione fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente, sono supportati i seguenti eventi: vendite, depositi conto cliente e depositi ordine cliente.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Questa richiesta restituisce la risposta del servizio di registrazione fiscale. Questa risposta viene serializzata per formare una stringa in modo da poter essere salvata.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il provider di documenti fiscali si trova in **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleCzech.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni per il provider di documenti fiscali da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con il servizio di registrazione fiscale. L'estensione stazione hardware utilizza il protocollo HTTP per inviare documenti generati dall'estensione CRT per il servizio di registrazione fiscale. Gestisce inoltre le risposte ricevute dal servizio di registrazione fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **EFRHandler** è il punto di ingresso per la trasmissione delle richieste al servizio di registrazione fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste.

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti al servizio di registrazione fiscale e restituisce una risposta.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del servizio di registrazione fiscale.
- **InitializeFiscalDeviceRequest** - Viene utilizzata per inizializzare il servizio di registrazione fiscale.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il connettore fiscale si trova in **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni del connettore fiscale da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
