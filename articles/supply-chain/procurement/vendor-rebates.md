---
title: Sconti fornitore
description: "Questo argomento fornisce una panoramica della maggior parte delle attività comuni che si potrebbero eseguire quando si utilizzano gli sconti fornitore. Gli sconti fornitore consentono alle società di gestire meglio i relativi programmi sconti fornitore automatizzando le attività necessarie per amministrare, tenere traccia e riscuotere gli sconti ottenuti."
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, Unified operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 477c1648ce700592677adfd8bfc8701c27fbab6f
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="vendor-rebates"></a>Sconti fornitore
[!include[banner](../includes/banner.md)]

Gli sconti fornitore consentono alle società di gestire meglio i relativi programmi sconti fornitore automatizzando le attività necessarie per amministrare, tenere traccia e riscuotere gli sconti ottenuti.

Questo argomento fornisce una panoramica della maggior parte delle attività comuni che si potrebbero eseguire quando si utilizzano gli sconti fornitore. La panoramica descrive le seguenti attività:

- Esaminare i dettagli di un accordo sugli sconti.
- Identificare gli ordini che beneficiano degli sconti e generare attestazioni di sconto.
- Esaminare ed approvare le attestazioni.

## <a name="audience-and-purpose"></a>Destinatari e scopo

Le informazioni contenute in questo argomento sono destinate ai decisori aziendali, ad esempio responsabili degli acquisti, responsabili finanziari e direttori amministrativi con le seguenti responsabilità:

- Negoziare accordi su prezzi, riduzioni e sconti fornitore.
- Gestire il personale che elabora le attestazioni di sconto e riscuote i pagamenti.
- Ordinare le scorte ai prezzi migliori.

Le persone che svolgono queste mansioni sono alla ricerca di metodi per conseguire vari obiettivi. Di seguito sono riportati alcuni esempi.

- Integrare in modo flessibile differenti tipi di programmi di promozione fornitore e condizioni di sconto.
- Ridurre il carico e gli errori amministrativi associati al monitoraggio delle prestazioni promozionali e all'elaborazione delle attestazioni.
- Migliorare le previsioni di cassa accumulando effetti attivi futuri.
- Disporre di una base quantificata per le negoziazioni correnti e future con i fornitori sugli sconti.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>Esaminare i dettagli di un accordo sugli sconti fornitore
Un accordo sugli sconti fornitore è un record di un contratto con un fornitore che specifica i termini e le condizioni negoziati in base ai quali la società ha diritto a un premio monetario in cambio del raggiungimento di obiettivi d'acquisto prestabiliti. Gli accordi sugli sconti fornitore sono registrati nella pagina **Accordi sugli sconti**.

Per aprire la pagina **Accordi sconto fornitore**, selezionare **Approvvigionamento** &gt; **Sconti fornitore** &gt; **Accordi sugli sconti**.

![Contratto di acquisto](media/purchase-agreement.PNG)

Nella pagina **Accordi sconto fornitore**, è possibile visualizzare dettagli relativi alle condizioni negoziate di un contratto fornitore.

L'intestazione del contratto specifica le condizioni generali secondo cui una società ha diritto agli sconti. In pratica, le informazioni nell'intestazione indicano che un fornitore concede uno sconto quando uno specifico prodotto viene acquistato in una specifica quantità. Nell'intestazione, è necessario specificare anche i campi Opzione sconto unità di misura e Tipo data di calcolo.

- Nella scheda **Generale**, nel campo **Opzione sconto unità di misura**, è possibile definire se un'unità di misura deve essere una condizione per stabilire se uno sconto è applicabile alla riga dell'ordine fornitore. 

    - **Converti**: uno sconto fornitore è applicabile a una riga dell'ordine fornitore secondo l'accordo sugli sconti. Si otterrà uno sconto indipendentemente dall'unità di misura applicata alla riga.
    - **Corrispondenza esatta**: per beneficiare di uno sconto, una riga acquisto deve avere la stessa unità di misura specificata nell'accordo.

- Nella scheda **Generale**, nel campo **Tipo data di calcolo**, selezionare la data utilizzata per determinare se l'acquisto rientra nel periodo di validità dell'accordo sugli sconti.

    - **Creato**: utilizzare la data di creazione dell'ordine fornitore.
    - **Consegna richiesta**: utilizzare la data di consegna richiesta.

Nelle righe del contratto, è possibile specificare l'accordo sugli sconti fornitore più in dettaglio.

- Nel campo **Accumula acquisti per**, è possibile impostare il calcolo dell'attestazione di sconto. L'importo può essere impostato in relazione a un periodo di tempo (settimana, mese, anno, durata o periodo personalizzato). Il valore **Fattura** indica che un'attestazione di sconto verrà determinata ogni volta che una riga dell'ordine fornitore viene fatturata.
- Nel campo **Origine**, è possibile specificare la base per il calcolo dello sconto.

    - **Lordo**: lo sconto viene calcolato in base al prezzo lordo dell'articolo.
    - **Netto**: lo sconto viene calcolato in base al prezzo netto dell'articolo (il prezzo dopo aver applicato altri sconti).

- I campi **Conto ratei programma sconti** e **Conto spese programma sconti predefinito** specificano i numeri di conto che riceveranno gli importi degli sconti accumulati durante la fase intermedia tra l'approvazione e l'elaborazione.
- Quando l'opzione **Approvazione richiesta** è impostata su **Sì**, l'attestazione di sconto deve essere approvata prima di essere accumulata o pagata.
- Il campo **Tipo di interruzione riga sconto** specifica la base per gli sconti.

    - **Quantità**: gli sconti sono basati sul volume.
    - **Importo**: gli sconti sono basati sull'importo.

- Nella scheda dettaglio **Righe**, è possibile osservare quanti livelli quantità possono essere impostati per vari sconti. Ad esempio, nell'illustrazione precedente, i campi **Dal valore** e **Al valore** indicano che per una quantità di prodotto compresa tra 10 e 19 unità viene concesso uno sconto di USD 15 per unità.

    > [!NOTE]
    > Il valore di **Dal valore** è incluso, mentre il valore **Al valore** non lo è. Ad esempio, il campo **Tipo di interruzione riga sconto** è impostato su **Quantità** e si immette **1** nel campo **Dal valore** e **3** nel campo **Al valore**. In questo caso, l'importo dello sconto viene applicato quando si acquistano uno o due articoli, ma non quando si acquistano tre articoli.

- Nel campo **Stato di approvazione flusso di lavoro**, il valore **Approvato** indica che l'accordo può essere applicato agli ordini fornitore che soddisfano le condizioni dell'accordo.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>Identificare gli ordini a cui si applicano gli sconti e generare attestazioni di sconto

Quando gli ordini fornitore vengono piazzati con un fornitore con il quale la società ha un accordo sugli sconti, il programma identifica eventuali pagamenti a credito futuri del fornitore. Se gli ordini fornitore beneficiano di uno sconto, un'attestazione di sconto viene generata per ogni riga dell'ordine non appena una fattura di acquisto viene registrata. Questo processo è automatico. Successivamente, è possibile esaminare gli sconti previsti e verificare l'impatto degli stessi sul costo e il margine di profitto del prodotto.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>Visualizzare i dettagli degli sconti applicati a una riga dell'ordine fornitore in base all'accordo sugli sconti fornitore
1. Nella pagina **Ordine fornitore**, selezionare una riga dell'ordine e selezionare **Riga ordine fornitore** &gt; **Visualizza** &gt; **Dettagli prezzi**.
2. Nella pagina **Dettagli prezzo**, selezionare la scheda dettaglio **Sconti**.

Le informazioni sugli sconti sono visualizzate anche nel campo **Sconto fornitori** nella sezione **Stima margine** della pagina **Dettagli prezzo**.

> [!NOTE]
> Nella pagina **Parametri di approvvigionamento**, nella scheda **Prezzi**, verificare che l'opzione **Attivare dettagli prezzo** è impostata su **Sì**. Se è impostata su **No**, non sarà possibile visualizzare gli sconti.

## <a name="review-and-approve-claims"></a>Esaminare ed approvare le attestazioni
Le attastazioni di sconto generate rappresentano i pagamenti futuri previsti da parte del fornitore. Prima di emettere una nota di accredito al fornitore, il titolare dell'accordo in genere desidera esaminare le attestazioni e approvarle. È tuttavia necessario notare che lo stato di un'attestazione determina se la stessa può essere sottoposta al processo di approvazione.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>Stato delle attestazioni ed effetto sul processo di approvazione
Quando un'attestazione viene generata, il relativo stato è impostato su **Da calcolare** se lo sconto viene concesso su base cumulativa o **Calcolato** se lo sconto viene concesso per fattura. Se lo stato di un'attestazione è **Da calcolare**, l'attestazione deve essere sottoposta a un processo di calcolo che viene gestito mediante la funzione Cumula. Solo le attestazioni con stato **Calcolato** possono essere incluse nel processo di approvazione.

> [!NOTE]
> Se l'opzione **Approvazione richiesta** in un accordo sugli sconti fornitore è impostata su **No**, tutte le attestazioni generate avranno lo stato **Approvato**. L'approvazione è obbligatoria per le attestazioni concesse su base cumulativa.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>Approvare le attestazioni e visualizzare registrazioni e dettagli delle fatture
Le assegnazioni approvate possono essere elaborate dalla contabilità fornitori. Un nota di credito (fattura fornitore) per l'importo dell'attestazione di sconto viene generata automaticamente. Il credito può quindi essere aggiunto al saldo fornitore e il team di contabilità fornitori può includerlo nel normale processo di liquidazione.

1. Selezionare &gt; **Approvvigionamento** **Sconti fornitore** &gt; **Attestazioni sconto** per aprire un'attestazione di sconto.
2. Chiudere l'attestazione di sconto.
3. Contrassegnare l'attestazione e nel riquadro azioni selezionare **Approva**.
4. Nella pagina di richiesta, nel campo **Fornitore**, selezionare il fornitore da cui si è autorizzati a ricevere uno sconto e selezionare **OK**.

    Un giornale di registrazione ratei sconto viene registrato per l'importo dell'attestazione. Questa registrazione addebita il conto degli sconti fornitore accumulati da ricevere del credito fornitore previsto e accredita il conto degli sconti fornitore accumulati ricevuti temporaneo dell'importo dell'attestazione.

    ![Messaggio](media/message.png)

5. Nell'elenco degli sconti, selezionare la riga, quindi nel riquadro azioni, selezionare **Transazioni di sconto** per visualizzare e passare al numero batch del giornale di registrazione per questa registrazione dei ratei sconto.

    Per includere le attestazioni nel processo di contabilità fornitori, l'addetto alla contabilità fornitori deve ora completare la gestione delle attestazioni di sconto eseguendo la funzione Elabora.

6. Nel riquadro azioni selezionare **Elabora**, quindi selezionare **Filtro**. Nel campo **Criteri** per il campo **Account fornitore**, selezionare il fornitore per cui elaborare le attestazioni di sconto, selezionare altri filtri pertinenti e selezionare **OK**.

    La barra dei messaggi e lo stato **Completato** indicano che si sono verificati i seguenti eventi:

    - Una registrazione del giornale di registrazione ratei sconto ha stornato gli importi provvisori precedenti sul conto ratei e sul conto spese.
    - È stata creata una fattura fornitore (nota di accredito) per l'importo dello sconto.

        > [!NOTE]
        > L'impostazione dell'opzione **Registrazione fattura manuale** nella scheda **Programma sconti** della pagina **Parametri di approvvigionamento** determina se una fattura fornitore viene registrata manualmente o automaticamente come parte dell'elaborazione delle attestazioni.

    - Quando la fattura fornitore viene registrata, automaticamente o manualmente, il conto debito del fornitore viene addebitato e il conto sconti e indennità ricevuti viene accreditato.

        > [!NOTE] 
        > Il numero del conto sconti e indennità ricevuti viene specificato per la categoria di approvvigionamento utilizzata nella riga della fattura di acquisto per lo sconto. La categoria di approvvigionamento viene impostata nella scheda **Programma sconti** della pagina **Parametri di approvvigionamento**.

7. Nell'elenco degli sconti, selezionare la riga, quindi nel riquadro azioni, selezionare **Transazioni di sconto** per visualizzare il numero batch del giornale di registrazione per la registrazione dei ratei sconto e il numero di fattura fornitore.
8. Selezionare la riga per la transazione della fattura fornitore, quindi nel riquadro azioni, selezionare **Fattura fornitore**. Se la fattura fornitore è stata registrata, viene visualizzato il giornale di registrazione fatture. In caso contrario, viene visualizzata la fattura fornitore come fattura fornitore in sospeso che richiede la registrazione manuale.

    La riga fattura specifica i dettagli della fattura fornitore per la categoria di approvvigionamento **Addebiti e sconti**.

9. Nella pagina **Tutti i fornitori**, selezionare il fornitore da cui si riceve uno sconto, quindi nel riquadro azioni selezionare **Transazioni**. Trovare la riga per la fattura. L'importo dello sconto viene ora aggiunto al saldo fornitore.

## <a name="summary"></a>Riepilogo
Il processo di gestione degli sconti fornitore include molteplici attività di tracciabilità manuali che risultano spesso noiose. Automatizzando queste attività, la funzionalità di gestione degli sconti fornitore può consentire l'esecuzione dei seguenti processi:

- Generazione di attestazioni di sconto accurate
- Accumulo di guadagni provvisori e crediti previsti nella contabilità generale
- Aggiornamento del saldo fornitore e del conto economico con lo sconto dovuto

