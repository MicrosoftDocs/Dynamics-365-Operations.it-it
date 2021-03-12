---
title: Ammortamento a saldi decrescenti
description: Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f188e440922436511db15e1842f1891c2da5b191
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976068"
---
# <a name="reduce-balance-depreciation"></a>Ammortamento a saldi decrescenti

[!include [banner](../includes/banner.md)]

Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti.

Quando si imposta un profilo di ammortamento cespiti e si seleziona A saldi decrescenti nel campo Metodo della pagina Profili di ammortamento, ai cespiti a cui è assegnato questo profilo verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento.

Per impostare l'ammortamento a saldi decrescenti, è necessario anche effettuare selezioni nei campi della scheda dettaglio Generale della pagina Profili di ammortamento. Selezionare innanzitutto un anno nel campo Anno di ammortamento. Le opzioni visualizzate nel campo Frequenza periodo dipendono dalla selezione effettuata nel campo precedente, come indicato di seguito. 

È inoltre necessario immettere un valore nel campo Percentuale relativo al profilo di ammortamento. Se si seleziona l'opzione Ammortamento completo, la base di ammortamento rimanente viene rilevata nell'ultimo periodo di ammortamento e l'importo risultante può essere molto elevato. In alcuni paesi non viene effettuato il passaggio al metodo di ammortamento a quote costanti. Il passaggio avviene quando l'importo di tale metodo è maggiore o uguale all'importo del profilo di ammortamento primario e l'importo di ammortamento sottratto costituisce l'importo del metodo alternativo. 

Poiché un cespite non viene mai completamente ammortizzato in base a un calcolo percentuale, per raggiungere questo scopo è necessario selezionare l'opzione Ammortamento completo.

## <a name="select-a-depreciation-year"></a>Selezionare un anno di ammortamento
È possibile selezionare Calendario o Fiscale nel campo Anno di ammortamento della pagina Profili di ammortamento. In base al valore selezionato verranno definite le opzioni disponibili nel campo Frequenza periodo. L'opzione predefinita è Calendario.

### <a name="calendar"></a>Calendario

Se si seleziona l'opzione Calendario, la base di ammortamento, che in genere corrisponde alla differenza tra il valore contabile netto e il valore di recupero, verrà aggiornata al 1° gennaio di ogni anno. Nell'esempio relativo all'ammortamento a saldi decrescenti illustrato più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli. 

Se si seleziona Calendario, nel campo Frequenza periodo, che consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario, saranno disponibili le seguenti opzioni:

-   Annuale: la registrazione viene eseguita il 31 dicembre.
-   Mensile: viene registrato un importo mensile alla fine di ciascun mese di calendario.
-   Trimestrale: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).
-   Semestrale: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).
-   Giornaliero: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.

Se ad esempio si seleziona Annuale, l'ammortamento annuale viene registrato una sola volta, il 31 dicembre di ciascun anno. Se si seleziona Mensile, l'ammortamento mensile viene registrato ogni mese ed è uguale a 1/12 dell'importo dell'ammortamento annuale.

### <a name="fiscal"></a>Fiscale

Se si seleziona Fiscale nel campo Anno di ammortamento, viene utilizzato il metodo di ammortamento a quote costanti. Viene calcolato in base all'anno fiscale, impostato nella pagina Calendari fiscali per il calendario fiscale selezionato nella pagina Contabilità generale. Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio. La durata dell'anno fiscale non deve essere necessariamente di 12 mesi. L'ammortamento viene rettificato per ciascun periodo fiscale. La durata dell'anno fiscale successivo si basa sui periodi fiscali impostati durante la creazione di un nuovo anno fiscale nella pagina Calendari fiscali.


Se si seleziona Fiscale nel campo Frequenza periodo sono disponibili le seguenti opzioni di frequenza del periodo:

-   Annuale: l'importo totale dell'ammortamento calcolato per l'anno fiscale viene registrato come importo unico nell'ultimo giorno dell'anno fiscale.
-   In Periodo fiscale viene registrato l'importo totale dell'ammortamento calcolato per l'anno fiscale, che viene attribuito ai periodi fiscali definiti per il calendario fiscale selezionato nella pagina Contabilità generale o per il calendario fiscale selezionato per il libro per il cespite.

## <a name="example-of-reducing-balance-depreciation"></a>Esempio di ammortamento a saldi decrescenti

Si supponga che il prezzo di acquisizione di un cespite sia 11.000, il valore di scarto 1.000 e il fattore della percentuale ammortamento 30. 

Utilizzando il metodo A saldi decrescenti, il 30% della base di ammortamento (valore contabile netto meno valore di scarto) viene calcolato alla fine del periodo di ammortamento precedente. L'ammortamento per i primi tre anni viene visualizzato nella seguente tabella.

| Periodo | Calcolo della quota di ammortamento annuale | Valore contabile netto alla fine dell'anno |
|--------|-------------------------------------------|---------------------------------------|
| Anno 1 | (11.000 - 1.000) \* 30% = 3.000           | (11.000 - 1.000) - 3.000 = 7.000      |
| Anno 2 | (7.000 - 1.000) \* 30% = 1.800            | (7.000 -1.800) = 5.200                |
| Anno 3 | (5.200 - 1.000) \* 30% = 1.260            | (5.200 - 1.260) = 3.940               |


-





