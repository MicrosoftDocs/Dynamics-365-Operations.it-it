---
title: Pianificazione generale per copertura a livello di sito, magazzino obbligatorio
description: "In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura. La dimensione magazzino è obbligatoria."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 14df626025a22237afe30cc5b08d42b475fc3a4f
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="327c8-104">Pianificazione generale per copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="327c8-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="327c8-105">In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura.</span><span class="sxs-lookup"><span data-stu-id="327c8-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="327c8-106">La dimensione magazzino è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="327c8-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="327c8-107">In questo scenario di pianificazione generale sono previste le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="327c8-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="327c8-108">La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="327c8-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="327c8-109">Questa impostazione non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="327c8-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="327c8-110">La dimensione magazzino è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="327c8-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="327c8-111">La dimensione sito non è impostata per la pianificazione di copertura.</span><span class="sxs-lookup"><span data-stu-id="327c8-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="327c8-112">Altre dimensioni possono essere impostate anche per la pianificazione copertura.</span><span class="sxs-lookup"><span data-stu-id="327c8-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="327c8-113">Tuttavia, non sono interessate dalla funzionalità multisito.</span><span class="sxs-lookup"><span data-stu-id="327c8-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="327c8-114">La dimensione magazzino non è impostata per la pianificazione di copertura.</span><span class="sxs-lookup"><span data-stu-id="327c8-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="327c8-115">Di conseguenza, la fornitura e la domanda verranno aggregate in base al sito e, forse, anche in base ad altre dimensioni pianificate per la copertura.</span><span class="sxs-lookup"><span data-stu-id="327c8-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="327c8-116">Nella figura riportata di seguito è illustrato il processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="327c8-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="327c8-117">I parametri a cui viene fatto riferimento nella figura comprendono:</span><span class="sxs-lookup"><span data-stu-id="327c8-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="327c8-118">La copertura articoli viene definita per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="327c8-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="327c8-119">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="327c8-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="327c8-120">Selezionare l'articolo, quindi fare clic su **Pianifica &gt;  Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="327c8-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="327c8-121">Relazioni di ricaricamento definite per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="327c8-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="327c8-122">Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini**</span><span class="sxs-lookup"><span data-stu-id="327c8-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="327c8-123">Nella scheda **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.</span><span class="sxs-lookup"><span data-stu-id="327c8-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="327c8-124">Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban.</span><span class="sxs-lookup"><span data-stu-id="327c8-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="327c8-125">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="327c8-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="327c8-126">Selezionare l'articolo, quindi fare clic su **Pianifica &gt; Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="327c8-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="327c8-127">Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.</span><span class="sxs-lookup"><span data-stu-id="327c8-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Copertura a livello di sito della domanda, magazzino obbligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a><span data-ttu-id="327c8-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="327c8-129">See also</span></span>
--------

[<span data-ttu-id="327c8-130">Pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="327c8-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="327c8-131">Pianificazione generale: copertura a livello di sito magazzino, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="327c8-131">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="327c8-132">Pianificazione generale: copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="327c8-132">Master planning - site coverage. warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="327c8-133">Pianificazione generale: copertura a livello di sito magazzino, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="327c8-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="327c8-134">Pianificazione generale - Come determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="327c8-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




