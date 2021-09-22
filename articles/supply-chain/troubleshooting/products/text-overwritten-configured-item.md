---
title: Testo sovrascritto quando l'articolo viene configurato nell'ordine cliente
description: Quando un prodotto è configurato in una riga dell'ordine cliente, il testo modificato viene sovrascritto con il testo standard. Modificare il testo dopo aver configurato la riga, non prima.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 20239b9b0eecb355274e909a8b8b39450e468c7e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476722"
---
# <a name="item-text-is-overwritten-when-a-product-is-configured-on-a-sales-order-line"></a>Il testo dell'articolo viene sovrascritto quando un prodotto viene configurato in una riga dell'ordine cliente

## <a name="symptoms"></a>Sintomi

Questo problema si verifica quando si crea una riga di ordine cliente per un articolo configurabile e quindi si modifica il testo dell'articolo. Quando si configura l'articolo e si seleziona /**OK/**, il testo viene sovrascritto con il testo standard.

## <a name="resolution"></a>Risoluzione

Questo comportamento è previsto. Il campo di testo include il nome della variante, che viene compilato solo dopo aver configurato la riga. Pertanto, è necessario modificare il testo dopo aver configurato la riga, non prima.
