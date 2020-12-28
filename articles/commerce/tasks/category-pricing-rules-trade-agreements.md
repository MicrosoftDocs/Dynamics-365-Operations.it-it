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
ms.openlocfilehash: 21b1986aa36aab23f50a5af434435f9e93318e45
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413514"
---
# <a name="category-pricing-rules-to-create-trade-agreements"></a><span data-ttu-id="1a7ff-103"> Regole per prezzi di categoria per creare accordi commerciali</span><span class="sxs-lookup"><span data-stu-id="1a7ff-103">Category pricing rules to create trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a7ff-104">Questa procedura dimostra la creazione degli accordi commerciali sui prezzi di vendita mediante una regola per prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-104">This procedure demonstrates how to create sales price trade agreements using a category pricing rule.</span></span> <span data-ttu-id="1a7ff-105">La società di dati dimostrativi utilizzata per creare questa attività è USRT.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="1a7ff-106">Questa attività è destinata al ruolo Responsabile merchandising commercio.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-106">This task is intended for the Commerce merchandising manager role.</span></span>

1. <span data-ttu-id="1a7ff-107">Fare clic su Gestione prezzi e sconti.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="1a7ff-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-108">Click New.</span></span>
3. <span data-ttu-id="1a7ff-109">Fare clic su Regola prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-109">Click Category price rule.</span></span>
4. <span data-ttu-id="1a7ff-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-110">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="1a7ff-111">Selezionare un'opzione nel campo Codice conto.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-111">In the Account code field, select an option.</span></span>
    * <span data-ttu-id="1a7ff-112">Un codice conto di tipo "Gruppo" viene utilizzato per impostare gli accordi commerciali sui prezzi di vendita specifici per i canali, i programmi fedeltà, i cataloghi e le affiliazioni.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-112">A "Group" type account code is used to set up sales price trade agreements that are specific for Channels, Loyalty programs, Catalogs, and Affiliations.</span></span>  
6. <span data-ttu-id="1a7ff-113">Nel campo Selezione del conto, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-113">In the Account selection field, enter or select a value.</span></span>
7. <span data-ttu-id="1a7ff-114">Nel campo Categoria immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-114">In the Category field, enter or select a value.</span></span>
8. <span data-ttu-id="1a7ff-115">Nel campo Importo/Percentuale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-115">In the Amount/Percent field, enter a number.</span></span>
9. <span data-ttu-id="1a7ff-116">Nel campo Versione di arrotondamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-116">In the Rounding version field, enter or select a value.</span></span>
10. <span data-ttu-id="1a7ff-117">Fare clic su Genera accordi commerciali.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-117">Click Generate trade agreements.</span></span>
11. <span data-ttu-id="1a7ff-118">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-118">Click Next.</span></span>
12. <span data-ttu-id="1a7ff-119">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-119">In the From date field, enter a date.</span></span>
13. <span data-ttu-id="1a7ff-120">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-120">In the To date field, enter a date.</span></span>
14. <span data-ttu-id="1a7ff-121">Selezionare Sì nel campo Trova successivo.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-121">Select Yes in the Find next field.</span></span>
15. <span data-ttu-id="1a7ff-122">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-122">Click Next.</span></span>
16. <span data-ttu-id="1a7ff-123">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-123">Click Finish.</span></span>
    * <span data-ttu-id="1a7ff-124">Si crea un giornale di registrazione accordi commerciali e viene aperto per la revisione.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-124">This creates a Trade agreement journal and opens it for your review.</span></span>  
17. <span data-ttu-id="1a7ff-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1a7ff-126">I giornali di registrazione accordi commerciali creati dalle regole per prezzi di categoria non vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-126">The trade agreement journals created from the Category pricing rules aren't posted.</span></span> <span data-ttu-id="1a7ff-127">È possibile rivedere e modificare i prezzi generati prima di registrarli.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-127">You can  review and edit the prices generated before posting them.</span></span>  
18. <span data-ttu-id="1a7ff-128">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-128">Click Edit.</span></span>
19. <span data-ttu-id="1a7ff-129">Nel campo Importo in valuta immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-129">In the Amount in currency field, enter a number.</span></span>
20. <span data-ttu-id="1a7ff-130">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-130">Click Post.</span></span>
21. <span data-ttu-id="1a7ff-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-131">Click OK.</span></span>
22. <span data-ttu-id="1a7ff-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-132">Close the page.</span></span>
23. <span data-ttu-id="1a7ff-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-133">Close the page.</span></span>
24. <span data-ttu-id="1a7ff-134">Fare clic sulla scheda Regole prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-134">Click the Category price rules tab.</span></span>
    * <span data-ttu-id="1a7ff-135">Le regole per prezzi di categoria specifiche del canale verranno visualizzate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-135">Channel specific Category pricing rules will show in this list.</span></span>  

