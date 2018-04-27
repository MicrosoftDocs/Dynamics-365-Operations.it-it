---
title: Previsione di cassa
description: "In questo argomento viene fornita una panoramica del processo di previsione di cassa. E viene illustrato come la previsione di cassa è integrata con altri moduli nel sistema."
author: saraschi2
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 9aefc79897d0abcee14c05f33516181b3eb05e55
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---

# <a name="cash-flow-forecasting"></a>Previsione di cassa

[!INCLUDE [banner](../includes/banner.md)]

È possibile utilizzare gli strumenti di previsione di cassa per analizzare il calcolo delle previsioni di cassa e dei fabbisogni valutari per stimare l'esigenza di contanti futura della società. Per ottenere una previsione del flusso di cassa, procedere come segue:

- identificare ed elencare tutti i conti liquidità. I conti liquidità sono i conti della società in contanti o equivalenti.
- Configurare il comportamento delle previsioni relative alle transazioni che influiscono sui conti liquidità della società.

Dopo aver completato queste attività, è possibile calcolare e analizzare le previsioni di cassa e dei fabbisogni valutari futuri.

## <a name="cash-flow-forecasting-integration"></a>Integrazione della previsione di cassa

È possibile integrare la previsione di cassa con Contabilità generale, Contabilità fornitori, Contabilità clienti, Impostazione budget e Gestione articoli. Il processo di previsione utilizza le informazioni delle transazioni immesse nel sistema e il processo di calcolo prevede l'impatto di cassa previsto per ciascuna transazione. Di seguito sono elencati i tipi di transazione considerati quando viene calcolato il flusso di cassa:

- **Ordini cliente** – Ordini cliente non ancora fatturati che determinano vendite fisiche o finanziarie.
- **Ordini fornitore** – Ordini fornitore non ancora fatturati che determinano acquisti fisici o finanziari.
- **Contabilità clienti** – Transazioni cliente aperte (fatture non ancora pagate).
- **Contabilità fornitori** – Transazioni fornitore aperte (fatture non ancora pagate).
- **Transazioni contabili** – Transazioni in cui è specificato che verrà eseguita una registrazione futura.
- **Voci del registro di budget** - Voci del registro di budget selezionate per le previsioni di cassa.
- **Previsioni della domanda** - Righe del modello previsionale di magazzino selezionate per le previsioni di cassa.
- **Previsioni dell'offerta** - Righe del modello previsionale di magazzino selezionate per le previsioni di cassa.

Sebbene non vi sia un'integrazione diretta con Gestione progetti e contabilità, esistono diversi modi per includere le transazioni di progetto nella previsione di cassa. Le fatture di progetto registrate vengono incluse nella previsione nell'ambito delle transazioni fornitore aperte. Gli ordini cliente e fornitore attivati da progetto vengono inclusi nella previsione come ordini aperti una volta immessi nel sistema. È inoltre possibile trasferire le previsioni di progetto a un modello di budget contabile. Questo modello di budget contabile quindi viene incluso nella previsione di cassa come parte delle voci del registro di budget.

## <a name="configuration"></a>Configurazione

Per configurare il processo di previsione di cassa, usare la pagina **Impostazione di previsione di cassa**. In questa pagina, specificare i conti liquidità da tracciare e i comportamenti di previsione predefiniti per ciascuna area.

### <a name="general-ledger"></a>Contabilità generale

Definire per prima cosa i conti liquidità da tracciare con le previsioni di cassa. In genere, i conti liquidità sono conti principali associati ai conti bancari che riceveranno e sborseranno contanti. Nella pagina **Impostazione di previsione di cassa**, nella scheda **Contabilità generale**, selezionare i conti principali da includere nelle previsioni. Se un conto bancario è stato associato al conto principale nella pagina **Conto bancario**, viene indicato nel campo **Conto bancario**.

È possibile impostare una previsione di cassa dipendente per un conto principale contenente le transazioni direttamente correlate alle transazioni contenute in un altro conto principale. Ogni riga aggiunta nella sezione **Conti dipendenti** crea un importo di previsione di cassa in un conto principale dipendente. Questo importo corrisponde a una percentuale degli importi del flusso di cassa del conto principale primario selezionato.

Innanzitutto, impostare il campo **Conto principale** sul conto principale primario in cui si prevede si verifichino inizialmente le transazioni. Impostare il campo **Conto principale dipendente** sul conto interessato dalla transazione iniziale del conto principale primario. Impostare i valori appropriati negli altri campi della riga. È possibile modificare il valore visualizzato nel campo **Percentuale** in modo che corrisponda all'effetto prodotto dal conto principale primario sul conto principale dipendente. Per una previsione di vendita o di acquisto, selezionare per **Termini di pagamento** un valore tipico della maggior parte dei clienti o dei fornitori. Impostare il campo **Tipo di registrazione** sul tipo di registrazione previsto correlato alla previsione di cassa.

### <a name="accounts-payable"></a>Contabilità fornitori

È possibile calcolare la previsione per gli acquisti utilizzando le opzioni di impostazione della scheda **Contabilità fornitori** nella pagina **Impostazione di previsione di cassa**. Prima di poter configurare le previsioni di cassa per la contabilità fornitori, è necessario configurare i termini di pagamento, i gruppi di fornitori e i profili di registrazione fornitori.

Nella sezione **Valori predefiniti previsione di acquisto**, è possibile selezionare i comportamenti di acquisto standard per le previsioni di cassa. Tre campi determinano il periodo dell'impatto di cassa: **Tempo tra la data di consegna e la data fattura**, **Termini di pagamento** e **Tempo tra la data di scadenza della fattura e la data di pagamento**. La previsione utilizza l'impostazione predefinita per il campo **Termini di pagamento** solo se non è specificato un valore per la transazione. Utilizzare un termine di pagamento per descrivere il numero di giorni tipico per ogni passaggio del processo.

Nel campo **Conto liquidità per i pagamenti** è specificato il conto liquidità utilizzato in genere per i pagamenti. Utilizzare il campo **Percentuale di importo da allocare alla previsione di cassa** per indicare se una percentuale degli importi deve essere utilizzata nelle previsioni. Lasciare vuoto questo campo se gli importi delle transazione complete vengono utilizzati nelle previsioni.

È possibile sostituire l'impostazione predefinita del campo **Tempo tra la data di scadenza della fattura e la data di pagamento** per i gruppi di fornitori specifici. La previsione utilizza il valore predefinito della sezione **Valori predefiniti previsione di acquisto** a meno che non sia stato specificato un valore diverso per il gruppo di fornitori correlato al fornitore nella transazione. Per sostituire il valore predefinito, selezionare un gruppo di fornitori e quindi impostare il nuovo valore del campo **Ora dell'acquisto**.

È possibile sostituire l'impostazione predefinita del campo **Conto liquidità** per i profili di registrazione di fornitori specifici. La previsione utilizza il valore predefinito della sezione **Valori predefiniti previsione di acquisto** a meno che non sia stato specificato un conto liquidità diverso per il profilo di registrazione correlato al fornitore nella transazione. Per sostituire il valore predefinito, selezionare un profilo di registrazione e specificare il conto liquidità che si prevede interessato.

### <a name="accounts-receivable"></a>Contabilità clienti

È possibile calcolare la previsione per le vendite utilizzando le opzioni di impostazione della scheda **Contabilità clienti** nella pagina **Impostazione di previsione di cassa**. Prima di poter configurare le previsioni di cassa per la contabilità clienti, è necessario configurare i termini di pagamento, i gruppi di clienti e i profili di registrazione clienti.

Nella sezione **Valori predefiniti previsione di vendita**, è possibile selezionare i comportamenti di vendita standard per le previsioni di cassa. Tre campi determinano il periodo dell'impatto di cassa: **Tempo tra la data di spedizione e la data fattura**, **Termini di pagamento** e **Tempo tra la data di scadenza della fattura e la data di pagamento**. La previsione utilizza l'impostazione predefinita per il campo **Termini di pagamento** solo se non è specificato un valore per la transazione. Utilizzare un termine di pagamento per descrivere il numero di giorni tipico per ogni passaggio del processo. 

Nel campo **Conto liquidità per i pagamenti** è specificato il conto liquidità utilizzato in genere per i pagamenti. Utilizzare il campo **Percentuale di importo da allocare alla previsione di cassa** per indicare se una percentuale degli importi deve essere utilizzata nelle previsioni. Lasciare vuoto questo campo se gli importi delle transazione complete vengono utilizzati nelle previsioni.

È possibile sostituire l'impostazione predefinita del campo **Tempo tra la data di scadenza della fattura e la data di pagamento** per i gruppi di clienti specifici. La previsione utilizza il valore predefinito della sezione **Valori predefiniti previsione di vendita** a meno che non sia stato specificato un valore diverso per il gruppo di clienti correlato al cliente nella transazione. Per sostituire il valore predefinito, selezionare un gruppo di clienti e quindi impostare il nuovo valore del campo **Ora della vendita**.

È possibile sostituire l'impostazione predefinita del campo **Conto liquidità** per i profili di registrazione di clienti specifici. La previsione utilizza il valore predefinito della sezione **Valori predefiniti previsione di vendita** a meno che non sia stato specificato un conto liquidità diverso per il profilo di registrazione correlato al cliente nella transazione. Per sostituire il valore predefinito, selezionare un profilo di registrazione e impostare il conto liquidità che si prevede interessato.

### <a name="budgeting"></a>Impostazione budget

È possibile includere i budget creati dai modelli di budget nelle previsioni di cassa. Nella scheda **Impostazione budget** della pagina **Impostazione previsione di cassa**, selezionare i modelli di budget da includere nella previsione. Per impostazione predefinita, le nuove voci del registro di budget vengono incluse nella previsione dopo che il modello di budget è stato attivato per le previsioni di cassa. L'inclusione nella previsione di cassa può essere sovrascritta nelle singole voci del registro di budget.

### <a name="inventory-management"></a>Gestione inventario

Le previsioni di offerta e domanda di magazzino possono essere incluse nella previsione di cassa. Nella scheda **Gestione inventario** della pagina **Impostazione previsione di cassa**, selezionare il modello di previsione da includere nella previsione di cassa. L'inclusione nella previsione di cassa può essere sovrascritta nelle singole righe della previsione della domanda e dell'offerta.

### <a name="calculation"></a>Calcolo

Per poter visualizzare l'analisi dei dati di una previsione di cassa, è necessario eseguire il processo di calcolo del flusso di cassa. Il processo di calcolo proietta gli impatti di cassa futuri delle transazioni che sono state immesse.

Calcolare la previsione di cassa utilizzando la pagina **Calcola previsioni di cassa**. È possibile calcolare la previsione di cassa completa o una previsione di cassa incrementale. 

- Per cancellare tutte le transazioni di previsione di cassa e ricalcolare, impostare il campo **Metodo di calcolo delle previsioni di cassa** su **Totale**. È consigliabile utilizzare questo metodo se per lungo tempo non sono state aggiornate le previsioni di cassa. 
- Per aggiornare le informazioni del flusso di cassa solo per le nuove transazioni, impostare il campo **Metodo di calcolo delle previsioni di cassa** su **Nuovo**. Nella pagina viene visualizzata la data in cui è stato eseguito l'ultimo calcolo del flusso di cassa.

È inoltre possibile utilizzare l'elaborazione batch per le previsioni di cassa. Per contribuire a garantire che l'analisi dei dati di previsione sia aggiornata regolarmente, impostare un processo batch ricorrente per il calcolo delle previsioni di cassa.

### <a name="reporting"></a>Report

Dopo che la previsione di cassa viene calcolata, è necessario aggiornare le informazioni di entità associate per il reporting analitico. Nella pagina **Archivio entità**, selezionare la misura di aggregazione **LedgerCovLiquidityMeasurement** e fare clic su **Aggiorna**.

Sono disponibili due aree di lavoro contenenti i dati di previsione di cassa. Un'area di lavoro contiene i dati per tutte le società e l'altra area di lavoro contiene solo i dati per la società corrente.

L'accesso all'area di lavoro per tutte le società viene controllato attraverso il diritto **Visualizza area di lavoro delle previsioni di cassa per tutte le società**. Per impostazione predefinita, l'area di lavoro **Panoramica situazione di cassa - tutte le società** è disponibile per i ruoli seguenti:

- Amministratore delegato
- Responsabile finanziario
- Supervisore finanziario

L'accesso all'area di lavoro per la società corrente viene controllato attraverso il diritto **Visualizza area di lavoro società corrente per il flusso di cassa**. Per impostazione predefinita, l'area di lavoro **Panoramica situazione di cassa - società corrente** è disponibile per i ruoli seguenti:

- Ragioniere
- Direttore amministrativo
- Supervisore contabile
- Responsabile contabilità fornitori
- Responsabile contabilità clienti

L'area di lavoro **Panoramica situazione di cassa - tutte le società** mostra l'analisi dei dati di previsione di cassa nella valuta di sistema. La valuta di sistema e il tipo di tasso di cambio del sistema utilizzati per l'analisi sono definiti nella pagina **Paramenti di sistema**. Questa area di lavoro visualizza una panoramica dei saldi del conto bancario e delle previsioni di cassa per tutte le società. Un grafico delle entrate e delle uscite di cassa fornisce una panoramica dei saldi e dei movimenti di cassa futuri nella valuta di sistema, insieme a informazioni dettagliate sulle transazioni previsionali. È inoltre possibile vedere i saldi previsti in valuta.

L'area di lavoro **Panoramica situazione di cassa - società corrente** mostra l'analisi di previsione di cassa nella valuta di contabilizzazione definita della società. La valuta di contabilizzazione utilizzata per l'analisi è definita nella pagina **Contabilità generale**. Questa area di lavoro visualizza una panoramica dei saldi del conto bancario e delle previsioni di cassa per la società corrente. Un grafico delle entrate e delle uscite di cassa fornisce una panoramica dei saldi e dei movimenti di cassa futuri nella valuta di contabilizzazione, insieme a informazioni dettagliate sulle transazioni previsionali. È inoltre possibile vedere i saldi previsti in valuta.

Per ulteriori informazioni sull'analisi di previsione di cassa, vedere l'argomento del contenuto di Power BI della panoramica situazione di cassa.

Inoltre, è possibile visualizzare i dati di previsione di cassa per conti, ordini e articoli specifici nelle pagine seguenti:

- **Bilancio di verifica**: Selezionare **Previsioni di cassa** per visualizzare i flussi di cassa futuri per il conto principale selezionato.
- **Tutti gli ordini cliente**: Nella scheda **Fattura**, selezionare **Previsioni di cassa** per visualizzare l'impatto di cassa previsto dell'ordine cliente selezionato.
- **Tutti gli ordini fornitore**: Nella scheda **Fattura**, selezionare **Previsioni di cassa** per visualizzare l'impatto di cassa previsto dell'ordine fornitore selezionato.
- **Previsione dell'offerta**: Selezionare **Previsioni di cassa** per visualizzare i flussi di cassa futuri associati alla previsione dell'offerta dell'articolo selezionata.
- **Previsione della domanda**: Selezionare **Previsioni di cassa** per visualizzare i flussi di cassa futuri associati alla previsione della domanda dell'articolo selezionata.


