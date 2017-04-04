---
title: Modelli di pianificazione del budget per Excel
description: In questo argomento viene descritto come creare modelli di Microsoft Excel che possono essere utilizzati con i piani di budget.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 0e2eb6e7c130f03edbf60a185d397d94b5d61d7d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-templates-for-excel"></a>Modelli di pianificazione del budget per Excel

In questo argomento viene descritto come creare modelli di Microsoft Excel che possono essere utilizzati con i piani di budget.

In questo argomento viene illustrato come creare modelli di Excel che verranno utilizzati con i piani di budget utilizzando il set di dati dimostrativi standard e di accesso utente di Admin. Per ulteriori informazioni sulla pianificazione del budget, vedere [panoramica di pianificazione del budget. budget-planning-overview-configuration.md] () È inoltre possibile monitorare [budget che prevede 101] esercitazione (budget-plan.md) per ottenere i principi di configurazione e del modulo di base.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Generare un foglio di lavoro utilizzando il layout di documento piano di budget
I documenti del piano di budget possono essere visualizzati e modificati utilizzando uno o più layout. Ogni layout può essere collegato un modello di documento piano di budget per visualizzare e modificare i dati del piano di un foglio di calcolo di Excel. In questo argomento, un modello di documento piano di budget verrà generato utilizzando una configurazione esistente del layout. Aprire ** i piani di budget in ** (** crearlo **&gt; ** piani di budget **). Fare clic su ** nuovo ** per creare un nuovo documento piano di budget. ![[] (bpt1. /media/bpt11-1024x552.png)](. /media/bpt11.png) 

** Usano aggiunti ** l'opzione riga per aggiungere le righe. Fare clic su ** layout ** per visualizzare la configurazione del layout di documento piano di budget. 
![[] (bpt2. /media/bpt2-1024x274.png)](. /media/bpt2.png) 

È possibile verificare la configurazione del layout e regolarlo come necessaria. Passare ** ** &gt; ** modello generano ** creare un file di Excel per il layout. Dopo che il modello viene generato, spostarsi ** modello ** &gt; ** la visualizzazione ** aprire e verificare il modello di documento piano di budget. È possibile salvare il file di Excel all'unità locale. ![[] (bpt3. /media/bpt3-1024x545.png)](. /media/bpt3.png) 

> [!NOTE] 
> Il layout di documento piano di budget non può essere modificato dopo l'immissione di un modello Excel è associato. Per modificare il layout, eliminare il modello di file di Excel collegato e rigenerilo. Questa operazione è necessaria per contenere i campi e nel layout del foglio di lavoro sincronizzati. 

Il modello Excel contiene tutti gli elementi dal layout di documento piano di budget, in cui ** disponibile nel foglio di lavoro ** la colonna è impostata su True. Elementi di sovrapposizione non sono attivati nel modello Excel. Ad esempio, se il layout sono incluse colonne di richiesta, Q1 di richiesta, Q2 di richiesta Q3 e richieste Q4 e una colonna totale di richiesta che rappresenta una somma di tutte le 4 colonne trimestrali, verranno visualizzate solo le colonne trimestrali o colonna totale è disponibile da utilizzare nel modello Excel. Il file di Excel non può aggiornare le colonne di sovrapposizione durante l'aggiornamento dei dati della tabella possono diventare superati e inesatti.

![[] (bpt4. /media/bpt4-1024x615.png)](. /media/bpt4.png)

> [!NOTE] 
> Per evitare le uscite potenziali alla visualizzazione e modificare i dati del piano di budget utilizzando Excel, lo stesso utente deve essere registrato in Dynamics 365 per le operazioni che il Connector di dati Componente di Office di Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Aggiungere un'intestazione al modello di documento piano di budget
Per aggiungere informazioni di intestazione, selezionare la riga superiore nel file di Excel e inserire le righe vuote. Fare clic su ** progettazione ** in ** Connector di dati ** per aggiungere i campi di intestazione a Excel file.

![[] (bpt5. /media/bpt5-1024x615.png)](. /media/bpt5.png) 

** Progettazione ** nella scheda, ** ** fare clic su ** aggiungere ** campi quindi selezionare BudgetPlanHeader ** ** come origine dei dati dell'entità.

![[] (bpt6. /media/bpt6-1024x615.png)](. /media/bpt6.png)

Indicano il cursore quella desiderata nel file di Excel. ** Fare clic su Aggiungi etichetta ** per aggiungere l'etichetta del campo nell'ubicazione selezionata. Selezionare ** aggiungere il valore ** aggiungere il campo relativo al valore selezionato nella posizione. Fare clic su ** effettuato ** per chiudere la finestra di progettazione.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>![[] (bpt7. /media/bpt7.png)](. /media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Aggiungono una colonna calcolata nella tabella del modello di documento piano di budget
--------------------------------------------------------------

A questo punto, le colonne calcolate verranno aggiunti al modello generato del documento piano di budget. ** La richiesta totale ** colonna, in cui sono riepilogati la richiesta Q1: Richiedere le colonne Q4 e ** rettifica ** una colonna, che ricalcola ** totale richiesta ** la colonna da un fattore predefinito.

Fare clic su ** progettazione ** in ** Connector di dati ** per aggiungere colonne alla tabella. Fare clic su ** modifica ** ** accanto alla BudgetPlanWorksheet ** origine dati da avviare aggiungere alle colonne.

![[] (bpt8. /media/bpt8-1024x301.png)](. /media/bpt8.png) 

Il gruppo di campi nelle colonne disponibili nel modello. Fare clic su ** formula ** per aggiungere una nuova colonna. Assegnare un nome alla nuova colonna quindi immettere la formula ** formula ** nel campo. Fare clic su ** aggiornamento ** per inserire la colonna.

![[] (bpt12. /media/bpt12-1024x565.png)](. /media/bpt12.png)

> [!NOTE] 
> Per definire la formula, creare la formula del foglio di lavoro quindi la progettazione copiano ** ** alla finestra. Dynamics 365 per le operazioni limita la tabella in genere verrà denominato "AXTable1". Ad esempio, riepilogare richiesta Q1: Richiedere le colonne Q4 del foglio di lavoro, Formula = la richiesta Q4\]di richiesta +AxTable1 Q3\]\[di richiesta +AxTable1 Q2\]\[di richiesta +AxTable1 Q1\]\[di AxTable1\[.

Ripetere questi passaggi per inserire ** rettifica ** la colonna. Utilizzare la formula = la richiesta\]\*$I$1 di totale di AxTable1\[per la colonna. Questo sarà il valore della cella I1 e moltiplicherà i valori ** ammonti alla richiesta ** nella colonna per calcolare gli importi di rettifica.

Consente di salvare e chiudere il file di Excel. Tornare a Dynamics 365 per le operazioni e in layout ** **, fare clic su ** modello &gt; caricare ** per caricare il modello salvato di Excel da utilizzare per il piano di budget. 

![[] (bpt10. /media/bpt10-1024x352.png)](. /media/bpt10.png) 

** Chiudono layout ** il cursore. ** Piano di budget ** nel documento, fare clic su ** foglio di lavoro ** per visualizzare e modificare il documento in Excel. Si noti che il modello Excel rettificata utilizzato per creare il foglio di calcolo del piano di budget e le colonne calcolate vengono aggiornate mediante formule definite nei passaggi precedenti. 

![[] (bpt11. /media/bpt111-1024x431.png)](. /media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>È di punta e inganna per creare modelli del piano di budget
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Posso aggiungere e utilizzare le origini dati supplementari a un modello di piano di budget?

Sì, è possibile utilizzare ** progettazione ** il menu per aggiungere le entità aggiuntivi allo stesso o altri documenti nel modello Excel. Ad esempio, è possibile aggiungere ** BudgetPlanProposedProject ** l'origine dati per creare e gestire un elenco di progetti proposti contemporaneamente si utilizzano i dati del piano di budget in Excel. Tenere presente che incluse le origini dati in pochi può influire sulle prestazioni della cartella di lavoro di Excel. 

È possibile utilizzare ** filtro ** l'opzione in ** Connector di dati ** per aggiungere i filtri desiderati origini dati aggiuntivi.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Posso nascondere l'opzione di progettazione in Connector di dati per altri utenti?

Sì **, aprire Connector di dati ** le opzioni per nascondere ** progettazione ** l'opzione che altri utenti.

![[] (bpt13. /media/bpt13-1024x565.png)](. /media/bpt13.png)

Per espandere ** opzioni di Connector di dati ** e deselezionare ** consentono la progettazione ** la casella di controllo. Questo nasconderà ** progettazione ** l'opzione da connettori ** di dati **.

![[] (bpt14. /media/bpt14-1024x592.png)](. /media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Posso impedire agli utenti venga di chiudere il Connector dei dati di lavoro con i dati?

Si consiglia di chiudere il modello è bloccato per impedire agli utenti di chiudere la finestra. Per attivare il blocco, fare clic su ** Connector ** di dati, a destra nell'angolo superiore che viene visualizzata una freccia. 

![[] (bpt15. /media/bpt15-1024x285.png)](. /media/bpt15.png) 

Cliccano la freccia per un menu aggiuntiva. Selezionare blocchi ** **.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>![[] (bpt16. /media/bpt16-1024x614.png)](. /media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Posso utilizzare altre funzionalità di Excel, ad esempio formattazione di celle, colori, formattazione condizionale e i grafici ai modelli personali del piano di budget?

Sì, la maggior parte delle capacità standard di Excel funzionerà nei modelli del piano di budget. Si consiglia utilizzando la codifica colori per gli utenti distinguiamo tra le colonne di sola lettura e modificabile. La formattazione condizionale può essere utilizzata per evidenziare le aree problemi di budget. I totali di colonna possono essere inviati facilmente mediante formule di calcolo di Excel nella tabella.

È inoltre possibile creare e utilizzare le tabelle pivot e i grafici per gruppi aggiuntivi e le visualizzazioni dei dati di budget. In ** dati ** cataloghi, ** connessioni ** nel gruppo, fare clic su ** aggiornare tutti ** quindi fare clic su ** proprietà di connessione **. Fare clic su ** ** utilizzare la scheda. In ** aggiornare **, selezionare ** aggiornare i dati all'apertura del file ** la casella di controllo. 

![[] (bpt17. /media/bpt17-1024x614.png)](. /media/bpt17.png)


