---
title: Definire i criteri di spesa
description: "In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio."
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 9a5ce1a3b6519b510c9f5aa5618ab91f77a2d91a
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="expense-policies"></a><span data-ttu-id="e101c-103">Criteri di spesa</span><span class="sxs-lookup"><span data-stu-id="e101c-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e101c-104">È possibile definire criteri che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.</span><span class="sxs-lookup"><span data-stu-id="e101c-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span> <span data-ttu-id="e101c-105">L'implementazione di criteri di spesa consente di gestire le spese in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="e101c-105">Implementing expense policies can help you manage expenses effectively.</span></span> 

<span data-ttu-id="e101c-106">È ad esempio possibile impostare un criterio per le spese di albergo a New York, secondo il quale non devono superare USD 250 a notte.</span><span class="sxs-lookup"><span data-stu-id="e101c-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span> <span data-ttu-id="e101c-107">Se un lavoratore invia una nota spese o una richiesta di viaggio in cui la tariffa per la stanza d'albergo supera quell'importo, il lavoratore riceverà una notifica in cui viene indicato che l'importo previsto dal criterio per questo tipo di spesa è stato superato.</span><span class="sxs-lookup"><span data-stu-id="e101c-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="e101c-108">È possibile configurare il messaggio che il lavoratore riceverà quando si definiscono i criteri.</span><span class="sxs-lookup"><span data-stu-id="e101c-108">You can configure the message that the worker will receive when you define the policy.</span></span> 

<span data-ttu-id="e101c-109">È possibile definire tre tipi di criteri:</span><span class="sxs-lookup"><span data-stu-id="e101c-109">You can define three types of policies:</span></span> 

 - <span data-ttu-id="e101c-110">Avviso: consente al lavoratore di inviare una nota spese o una richiesta di viaggio ma la spesa verrà contrassegnata per tutti gli approvatori e</span><span class="sxs-lookup"><span data-stu-id="e101c-110">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>  
 <span data-ttu-id="e101c-111">per la dichiarazione successiva.</span><span class="sxs-lookup"><span data-stu-id="e101c-111">for later reporting.</span></span> 
 - <span data-ttu-id="e101c-112">Errore: richiede al lavoratore di rivedere la spesa per conformarsi ai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="e101c-112">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span> 
 - <span data-ttu-id="e101c-113">Motivazione: richiede al lavoratore o a un responsabile di immettere una motivazione per superare l'importo previsto dai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="e101c-113">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span> 

<span data-ttu-id="e101c-114">È inoltre possibile impostare un intervallo di date per il quale sono validi i criteri di spesa.</span><span class="sxs-lookup"><span data-stu-id="e101c-114">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="e101c-115">Le tariffe aeree per i voli tra la Danimarca e New York ad esempio possono essere costose durante il periodo di picco della stagione turistica.</span><span class="sxs-lookup"><span data-stu-id="e101c-115">For example, airline fares for flights between Denmark and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="e101c-116">È possibile definire una regola per le spese aeree in modo da specificare un limite di DKK 5.000 per il costo dei voli diretti a New York e indicare che tale regola deve essere applicata nel periodo compreso tra il 15 marzo e il 15 settembre.</span><span class="sxs-lookup"><span data-stu-id="e101c-116">You can define a flight expense rule that restricts the cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and September 15.</span></span> 

