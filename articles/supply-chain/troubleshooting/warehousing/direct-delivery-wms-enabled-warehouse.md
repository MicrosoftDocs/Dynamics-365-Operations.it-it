---
title: Impossibile elaborare la consegna diretta per il magazzino abilitato per WMS
description: Se il magazzino ha WMS abilitato, non supporta la consegna diretta. Per utilizzare la consegna diretta, è necessario selezionare un articolo e un magazzino non WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 090e17091e9fb92c2065679bb9b04637214e2eea
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476820"
---
# <a name="direct-delivery-not-able-to-process-for-wms-enabled-warehouse"></a>Non è possibile elaborare la consegna diretta per il magazzino abilitato per WMS

## <a name="symptoms"></a>Sintomi

Se un articolo viene aggiunto a una riga di vendita per la consegna diretta da un magazzino abilitato per la gestione del magazzino (WMS), viene visualizzato il seguente messaggio di errore quando la riga di vendita viene aggiornata:

> La consegna diretta non è in grado di elaborare per il magazzino 1% poiché la gestione magazzino è abilitata. Specificare un altro magazzino non abilitato per la gestione del magazzino.

## <a name="resolution"></a>Risoluzione

Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. Attualmente, WMS non supporta la consegna diretta. Pertanto, per utilizzare la consegna diretta, è necessario selezionare un articolo e un magazzino non WMS.
