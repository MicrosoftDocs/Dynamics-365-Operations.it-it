---
title: Pianificazione generale per copertura a livello di sito, magazzino obbligatorio
description: In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura. La dimensione magazzino è obbligatoria.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eaac165865b04a7c4ad2f08ca758b07fd41eaaa0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833547"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="ea3a5-104">Pianificazione generale per copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ea3a5-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea3a5-105">In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="ea3a5-106">La dimensione magazzino è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="ea3a5-107">In questo scenario di pianificazione generale sono previste le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="ea3a5-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="ea3a5-108">La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="ea3a5-109">Questa impostazione non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="ea3a5-110">La dimensione magazzino è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="ea3a5-111">La dimensione sito non è impostata per la pianificazione di copertura.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="ea3a5-112">Altre dimensioni possono essere impostate anche per la pianificazione copertura.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="ea3a5-113">Tuttavia, non sono interessate dalla funzionalità multisito.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="ea3a5-114">La dimensione magazzino non è impostata per la pianificazione di copertura.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="ea3a5-115">Di conseguenza, la fornitura e la domanda verranno aggregate in base al sito e, forse, anche in base ad altre dimensioni pianificate per la copertura.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="ea3a5-116">Nella figura riportata di seguito è illustrato il processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="ea3a5-117">I parametri a cui viene fatto riferimento nella figura comprendono:</span><span class="sxs-lookup"><span data-stu-id="ea3a5-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="ea3a5-118">La copertura articoli viene definita per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="ea3a5-119">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ea3a5-120">Selezionare l'articolo, quindi fare clic su **Pianifica &gt;  Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="ea3a5-121">Relazioni di ricaricamento definite per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="ea3a5-122">Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini**</span><span class="sxs-lookup"><span data-stu-id="ea3a5-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="ea3a5-123">Nella scheda **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="ea3a5-124">Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="ea3a5-125">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ea3a5-126">Selezionare l'articolo, quindi fare clic su **Pianifica &gt; Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="ea3a5-127">Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.</span><span class="sxs-lookup"><span data-stu-id="ea3a5-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Copertura a livello di sito della domanda, magazzino obbligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="ea3a5-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ea3a5-129">Additional resources</span></span>
--------

[<span data-ttu-id="ea3a5-130">Panoramica pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="ea3a5-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="ea3a5-131">Pianificazione generale a livello di sito e magazzino, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ea3a5-131">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ea3a5-132">Pianificazione generale per copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ea3a5-132">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ea3a5-133">Pianificazione generale a livello di sito e magazzino, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ea3a5-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="ea3a5-134">Determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="ea3a5-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]