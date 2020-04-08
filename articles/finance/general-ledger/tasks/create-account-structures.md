---
title: Creare strutture dei conti
description: Questa guida attività descrive la creazione di una struttura dei conti.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b75ee76a1fb874652415a2174441f629955d763a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145158"
---
# <a name="create-account-structures"></a><span data-ttu-id="e1d06-103">Creare strutture dei conti</span><span class="sxs-lookup"><span data-stu-id="e1d06-103">Create account structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1d06-104">Questa guida attività descrive la creazione di una struttura dei conti.</span><span class="sxs-lookup"><span data-stu-id="e1d06-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="e1d06-105">I passaggi utilizzano la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="e1d06-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="e1d06-106">Andare a **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Strutture > Configura strutture dei conti**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-106">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="e1d06-107">Nel **Riquadro azioni**, fare clic su **Nuovo** per aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e1d06-107">On the **Action pane**, click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="e1d06-108">Nel campo **Struttura dei conti**, immettere un nome per descrivere lo scopo della struttura dei conti.</span><span class="sxs-lookup"><span data-stu-id="e1d06-108">In the **Account structure** field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="e1d06-109">Nel campo **Descrizione**, immettere una descrizione per specificare lo scopo della struttura dei conti.</span><span class="sxs-lookup"><span data-stu-id="e1d06-109">In the **Description** field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="e1d06-110">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-110">Click **Create**.</span></span>
6. <span data-ttu-id="e1d06-111">In **Segmenti e valori consentiti**, fare clic su **Aggiungi segmento**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-111">In the **Segments and allowed values**, click **Add segment**.</span></span>
7. <span data-ttu-id="e1d06-112">Nell'elenco Dimensioni, selezionare la dimensione da aggiungere alla struttura dei conti.</span><span class="sxs-lookup"><span data-stu-id="e1d06-112">In the dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="e1d06-113">Alla fine dell'elenco, fare clic su **Aggiungi segmento**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-113">At the end of the list, click **Add segment**.</span></span>
9. <span data-ttu-id="e1d06-114">Ripetere i passaggi da 6 a 9 come necessario.</span><span class="sxs-lookup"><span data-stu-id="e1d06-114">Repeat step 6 to 9 as needed.</span></span>
10. <span data-ttu-id="e1d06-115">Nella sezione **Dettagli valori consentiti**, selezionare il segmento per modificare i valori consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1d06-115">In the **Allowed value details** section, select the segment to edit the allowed values.</span></span>
    <span data-ttu-id="e1d06-116">Ad esempio, fare clic su **Conto principale**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-116">For example, click the **Main Account** field.</span></span>  
11. <span data-ttu-id="e1d06-117">Nel campo **Operatore**, selezionare un'opzione, ad esempio è compreso in e include.</span><span class="sxs-lookup"><span data-stu-id="e1d06-117">In the **Operator** field, select an option, such as is between and includes.</span></span>
12. <span data-ttu-id="e1d06-118">Digitare un valore nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-118">In the **Value** field, type a value.</span></span> <span data-ttu-id="e1d06-119">Ad esempio, 600000.</span><span class="sxs-lookup"><span data-stu-id="e1d06-119">For example, 600000.</span></span>  
13. <span data-ttu-id="e1d06-120">Digitare un valore nel campo **attraverso**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-120">In the **through** field, type a value.</span></span> <span data-ttu-id="e1d06-121">Ad esempio, 699999.</span><span class="sxs-lookup"><span data-stu-id="e1d06-121">For example, 699999.</span></span>  
14. <span data-ttu-id="e1d06-122">Nella sezione **Dettagli valori consentiti**, fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-122">In the **Allowed value details** section, click **Apply**.</span></span>
15. <span data-ttu-id="e1d06-123">Ripetere i passaggi da 10 a 15 come necessario.</span><span class="sxs-lookup"><span data-stu-id="e1d06-123">Repeat step 10 to 15 as needed.</span></span>  
16. <span data-ttu-id="e1d06-124">Nella sezione **Dettagli valori consentiti**, fare clic su **Aggiungi nuovi criteri**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-124">In the **Allowed value details** section, click **Add new criteria**.</span></span>
17. <span data-ttu-id="e1d06-125">Nel campo Operatore, selezionare un'opzione, ad esempio è compreso in e include.</span><span class="sxs-lookup"><span data-stu-id="e1d06-125">In the Operator field, select an option, such as is between and includes.</span></span>
18. <span data-ttu-id="e1d06-126">Digitare un valore nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-126">In the **Value** field, type a value.</span></span> <span data-ttu-id="e1d06-127">Ad esempio, 033.</span><span class="sxs-lookup"><span data-stu-id="e1d06-127">For example, 033.</span></span>  
19. <span data-ttu-id="e1d06-128">Digitare un valore nel campo **attraverso**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-128">In the **through** field, type a value.</span></span> <span data-ttu-id="e1d06-129">Ad esempio, 034.</span><span class="sxs-lookup"><span data-stu-id="e1d06-129">For example, 034.</span></span>  
20. <span data-ttu-id="e1d06-130">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-130">Click **Apply**.</span></span>
21. <span data-ttu-id="e1d06-131">Nella griglia, selezionare il segmento per modificare i valori consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1d06-131">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="e1d06-132">Ad esempio, Centro di costo.</span><span class="sxs-lookup"><span data-stu-id="e1d06-132">For example, Cost Center.</span></span>  
22. <span data-ttu-id="e1d06-133">Digitare un valore nel campo **CostCenter**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-133">In the **CostCenter field**, type a value.</span></span> <span data-ttu-id="e1d06-134">Ad esempio, 007..021.</span><span class="sxs-lookup"><span data-stu-id="e1d06-134">For example, 007..021.</span></span>  
23. <span data-ttu-id="e1d06-135">In **Segmenti e valori consentiti**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-135">In the **Segments and allowed values**, click **Add**.</span></span>
24. <span data-ttu-id="e1d06-136">Digitare un valore nel campo **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-136">In the **MainAccount** field, type a value.</span></span> <span data-ttu-id="e1d06-137">Ad esempio, 600000..699999</span><span class="sxs-lookup"><span data-stu-id="e1d06-137">For example, 600000..699999</span></span>  
25. <span data-ttu-id="e1d06-138">Nella griglia, selezionare il segmento per modificare i valori consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1d06-138">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="e1d06-139">Ad esempio, Reparto.</span><span class="sxs-lookup"><span data-stu-id="e1d06-139">For example, Department.</span></span>  
26. <span data-ttu-id="e1d06-140">Digitare un valore nel campo Reparto.</span><span class="sxs-lookup"><span data-stu-id="e1d06-140">In the Department field, type a value.</span></span> <span data-ttu-id="e1d06-141">Ad esempio, 032.</span><span class="sxs-lookup"><span data-stu-id="e1d06-141">For example, 032.</span></span>  
27. <span data-ttu-id="e1d06-142">Digitare un valore nel campo CostCenter.</span><span class="sxs-lookup"><span data-stu-id="e1d06-142">In the CostCenter field, type a value.</span></span> <span data-ttu-id="e1d06-143">Ad esempio, 086.</span><span class="sxs-lookup"><span data-stu-id="e1d06-143">For example, 086.</span></span>  
28. <span data-ttu-id="e1d06-144">Nel **riquadro azioni** fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-144">On the **Action pane**, click **Validate**.</span></span>
29. <span data-ttu-id="e1d06-145">Nel **riquadro azioni** fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-145">On the **Action pane**, click **Activate**.</span></span>
30. <span data-ttu-id="e1d06-146">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="e1d06-146">Click **Activate**.</span></span>

