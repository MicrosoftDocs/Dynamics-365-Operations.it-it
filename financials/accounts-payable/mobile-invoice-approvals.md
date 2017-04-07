---
title: Approvazioni mobili fatture
description: "Le capacità spostati in Microsoft Dynamics 365 per le operazioni è necessaria un utente aziendali progettare le esperienze mobili. Per gli scenari avanzati, la piattaforma anche consente agli sviluppatori estendere le capacità quando desiderano. La maggior parte del modo più efficiente di ottenere alcuni nuovi concetti del cellulare è di passare attraverso il processo di pianificazione di alcuni scenari. In questo argomento viene utilizzato per fornire un approccio di progettazione gli scenari mobili calcolando le approvazioni fatture fornitore per il cellulare come caso di utilizzo. In questo argomento nella progettazione altre variazioni degli scenari e può applicare anche altri scenari non correlati alle fatture fornitore."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 30229c0d24aed0bd927993b9af76b32d9bb073ee
ms.lasthandoff: 03/31/2017


---

# <a name="mobile-invoice-approvals"></a>Approvazioni mobili fatture

Le capacità spostati in Microsoft Dynamics 365 per le operazioni è necessaria un utente aziendali progettare le esperienze mobili. Per gli scenari avanzati, la piattaforma anche consente agli sviluppatori estendere le capacità quando desiderano. La maggior parte del modo più efficiente di ottenere alcuni nuovi concetti del cellulare è di passare attraverso il processo di pianificazione di alcuni scenari. In questo argomento viene utilizzato per fornire un approccio di progettazione gli scenari mobili calcolando le approvazioni fatture fornitore per il cellulare come caso di utilizzo. In questo argomento nella progettazione altre variazioni degli scenari e può applicare anche altri scenari non correlati alle fatture fornitore.

<a name="prerequisites"></a>Prerequisiti
-------------

| Prerequisito                                                                                            | descrizione                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pre- read mobile manuali                                                                                |(/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform.md)                                                                                                  |
| Dynamics 365 per le operazioni                                                                             | In un ambiente con Microsoft Dynamics 365 per la versione 1611 delle operazioni e Microsoft Dynamics per l'aggiornamento 3 la piattaforma delle operazioni (novembre 2016)                   |
| Impostare il 3204341 KB di hotfix.                                                                              | In Registrazione attività può registrare per errore due controlli vicina per i dialoghi che a discesa è incluso in Dynamics 365 per l'aggiornamento 3 (aggiornamento) novembre 2016 la piattaforma dell'operazione |
| Impostare il 3207800 KB di hotfix.                                                                              | Questo hotfix consente agli allegati con essere pubblicato sul client che spostato è incluso in Dynamics 365 per l'aggiornamento 3 (aggiornamento) novembre 2016 la piattaforma dell'operazione.           |
| Impostare il 3208224 KB di hotfix.                                                                              | Il codice dell'applicazione dell'applicazione mobile di approvazione fatture fornitore è incluso nell'applicazione 7.0.1 Microsoft Dynamics AX (maggio 2016).                          |
| Android Dynamic o un dispositivo di Windows con il app mobile impostate per Dynamics 365 per le operazioni | Ricerca del app Approvazioni nella memoria del app.                                                                                                                     |

## <a name="introduction"></a>Introduzione
Le approvazioni mobili per le fatture fornitore richiedono i tre hotfixes indicati nella sezione "prerequisiti". Questi hotfixes non fanno un'area di lavoro per le approvazioni fatture. Per informazioni sui tempi un'area di lavoro nel contesto del cellulare, leggere il manuale mobile in cui è indicato nella sezione "prerequisiti". L'area di lavoro di approvazione fatture deve essere pianificata. 

Ogni organizzazione orchestra diverso e definisce il proprio processo aziendale delle fatture fornitore. Prima di iniziare a progettare di esperienza mobile per le approvazioni fatture fornitore, valutare i seguenti aspetti del processo aziendale. Il concetto di base è di utilizzare questi punti del più informazioni possibile per ottimizzare le esperienze utente nell'unità.

-   I campi dall'intestazione della fattura l'utente vorrà visualizzare in passato spostato e il relativo ordine?
-   I campi dalle righe fattura l'utente vorrà visualizzare in passato spostato e il relativo ordine?
-   Quante righe della fattura è presente una fattura? Applicare la regola 80-20 e ottimizzazione di seguito per i 80.
-   Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura al dispositivo mobile nelle revisioni? Se la risposta a questo problema in caso affermativo, considerare le domande seguenti:
    -   Quante distribuzioni contabili (prezzo esteso, l'VAT, spese, spaccature e così via, vengono sono per una riga della fattura? Anche in questo caso, applicare la regola 80-20.
    -   Le fatture vengono inoltre le distribuzioni contabili nell'intestazione della fattura? In tal caso, queste devono distribuzioni contabili essere disponibili nell'unità?

> [!NOTE]
> In questo argomento non viene illustrato come modificare le distribuzioni contabili, poiché non è attualmente non sono supportate per scenari mobili.

-   Gli utenti vorranno visualizzare gli allegati per la fattura all'unità?

La pianificazione delle esperienze mobile per le approvazioni fatture, varia in base alle risposte. La destinazione è di ottimizzare l'esperienza utente del processo aziendale il cellulare di un'organizzazione. Nel resto di questo argomento, esamineremo le due variazioni allo scenario in base alle diverse risposte alle domande precedenti. 

In generale generale quando si dedicano alla finestra di progettazione, assicurarsi di cellulare "" emettere le modifiche per evitare la perdita degli aggiornamenti.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Progettazione allo scenario semplice di approvazione fatture per Contoso
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo scenario</th>
<th>Risposta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>I campi dall'intestazione della fattura l'utente vorrà visualizzare in passato spostato e il relativo ordine?</td>
<td><ol>
<li>Nome fornitore</li>
<li>Totale fattura</li>
<li>Conto fatture</li>
<li>Numero fattura</li>
<li>Data fattura</li>
<li>Descrizione fattura</li>
<li>Data di scadenza</li>
<li>Valuta della fattura</li>
</ol></td>
</tr>
<tr class="even">
<td>I campi dalle righe fattura l'utente vorrà visualizzare in passato spostato e il relativo ordine?</td>
<td><ol>
<li>Categoria di approvvigionamento</li>
<li>Quantità</li>
<li>Prezzo unitario</li>
<li>Importo netto riga</li>
<li>Importo 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quante righe della fattura è presente una fattura? Applicare la regola 80-20 e ottimizzazione di seguito per i 80.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura al dispositivo mobile nelle revisioni?</td>
<td>Sì</td>
</tr>
<tr class="odd">
<td>Quante distribuzioni contabili (prezzo esteso, l'VAT, spese e così via, vengono sono per una riga della fattura? Anche in questo caso, applicare la regola 80-20.</td>
<td>Prezzo esteso: VAT: 2 Spese: 0 0</td>
</tr>
<tr class="even">
<td>Le fatture vengono inoltre le distribuzioni contabili nell'intestazione della fattura? In tal caso, queste devono distribuzioni contabili essere disponibili nell'unità?</td>
<td>Non utilizzato</td>
</tr>
<tr class="odd">
<td>Gli utenti vorranno visualizzare gli allegati per la fattura all'unità?</td>
<td>Sì</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Crea area di lavoro

1.  In un browser, aperto Dynamics 365 per le operazioni e di firma.
2.  Una volta completati in, aggiungere ** &mode=mobile ** all'URL come illustrato nella seguente esempio e aggiornare la pagina: https://yoururl/?cmp=usmf&mi=DefaultDashboard**&mode=mobile**&lt;&gt;
3.  Fare clic su ** impostazioni ** (ingranaggio) in l pulsante in alto a destra della pagina e fare clic su ** app mobile **. In Designer di cellulare del app è indicato così come la funzione Registrazione attività è indicato.
4.  Fare clic su ** aggiungere ** per creare una nuova area di lavoro. Per questo esempio, assegnare l'area di lavoro ** recuperare le approvazioni **.
5.  Immettere una descrizione.
6.  Selezionare un colore dell'area di lavoro. Colore di area di lavoro verrà utilizzato per lo stile globale delle esperienze mobile per l'area di lavoro.
7.  Selezionare un'icona per l'area di lavoro.
8.  Fare clic su ** effettuato **
9.  Fare clic su ** pubblicare l'area di lavoro ** per salvare le modifiche

### <a name="vendor-invoices-assigned-to-me"></a>Fatture fornitore assegnate all'utente

La prima pagina mobile in cui è consigliabile pianificare l'elenco di fatture assegnato all'utente per la revisione. Per pianificare la pagina di cellulare, utilizzare VendMobileInvoiceAssignedToMeListPage ** ** impaginano in Dynamics 365 per le operazioni. Prima di completare questa procedura, assicurarsi di almeno una fattura fornitore sia assegnati per la visualizzazione e la riga fattura è due distribuzioni. Questa impostazione soddisfa i requisiti di questo scenario.

1.  In Dynamics 365 per le operazioni URL, sostituire il nome della voce di menu con ** VendMobileInvoiceAssignedToMeListPage ** per aprire la versione ** spostata in Fatture fornitore in sospeso assegnate me ** della pagina elenco ** contabilità fornitori ** nel modulo. A seconda del numero delle fatture da pagare nel sistema assegnato all'utente, questa pagina verranno visualizzate le fatture. Per trovare una fattura specifica, è possibile utilizzare il filtro a sinistra. Tuttavia, non richiediamo una fattura specifica per questo esempio. Per appena una fattura assegnati ad esempio desiderano consentire a progettare la pagina spostato. Le pagine disponibili sono state progettato appositamente per creare gli scenari mobili per la fattura fornitore. Di conseguenza, è necessario utilizzare queste pagine. L'URL deve essere il seguente URL e dopo l'applicazione dello voci, la pagina indicato nella figura deve essere publicata: https://yourURL/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile&lt;&gt;[di fatture fornitore in attesa![assegnate me pagina (]. /media/mobile-invoice-approvals01-1024x281.png)](. /media/mobile-invoice-approvals01.png)
2.  ** Impostazioni Cliccano ** il pulsante (di ingranaggio) nell'angolo superiore destro della pagina e fare clic su ** app mobile **
3.  Selezionare nell'area di lavoro e fare clic su ** modifica **
4.  Fare clic su ** aggiungere la pagina ** per creare la prima pagina spostato.
5.  Immettere un nome, ad esempio ** recuperare le fatture fornitore ** e una descrizione, ad esempio ** fatture fornitore assegnate me per l'esame **.
6.  Click **Done**.
7.  In Progettazione di cellulare, ** ** campi nella scheda, fare clic su ** campi selezionati **. Nelle colonne della pagina elenco devono essere alla figura seguente. [colonne![delle fatture fornitore in attesa assegnate me pagina (]. /media/mobile-invoice-approvals02-1024x117.png)](. /media/mobile-invoice-approvals02.png)
8.  Aggiungere colonne necessarie dalla pagina elenco da cui deve essere visualizzata agli utenti della pagina spostato. Ordine in cui viene aggiunto l'ordine in cui i campi visualizzati in utilizzatore finale. Il solo per modificare l'ordine di campi verrà riselezionando tutti i campi. In base ai requisiti di questo esempio, i seguenti otto campi obbligatori. Tuttavia, alcuni utenti possono considerare otto campi troppe informazioni sulla visualizzazione di un dispositivo mobile. Di conseguenza, mostreremo solo i campi più importanti spostato nell'elenco. I campi rimanenti sembreranno visualizzare i dettagli che pianificare in un secondo momento. Per ora, aggiungeremo i seguenti campi. Fare clic sul segno (**+**) nelle colonne da aggiungere alla pagina spostato.
    1.  Nome fornitore
    2.  Totale fattura
    3.  Conto fatture
    4.  Numero fattura
    5.  Data fattura

    Dopo che i campi vengono aggiunti, la pagina deve essere spostato alla figura seguente. [la pagina![dopo i campi viene aggiunto (]. /media/mobile-invoice-approvals03.png)](. /media/mobile-invoice-approvals03.png)
9.  È inoltre possibile aggiungere le seguenti colonne, in modo da consentire possiamo successivamente le azioni del flusso di lavoro.
    1.  Consente di visualizzare le attività completata
    2.  Consente di visualizzare le attività del delegato
    3.  Visualizza l'attività di Richiamo
    4.  Visualizza l'attività di scarto
    5.  Consente di visualizzare le attività di completamento di richiesta
    6.  La visualizza l'attività presenta di nuovo

10. Fare clic su ** effettuato ** per annullare modalità di modifica.
11. Fare clic su Indietro ** ** quindi ** effettuato ** uscire dall'area di lavoro
12. Fare clic su ** pubblicare l'area di lavoro ** per salvare il lavoro.
13. Attivare ** totale fattura di visualizzazione nell'elenco in sospeso delle fatture fornitore ** nel modulo Accounts payable parameters in ** ** fattura. Tenere presente che, consentendo soltanto a questo parametro, i totali fattura verranno calcolati da visualizzare nella pagina elenco in attesa delle fatture fornitore. Si tratta di una nuova funzione nella correzione rapida 3208224 di registrazione.

### <a name="vendor-invoice-details"></a>Dettagli fattura fornitore

Per pianificare la pagina dei dettagli del cellulare, utilizzare VendMobileInvoiceHeaderDetails ** ** impaginano in Dynamics 365 per le operazioni. Tenere presente che, a seconda del numero di fatture da pagare nel sistema, in questa pagina precedente a quella della fattura (la fattura creata innanzitutto). Per trovare una fattura specifica, è possibile utilizzare il filtro a sinistra. Tuttavia, non richiediamo una fattura specifica per questo esempio. Per solo alcuni dati della fattura in per consentire a Microsoft di pianificare quale la pagina spostato. [pagina del flusso di lavoro![(]. /media/mobile-invoice-approvals04-1024x425.png)](. /media/mobile-invoice-approvals04.png)

1.  In Dynamics 365 per le operazioni, URL sostituiscono il nome della voce di menu con ** VendMobileInvoiceHeaderDetails ** per aprire il modulo
2.  Consente di aprire Progettazione report spostato da ** impostazioni ** pulsante di ingranaggio ().
3.  Fare clic su ** modifica ** viene subito per avviare la modalità di modifica nell'area di lavoro.
4.  Selezionare ** recuperare le fatture fornitore ** impaginano creato in precedenza quindi su ** ** modifica.
5.  ** ** Campi nella scheda, fare clic su ** griglia ** la colonna.
6.  Fare clic su ** proprietà ** &gt; ** aggiungere la pagina **. ** Nota: ** Quando si fa clic su ** griglia ** l'intestazione e si aggiunge una pagina, la relazione con la pagina dei dettagli è impostato automaticamente.
7.  Immettere un titolo della pagina, ad esempio ** dettagli della fattura ** e una descrizione, ad esempio ** intestazione e dettagli della riga dello storico di **.
8.  Fare clic su ** campi selezionati **. Tenere presente che, l'ordine in cui viene aggiunto l'ordine in cui i campi visualizzati in utilizzatore finale. Il solo per modificare l'ordine di campi verrà riselezionando tutti i campi.
9.  Aggiungere i seguenti campi dall'intestazione, in base ai requisiti per questo scenario:
    1.  Nome fornitore
    2.  Totale fattura
    3.  Conto fatture
    4.  Numero fattura
    5.  Data fattura
    6.  Descrizione fattura
    7.  Data di scadenza
    8.  Valuta della fattura

10. Aggiungere i seguenti campi dalla griglia di righe nella pagina:
    1.  Categoria di approvvigionamento
    2.  Quantità
    3.  Prezzo unitario
    4.  Importo netto riga
    5.  Importo 1099

11. Dopo tutti i campi da due passaggi precedenti sono stati aggiunti, fare clic su ** effettuato **. Verrà visualizzata la pagina deve essere alla figura seguente. [![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Fare clic su ** effettuato ** per annullare modalità di modifica.
13. Fare clic su Indietro ** ** quindi ** effettuato ** uscire dall'area di lavoro
14. Fare clic su ** pubblicare l'area di lavoro ** per salvare il lavoro

### <a name="workflow-actions"></a>Azioni flusso di lavoro

Per aggiungere le azioni del flusso di lavoro, utilizzare VendMobileInvoiceHeaderDetails ** ** impaginano in Dynamics 365 per le operazioni. Per visualizzare questa pagina, sostituire il nome della voce di menu nell'URL, ad esempio la selezione precedente. Per aprire Progettazione report spostato da ** impostazioni ** pulsante di ingranaggio (). Seguire questi passaggi per aggiungere le azioni del flusso di lavoro nella pagina dei dettagli.

1.  Fare clic su ** modifica ** viene subito per avviare la modalità di modifica nell'area di lavoro.
2.  Selezionare ** dettagli della fattura ** impaginano creato in precedenza quindi su ** ** modifica.
3.  ** Azioni ** nella scheda, fare clic su Aggiungi ** ** azione.
4.  Immettere un titolo dell'azione, come ** approvare ** e una descrizione, ad esempio ** approvare la fattura **. Si noti che il titolo di azione immesso in questo campo diventa il nome dell'azione che verrà visualizzata all'utente nell'app Approvazioni spostato.
5.  Click **Done**.
6.  Fare clic su ** campi selezionati **.
7.  Passare al processo del flusso di lavoro ** VendMobileInvoiceHeaderDetails ** nella pagina ed eseguire l'azione aver voluto la registrazione. Assicurarsi di immettere commenti del flusso di lavoro durante il processo, in modo da un campo di commenti viene inoltre incluso in passato spostato.
8.  Dopo che l'azione del flusso di lavoro viene eseguita, fare clic su ** effettuato ** per completare l'attività selezionata i campi.
9.  Fare clic su ** effettuato ** per annullare modalità di modifica.
10. Fare clic su Indietro ** ** quindi ** effettuato ** uscire dall'area di lavoro
11. Fare clic su ** pubblicare l'area di lavoro ** per salvare il lavoro
12. Ripetere i passaggi da 3 a 11 per registrare tutte le azioni necessarie del flusso di lavoro. Tenere presente che, è obbligatorio essere assegnate a fatture in una condizione per rendere disponibili le azioni del flusso di lavoro per l'utente che si desidera pianificare.
13. Apre il Blocco note o Microsoft Visual Studio e inserire il seguente codice. Salvare il file come file di .js. Questo codice viene due elementi:
    1.  Nasconde le colonne correlate ai flussi di lavoro aggiuntivi disponibili aggiunto in precedenza nella pagina elenco spostato. È stato aggiunto le colonne in modo che il app cui le informazioni nel contesto e è necessario il passaggio successivo.
    2.  In base al passaggio del flusso di lavoro attiva, viene applicata la logica per visualizzare solo le azioni.

Tenere presente che, il nome delle pagine e altri controlli nel codice JS devono essere ugualiarea di lavoro.

1.  conto principale (funzione di metadataService, dataService, cacheService, $q) {reso {appInit: (funzione appMetadata) {controlli di nascondere di //che devono essere presenti, ma non metadataService.configureControl visibile ("Mio-fornitore- fatture ", "ShowAccept", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowApprove", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowReject", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowDelegate", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowRequestChange", nascosto: { riga});              metadataService.configureControl ("Mio-fornitore- fatture ", "ShowRecall", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowComplete", nascosto: { riga});            metadataService.configureControl ("Mio-fornitore- fatture ", "ShowResubmit", nascosto: { riga});            }, pageInit: (funzione pageMetadata, params) {se Fattura- dettagli (") di == di pageMetadata.Name "{azioni del flusso di lavoro di l o nascondere di //in base al passaggio metadataService.configureAction del flusso di lavoro ("," accettare visibile: { riga});                    metadataService.configureAction ("Approvare", visibile: { riga});                    metadataService.configureAction ("e", visibile: { riga});                    metadataService.configureAction ("a", visibile: { riga});                    metadataService.configureAction ("Richiesta- modifica", visibile: { riga});                    metadataService.configureAction Richiamo ("," visibile: { riga});                    metadataService.configureAction ("a", visibile: { riga});                    metadataService.configureAction ("," inviare di nuovo disponibile: { riga});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  Caricare il file del codice nell'area di lavoro selezionando ** logica ** la scheda
3.  Fare clic su ** effettuato ** per annullare modalità di modifica.
4.  Fare clic su Indietro ** ** quindi ** effettuato ** uscire dall'area di lavoro
5.  Fare clic su ** pubblicare l'area di lavoro ** per salvare il lavoro

### <a name="vendor-invoice-attachments"></a>Allegati fatture fornitore

1.  ** Impostazioni Cliccano ** il pulsante (di ingranaggio) nell'angolo superiore destro della pagina e fare clic su ** app mobile **
2.  Fare clic su ** modifica ** viene subito per avviare la modalità di modifica nell'area di lavoro.
3.  Selezionare ** dettagli della fattura ** impaginano creato in precedenza quindi su ** ** modifica.
4.  Impostare ** gestione documenti ** l'opzione ** Sì ** come indicato di seguito. ** Nota: ** Se non sono presenti fabbisogni visualizzare gli allegati del dispositivo mobile, è possibile lasciare questa opzione impostata alcuna ** **, che è l'impostazione predefinita.
5.  [docmanagement![(]. /media/docmanagement-216x300.png)](. /media/docmanagement.png)
6.  Fare clic su ** effettuato ** per annullare modalità di modifica.
7.  Fare clic su Indietro ** ** quindi ** effettuato ** uscire dall'area di lavoro
8.  Fare clic su ** pubblicare l'area di lavoro ** per salvare il lavoro

### <a name="vendor-invoice-line-distributions"></a>Distribuzioni delle righe fattura fornitore

I requisiti di questo scenario confermare che ci saranno utilizzato solo nelle distribuzioni a livello di riga e una fattura che contiene sempre una sola riga. Poiché questo scenario è semplice, l'esperienza utente del dispositivo mobile sia sufficiente semplice che l'utente non è presente in più livelli per visualizzare le distribuzioni. Le fatture fornitore in Dynamics 365 per le operazioni includono l'opzione di mostra di tutte le distribuzioni dall'intestazione della fattura. Questa passato viene delle informazioni necessarie per abbiamo lo scenario spostato. Di conseguenza, useremo ** VendMobileInvoiceAllDistributionTree ** la pagina per pianificare la parte dello scenario spostato. 

> [!NOTE] 
> Conoscere i requisiti sono facilita la pagina decidere quali specifica da utilizzare con precisione e la quantità di ottimizzare l'esperienza mobile per l'utente per pianificare lo scenario. Nel secondo scenario, useremo una pagina diversa per visualizzare le distribuzioni, poiché i requisiti di questo scenario diversi.

1.  Nell'URL, sostituire il nome della voce di menu, ad esempio è stata effettuata prima. Verrà visualizzata la pagina visualizzata deve essere alla figura seguente. [![qualsiasi pagina di distribuzioni (]. /media/mobile-invoice-approvals06.png)](. /media/mobile-invoice-approvals06.png)
2.  Consente di aprire Progettazione report spostato da ** impostazioni ** pulsante di ingranaggio ().
3.  Fare clic su ** modifica ** viene subito per avviare la modalità di modifica nell'area di lavoro. ** Nota: ** Vedrete che due pagine sono state create automaticamente. Il sistema crea queste pagine, poiché è stato attivato la gestione dei documenti nella sezione precedente. È possibile ignorare tali pagine.
4.  Fare clic su ** aggiungere la pagina **.
5.  Immettere un titolo della pagina, ad esempio ** contabilità di visualizzazione ** e una descrizione, ad esempio ** visualizzazione che rappresenta la fattura **.
6.  Click **Done**.
7.  ** ** Campi nella scheda, fare clic su ** campi selezionati **, selezionare i seguenti campi della pagina di distribuzioni e fare clic su ** effettuato **:
    1.  Importo
    2.  Valuta
    3.  Conto CoGe

> [!NOTE] 
> Non magazzino è attualmente selezionato ** descrizione ** la colonna nella griglia di distribuzioni, poiché i requisiti di questo scenario è confermato che il prezzo esteso è l'unico importo che ci saranno distribuzioni. Pertanto, l'utente non richiede altre campo per determinare l'importo del tipo che la distribuzione sia. Tuttavia, nello scenario successiva, ** ** utilizziamo queste informazioni, poiché i requisiti di questo scenario indica che un altro importo di tipo ha distribuzioni, ad esempio VAT).
8.  Fare clic su ** effettuato ** per annullare modalità di modifica.
9.  Fare clic su Indietro ** ** quindi ** effettuato ** uscire dall'area di lavoro
10. Fare clic su ** pubblicare l'area di lavoro ** per salvare il lavoro

** Nota: ** ** Contabilità ** di visualizzare la pagina spostato non è attualmente associata a una delle pagine mobili disponibili previsto fino a questo momento. Poiché l'utente deve poter accedere ** contabilità di visualizzazione della pagina ** ** dettagli della fattura ** la pagina del dispositivo mobile, dobbiamo specificare il percorso ** dettagli della fattura ** dalla pagina ** contabilità di visualizzazione ** nella pagina. Stabiliamo questo percorso utilizzando la logica aggiuntivo tramite il JavaScript.

1.  Apre il file di .js creato in precedenza e aggiungere righe che vengono evidenziate nel codice riportato di seguito. Questo codice viene due elementi:
    1.  Aiuta la garanzia che gli utenti non potranno accedere direttamente all'area di lavoro della contabilità ** ** visualizzazione della pagina.
    2.  Stabilisce un controllo di navigazione ** dettagli della fattura ** dalla pagina ** contabilità di visualizzazione ** nella pagina.

> [!NOTE] 
> Nome delle pagine e di altri controlli nel codice JS deve essere lo stessoarea di lavoro.

1.  conto principale (funzione di metadataService, dataService, cacheService, $q) {reso {appInit: (funzione appMetadata) {controlli di nascondere di //che devono essere presenti, ma non metadataService.configureControl visibile ("Mio-fornitore- fatture ", "ShowAccept", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowApprove", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowReject", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowDelegate", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowRequestChange", nascosto: { riga});              metadataService.configureControl ("Mio-fornitore- fatture ", "ShowRecall", nascosto: { riga});                metadataService.configureControl ("Mio-fornitore- fatture ", "ShowComplete", nascosto: { riga});            metadataService.configureControl ("Mio-fornitore- fatture ", "ShowResubmit", nascosto: { riga});                Il di nascondere //impagina non applicabile per percorso metadataService.hideNavigation ("contabilità Visualizzazione- ") radice;                //Link per visualizzare metadataService.addLink di stima ("Fattura- dettagli ", "contabilità Visualizzazione- ", "Visualizzazione-contabilità-NAV- control ", "contabilità di visualizzazione", soddisfatte);            }, pageInit: (funzione pageMetadata, params) {se Fattura- dettagli (") di == di pageMetadata.Name "{azioni del flusso di lavoro di l o nascondere di //in base al passaggio metadataService.configureAction del flusso di lavoro ("," accettare visibile: { riga});                    metadataService.configureAction ("Approvare", visibile: { riga});                    metadataService.configureAction ("e", visibile: { riga});                    metadataService.configureAction ("a", visibile: { riga});                    metadataService.configureAction ("Richiesta- modifica", visibile: { riga});                    metadataService.configureAction Richiamo ("," visibile: { riga});                    metadataService.configureAction ("a", visibile: { riga});                    metadataService.configureAction ("," inviare di nuovo disponibile: { riga});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  Caricare il file del codice nell'area di lavoro selezionando ** logica ** la scheda sovrascrivere il codice precedente
3.  Fare clic su ** effettuato ** per annullare modalità di modifica.
4.  Fare clic su Indietro ** ** quindi ** effettuato ** uscire dall'area di lavoro
5.  Fare clic su ** pubblicare l'area di lavoro ** per salvare il lavoro

### <a name="validation"></a>Convalida

Dal dispositivo mobile, aprire il app e connettersi a l Dynamics 365 per l'istanza delle operazioni. Verificare che firmiate nella società in cui le fatture fornitore vengono assegnate per la revisione. È possibile eseguire le seguenti operazioni:

-   ** Per recuperare le approvazioni ** l'area di lavoro.
-   Eseguire ** recuperare le approvazioni ** nell'area di lavoro e vedere ** recuperare le fatture fornitore ** la pagina.
-   Eseguire il ** recuperare le fatture fornitore ** impaginano e visualizzare l'elenco delle fatture assegnato all'utente.
-   Drill nelle fatture cliente e visualizzare i dettagli e i dettagli riga dell'intestazione della fattura.
-   Nei dettagli di pagine, vedere un collegamento agli allegati e utilizzare questo collegamento per spostarsi all'elenco degli allegati e visualizzare gli allegati.
-   Nei dettagli di pagine, vedere un collegamento ** contabilità di visualizzazione ** nella pagina e utilizzare questo collegamento per accedere alla pagina di distribuzioni e visualizzare le distribuzioni.
-   Nei dettagli di pagine, fare clic su ** azioni ** il menu nella parte inferiore ed eseguire azioni del flusso di lavoro applicabili al passaggio del flusso di lavoro.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Progettazione allo scenario complessa di approvazione fatture per Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo scenario</th>
<th>Risposta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>I campi dall'intestazione della fattura l'utente vorrà visualizzare in passato spostato e il relativo ordine?</td>
<td><ol>
<li>Nome fornitore</li>
<li>Importo fattura</li>
<li>Conto fatture</li>
<li>Numero fattura</li>
<li>Data fattura</li>
<li>Descrizione fattura</li>
<li>Data di scadenza</li>
<li>Valuta della fattura</li>
</ol></td>
</tr>
<tr class="even">
<td>I campi dalle righe fattura l'utente vorrà visualizzare in passato spostato e il relativo ordine?</td>
<td><ol>
<li>Categoria di approvvigionamento</li>
<li>Quantità</li>
<li>Prezzo unitario</li>
<li>Importo netto riga</li>
<li>Importo 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quante righe della fattura è presente una fattura? Applicare la regola 80-20 e ottimizzazione di seguito per i 80.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura al dispositivo mobile nelle revisioni?</td>
<td>Sì</td>
</tr>
<tr class="odd">
<td>Quante distribuzioni contabili (prezzo esteso, l'VAT, spese e così via, vengono sono per una riga della fattura? Anche in questo caso, applicare la regola 80-20.</td>
<td>Prezzo esteso: VAT: 2 Spese: 2 2</td>
</tr>
<tr class="even">
<td>Le fatture vengono inoltre le distribuzioni contabili nell'intestazione della fattura? In tal caso, queste devono distribuzioni contabili essere disponibili nell'unità?</td>
<td>Non utilizzato</td>
</tr>
<tr class="odd">
<td>Gli utenti vorranno visualizzare gli allegati per la fattura all'unità?</td>
<td>Sì</td>
</tr>
</tbody>
</table>

### <a name="exercise"></a>Esercizio

Nelle variazioni possono essere effettuate per lo scenario 1, in base ai requisiti dello scenario 2. Utilizzare questa sezione viene illustrato come lavoro che è possibile completare dell'apprendimento di reporting.

1.  Poiché più righe della fattura verranno programmate nello scenario 2, le seguenti modifiche alla struttura consentano di ottimizzare l'esperienza utente del dispositivo mobile:
    1.  Anziché dello storico delle righe nella pagina dei dettagli (come lo scenario 1), gli utenti può scegliere di visualizzare le righe in una pagina separata spostato.
    2.  Poiché più righe della fattura viene programmata in questo scenario, se ** VendMobileInvoiceAllDistributionTree ** la pagina viene utilizzata per pianificare la pagina di distribuzioni per il cellulare (ad esempio lo scenario 1), potrebbe essere confusionario all'utente correli le righe le distribuzioni. Di conseguenza, utilizzare VendMobileInvoiceLineDistributionTree ** ** la pagina per pianificare la pagina di distribuzioni.
    3.  A livello ideale, distribuzioni devono essere visualizzate nel contesto di una riga della fattura in questo scenario. Di conseguenza, assicurarsi che un utente possa eseguire in una riga per visualizzare la pagina di distribuzioni. Utilizzare la capacità di collegamento di pagina per stabilire tra trapano-, come dimensioni nell'intestazione e sulle pagine nello scenario 1.

2.  Poiché più Tipo di importo viene programmato nelle distribuzioni allo scenario 2 (sconti, VAT, spese), verrà utile visualizzare la descrizione dell'importo del tipo. Si (omesso queste informazioni nello scenario 1).

## <a name="conclusion"></a>Conclusione
Area spostati né le capacità dell'applicazione consentono di progettare gli scenari che vengono spostati ottimizzati per una base di utenti di un'organizzazione. A seconda degli esempi disponibili in questo argomento, è possibile provare altre modifiche e creare le esperienze diversi da soddisfare un fabbisogno specifica.


