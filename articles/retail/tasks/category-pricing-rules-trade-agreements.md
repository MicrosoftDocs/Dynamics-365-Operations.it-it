---
title: " Regole per prezzi di categoria per creare accordi commerciali"
description: Questa procedura dimostra la creazione degli accordi commerciali sui prezzi di vendita mediante una regola per prezzi di categoria.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPricingDiscountCategoryPriceRule, RetailCategoryPriceRule, EcoResCategorySingleLookup, RetailCategoryPriceWizard, PriceDiscAdm, PriceDiscAdmTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d252982cf1e4fa2f06646d0909e6f82d16f4cfc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548510"
---
# <a name="category-pricing-rules-to-create-trade-agreements"></a><span data-ttu-id="3e365-103"> Regole per prezzi di categoria per creare accordi commerciali</span><span class="sxs-lookup"><span data-stu-id="3e365-103">Category pricing rules to create trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="3e365-104">Questa procedura dimostra la creazione degli accordi commerciali sui prezzi di vendita mediante una regola per prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="3e365-104">This procedure demonstrates how to create sales price trade agreements using a category pricing rule.</span></span> <span data-ttu-id="3e365-105">La società di dati dimostrativi utilizzata per creare questa attività è USRT.</span><span class="sxs-lookup"><span data-stu-id="3e365-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="3e365-106">Questa attività è destinata al ruolo Responsabile merchandising vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="3e365-106">This task is intended for the Retail merchandising manager role.</span></span>

1. <span data-ttu-id="3e365-107">Fare clic su Gestione prezzi e sconti.</span><span class="sxs-lookup"><span data-stu-id="3e365-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="3e365-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3e365-108">Click New.</span></span>
3. <span data-ttu-id="3e365-109">Fare clic su Regola prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="3e365-109">Click Category price rule.</span></span>
4. <span data-ttu-id="3e365-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3e365-110">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="3e365-111">Selezionare un'opzione nel campo Codice conto.</span><span class="sxs-lookup"><span data-stu-id="3e365-111">In the Account code field, select an option.</span></span>
    * <span data-ttu-id="3e365-112">Un codice conto di tipo "Gruppo" viene utilizzato per impostare gli accordi commerciali sui prezzi di vendita specifici per i canali, i programmi fedeltà, i cataloghi e le affiliazioni.</span><span class="sxs-lookup"><span data-stu-id="3e365-112">A "Group" type account code is used to set up sales price trade agreements that are specific for Channels, Loyalty programs, Catalogs, and Affiliations.</span></span>  
6. <span data-ttu-id="3e365-113">Nel campo Selezione del conto, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3e365-113">In the Account selection field, enter or select a value.</span></span>
7. <span data-ttu-id="3e365-114">Nel campo Categoria immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3e365-114">In the Category field, enter or select a value.</span></span>
8. <span data-ttu-id="3e365-115">Nel campo Importo/Percentuale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3e365-115">In the Amount/Percent field, enter a number.</span></span>
9. <span data-ttu-id="3e365-116">Nel campo Versione di arrotondamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3e365-116">In the Rounding version field, enter or select a value.</span></span>
10. <span data-ttu-id="3e365-117">Fare clic su Genera accordi commerciali.</span><span class="sxs-lookup"><span data-stu-id="3e365-117">Click Generate trade agreements.</span></span>
11. <span data-ttu-id="3e365-118">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="3e365-118">Click Next.</span></span>
12. <span data-ttu-id="3e365-119">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="3e365-119">In the From date field, enter a date.</span></span>
13. <span data-ttu-id="3e365-120">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="3e365-120">In the To date field, enter a date.</span></span>
14. <span data-ttu-id="3e365-121">Selezionare Sì nel campo Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="3e365-121">Select Yes in the Find next field.</span></span>
15. <span data-ttu-id="3e365-122">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="3e365-122">Click Next.</span></span>
16. <span data-ttu-id="3e365-123">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="3e365-123">Click Finish.</span></span>
    * <span data-ttu-id="3e365-124">Si crea un giornale di registrazione accordi commerciali e viene aperto per la revisione.</span><span class="sxs-lookup"><span data-stu-id="3e365-124">This creates a Trade agreement journal and opens it for your review.</span></span>  
17. <span data-ttu-id="3e365-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="3e365-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3e365-126">I giornali di registrazione accordi commerciali creati dalle regole per prezzi di categoria non vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="3e365-126">The trade agreement journals created from the Category pricing rules aren't posted.</span></span> <span data-ttu-id="3e365-127">È possibile rivedere e modificare i prezzi generati prima di registrarli.</span><span class="sxs-lookup"><span data-stu-id="3e365-127">You can  review and edit the prices generated before posting them.</span></span>  
18. <span data-ttu-id="3e365-128">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="3e365-128">Click Edit.</span></span>
19. <span data-ttu-id="3e365-129">Nel campo Importo in valuta immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3e365-129">In the Amount in currency field, enter a number.</span></span>
20. <span data-ttu-id="3e365-130">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="3e365-130">Click Post.</span></span>
21. <span data-ttu-id="3e365-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3e365-131">Click OK.</span></span>
22. <span data-ttu-id="3e365-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3e365-132">Close the page.</span></span>
23. <span data-ttu-id="3e365-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3e365-133">Close the page.</span></span>
24. <span data-ttu-id="3e365-134">Fare clic sulla scheda Regole prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="3e365-134">Click the Category price rules tab.</span></span>
    * <span data-ttu-id="3e365-135">Le regole per prezzi di categoria specifiche del canale verranno visualizzate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3e365-135">Channel specific Category pricing rules will show in this list.</span></span>  

