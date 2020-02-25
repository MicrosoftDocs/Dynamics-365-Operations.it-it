---
title: " Configurare un lavoratore"
description: Questa procedura dimostra come configurare un lavoratore come rappresentante che ha diritto alla provvigione sulle vendite nel POS.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aee84f2dc39d2225985992fac0f9c20985ed9804
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023014"
---
# <a name="configure-a-worker"></a><span data-ttu-id="d7290-103"> Configurare un lavoratore</span><span class="sxs-lookup"><span data-stu-id="d7290-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d7290-104">Questa procedura dimostra come configurare un lavoratore come rappresentante che ha diritto alla provvigione sulle vendite nel POS.</span><span class="sxs-lookup"><span data-stu-id="d7290-104">This procedure demonstrates how to configure a worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="d7290-105">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="d7290-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="d7290-106">Creare un gruppo di vendite con provvigione per il lavoratore</span><span class="sxs-lookup"><span data-stu-id="d7290-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="d7290-107">Andare a Vendite e marketing > Provvigioni > Gruppi vendite.</span><span class="sxs-lookup"><span data-stu-id="d7290-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="d7290-108">I lavoratori possono essere assegnati a uno o più gruppi di vendite.</span><span class="sxs-lookup"><span data-stu-id="d7290-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="d7290-109">In POS, è possibile scegliere qualsiasi gruppo di vendite contenente i lavoratori dalla rubrica del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d7290-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="d7290-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d7290-110">Click New.</span></span>
3. <span data-ttu-id="d7290-111">Digitare un valore nel campo Gruppo.</span><span class="sxs-lookup"><span data-stu-id="d7290-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="d7290-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d7290-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d7290-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d7290-113">Click Save.</span></span>
6. <span data-ttu-id="d7290-114">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="d7290-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="d7290-115">Fare clic su Rappres.</span><span class="sxs-lookup"><span data-stu-id="d7290-115">Click Sales rep.</span></span>
    * <span data-ttu-id="d7290-116">Un gruppo di vendite può contenere più di un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="d7290-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="d7290-117">Le provvigioni possono essere suddivise tra i lavoratori in base alla modalità di definizione della quota di provvigione.</span><span class="sxs-lookup"><span data-stu-id="d7290-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="d7290-118">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d7290-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="d7290-119">Nel campo Quota provvigione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d7290-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="d7290-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d7290-120">Click Save.</span></span>
11. <span data-ttu-id="d7290-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d7290-121">Close the page.</span></span>
12. <span data-ttu-id="d7290-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d7290-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="d7290-123">Assegnare i lavoratori al gruppo di vendite predefinito</span><span class="sxs-lookup"><span data-stu-id="d7290-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="d7290-124">Passare a Retail e Commerce > Dipendenti > Lavoratori.</span><span class="sxs-lookup"><span data-stu-id="d7290-124">Go to Retail and Commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="d7290-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d7290-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d7290-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d7290-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d7290-127">Fare clic sulla scheda Commerce.</span><span class="sxs-lookup"><span data-stu-id="d7290-127">Click the Commerce tab.</span></span>
    * <span data-ttu-id="d7290-128">Un lavoratore può essere assegnato a un gruppo di vendite predefinito.</span><span class="sxs-lookup"><span data-stu-id="d7290-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="d7290-129">Il gruppo di vendite predefinito viene aggiunto automaticamente alle righe di vendita nel POS se l'opzione è abilitata nel profilo funzionalità per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d7290-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="d7290-130">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d7290-130">Click Edit.</span></span>
6. <span data-ttu-id="d7290-131">Nel campo Gruppo predefinito, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d7290-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="d7290-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d7290-132">Click Save.</span></span>

