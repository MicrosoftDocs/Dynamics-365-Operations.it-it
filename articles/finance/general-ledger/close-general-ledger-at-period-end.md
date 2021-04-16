---
title: Chiudere la contabilità generale a fine periodo
description: In questo argomento vengono descritte le attività che vengono completate in genere quando si esegue una chiusura periodo per la contabilità generale.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9781a439469b54e5449382fbdd04447a7f4a079
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821915"
---
# <a name="close-the-general-ledger-at-period-end"></a><span data-ttu-id="c1821-103">Chiudere la contabilità generale a fine periodo</span><span class="sxs-lookup"><span data-stu-id="c1821-103">Close the general ledger at period end</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1821-104">In questo argomento vengono descritte le attività che vengono completate in genere quando si esegue una chiusura periodo per la contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="c1821-104">This topic describes the tasks that are typically completed when performing a period closing for General ledger.</span></span> 

<span data-ttu-id="c1821-105">In Contabilità generale, è possibile completare le procedure di chiusura per un periodo di tempo o un anno.</span><span class="sxs-lookup"><span data-stu-id="c1821-105">In General ledger, you can complete closing procedures for a period or a year.</span></span> <span data-ttu-id="c1821-106">La chiusura di processi consente di preparare il sistema per nuovo periodo.</span><span class="sxs-lookup"><span data-stu-id="c1821-106">Closing processes prepare the system for a new period.</span></span> <span data-ttu-id="c1821-107">Per preparare il sistema per un nuovo anno, è necessario eseguire il processo di chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c1821-107">To prepare the system for a new year, you must run the year end close process.</span></span> <span data-ttu-id="c1821-108">Ogni organizzazione ha processi e passaggi diversi che esegue per la fine di un periodo.</span><span class="sxs-lookup"><span data-stu-id="c1821-108">Each organization has different processes and steps that it performs for the end of a period.</span></span> <span data-ttu-id="c1821-109">Di seguito sono riportati alcuni passaggi facoltativi per la fine del periodo:</span><span class="sxs-lookup"><span data-stu-id="c1821-109">Here are some optional steps for period ends:</span></span>

-   <span data-ttu-id="c1821-110">Completare tutte le attività per tutti gli altri moduli, ad esempio Contabilità clienti, Contabilità fornitori e Inventario.</span><span class="sxs-lookup"><span data-stu-id="c1821-110">Complete all the tasks for all other modules, such as Accounts receivable, Accounts payable, and Inventory.</span></span>
-   <span data-ttu-id="c1821-111">Verificare che tutte i giornali di registrazione siano stati registrati.</span><span class="sxs-lookup"><span data-stu-id="c1821-111">Verify that all journals are posted.</span></span>
-   <span data-ttu-id="c1821-112">Eseguire la rivalutazione valuta estera per generare tutti gli eventuali importi di perdite o profitti non realizzati.</span><span class="sxs-lookup"><span data-stu-id="c1821-112">Run foreign currency revaluation to generate any unrealized gain or loss amounts.</span></span>
-   <span data-ttu-id="c1821-113">Liquidare le transazioni per ogni conto CoGe.</span><span class="sxs-lookup"><span data-stu-id="c1821-113">Settle transactions for each ledger account.</span></span>
-   <span data-ttu-id="c1821-114">Elaborare le eventuali allocazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="c1821-114">Process any required allocations.</span></span>
-   <span data-ttu-id="c1821-115">Registrare manualmente le rettifiche di fine periodo.</span><span class="sxs-lookup"><span data-stu-id="c1821-115">Manually post period-end adjustments.</span></span>
-   <span data-ttu-id="c1821-116">Inserire transazioni nel giornale di registrazione e revisionare il report **Giornale di registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="c1821-116">Journalize transactions, and review the **Ledger journal** report.</span></span>
-   <span data-ttu-id="c1821-117">Eseguire un consolidamento utilizzando una società di consolidamento o report finanziari.</span><span class="sxs-lookup"><span data-stu-id="c1821-117">Perform a consolidation by using a consolidation company or Financial reporting.</span></span>
-   <span data-ttu-id="c1821-118">Generare rendiconti finanziari di fine periodo utilizzando i report finanziari.</span><span class="sxs-lookup"><span data-stu-id="c1821-118">Generate period-end financial statements by using Financial reporting.</span></span>
-   <span data-ttu-id="c1821-119">Impostare i periodi contabili su **In attesa** in modo che non vengano eseguite ulteriori registrazioni.</span><span class="sxs-lookup"><span data-stu-id="c1821-119">Set ledger periods to **On hold**, so that no further posting occurs.</span></span> <span data-ttu-id="c1821-120">Per un maggiore controllo, è inoltre possibile limitare un periodo a un gruppo di utenti specifico durante l'esecuzione delle attività di fine periodo.</span><span class="sxs-lookup"><span data-stu-id="c1821-120">You can also restrict a period to a specific user group while period-end activities are occurring, for better control.</span></span> <span data-ttu-id="c1821-121">Non è consigliabile impostare i periodi su **Chiuso in modo permanente** poiché non è possibile riaprire un periodo che è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="c1821-121">It's not a good idea to set periods to **Permanently closed**, because you can't reopen a period that has been closed.</span></span>

<span data-ttu-id="c1821-122">L'area di lavoro Chiusura periodo finanziario può essere utilizzata per organizzare e tenere traccia delle attività richieste per vari processi di fine periodo.</span><span class="sxs-lookup"><span data-stu-id="c1821-122">The Financial period close workspace can be used to organize and track the tasks required for various period end processes.</span></span> 


<span data-ttu-id="c1821-123">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1821-123">For more information, see the following topics for more information:</span></span>
- [<span data-ttu-id="c1821-124">Area di lavoro chiusura periodo finanziario</span><span class="sxs-lookup"><span data-stu-id="c1821-124">Financial period close workspace</span></span>](financial-period-close-workspace.md) 
- [<span data-ttu-id="c1821-125">Chiusura di fine anno</span><span class="sxs-lookup"><span data-stu-id="c1821-125">Year-end close</span></span>](Year-end-close.md)  
- [<span data-ttu-id="c1821-126">Chiusura in massa del periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="c1821-126">Mass financial period close</span></span>](tasks/mass-financial-period-close.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]