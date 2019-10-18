---
title: Definire i criteri di spesa
description: In Microsoft Dynamics 365 Finance è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
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
ms.openlocfilehash: 7d3b4a8f6cf74bb1fe7e53a4dfdd607f604e16e3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187454"
---
# <a name="define-expense-policies"></a><span data-ttu-id="a963c-103">Definire i criteri di spesa</span><span class="sxs-lookup"><span data-stu-id="a963c-103">Define expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a963c-104">È possibile definire criteri che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.</span><span class="sxs-lookup"><span data-stu-id="a963c-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="a963c-105">L'implementazione di criteri di spesa consente di gestire le spese in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="a963c-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="a963c-106">È ad esempio possibile impostare un criterio per le spese di albergo a New York, secondo il quale non devono superare USD 250 a notte.</span><span class="sxs-lookup"><span data-stu-id="a963c-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="a963c-107">Se un lavoratore invia una nota spese o una richiesta di viaggio in cui il prezzo della camera supera questo importo, riceverà una notifica</span><span class="sxs-lookup"><span data-stu-id="a963c-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="a963c-108">in cui viene indicato che è stato superato l'importo previsto dal criterio per questo tipo di spesa.</span><span class="sxs-lookup"><span data-stu-id="a963c-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="a963c-109">È possibile configurare il messaggio che il lavoratore riceverà quando</span><span class="sxs-lookup"><span data-stu-id="a963c-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="a963c-110">si definiscono i criteri.</span><span class="sxs-lookup"><span data-stu-id="a963c-110">define the policy.</span></span>      
        
<span data-ttu-id="a963c-111">È possibile definire tre tipi di criteri:</span><span class="sxs-lookup"><span data-stu-id="a963c-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="a963c-112">Avviso: consente al lavoratore di inviare una nota spese o una richiesta di viaggio ma la spesa verrà contrassegnata per tutti gli approvatori e</span><span class="sxs-lookup"><span data-stu-id="a963c-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="a963c-113">per la dichiarazione successiva.</span><span class="sxs-lookup"><span data-stu-id="a963c-113">for later reporting.</span></span>        

- <span data-ttu-id="a963c-114">Errore: richiede al lavoratore di rivedere la spesa per conformarsi ai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="a963c-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="a963c-115">Motivazione: richiede al lavoratore o a un responsabile di immettere una motivazione per superare l'importo previsto dai criteri prima di inviare la nota spese o la richiesta di viaggio.</span><span class="sxs-lookup"><span data-stu-id="a963c-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

## <a name="policy-tips"></a><span data-ttu-id="a963c-116">Suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="a963c-116">Policy tips</span></span>
<span data-ttu-id="a963c-117">Di seguito sono riportati alcuni suggerimenti per semplificare la creazione di nuovi criteri per la gestione delle spese.</span><span class="sxs-lookup"><span data-stu-id="a963c-117">Here are a few suggestions that can assist you whe creating new policies for expense management.</span></span> 
* <span data-ttu-id="a963c-118">I criteri sono sensibili alla data e non avranno effetto se vengono creati con una data successiva alla data in cui si è verificata la spesa.</span><span class="sxs-lookup"><span data-stu-id="a963c-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="a963c-119">Ad esempio, se oggi si stanno creando nuovi criteri per applicare una spesa massima per il pasto di 50 EUR, le eventuali spese esistenti inserite ieri non verranno verificate rispetto a questo criterio.</span><span class="sxs-lookup"><span data-stu-id="a963c-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="a963c-120">Durante la creazione dei criteri per una categoria di spesa che può essere dettagliata, è opportuno considerare l'aggiunta di una condizione per il tipo di riga spese.</span><span class="sxs-lookup"><span data-stu-id="a963c-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="a963c-121">Alcuni criteri come la richiesta di una ricevuta potrebbero non avere senso per le righe dettagliate e dovrebbero essere applicate solo alla riga dell'intestazione o a una riga non dettagliata.</span><span class="sxs-lookup"><span data-stu-id="a963c-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 

## <a name="when-to-evaluate-policies"></a><span data-ttu-id="a963c-122">Quando effettuare la valutazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="a963c-122">When to evaluate policies</span></span>

<span data-ttu-id="a963c-123">Nei parametri di Gestione spese, è disponibile un'opzione per effettuare la valutazione basata sui criteri di gestione delle spese quando viene salvata una riga o quando viene inviata una nota spese.</span><span class="sxs-lookup"><span data-stu-id="a963c-123">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="a963c-124">Se si sceglie di effettuare la valutazione dei criteri quando viene salvata una riga, ciò garantisce che gli utenti abbiano una visibilità anticipata su ciò che devono fare per completare le note spese contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a963c-124">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="a963c-125">In alternativa, è possibile ritardare la valutazione basata sui criteri e risparmiare tempo impostando la convalida alla fine, durante l'invio al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a963c-125">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
