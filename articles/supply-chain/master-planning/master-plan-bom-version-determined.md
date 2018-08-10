---
title: Determinare la versione DBA
description: "Durante un'esplosione della domanda, se per un articolo è impostato il tipo di ordine predefinito Produzione, il motore di pianificazione identifica una versione DBA valida in base al sito,"
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7e6745a52138e545b557fa1aa286cd49481b2ecd
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="determine-the-bom-version"></a>Determinare la versione DBA

[!include [banner](../includes/banner.md)]

Durante un'esplosione della domanda, se per un articolo è impostato il tipo di ordine predefinito Produzione, il motore di pianificazione identifica una versione DBA valida in base al sito, 

La dimensione sito è sempre nota ed è indicata nella transazione della domanda. Di seguito è illustrato il processo in base al quale viene determinata la versione DBA da utilizzare:

-   Se nel sito della domanda è definita una versione DBA per l'articolo, verrà utilizzata la DBA specifica del sito.
-   Se invece per l'articolo non è definita una versione DBA specifica del sito, verrà utilizzata una DBA generale, ovvero una DBA valida per più siti. Se presente, verrà utilizzata la DBA generale.
-   Se non è presente una versione DBA da utilizzare, l'esplosione della domanda verrà interrotta in questo punto.

Una versione DBA valida, generale o specifica di un sito, deve soddisfare i criteri relativi alla data e alla quantità.






