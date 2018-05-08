---
title: Rilascio delle righe di formula e DBA nel magazzino
description: In questo argomento viene descritto il processo per il rilascio di materie prime per righe DBA e righe formula nel magazzino.
author: johanhoffmann
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validfrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 838dc1e5867b8380823275aba5fc425003a54523
ms.contentlocale: it-it
ms.lasthandoff: 03/08/2018

---

# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>Rilascio delle righe di formula e DBA nel magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto il processo per il rilascio di materie prime per righe distinta base (DBA) e righe formula nel magazzino. Quando si rilascia una DBA o una riga formula nel magazzino, il sistema determina innanzitutto se il materiale è già disponibile nell'ubicazione di input di produzione nello shop floor in cui il materiale verrà consumato per il processo di produzione.

- Se il materiale è disponibile nell'ubicazione di produzione, viene prelevato da quell'ubicazione immediatamente dopo il segnale per il rilascio del materiale nel magazzino.
- Se il materiale non è disponibile nell'ubicazione di produzione, il rilascio del materiale indica che il materiale deve essere spostato dalle ubicazioni nel magazzino all'ubicazione di input di produzione. Il materiale viene spostato tramite il lavoro magazzino per il prelievo di materie prime. Di conseguenza, i processi di magazzino per il prelievo di materie prime devono essere configurati. Per ulteriori informazioni, vedere [Rifornimento](../warehousing/replenishment.md) e [Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione](../warehousing/control-warehouse-location-directives.md).

## <a name="methods-for-releasing-bom-and-formula-lines"></a>Metodi per il rilascio di DBA e righe formula

È possibile configurare il rilascio di DBA e righe formula in modo che si verifichi come parte del rilascio di un ordine di produzione o di un ordine batch. In alternativa, la versione può essere controllata da un processo batch o essere eseguita come interazione manuale.

Il metodo utilizzato per rilasciare DBA e righe formula è controllato dal parametro **Rilascio riga di produzione**. È possibile trovare questo parametro in **Controllo produzione** \> **Impostazione** \> **Parametri di produzione**.

- **Rilascio DBA e righe formula come parte del rilascio di un ordine di produzione o di un ordine batch** - In questo metodo, DBA e righe per un ordine di produzione o un ordine batch vengono rilasciate durante il processo di rilascio di un ordine. Di solito, durante il rilascio di un ordine di produzione o batch, i processi di produzione vengono rilasciati per per i lavoratori del reparto produzione e vengono stampati i documenti di produzione. Durante questo processo, lo stato dell'ordine viene modificato come **Rilasciato**.
- **Rilascio di DBA e righe formula mediante un processo batch o come interazione manuale** - In questo metodo, DBA e righe formula possono essere rilasciate solo tramite il processo batch **Rilascio automatico di righe di DBA e di formula** o come interazione manuale. Per rilasciare manualmente DBA e righe formula, nella pagina elenco dell'ordine di produzione o nella pagina dettagli dell'ordine di produzione, nel riquadro azioni **Rilascia in magazzino**.

Per una rapida dimostrazione di come rilasciare BOM e righe formula in produzione utilizzando un processo batch, guardare questo breve video di YouTube:
[!Video <https://www.youtube.com/embed/8urAJn50dQ8>]

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>Rilascio di DBA e righe formula utilizzando un processo batch

Il processo batch **Rilascio automatico di righe di DBA e di formula** esamina la DBA e le righe formula selezionate con una quantità rimanente da rilasciare. Il processo prende in considerazione solo gli ordini con stato **Rilasciato**, **Iniziato** oppure **Dichiarato finito**. Se una distinta base o una riga formula ha una quantità rimanete da rilasciare, il processo rilascia fino alla quantità che può essere coperta dalla quantità che è già stata fisicamente prenotata e la quantità fisicamente disponibile.

### <a name="example-of-a-batch-job-release"></a>Esempio di rilascio di un processo batch

| Scenario | Quantità rimanente per rilascio | Quantità fisica prenotata | Quantità fisica disponibile | Quantità rilasciata dal processo batch |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>Impostazione del processo batch

Nella query per il processo batch **Rilascio automatico di righe di DBA e di formula**, è possibile impostare un criterio di filtro per specificare il numero con quanti giorni in anticipo il processo deve cercare le righe con quantità non rilasciate. Nella query per il processo, nel campo **Data materie prime**, utilizzare la funzione **(LessThanDate())** come criterio di filtro.

Nella figura seguente viene illustrato un ordine di produzione con due processi, 10 e 20, relativi all'assemblaggio e all'imballaggio per l'ordine di produzione. Ogni processo viene impostato per il consumo di una quantità di materiale. In questa illustrazione, l'intervallo temporale di rilascio indicato dalla freccia verde sotto la riga del tempo è uguale al numero di giorni specificato nel criterio **(LessThanDate())**. Ad esempio, **(LessThanDate(2))** indica che il processo deve cercare le quantità non rilasciate solo all'interno di un intervallo temporale dei due giorni.

![Esempio di un ordine di produzione con due processi batch](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>Rilasciare materiale per numero operazione o proporzionalmente alla quantità di prodotti finiti

Se si rilasciano i materiali mediante l'impostazione dei parametri **Su rilascio di ordine di produzione**, quando si effettua un rilascio manuale, sono disponibili due opzioni per il controllo del rilascio materiali:

- Rilascio materiale per numero di operazione.
- Rilascio materiale proporzionalmente alla quantità di prodotti finiti.

### <a name="release-material-per-operation-number"></a>Rilasciare materiale per numero di operazione

Per controllare le operazioni per cui il materiale deve essere rilasciato, utilizzare la pagina **Rilascia in magazzino**.

- Selezionare **Controllo produzione** \> **Ordini di produzione** \> **Tutti gli ordini di produzione**, selezionare un ordine di produzione e quindi nella scheda **Magazzino** selezionare **Rilascia in magazzino**. Utilizzare quindi i campi **Da oper. n.** e **A oper. n.** per specificare l'intervallo di numeri di operazione.

Nella figura seguente viene illustrato un ordine di produzione con due operazioni, 10 e 20. In questo esempio, se si limita il rilascio all'operazione 10, solo il materiale M9203 verrà rilasciato.

![Esempio di rilascio di materiali per numero di operazione](media/two-operations.PNG)

Per una rapida dimostrazione di come distribuire materiale in proporzione alla quantità di prodotti finiti, guardare questo breve video di YouTube:
[!Video <https://www.youtube.com/embed/Rm3ojAz6Zu0>]

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>Rilasciare materiale proporzionalmente alla quantità di prodotti finiti

È possibile rilasciare le materie prime per una quantità parziale dei prodotti finiti o in un'unità specifica.

- Per rilasciare le materie prime per una quantità parziale dei prodotti finiti, selezionare **Controllo produzione** \> **Ordini di produzione** \> **Tutti gli ordini di produzione**, selezionare un ordine di produzione e quindi nella scheda **Magazzino** selezionare **Rilascia in magazzino**. Nel campo **Quantità** immettere una quantità.

    Ad esempio, un ordine di produzione viene creato e programmato per 1.000 pezzi. Il supervisore dello shop floor sta pianificando la produzione di 100 pezzi per il turno successivo e desidera rilasciare materiali solo per questo turno di lavoro. In questo caso, il supervisore può utilizzare il campo **Quantità** per rilasciare materiali per i 100 pezzi pianificati per il turno successivo.

- Per rilasciare le materie prime in un'unità specifica, selezionare **Controllo produzione** \> **Ordini di produzione** \> **Tutti gli ordini di produzione**, selezionare un ordine di produzione e quindi nella scheda **Magazzino** selezionare **Rilascia in magazzino**. Utilizzare quindi il campo **Unità** per selezionare l'unità del prodotto finito in cui rilasciare il materiale.

    Le unità disponibili sono definite nell'ID gruppo di sequenze unità del prodotto finito.

    Ad esempio, un prodotto finito ha la seguente conversione di unità tra chilogrammi (kg) e pallet (PL): PL 1 = 100 kg. Per creare un ordine di produzione per 10.000 kg del prodotto finito, è possibile rilasciare le materie prime per il numero di pallet che si pianifica di produrre. Selezionare **PL** come unità quindi selezionare un numero corrispondente nel campo **Quantità**.

