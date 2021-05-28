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
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a><span data-ttu-id="1afc7-103">Lo storno del reporting come finito crea una transazione aperta imprevista</span><span class="sxs-lookup"><span data-stu-id="1afc7-103">Reversal of reporting as finished creates an unexpected open transaction</span></span>

<span data-ttu-id="1afc7-104">Numero KB: 4612469</span><span class="sxs-lookup"><span data-stu-id="1afc7-104">KB number: 4612469</span></span>

## <a name="symptoms"></a><span data-ttu-id="1afc7-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="1afc7-105">Symptoms</span></span>

<span data-ttu-id="1afc7-106">Se storni il reporting come finito con contrassegno, i lsistema crea una transazione aperta in cui la quantità stornata ha le stesse dimensioni inventariali della transazione stornata.</span><span class="sxs-lookup"><span data-stu-id="1afc7-106">If you reverse reporting as finished that has marking, the system creates an open transaction where the reversed quantity has the same inventory dimensions as the transaction that was reversed.</span></span>

## <a name="resolution"></a><span data-ttu-id="1afc7-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1afc7-107">Resolution</span></span>

<span data-ttu-id="1afc7-108">Quando storni un'operazione di report come finita, la dimensione inventariale viene inizializzata dal giornale di registrazione produzione.</span><span class="sxs-lookup"><span data-stu-id="1afc7-108">When you reverse a report-as-finished operation, the inventory dimension is initialized from the production journal.</span></span> <span data-ttu-id="1afc7-109">Pertanto, ottiene il numero batch.</span><span class="sxs-lookup"><span data-stu-id="1afc7-109">Therefore, it gets the batch number.</span></span> <span data-ttu-id="1afc7-110">A causa del contrassegno, le transazioni dell'ordine cliente erediteranno il numero batch.</span><span class="sxs-lookup"><span data-stu-id="1afc7-110">Because of marking, the sales order transactions will inherit the batch number.</span></span>

<span data-ttu-id="1afc7-111">La dimensione può essere reimpostata quando il reporting viene registrato come finito.</span><span class="sxs-lookup"><span data-stu-id="1afc7-111">The dimension can be reset when the reporting as finished is posted.</span></span>
