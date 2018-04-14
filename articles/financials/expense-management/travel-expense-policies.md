---
title: Definire i criteri di spesa
description: "In Microsoft Dynamics 365 for Finance and Operations, è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 73e4fc7c1d0273c51be57d9c3ab04dbfbd839327
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="expense-policies"></a><span data-ttu-id="6b03d-103">Criteri di spesa</span><span class="sxs-lookup"><span data-stu-id="6b03d-103">Expense policies</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="6b03d-104">È possibile definire criteri che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.</span><span class="sxs-lookup"><span data-stu-id="6b03d-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="6b03d-105">L'implementazione di criteri di spesa consente di gestire le spese in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="6b03d-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="6b03d-106">È ad esempio possibile impostare un criterio per le spese di albergo a New York, secondo il quale non devono superare USD 250 a notte.</span><span class="sxs-lookup"><span data-stu-id="6b03d-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="6b03d-107">Se un lavoratore invia una nota spese o una richiesta di viaggio in cui il prezzo della camera supera questo importo, riceverà una notifica</span><span class="sxs-lookup"><span data-stu-id="6b03d-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="6b03d-108">in cui viene indicato che è stato superato l'importo previsto dal criterio per questo tipo di spesa.</span><span class="sxs-lookup"><span data-stu-id="6b03d-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="6b03d-109">È possibile configurare il messaggio che il lavoratore riceverà quando</span><span class="sxs-lookup"><span data-stu-id="6b03d-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="6b03d-110">si definiscono i criteri.</span><span class="sxs-lookup"><span data-stu-id="6b03d-110">define the policy.</span></span>      
        
<span data-ttu-id="6b03d-111">È possibile definire tre tipi di criteri:</span><span class="sxs-lookup"><span data-stu-id="6b03d-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="6b03d-112">Avviso: consente al lavoratore di inviare una nota spese o una richiesta di viaggio ma la spesa verrà contrassegnata per tutti gli approvatori e</span><span class="sxs-lookup"><span data-stu-id="6b03d-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="6b03d-113">per la dichiarazione successiva.</span><span class="sxs-lookup"><span data-stu-id="6b03d-113">for later reporting.</span></span>        

- <span data-ttu-id="6b03d-114">Errore: richiede al lavoratore di rivedere la spesa per conformarsi ai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="6b03d-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
  - <span data-ttu-id="6b03d-115">Motivazione: richiede al lavoratore o a un responsabile di immettere una motivazione per superare l'importo previsto dai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="6b03d-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        
 
  <span data-ttu-id="6b03d-116">È inoltre possibile impostare un intervallo di date per il quale sono validi i criteri di spesa.</span><span class="sxs-lookup"><span data-stu-id="6b03d-116">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="6b03d-117">Ad esempio, le tariffe aeree per i voli tra la Danimarca</span><span class="sxs-lookup"><span data-stu-id="6b03d-117">For example, airline fares for flights between Denmark</span></span>      
  <span data-ttu-id="6b03d-118">e New York possono essere costose durante il periodo di picco della stagione turistica.</span><span class="sxs-lookup"><span data-stu-id="6b03d-118">and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="6b03d-119">È possibile definire una regola per le spese aeree in modo da specificare un limite</span><span class="sxs-lookup"><span data-stu-id="6b03d-119">You can define a flight expense rule that restricts the</span></span>      
  <span data-ttu-id="6b03d-120">di DKK 5.000 per il costo dei voli diretti a New York e indicare che tale regola deve essere applicata nel periodo compreso tra il 15 marzo e</span><span class="sxs-lookup"><span data-stu-id="6b03d-120">cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and</span></span>      
  <span data-ttu-id="6b03d-121">il 15 settembre.</span><span class="sxs-lookup"><span data-stu-id="6b03d-121">September 15.</span></span>

