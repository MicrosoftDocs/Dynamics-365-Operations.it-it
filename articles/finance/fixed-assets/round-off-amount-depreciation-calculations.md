---
title: Importo per l'arrotondamento dei calcoli di ammortamento
description: Questo articolo illustra il campo Arrotonda ammortamento presente nelle pagine Impostazione libro.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a99a55e58294f765b606aaabb373cc3f72415ef4ed94c213ebc8cd58af6157ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719758"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Importo per l'arrotondamento dei calcoli di ammortamento

[!include [banner](../includes/banner.md)]

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







[!INCLUDE[footer-include](../../includes/footer-banner.md)]