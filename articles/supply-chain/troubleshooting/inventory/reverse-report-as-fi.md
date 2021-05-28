---
title: Lo storno del reporting come finito crea una transazione aperta imprevista
description: Lo storno del reporting come finito con contrassegno crea una transazione aperta in cui la quantità stornata ha le stesse dimensioni inventariali della transazione stornata.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026655"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>Lo storno del reporting come finito crea una transazione aperta imprevista

Numero KB: 4612469

## <a name="symptoms"></a>Sintomi

Se storni il reporting come finito con contrassegno, i lsistema crea una transazione aperta in cui la quantità stornata ha le stesse dimensioni inventariali della transazione stornata.

## <a name="resolution"></a>Risoluzione

Quando storni un'operazione di report come finita, la dimensione inventariale viene inizializzata dal giornale di registrazione produzione. Pertanto, ottiene il numero batch. A causa del contrassegno, le transazioni dell'ordine cliente erediteranno il numero batch.

La dimensione può essere reimpostata quando il reporting viene registrato come finito.
