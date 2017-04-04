---
title: Importo per l&quot;arrotondamento dei calcoli di ammortamento
description: Questo articolo illustra il campo Arrotonda ammortamento presente nelle pagine Impostazione libro.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 0cb514dfb8c37b8c027ab895cb970af1b0135bf0
ms.lasthandoff: 03/31/2017


---

# <a name="round-off-amount-for-depreciation-calculations"></a>Importo per l'arrotondamento dei calcoli di ammortamento

Questo articolo illustra il campo Arrotonda ammortamento presente nelle pagine Impostazione libro.

Gli importi di arrotondamento di ammortamento vengono impostati per ciascun libro. Gli importi di arrotondamento di ammortamento vengono utilizzati nel profilo di ammortamento cespiti con l'ammortamento e il valore futuro del cespite nonché nelle proposte di ammortamento. Immettere l'importo minimo dell'ammortamento consentito per il libro. 

Indipendentemente dall'arrotondamento che viene impostato, l'importo di ammortamento nell'ultimo periodo di ammortamento non viene arrotondato. Alla fine dell'ultimo periodo di ammortamento, il valore del cespite deve essere 0 (zero) o il valore di scarto, se il valore di scarto viene utilizzato.

### <a name="example"></a>Esempio

L'ammortamento senza arrotondamento ammonta a 2.444,44. Come indicato nella tabella seguente, gli importi suggeriti variano a seconda del modo in cui l'arrotondamento viene impostato.

| Metodo di arrotondamento | Importo di ammortamento |
|-----------------|---------------------|
| Arrotondamento 0,1    | 2.444,40            |
| Arrotondamento 1,00   | 2.444,00            |
| Arrotondamento 10,00  | 2.440,00            |
| Arrotondamento 100,00 | 2.400,00            |




