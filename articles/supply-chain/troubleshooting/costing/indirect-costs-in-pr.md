---
title: Il report Costi indiretti in esecuzione include gli ordini di produzione eliminati
description: Il report Costi indiretti in esecuzione presenta informazioni sugli ordini di produzione che sono stati parzialmente elaborati e successivamente eliminati.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026644"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a><span data-ttu-id="ad0b8-103">Il report Costi indiretti in esecuzione include gli ordini di produzione eliminati</span><span class="sxs-lookup"><span data-stu-id="ad0b8-103">The Indirect costs in process report includes deleted production orders</span></span>

<span data-ttu-id="ad0b8-104">Numero KB: 4612748</span><span class="sxs-lookup"><span data-stu-id="ad0b8-104">KB number: 4612748</span></span>

## <a name="symptoms"></a><span data-ttu-id="ad0b8-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="ad0b8-105">Symptoms</span></span>

<span data-ttu-id="ad0b8-106">Il report **Costi indiretti in esecuzione** presenta informazioni sugli ordini di produzione che sono stati parzialmente elaborati e successivamente eliminati.</span><span class="sxs-lookup"><span data-stu-id="ad0b8-106">The **Indirect costs in process** report presents information about production orders that were partially processed and later deleted.</span></span>

## <a name="resolution"></a><span data-ttu-id="ad0b8-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="ad0b8-107">Resolution</span></span>

<span data-ttu-id="ad0b8-108">Quando storni un ordine di produzione, annulli anche tutte le transazioni di tale ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="ad0b8-108">When you reverse a production order, you also reverse all the transactions of that production order.</span></span> <span data-ttu-id="ad0b8-109">Quando elimini l'ordine di produzione, le tabelle del giornale di registrazione secondario e la contabilità generale mantengono tutte le transazioni ad esso correlate.</span><span class="sxs-lookup"><span data-stu-id="ad0b8-109">When you delete the production order, the subledger tables and general ledger persist all transactions that are related to it.</span></span> <span data-ttu-id="ad0b8-110">I report mostreranno le transazioni nelle tabelle del giornale di registrazione secondario.</span><span class="sxs-lookup"><span data-stu-id="ad0b8-110">The reports will show the transactions in the subledger tables.</span></span> <span data-ttu-id="ad0b8-111">Per l'ordine di produzione specifico, il valore netto dovrebbe essere 0,00.</span><span class="sxs-lookup"><span data-stu-id="ad0b8-111">For the specific production order, the net value should be 0.00.</span></span>
