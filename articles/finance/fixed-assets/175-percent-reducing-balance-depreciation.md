---
title: Ammortamento a saldi decrescenti del 175%
description: Questo argomento offre una panoramica del metodo di ammortamento a saldi decrescenti del 175%.
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8138003971ace280b08760df718671b1779bd101
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230348"
---
# <a name="175-percent-reducing-balance-depreciation"></a>Ammortamento a saldi decrescenti del 175%

[!include [banner](../includes/banner.md)]

Questo argomento offre una panoramica del metodo di ammortamento a saldi decrescenti del 175%.

Quando si imposta un profilo di ammortamento cespiti e si seleziona **Saldo decrescente 175%** nel campo **Metodo** della pagina **Profili di ammortamento**, ai cespiti che sono assegnati al profilo di ammortamento verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento. 

Per impostare l'ammortamento a saldi decrescenti del 175%, è inoltre necessario selezionare le opzioni presenti nel campo **Anno di ammortamento** e nel campo **Frequenza periodo** della pagina **Profili di ammortamento**. Le opzioni disponibili nel campo **Frequenza periodo** variano a seconda del valore selezionato in **Anno di ammortamento**.

## <a name="select-a-depreciation-year"></a>Selezionare un anno di ammortamento
È possibile selezionare **Calendario** o **Fiscale** nel campo **Anno di ammortamento** della pagina **Profili di ammortamento**. Il valore predefinito è **Calendario**. 

La selezione determina le opzioni disponibili nel campo **Frequenza periodo**. Il campo consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario.

### <a name="calendar"></a>Calendario

È possibile scegliere di mantenere il valore predefinito nel campo **Anno di ammortamento**, **Calendario**. 

L'opzione **Calendario** aggiorna la base di ammortamento il 1° gennaio di ogni anno. In genere, la base di ammortamento corrisponde al valore contabile netto meno il valore di recupero. Negli esempi illustrati più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli. 

Se si seleziona **Calendario** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:

-   **Annuale**: viene registrato un importo il 31 dicembre.
-   **Mensile**: viene registrato un importo mensile alla fine di ciascun mese di calendario.
-   **Trimestrale**: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).
-   **Semestrale**: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).
-   **Giornaliero**: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.

### <a name="fiscal"></a>Fiscale

Se si seleziona **Fiscale** nel campo **Anno di ammortamento**, l'ammortamento a saldi decrescenti del 175% viene calcolato in base all'anno fiscale del calendario fiscale specificato per il libro oppure del calendario fiscale selezionato nella pagina **Contabilità generale**. I calendari fiscali vengono impostati nella pagina **Calendari fiscali**. Per ulteriori informazioni, vedere [Calendari fiscali, anni fiscali e periodi](../budgeting/fiscal-calendars-fiscal-years-periods.md).

Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio. La durata dell'anno fiscale non deve essere necessariamente di 12 mesi. L'ammortamento viene rettificato automaticamente per ciascun periodo e la durata dell'anno fiscale successivo dipende dall'impostazione dei periodi nella pagina **Calendari fiscali**. 

Se si seleziona **Fiscale** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:

-   **Annuale**: l'importo totale dell'ammortamento calcolato per l'anno fiscale viene registrato come importo unico nell'ultimo giorno dell'anno fiscale.
-   **Periodo fiscale**: calcola l'importo totale dell'ammortamento per l'anno fiscale. Questo importo viene attribuito ai periodi fiscali definiti nella pagina **Calendari fiscali**.

## <a name="example-of-175-reducing-balance-depreciation"></a>Esempio di ammortamento a saldi decrescenti del 175%

|                                |        |
|--------------------------------|--------|
| Costo di acquisizione               | 11.000 |
| Valore di realizzo                  | 1.000  |
| Base di ammortamento              | 10.000 |
| Anni vita utile             | 5      |
| Percentuale di ammortamento annuale | 35%    |

Il metodo di ammortamento a saldi decrescenti del 175% divide il 175% per gli anni di vita utile. Tale percentuale verrà moltiplicata per il valore contabile netto del cespite al fine di determinare l'importo dell'ammortamento per l'anno.

| Periodo | Calcolo della quota di ammortamento annuale | Valore contabile                  | Valore contabile netto alla fine dell'anno |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| Anno 1 | (11.000 – 1.000) × 35% = 3.500                | 11.000 – 3.500 = 7.500      | 11.000 – 1.000 – 3.500 = 6.500        |
| Anno 2 | 6.500 × 35% = 2.275                           | 7.500 – 2.275 = 5.225       | 6.500 – 2.275 = 4.225                 |
| Anno 3 | 4.225 × 35% = 1.478,75                        | 5.225 – 1.478,75 = 3.746,25 | 4.225 – 1.478,75 = 2.746,25           |

> [!NOTE] 
> In genere, quando l'importo calcolato utilizzando il metodo di ammortamento a saldi decrescenti del 175% diventa inferiore all'importo che sarà calcolato utilizzando il metodo a quote costanti, si verifica una conversione al metodo a quote costanti per la vita utile rimanente.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]