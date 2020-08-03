---
title: Gestire criteri di acquisto e vendita di congedi
description: È possibile consentire ai dipendenti di acquistare e vendere congedi in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429015"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="35b1a-103">Gestire criteri di acquisto e vendita di congedi</span><span class="sxs-lookup"><span data-stu-id="35b1a-103">Manage buy and sell leave policies</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="35b1a-104">È possibile consentire ai dipendenti di acquistare congedi creando un criterio di acquisto di congedi.</span><span class="sxs-lookup"><span data-stu-id="35b1a-104">You can enable employees to buy leave by creating a buy leave policy.</span></span>  

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="35b1a-105">Consentire ai dipendenti di acquistare e vendere congedi</span><span class="sxs-lookup"><span data-stu-id="35b1a-105">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="35b1a-106">Nella pagina **Parametri di congedi e assenze**, selezionare **Sì** per **Consenti a dipendenti di acquistare congedi**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-106">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave**.</span></span> 

## <a name="create-a-buy-leave-policy"></a><span data-ttu-id="35b1a-107">Creare un criterio di acquisto di congedi</span><span class="sxs-lookup"><span data-stu-id="35b1a-107">Create a buy leave policy</span></span>

1. <span data-ttu-id="35b1a-108">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-108">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="35b1a-109">Selezionare **Criterio di acquisto e vendita di congedi**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-109">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="35b1a-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-110">Select **New**.</span></span>

4. <span data-ttu-id="35b1a-111">Immettere un **Nome** e una **Descrizione** per il criterio sotto **Criterio di acquisto e vendita di congedi**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-111">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="35b1a-112">Selezionare un **Tipo di criterio**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-112">Select a **Policy type**.</span></span> 

   <span data-ttu-id="35b1a-113">I tipi di criteri disponibili sono **Quantità** e **Ore per settimana**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-113">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="35b1a-114">Selezionare **Quantità** per immettere un **Quantità fissa** per le quantità massime che i dipendenti possono acquistare e vendere.</span><span class="sxs-lookup"><span data-stu-id="35b1a-114">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="35b1a-115">Se si seleziona **Ore per settimana**, l'orario di lavoro definito nel calendario dell'orario di lavoro assegnato del dipendente viene utilizzato per determinare la quantità massima del criterio.</span><span class="sxs-lookup"><span data-stu-id="35b1a-115">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="35b1a-116">Selezionare una **Data di inizio** e una **Data di fine** per il criterio.</span><span class="sxs-lookup"><span data-stu-id="35b1a-116">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="35b1a-117">Le richieste di acquisto o vendita di congedi possono essere inviate solo durante questo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="35b1a-117">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="35b1a-118">Sotto **Criterio di acquisto**, selezionare **Equivalenza a tempo pieno** per ripartire la quantità massima in base all'equivalenza a tempo pieno definita nella posizione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="35b1a-118">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="35b1a-119">Se il tipo di criterio è **Quantità**, immettere una **Quantità fissa massima**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-119">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

8. <span data-ttu-id="35b1a-120">Selezionare **Aggiungi** per aggiungere i tipi di congedo che i dipendenti possono acquistare.</span><span class="sxs-lookup"><span data-stu-id="35b1a-120">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="35b1a-121">È possibile aggiungere più tipi di congedo al criterio.</span><span class="sxs-lookup"><span data-stu-id="35b1a-121">You can add multiple leave types to the policy.</span></span> 

9. <span data-ttu-id="35b1a-122">Immettere i **Mesi di servizio** per il tipo di congedo allo scopo di consentire diversi mesi di servizio e determinare la quantità massima che un dipendente può acquistare.</span><span class="sxs-lookup"><span data-stu-id="35b1a-122">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

10. <span data-ttu-id="35b1a-123">Immettere la **Quantità massima** per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="35b1a-123">Enter the **Maximum amount** for the leave type.</span></span> 

11. <span data-ttu-id="35b1a-124">Immettere il **Tasso** al quale il dipendente acquisterà il congedo.</span><span class="sxs-lookup"><span data-stu-id="35b1a-124">Enter the **Rate** at which the employee will buy the leave.</span></span> 

12. <span data-ttu-id="35b1a-125">Eventualmente, immettere il **Codice di reddito** da utilizzare per l'acquisto dei congedi.</span><span class="sxs-lookup"><span data-stu-id="35b1a-125">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

13. <span data-ttu-id="35b1a-126">Se necessario, impostare se utilizzare l'equivalenza a tempo pieno per determinare la quantità massima per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="35b1a-126">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="35b1a-127">Aggiungere il criterio di acquisto e vendita di congedi a un piano di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="35b1a-127">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="35b1a-128">Nella pagina **Congedo e assenza**, selezionare un piano di congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="35b1a-128">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="35b1a-129">Sotto **Regole**, selezionare **Criterio di acquisto e vendita di congedi**.</span><span class="sxs-lookup"><span data-stu-id="35b1a-129">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="35b1a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35b1a-130">See also</span></span>

[<span data-ttu-id="35b1a-131">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="35b1a-131">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="35b1a-132">Configurare i tipi di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="35b1a-132">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="35b1a-133">Accumulare piani di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="35b1a-133">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="35b1a-134">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="35b1a-134">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)
