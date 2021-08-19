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
ms.openlocfilehash: 73ebc45ee83516f573c3f73ef8106da9ae44c590c05d8dbd08520bc5ef19e49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714212"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>Lo storno del reporting come finito crea una transazione aperta imprevista

Numero KB: 4612469

## <a name="symptoms"></a>Sintomi

Se storni il reporting come finito con contrassegno, i lsistema crea una transazione aperta in cui la quantità stornata ha le stesse dimensioni inventariali della transazione stornata.

## <a name="resolution"></a>Risoluzione

Quando storni un'operazione di report come finita, la dimensione inventariale viene inizializzata dal giornale di registrazione produzione. Pertanto, ottiene il numero batch. A causa del contrassegno, le transazioni dell'ordine cliente erediteranno il numero batch.

La dimensione può essere reimpostata quando il reporting viene registrato come finito.
