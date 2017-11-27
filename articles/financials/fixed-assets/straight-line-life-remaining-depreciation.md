---
title: Ammortamento basato sulla vita utile rimanente a quote costanti
description: Questo articolo offre una panoramica del metodo di ammortamento basato sulla vita utile rimanente a quote costanti.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ebca31727ecdaa2b94d4930174b2461845ab5578
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="straight-line-life-remaining-depreciation"></a>Ammortamento basato sulla vita utile rimanente a quote costanti

[!include[banner](../includes/banner.md)]


Questo articolo offre una panoramica del metodo di ammortamento basato sulla vita utile rimanente a quote costanti.

Quando si imposta un profilo di ammortamento cespiti e si seleziona **Vita utile rimanente a quote costanti** nel campo **Metodo** della pagina **Profili di ammortamento**, l'ammortamento dei cespiti assegnati al profilo di ammortamento verrà basato sulla vita utile rimanente del cespite. In genere è lo stesso importo in ciascun periodo di ammortamento. Per impostare l'ammortamento a quote costanti basato sulla vita utile rimanente, è inoltre necessario selezionare le opzioni presenti nel campo **Anno di ammortamento** e nel campo **Frequenza periodo** della pagina **Profili di ammortamento**. Le opzioni disponibili nel campo **Frequenza periodo** variano a seconda del valore selezionato in **Anno di ammortamento**.

## <a name="select-a-depreciation-year"></a>Selezionare un anno di ammortamento
È possibile selezionare **Calendario** o **Fiscale** nel campo **Anno di ammortamento** della pagina **Profili di ammortamento**. Il valore predefinito è **Calendario**. La selezione determina le opzioni disponibili nel campo **Frequenza periodo**. Il campo consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario.

### <a name="calendar"></a>Calendario

Se si seleziona **Calendario** nel campo ***Anno di ammortamento***, si presuppone che l'anno inizi il primo gennaio e termini il 31 dicembre, anche se il calendario fiscale è stato definito in modo diverso. L'opzione **Calendario** aggiorna la base di ammortamento il 1° gennaio di ogni anno. In genere, la base di ammortamento corrisponde al valore contabile netto meno il valore di realizzo. Nell'esempio illustrato più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli. Se si seleziona **Calendario** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:

-   **Annuale**: viene registrato un importo il 31 dicembre.
-   **Mensile**: viene registrato un importo mensile alla fine di ciascun mese di calendario.
-   **Trimestrale**: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).
-   **Semestrale**: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).
-   **Giornaliero**: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.

Se ad esempio si seleziona **Annuale**, l'ammortamento annuale viene registrato una sola volta, il 31 dicembre di ciascun anno. Se si seleziona **Mensile**, l'ammortamento mensile viene registrato ogni mese ed è uguale a 1/12 dell'importo dell'ammortamento annuale.

### <a name="fiscal"></a>Fiscale

Se si seleziona **Fiscale** nel campo **Anno di ammortamento**, viene utilizzato l'ammortamento a quote costanti basato sulla vita utile rimanente, calcolato in base agli anni fiscali rimanenti. Se ad esempio l'anno fiscale inizia il 1° luglio 2015 e termina il 30 giugno 2016, il calcolo dell'ammortamento inizia il 1° luglio. La durata dell'anno fiscale non deve essere necessariamente di 12 mesi. L'ammortamento viene rettificato per ciascun periodo fiscale. La durata dell'anno fiscale successivo si baserà sui periodi fiscali impostati nella pagina **Calendari fiscali**. Se si seleziona **Fiscale** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:

-   L'opzione **Annuale** registra l'importo totale dell'ammortamento che viene calcolato per l'anno fiscale come importo unico nell'ultimo giorno dell'anno fiscale.
-   **Periodo fiscale**calcola l'importo totale dell'ammortamento per l'anno fiscale. L'importo totale viene quindi attribuito ai periodi fiscali definiti nella pagina **Calendari fiscali** per il calendario fiscale specificato per il libro.

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Esempio di ammortamento a quote costanti di un cespite non modificato
A un cespite sono associate le seguenti caratteristiche.

|                     |        |
|---------------------|--------|
| Costo di acquisizione    | 11.000 |
| Valore di realizzo       | 1.000  |
| Base di ammortamento   | 10.000 |
| Anni vita utile  | 5      |
| Ammortamento annuale | 2.000  |

L'importo di ammortamento è uguale ogni anno: (Costo di acquisizione – Valore di realizzo) ÷ Anni vita utile

| Periodo | Calcolo della quota di ammortamento annuale | Valore contabile netto alla fine dell'anno |
|--------|-----------------------------------------------|---------------------------------------|
| Anno 1 | (11.000 – 1.000) ÷ 5 = 2.000                  | 9.000                                 |
| Anno 2 | (9.000 – 1.000) ÷ 4 = 2.000                   | 7.000                                 |
| Anno 3 | (7.000 – 1.000) ÷ 3 = 2.000                   | 5.000                                 |
| Anno 4 | (5.000 – 1.000) ÷ 2 = 2.000                   | 3.000                                 |
| Anno 5 | (3.000 – 1.000) ÷ 1 = 2.000                   | 1.000                                 |






