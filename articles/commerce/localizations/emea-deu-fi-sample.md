---
title: Esempio di integrazione del servizio di registrazione fiscale per la Germania
description: In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per la Germania in Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-5-29
ms.openlocfilehash: 65315a9fd6bc1af26bc225220e096aee4da09be2
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388161"
---
# <a name="fiscal-registration-service-integration-sample-for-germany"></a>Esempio di integrazione del servizio di registrazione fiscale per la Germania

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per la Germania in Microsoft Dynamics 365 Commerce.

Per soddisfare i requisiti fiscali locali per i registratori di cassa in Germania, la funzionalità Microsoft Dynamics 365 Commerce per la Germania include un esempio di integrazione del point of sale (POS) con un servizio di registrazione fiscale esterno. L'esempio estende la [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md). Si basa sulla soluzione [EFR (Registro Fiscale Elettronico)](https://www.efsta.eu/de/fiskalloesungen/deutschland) di [EFSTA](https://www.efsta.eu/de/) e consente la comunicazione con il servizio EFR tramite il protocollo HTTPS. Il servizio EFR deve essere ospitato sulla stazione hardware Retail o su un computer separato a cui è possibile connettersi dalla stazione hardware. L'esempio viene fornito sotto forma di codice sorgente e fa parte del kit SDK.

Microsoft non rilascia hardware, software o documentazione di EFSTA. Per informazioni su come ottenere la soluzione EFR e utilizzarla, contatta [EFSTA](https://www.efsta.eu/de/kontakt/kontakt).

## <a name="scenarios"></a>Scenari

Gli scenari seguenti sono coperti dall'esempio di integrazione di servizio di registrazione fiscale per la Germania:

### <a name="sales-operations"></a>Operazioni di vendita

- **Registrazione delle vendite e dei resi cash and carry nel servizio di registrazione fiscale:**

    La registrazione delle operazioni di vendita comprende i seguenti passaggi:

    1. Registrazione dell'inizio della transazione

        L'inizio di ogni transazione è registrato in un elemento di sicurezza tecnica (TSE) collegato al servizio EFR. Come risultato della registrazione, un TSE assegna un ID transazione (TID).

    2. Registrazione della fine della transazione

        Quando una transazione viene conclusa al POS, viene registrata utilizzando lo stesso TID che è stato assegnato durante la registrazione dell'inizio della transazione. In quel momento, i dati dettagliati della transazione vengono inviati al servizio di registrazione fiscale. Questi dati includono informazioni sulla riga di vendita e informazioni su sconti, pagamenti e imposte.

    3. Acquisizione di una risposta dal servizio di registrazione fiscale

        I dati di sicurezza vengono ricevuti da un TSE come parte di una risposta e vengono salvati nella transazione nel database del canale. I dati di sicurezza sono costituiti dalle seguenti informazioni:

        - TID
        - Data e ora di inizio della transazione
        - Data e ora di fine della transazione
        - Contatore firme
        - Valore controllo
        - Numero di serie del TSE

- **Registrazione degli ordini cliente nel servizio di registrazione fiscale:** Il processo di registrazione è lo stesso del processo di vendita cash and carry e resi.
- **Registrazione delle operazioni che includono gift card e depositi:** Il processo di registrazione è lo stesso del processo di vendita cash and carry e resi.

#### <a name="notifying-users-about-fiscal-registration-failures"></a>Notificare agli utenti di errori di registrazione fiscale

Ci sono due modi in cui il servizio di registrazione fiscale può notificare agli utenti gli errori verificatisi durante la registrazione fiscale:

- Stampa ulteriori informazioni dalla risposta nel campo **Messaggio informativo** sulle ricevute.
- Mostra le notifiche del servizio fiscale come messaggi utente al POS.

    > [!NOTE]
    > Questo meccanismo di notifica richiede che il parametro **Mostra notifiche di registrazione fiscale** nella pagina **Profili tecnici connettori** sia attivato.

#### <a name="printing-receipts"></a>Stampa delle ricevute

La stampa della ricevuta è obbligatoria in Germania. Tutte le ricevute devono contenere almeno le seguenti informazioni:

- Nome e indirizzo della società
- Informazioni sulle merci, compresi i prezzi e le quantità
- Informazioni sui pagamenti ricevuti
- Informazioni sulle tasse, inclusi gli importi totali per aliquota fiscale
- Dati di sicurezza:

    - TID
    - Data e ora di inizio della transazione
    - Data e ora di fine della transazione
    - Contatore firme
    - Valore controllo
    - Numero di serie del TSE

- Messaggio informativo

> [!NOTE]
> Un codice a matrice può essere stampato anche sulle ricevute. Sebbene il codice a matrice sia facoltativo, è altamente raccomandato. Per ulteriori informazioni su come ottenere il codice a matrice come parte di una risposta dal servizio di registrazione fiscale, consulta il documento "Guida EFR \[DE\]" che viene pubblicato sul sito web [Documentazione EFSTA](https://public.efsta.net/efr/).
>
> Il campo **Messaggio informativo** sulle ricevute riporta una notifica del servizio di registrazione fiscale. Ad esempio, se un dispositivo di firma è rotto, è possibile stampare un testo speciale su una ricevuta.

#### <a name="voided-suspended-and-recalled-transactions"></a>Transazioni annullate, sospese e richiamate

- Una transazione annullata viene registrata come richiesta di interruzione di una transazione nel servizio di registrazione fiscale.
- Una transazione sospesa viene registrata come richiesta di interruzione di una transazione nel servizio di registrazione fiscale.
- Il richiamo di una transazione sospesa viene registrata come l'inizio di una nuova transazione nel servizio di registrazione fiscale.

### <a name="non-sales-transactions-and-shift-closing"></a>Transazioni non di vendita e chiusura dei turni

Le seguenti transazioni non di vendita sono registrate come operazioni non fiscali nel servizio di registrazione fiscale utilizzando il tag **NFS**:

- Dichiara importo iniziale
- Immissione fondo cassa
- Rimozione metodo di pagamento
- Deposito in cassaforte
- Deposito bancario
- Conti ricavi
- Conti spese

Anche l'operazione **Chiudi turno** è registrata come operazione non fiscale nel servizio di registrazione fiscale utilizzando il tag **NFS**.

### <a name="data-export-and-audit"></a>Esportazione dei dati e controllo

Tutte le transazioni devono essere firmate da un TSE per garantirne l'integrità, l'autenticità e la completezza e per aiutare a prevenire la manipolazione dei dati registrati.

> [!WARNING]
> È possibile utilizzare solo un TSE certificato. Per informazioni sui tipi e i modelli di TSE supportati nella soluzione EFR, vedi il documento "Guida EFR" \[DE\]" che viene pubblicato sul sito web [Documentazione EFSTA](https://public.efsta.net/efr/). Per informazioni su come scegliere e ottenere un TSE, contatta [EFSTA](https://www.efsta.eu/at/kontakt).

Le normative in Germania richiedono il supporto per l'esportazione DSFinV-K. L'esportazione DSFinV-K può essere attivata nella soluzione EFR. Per ulteriori informazioni sull'esportazione DSFinV-K, vedi il documento "Guida EFR \[DE\]" che viene pubblicato sul sito web [Documentazione EFSTA](https://public.efsta.net/efr/).

### <a name="limitations-of-the-sample"></a>Limitazioni dell'esempio

Il servizio di registrazione fiscale supporta solo gli scenari in cui l'IVA è inclusa nel prezzo. Di conseguenza, l'opzione **Prezzi IVA inclusa** deve essere impostata su **Sì** per i punti vendita e i clienti.

Il servizio fiscale non supporta situazioni in cui viene applicato più di un codice IVA alla stessa riga di transazione.

Il framework di integrazione fiscale non supporta le offerte di vendita. Pertanto, tali operazioni non sono registrate nel servizio fiscale.

## <a name="set-up-commerce-for-germany"></a>Impostazione di Commerce per la Germania

Questa sezione descrive le impostazioni di Commerce specifiche e consigliate per la Germania. Per ulteriori informazioni sull'impostazione, vedi [Home page di Commerce](../index.md).

Per utilizzare la funzionalità specifica per la Germania, è necessario specificare le seguenti impostazioni.

- Imposta il campo **Paese/area geografica** su **DEU** (Germania) nell'indirizzo principale della persona giuridica.
- Imposta il campo **Codice ISO** su **DE** (Germania) nel profilo della funzionalità POS di ogni negozio che si trova in Germania.

È inoltre necessario specificare le seguenti impostazioni per la Germania. Assicurati di eseguire i processi di distribuzione appropriati dopo aver completato l'impostazione.

### <a name="set-up-vat-per-german-requirements"></a>Impostare l'IVA per i requisiti tedeschi

È necessario creare codici IVA, fasce IVA e fasce IVA articoli. È inoltre necessario impostare le informazioni sull'IVA per prodotti e servizi. Per ulteriori informazioni su come impostare e usare le funzionalità dell'IVA vedi [Panoramica dell'IVA](../../finance/general-ledger/indirect-taxes-overview.md).

Sulle ricevute di vendita è possibile stampare un codice abbreviato per un codice IVA (ad esempio, "A" o "B"). Per rendere disponibile questa funzionalità, imposta il campo **Codice per la stampa** nella pagina **Codici IVA**.

### <a name="set-up-stores"></a>Impostare i punti vendita

Nella pagina **Tutti i punti vendita** aggiorna i dettagli del punto vendita. In specifico, imposta i seguenti parametri:

- Nel campo **Fascia IVA**, specifica la fascia IVA da utilizzare per le vendite per il cliente predefinito.
- Imposta l'opzione **Prezzi IVA inclusa** su **Sì**.
- Imposta il campo **Nome** sul nome della società. Questa modifica aiuta a garantire che il nome della società venga visualizzato su una ricevuta di vendita. In alternativa, puoi aggiungere il nome della società al layout della ricevuta di vendita come testo in formato libero.
- Imposta il campo **Codice di identificazione fiscale (TIN)** sul numero di identificazione della società. Questa modifica aiuta a garantire che il numero identificativo della società venga visualizzato su una ricevuta di vendita. In alternativa, puoi aggiungere il numero di identificazione della società al layout della ricevuta di vendita come testo in formato libero.

### <a name="set-up-functionality-profiles"></a>Impostare i profili della funzionalità

Imposta i profili della funzionalità POS. Nella scheda dettaglio **Numerazione ricevuta** imposta la numerazione delle ricevute creando o aggiornando i record per i tipi di transazione con ricevuta di **Vendita**, **Ordine cliente**, e **Reso**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurare i campi personalizzati in modo che possano essere utilizzati nei formati per ricevute di vendita

È possibile configurare il testo della lingua e i campi personalizzati utilizzati nei formati di ricevuta POS. La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua. In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.

Nella pagina **Testo lingua** aggiungi i record seguenti per le etichette dei campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi. Puoi modificarli in base alle esigenze. Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.

Aggiungi le seguenti etichette POS alla sezione **POS** della pagina **Testo in lingua**.

| ID lingua | ID testo | Testo                                  |
|-------------|---------|---------------------------------------|
| en-US       | 900001  | Codice a matrice                               |
| en-US       | 900002  | ID transazione                        |
| en-US       | 900003  | Codice stampa vendita al dettaglio imposte                 |
| en-US       | 900004  | Importo imposta (vendite)                    |
| en-US       | 900005  | Base imposta (vendite)                     |
| en-US       | 900006  | Data e ora di inizio transazione           |
| en-US       | 900007  | Data e ora di fine transazione             |
| en-US       | 900008  | Numero di serie dell'elemento di sicurezza |
| en-US       | 900009  | Contatore firme                     |
| en-US       | 900010  | Valore controllo                           |
| en-US       | 900011  | Messaggio informativo                          |

Nella pagina **Campi personalizzati**, aggiungi i record seguenti per i campi personalizzati per i layout di ricevuta. Si noti che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**.

| Name                            | Tipo    | ID testo didascalia |
|---------------------------------|---------|-----------------|
| QRCODE\_DE                      | Ricevimento | 900001          |
| TRANSACTIONID\_DE               | Ricevimento | 900002          |
| RETAILPRINTCODE\_DE             | Ricevimento | 900003          |
| SALESTAXAMOUNT\_DE              | Ricevimento | 900004          |
| SALESTAXBASIS\_DE               | Ricevimento | 900005          |
| TRANSACTIONSTARTDATETIME\_DE    | Ricevimento | 900006          |
| TRANSACTIONENDDATETIME\_DE      | Ricevimento | 900007          |
| SECURITYELEMENTSERIALNUMBER\_DE | Ricevimento | 900008          |
| SIGNCOUNTER\_DE                 | Ricevimento | 900009          |
| SIGN\_DE                        | Ricevimento | 900010          |
| INFOMESSAGE\_DE                 | Ricevimento | 900011          |

> [!NOTE]
> È importante specificare i nomi dei campi personalizzati corretti, come elencato nella tabella precedente. Un nome di campo personalizzato errato causerà la mancanza di dati nelle ricevute.

### <a name="configure-receipt-formats"></a>Configurare i formati di ricevuta

Per tutti i formati di ricevuta richiesti, modifica il valore del campo **Comportamento stampa** su **Stampa sempre**.

Nella progettazione formato ricevuta, aggiungi i seguenti campi personalizzati alle sezioni ricevuta appropriate. Tieni presente che i nomi dei campi corrispondono ai testi in lingua definiti nella sezione precedente.

- **Intestazione:** Aggiungi i seguenti campi:

    - I campi **Nome del negozio** e **Codice di identificazione fiscale**, che vengono utilizzati per stampare il nome della società e il numero di identificazione sulle ricevute. In alternativa, puoi aggiungere il nome della società e il numero di identificazione al layout come testo in formato libero.
    - Campi **Indirizzo del negozio**, **Data**, **Orario 24H**, **Numero di ricevuta**, e **Numero di registro**.

- **Righe:** Aggiungi i seguenti campi:

    - Campo **nome articolo**
    - Campo **Qtà**
    - Campo **Prezzo totale con imposte**
    - Campo **Codice stampa vendita al dettaglio imposte** che viene utilizzato per stampare il codice abbreviato che corrisponde al codice IVA applicabile all'articolo

- **Piè di pagina:** Aggiungi i seguenti campi:

    - Campi di pagamento, in modo che vengano stampati gli importi di pagamento per ciascun metodo di pagamento. Ad esempio, aggiungi i campi **Nome offerta** e **Importo offerta** su una riga del layout.
    - I campi nel gruppo di campi **Dettaglio imposte**. Tutti i campi di questo gruppo devono essere stampati su una riga separata.

        - Campo **ID imposta** che è un campo standard che consente di stampare un riepilogo IVA per ogni codice IVA. Il campo deve essere aggiunto in una nuova riga.
        - Campo **Percentuale fiscale** che è un campo standard utilizzato per stampare l'aliquota fiscale effettiva per il codice IVA.
        - Campo **Base imposte (vendite)** che viene usato per stampare l'importo totale della vendita in contanti per il codice IVA. Sono esclusi i pagamenti anticipati e le operazioni con gift card.
        - Campo **Importo imposte (vendite)** che viene usato per stampare l'importo imposte della vendita in contanti per il codice IVA.
        - Campo **Codice stampa vendita al dettaglio imposte** che viene utilizzato per stampare il codice abbreviato che corrisponde al codice IVA.

    - i campi che contengono dati di transazione protetti restituiti dal servizio di registrazione fiscale:

        - Campo **ID transazione** che identifica il numero della transazione di cassa nel servizio di registrazione fiscale
        - Campo **Data e ora di inizio transazione**
        - Campo **Data e ora di fine transazione**
        - Campo **Numero di serie dell'elemento di sicurezza**
        - Campo **Contatore firme**
        - Campo **Valore controllo**
        - Campo **Codice a matrice** che viene utilizzato per stampare il riferimento alla transazione di cassa registrata sotto forma di codice a matrice

        > [!NOTE]
        > Il valore **Codice a matrice** viene recuperato dalla risposta del registro fiscale. EFR restituisce un codice a matrice nella risposta solo se il valore del campo **Attributi** nella configurazione EFR è descritto nella documentazione EFSTA. Il formato del codice QR nel campo **Attributi** nella configurazione EFR deve essere impostato su **BMP**.

    - Il campo **Messaggio informativo** in modo che i messaggi di notifica del servizio di registrazione fiscale vengano riportati sulle ricevute. Ad esempio, se un dispositivo di firma è rotto, è possibile stampare un testo speciale su una ricevuta.

Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedi [Impostare e progettare formati di ricevute](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-germany"></a>Impostare l'integrazione fiscale per la Germania

L'esempio di integrazione del servizio di registrazione fiscale per la Germania si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\Efr** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) di un provider di documenti fiscali, che è un'estensione di Commerce Runtime (CRT) e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per la Germania (legacy)](emea-deu-fi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

Completare la procedura di configurazione dell'integrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md):

1. [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Inoltre, prendi nota delle impostazioni per il processo di registrazione fiscale che sono [specifiche dell'esempio di integrazione del servizio di registrazione fiscale](#set-up-the-registration-process).
1. [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

    > [!WARNING]
    > Le capacità di gestione degli errori del framework di integrazione fiscale potrebbero non essere completamente allineate con le normative fiscali locali.
    >
    > - Ti consigliamo di lasciare l'opzione **Continua in caso di errore** nella pagina **Processo di registrazione fiscale** disattivata, perché tutte le transazioni devono essere registrate correttamente, anche se il primo tentativo di registrazione fiscale non è andato a buon fine.
    > - Prima di attivare l'opzione **Ignora** o **Contrassegna come registrato** nella pagina **Processo di registrazione fiscale** dovresti discutere queste modifiche al processo di registrazione fiscale con il tuo consulente fiscale o l'ufficio delle imposte locali.

1. [Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configura i componenti del canale](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Impostare il processo di registrazione

Per abilitare il processo di registrazione, segui questi passaggi per configurare Commerce headquarters. Per ulteriori informazioni vedi [Impostare l'integrazione fiscale per i canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Scarica i file di configurazione per il provider di documenti fiscali e il connettore fiscale:

    1. Apri il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione (ad esempio, **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Apri **src \> FiscalIntegration \> Efr**.
    1. Scarica il file di configurazione del provider di documenti fiscali in **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleGermany.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleGermany.xml)).
    1. Scarica il file di configurazione del connettore in **Configurations \> Connectors \> ConnectorEFRSample.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. I file di configurazione per questo esempio di integrazione fiscale si trovano nelle seguenti cartelle di Retail SDK su una macchina virtuale per sviluppatori in LCS:
    >
    > - **File di configurazione provider documenti fiscali:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleGermany.xml
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

- **Mapping del tipo di metodo di pagamento** – Il mapping dei metodi di pagamento ai valori dell'attributo **PayG** (gruppo di pagamenti) nelle richieste inviate al servizio fiscale. Ecco il mapping predefinito:

    ```
    1: 0; 2: 1; 3: 3; 4: 8; 5: 2; 6: 0; 7: 7; 8: 6; 9: 0; 10: 8; 11: 1
    ```

    Il primo componente di ogni coppia rappresenta un metodo di pagamento impostato per il negozio. Il secondo componente rappresenta il gruppo di pagamenti corrispondente supportato dal servizio di registrazione fiscale EFR. Per ulteriori informazioni sui gruppi di pagamenti supportati da EFR per la Germania, vedi il [Riferimento EFR](https://public.efsta.net/efr/).

    Il mapping di esempio dei metodi di pagamento corrisponde ai metodi di pagamento memorizzati che sono configurati nei dati demo standard.

    | Metodo di pagamento | Nome metodo di pagamento |
    |----------------|---------------------|
    | 1              | Cassa                |
    | 2              | Seleziona               |
    | 3              | Scheda                |
    | 4              | Conto cliente    |
    | 5              | Altro               |
    | 6              | Valuta            |
    | 7              | Giustificativo             |
    | 8              | Gift card           |
    | 9              | Rimuovi/sospendi metodo di pagamento |
    | 10             | Carte fedeltà       |
    | 11             | Controlli non locali    |

    Pertanto è necessario modificare il mapping di esempio in base ai metodi di pagamento configurati nell'applicazione.

- **Includi i dati del cliente** – Se questo parametro è attivato, le richieste al servizio fiscale conterranno informazioni sul cliente, come nomi e indirizzi, nei casi in cui un cliente viene aggiunto a una transazione.
- **Mapping delle aliquote IVA** – Il mapping dei valori delle percentuali di imposta impostati per i codici IVA sui valori dell'attributo **TaxG** (gruppo di imposte) nelle richieste inviate al servizio fiscale. Ecco il mapping predefinito:

    ```
    A: 19.00; B: 7.00; C: 10.70; D: 5.50; E: 0.00
    ```

    Il primo componente in ogni coppia rappresenta il gruppo IVA supportato dal servizio di registrazione fiscale EFR. Il secondo componente rappresenta l'aliquota IVA corrispondente. Per ulteriori informazioni sui gruppi di imposte IVA supportati da EFR per la Germania, vedi il [Riferimento EFR](https://public.efsta.net/efr/).

- **Gruppo fiscale per gift card e depositi** – Il valore dell'attributo **TaxG** nelle richieste che vengono inviate al servizio fiscale, sulla base di operazioni che prevedono gift card o depositi. Ecco il mapping predefinito:

    ```
    G
    ```

- **Gruppo di imposte per esenzione IVA** – Il valore dell'attributo **TaxG** nelle richieste che vengono inviate al servizio fiscale, sulla base di operazioni esenti da obblighi fiscali. Ecco il mapping predefinito:

    ```
    F
    ```

> [!NOTE]
> Le impostazioni fiscali nel mapping dei dati predefinito sono responsabili della corrispondenza delle impostazioni delle imposte nel sistema e dei gruppi di imposte nel servizio EFR. I gruppi di imposte possono essere stampati sugli scontrini solo se il campo **Codice per la stampa** è impostato nella pagina **Codici IVA**.

#### <a name="fiscal-connector-settings"></a>Impostazioni del connettore fiscale

Le seguenti impostazioni sono incluse nella configurazione del connettore fiscale fornita nell'esempio di integrazione fiscale:

- **Indirizzo dell'endpoint** – L'URL del servizio di registrazione fiscale.
- **Timeout** – La quantità di tempo, in millisecondi che il connettore fiscale trascorre in attesa di una risposta dal servizio di registrazione fiscale.
- **Mostra notifiche di registrazione fiscale** – Questo flag controlla se le notifiche che il servizio di registrazione fiscale restituisce devono essere mostrate all'operatore.

### <a name="configure-channel-components"></a>Configurare i componenti del canale

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per la Germania (legacy)](emea-deu-fi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

#### <a name="set-up-the-development-environment"></a>Impostare un ambiente di sviluppo

Segui questi passaggi per impostare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

1. Clona o scarica il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione. Per altre informazioni vedi [Scaricare gli esempi Retail SDK e i pacchetti di riferimento da GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Apri la soluzione EFR in **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln**, e compilala.
1. Installa le estensioni di Commerce Runtime:

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

L'esempio di integrazione del servizio di registrazione fiscale per la Germania si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\Efr** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) di un provider di documenti fiscali, che è un'estensione di CRT e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione fiscale per la Germania (legacy)](emea-deu-fi-sample-sdk.md). Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

### <a name="crt-extension-design"></a>Progettazione delle estensioni CRT

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per il servizio e di gestire le risposte dal servizio di registrazione fiscale.

#### <a name="request-handler"></a>Gestore richieste

È disponibile un gestore di richiesta per il provider di documenti, **DocumentProviderEFRFiscalDEU**. Questo gestore viene utilizzato per generare documenti fiscali per il servizio di registrazione fiscale. Viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico del servizio che deve essere registrato nel servizio di registrazione fiscale.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** – Questa richiesta restituisce la risposta insieme ai dati estesi.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il provider di documenti fiscali si trova in **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleGermany.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni per il provider di documenti fiscali da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con il servizio di registrazione fiscale.

L'estensione stazione hardware è **HardwareStation.Extension.EFRSample**. Utilizza il protocollo HTTP per inviare documenti generati dall'estensione CRT per il servizio di registrazione fiscale. Gestisce inoltre le risposte ricevute dal servizio di registrazione fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **EFRHandler** è il punto di ingresso per la trasmissione delle richieste al servizio di registrazione fiscale. Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

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
