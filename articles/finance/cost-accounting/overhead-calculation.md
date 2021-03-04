---
title: Calcolo generale
description: In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444894"
---
# <a name="overhead-calculation"></a>Calcolo generale

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.

<a name="term-definition"></a>Definizione del termine
---------------

I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico. I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto. Di seguito sono riportati alcuni esempi di costi generali:

-   Affitto
-   Elettricità
-   Stipendi amministrativi

## <a name="overhead-calculation-overview"></a>Panoramica del calcolo dei costi generali
Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto. È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici. Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni. Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione. Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo. L'ID univoco della versione è costituito dai seguenti elementi:

-   Tipo di versione
-   Data e ora
-   Movimento CoGe di contabilità industriale
-   Anno fiscale
-   Periodo fiscale

Il calcolo dei costi generali viene eseguito indipendentemente dalla versione. Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo. Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente. A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione. In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo. I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output. Di conseguenza, la tracciabilità è sempre completa. 

[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>Calcolare e allocare il costo generale dell'elettricità
Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria. Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale. In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative. Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa. Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.

<table>
<thead>
<tr>
<th>Data di registrazione</th>
<th colspan="2">Centro di costo</th>
<th colspan="2">Conto principale</th>
<th>Importo nella valuta di contabilizzazione</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 gennaio 2017</td>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>10.000,00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>Passaggio 1: Elaborare il calcolo comportamento costo

Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale. Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.

#### <a name="define-the-cost-behavior-rule"></a>Definire la regola di comportamento costo

In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo. Le bollette elettricità spesso corrispondono a questa definizione. Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH). Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:

-   Importo fisso 1.000,00
    -   0 &lt;= 1.000,00 = Fisso
    -   1.000,01 &lt; N = Variabile

##### <a name="journal"></a>Giornale di registrazione

<table>
<thead>
<tr>
<th>Giornale di registrazione</th>
<th>Tipo giornale di registrazione</th>
<th colspan="3">Periodo di calendario fiscale</th>
<th>Versione</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>Giornale di registrazione calcoli comportamento costo</td>
<td>Fiscale</td>
<td>2017</td>
<td>Periodo 1</td>
<td>Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Scritture contabili (scritture contabili saldo oggetto di costo)

<table>
<thead>
<tr>
<th>Data di registrazione</th>
<th colspan="2">Oggetto di costo</th>
<th colspan="2">Elemento di costo</th>
<th>Comportamento costo</th>
<th>Importo</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 gennaio 2017</td>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Non classificato</td>
<td>10.000,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Voci di costo

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th colspan="2">Elemento di costo</th>
<th>Comportamento costo</th>
<th>Importo</th>
<th>Data di registrazione</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Non classificato</td>
<td>10.000,00</td>
<td>3 gennaio 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Non classificato</td>
<td>-10.000,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>1.000,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>9.000,00</td>
<td>31 gennaio 2017</td>
</tr>
</tbody>
</table>

Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).
### <a name="step-2-process-the-cost-distribution-calculation"></a>Passaggio 2: Elaborare il calcolo distribuzione costo

La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante. La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.

#### <a name="define-the-cost-distribution-rule"></a>Definire la regola di distribuzione costo

Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria. Nella contabilità industriale, questo approccio non è sufficientemente dettagliato. Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa. La base di allocazione più logica è il consumo di elettricità (KWH). Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità. Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>KWH</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>1.000</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>6.000</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>0</td>
</tr>
</tbody>
</table>

Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Grandezza</th>
<th>Fattore di allocazione</th>
<th>Importo</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>1.000</td>
<td>(1.000 ÷ 7.000) × 9.000,00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>6.000</td>
<td>(6.000 ÷ 7.000) × 9.000,00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>0</td>
<td>(0 ÷ 7.000) × 9.000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità. È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Formula</th>
<th>Grandezza</th>
<th>Fattore di allocazione</th>
<th>Importo</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>(1.000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1.000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>(6.000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1.000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>(0 &gt; 0,00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1.000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Giornale di registrazione

<table>
<thead>
<tr>
<th>Giornale di registrazione</th>
<th>Tipo giornale di registrazione</th>
<th colspan="3">Periodo di calendario fiscale</th>
<th>Versione</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>Giornale di registrazione calcolo distribuzione costo</td>
<td>Fiscale</td>
<td>2017</td>
<td>Periodo 1</td>
<td>Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Scritture contabili (scritture contabili saldo oggetto di costo)

<table>
<thead>
<tr>
<th>Data di registrazione</th>
<th colspan="2">Oggetto di costo</th>
<th colspan="2">Elemento di costo</th>
<th>Comportamento costo</th>
<th>Importo</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 gennaio 2017</td>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>1.000,00</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>9.000,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Voci di costo

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th colspan="2">Elemento di costo</th>
<th>Comportamento costo</th>
<th>Importo</th>
<th>Data di registrazione</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>-1.000,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>500,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>500,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro di costo predefinito</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>-9.000,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>1,285.71</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>7,714.29</td>
<td>31 gennaio 2017</td>
</tr>
</tbody>
</table>

Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md). 

### <a name="step-3-process-the-overhead-rate-calculation"></a>Passaggio 3: Elaborare il calcolo tassi generali

Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici. L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata. 

#### <a name="define-the-overhead-rate"></a>Definire il tasso generali

L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni. Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Ore</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Progetto 1</td>
<td>3</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Progetto 2</td>
<td>1</td>
</tr>
</tbody>
</table>

È stato definito un tasso costo predeterminato per il supporto di progetti di costi.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Elemento di costo</th>
<th>Comportamento costo</th>
<th>Unità</th>
<th>Tasso</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Costo variabile</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Grandezza</th>
<th>Elemento di costo</th>
<th>Fattore di allocazione</th>
<th>Importo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Progetto 1</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10,00</td>
<td>30,00</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Progetto 2</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10,00</td>
<td>10,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Giornale di registrazione

<table>
<thead>
<tr>
<th>Giornale di registrazione</th>
<th>Tipo giornale di registrazione</th>
<th colspan="3">Periodo di calendario fiscale</th>
<th>Versione</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>Giornale di registrazione calcoli tassi generali</td>
<td>Fiscale</td>
<td>2017</td>
<td>Periodo 1</td>
<td>Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>Scritture contabili (Scritture contabili per calcolo tassi generali)

<table>
<thead>
<tr>
<th>Data di registrazione</th>
<th colspan="2">Oggetto di costo</th>
<th>Grandezza</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 gennaio 2017</td>
<td>Proj 1</td>
<td>Progetto interno 1</td>
<td>3,00</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>Proj 2</td>
<td>Progetto interno 2</td>
<td>1,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Voci di costo

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th colspan="2">Elemento di costo</th>
<th>Comportamento costo</th>
<th>Importo</th>
<th>Data di registrazione</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>-30,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Proj 1</td>
<td>Progetto interno 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>30,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>-10.00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Progetto interno 2</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>10.00</td>
<td>31 gennaio 2017</td>
</tr>
</tbody>
</table>

Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).

### <a name="step-4-process-the-cost-allocation-calculation"></a>Passaggio 4: Elaborare il calcolo allocazione costo

L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione. Finance supporta il metodo di allocazione reciproco. Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti. Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni. Il saldo di un oggetto costo viene assegnato da una singola base di allocazione. Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate. L'ordine di allocazione è controllato dall'unità di controllo dei costi. 

[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)

#### <a name="define-the-cost-allocation"></a>Definizione dell'allocazione costi

Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo. L'oggetto di costo CC001 HR contribuisce a più oggetti di costo. Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Servizi HR</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>10</td>
</tr>
</tbody>
</table>

L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo. Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Servizi finanziari</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>35</td>
</tr>
</tbody>
</table>

L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo. Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Servizi assemblaggio (ore)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>60</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>20</td>
</tr>
</tbody>
</table>

L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo. Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Servizi di imballaggio (ore)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>80</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>15</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine. Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template). Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Grandezza</th>
<th>Fattore di allocazione</th>
<th>Importo</th>
<th>Comportamento costo</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>35</td>
<td>(35 ÷ 100) × 500,00</td>
<td>175.00</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>55</td>
<td>(55 ÷ 100) × 500,00</td>
<td>275.00</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>10</td>
<td>(10 ÷ 100) × 500,00</td>
<td>50,00</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>35</td>
<td>(35 ÷ 100) × 1.245,71</td>
<td>436.00</td>
<td>Costo variabile</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>55</td>
<td>(55 ÷ 100) × 1.245,71</td>
<td>685.14</td>
<td>Costo variabile</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>10</td>
<td>(10 ÷ 100) × 1.245,71</td>
<td>124.57</td>
<td>Costo variabile</td>
</tr>
</tbody>
</table>

Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Grandezza</th>
<th>Fattore di allocazione</th>
<th>Importo</th>
<th>Comportamento costo</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>65</td>
<td>(65 ÷ 100) × (500,00 + 175,00)</td>
<td>438.75</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>35</td>
<td>(35 ÷ 100) × (500,00 + 175,00)</td>
<td>236.25</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>65</td>
<td>(65 ÷ 100) × (7.714,29 + 436,00)</td>
<td>5,297.69</td>
<td>Costo variabile</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>35</td>
<td>(35 ÷ 100) × (7.714,29 + 436,00)</td>
<td>2,852.60</td>
<td>Costo variabile</td>
</tr>
</tbody>
</table>

Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Grandezza</th>
<th>Fattore di allocazione</th>
<th>Importo</th>
<th>Comportamento costo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275,00 + 438,75)</td>
<td>535.31</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275,00 + 438,75)</td>
<td>178.44</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5.297,69 + 685,14)</td>
<td>4,487.12</td>
<td>Costo variabile</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5.297,69 + 685,14)</td>
<td>1,495.71</td>
<td>Costo variabile</td>
</tr>
</tbody>
</table>

Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th>Grandezza</th>
<th>Fattore di allocazione</th>
<th>Importo</th>
<th>Comportamento costo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50,00 + 236,25)</td>
<td>241.05</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50,00 + 236,25)</td>
<td>45.20</td>
<td>Costo fisso</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2.852,60 + 124,57)</td>
<td>2,507.09</td>
<td>Costo variabile</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2.852,60 + 124,57)</td>
<td>470.08</td>
<td>Costo variabile</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Scritture contabili (scritture contabili saldo oggetto di costo)

<table>
<thead>
<tr>
<th>Giornale di registrazione</th>
<th>Tipo giornale di registrazione</th>
<th colspan="3">Periodo di calendario fiscale</th>
<th>Versione</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>Giornale di registrazione allocazione costi</td>
<td>Fiscale</td>
<td>2017</td>
<td>Periodo 1</td>
<td>Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>Righe giornale di registrazione

<table>
<thead>
<tr>
<th>Data di registrazione</th>
<th colspan="2">Oggetto di costo</th>
<th colspan="2">Elemento di costo</th>
<th>Comportamento costo</th>
<th>Importo</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 gennaio 2017</td>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>500,00</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>1,245.71</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>675.00</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>8,150.29</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>713.75</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>5,982.83</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC003</td>
<td>Imballaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>286.25</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>CC003</td>
<td>Imballaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>2,977.17</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>776.36</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>6,994.21</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>Prod 2</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>223.64</td>
</tr>
<tr>
<td>31 gennaio 2017</td>
<td>Prod 2</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Voci di costo

<table>
<thead>
<tr>
<th colspan="2">Oggetto di costo</th>
<th colspan="2">Elemento di costo</th>
<th>Comportamento costo</th>
<th>Importo</th>
<th>Data di registrazione</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>-500,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>175.00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>275.00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>50,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Risorse umane</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>-1.245,71</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>436.00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>685.14</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>124.57</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>-675,00</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>438.75</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>236.25</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Dati finanziari</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>-8.150,29</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>5,297.69</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Imballaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>2,852.60</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>-713,75</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>535.31</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>178.44</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>-5.982,83</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>4,487.12</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>1,495.71</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>-286,25</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>241.05</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo fisso</td>
<td>45.20</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblaggio</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>-2.977,17</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Prodotto 1</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>2,507.09</td>
<td>31 gennaio 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Prodotto 2</td>
<td>10001</td>
<td>Elettricità</td>
<td>Costo variabile</td>
<td>470.08</td>
<td>31 gennaio 2017</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>Conclusione
Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo. Di conseguenza, i contabili capiranno che il costo deve essere allocato. Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati. Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.

<table>
<thead>
<tr>
<th colspan="2" rowspan="2">Elemento di costo</th>
<th colspan="9">Oggetto di costo</th>
<th rowspan="2">Totale</th>
</tr>
<tr>
<th>CC099</th>
<th>CC001</th>
<th>CC002</th>
<th>CC003</th>
<th>CC004</th>
<th>Proj 1</th>
<th>Proj 2</th>
<th>Prod 1</th>
<th>Prod 2</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">10001 Elettricità</td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><strong>30.00</strong></td>
<td style="text-align: right;"><strong>10.00</strong></td>
<td style="text-align: right;"><strong>7,770.57</strong></td>
<td style="text-align: right;"><strong>2,189.43</strong></td>
<td style="text-align: right;"><strong>10,000.00</strong></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;">Non classificato</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Costo fisso</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;">776.36</td>
<td style="text-align: right;">223.64</td>
<td style="text-align: right;"><strong>1,000.00</strong></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Costo variabile</td>
<td style="text-align: right;">000</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">30,00</td>
<td style="text-align: right;">10,00</td>
<td style="text-align: right;">6,994.21</td>
<td style="text-align: right;">1,965.79</td>
<td style="text-align: right;"><strong>9,000.00</strong></td>
</tr>
</tbody>
</table>

> [!NOTE]
> In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo. Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione. In altre parole, gli oggetti costo al livello più basso sostengono il costo. Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo. Per ulteriori informazioni, vedere [Criteri rollup costi e calcolo dei costi generali](cost-rollup.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]