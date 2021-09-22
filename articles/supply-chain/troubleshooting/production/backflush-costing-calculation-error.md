---
title: Errore di calcolo di determinazione costi di tipo backflush durante la chiusura dell'inventario
description: Nelle versioni precedenti, era possibile ricevere un errore di calcolo di determinazione costi di tipo backflush durante la chiusura dell'inventario. Questo problema è stato risolto.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ae92b7121998d6b1ba2f08ea5736c55637867fbf
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476753"
---
# <a name="backflush-costing-calculation-error-during-inventory-closing"></a>Errore di calcolo di determinazione costi di tipo backflush durante la chiusura dell'inventario

## <a name="symptoms"></a>Sintomi

Nelle versioni precedenti alla versione 10.0.13, se non si utilizza il flusso di determinazione dei costi di produzione snella, viene visualizzato il seguente messaggio di avviso errato durante la chiusura dell'inventario:

> Si sta per eseguire una chiusura dell'inventario con data %1. Nessuna esecuzione del calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo è stata registrata. Eseguire il calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo. La valutazione degli inventari, del costo del venduto e degli scostamenti potrebbe non essere corretta nella contabilità generale secondaria o nella contabilità generale fino a quando non viene eseguito.

## <a name="resolution"></a>Risoluzione

Questo problema è stato risolto nella versione 10.0.13 e successive. Per ulteriori informazioni, vedere [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
