---
title: Criteri di idoneità benefit
description: Questo articolo fornisce le informazioni sui criteri di idoneità ai benefit, che consentono di definire chi è idoneo per ottenere i benefit specifici.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 55ba685e36878e57fa0496191fbd24a052c073f9
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742867"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="0773a-103">Criteri di idoneità benefit</span><span class="sxs-lookup"><span data-stu-id="0773a-103">Benefit eligibility policies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0773a-104">Questo argomento fornisce le informazioni sui criteri di idoneità ai benefit, che consentono di definire chi è idoneo per ottenere i benefit specifici.</span><span class="sxs-lookup"><span data-stu-id="0773a-104">This topic provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="0773a-105">Quando si creano benefit, si decide quali benefit saranno disponibili per determinati dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0773a-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="0773a-106">Nella seguente tabella vengono visualizzati gli esempi di benefit che è possibile rendere disponibili per dipendenti specifici.</span><span class="sxs-lookup"><span data-stu-id="0773a-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="0773a-107">Benefit</span><span class="sxs-lookup"><span data-stu-id="0773a-107">Benefit</span></span>          | <span data-ttu-id="0773a-108">Per chi è disponibile il benefit</span><span class="sxs-lookup"><span data-stu-id="0773a-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="0773a-109">Assicurazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="0773a-109">Health insurance</span></span> | <span data-ttu-id="0773a-110">Tutti i dipendenti</span><span class="sxs-lookup"><span data-stu-id="0773a-110">All employees</span></span>                   |
| <span data-ttu-id="0773a-111">Cellulare</span><span class="sxs-lookup"><span data-stu-id="0773a-111">Mobile phone</span></span>     | <span data-ttu-id="0773a-112">Venditori, dirigenti</span><span class="sxs-lookup"><span data-stu-id="0773a-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="0773a-113">Pass di parcheggio</span><span class="sxs-lookup"><span data-stu-id="0773a-113">Parking passes</span></span>   | <span data-ttu-id="0773a-114">Dirigenti</span><span class="sxs-lookup"><span data-stu-id="0773a-114">Executives</span></span>                      |

<span data-ttu-id="0773a-115">I seguenti componenti vengono utilizzati per creare i criteri di idoneità:</span><span class="sxs-lookup"><span data-stu-id="0773a-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="0773a-116">Tipi di regola dei criteri</span><span class="sxs-lookup"><span data-stu-id="0773a-116">Policy rule types</span></span>
-   <span data-ttu-id="0773a-117">Criteri di idoneità benefit</span><span class="sxs-lookup"><span data-stu-id="0773a-117">Benefit eligibility policies</span></span>

<span data-ttu-id="0773a-118">I tipi di regola dei criteri consentono di definire i parametri relativi a query utilizzati quando si sviluppano regole dei criteri specifiche.</span><span class="sxs-lookup"><span data-stu-id="0773a-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="0773a-119">Dopo aver creato i tipi di regola dei criteri, è possibile creare i criteri di idoneità al benefit.</span><span class="sxs-lookup"><span data-stu-id="0773a-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="0773a-120">I criteri consentono di creare una raccolta di regole applicabili a una o più persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="0773a-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="0773a-121">All'interno di ciascun criterio, è possibile visualizzare qualsiasi tipo di regola dei criteri di idoneità al benefit creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0773a-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="0773a-122">Definire l'ambito della regola all'interno del criterio.</span><span class="sxs-lookup"><span data-stu-id="0773a-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="0773a-123">Ad esempio, se si crea un tipo di regola dei criteri di idoneità al benefit denominata **Dirigente**, è possibile specificare come deve essere considerata la regola all'interno di tale criterio.</span><span class="sxs-lookup"><span data-stu-id="0773a-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="0773a-124">In questo esempio, la regola può prevedere che qualsiasi posizione contenente la parola "dirigente" debba essere inclusa nella regola.</span><span class="sxs-lookup"><span data-stu-id="0773a-124">In this example, the rule might state that any job title that contains the word "executive" should be included in the rule.</span></span> <span data-ttu-id="0773a-125">Dopo aver definito i parametri della regola o delle regole incluse nel criterio, è possibile assegnare una regola specifica al benefit.</span><span class="sxs-lookup"><span data-stu-id="0773a-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>

<a name="additional-resources"></a><span data-ttu-id="0773a-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0773a-126">Additional resources</span></span>
--------

[<span data-ttu-id="0773a-127">Definizione e gestione di un programma di benefit</span><span class="sxs-lookup"><span data-stu-id="0773a-127">Defining and managing a benefit program</span></span>](manage-benefit-program.md)



