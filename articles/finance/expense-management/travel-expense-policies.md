---
title: Definire i criteri di spesa
description: In Microsoft Dynamics 365 Finance è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389717"
---
# <a name="define-expense-policies"></a><span data-ttu-id="092e4-103">Definire i criteri di spesa</span><span class="sxs-lookup"><span data-stu-id="092e4-103">Define expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="092e4-104">È possibile definire criteri che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.</span><span class="sxs-lookup"><span data-stu-id="092e4-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="092e4-105">L'implementazione di criteri di spesa consente di gestire le spese in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="092e4-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="092e4-106">È ad esempio possibile impostare un criterio per le spese di albergo a New York, secondo il quale non devono superare USD 250 a notte.</span><span class="sxs-lookup"><span data-stu-id="092e4-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="092e4-107">Se un lavoratore invia una nota spese o una richiesta di viaggio in cui il prezzo della camera supera questo importo, riceverà una notifica</span><span class="sxs-lookup"><span data-stu-id="092e4-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="092e4-108">in cui viene indicato che è stato superato l'importo previsto dal criterio per questo tipo di spesa.</span><span class="sxs-lookup"><span data-stu-id="092e4-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="092e4-109">È possibile configurare il messaggio che il lavoratore riceverà quando</span><span class="sxs-lookup"><span data-stu-id="092e4-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="092e4-110">si definiscono i criteri.</span><span class="sxs-lookup"><span data-stu-id="092e4-110">define the policy.</span></span>      
        
<span data-ttu-id="092e4-111">È possibile definire tre tipi di criteri:</span><span class="sxs-lookup"><span data-stu-id="092e4-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="092e4-112">Avviso: consente al lavoratore di inviare una nota spese o una richiesta di viaggio ma la spesa verrà contrassegnata per tutti gli approvatori e</span><span class="sxs-lookup"><span data-stu-id="092e4-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="092e4-113">per la dichiarazione successiva.</span><span class="sxs-lookup"><span data-stu-id="092e4-113">for later reporting.</span></span>        

- <span data-ttu-id="092e4-114">Errore: richiede al lavoratore di rivedere la spesa per conformarsi ai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="092e4-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="092e4-115">Motivazione: richiede al lavoratore o a un responsabile di immettere una motivazione per superare l'importo previsto dai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="092e4-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

## <a name="policy-tips"></a><span data-ttu-id="092e4-116">Suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="092e4-116">Policy tips</span></span>
<span data-ttu-id="092e4-117">Di seguito sono riportati alcuni suggerimenti per semplificare la creazione di nuovi criteri per la gestione delle spese.</span><span class="sxs-lookup"><span data-stu-id="092e4-117">Here are a few suggestions that can assist you when creating new policies for expense management.</span></span> 
* <span data-ttu-id="092e4-118">I criteri sono sensibili alla data e non avranno effetto se vengono creati con una data successiva alla data in cui si è verificata la spesa.</span><span class="sxs-lookup"><span data-stu-id="092e4-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="092e4-119">Ad esempio, se oggi si stanno creando nuovi criteri per applicare una spesa massima per il pasto di 50 EUR, le eventuali spese esistenti inserite ieri non verranno verificate rispetto a questo criterio.</span><span class="sxs-lookup"><span data-stu-id="092e4-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="092e4-120">Durante la creazione dei criteri per una categoria di spesa che può essere dettagliata, è opportuno considerare l'aggiunta di una condizione per il tipo di riga spese.</span><span class="sxs-lookup"><span data-stu-id="092e4-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="092e4-121">Alcuni criteri come la richiesta di una ricevuta potrebbero non avere senso per le righe dettagliate e dovrebbero essere applicate solo alla riga dell'intestazione o a una riga non dettagliata.</span><span class="sxs-lookup"><span data-stu-id="092e4-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 
* <span data-ttu-id="092e4-122">I criteri di gestione delle spese vengono valutati in base all'entità di origine per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="092e4-122">Expense management policies are evaluated against the source entity by default.</span></span> <span data-ttu-id="092e4-123">Per gli scenari interaziendali, puoi invece impostare i criteri da valutare rispetto all'entità di destinazione (entità mutuataria).</span><span class="sxs-lookup"><span data-stu-id="092e4-123">For intercompany scenarios, you can set the policy to be evaluated against the destination entity (borrowing entity) instead.</span></span> <span data-ttu-id="092e4-124">Per eseguire i criteri sull'entità di destinazione, attiva la funzione "Valuta i criteri di spesa contro l'entità giuridica richiedente" nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="092e4-124">To run the policies against the destination entity, turn on the "Evaluate Expense policy against borrowing legal entity" feature in the **Feature Management** workspace.</span></span>

## <a name="when-to-evaluate-policies"></a><span data-ttu-id="092e4-125">Quando effettuare la valutazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="092e4-125">When to evaluate policies</span></span>

<span data-ttu-id="092e4-126">Nei parametri di Gestione spese, è disponibile un'opzione per effettuare la valutazione basata sui criteri di gestione delle spese quando viene salvata una riga o quando viene inviata una nota spese.</span><span class="sxs-lookup"><span data-stu-id="092e4-126">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="092e4-127">Se si sceglie di effettuare la valutazione dei criteri quando viene salvata una riga, ciò garantisce che gli utenti abbiano una visibilità anticipata su ciò che devono fare per completare le note spese contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="092e4-127">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="092e4-128">In alternativa, è possibile ritardare la valutazione basata sui criteri e risparmiare tempo impostando la convalida alla fine, durante l'invio al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="092e4-128">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
