---
title: Esempio di integrazione del servizio di registrazione fiscale per l'Austria
description: In questo articolo viene fornita una panoramica dell'esempio di integrazione fiscale per l'Austria in Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 7f4f1d796028330d2d655b1e13d3e36bbef95403
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287567"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Esempio di integrazione del servizio di registrazione fiscale per l'Austria

[!include[banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica dell'esempio di integrazione fiscale per l'Austria in Microsoft Dynamics 365 Commerce.

Per soddisfare i requisiti fiscali locali per i registratori di cassa in Austria, la funzionalità Dynamics 365 Retail per l'Austria include un esempio di integrazione del point of sale (POS) con un servizio di registrazione fiscale esterno. L'esempio estende la [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md). Si basa sulla soluzione [EFR (Registro Fiscale Elettronico)](https://www.efsta.eu/at/fiskalloesungen/oesterreich) di [EFSTA](https://www.efsta.eu/at/) e consente la comunicazione con il servizio EFR tramite il protocollo HTTPS. Il servizio EFR deve essere ospitato sulla stazione hardware Retail o su una macchina separata a cui è possibile connettersi dalla stazione hardware. L'esempio viene fornito sotto forma di codice sorgente e fa parte del kit SDK.

Microsoft non rilascia hardware, software o documentazione di EFSTA. Per informazioni su come ottenere la soluzione EFR e utilizzarla, contatta [EFSTA](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Scenari

Gli scenari seguenti sono coperti dall'esempio di integrazione di servizio di registrazione fiscale per l'Austria:

- Registrazione delle transazioni di cassa nel servizio di registrazione fiscale:

    - Invia i dati dettagliati della transazione al servizio di registrazione fiscale. Questi dati includono informazioni sulla riga di vendita e informazioni su sconti, pagamenti e imposte.
    - Acquisisci una risposta dal servizio di registrazione fiscale. Questa risposta include una firma digitale e un collegamento alla transazione registrata.
    - Registra le imposte e mappale ai codici imposta del servizio di registrazione fiscale.
    - Stampa il codice a matrice sulla ricevuta di una transazione registrata.

- Registrazione delle operazioni gift card e depositi dei clienti come transazioni non di cassa nel servizio di registrazione fiscale:

    - Emetti o aggiungi denaro a una gift card.
    - Registra un deposito conto cliente.
    - Registra un deposito ordine cliente.

- Registrazione delle transazioni non di vendita ed eventi come transazioni non di cassa nel servizio di registrazione fiscale:

    - Turno aperto e turno chiuso
    - Importo iniziale, immissione fondo cassa e rimozione offerta
    - Forzatura prezzo
    - Forzatura imposta
    - Stampa copia della ricevuta
    - Apri cassetto
    - Stampa x-report
    - Stampa report Z

- Stampa dei rendiconti di fine giornata (report X/Z) con campi specifici per l'Austria:

    - Numero totale di prodotti o servizi che sono stati consegnati ai clienti
    - Dettagli delle vendite per aliquota fiscale
    - Dettagli dei pagamenti per cassiere/operatore registratore di cassa
    - Sconti sui prezzi e resi che riducono le vendite giornaliere
    - Vendite a zero (omaggi)

- Gestione degli errori, ad esempio le seguenti opzioni:

    - Riprova la registrazione fiscale se è possibile riprova, ad esempio se il servizio di registrazione fiscale non è disponibile, non è pronto o non risponde.
    - Posticipare la registrazione fiscale.
    - Ignorare la registrazione fiscale, o contrassegnare la transazione come registrata, e includere i codici informativi per acquisire il motivo dell'errore e ulteriori informazioni.
    - Verifica la disponibilità del servizio di registrazione fiscale prima dell'apertura di una nuova transazione di vendita o della finalizzazione di una transazione di vendita.

### <a name="gift-cards"></a>Gift card

L'esempio di integrazione del servizio di registrazione fiscale implementa le seguenti regole relative alle gift card:

- Escludere le righe di vendita correlate alle operazioni *Emetti gift card* e *Aggiungi a gift card* di una transazione di cassa. Invece di registrare tali righe come parte di una transazione di cassa, registrale come transazione non di cassa separata nel servizio di registrazione fiscale.
- Non stampare un dettaglio del gruppo fiscale e un codice a matrice su una ricevuta se la ricevuta è composta solo da righe di gift card.
- Stampa l'importo totale delle gift card emesse o ricaricate in una transazione separatamente dall'importo della transazione di cassa sulla ricevuta.
- Salvare le rettifiche calcolate delle righe di pagamento nel database del canale con un riferimento a una transazione fiscale corrispondente.
- Il pagamento tramite gift card è considerato un pagamento normale.

### <a name="customer-deposits-and-customer-order-deposits"></a>Depositi cliente e depositi ordine cliente

L'esempio di integrazione del servizio di registrazione fiscale implementa le seguenti regole relative a depositi cliente e a depositi ordine cliente:

- Registra una transazione non di cassa se una transazione è un deposito cliente.
- Registra una transazione non di cassa se una transazione contiene solo un deposito ordine cliente o un rimborso di deposito ordine cliente.
- Dedurre l'importo del deposito ordine cliente dalle righe di pagamento quando si crea un ordine cliente ibrido.
- Salvare le rettifiche calcolate delle righe di pagamento nel database del canale con un riferimento a una transazione fiscale per un ordine cliente ibrido.

### <a name="limitations-of-the-sample"></a>Limitazioni dell'esempio

Il servizio di registrazione fiscale supporta solo gli scenari in cui l'IVA è inclusa nel prezzo. Di conseguenza, l'opzione **Prezzi IVA inclusa** deve essere impostata su **Sì** per i punti vendita e i clienti.

## <a name="set-up-commerce-for-austria"></a>Impostazione di Commerce per l'Austria

Questa sezione descrive le impostazioni di Commerce specifiche e consigliate per l'Austria. Per ulteriori informazioni sull'impostazione, vedi [Home page di Commerce](../index.md).

Per utilizzare la funzionalità specifica per l'Austria, è necessario specificare le seguenti impostazioni:

- Imposta il campo **Paese/area geografica** su **AUT** (Austria) nell'indirizzo principale della persona giuridica.
- Imposta il campo **Codice ISO** su **AT** (Austria) nel profilo della funzionalità POS di ogni negozio che si trova in Austria.

È inoltre necessario specificare le seguenti impostazioni per l'Austria. Tieni presente che è necessario eseguire i processi di distribuzione appropriati dopo aver completato l'impostazione.

### <a name="set-up-vat-per-austrian-requirements"></a>Impostare l'IVA per i requisiti austriaci

È necessario creare codici IVA, fasce IVA e fasce IVA articoli. È inoltre necessario impostare le informazioni sull'IVA per prodotti e servizi. Per ulteriori informazioni su come impostare e usare le funzionalità dell'IVA vedi [Panoramica dell'IVA](../../finance/general-ledger/indirect-taxes-overview.md).

Sulle ricevute di vendita è possibile stampare un codice abbreviato per un codice IVA (ad esempio, "A" o "B"). Per rendere disponibile questa funzionalità, imposta il campo **Codice stampa** nella pagina **Codici IVA**.

### <a name="set-up-stores"></a>Impostare i punti vendita

Nella pagina **Tutti i punti vendita** aggiorna i dettagli del punto vendita. In specifico, imposta i seguenti parametri:

- Nel campo **Fascia IVA**, specifica la fascia IVA da utilizzare per le vendite per il cliente predefinito.
- Imposta l'opzione **Prezzi IVA inclusa** su **Sì**.
- Imposta il campo **Nome** sul nome della società. Questa modifica aiuta a garantire che il nome della società venga visualizzato su una ricevuta di vendita. In alternativa, puoi aggiungere il nome della società al layout della ricevuta di vendita come testo in formato libero.
- Imposta il campo **Codice di identificazione fiscale (TIN)** sul numero di identificazione della società. Questa modifica aiuta a garantire che il numero identificativo della società venga visualizzato su una ricevuta di vendita. In alternativa, puoi aggiungere il numero di identificazione della società al layout della ricevuta di vendita come testo in formato libero.

### <a name="set-up-functionality-profiles"></a>Impostare i profili della funzionalità

Imposta i profili della funzionalità POS:

- Nella scheda dettaglio **Numerazione ricevuta** imposta la numerazione delle ricevute creando o aggiornando i record per i tipi di transazione con ricevuta di **Vendita**, **Ordine cliente**, e **Reso**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurare i campi personalizzati in modo che possano essere utilizzati nei formati per ricevute di vendita

È possibile configurare il testo della lingua e i campi personalizzati utilizzati nei formati di ricevuta POS. La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua. In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.

Nella pagina **Testo lingua** aggiungi i record seguenti per le etichette dei campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi. Puoi modificarli in base alle esigenze. Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.

Aggiungi le seguenti etichette POS alla sezione **POS** di **Testo in lingua** dalla tabella:

| ID lingua | ID testo | Testo                      |
|-------------|---------|---------------------------|
| en-US       | 900001  | Codice QR                   |
| en-US       | 900002  | Numero continuo         |
| en-US       | 900003  | Codice stampa vendita al dettaglio imposte     |
| en-US       | 900004  | Totale (vendite)             |
| en-US       | 900005  | Totale imposte (vendite)         |
| en-US       | 900006  | Totale con imposte (vendite) |
| en-US       | 900007  | Importo imposta (vendite)        |
| en-US       | 900008  | Base imposta (vendite)         |

Nella pagina **Campi personalizzati**, aggiungi i record seguenti per i campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**:

| Name                 | Tipo    | ID testo didascalia |
|----------------------|---------|-----------------|
| QRCODE               | Ricevimento | 900001          |
| CONTINUOUSNUMBER     | Ricevimento | 900002          |
| RETAILPRINTCODE      | Ricevimento | 900003          |
| SALESTOTAL           | Ricevimento | 900004          |
| SALESTOTALTAX        | Ricevimento | 900005          |
| SALESTOTALINCLUDETAX | Ricevimento | 900006          |
| SALESTAXAMOUNT       | Ricevimento | 900007          |
| SALESTAXBASIS        | Ricevimento | 900008          |

> [!NOTE]
> È importante specificare i nomi dei campi personalizzati corretti, come elencato nella tabella precedente. Un nome di campo personalizzato errato causerà la mancanza di dati nelle ricevute.

### <a name="configure-receipt-formats"></a>Configurare i formati di ricevuta

Per tutti i formati di ricevuta richiesti, modifica il valore del campo **Comportamento stampa** su **Stampa sempre**.

Nella progettazione formato ricevuta, aggiungi i seguenti campi personalizzati alle sezioni ricevuta appropriate. Tieni presente che i nomi dei campi corrispondono ai testi in lingua definiti nella sezione precedente.

- **Intestazione:** Aggiungi i seguenti campi:

    - I campi **Nome del negozio** e **Codice di identificazione fiscale**, che vengono utilizzati per stampare il nome della società e il numero di identità sulle ricevute. In alternativa, puoi aggiungere il nome della società e il numero di identità al layout come testo in formato libero.
    - Campi **Indirizzo del negozio**, **Data**, **Orario 24H**, **Numero di ricevuta**, e **Numero di registro**.
    - I campi **Numero continuo** per identificare il numero della transazione in contanti nel servizio di registrazione fiscale.

- **Righe:** Aggiungi i seguenti campi:

    - **Nome articolo**.
    - **Qtà**.
    - **Prezzo totale con imposte**.
    - **Codice stampa vendita al dettaglio imposte** che viene utilizzato per stampare il codice abbreviato che corrisponde al codice IVA applicabile all'articolo.

- **Piè di pagina:** Aggiungi i seguenti campi:

    - Campi di pagamento, in modo che vengano stampati gli importi di pagamento per ciascun metodo di pagamento. Ad esempio, aggiungi i campi **Nome offerta** e **Importo offerta** su una riga del layout.
    - Gruppo di campi **Totale vendite**:

        - Campo **Totale (vendite)** che viene usato per stampare l'importo totale della vendita in contanti della ricevuta. L'importo non include le imposte. Sono esclusi i pagamenti anticipati e le operazioni con gift card.
        - Campo **Totale con imposte (vendite)** che viene usato per stampare l'importo totale della vendita in contanti della ricevuta. L'importo include le imposte. Sono esclusi i pagamenti anticipati e le operazioni con gift card.
        - Campo **Totale imposte (vendite)** che viene usato per stampare l'importo totale delle imposte per le vendite in contanti. Sono esclusi i pagamenti anticipati e le operazioni con gift card.

    - Gruppo di campi **Dettaglio imposte**. Tutti i campi di questo gruppo devono essere stampati su una riga separata.

        - Campo **ID imposta** che è un campo standard che consente di stampare un riepilogo IVA per ogni codice IVA. Il campo deve essere aggiunto in una nuova riga.
        - Campo **Percentuale fiscale** che è un campo standard utilizzato per stampare l'aliquota fiscale effettiva per il codice IVA.
        - Campo **Base imposte (vendite)** che viene usato per stampare l'importo totale della vendita in contanti per il codice IVA. Sono esclusi i pagamenti anticipati e le operazioni con gift card.
        - Campo **Importo imposte (vendite)** che viene usato per stampare l'importo imposte della vendita in contanti per il codice IVA.
        - Campo **Codice stampa vendita al dettaglio imposte** che viene utilizzato per stampare il codice abbreviato che corrisponde al codice IVA.

    - Campo **Codice a matrice** che viene utilizzato per stampare il riferimento alla transazione in contanti registrata sotto forma di codice a matrice.

        > [!NOTE]
        > Il valore **Codice a matrice** viene recuperato dalla risposta del registro fiscale. EFR restituisce un codice a matrice nella risposta solo se il valore del campo **Attributi** nella configurazione EFR è descritto nella documentazione EFSTA. Il formato del codice QR nel campo **Attributi** nella configurazione EFR deve essere impostato su **BMP**.

Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedi [Impostare e progettare formati di ricevute](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-austria"></a>Impostare l'integrazione fiscale per l'Austria

L'esempio di integrazione del servizio di registrazione fiscale per l'Austria si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\Efr** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) di un provider di documenti fiscali, che è un'estensione di Commerce Runtime (CRT) e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per l'Austria (legacy)](emea-aut-fi-sample-sdk.md). Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

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
    1. Apri **Configurations \> DocumentProviders** e scarica i file di configurazione del provider di documenti fiscali: **DocumentProviderFiscalEFRSampleAustria.xml** e **DocumentProviderNonFiscalEFRSampleAustria.xml** (ad esempio, [la posizione dei file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)).
    1. Scarica il file di configurazione del connettore in **Configurations \> Connectors \> ConnectorEFRSample.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. I file di configurazione per questo esempio di integrazione fiscale si trovano nelle seguenti cartelle di Retail SDK su una macchina virtuale per sviluppatori in LCS:
    >
    > - **File di configurazione provider documenti fiscali:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration
    > - **File di configurazione connettore fiscale:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration
    > 
    > Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di commercio**. Nella Scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Provider di documenti fiscali**, e carica i file di configurazione del provider di documenti fiscali che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**, e carica il file di configurazione del connettore fiscale che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**. Crea due nuovi profili funzionali del connettore, uno per ogni provider di documenti fiscali caricato in precedenza e seleziona il connettore fiscale caricato in precedenza. Aggiorna le [impostazioni di mapping dei dati](#default-data-mapping) se necessario.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**. Crea un nuovo profilo tecnico del connettore, quindi seleziona il connettore fiscale caricato in precedenza. Aggiorna le [impostazioni del connettore](#fiscal-connector-settings) se necessario.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**. Crea due nuovi gruppi di connettori fiscali uno per ogni profilo funzionale del connettore che hai creato in precedenza.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**. Crea un nuovo processo di registrazione fiscale e due passaggi del processo di registrazione fiscale e seleziona i gruppi di connettori fiscali creati in precedenza.
1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. Seleziona il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Nella scheda Dettaglio **Processo di registrazione fiscale**, seleziona il processo di registrazione fiscale creato precedentemente. Per abilitare la registrazione degli eventi non fiscali sul POS, nella scheda dettaglio **Funzioni** sotto **POS**, imposta l'opzione **Controllo** su **sì**.
1. Andare a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**. Seleziona un profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata. Nella scheda Dettaglio **Periferiche fiscali**, seleziona il profilo tecnico del connettore creato in precedenza.
1. Aprire la programmazione della distribuzione (**Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**) e selezionare i processi **1070** e **1090** per trasferire i dati al database del canale.

#### <a name="default-data-mapping"></a>Mapping dei dati predefiniti

Il mapping dei dati predefiniti seguente è incluso nella configurazione di provider di documenti fiscali fornita nell'esempio di integrazione fiscale:

- **Mapping delle aliquote IVA** – Il mapping dei valori delle percentuali di imposta impostati per i codici IVA sui valori dell'attributo **TaxG** (gruppo di imposte) nelle richieste inviate al servizio fiscale. Ecco il mapping predefinito:

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    Il primo componente in ogni coppia rappresenta il gruppo IVA supportato dal servizio di registrazione fiscale EFR. Il secondo componente rappresenta l'aliquota IVA corrispondente. Per ulteriori informazioni sui gruppi di imposte IVA supportati da EFR per l'Austria, vedi il [Riferimento EFR](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Impostazioni del connettore fiscale

Le seguenti impostazioni sono incluse nella configurazione del connettore fiscale fornita nell'esempio di integrazione fiscale:

- **Indirizzo dell'endpoint** – L'URL del servizio di registrazione fiscale.
- **Timeout dispositivo** – La quantità di tempo, in millisecondi che il connettore fiscale trascorre in attesa di una risposta dal servizio di registrazione fiscale.
- **Mostra notifiche di registrazione fiscale** – Questo flag controlla se le notifiche che il servizio di registrazione fiscale restituisce devono essere mostrate all'operatore.

### <a name="configure-channel-components"></a>Configurare i componenti del canale

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per l'Austria (legacy)](emea-aut-fi-sample-sdk.md).
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

1. Installare le estensioni del connettore fiscale:

    È possibile installare le estensioni del connettore fiscale sulla [stazione hardware](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) o il [Registro POS](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

    1. Installa le estensioni stazione hardware:

        1. Nella cartella **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461** trova il programma di installazione **HardwareStation.EFR.Installer**.
        1. Avvia il programma di installazione dell'estensione dalla riga di comando eseguendo questo comando.

            ```Console
            HardwareStation.EFR.Installer.exe install --verbosity 0
            ```

    1. Installa le estensioni POS:

        1. Aprire la soluzione di esempio del connettore fiscale POS all'indirizzo **Dynamics365Commerce.Solutions\\FiscalIntegration\\PosFiscalConnectorSample\\Contoso.PosFiscalConnectorSample.sln** e costruiscilo.
        1. Nella cartella **PosFiscalConnectorSample\\StoreCommerce.Installer\\bin\\Debug\\net461**, trova il programma di installazione **Contoso.PosFiscalConnectorSample.StoreCommerce.Installer**.
        1. Avvia il programma di installazione dell'estensione dalla riga di comando eseguendo questo comando.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Ambiente di produzione

Segui i passaggi in [Configurare una pipeline di compilazione per un esempio di integrazione fiscale](fiscal-integration-sample-build-pipeline.md) per generare e rilasciare Cloud Scale Unit e pacchetti distribuibili self-service per l'esempio di integrazione fiscale. Il file YAML del modello **EFR build-pipeline.yml** è disponibile nella cartella **Pipeline\\YAML_Files** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

L'esempio di integrazione del servizio di registrazione fiscale per l'Austria si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\Efr** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) di un provider di documenti fiscali, che è un'estensione di CRT e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per l'Austria (legacy)](emea-aut-fi-sample-sdk.md). Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime 

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per il servizio e di gestire le risposte dal servizio di registrazione fiscale.

#### <a name="request-handler"></a>Gestore richieste

Esistono due gestori di richieste per i provider di documenti:

- **DocumentProviderEFRFiscalAUT** – Questo gestore viene utilizzato per generare documenti fiscali per il servizio di registrazione fiscale.
- **DocumentProviderEFRNonFiscalAUT** – Questo gestore viene utilizzato per generare documenti non fiscali per il servizio di registrazione fiscale.

Questi gestori sono ereditati dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico del servizio che deve essere registrato nel servizio di registrazione fiscale.
- **GetNonFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento non fiscale dovrà essere generato. Restituisce un documento specifico del servizio che deve essere registrato nel servizio di registrazione fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente, sono supportati i seguenti eventi: vendite, stampa di report X, stampa di report Z, depositi conto cliente, depositi ordine cliente, eventi di controllo e transazioni non di vendita.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Questa richiesta restituisce la risposta del servizio di registrazione fiscale. Questa risposta viene serializzata per formare una stringa in modo da poter essere salvata.

#### <a name="configuration"></a>Configurazione

I file di configurazione per il provider di documenti fiscali si trovano nella cartella **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/):

- **DocumentProviderFiscalEFRSampleAustria** – Il file di configurazione per il provider di documenti fiscali per i documenti fiscali.
- **DocumentProviderNonFiscalEFRSampleAustria** – Il file di configurazione per il provider di documenti fiscali per i non documenti fiscali.

Lo scopo dei file è di consentire la configurazione delle impostazioni per il provider di documenti fiscali da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione del connettore fiscale è di comunicare con il servizio di registrazione fiscale. L'estensione stazione hardware utilizza i protocolli HTTP e HTTPS per inviare documenti generati dall'estensione CRT per il servizio di registrazione fiscale. Gestisce inoltre le risposte ricevute dal servizio di registrazione fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **EFRHandler** è il punto di ingresso per la trasmissione delle richieste al servizio di registrazione fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore fiscale supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti al servizio di registrazione fiscale e restituisce una risposta.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del servizio di registrazione fiscale.
- **InitializeFiscalDeviceRequest** - Viene utilizzata per inizializzare il servizio di registrazione fiscale.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il connettore fiscale si trova in **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni del connettore fiscale da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

### <a name="pos-fiscal-connector-extension-design"></a>Progettazione delle estensioni del connettore fiscale POS

Lo scopo dell'estensione del connettore fiscale POS è di comunicare con il servizio di registrazione fiscale dal POS. Utilizza il protocollo HTTPS per la comunicazione.

#### <a name="fiscal-connector-factory"></a>Factory del connettore fiscale

La factory del connettore fiscale associa il nome del connettore all'implementazione del connettore fiscale e si trova nel file **Pos.Extension\\Connectors\\FiscalConnectorFactory.ts**. Il nome del connettore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

#### <a name="efr-fiscal-connector"></a>Connettore fiscale EFR

Il connettore fiscale EFR si trova nel file **Pos.Extension\\Connectors\\Efr\\EfrFiscalConnector.ts**. Implementa l'interfaccia **IFiscalConnector** che supporta le seguenti richieste:

- **FiscalRegisterSubmitDocumentClientRequest** - Invia documenti al servizio di registrazione fiscale e restituisce una risposta.
- **FiscalRegisterIsReadyClientRequest** - Viene utilizzata per un controllo di integrità del servizio di registrazione fiscale.
- **FiscalRegisterInitializeClientRequest** - Viene utilizzata per inizializzare il servizio di registrazione fiscale.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** del repository [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore fiscale da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- **Indirizzo dell'endpoint** – L'URL del servizio di registrazione fiscale.
- **Timeout** – La quantità di tempo, in millisecondi (ms) che il connettore trascorre in attesa di una risposta dal servizio di registrazione fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
