---
title: La pianificazione generale programma più della capacità disponibile
description: La pianificazione generale non sembra rispettare i limiti di capacità e sta pianificando più della capacità disponibile
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
ms.openlocfilehash: 48b3d179bb923ff6f6cc5b6be291408b3eb34d98
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476782"
---
# <a name="master-planning-is-scheduling-more-than-the-available-capacity"></a>La pianificazione generale programma più della capacità disponibile

## <a name="symptoms"></a>Sintomi

La pianificazione generale non sembra rispettare i limiti di capacità e sta pianificando più della capacità disponibile.

Quando si utilizza la pianificazione delle operazioni in cui è presente una capacità finita e dove il ciclo di lavorazione specifica una combinazione di requisiti sia per un gruppo di risorse che per le singole risorse, esiste una piccola possibilità di prenotazioni in eccesso a causa del modo in cui l'algoritmo convalida i conflitti di capacità. Questo prenotazione in eccesso può verificarsi quando si utilizzano helper per eseguire la pianificazione generale. È molto probabile che si verifichi se sono presenti molti processi che hanno un tempo di esecuzione relativamente breve.

## <a name="resolution"></a>Risoluzione

Se è essenziale che non si verifichi la prenotazione in eccesso per la pianificazione delle operazioni, è possibile rendere la pianificazione parte della pianificazione generale a thread singolo attivando l'opzione **Capacità finita accurata per la pianificazione delle operazioni** nella pagina **Parametri di pianificazione generale**. Questa opzione non è disponibile per impostazione predefinita. È necessario aggiungerla manualmente alla pagina utilizzando le funzionalità di personalizzazione. Quando si utilizza questa opzione, la pianificazione verrà eseguita più lentamente a causa della mancanza di elaborazione parallela.
