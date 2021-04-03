---
title: Definire regole e criteri di idoneità ai benefit
description: In questo articolo viene descritto come è possibile creare regole e criteri di idoneità di benefit e come assegnare le regole ai benefit.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 39a9a1c96ae2a12a32b3c5fbc67571bcf983c898
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467989"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="8a8a9-103">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="8a8a9-103">Define benefit eligibility rules and policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8a8a9-104">In questo argomento viene descritto come è possibile creare regole e criteri di idoneità di benefit e come assegnare le regole ai benefit.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-104">This topic shows you how you can create benefit eligibility rules and policies and then assign rules to benefits.</span></span>  

## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="8a8a9-105">Creare il tipo di regola dei criteri di idoneità al benefit</span><span class="sxs-lookup"><span data-stu-id="8a8a9-105">Create benefit eligibility policy rule type</span></span>

1. <span data-ttu-id="8a8a9-106">Andare a **Risorse umane > Benefit > Idoneità > Tipi di regole dei criteri di idoneità al benefit**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-106">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policy rule types**.</span></span>
2. <span data-ttu-id="8a8a9-107">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-107">Select **New**.</span></span>
3. <span data-ttu-id="8a8a9-108">Nel campo **Nome regola** immetti un valore.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-108">In the **Rule name** field, enter a value.</span></span>
4. <span data-ttu-id="8a8a9-109">Nel campo **Descrizione** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-109">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="8a8a9-110">Nel campo **Nome query**, seleziona il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-110">In the **Query name** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8a8a9-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-111">In the list, select the link in the selected row.</span></span>
7. <span data-ttu-id="8a8a9-112">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-112">Select **Save**.</span></span>
8. <span data-ttu-id="8a8a9-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-113">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="8a8a9-114">Criteri di idoneità al benefit</span><span class="sxs-lookup"><span data-stu-id="8a8a9-114">Benefit eligibility policy</span></span>

1. <span data-ttu-id="8a8a9-115">Vai a **Risorse umane > Benefit > Idoneità > Criteri di idoneità benefit**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-115">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policies**.</span></span>
2. <span data-ttu-id="8a8a9-116">Selezionare uno dei criteri di benefit esistenti.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-116">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="8a8a9-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-117">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="8a8a9-118">Attivare/disattivare l'espansione delle sezioni **Organizzazioni criteri**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-118">Toggle the expansion of the **Policy organizations** sections.</span></span> <span data-ttu-id="8a8a9-119">Puoi aggiungere o rimuovere tutte le organizzazioni da includere nei criteri.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-119">You can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="8a8a9-120">Espandere o comprimere la sezione **Regole dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-120">Expand or collapse the **Policy rules** section.</span></span>
6. <span data-ttu-id="8a8a9-121">Nell'elenco individuare la regola dei criteri creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-121">In the list, find the policy rule previously created.</span></span>
7. <span data-ttu-id="8a8a9-122">Selezionare **Crea regola dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-122">Select **Create policy rule**.</span></span>
8. <span data-ttu-id="8a8a9-123">Nel campo **Data di validità** immetti la data in cui si desidera che i criteri diventino effettivi.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-123">In the **Effective date** field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="8a8a9-124">Se si impostano le date di fine effettive, è possibile apportare modifiche future alle regole dei criteri in modo da eliminare la necessità di tornare ai criteri quando si desidera che le modifiche siano effettive.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-124">Setting effective end dates allows you to make future changes to policy rules so you don't need to come back to the policy when you want those changes to take effect.</span></span>  
9. <span data-ttu-id="8a8a9-125">Se necessario, aggiungi una clausola al campo **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-125">If needed, add a where clause to the **Add condition** field.</span></span>
    * <span data-ttu-id="8a8a9-126">Se ad esempio si desidera che la regola venga applicata solo ai responsabili delle vendite, è possibile creare la clausola WHERE nel modo seguente: WHERE descrizione posizione corrisponde al responsabile vendite.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-126">For example if you wanted the rule to only apply to Sales Managers you could create the where clause to say: Where position description equals Sales Manager.</span></span> <span data-ttu-id="8a8a9-127">Puoi aggiungere più clausole WHERE insieme nella regola.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-127">You can add multiple where statements together in the rule.</span></span>  
10. <span data-ttu-id="8a8a9-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-128">Select **OK**.</span></span>
11. <span data-ttu-id="8a8a9-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-129">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="8a8a9-130">Assegnare la regola al benefit</span><span class="sxs-lookup"><span data-stu-id="8a8a9-130">Assign rule to benefit</span></span>

1. <span data-ttu-id="8a8a9-131">Vai a **Risorse umane > Benefit > Benefit**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-131">Go to **Human resources > Benefits > Benefits**.</span></span>
2. <span data-ttu-id="8a8a9-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-132">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8a8a9-133">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-133">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="8a8a9-134">Espandere o comprimere la sezione **Regole di idoneità**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-134">Expand or collapse the **Eligibility rules** section.</span></span>
5. <span data-ttu-id="8a8a9-135">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-135">Select **Edit**.</span></span>
6. <span data-ttu-id="8a8a9-136">Nel campo **Idoneità**, seleziona la regola.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-136">In the **Eligibility** field, select the rule.</span></span>
7. <span data-ttu-id="8a8a9-137">Nel campo **Tipo di regola** seleziona la regola creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-137">In the **Rule type** field, select the rule you previously created.</span></span>
9. <span data-ttu-id="8a8a9-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-138">In the list, select the link in the selected row.</span></span>
10. <span data-ttu-id="8a8a9-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-139">Select **Save**.</span></span>
11. <span data-ttu-id="8a8a9-140">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="8a8a9-140">Close the form.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]