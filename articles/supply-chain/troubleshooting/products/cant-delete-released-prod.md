---
title: Impossibile eliminare un prodotto rilasciato
description: È possibile eliminare un prodotto rilasciato e tutte le sue varianti solo se il prodotto rilasciato non ha transazioni correlate.
author: SmithaNataraj
ms.date: 06/11/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f03d45a36401314a4b02ff354fabb474568c48b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476800"
---
# <a name="you-cant-delete-a-released-product"></a>Impossibile eliminare un prodotto rilasciato

## <a name="symptoms"></a>Sintomi

È possibile eliminare un prodotto rilasciato e tutte le sue varianti solo se il prodotto rilasciato non ha transazioni correlate.

## <a name="resolution"></a>Risoluzione

Seguire questi passaggi per eliminare un prodotto rilasciato o una rappresentazione generale del prodotto.

1. Chiudere tutte le transazioni aperte per gli articoli.
1. Ridurre l'inventario a 0 (zero).
1. Eseguire la chiusura dell'inventario.
1. Eliminare tutte le varianti prodotto per la rappresentazione generale prodotto che si desidera eliminare.
