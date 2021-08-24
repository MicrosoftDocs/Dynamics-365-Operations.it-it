---
title: Riduzione del 200% dell'ammortamento del saldo
description: Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 200%.
author: saraschi2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f7d821dbd6603eba7a228e5caa6def6d783e4774c72687839bd198f4e228633
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767006"
---
# <a name="200-percent-reducing-balance-depreciation"></a>Riduzione del 200% dell'ammortamento del saldo

[!include [banner](../includes/banner.md)]

Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 200%.

Quando si imposta un profilo di ammortamento cespiti e si seleziona **Saldo decrescente 200%** nel campo **Metodo** della pagina **Profili di ammortamento**, ai cespiti che sono assegnati al profilo di ammortamento verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento. Questa percentuale viene calcolata in base alla vita utile del cespite. Ad esempio, se un cespite ha una vita utile di cinque anni, la percentuale viene calcolata come 40% (200% ÷ 5). 

Questo metodo è detto anche metodo a doppie quote proporzionali.

Per impostare l'ammortamento a saldi decrescenti del 200%, è inoltre necessario selezionare le opzioni presenti nel campo **Anno di ammortamento** e nel campo **Frequenza periodo** della pagina **Profili di ammortamento**. Le opzioni disponibili nel campo **Frequenza periodo** variano a seconda del valore selezionato in **Anno di ammortamento**.

## <a name="select-a-depreciation-year"></a>Selezionare un anno di ammortamento
È possibile selezionare **Calendario** o **Fiscale** nel campo **Anno di ammortamento** della pagina **Profili di ammortamento**. Il valore predefinito è **Calendario**. 

La selezione determina le opzioni disponibili nel campo **Frequenza periodo**. Il campo consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario.

### <a name="calendar"></a>Calendario

È possibile scegliere di mantenere il valore predefinito nel campo **Anno di ammortamento**, **Calendario**. 

L'opzione **Calendario** aggiorna la base di ammortamento il 1° gennaio di ogni anno. In genere, l'ammortamento corrisponde al valore contabile netto meno il valore di recupero. Negli esempi illustrati più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli. 

Se si seleziona **Calendario** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:

-   **Annuale**: viene registrato un importo il 31 dicembre.
-   **Mensile**: viene registrato un importo mensile alla fine di ciascun mese di calendario.
-   **Trimestrale**: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).
-   **Semestrale**: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).
-   **Giornaliero**: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.

### <a name="fiscal"></a>Fiscale

Se si seleziona **Fiscale** nel campo **Anno di ammortamento**, l'ammortamento a saldi decrescenti del 200% viene calcolato in base all'anno fiscale del calendario fiscale specificato per il libro oppure del calendario fiscale selezionato nella pagina **Contabilità generale**. I calendari fiscali vengono impostati nella pagina **Calendari fiscali**. 

Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio. La durata dell'anno fiscale non deve essere necessariamente di 12 mesi. L'ammortamento viene rettificato per ciascun periodo. La durata dell'anno fiscale successivo si baserà sull'impostazione dei periodi nella pagina **Calendari fiscali**. 

Se si seleziona **Fiscale** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:

-   L'opzione **Annuale** registra l'importo totale dell'ammortamento che viene calcolato per l'anno fiscale come importo unico nell'ultimo giorno dell'anno fiscale.
-   **Periodo fiscale** registra l'importo totale dell'ammortamento calcolato per l'anno fiscale. Questo importo viene attribuito ai periodi fiscali definiti nella pagina **Calendari fiscali**.

## <a name="example-of-200-reducing-balance-depreciation"></a>Esempio di ammortamento a saldi decrescenti del 200%

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| Costo di acquisizione               | 11.000 |
| Valore di realizzo                  | 1. 000 |
| Base di ammortamento              | 10.000 |
| Anni vita utile             | 5      |
| Percentuale di ammortamento annuale | 40%    |

Il metodo a saldi decrescenti del 200% consente di dividere il 200% per gli anni di vita utile. Tale percentuale verrà moltiplicata per il valore contabile netto del cespite al fine di determinare l'importo dell'ammortamento per l'anno.

| Periodo | Calcolo della quota di ammortamento annuale | Valore contabile             | Valore contabile netto alla fine dell'anno |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| Anno 1 | (11.000 – 1.000) × 40% = 4.000                | 11.000 – 4.000 = 7.000 | 11.000 – 1.000 – 4.000 = 6.000        |
| Anno 2 | 6.000 × 40% = 2.400                           | 7.000 – 2.400 = 4.600  | 6.000 – 2.400 = 3.600                 |
| Anno 3 | 3.600 × 40% = 1.440                           | 4.600 – 1.440 = 3.160  | 3.600 – 1.440 = 2.160                 |

> [!NOTE] 
> In genere, quando l'importo calcolato utilizzando il metodo di ammortamento a saldi decrescenti del 200% diventa inferiore all'importo che sarà calcolato utilizzando il metodo a quote costanti, si verifica una conversione al metodo a quote costanti per la vita utile rimanente.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]