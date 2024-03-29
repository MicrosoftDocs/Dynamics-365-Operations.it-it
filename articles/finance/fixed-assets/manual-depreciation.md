---
title: Ammortamento manuale
description: Questo articolo fornisce una panoramica del metodo di ammortamento manuale.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: kfend
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3545b863f14ac9553563caa9b6e57443ea378536
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "8723197"
---
# <a name="manual-depreciation"></a>Ammortamento manuale

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica del metodo di ammortamento manuale.

Quando si imposta un profilo di ammortamento cespiti e si seleziona **Manuale** nel campo **Metodo** della pagina **Profili di ammortamento**, l'ammortamento dei cespiti assegnati a questo profilo viene determinato dalla percentuale immessa per ciascun intervallo nell'anno di calendario. Gli intervalli per cui si impostano percentuali vengono registrati in base al valore selezionato nel campo **Frequenza periodo** della scheda dettaglio **Generale** nella pagina **Profili di ammortamento**. È possibile selezionare i seguenti valori:

- Annuale
- Mensile
- Trimestrale
- Semestrale
- Giornaliero

Dopo che si seleziona la frequenza del periodo, fare clic su **Programmi manuali** e impostare le percentuali per ciascun intervallo. I programmi manuali e gli intervalli di registrazione consentono di definire la quota di ammortamento, come illustrato negli esempi più avanti in questo argomento. L'ammortamento manuale viene sempre calcolato come una percentuale del prezzo di acquisizione. Con l'ammortamento manuale, non è necessario che il totale delle percentuali immesse negli intervalli dell'ammortamento ammonti al 100%. Ammortamento manuale è un metodo di ammortamento flessibile spesso utilizzato per definire un profilo di ammortamento straordinario nella pagina **Libri**, quale un ammortamento non periodico per scopi speciali (ad esempio fiscali).

## <a name="examples"></a>Esempi
Prezzo di acquisizione: 11.000,00 Valore di scarto atteso: 1.000,00 Nella seguente tabella vengono visualizzati gli intervalli e le percentuali impostati **Programmazioni profilo di ammortamento cespiti** nella pagina.

| Numero intervallo | Percentuale |
|-----------------|------------|
| 1               | 10,00      |
| 2               | 50,00      |
| 3               | 8,00       |

L'ammortamento per periodo viene calcolato come illustrato nella seguente tabella.

|  Numero intervallo | Calcolo della quota di ammortamento annuale | Valore contabile netto alla fine dell'intervallo |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11.000 – 1.000) × 10% = 1.000                | 10.000 (11.000 – 1.000)                   |
| 2                | (11.000 – 1.000) × 50% = 5.000                | 5.000 (10.000 – 5.000)                    |
| 3                | (11.000 – 1.000) × 8% = 800                   | 4.200 (5.000 – 800)                       |

Se si seleziona **Mensile** nel campo **Frequenza periodo**, vengono impostati 12 intervalli di programmi manuali. Le quote di ammortamento per i primi due intervalli sono mostrate nella seguente tabella.

| Intervallo | Importo di ammortamento            |
|----------|--------------------------------|
| gennaio  | (11.000 – 1.000) × 10% = 1.000 |
| febbraio | (11.000 – 1.000) × 50% = 5.000 |

Se si seleziona <strong>Semestrale</strong> nel campo *<strong><em>Frequenza periodo</em>*</strong>, si configurano due intervalli di programmazione manuale. Le quote di ammortamento per i primi due intervalli sono mostrate nella seguente tabella.

| Intervallo    | Importo di ammortamento            |
|-------------|--------------------------------|
| 30 giugno     | (11.000 – 1.000) × 10% = 1.000 |
| 31 dicembre | (11.000 – 1.000) × 50% = 5.000 |

Non è necessario che il totale delle percentuali per tutti gli intervalli ammonti a 100. Tuttavia, verrà visualizzato un messaggio se il valore nel campo **Percentuale cumulativa** della pagina **Programmi profili di ammortamento cespiti** non è **100**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
