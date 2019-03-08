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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "362535"
---
# <a name="configure-a-worker"></a><span data-ttu-id="203ca-103"> Configurare un lavoratore</span><span class="sxs-lookup"><span data-stu-id="203ca-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="203ca-104">Questa procedura dimostra come configurare un lavoratore di vendita al dettaglio come rappresentante che ha diritto alla provvigione sulle vendite nel POS.</span><span class="sxs-lookup"><span data-stu-id="203ca-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="203ca-105">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="203ca-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="203ca-106">Creare un gruppo di vendite con provvigione per il lavoratore</span><span class="sxs-lookup"><span data-stu-id="203ca-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="203ca-107">Andare a Vendite e marketing > Provvigioni > Gruppi vendite.</span><span class="sxs-lookup"><span data-stu-id="203ca-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="203ca-108">I lavoratori possono essere assegnati a uno o più gruppi di vendite.</span><span class="sxs-lookup"><span data-stu-id="203ca-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="203ca-109">In POS, è possibile scegliere qualsiasi gruppo di vendite contenente i lavoratori dalla rubrica del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="203ca-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="203ca-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="203ca-110">Click New.</span></span>
3. <span data-ttu-id="203ca-111">Digitare un valore nel campo Gruppo.</span><span class="sxs-lookup"><span data-stu-id="203ca-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="203ca-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="203ca-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="203ca-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="203ca-113">Click Save.</span></span>
6. <span data-ttu-id="203ca-114">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="203ca-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="203ca-115">Fare clic su Rappres.</span><span class="sxs-lookup"><span data-stu-id="203ca-115">Click Sales rep.</span></span>
    * <span data-ttu-id="203ca-116">Un gruppo di vendite può contenere più di un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="203ca-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="203ca-117">Le provvigioni possono essere suddivise tra i lavoratori in base alla modalità di definizione della quota di provvigione.</span><span class="sxs-lookup"><span data-stu-id="203ca-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="203ca-118">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="203ca-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="203ca-119">Nel campo Quota provvigione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="203ca-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="203ca-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="203ca-120">Click Save.</span></span>
11. <span data-ttu-id="203ca-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="203ca-121">Close the page.</span></span>
12. <span data-ttu-id="203ca-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="203ca-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="203ca-123">Assegnare i lavoratori al gruppo di vendite predefinito</span><span class="sxs-lookup"><span data-stu-id="203ca-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="203ca-124">Passare a Vendita al dettaglio e commercio > Dipendenti > Lavoratori.</span><span class="sxs-lookup"><span data-stu-id="203ca-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="203ca-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="203ca-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="203ca-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="203ca-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="203ca-127">Fare clic sulla scheda Vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="203ca-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="203ca-128">Un lavoratore può essere assegnato a un gruppo di vendite predefinito.</span><span class="sxs-lookup"><span data-stu-id="203ca-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="203ca-129">Il gruppo di vendite predefinito viene aggiunto automaticamente alle righe di vendita nel POS se l'opzione è abilitata nel profilo funzionalità per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="203ca-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="203ca-130">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="203ca-130">Click Edit.</span></span>
6. <span data-ttu-id="203ca-131">Nel campo Gruppo predefinito, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="203ca-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="203ca-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="203ca-132">Click Save.</span></span>

