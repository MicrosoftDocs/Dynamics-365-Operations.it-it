---
title: Approvazioni fatture per dispositivi mobili
description: Questo argomento è destinato a fornire un approccio pratico alla progettazione di scenari mobili utilizzando l'approvazione delle fatture fornitore come caso d'uso.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9e6138ccd92019f52afab0d8ed4b8cf64d66ff24
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897698"
---
# <a name="mobile-invoice-approvals"></a>Approvazioni fatture per dispositivi mobili

[!include [banner](../includes/banner.md)]

Le funzionalità mobili consentono agli utenti aziendali di progettare esperienze mobili. Per gli scenari avanzati, la piattaforma anche consente agli sviluppatori di estendere le funzionalità nel modo desiderato. Il modo più efficace di apprendere alcuni dei nuovi concetti sulle funzionalità mobili è di esaminare il processo di progettazione di alcuni scenari. Questo argomento è destinato a fornire un approccio pratico alla progettazione di scenari mobili utilizzando l'approvazione delle fatture fornitore come caso d'uso. Questo argomento dovrebbe aiutare nella progettazione di altre variazioni degli scenari e può essere applicato anche ad altri scenari non correlati alle fatture fornitore.

<a name="prerequisites"></a>Prerequisiti
-------------

| Prerequisito                                                                                            | Descrizione                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lettura preventiva del manuale sulle funzionalità mobili                                                                                |[Piattaforma mobile](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 Finance                                                                              | Un ambiente con versione 1611 e aggiornamento 3 della piattaforma (novembre 2016)                   |
| Installare l'aggiornamento rapido KB 3204341.                                                                              | Registrazione attività può registrare per errore due comandi di chiusura per le finestre di dialogo a discesa. Incluso nell'aggiornamento 3 della piattaforma (aggiornamento di novembre 2016) |
| Installare l'aggiornamento rapido KB 3207800.                                                                              | Questo aggiornamento rapido consente agli allegati di essere visualizzati sul client mobile. Incluso nell'aggiornamento 3 della piattaforma (aggiornamento di novembre 2016).           |
| Installare l'aggiornamento rapido KB 3208224.                                                                              | Codice dell'applicazione mobile di approvazione fatture fornitore. Incluso nella versione 7.0.1 (maggio 2016).                          |
| Un dispositivo Android o iOS o Windows su cui è installata l'applicazione mobile. | Cercare l'app nell'app store appropriato.                                                                                                                     |

## <a name="introduction"></a>Introduzione
Le approvazioni mobili per le fatture fornitore richiedono i tre aggiornamenti rapidi indicati nella sezione "Prerequisiti". Questi aggiornamenti rapidi non forniscono un'area di lavoro per le approvazioni fatture. Per informazioni su cos'è un'area di lavoro nel contesto delle funzionalità mobili, leggere il relativo manuale indicato nella sezione "Prerequisiti". L'area di lavoro di approvazione fatture deve essere progettata. 

Ogni organizzazione orchestra e definisce il proprio processo aziendale per le fatture fornitore in modo diverso. Prima di iniziare a progettare un'esperienza mobile per le approvazioni fatture fornitore, valutare i seguenti aspetti del processo aziendale. Il concetto di base è di utilizzare questi punti dati il più possibile per ottimizzare l'esperienza utente sul dispositivo.

-   Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?
-   Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?
-   Quante righe fattura sono presenti in una fattura? Applicare la regola 80-20 qui e ottimizzare per l'80%.
-   Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni? Se la risposta a questa domanda è affermativa, considerare le domande seguenti:
    -   Quante distribuzioni contabili (prezzo esteso, IVA, spese, suddivisioni e così via) esistono per una riga della fattura? Anche in questo caso, applicare la regola 80-20.
    -   Le fatture hanno distribuzioni contabili anche nell'intestazione? In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?

    > [!NOTE]
    > In questo argomento non viene illustrato come modificare le distribuzioni contabili, poiché questa funzionalità non è attualmente supportata per scenari mobili.

-   Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?

La progettazione dell'esperienza mobile per le approvazioni fatture varierà in base alle risposte a queste domande. L'obiettivo è di ottimizzare l'esperienza utente del processo aziendale sui dispositivi mobili di un'organizzazione. Nel resto di questo argomento, esamineremo due variazioni allo scenario basate sulle diverse risposte alle domande precedenti. 

In generale quando si lavora con lo strumento di progettazione mobile, assicurarsi di "pubblicare" le modifiche per evitare la perdita degli aggiornamenti.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Progettazione di uno scenario di approvazione fatture semplice per Contoso
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
<td>Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</td>
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
<td>Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</td>
<td><ol>
<li>Categoria di approvvigionamento</li>
<li>Quantità</li>
<li>Prezzo unitario</li>
<li>Importo netto riga</li>
<li>Importo 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quante righe fattura sono presenti in una fattura? Applicare la regola 80-20 qui e ottimizzare per l'80%.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</td>
<td>Sì</td>
</tr>
<tr class="odd">
<td>Quante distribuzioni contabili (prezzo esteso, IVA, spese e così via) esistono per una riga della fattura? Anche in questo caso, applicare la regola 80-20.</td>
<td>Prezzo esteso: 2 IVA: 0 Spese: 0</td>
</tr>
<tr class="even">
<td>Le fatture hanno distribuzioni contabili anche nell'intestazione? In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</td>
<td>Non utilizzato</td>
</tr>
<tr class="odd">
<td>Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</td>
<td>Sì</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Creare l'area di lavoro

1.  In un browser, accedere all'applicazione.
2.  Effettuato l'accesso. aggiungere **&mode=mobile** all'URL come mostrato nell'esempio seguente e aggiornare la pagina: https://&lt;urlutente&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**. Lo strumento di progettazione app per dispositivo mobili deve apparire come Registrazione attività.
4.  Fare clic su **Aggiungi** per creare una nuova area di lavoro. Per questo esempio, chiamare l'area di lavoro **Approvazioni personali**.
5.  Immettere una descrizione.
6.  Seleziona un colore per l'area di lavoro. IL colore dell'area di lavoro verrà utilizzato per lo stile globale dell'esperienza mobile per l'area di lavoro.
7.  Selezionare un'icona per l'area di lavoro.
8.  Fare clic su **Fine**.
9.  Fare clic su **Pubblica area di lavoro** per salvare le modifiche.

### <a name="vendor-invoices-assigned-to-me"></a>Fatture fornitore assegnate all'utente

La prima pagina in versione mobile che è consigliabile progettare è l'elenco di fatture assegnate all'utente per la revisione. Per progettare questa pagina in versione mobile, utilizzare la pagina **VendMobileInvoiceAssignedToMeListPage**. Prima di completare questa procedura, assicurarsi di avere almeno una fattura fornitore assegnata per la revisione e che la riga fattura abbia due distribuzioni. Questa impostazione soddisfa i requisiti di questo scenario.

1.  Nell'URL, sostituire il nome della voce di menu con **VendMobileInvoiceAssignedToMeListPage** per aprire la versione mobile della pagina elenco **Fatture fornitore in sospeso assegnate all'utente** nel modulo **Contabilità fornitori**. A seconda del numero delle fatture assegnate all'utente, questa pagina mostrerà tali fatture. È possibile usare il filtro a sinistra per trovare una fattura specifica. Tuttavia, non è richiesta una fattura specifica per questo esempio. È solo necessario avere qualche fattura assegnata in modo da poter progettare la pagina in versione mobile. Le nuove pagine disponibili sono state progettate appositamente per sviluppare scenari mobili per la fattura fornitore. Di conseguenza, è necessario utilizzare queste pagine. L'URL deve essere simile al seguente e dopo l'immissione la pagina indicata nella figura deve essere visualizzata: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile 

    [![Pagina Fatture fornitore in sospeso assegnate all'utente](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
    
2.  Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.
3.  Selezionare l'area di lavoro e fare clic su **Modifica**
4.  Fare clic su **Aggiungi pagina** per creare la prima pagina in versione mobile.
5.  Immettere un nome, ad esempio **My vendor invoices** e una descrizione, ad esempio **Vendor invoices assigned to me for review**.
6.  Fare clic su **Fine**.
7.  Nello strumento di progettazione mobile, nella scheda **Campi** fare clic su **Seleziona campi**. Le colonne della pagina elenco devono essere simili alla figura seguente. 

    [![Colonne nella pagina Fatture fornitore in sospeso assegnate all'utente](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
    
8.  Aggiungere le colonne necessarie dalla pagina elenco che devono essere visualizzate agli utenti nella pagina in versione mobile. L'ordine di aggiunta è l'ordine in cui i campi verranno visualizzati all'utente finale. Il solo modo per modificare l'ordine dei campi è riselezionarli tutti. In base ai requisiti di questo scenario, sono necessari i seguenti otto campi. Tuttavia, alcuni utenti potrebbero considerare otto campi troppe informazioni da avere su un dispositivo mobile. Di conseguenza, mostreremo solo i campi più importanti nella visualizzazione elenco mobile. I campi rimanenti sembreranno appariranno nella visualizzazione dettagli che progetteremo in un secondo momento. Per ora, aggiungeremo i seguenti campi. Fare clic sul segno (**+**) nelle colonne da aggiungere alla pagina mobile.
    - Nome fornitore
    - Totale fattura
    - Conto fatture
    - Numero fattura
    - Data fattura

    Dopo che i campi vengono aggiunti, la pagina mobile deve somigliare alla figura seguente. 
    
    [![Pagina dopo l'aggiunta dei campi](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)

9.  È inoltre necessario aggiungere le seguenti colonne ora, in modo da abilitare le azioni del flusso di lavoro successivamente.
    - Mostra attività completare
    - Mostra attività delegare
    - Mostra attività richiamare
    - Mostra attività rifiutare
    - Mostra attività richiedere completamento
    - Mostra attività inviare nuovamente

10. Fare clic su **Fine** per uscire dalla modalità di modifica.
11. Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro
12. Fare clic su **Pubblica area di lavoro** per salvare il lavoro.
13. Abilitare **Visualizza totale fatture su elenco fatture fornitore in sospeso** nel modulo dei parametri contabilità fornitori in **Fattura**. Tenere presente che solo abilitando questo parametro, i totali fattura verranno calcolati e visualizzati nella pagina elenco delle fatture fornitore in sospeso. Si tratta di una nuova funzionalità nell'ambito dell'aggiornamento rapido 3208224.

### <a name="vendor-invoice-details"></a>Dettagli fattura fornitore

Per progettare la pagina dei dettagli fattura per l'ambiente mobile, utilizzare la pagina **VendMobileInvoiceHeaderDetails**. Tenere presente che, a seconda del numero di fatture nel sistema, la pagina mostra la fattura più vecchia (la fattura creata per prima). È possibile usare il filtro a sinistra per trovare una fattura specifica. Tuttavia, non è richiesta una fattura specifica per questo esempio. Sono neecssari solo alcuni dati della fattura per progettare la pagina in versione mobile. 

[![Pagina Flusso di lavoro](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. Nell'URL, sostituire il nome della voce di menu con **VendMobileInvoiceHeaderDetails** per aprire il modulo

2. Aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).

3. Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.

4. Selezionare la pagina **My vendor invoices** creata in precedenza, quindi fare clic su **Modifica**.

5. Nella scheda **Campi** fare clic sull'intestazione di colonna **Griglia**.

6. Fare clic su **Proprietà &gt; Aggiungi pagina**. **Nota:** Quando si fa clic su l'intestazione **Griglia** e si aggiunge una pagina, la relazione con la pagina dei dettagli è impostata automaticamente.

7. Immettere un titolo della pagina, ad esempio **Invoice details** e una descrizione, ad esempio **View invoice header and line details**.

8. Fare clic su **Seleziona campi**. Notare che l'ordine di aggiunta è l'ordine in cui i campi verranno visualizzati all'utente finale. Il solo modo per modificare l'ordine dei campi è riselezionarli tutti. 

9. Aggiungere i campi seguenti dall'intestazione in base ai requisiti di questo scenario:
   - Nome fornitore
   - Totale fattura
   - Conto fatture
   - Numero fattura
   - Data fattura
   - Descrizione fattura
   - Data di scadenza
   - Valuta della fattura

10. Aggiungere i seguenti campi dalla griglia di righe nella pagina:
    - Categoria di approvvigionamento
    - Quantità
    - Prezzo unitario
    - Importo netto riga
    - Importo 1099

11. Dopo che tutti i campi dai due passaggi precedenti sono stati aggiunti, fare clic su **Fine**. La pagina deve essere simili alla figura seguente.
    
    [![Illustrazione che mostra i campi aggiuntivi aggiunti](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)

12. Fare clic su **Fine** per uscire dalla modalità di modifica.

13. Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro

14. Fare clic su **Pubblica area di lavoro** per salvare il lavoro.

### <a name="workflow-actions"></a>Azioni flusso di lavoro

Per aggiungere le azioni del flusso di lavoro, utilizzare la pagina **VendMobileInvoiceHeaderDetails**. Per visualizzare questa pagina, sostituire il nome della voce di menu nell'URL, come fatto in precedenza. Quindi aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio). Seguire questi passaggi per aggiungere le azioni del flusso di lavoro nella pagina dei dettagli. È obbligatorio avere fatture assegnate che si trovato in uno stato tale da rendere disponibili le azioni del flusso di lavoro per l'utente per la progettazione desiderata.

#### <a name="record-workflow-actions"></a>Registrare azioni del flusso di lavoro
1.  Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.
2.  Selezionare la pagina **Invoice details** creata in precedenza quindi fare clic su **Modifica**.
3.  Nella scheda **Azioni** fare clic su **Aggiungi azione**.
4.  Immettere un titolo dell'azione, come **Approve** e una descrizione, ad esempio **Approve invoice**. Si noti che il titolo di azione immesso in questo campo diventa il nome dell'azione che verrà visualizzata all'utente nell'app per dispositivi mobili.
5.  Fare clic su **Fine**.
6.  Fare clic su **Seleziona campi**.
7.  Procedere lungo il processo del flusso di lavoro nella pagina **VendMobileInvoiceHeaderDetails** e completare l'azione che si è voluta registrare. Assicurarsi di immettere commenti del flusso di lavoro durante il processo, in modo che un campo di commenti viene anche incluso nell'esperienza mobile.
8.  Dopo che l'azione del flusso di lavoro viene eseguita, fare clic su **Fine** per completare l'attività Seleziona campi.
9.  Fare clic su **Fine** per uscire dalla modalità di modifica.
10. Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro
11. Fare clic su **Pubblica area di lavoro** per salvare il lavoro.
12. Ripetere i passaggi precedenti per registrare tutte le azioni necessarie del flusso di lavoro. 

#### <a name="create-a-js-file"></a>Creare un file .js
1. Aprire il Blocco note o Microsoft Visual Studio e incollare il seguente codice. Salvare il file come file .js. Il codice effettua quanto segue:
    - Nasconde le colonne extra correlate ai flussi di lavoro che abbiamo aggiunto in precedenza nella pagina elenco in versione mobile. Abbiamo aggiunto le colonne in modo che l'app abbia quelle informazioni nel contesto e possa eseguire il passaggio successivo.
    - In base al passaggio del flusso di lavoro attivo, viene applicata la logica per visualizzare solo queste azioni.

    > [!NOTE]
    > Il nome delle pagine e altri controlli nel codice devono essere gli stessi dell'area di lavoro.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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
    ```

2.  Caricare il file del codice nell'area di lavoro selezionando la scheda **Logica**
3.  Fare clic su **Fine** per uscire dalla modalità di modifica.
4.  Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro
5.  Fare clic su **Pubblica area di lavoro** per salvare il lavoro.

### <a name="vendor-invoice-attachments"></a>Allegati della fattura fornitore

1. Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.

2. Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.

3. Selezionare la pagina <strong>Invoice detailsv **creata in precedenza, quindi fare clic su** Modifica</strong>.

4. Impostare l'opzione **Gestione documenti** su **Sì** come indicato di seguito. **Nota:** Se non sono presenti esigenze di visualizzare gli allegati sul dispositivo mobile, è possibile lasciare questa opzione impostata su **No**, che è l'impostazione predefinita.
   
   ![Gestione documenti](./media/docmanagement-216x300.png)

5. Fare clic su **Fine** per uscire dalla modalità di modifica.

6. Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro

7. Fare clic su **Pubblica area di lavoro** per salvare il lavoro.

### <a name="vendor-invoice-line-distributions"></a>Distribuzioni a livello di riga fattura fornitore

I requisiti di questo scenario confermano che ci saranno solo distribuzioni a livello di riga e che una fattura conterrà sempre una sola riga. Poiché questo scenario è semplice, anche l'esperienza utente sul dispositivo mobile deve essere abbastanza semplice da evitare che l'utente debba eseguire il drill-down di più livelli per visualizzare le distribuzioni. Le fatture fornitore includono l'opzione di mostrare tutte le distribuzioni dall'intestazione della fattura. Questa esperienza è quello che serve per lo scenario mobile. Di conseguenza, useremo la pagina **VendMobileInvoiceAllDistributionTree** per progettare questa parte dello scenario mobile. 

> [!NOTE] 
> Conoscere i requisiti aiuta a decidere quale pagina specifica utilizzare come esattamente ottimizzare l'esperienza mobile per l'utente nella progettazione dello scenario. Nel secondo scenario, useremo una pagina diversa per visualizzare le distribuzioni, poiché i requisiti di quello scenario sono diversi.

1.  Nell'URL, sostituire il nome della voce di menu, come fatto in precedenza. Verrà visualizzata una che deve essere simile alla figura seguente.

    [![Pagina Tutte le distribuzioni](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)

2.  Aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).

3.  Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro. **Nota:**  Vedrete che due pagine sono state create automaticamente. Il sistema crea queste pagine, poiché è stata abilitata la gestione dei documenti nella sezione precedente. È possibile ignorare tali nuove pagine.

4.  Fare clic su **Aggiungi pagina**.

5.  Immettere un titolo della pagina, ad esempio **Visualizza contabilità** e una descrizione, ad esempio **View accounting for the invoice**.

6.  Fare clic su **Fine**.

7.  Nella scheda **Campi** fare clic su **Seleziona campi**, selezionare i campi seguenti dalla pagina delle sitribuzioni e fare clic su **Fine**:
    1.  Importo
    2.  Valuta
    3.  Conto CoGe

    > [!NOTE] 
    > Non abbiamo selezionato la colonna **Descrizione** nella griglia di distribuzioni, poiché i requisiti di questo scenario hanno confermato che il prezzo esteso è l'unico importo per cui ci saranno distribuzioni. Pertanto, l'utente non avrà bisogno di un altro campo per determinare il tipo di importo per cui è la distribuzione. Tuttavia, nello scenario successivo, queste informazioni **verranno** utilizzate, poiché i requisiti di quello scenario specificano che altri tipi di importo hanno distribuzioni, ad esempio IVA.

8.  Fare clic su **Fine** per uscire dalla modalità di modifica.

9.  Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro

10. Fare clic su **Pubblica area di lavoro** per salvare il lavoro.

#### <a name="adding-navigation-to-view-accounting-page"></a>Aggiunto lo spostamento alla pagina "Visualizza contabilità"

La pagina in versione mobile **Visualizza contabilità** non è attualmente collegata a nessuna delle pagine mobili disponibili progettate fino a questo momento. Poiché l'utente deve poter accedere alla pagina **Visualizza contabilità** dalla pagina **Dettagli fattura** sul dispositivo mobile, dobbiamo specificare lo spostamento dalla pagina **Dettagli fattura** alla pagina **Visualizza contabilità** . Stabiliamo questo spostamento utilizzando la logica aggiuntiva tramite JavaScript.

1.  Apre il file .js creato in precedenza e aggiungere le righe che vengono evidenziate nel codice riportato di seguito. Questo codice fa due cose:
    1.  Aiuta a garantire che gli utenti non possono accedere direttamente dall'area di lavoro alla pagina **Visualizza contabilità**.
    2.  Stabilisce un controllo di spostamento dalla pagina **Invoice details** alla pagina **View accounting**.

    > [!NOTE] 
    > Il nome delle pagine e altri controlli nel codice devono essere gli stessi dell'area di lavoro.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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
    ```
    
2.  Caricare il file del codice nell'area di lavoro selezionando la scheda **Logica** per sovrascrivere il codice precedente
3.  Fare clic su **Fine** per uscire dalla modalità di modifica.
4.  Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro
5.  Fare clic su **Pubblica area di lavoro** per salvare il lavoro.

### <a name="validation"></a>Convalida

Dal dispositivo mobile, aprire l'app e connettersi all'istanza. Verificare di accedere alla società in cui le fatture fornitore sono assegnate a se stessi per la revisione. Dovrebbe esssere possibile eseguire le seguenti azioni:

-   Vedere l'area di lavoro **My approvals**.
-   Analizzare l'area di lavoro **My approvals** e vedere la pagina **My vendor invoices**.
-   Analizzare la pagina **My vendor invoices** e visualizzare l'elenco delle fatture assegnate all'utente.
-   Analizzare una delle fatture e visualizzare i dettagli dell'intestazione della fattura e delle righe.
-   Nella pagina dei dettagli, vedere un collegamento agli allegati e utilizzare questo collegamento per spostarsi all'elenco degli allegati e visualizzare gli allegati.
-   Nella pagina dei dettagli, vedere un collegamento alla pagina **Visualizza contabilità** e utilizzare questo collegamento per spostarsi alla pagina delle distribuzioni e visualizzare le distribuzioni.
-   Nella pagina dei dettagli, fare clic sul menu **Azioni** nella parte inferiore ed eseguire le azioni del flusso di lavoro applicabili al passaggio del flusso di lavoro.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Progettazione di uno scenario complesso di approvazione fatture per Fabrikam
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
<td>Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</td>
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
<td>Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</td>
<td><ol>
<li>Categoria di approvvigionamento</li>
<li>Quantità</li>
<li>Prezzo unitario</li>
<li>Importo netto riga</li>
<li>Importo 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quante righe fattura sono presenti in una fattura? Applicare la regola 80-20 qui e ottimizzare per l'80%.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</td>
<td>Sì</td>
</tr>
<tr class="odd">
<td>Quante distribuzioni contabili (prezzo esteso, IVA, spese e così via) esistono per una riga della fattura? Anche in questo caso, applicare la regola 80-20.</td>
<td>Prezzo esteso: 2 IVA: 2 Spese: 2</td>
</tr>
<tr class="even">
<td>Le fatture hanno distribuzioni contabili anche nell'intestazione? In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</td>
<td>Non utilizzato</td>
</tr>
<tr class="odd">
<td>Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</td>
<td>Sì</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>Passaggi successivi

Le variazioni seguenti possono essere effettuate per lo scenario 1, in base ai requisiti dello scenario 2. È possibile utilizzare questa sezione migliorare l'esperienza con l'app mobile.

1.  Poiché più righe fattura sono previste nello scenario 2, le seguenti modifiche alla progettazione aiuteranno a ottimizzare l'esperienza utente sul dispositivo mobile:
    1.  Anziché visualizzare le righe fattura nella pagina dei dettagli (come nello scenario 1), gli utenti possono scegliere di visualizzare le righe in una pagina in versione mobile separata.
    2.  Poiché più righe fattura sono previste in questo scenario, se la pagina **VendMobileInvoiceAllDistributionTree** viene utilizzata per progettare la pagina delle distribuzioni per l'ambiente mobile (come nello scenario 1), potrebbe confondere l'utente correlare le righe alle distribuzioni. Di conseguenza, utilizzare la pagina **VendMobileInvoiceLineDistributionTree** per progettare la pagina delle distribuzioni.
    3.  A livello ideale, le distribuzioni devono essere visualizzate nel contesto di una riga della fattura in questo scenario. Di conseguenza, assicurarsi che l'utente possa eseguire il drill-down in una riga per visualizzare la pagina delle distribuzioni. Utilizzare la funzionalità di collegamento pagina per stabilire il drill-through, esattamente come fatto per l'intestazione e le pagine dei dettagli nello scenario 1.

2.  Poiché sono previsti più tipi di importo nelle distribuzioni nello scenario 2 (IVA, spese e così via), sarà utile visualizzare la descrizione del tipo di importo. (Abbiamo omesso queste informazioni nello scenario 1).






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
