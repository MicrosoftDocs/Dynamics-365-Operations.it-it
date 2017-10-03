---
title: Ordini batch consolidati
description: Questo articolo descrive il concetto degli ordini batch consolidati.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 45c83752b4dc50a615e3bb64320cb22b7fc6dec0
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017

---

# <a name="consolidated-batch-orders"></a>Ordini batch consolidati

[!include[banner](../includes/banner.md)]


Questo articolo descrive il concetto degli ordini batch consolidati.

Un articolo in blocco che viene prodotto viene considerato un elemento padre, mentre un articolo imballato viene considerato un articolo figlio. La relazione tra l'articolo in blocco e l'articolo imballato viene espressa in una conversione articolo in blocco. La conversione articolo in blocco è definita nell'articolo in blocco stesso.  

Gli articoli imballati possono essere confezionati in contenitori di uno o più formati che vengono considerati come un'unità. Quando vengono consolidati gli ordini per un articolo in blocco, è possibile vedere tutti gli ordini batch correlati in un'unica visualizzazione, agevolando così l'individuazione dell'eventuale lavoro rimanente da completare.  

Un ordine lotto consolidato può contenere qualsiasi combinazione dei seguenti ordini:

-   Un singolo ordine stoccaggio e più ordini articoli imballati
-   Più ordini stoccaggio e più ordini articoli imballati
-   Più ordini stoccaggio e un singolo ordine articoli imballati
-   Solo ordini articoli imballati





