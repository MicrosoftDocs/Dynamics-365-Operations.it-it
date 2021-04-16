---
title: Generare i rendiconti finanziari consolidati
description: In questo argomento vengono descritti vari scenari in cui è possibile generare rendiconti finanziari consolidati.
author: aprilolson
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 2db444d4a5e40c1bbfdab9e044aff43031b6e9f4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826692"
---
# <a name="generate-consolidated-financial-statements"></a>Generare i rendiconti finanziari consolidati

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti vari scenari in cui è possibile generare rendiconti finanziari consolidati.

## <a name="single-level-and-multilevel-consolidations-across-legal-entities"></a>Consolidamenti a singolo livello e multilivello tra persone giuridiche
Il metodo più semplice per il consolidamento tramite la creazione di report finanziari consiste nell'utilizzare gli alberi gerarchici per aggregare i dati di più società con lo stesso piano dei conti e gli stessi periodi fiscali. Di seguito vengono riportati i passaggi di alto livello per eseguire il consolidamento tramite un albero gerarchico.

1. Creare una definizione di riga e assicurarsi che tutti conti appropriati in tutte le società vengano inclusi nelle righe.
2. Creare una definizione di colonna che include tutte le colonne necessarie per il report da creare.
3. Creare un albero gerarchico che include un nodo di report per ciascuna società che si sta utilizzando nei report consolidati.

> [!TIP]
> Per ulteriori informazioni su come creare e gestire definizioni di riga, di colonna e alberi gerarchici, vedere [Componenti del report finanziario](../../dev-itpro/analytics/financial-report-components.md).

Nella figura seguente viene illustrato come utilizzare una definizione di albero gerarchico nei report finanziari per identificare ogni società coinvolta nel consolidamento.

![Definizione di albero gerarchico](./media/reporting-tree-definition.png "Definizione di albero gerarchico")

Come viene mostrato nel report consolidato nella figura seguente, quando si utilizza l'albero gerarchico insieme a una definizione di report, è possibile visualizzare ciascuna società separatamente. Gli importi consolidati vengono visualizzati al livello di riepilogo.

![Livello di riepilogo degli importi consolidati](./media/consolidate-amount-summary-level.png "Livello di riepilogo degli importi consolidati")

È inoltre possibile creare un albero gerarchico multilivello che include tutti i livelli necessari. Nella figura seguente viene illustrata una definizione di albero gerarchico multilivello con rollup per area mondiale.

![Definizione di albero gerarchico multilivello con rollup per area](./media/multilevel-reporting-tree-definition-roll-ups-worldwide-region.png "Definizione di albero gerarchico multilivello con rollup per area")

Nella figura seguente viene illustrata una definizione di albero gerarchico multilivello con rollup per funzione.

![Definizione di albero gerarchico multilivello con rollup per funzione](./media/multilevel-reporting-tree-definition-roll-ups-by-function.png "Definizione di albero gerarchico multilivello con rollup per funzione")

### <a name="viewing-companies-side-by-side"></a>Visualizzazione affiancata delle società
Molti clienti preferiscono i report in cui le società vengono visualizzate affiancate e dove una colonna mostra il totale consolidato. Questo formato è facile da ottenere dopo che è stato creato l'albero gerarchico. Di seguito vengono riportati i passaggi di alto livello per visualizzare le società affiancate nei rendiconti finanziari consolidati.

1. Creare una definizione di colonna che include una colonna **Dimensione finanziaria** per ogni società.
2. Utilizzare il campo **Unità gerarchica** per selezionare l'albero e l'unità gerarchica per ciascuna colonna.
3. Facoltativo: Aggiungere le intestazioni e le colonne dei totali.

Nella figura seguente viene mostrata una definizione di colonna nel formato affiancato.

![Definizione di colonna in un formato affiancato](./media/column-definition-side-by-side-format.png "Definizione di colonna in un formato affiancato")

## <a name="consolidations-that-use-organization-structures-that-are-created-from-legal-entities"></a>Consolidamenti che utilizzano strutture organizzative create da persone giuridiche
Le gerarchie organizzative che contengono dimensioni o persone giuridiche creano dinamicamente definizioni di albero gerarchico nei report finanziari. Un metodo facile per semplificare i consolidamenti consiste nell'aggiungere una gerarchia organizzativa al report nella creazione di report finanziari. In base alla data del report, Financial Reporting selezionerà la gerarchia organizzativa alla data effettiva o prima di questa data, come illustrato nella figura seguente.

![Creare dinamicamente una definizione di albero gerarchico](./media/dynamically-create-reporting-tree-definitions.png "Creare dinamicamente una definizione di albero gerarchico")

## <a name="consolidations-that-involve-eliminations"></a>Consolidamenti che implicano eliminazioni
Le transazioni di eliminazione sono una parte comune del processo di consolidamento. In questo esempio vengono eliminati cinque conti durante il consolidamento: 142600, 211400, 401420, 401180 e 510820. Le società possono impostare diversamente i relativi conti interaziendali. Ad esempio, alcune società impostano l'ultima cifra su 9 se il conto viene utilizzato nelle transazioni interaziendali. Indipendentemente dal metodo, se si conoscono i conti interaziendali, è possibile mostrare le eliminazioni nei rendiconti finanziari consolidati.

Nella figura seguente viene illustrata una definizione di colonna per un conto economico consolidato. Tre conti interaziendali profitti e perdite vengono definiti per ogni società mediante il filtro dimensioni. Le colonne F, G e H includono i conti di eliminazione solo per le società USMF, USRT e DEMF. Le colonne sono impostate in modo che **non** vengano stampate nel rendiconto finanziario.

![Conto economico consolidato con definizione di colonna](./media/column-definition-consolidated-income-statement.png "Conto economico consolidato con definizione di colonna")

Quando viene generato il report, gli importi di eliminazione vengono calcolati nelle colonne F, G e H, e i totali delle colonne nella colonna I. La colonna J mostra gli importi consolidati. Questi importi di consolidamento escludono le eliminazioni per le società USMF, USRT e DEMF.

> [!TIP]
> Creare un secondo report in cui vengono visualizzate solo le voci di eliminazione e utilizzarlo in un gruppo di report che include il report consolidato. In questo modo, si hanno a disposizione tutte le informazioni necessarie per generare tutte le voci di giornale di registrazione necessarie.

L'illustrazione seguente mostra il report consolidato.

![Conto economico in report consolidato](./media/consolidated-report-income-statement.png "Conto economico in report consolidato")

Che si utilizzino conti, dimensioni o entrambi, la funzionalità di creazione di report finanziari consente di filtrare le voci di eliminazione utilizzando le funzionalità di filtro delle dimensioni.

## <a name="minority-interest"></a>Interessi di minoranza
Una società può possedere solo una percentuale di un'altra società. In questo caso, quando si genera un report consolidato, è importante rendere conto solo della percentuale di proprietà della società. La funzionalità di creazione di report finanziari ha vari modi per visualizzare gli interessi di minoranza, a seconda delle preferenze utente. Un modo consiste nell'utilizzare una percentuale di rollup nella definizione di albero gerarchico. Un altro metodo consiste nel mostrare la proprietà di minoranza come riga separata in un report.

### <a name="using-the-reporting-tree-definition"></a>Utilizzo della definizione di albero gerarchico
Nella definizione di albero gerarchico, immettere la percentuale di proprietà nella colonna **% Rollup** (colonna H), come illustrato nella figura seguente. Quando viene generato il report, la percentuale verrà utilizzata per calcolare l'importo consolidato. In questo esempio, Contoso possiede solo l'80% di Contoso Germania. È possibile immettere **80** o **,8** nella colonna **% rollup** e verrà eseguito il rollup dell'80% al livello di consolidamento.

> [!NOTE]
> È possibile applicare questa percentuale di proprietà a qualsiasi unità gerarchica, non solo a livello di società. 

![Utilizzo della percentuale nella definizione dell'albero gerarchico](./media/Using-reporting-tree-definition-percentage.png "Utilizzo della percentuale nella definizione dell'albero gerarchico")

Quando viene generato il report, il report di Contoso Germania mostrerà il 100% dell'importo vendite e l'80% dell'importo verrà allocato con rollup al livello di consolidamento per le vendite.

Se si possiede meno dell'1% della società, è possibile selezionare la casella di controllo **Consenti rollup minore dell'1%** nella scheda **Altre opzioni** della pagina **Impostazioni report**, come mostrato nella figura seguente. In questo caso i valori nella colonna **% rollup** nell'albero gerarchico verranno trattati come se fossero meno dell'1%. Se ad esempio si immette **,8**, verrà eseguito il rollup della percentuale 0,8 al livello di consolidamento, non l'80%. In alternativa è possibile raggiungere lo stesso risultato lasciando deselezionata la casella di controllo **Consenti rollup minore dell'1%** e immettendo **,008** nella colonna **% rollup**.

![Opzioni di impostazione di creazione report](./media/reporting-setting-options.png "Opzioni di impostazione di creazione report")

### <a name="showing-ownership-as-a-separate-row-on-the-consolidated-report"></a>Visualizzazione della proprietà come riga separata nel report consolidato
Un'altra opzione per gli interessi di minoranza consiste nel visualizzare il 100% della società affiliata per ogni riga del report sottraendo al contempo gli interessi non di controllo dal reddito netto.

Come mostrato nella figura, è possibile utilizzare un'istruzione **IF THEN ELSE** e una limitazione di colonna nella definizione di riga per calcolare l'interesse di minoranza nei report finanziari.

![Visualizzazione della proprietà come riga separata nel report consolidato](./media/Showing-ownership-separate-row-consolidated-report.png "Visualizzazione della proprietà come riga separata nel report consolidato")

## <a name="multiple-charts-of-accounts-across-legal-entities"></a>Più piani dei conti tra persone giuridiche
Persone giuridiche diverse hanno spesso piani dei conti diversi, ma hanno ugualmente la necessità di generare rendiconti finanziari consolidati. In questa situazione, è possibile utilizzare la funzionalità di creazione di report finanziari per consolidare i dati in modo da poter generare report finanziari consolidati. Di seguito vengono riportati i passaggi di alto livello per consolidare persone giuridiche con piani de conti diversi.

1. Creare una definizione di riga che abbia più collegamenti a dimensioni finanziarie. È consigliabile che sia presente un collegamento per ogni piano dei conti.
2. Utilizzare la restrizione di un'unità gerarchica nella definizione di colonna per assegnare ogni società alla colonna appropriata.


È possibile aggiungere più collegamenti alle dimensioni finanziarie a ogni riga nella definizione di riga del ogni piano dei conti di ciascuna società univoca. Nella figura seguente, la società USMF utilizza il set di conti nella prima colonna **Collegamento a dimensioni finanziarie** (colonna J) e la società DEMF utilizza i conti nella seconda colonna **Collegamento a dimensioni finanziarie** (colonna K).

> [!TIP]
> Per ulteriori informazioni sulla cella **Collegamento a dimensioni finanziarie**, vedere Specificare la cella Collegamento a Dimensioni finanziarie.

![Primo collegamento del set di conti alle dimensioni finanziarie](./media/set-accounts-first-Link-to-Financial-Dimensions.png "Primo collegamento del set di conti alle dimensioni finanziarie")

È possibile utilizzare un albero gerarchico per definire quali collegamenti alle dimensioni finanziarie dalla definizione di riga viene utilizzato per ogni società. Selezionare la definizione di riga nella colonna E quindi selezionare il collegamento di riga appropriato nella colonna F, come illustrato nella figura seguente.

![Utilizzo della definizione di riga di Collegamento a dimensioni finanziarie](./media/link-financial-dimensions-row-definition-used.png "Utilizzo della definizione di riga di Collegamento a dimensioni finanziarie")

> [!TIP]
> Quando si creano collegamenti a dimensioni finanziarie, utilizzare la descrizione per identificare le società a cui si applica ciascun collegamento. In questo modo, è possibile selezionare più facilmente la società corretta quando si crea un albero gerarchico. Nella definizione di colonna, il campo **Unità gerarchica** consente di restringere ogni colonna a un'unità dell'albero gerarchico, in modo che si possano visualizzare i dati affiancati. Se non si indica una società specifica per una colonna, verranno visualizzati i dati consolidati per tutte le società.

## <a name="different-fiscal-calendars-across-multiple-legal-entities"></a>Calendari fiscali diversi tra più persone giuridiche
Le diverse persone giuridiche potrebbero avere calendari fiscali diversi ma potrebbero comunque avere bisogno di generare rendiconti finanziari consolidati. Esistono due modi per consolidare le persone giuridiche con periodi fiscali diversi:

- Creare una definizione di colonna e utilizzare il periodo e l'anno per mappare i periodi appropriati per ogni società.
- In **Impostazioni** \> **Altro** \> **Altre opzioni** selezionare se consolidare utilizzando la data di fine periodo o il numero di periodo.

Quando si progetta la definizione di colonna per più società con periodi fiscali diversi, è importante considerare quale società verrà assegnata al campo **Nome società** nella definizione di report. Il calendario fiscale di quella società verrà utilizzato come calendario fiscale di base per la definizione di report. La tabella seguente ad esempio mostra l'impostazione del periodo fiscale per le società INMF e USMF. Per i report consolidati, si vuole utilizzare il calendario fiscale utilizzato da USMF. La colonna "Mapping" mostra il periodo e l'anno equivalenti per ogni società se un report viene generato per il 30 giugno 2018.

| Società   | Anno fiscale                                  | Mapping                     |
|-----------|----------------------------------------------|-----------------------------|
| USMF      | Anno fiscale, dal 1° luglio al 30 giugno          | Periodo 12, anno fiscale 2018 | 
| INMF      | Anno di calendario, dal 1° gennaio al 31 dicembre | Periodo 6, anno fiscale 2018  |

Nella figura seguente la società USMF viene specificata nel campo **Nome società** nella definizione di report. Il calendario fiscale della società USMF verrà pertanto utilizzato come calendario fiscale di base. In questo esempio, quando viene generato un report per il 30 giugno 2018, la società USMF utilizzerà il periodo BASE, definito come periodo 12 nella definizione di report. La società INMF utilizzerà BASE–6, che corrisponde al periodo 6. Entrambe le colonne comprenderanno i dati per il giugno 2018.

![Periodo di base del report](./media/report-base-period.png "Periodo di base del report")

La figura seguente mostra le opzioni nella definizione di report che consentono di selezionare se il numero di periodo o la data di fine del periodo viene utilizzata per il consolidamento.

![Numero di periodo nelle opzioni della definizione di report](./media/options-report-definition-period-number.png "Numero di periodo nelle opzioni della definizione di report")

## <a name="business-unit-consolidations"></a>Consolidamenti di Business Unit
Questo argomento è incentrato sull'utilizzo delle definizioni e sulle gerarchie organizzative dell'albero gerarchico nella creazione di report finanziari per scopi di consolidamento. È inoltre possibile utilizzare l'albero gerarchico per creare il consolidamento di Business Unit, ad esempio i report relativi alle vendite o alle operazioni mondiali. Questi report sono un requisito comune. Per crearli, selezionare una società e una dimensione per ogni unità che si vuole utilizzare nel consolidamento. Nella figura seguente ad esempio il rollup della Business Unit viene ottenuto ripetendo ogni società nella colonna **Società** (colonna A) e identificando un gruppo di valori di dimensioni di reparto per società nella colonna **Dimensioni** (colonna D).

![Report di consolidamento di Business Unit](./media/business-unit-consolidation-reports.png "Report di consolidamento di Business Unit")

## <a name="consolidations-that-involve-multiple-reporting-currencies"></a>Consolidamenti che includono più valute di dichiarazione
La creazione di report finanziari offre maggiore flessibilità quando si visualizzano i dati effettivi, di budget, di controllo del budget e di pianificazione del budget in più valute. Se si riuniscono i dati di impostazione chiave, non è necessario impostare altro nella creazione di report finanziari per visualizzare un report, in una valuta qualsiasi, in qualsiasi momento, per un qualsiasi utente.

### <a name="prerequisites"></a>Prerequisiti
Per calcolare correttamente i saldi convertiti, la creazione di report finanziari richiede che la categoria **Conto Utili non distribuiti** venga assegnata al conto Utili non distribuiti nell'elenco **Conto principale**. La creazione di report finanziari non supporta la registrazione al conto Utili non distribuiti. Se le transazioni vengono registrate nel conto Utili non distribuiti, i saldi convertiti non verranno calcolati correttamente. È consigliabile che gli utenti impostino un conto Utili non distribuiti aggiuntivo per registrare le correzioni al conto Utili non distribuiti.

Nel conto principale, è necessario impostare i campi **Tipo di tasso di cambio report finanziari** e **Tipo di conversione valuta** nella Scheda dettaglio **Creazione di report finanziari** per ogni conto, come mostrato nella figura seguente. È possibile completare questa attività conto per conto oppure è possibile utilizzare i modelli di conto per invertire facilmente le modifiche.

- Nel campo **Tipo di tasso di cambio report finanziari** selezionare il tipo di tasso di cambio che contiene le valute e i tassi di cambio da applicare al conto. Questa tabella di valute e tassi di cambio verrà applicata ai dati effettivi nella creazione di report finanziari.
- Nel campo **Tipo di conversione valuta** selezionare il metodo che viene utilizzato per calcolare il tasso di cambio per il conto. Questo metodo di valuta viene utilizzato sia per i dati effettivi che per i dati di budget nella creazione di report finanziari.

![Conti principali per la creazione di report finanziari](./media/Financial-reporting-main-accounts.png "Conti principali per la creazione di report finanziari")

Per i dati di budget, di controllo del budget e di pianificazione del budget, il tipo di tasso di cambio viene definito nella pagina **Contabilità generale**. La tabella verrà utilizzata per estrarre i tassi di cambio e verrà utilizzato il tipo di conversione di valuta assegnato al conto.

### <a name="currency-translation-methods"></a>Metodi di conversione di valuta
Sono disponibili quattro opzioni per calcolare i tassi di cambio nella creazione di report finanziari:

- **Media ponderata** - Questo metodo viene utilizzato con maggiore frequenza per i conti profitti e perdite. Utilizza la seguente formula:

    (Tasso di cambio × Giorni in vigore) ÷ Giorni nel periodo

- **Media** - Questo metodo è un metodo alternativo per i conti profitti e perdite. Utilizza la seguente formula:

    Totale di tassi di cambio ÷ Numero di tassi di cambio

- **Corrente** - Questo metodo viene utilizzato con maggiore frequenza per i conti dello stato patrimoniale. Il tasso di cambio utilizzato è il tasso alla data o prima della data del report o della colonna nella creazione di report finanziari.
- **Data della transazione** - Questo metodo viene utilizzato per i conti di cespiti. Il tasso di cambio utilizzato è il tasso alla data di acquisizione del cespite. Se un tasso non viene specificato per tale data, viene utilizzato il tasso precedente immesso alla data più vicina alla data di acquisizione del cespite.

### <a name="report-designer-options-for-currency-translation"></a>Opzioni di Progettazione report per la conversione di valuta
Nella creazione di report finanziari, qualsiasi report può essere visualizzato in un qualsiasi numero di valute di dichiarazione. I campi seguenti nella definizione di report supportano questa capacità:

- La sezione **Informazioni valuta** nella pagina **Definizione di report**. Questa sezione mostra la valuta i cui sono visualizzati i valori quando viene generato un report.
- Una nuova casella di controllo **Includi tutte le valute di dichiarazione**. Se questa casella di controllo è selezionata, verrà aggiunto un report per ogni valuta di dichiarazione alla coda di report dopo la generazione del report che utilizza la valuta funzionale della società. Se la casella di controllo è deselezionata, è comunque possibile selezionare una valuta di dichiarazione nel Visualizzatore Web. In questo caso, la valuta di dichiarazione verrà elaborata solo quando la si seleziona.

Le opzioni nella definizione di report consentono di convertire facilmente un report in tutte le valute di dichiarazione. Di conseguenza, è possibile eliminare le definizioni di report duplicate che differiscono solo nelle valute utilizzate. Se occorre un report che mostri più valute affiancate, è possibile continuare a utilizzare il campo **Valuta visualizzata** nella pagina **Definizione di colonna** per convertire solo quella colonna del report in una valuta di dichiarazione alternativa.

### <a name="currency-translation-adjustment"></a>Rettifica della conversione di valuta
La rettifica di conversione di valuta (CTA) è la differenza tra i tassi utilizzati per calcolare i conti dello stato patrimoniale e quello utilizzato per calcolare i conti del conto economico. Questa differenza causerà uno squilibrio nello stato patrimoniale. È possibile utilizzare la funzionalità di creazione di report finanziari per calcolare la CTA in due modi:

- Utilizzare la pagina **Arrotondamento delle rettifiche** nella definizione di riga, come illustrato nella figura seguente.

    ![Rettifiche per arrotondamento delle rettifiche alla conversione di valuta](./media/Currency-translation-adjustment-rounding-adjustments.png "Rettifiche per arrotondamento delle rettifiche alla conversione di valuta")

    Quando si specifica la riga che deve visualizzare la rettifica per arrotondamento (CTA), la riga del totale cespiti, la riga delle passività totali e del capitale netto e la soglia ottimale, i report finanziari calcoleranno la differenza e la inseriranno nella riga desiderata. Verrà creata una riga denominata **Rettifica per arrotondamento** e verrà visualizzato il drill-down, come mostrato nella figura seguente.

    ![Drill-down della rettifica per arrotondamento](./media/rounding-adjustment-drill-down.png "Drill-down della rettifica per arrotondamento")

- Inserire tutti i conti in un intervallo, dai cespiti alle spese. Come mostrato nella figura seguente, la differenza sarà lo stesso importo della rettifica per arrotondamento (CTA). Di conseguenza, è possibile utilizzarla come totale di verifica per assicurarsi che la pagina della rettifica per arrotondamento non includa saldi di conti persi.

    ![Verifica della rettifica per arrotondamento](./media/rounding-adjustment-form-check.png "Verifica della rettifica per arrotondamento")

### <a name="balance-calculation-approach"></a>Approccio al calcolo del saldo
Per ottenere la conversione corretta degli importi quando si utilizzano le valute, la creazione di report finanziari utilizza i seguenti metodi di calcolo per i saldi:

- **Media ponderata e media** - Ciascun periodo viene calcolato alla media ponderata e ne viene calcolato il totale per le colonne, ad esempio il trimestre e la data di fine anno.
- **Storico** - Un conto che utilizza il metodo di conversione storico risale sempre alla data della transazione. Se una data di acquisizione è associata la transazione, questa data verrà utilizzata per ottenere il tasso di cambio. Ogni periodo verrà archiviato con totale per migliorare il tempo di calcolo.
- **Corrente** - Le colonne calcolate e dei totali, ad esempio le colonne per il trimestre o la data di fine anno, vengono calcolate alla quotazione corrente che viene determinata nella colonna o nel report. La colonna **Trimestre 1** utilizzerà il tasso del 31 marzo se viene utilizzato l'anno di calendario.

## <a name="additional-resources"></a>Risorse aggiuntive

Per ulteriori informazioni sul consolidamento e sulle conversioni di valuta, vedere l'argomento padre di questo argomento [Panoramica dei consolidamenti finanziari e delle conversioni di valuta](./financial-consolidations-currency-translation.md).

Per ulteriori informazioni su come immettere i dettagli dei consolidamenti online, vedere [Consolidamenti finanziari online](./consolidate-online.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]