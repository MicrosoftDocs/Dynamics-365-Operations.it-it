---
title: Ubicazione uscita produzione
description: Questo argomento descrive la gerarchia utilizzata per identificare l'ubicazione uscita produzione.
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e53c8e96579dba3b47bef0c00e55b8fa786fc55c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="production-output-location"></a>Ubicazione uscita produzione

[!include[banner](../includes/banner.md)]

Questo argomento descrive la gerarchia utilizzata per identificare l'ubicazione uscita produzione.

L'ubicazione uscita produzione è l'ubicazione in cui un prodotto viene immagazzinato dopo la produzione. In genere l'ubicazione si trova vicino al processo di produzione che realizza il prodotto finito. L'ubicazione uscita produzione viene utilizzata come magazzino intermedio per il materiale prima che venga spostato nell'area di spedizione, un'ubicazione di immagazzinamento, un'ubicazione entrata produzione per un processo di produzione a valle e così via. 

Un'ubicazione uscita produzione predefinita viene impostata quando i prodotti finiti vengono dichiarati in un ordine di produzione o un ordine batch. La gerarchia seguente viene utilizzata per identificare questa ubicazione uscita:

1. Utilizzare l'ubicazione uscita definita nell'intestazione dell'ordine di produzione o dell'ordine batch.
2. Se non è presente alcuna ubicazione, utilizzare l'ubicazione uscita definita nella risorsa utilizzata dall'ultima operazione definita nel ciclo di lavorazione produzione.
3. Se non è presente alcuna ubicazione, utilizzare l'ubicazione uscita definita nel gruppo di risorse utilizzato dalla risorsa per l'ultima operazione definita nel ciclo di lavorazione produzione.
4. Se non è presente alcuna ubicazione, utilizzare l'ubicazione uscita definita nel magazzino definito per l'ordine di produzione.

L'ubicazione uscita produzione predefinita viene impostata solo per i prodotti che vengono impostati utilizzando i processi di magazzino avanzati. Quando questo tipo di articolo viene dichiarato finito, viene creato il lavoro magazzino di tipo **Stoccaggio prodotti finiti** o **Stoccaggio co-prodotti e sottoprodotti**. Questo tipo di lavoro utilizza l'ubicazione uscita produzione come ubicazione di prelievo. L'ubicazione di stoccaggio è determinata dalle direttive ubicazione.

