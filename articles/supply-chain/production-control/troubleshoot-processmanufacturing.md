---
title: Risolvere i problemi di produzione processo
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza la produzione processo.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d999c91aa1cc14f29ebfa6be8e456e45ef0d3fa4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966182"
---
# <a name="troubleshoot-process-manufacturing"></a><span data-ttu-id="b34d2-103">Risolvere i problemi di produzione processo</span><span class="sxs-lookup"><span data-stu-id="b34d2-103">Troubleshoot process manufacturing</span></span>

<span data-ttu-id="b34d2-104">Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza la produzione processo.</span><span class="sxs-lookup"><span data-stu-id="b34d2-104">This topic describes how to fix issues that you might encounter while you work with process manufacturing.</span></span>

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a><span data-ttu-id="b34d2-105">Quando si utilizza il dispositivo scheda processo per dichiarare una quantità parziale sull'ultimo processo in un ordine di produzione, tutti i processi precedenti su quell'ordine che hanno lo stato In corso vengono automaticamente terminati.</span><span class="sxs-lookup"><span data-stu-id="b34d2-105">When I use the job card device to report a partial quantity on the last job in a production order, all the previous jobs on that order that have a status of In progress are automatically ended.</span></span>

<span data-ttu-id="b34d2-106">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="b34d2-106">This behavior is by design.</span></span> <span data-ttu-id="b34d2-107">Nella pagina **Impostazioni predefinite ordine di produzione**, nella scheda **Dichiarazione di finito**, c'è un'opzione denominata **Ciclo di lavorazione con contrassegno di fine**.</span><span class="sxs-lookup"><span data-stu-id="b34d2-107">On the **Production order defaults** page, on the **Report as finished** tab, there is an option that is named **End-mark route**.</span></span> <span data-ttu-id="b34d2-108">Se questo argomento è impostato su *Sì*, viene registrato un giornale di registrazione delle schede cicli di lavorazione quando un lavoratore utilizza il dispositivo scheda processo o il terminale scheda processo per dichiarare l'ultima operazione.</span><span class="sxs-lookup"><span data-stu-id="b34d2-108">If this topic is set to *Yes*, a route card journal is posted when a worker uses the job card device or job card terminal to report the last operation.</span></span> <span data-ttu-id="b34d2-109">Questo giornale contrassegna tutte le operazioni come completate e termina tutti i processi di produzione.</span><span class="sxs-lookup"><span data-stu-id="b34d2-109">This journal marks all the operations as completed and ends all the production jobs.</span></span> <span data-ttu-id="b34d2-110">Quando l'opzione **Ciclo di lavorazione con contrassegno di fine** è impostata su *Sì*, il sistema non considera lo stato del processo che il lavoratore ha selezionato quando ha dichiarato l'ultima operazione.</span><span class="sxs-lookup"><span data-stu-id="b34d2-110">When the **End-mark route** option is set to *Yes*, the system doesn't consider the job status that the worker selected when they reported the last operation.</span></span> <span data-ttu-id="b34d2-111">Il sistema inoltre non considera se il lavoratore sta dichiarando una quantità totale o parziale.</span><span class="sxs-lookup"><span data-stu-id="b34d2-111">The system also doesn't consider whether the worker is reporting a full or partial quantity.</span></span>

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a><span data-ttu-id="b34d2-112">Quando si tenta di chiudere uno stock viene visualizzato il seguente messaggio di avviso: "Nessuna esecuzione del calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo è stata registrata."</span><span class="sxs-lookup"><span data-stu-id="b34d2-112">When I attempt a stock closing, I receive the following warning message: "No execution of Backflush costing calculation with a date %1 matching period end has been registered."</span></span>

<span data-ttu-id="b34d2-113">Nelle versioni precedenti alla versione 10.0.13, se non si utilizza il flusso di determinazione dei costi di produzione snella, viene visualizzato il seguente messaggio di avviso errato durante la chiusura dell'inventario:</span><span class="sxs-lookup"><span data-stu-id="b34d2-113">In releases before release 10.0.13, if you aren't using the lean production costing flow, you receive the following erroneous warning message during inventory closing:</span></span>

> <span data-ttu-id="b34d2-114">Si sta per eseguire una chiusura dell'inventario con data %1.</span><span class="sxs-lookup"><span data-stu-id="b34d2-114">You are about to execute an Inventory close with a date %1.</span></span> <span data-ttu-id="b34d2-115">Nessuna esecuzione del calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo è stata registrata.</span><span class="sxs-lookup"><span data-stu-id="b34d2-115">No execution of Backflush costing calculation with a date %1 matching period end has been registered.</span></span> <span data-ttu-id="b34d2-116">Eseguire il calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo.</span><span class="sxs-lookup"><span data-stu-id="b34d2-116">Please remember to execute a Backflush costing calculation with a date of %1 matching period end.</span></span> <span data-ttu-id="b34d2-117">La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="b34d2-117">The valuation of inventories, cost of goods sold and variances might not be correct in Subledger or General ledger until this has been executed.</span></span>

<span data-ttu-id="b34d2-118">Questo problema è stato risolto nella versione 10.0.13 e successive.</span><span class="sxs-lookup"><span data-stu-id="b34d2-118">This issue has been fixed in release 10.0.13 and later.</span></span> <span data-ttu-id="b34d2-119">Per ulteriori informazioni, vedere [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span><span class="sxs-lookup"><span data-stu-id="b34d2-119">For more information, see [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span></span>
