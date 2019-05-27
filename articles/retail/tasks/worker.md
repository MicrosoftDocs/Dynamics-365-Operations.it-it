---
title: " Configurare un lavoratore"
description: Questa procedura dimostra come configurare un lavoratore di vendita al dettaglio come rappresentante che ha diritto alla provvigione sulle vendite nel POS.
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
ms.openlocfilehash: 797640b487884fc487582addea274007e4ba7a7d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563622"
---
# <a name="configure-a-worker"></a><span data-ttu-id="d2bb2-103"> Configurare un lavoratore</span><span class="sxs-lookup"><span data-stu-id="d2bb2-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d2bb2-104">Questa procedura dimostra come configurare un lavoratore di vendita al dettaglio come rappresentante che ha diritto alla provvigione sulle vendite nel POS.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="d2bb2-105">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="d2bb2-106">Creare un gruppo di vendite con provvigione per il lavoratore</span><span class="sxs-lookup"><span data-stu-id="d2bb2-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="d2bb2-107">Andare a Vendite e marketing > Provvigioni > Gruppi vendite.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="d2bb2-108">I lavoratori possono essere assegnati a uno o più gruppi di vendite.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="d2bb2-109">In POS, è possibile scegliere qualsiasi gruppo di vendite contenente i lavoratori dalla rubrica del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="d2bb2-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-110">Click New.</span></span>
3. <span data-ttu-id="d2bb2-111">Digitare un valore nel campo Gruppo.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="d2bb2-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d2bb2-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-113">Click Save.</span></span>
6. <span data-ttu-id="d2bb2-114">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="d2bb2-115">Fare clic su Rappres.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-115">Click Sales rep.</span></span>
    * <span data-ttu-id="d2bb2-116">Un gruppo di vendite può contenere più di un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="d2bb2-117">Le provvigioni possono essere suddivise tra i lavoratori in base alla modalità di definizione della quota di provvigione.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="d2bb2-118">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="d2bb2-119">Nel campo Quota provvigione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="d2bb2-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-120">Click Save.</span></span>
11. <span data-ttu-id="d2bb2-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-121">Close the page.</span></span>
12. <span data-ttu-id="d2bb2-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="d2bb2-123">Assegnare i lavoratori al gruppo di vendite predefinito</span><span class="sxs-lookup"><span data-stu-id="d2bb2-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="d2bb2-124">Passare a Vendita al dettaglio e commercio > Dipendenti > Lavoratori.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="d2bb2-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d2bb2-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d2bb2-127">Fare clic sulla scheda Vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="d2bb2-128">Un lavoratore può essere assegnato a un gruppo di vendite predefinito.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="d2bb2-129">Il gruppo di vendite predefinito viene aggiunto automaticamente alle righe di vendita nel POS se l'opzione è abilitata nel profilo funzionalità per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="d2bb2-130">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-130">Click Edit.</span></span>
6. <span data-ttu-id="d2bb2-131">Nel campo Gruppo predefinito, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="d2bb2-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d2bb2-132">Click Save.</span></span>

