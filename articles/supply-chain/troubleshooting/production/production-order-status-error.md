---
title: Errore durante la modifica dello stato da Dichiarato finito a Fine
description: È possibile che venga visualizzato un errore quando si modifica lo stato di un ordine di produzione da Dichiarato finito a Fine. Questa pagina spiega come risolvere il problema.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 744637f5cccffe44b85f77c1a9df2034012fac40
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476774"
---
# <a name="error-when-changing-status-of-production-order-from-reported-as-finished-to-end"></a>Errore durante la modifica dello stato dell'ordine di produzione da Dichiarato finito a Fine

## <a name="symptoms"></a>Sintomi

Quando lo stato di un ordine di produzione viene modificato da Dichiarato finito a Fine, vengono visualizzati i seguenti messaggi di errore:

> Conflitto di aggiornamento. Il costo standard non corrisponde al valore dell'inventario finanziario dopo l'aggiornamento.

> Si è verificato un errore critico nella funzione InventCostMovement.checkVariance.

## <a name="cause"></a>Causa

Questo problema si verifica perché i dati sottostanti sono stati modificati da un altro processo. Il processo proverà ad aggiornare i dati fino a cinque volte. Se il conflitto persiste dopo cinque tentativi, viene visualizzati uno dei messaggi elencati in precedenza.

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. Per contenere il problema, riprendere il processo batch. Deve finire l'esecuzione.

Se il processo batch non riesce in modo coerente dopo essere stato ripreso, verificare che la precisione di arrotondamento per la valuta predefinita della contabilità generale sia conforme all'arrotondamento applicato ai valori nella tabella InventSum. Se la precisione di arrotondamento è stata modificata in un valore non conforme, è probabile che sia necessario modificarla nuovamente in un valore conforme. Cercare **ModifiedDateTime**. In questo caso, il valore mostrerà in genere che la precisione di arrotondamento è stata modificata di recente.
