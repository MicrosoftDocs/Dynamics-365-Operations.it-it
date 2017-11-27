---
title: "Criteri di idoneità benefit"
description: "Questo articolo fornisce le informazioni sui criteri di idoneità ai benefit, che consentono di definire chi è idoneo per ottenere i benefit specifici."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 682100881d6ea8c1e02db50629208c765600c49a
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="benefit-eligibility-policies"></a><span data-ttu-id="5a406-103">Criteri di idoneità benefit</span><span class="sxs-lookup"><span data-stu-id="5a406-103">Benefit eligibility policies</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="5a406-104">Questo argomento fornisce le informazioni sui criteri di idoneità ai benefit, che consentono di definire chi è idoneo per ottenere i benefit specifici.</span><span class="sxs-lookup"><span data-stu-id="5a406-104">This topic provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="5a406-105">Quando si creano benefit, si decide quali benefit saranno disponibili per determinati dipendenti.</span><span class="sxs-lookup"><span data-stu-id="5a406-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="5a406-106">Nella seguente tabella vengono visualizzati gli esempi di benefit che è possibile rendere disponibili per dipendenti specifici.</span><span class="sxs-lookup"><span data-stu-id="5a406-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="5a406-107">Benefit</span><span class="sxs-lookup"><span data-stu-id="5a406-107">Benefit</span></span>          | <span data-ttu-id="5a406-108">Per chi è disponibile il benefit</span><span class="sxs-lookup"><span data-stu-id="5a406-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="5a406-109">Assicurazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="5a406-109">Health insurance</span></span> | <span data-ttu-id="5a406-110">Tutti i dipendenti</span><span class="sxs-lookup"><span data-stu-id="5a406-110">All employees</span></span>                   |
| <span data-ttu-id="5a406-111">Cellulare</span><span class="sxs-lookup"><span data-stu-id="5a406-111">Mobile phone</span></span>     | <span data-ttu-id="5a406-112">Venditori, dirigenti</span><span class="sxs-lookup"><span data-stu-id="5a406-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="5a406-113">Pass di parcheggio</span><span class="sxs-lookup"><span data-stu-id="5a406-113">Parking passes</span></span>   | <span data-ttu-id="5a406-114">Dirigenti</span><span class="sxs-lookup"><span data-stu-id="5a406-114">Executives</span></span>                      |

<span data-ttu-id="5a406-115">I seguenti componenti vengono utilizzati per creare i criteri di idoneità:</span><span class="sxs-lookup"><span data-stu-id="5a406-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="5a406-116">Tipi di regola dei criteri</span><span class="sxs-lookup"><span data-stu-id="5a406-116">Policy rule types</span></span>
-   <span data-ttu-id="5a406-117">Criteri di idoneità benefit</span><span class="sxs-lookup"><span data-stu-id="5a406-117">Benefit eligibility policies</span></span>

<span data-ttu-id="5a406-118">I tipi di regola dei criteri consentono di definire i parametri relativi a query utilizzati quando si sviluppano regole dei criteri specifiche.</span><span class="sxs-lookup"><span data-stu-id="5a406-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="5a406-119">Dopo aver creato i tipi di regola dei criteri, è possibile creare i criteri di idoneità al benefit.</span><span class="sxs-lookup"><span data-stu-id="5a406-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="5a406-120">I criteri consentono di creare una raccolta di regole applicabili a una o più persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="5a406-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="5a406-121">All'interno di ciascun criterio, è possibile visualizzare qualsiasi tipo di regola dei criteri di idoneità al benefit creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5a406-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="5a406-122">Definire l'ambito della regola all'interno del criterio.</span><span class="sxs-lookup"><span data-stu-id="5a406-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="5a406-123">Ad esempio, se si crea un tipo di regola dei criteri di idoneità al benefit denominata **Dirigente**, è possibile specificare come deve essere considerata la regola all'interno di tale criterio.</span><span class="sxs-lookup"><span data-stu-id="5a406-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="5a406-124">In questo esempio, la regola può prevedere che qualsiasi posizione contenente la parola "dirigente" venga inclusa nella regola.</span><span class="sxs-lookup"><span data-stu-id="5a406-124">In this example, the rule might state that any job title that contains the word “executive” should be included in the rule.</span></span> <span data-ttu-id="5a406-125">Dopo aver definito i parametri della regola o delle regole incluse nel criterio, è possibile assegnare una regola specifica al benefit.</span><span class="sxs-lookup"><span data-stu-id="5a406-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>

<a name="see-also"></a><span data-ttu-id="5a406-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a406-126">See also</span></span>
--------

[<span data-ttu-id="5a406-127">Definizione e gestione di un programma di benefit</span><span class="sxs-lookup"><span data-stu-id="5a406-127">Defining and managing a benefit program</span></span>](manage-benefit-program.md)




