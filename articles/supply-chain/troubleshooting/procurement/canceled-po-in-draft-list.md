---
title: Gli ordini fornitore annullati vengono visualizzati nell'elenco delle bozze nell'area di lavoro
description: Gli ordini fornitore annullati vengono visualizzati nell'elenco delle bozze nell'area di lavoro Preparazione ordini fornitore
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f1dc23cd7e5b4b99cb7a9440d7d4666d8396511f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476790"
---
# <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-workspace"></a>Gli ordini fornitore annullati vengono visualizzati nell'elenco delle bozze nell'area di lavoro

## <a name="symptoms"></a>Sintomi

Dopo aver annullato gli ordini fornitore che erano nello stato *Confermato*, gli ordini fornitore annullati vengono ancora visualizzati nell'elenco delle bozze di ordini fornitore nell'area di lavoro **Preparazione ordine fornitore**.

## <a name="resolution"></a>Risoluzione

Questo problema si verifica solo per gli ordini fornitore soggetti a gestione delle modifiche. Si verifica perché l'annullamento è considerato una modifica che deve essere approvata. L'approvazione può essere eseguita automaticamente dal sistema. Pertanto, il processo consiste nell'inviare l'ordine fornitore annullato al flusso di lavoro di approvazione in modo che possa passare allo stato *Approvato*. A quel punto, l'ordine fornitore non verrà più visualizzato nell'elenco delle bozze di ordini fornitore nell'area di lavoro **Preparazione ordine fornitore**.
