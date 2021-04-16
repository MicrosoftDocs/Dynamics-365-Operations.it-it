---
title: Gestire criteri di acquisto e vendita di congedi
description: È possibile consentire ai dipendenti di acquistare e vendere congedi in Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f03d6055c407b2c3e13831c8b5a6f8b0d6c47897
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794711"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="bfaf8-103">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="bfaf8-103">Manage buy and sell leave policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="bfaf8-104">È possibile consentire ai dipendenti di acquistare e vendere congedi creando un criterio di acquisto e vendita di congedi.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="bfaf8-105">È possibile configurare questi criteri per utilizzare il flusso di lavoro per le approvazioni, impostare importi e tariffe massime e impostare tariffe per l'acquisto e la vendita.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="bfaf8-106">Consentire ai dipendenti di acquistare e vendere congedi</span><span class="sxs-lookup"><span data-stu-id="bfaf8-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="bfaf8-107">Nella pagina **Parametri di congedi e assenze**, selezionare **Sì** per **Consenti a dipendenti di acquistare congedi** e **Consenti a dipendenti di vendere congedi**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="bfaf8-108">Creare criteri per l'acquisto e la vendita di congedi</span><span class="sxs-lookup"><span data-stu-id="bfaf8-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="bfaf8-109">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="bfaf8-110">Selezionare **Criterio di acquisto e vendita di congedi**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="bfaf8-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-111">Select **New**.</span></span>

4. <span data-ttu-id="bfaf8-112">Immettere un **Nome** e una **Descrizione** per il criterio sotto **Criterio di acquisto e vendita di congedi**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="bfaf8-113">Selezionare un **Tipo di criterio**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="bfaf8-114">I tipi di criteri disponibili sono **Quantità** e **Ore per settimana**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="bfaf8-115">Selezionare **Quantità** per immettere un **Quantità fissa** per le quantità massime che i dipendenti possono acquistare e vendere.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="bfaf8-116">Se si seleziona **Ore per settimana**, l'orario di lavoro definito nel calendario dell'orario di lavoro assegnato del dipendente viene utilizzato per determinare la quantità massima del criterio.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="bfaf8-117">Selezionare una **Data di inizio** e una **Data di fine** per il criterio.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="bfaf8-118">Le richieste di acquisto o vendita di congedi possono essere inviate solo durante questo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="bfaf8-119">Selezionare un **ID flusso di lavoro** per i criteri.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="bfaf8-120">Qualsiasi richiesta di acquisto e vendita utilizzerà questo flusso di lavoro per la revisione e l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="bfaf8-121">Sotto **Criterio di acquisto**, selezionare **Equivalenza a tempo pieno** per ripartire la quantità massima in base all'equivalenza a tempo pieno definita nella posizione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="bfaf8-122">Se il tipo di criterio è **Quantità**, immettere una **Quantità fissa massima**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="bfaf8-123">Selezionare **Aggiungi** per aggiungere i tipi di congedo che i dipendenti possono acquistare.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="bfaf8-124">È possibile aggiungere più tipi di congedo al criterio.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="bfaf8-125">Immettere i **Mesi di servizio** per il tipo di congedo allo scopo di consentire diversi mesi di servizio e determinare la quantità massima che un dipendente può acquistare.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="bfaf8-126">Immettere la **Quantità massima** per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="bfaf8-127">Immettere il **Tasso** al quale il dipendente acquisterà il congedo.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="bfaf8-128">Eventualmente, immettere il **Codice di reddito** da utilizzare per l'acquisto dei congedi.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="bfaf8-129">Se necessario, impostare se utilizzare l'equivalenza a tempo pieno per determinare la quantità massima per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="bfaf8-130">Per creare i criteri di vendita, seguire i passaggi da 8 a 14 in **Criteri di vendita**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="bfaf8-131">Aggiungere il criterio di acquisto e vendita di congedi a un piano di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="bfaf8-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="bfaf8-132">Nella pagina **Congedo e assenza**, selezionare un piano di congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="bfaf8-133">Sotto **Regole**, selezionare **Criterio di acquisto e vendita di congedi**.</span><span class="sxs-lookup"><span data-stu-id="bfaf8-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfaf8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfaf8-134">See also</span></span>

[<span data-ttu-id="bfaf8-135">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="bfaf8-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="bfaf8-136">Configurare i tipi di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="bfaf8-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="bfaf8-137">Accumulare piani di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="bfaf8-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="bfaf8-138">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="bfaf8-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]