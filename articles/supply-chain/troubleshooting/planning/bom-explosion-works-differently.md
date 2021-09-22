---
title: L'esplosione della distinta base si comporta in modo diverso per gli ordini di produzione consolidati e stimati
description: L'esplosione della distinta base si comporta in modo diverso per gli ordini di produzione consolidati e per gli ordini di produzione stimati per il lavoro creato manualmente
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 94d4b00ea30396923a61b2748cf1aaeedc0af8af
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476765"
---
# <a name="bom-explosion-behaves-differently-for-firmed-and-estimated-production-orders"></a>L'esplosione della distinta base si comporta in modo diverso per gli ordini di produzione consolidati e stimati

## <a name="symptoms"></a>Sintomi

Quando un ordine di produzione viene stabilizzato, gli articoli non vengono esplosi quando si esplode la distinta base (DBA). Tuttavia, quando si crea manualmente un ordine di lavoro e quindi si stima l'ordine di produzione, gli articoli vengono esplosi.

### <a name="resolution"></a>Risoluzione

L'esplosione che si verifica quando l'ordine di produzione viene stabilizzato punterà all'ordine pianificato, ma in questo caso non sembra che l'ordine pianificato sia attualmente confermato. Tuttavia, se l'ordine di produzione è stato stimato, l'esplosione viene attivata dall'ordine di produzione rilasciato in cui non esiste alcun ordine pianificato.
