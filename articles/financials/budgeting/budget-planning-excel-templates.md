---
title: Modelli di pianificazione del budget per Excel
description: In questo argomento viene descritto come creare modelli di Microsoft Excel che possono essere utilizzati con i piani di budget.
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 156688b705337331e083ebc19fded57b028acb67
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-templates-for-excel"></a>Modelli di pianificazione del budget per Excel

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come creare modelli di Microsoft Excel che possono essere utilizzati con i piani di budget.

In questo argomento viene illustrato come creare modelli di Excel che verranno utilizzati con i piani di budget con il set di dati dimostrativi standard e l'accesso utente Admin. Per ulteriori informazioni sulla pianificazione del budget, vedere [Panoramica sulla pianificazione del budget.](budget-planning-overview-configuration.md) È inoltre possibile seguire l'esercitazione [Pianificazione del budget 101](budget-plan.md) per apprendere i principi di base sulla configurazione e l'uso del modulo.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Generare un foglio di lavoro usando il layout dei documenti del piano di budget

I documenti del piano di budget possono essere visualizzati e modificati utilizzando uno o più layout. Ogni layout può avere un modello di documento di piano di budget associato per visualizzare e modificare i dati del piano di budget in un foglio di lavoro di Excel. In questo argomento, un modello di documento del piano di budget verrà generato utilizzando una configurazione di layout esistente. 

1. Aprire l'**elenco dei piani di budget** (**Impostazione budget** &gt; **Piani di budget**). 
2. Fare clic su **Nuovo** per creare un nuovo documento di piano di budget. 

   [![Elenco piani di budget](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Usare l'opzione **Aggiungi** riga per aggiungere righe. Fare clic su **Layout** visualizzare la configurazione di layout del documento di piano di budget. 

   [![Aggiunta piani di budget](./media/bpt2-1024x274.png)](./media/bpt2.png) 

È possibile rivedere la configurazione del layout e modificarla in base alle necessità. 
1. Passare a **Modello** &gt; **Genera** per creare un file di Excel per il layout. 
2. Dopo che il modello viene generato, passare a **Modello** &gt; **Visualizza**  per aprire e rivedere il modello di documento di piano di budget. È possibile salvare il file di Excel nell'unità locale. 

[![Salva con nome](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> Il layout di documento del piano di budget non può essere modificato dopo che viene associato a un modello di Excel. Per modificare il layout, eliminare il file del modello di Excel associato e rigenerarlo. Questa operazione è necessaria per mantenere i campi nel layout e nel foglio di lavoro sincronizzati. 

Il modello di Excel contiene tutti gli elementi dal layout di documento del piano di budget, in cui la colonna **Disponibile nel foglio di lavoro** è impostata su True. La sovrapposizione di elementi non è consentita nel modello Excel. Ad esempio, se il layout include le colonne Request Q1, Request Q2, Request Q3, e Request Q4 e una colonna di richiesta totale che rappresenta una somma di tutte le 4 colonne trimestrali, solo le colonne trimestrali o la colonna totale è disponibile da utilizzare nel modello Excel. Il file di Excel non può aggiornare le colonne sovrapposte durante l'aggiornamento perché i dati della tabella possono diventare obsoleti e inesatti.

[![Esempio](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> Per evitare problemi potenziali di visualizzazione e modifica dei dati del piano di budget utilizzando Excel, lo stesso utente deve essere collegato sia a Microsoft Dynamics 365 for Finance and Operations che al connettore dati del componente aggiuntivo per Office di Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Aggiungere un'intestazione al modello di documento del piano di budget
Per aggiungere informazioni di intestazione, selezionare la riga superiore nel file di Excel e inserire righe vuote. Fare clic su **Progettazione** in **Connettore dati** per aggiungere i campi di intestazione al file Excel.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

Nella scheda **Progettazione**, fare clic sui campi **Aggiungi** quindi selezionare **BudgetPlanHeader** come origine dati di entità.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

Puntare il cursore nella posizione desiderata nel file di Excel. Fare clic su **Aggiungi etichetta** per aggiungere l'etichetta del campo nella posizione selezionata. Selezionare **Aggiungi valore** per il campo relativo al valore nel posto selezionato. Fare clic su **Fine** per chiudere la finestra di progettazione.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Aggiungere una colonna calcolata alla tabella del modello di documento del piano di budget
--------------------------------------------------------------

A questo punto, le colonne calcolate verranno aggiunte al modello del documento piano di budget generato. Una colonna **Total request** che riepiloga le colonne Request Q1: Request Q4 e una colonna **Adjustment** che ricalcola la colonna **Total Request** in base a un fattore predefinito.

Fare clic su **Progettazione** in **Connettore dati** per aggiungere colonne alla tabella. Fare clic su **Modifica** accanto all'origine dati **BudgetPlanWorksheet** per avviare l'aggiunta delle colonne.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

Il gruppo di campi selezionato visualizza le colonne disponibili nel modello. Fare clic su **Formula** per aggiungere una nuova colonna. Assegnare un nome alla nuova colonna quindi incollare la formula nel campo **Formula**. Fare clic su **Aggiorna** per inserire la colonna.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Per definire la formula, creare la formula nel foglio di calcolo quindi copiarla nella finestra di **Progettazione**. Una tabella associata a Finance and Operations in genere verrà denominata "AXTable1". Ad esempio, per le riepilogare le colonne Request Q1 : Request Q4 del foglio di calcolo, la formula  = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\].

Ripetere questi passaggi per inserire la colonna **Adjustment**. Utilizzare la formula = AxTable1\[Total request\]\*$I$1 per la colonna. Questa accetterà il valore della cella I1 e moltiplicherà i valori nella colonna **Total request** per calcolare gli importi di rettifica.

Salvare e chiudere il file di Excel. Tornare a Finance and Operations e in **Layout**, fare clic su **Modello &gt; Carica** per caricare il modello salvato di Excel da utilizzare per il piano di budget. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Chiudere il dispositivo di scorrimento **Layout**. Nel documento **Piano di budget**, fare clic su **Foglio di lavoro** per visualizzare e modificare il documento in Excel. Si noti che il modello Excel rettificato è stato utilizzato per creare questo foglio di lavoro del piano di budget e le colonne calcolate vengono aggiornate mediante le formule definite nei passaggi precedenti. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Suggerimenti per creare modelli del piano di budget
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Posso aggiungere e utilizzare origini dati supplementari a un modello di piano di budget?

Sì, è possibile utilizzare il menu **Progettazione** per aggiungere le entità aggiuntivi allo stesso o altri fogli nel modello Excel. Ad esempio, è possibile aggiungere l'origine dati **BudgetPlanProposedProject** per creare e gestire un elenco di progetti proposti contemporaneamente all'uso dei dati del piano di budget in Excel. Tenere presente che includere origini dati di volume elevato può influire sulle prestazioni della cartella di lavoro di Excel. 

È possibile utilizzare l'opzione **Filtro** in **Connettore dati** per aggiungere i filtri desiderati alle origini dati aggiuntive.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Posso nascondere l'opzione di progettazione in Connettore dati ad altri utenti?

Sì. aprire le opzioni del **Connettore dati** per nascondere l'opzione **Progettazione** ad altri utenti.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Espandere le opzioni del **Connettore dati** e deselezionare la casella di controllo **Abilita progettazione**. Questo nasconderà l'opzione  **Progettazione** dal **Connettori dati**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Posso impedire agli utenti di chiudere accidentalmente il connettore dati mentre utilizzano i dati?

Si consiglia di bloccare il modello per impedire agli utenti di chiuderlo. Per abilitare il blocco, fare clic su  **Connettore dati**, nell'angolo superiore destro viene visualizzata una freccia. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Fare clic sulla freccia per un menu aggiuntivo. Selezionare **Blocca**.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Posso utilizzare altre funzionalità di Excel, ad esempio formattazione di celle, colori, formattazione condizionale e i grafici con i modelli del piano di budget?

Sì, la maggior parte delle funzionalità standard di Excel funzionerà nei modelli del piano di budget. Si consiglia utilizzate la codifica colori per gli utenti per distinguere tra le colonne di sola lettura e modificabili. La formattazione condizionale può essere utilizzata per evidenziare le aree problematiche del budget. I totali di colonna possono essere presentati facilmente mediante formule di Excel standard sopra la tabella.

È inoltre possibile creare e utilizzare tabelle pivot e i grafici per raggruppamenti e visualizzazioni ulteriori dei dati di budget. Nella scheda **Dati**, nel gruppo **Connessioni**, fare clic su **Aggiorna tutti**, quindi su **Proprietà connessione**. Nella scheda **Utilizzo** in **Aggiorna**, selezionare la casella di controllo **Aggiorna dati all'apertura del file**. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)




