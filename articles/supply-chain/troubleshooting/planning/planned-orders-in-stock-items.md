---
title: Gli ordini pianificati vengono generati per le scorte in magazzino con ordini di produzione
description: Gli ordini pianificati vengono generati anche se sono presenti articoli in magazzino e per essi esistono già ordini di produzione.
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
ms.openlocfilehash: aa803bcd7d43aa36675596050ccbe06831f1724d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476817"
---
# <a name="planned-orders-are-generated-for-in-stock-with-production-orders"></a>Gli ordini pianificati vengono generati per le scorte in magazzino con ordini di produzione

## <a name="symptoms"></a>Sintomi

Gli ordini pianificati vengono generati anche se sono presenti articoli in magazzino e per essi esistono già ordini di produzione.

## <a name="resolution"></a>Risoluzione

È possibile risolvere questo problema aumentando il valore **Giorni positivi** per i gruppi rilevanti nella pagina **Gruppo di copertura**. Questa modifica farà sì che il sistema determini se le scorte disponibili possono essere utilizzate per la domanda. Quindi non verrà generato un nuovo ordine pianificato per gli articoli disponibili.
