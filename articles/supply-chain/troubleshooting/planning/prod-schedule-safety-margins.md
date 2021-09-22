---
title: La programmazione della produzione non considera i margini di sicurezza
description: La programmazione della produzione non considera i margini di sicurezza impostati sulla copertura dell'articolo per la fornitura con pegging
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
ms.openlocfilehash: 738296b7570ded0a4ee806e4445204a68e6a08c8
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476747"
---
# <a name="production-scheduling-doesnt-consider-the-safety-margins"></a>La programmazione della produzione non considera i margini di sicurezza

## <a name="symptoms"></a>Sintomi

La pianificazione generale considera i margini di sicurezza. Tuttavia, i margini di sicurezza vengono ignorati quando vengono pianificati gli ordini di produzione pianificati.

## <a name="resolution"></a>Risoluzione

I margini vengono considerati solo durante la pianificazione generale, non durante la pianificazione manuale. I margini sono progettati per fungere da cuscinetto durante la fase di pianificazione, per dare un certo "margine" al processo vero e proprio.

Per ottenere il risultato desiderato, è possibile rimuovere il margine. Il ciclo di lavorazione deve quindi essere aggiornato in modo che includa il tempo desiderato (ad esempio, come tempo di coda). Sia la pianificazione generale che la pianificazione manuale devono quindi produrre lo stesso risultato.
