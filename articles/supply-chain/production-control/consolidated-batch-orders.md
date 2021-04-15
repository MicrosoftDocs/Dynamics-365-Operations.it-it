---
title: Ordini batch consolidati
description: Questo articolo descrive il concetto degli ordini batch consolidati.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8d7656889b69cfd1dcffb45b52eb649bce59629
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809232"
---
# <a name="consolidated-batch-orders"></a>Ordini batch consolidati

[!include [banner](../includes/banner.md)]

Questo articolo descrive il concetto degli ordini batch consolidati.

Un articolo in blocco che viene prodotto viene considerato un elemento padre, mentre un articolo imballato viene considerato un articolo figlio. La relazione tra l'articolo in blocco e l'articolo imballato viene espressa in una conversione articolo in blocco. La conversione articolo in blocco è definita nell'articolo in blocco stesso.  

Gli articoli imballati possono essere confezionati in contenitori di uno o più formati che vengono considerati come un'unità. Quando vengono consolidati gli ordini per un articolo in blocco, è possibile vedere tutti gli ordini batch correlati in un'unica visualizzazione, agevolando così l'individuazione dell'eventuale lavoro rimanente da completare.  

Un ordine lotto consolidato può contenere qualsiasi combinazione dei seguenti ordini:

-   Un singolo ordine stoccaggio e più ordini articoli imballati
-   Più ordini stoccaggio e più ordini articoli imballati
-   Più ordini stoccaggio e un singolo ordine articoli imballati
-   Solo ordini articoli imballati






[!INCLUDE[footer-include](../../includes/footer-banner.md)]