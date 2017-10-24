---
title: Importo per l'arrotondamento dei calcoli di ammortamento
description: Questo articolo illustra il campo Arrotonda ammortamento presente nelle pagine Impostazione libro.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ae5c24633a9ce4ce43e213581eb64c8548eecf5d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="round-off-amount-for-depreciation-calculations"></a>Importo per l'arrotondamento dei calcoli di ammortamento

[!include[banner](../includes/banner.md)]


Questo articolo illustra il campo Arrotonda ammortamento presente nelle pagine Impostazione libro.

Gli importi di arrotondamento per l'ammortamento vengono impostati per ogni libro. Gli importi di arrotondamento per l'ammortamento vengono utilizzati nel profilo di ammortamento cespiti che mostra l'ammortamento e il valore futuri del cespite e anche nelle proposte di ammortamento. Immettere l'importo minimo dell'ammortamento consentito per il libro. 

Indipendentemente dall'arrotondamento che viene impostato, l'importo di ammortamento nell'ultimo periodo di ammortamento non viene arrotondato. Alla fine dell'ultimo periodo di ammortamento, il valore del cespite deve essere 0 (zero) o il valore di scarto, se il valore di scarto viene utilizzato.

### <a name="example"></a>Esempio

L'ammortamento senza arrotondamento ammonta a 2.444,44. Come indicato nella tabella seguente, gli importi suggeriti variano a seconda del modo in cui l'arrotondamento viene impostato.

| Metodo di arrotondamento | Importo di ammortamento |
|-----------------|---------------------|
| Arrotondamento 0,1    | 2.444,40            |
| Arrotondamento 1,00   | 2.444,00            |
| Arrotondamento 10,00  | 2.440,00            |
| Arrotondamento 100,00 | 2.400,00            |






