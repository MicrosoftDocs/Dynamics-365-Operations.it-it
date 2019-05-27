---
title: Definire regole e criteri di idoneità ai benefit
description: Questa registrazione indicherà come è possibile creare regole e criteri di idoneità di benefit e come assegnare le regole ai benefit.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d35266c95cfbf3473a14fec47a1c748229dd25
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1510581"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="34576-103">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="34576-103">Define benefit eligibility rules and policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34576-104">Questa registrazione indicherà come è possibile creare regole e criteri di idoneità di benefit e come assegnare le regole ai benefit.</span><span class="sxs-lookup"><span data-stu-id="34576-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="34576-105">La società di dati dimostrativi utilizzata per creare questa registrazione è USMF.</span><span class="sxs-lookup"><span data-stu-id="34576-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="34576-106">Creare il tipo di regola dei criteri di idoneità al benefit</span><span class="sxs-lookup"><span data-stu-id="34576-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="34576-107">Andare a Risorse umane > Benefit > Idoneità > Tipi di regole dei criteri di idoneità al benefit.</span><span class="sxs-lookup"><span data-stu-id="34576-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="34576-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="34576-108">Click New.</span></span>
3. <span data-ttu-id="34576-109">Digitare un valore nel campo Regola.</span><span class="sxs-lookup"><span data-stu-id="34576-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="34576-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="34576-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="34576-111">Nel campo Nome query fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="34576-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="34576-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="34576-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="34576-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="34576-113">Click Save.</span></span>
8. <span data-ttu-id="34576-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="34576-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="34576-115">Criteri di idoneità al benefit</span><span class="sxs-lookup"><span data-stu-id="34576-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="34576-116">Andare a Risorse umane > Benefit > Idoneità > Criteri di idoneità benefit.</span><span class="sxs-lookup"><span data-stu-id="34576-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="34576-117">Selezionare uno dei criteri di benefit esistenti.</span><span class="sxs-lookup"><span data-stu-id="34576-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="34576-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="34576-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="34576-119">Attivare/disattivare l'espansione delle sezioni Organizzazioni criteri.</span><span class="sxs-lookup"><span data-stu-id="34576-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="34576-120">In questo punto è possibile aggiungere o rimuovere tutte le organizzazioni da includere nei criteri.</span><span class="sxs-lookup"><span data-stu-id="34576-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="34576-121">Espandere o comprimere la sezione Regole dei criteri.</span><span class="sxs-lookup"><span data-stu-id="34576-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="34576-122">Nell'elenco individuare la regola dei criteri creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="34576-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="34576-123">Fare clic su Crea regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="34576-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="34576-124">Nel campo Data di validità immettere la data in cui si desidera che i criteri diventino effettivi.</span><span class="sxs-lookup"><span data-stu-id="34576-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="34576-125">Se si impostano le date di validità e di fine, è possibile apportare modifiche future alle regole dei criteri ed eliminare la necessità di tornare ai criteri quando si desidera che le modifiche siano effettive.</span><span class="sxs-lookup"><span data-stu-id="34576-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="34576-126">Se ad esempio si desidera che la regola venga applicata solo ai responsabili delle vendite, è possibile creare la clausola WHERE nel modo seguente: WHERE descrizione posizione corrisponde al responsabile vendite.</span><span class="sxs-lookup"><span data-stu-id="34576-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="34576-127">È possibile utilizzare l'operatore And oppure Or in più istruzioni WHERE nella regola.</span><span class="sxs-lookup"><span data-stu-id="34576-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="34576-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="34576-128">Click OK.</span></span>
11. <span data-ttu-id="34576-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="34576-129">Close the page.</span></span>
12. <span data-ttu-id="34576-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="34576-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="34576-131">Assegnare la regola al benefit</span><span class="sxs-lookup"><span data-stu-id="34576-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="34576-132">Andare a Risorse umane > Benefit > Benefit.</span><span class="sxs-lookup"><span data-stu-id="34576-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="34576-133">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="34576-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="34576-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="34576-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="34576-135">Espandere o comprimere la sezione Regole di idoneità.</span><span class="sxs-lookup"><span data-stu-id="34576-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="34576-136">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="34576-136">Click Edit.</span></span>
6. <span data-ttu-id="34576-137">Nel campo Idoneità selezionare Basato su regole.</span><span class="sxs-lookup"><span data-stu-id="34576-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="34576-138">Nel campo Tipo di regola fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="34576-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="34576-139">Nell'elenco individuare e selezionare la regola creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="34576-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="34576-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="34576-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="34576-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="34576-141">Click Save.</span></span>
11. <span data-ttu-id="34576-142">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="34576-142">Close the form.</span></span>

