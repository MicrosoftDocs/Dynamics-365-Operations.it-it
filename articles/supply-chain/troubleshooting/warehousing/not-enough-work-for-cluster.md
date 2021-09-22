---
title: Non è stato trovato lavoro sufficiente per il cluster dopo la configurazione del profilo
description: Se si configura un profilo cluster, si può ricevere un messaggio di errore che indica che non è stato trovato lavoro sufficiente. Modificare il profilo e impostare Attiva posizioni su No.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 139fd72e571c8ef83af2fd0e497cf334b6ef0ea4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476734"
---
# <a name="not-enough-work-found-for-cluster-when-using-system-directed-cluster-picking"></a>Non è stato trovato lavoro sufficiente per il cluster quando si utilizza un prelievo cluster diretto dal sistema

## <a name="symptoms"></a>Sintomi

Quando si usa il processo *Prelievo cluster diretto dal sistema*, se si configura un profilo cluster in cui, ad esempio, è possibile selezionare 10 posizioni, il processo funziona come pianificato quando c'è abbastanza lavoro per selezionare 10 posizioni. Tuttavia, se sono presenti solo otto posizioni da selezionare, viene visualizzato il seguente messaggio di errore:

> Impossibile trovare lavoro sufficiente per il cluster.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, modificare il profilo del cluster e impostare l'opzione **Attiva posizioni** su *No*.
