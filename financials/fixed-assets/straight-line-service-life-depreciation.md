---
title: Ammortamento a quote costanti basato sulla vita utile
description: Questo articolo offre una panoramica del metodo di ammortamento basato sulla vita utile a quote costanti.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: b210a69ee8675127f6799e0531c024c7b48f4e32
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="straight-line-service-life-depreciation"></a>Ammortamento a quote costanti basato sulla vita utile

[!include[banner](../includes/banner.md)]


Questo articolo offre una panoramica del metodo di ammortamento basato sulla vita utile a quote costanti.

Quando si imposta un profilo di ammortamento cespiti e si seleziona Vita utile a quote costanti nel campo Metodo della pagina Profili di ammortamento, i cespiti cui è assegnato questo profilo vengono ammortizzati in base all'intera vita utile del cespite. In genere è lo stesso importo in ciascun periodo di ammortamento. 

La differenza dell'importo di ammortamento calcolato tra il metodo a quote costanti basato sulla vita utile rimanente del cespite e il metodo a quote costanti basato sulla vita utile del cespite è data dall'eventuale registrazione di una rettifica nel cespite. 

Per impostare l'ammortamento a quote costanti basato sulla vita utile, è inoltre necessario selezionare le opzioni presenti nei campi Anno di ammortamento e Frequenza periodo della pagina Profili di ammortamento.

## <a name="select-a-depreciation-year"></a>Selezionare un anno di ammortamento
È possibile selezionare Calendario o Fiscale nel campo Anno di ammortamento della pagina Profili di ammortamento. In base al valore selezionato verranno definite le opzioni disponibili nel campo Frequenza periodo. L'opzione predefinita è Calendario.

### <a name="calendar"></a>Calendario

Se si seleziona Calendario, si presuppone che l'anno inizi il 1° gennaio e termini il 31 dicembre, anche se il calendario fiscale è stato definito in modo diverso. 

Se si seleziona l'opzione Calendario, la base di ammortamento, che in genere corrisponde alla differenza tra il valore contabile netto e il valore di realizzo, verrà aggiornata al 1° gennaio di ogni anno. Negli esempi illustrati più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli. 

Se si seleziona Calendario, nel campo Frequenza periodo, che consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario, saranno disponibili le seguenti opzioni:
-   Annuale: viene registrato un importo il 31 dicembre.
-   Mensile: viene registrato un importo mensile alla fine di ciascun mese di calendario.
-   Trimestrale: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).
-   Semestrale: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).
-   Giornaliero: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.

Se ad esempio si seleziona Annuale, l'ammortamento annuale viene registrato una sola volta, il 31 dicembre di ciascun anno. Se si seleziona Mensile, l'ammortamento mensile viene registrato ogni mese ed è uguale a 1/12 dell'importo dell'ammortamento annuale.

### <a name="fiscal"></a>Fiscale

Se si seleziona Fiscale nel campo Anno di ammortamento, viene utilizzato l'ammortamento a quote costanti basato sulla vita utile, calcolato in base all'anno fiscale definito dal calendario fiscale specificato per il libro oppure dal calendario fiscale selezionato nella pagina Contabilità generale. I calendari fiscali vengono impostati nella pagina Calendari fiscali.

Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio. La durata dell'anno fiscale non deve essere necessariamente di 12 mesi. L'ammortamento viene rettificato automaticamente per ciascun periodo fiscale. La durata dell'anno fiscale successivo si basa sui periodi fiscali impostati durante la creazione di un nuovo anno fiscale nel modulo Calendari fiscali. 

Se si seleziona Fiscale nel campo Frequenza periodo sono disponibili le seguenti opzioni di frequenza del periodo:
-   L'opzione Annuale registra l'importo totale dell'ammortamento che viene calcolato per l'anno fiscale come importo unico nell'ultimo giorno dell'anno fiscale.
-   Nel periodo fiscale viene calcolato l'importo totale dell'ammortamento per l'anno fiscale, che viene attribuito ai periodi definiti nel modulo Calendari fiscali per l'anno fiscale.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Esempio: ammortamento a quote costanti di un cespite non modificato
Si supponga che un cespite abbia le seguenti caratteristiche.

|                     |        |
|---------------------|--------|
| Costo di acquisizione    | 11.000 |
| Valore di realizzo       | 1.000  |
| Base di ammortamento   | 10.000 |
| Anni vita utile  | 5      |
| Ammortamento annuale | 2.000  |

Si otterrà lo stesso importo di ammortamento per ciascun anno. (Costo di acquisizione - Valore di realizzo) / Anni vita utile

| Periodo | Calcolo dell'importo di ammortamento annuale | Valore contabile netto alla fine dell'anno |
|--------|-------------------------------------------|---------------------------------------|
| Anno 1 | (11.000 - 1.000) / 5 = 2.000              | 9.000                                 |
| Anno 2 | (11.000 - 1.000) / 5 = 2.000              | 7.000                                 |
| Anno 3 | (11.000 - 1.000) / 5 = 2.000              | 5.000                                 |
| Anno 4 | (11.000 - 1.000) / 5 = 2.000              | 3.000                                 |
| Anno 5 | (11.000 - 1.000) / 5 = 2.000              | 1.000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a>Esempio: ammortamento a quote costanti di un cespite modificato

Si supponga di aggiungere allo stesso cespite una rettifica di acquisizione pari a 4000 nell'anno 2. 

La vita utile della rettifica di acquisizione è la stessa del cespite e inizia al momento della relativa acquisizione. Alla fine dell'anno 5 rimane un valore contabile netto che corrisponde al valore contabile netto della rettifica di acquisizione. L'ammortamento per periodo viene calcolato come illustrato nella seguente tabella.

| Periodo | Calcolo della quota di ammortamento annuale | Valore contabile netto alla fine dell'anno |
|--------|-------------------------------------------|---------------------------------------|
| Anno 1 | 10.000 / 5 = 2.000                        | 11.000 - 2.000 = 9.000                |
| Anno 2 | 4.000 (rettifica acquisizione)            | 9.000 + 4.000 =13.000                 |
| Anno 2 | 14.000 / 5 = 2.800                        | 13.000 - 2.800 = 10.200               |
| Anno 3 | 14.000 / 5 = 2.800                        | 10.200 - 2.800 = 7.400                |
| Anno 4 | 14.000 / 5 = 2.800                        | 7.400 - 2.800 = 4.600                 |
| Anno 5 | 14.000 / 5 = 2.800                        | 4.600 - 2.800 = 1.800                 |
| Anno 6 | Importo rimanente 800\*                           | 1.800 – 800 = 1.000                   |

\*Poiché l'importo rimanente è inferiore all'importo dell'ammortamento, viene considerato solo l'importo rimanente meno il valore di realizzo.






