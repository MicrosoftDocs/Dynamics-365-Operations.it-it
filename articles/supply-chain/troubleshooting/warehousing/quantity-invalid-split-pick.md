---
title: Quantità non valida per l' unità %1 quando si esegue un prelievo condiviso
description: Quando si esegue un prelievo condiviso in più batch, è possibile che venga visualizzato un errore che indica che la quantità non è valida per l'unità %1. Questa pagina aiuta a risolvere il problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4627db7400d6ccd81f25f100de4696058ce35c42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476725"
---
# <a name="quantity-is-not-valid-when-performing-a-split-pick-across-multiple-batches"></a>La quantità non è valida quando si esegue un prelievo condiviso in più batch

## <a name="symptoms"></a>Sintomi

Quando si tenta di eseguire un *prelievo condiviso* in più batch, si riceve il messaggio di errore seguente:

> Quantità non valida per l'unità %1.

## <a name="resolution"></a>Risoluzione

Il magazziniere deve utilizzare il processo di *prelievo breve* nell'app per dispositivi mobili Warehouse Management. Se tenti di prelevare più batch dalla stessa ubicazione, puoi anche utilizzare l'opzione **Completo** nell'app per dispositivi mobili Gestione magazzino.
