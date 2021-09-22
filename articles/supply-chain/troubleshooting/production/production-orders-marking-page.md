---
title: Gli ordini di produzione non vengono visualizzati nella pagina Contrassegno
description: Alcuni ordini di produzione non vengono visualizzati nella pagina Contrassegno. Questo argomento illustra le tre configurazioni del prodotto non disponibili per il contrassegno.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 87507e91d3feb2557e7ba771b8e34ff7ca105749
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476714"
---
# <a name="production-orders-arent-shown-on-the-marking-page"></a>Gli ordini di produzione non vengono visualizzati nella pagina Contrassegno

## <a name="symptoms"></a>Sintomi

Quando si lavora con una produzione discreta, alcuni ordini di produzione non vengono visualizzati nella pagina **Contrassegno**.

## <a name="resolution"></a>Risoluzione

I prodotti con le seguenti configurazioni non sono disponibili per il contrassegno. Pertanto, non verranno mostrati nella pagina **Contrassegno**:

- I prodotti sono definiti come prodotti di tipo *peso variabile*.
- Sono abilitati per i processi di magazzino avanzati.
- Sono configurati per essere controllati dal principio *Costo standard*.
