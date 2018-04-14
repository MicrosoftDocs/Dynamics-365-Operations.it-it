--- 
title: " Configurare un lavoratore"
description: Questa procedura dimostra come configurare un lavoratore di vendita al dettaglio come rappresentante che ha diritto alla provvigione sulle vendite nel POS.
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5e168c4d0b4e48b73d4a31ca8525e2aeb288846c
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="configure-a-worker"></a><span data-ttu-id="de3bf-103"> Configurare un lavoratore</span><span class="sxs-lookup"><span data-stu-id="de3bf-103">Configure a worker</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="de3bf-104">Questa procedura dimostra come configurare un lavoratore di vendita al dettaglio come rappresentante che ha diritto alla provvigione sulle vendite nel POS.</span><span class="sxs-lookup"><span data-stu-id="de3bf-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="de3bf-105">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="de3bf-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="de3bf-106">Creare un gruppo di vendite con provvigione per il lavoratore</span><span class="sxs-lookup"><span data-stu-id="de3bf-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="de3bf-107">Andare a Vendite e marketing > Provvigioni > Gruppi vendite.</span><span class="sxs-lookup"><span data-stu-id="de3bf-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="de3bf-108">I lavoratori possono essere assegnati a uno o più gruppi di vendite.</span><span class="sxs-lookup"><span data-stu-id="de3bf-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="de3bf-109">In POS, è possibile scegliere qualsiasi gruppo di vendite contenente i lavoratori dalla rubrica del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="de3bf-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="de3bf-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="de3bf-110">Click New.</span></span>
3. <span data-ttu-id="de3bf-111">Digitare un valore nel campo Gruppo.</span><span class="sxs-lookup"><span data-stu-id="de3bf-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="de3bf-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="de3bf-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="de3bf-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="de3bf-113">Click Save.</span></span>
6. <span data-ttu-id="de3bf-114">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="de3bf-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="de3bf-115">Fare clic su Rappres.</span><span class="sxs-lookup"><span data-stu-id="de3bf-115">Click Sales rep.</span></span>
    * <span data-ttu-id="de3bf-116">Un gruppo di vendite può contenere più di un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="de3bf-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="de3bf-117">Le provvigioni possono essere suddivise tra i lavoratori in base alla modalità di definizione della quota di provvigione.</span><span class="sxs-lookup"><span data-stu-id="de3bf-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="de3bf-118">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="de3bf-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="de3bf-119">Nel campo Quota provvigione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="de3bf-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="de3bf-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="de3bf-120">Click Save.</span></span>
11. <span data-ttu-id="de3bf-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="de3bf-121">Close the page.</span></span>
12. <span data-ttu-id="de3bf-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="de3bf-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="de3bf-123">Assegnare i lavoratori al gruppo di vendite predefinito</span><span class="sxs-lookup"><span data-stu-id="de3bf-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="de3bf-124">Passare a Vendita al dettaglio e commercio > Dipendenti > Lavoratori.</span><span class="sxs-lookup"><span data-stu-id="de3bf-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="de3bf-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="de3bf-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="de3bf-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="de3bf-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="de3bf-127">Fare clic sulla scheda Vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="de3bf-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="de3bf-128">Un lavoratore può essere assegnato a un gruppo di vendite predefinito.</span><span class="sxs-lookup"><span data-stu-id="de3bf-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="de3bf-129">Il gruppo di vendite predefinito viene aggiunto automaticamente alle righe di vendita nel POS se l'opzione è abilitata nel profilo funzionalità per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="de3bf-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="de3bf-130">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="de3bf-130">Click Edit.</span></span>
6. <span data-ttu-id="de3bf-131">Nel campo Gruppo predefinito, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="de3bf-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="de3bf-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="de3bf-132">Click Save.</span></span>


