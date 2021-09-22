---
title: L'ubicazione della dimensione non può essere vuota se è impostato il numero di serie
description: Se si riceve questo errore quando si conferma una spedizione dopo aver creato un ordine di trasferimento per un articolo di serie, il campo Ubicazione predefinita entrata è vuoto.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6f58c72438d5d1d93e59e46525debd65d44d9a76
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476804"
---
# <a name="error-when-confirming-shipment-after-creating-a-transfer-order-for-a-serial-item"></a>Errore durante la conferma della spedizione dopo aver creato un ordine di trasferimento per un articolo seriale

## <a name="symptoms"></a>Sintomi

Se si crea un ordine di trasferimento per un articolo con numero di serie utilizzando un magazzino abilitato per la gestione avanzata del magazzino (WMS) e, dopo il completamento del lavoro, si tenta di confermare la spedizione, viene visualizzato il seguente messaggio di errore:

> L'ubicazione della dimensione non può essere lasciata vuota se è impostato il numero di serie.

## <a name="cause"></a>Causa

Ciò si verifica perché il campo **Ubicazione predefinita entrata** è vuoto per un magazzino di transito del magazzino di provenienza.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, specificare un'ubicazione di ricevimento predefinita nel magazzino di transito. Assicurarsi che questa ubicazione sia controllata dalla targa.
