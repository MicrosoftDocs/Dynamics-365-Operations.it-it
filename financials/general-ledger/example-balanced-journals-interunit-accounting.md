---
title: "Giornali di registrazione bilanciati per la contabilizzazione interunità"
description: "Questo articolo mostra in che modo un giornale di registrazione viene automaticamente bilanciato quando si seleziona una dimensione finanziaria di bilanciamento nella pagina Contabilità generale."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0909b64a77024d551af0dad2de985887cf6ff06d
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="balanced-journals-for-interunit-accounting"></a>Giornali di registrazione bilanciati per la contabilizzazione interunità

[!include[banner](../includes/banner.md)]


Questo articolo mostra in che modo un giornale di registrazione viene automaticamente bilanciato quando si seleziona una dimensione finanziaria di bilanciamento nella pagina Contabilità generale. 

Se la voce contabile non è in pareggio a livello dei valori di dimensione finanziaria, le voci contabili aggiuntive vengono create automaticamente per bilanciare la voce contabile. Queste voci contabili utilizzano i tipi di registrazione **Interunit di debito** e**Interunit di credito** nella pagina **Conti per transazioni automatiche** per determinare il conto principale. Ad esempio, la filiale, ovvero il secondo segmento del conto CoGe, è selezionato come dimensione finanziaria di compensazione e le seguenti voci contabili di circa per essere creato.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100,00 DR |
| 6100 – NY – OU\_249  | 100,00 DR |
| 2100 – MSP – OU\_256 | 200,00 CR |

In questo caso, i seguenti saldi sono determinati:

-   Per filiale MSP = 100,00 CR
-   Per filiale NY Dott = 100,00

Pertanto, le seguenti voci contabili vengono create automaticamente per bilanciare il giornale di registrazione a livello dei valori di dimensione finanziaria.

|                                   |           |
|-----------------------------------|-----------|
| (Interunità - Dare) – MSP – OU\_256 | 100,00 DR |
| (Interunità - Avere– NY – OU\_249 | 100,00 CR |






