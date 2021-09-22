---
title: Il valore di ritardo non viene aggiornato quando si riprogramma un ordine pianificato
description: Il valore di ritardo non viene aggiornato quando si riprogramma un ordine pianificato
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
ms.openlocfilehash: 566702913774cf002ab38e367f690a479d968657
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476791"
---
# <a name="the-delay-value-isnt-updated-when-you-reschedule-a-planned-order"></a>Il valore di ritardo non viene aggiornato quando si riprogramma un ordine pianificato

## <a name="symptoms"></a>Sintomi

Il valore di ritardo non viene aggiornato quando si riprogramma un ordine pianificato.

## <a name="resolution"></a>Risoluzione

Per aggiornare il ritardo per gli ordini pianificati, aprire la finestra di dialoto **Riprogrammazione** per l'ordine pianificato. Nella Scheda dettaglio **Esplosione**, assicurarsi che l'opzione **Esegui esplosione dopo la riprogrammazione** sia impostata su *Sì*.
