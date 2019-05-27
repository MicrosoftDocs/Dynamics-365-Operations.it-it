---
title: Pianificazione generale per copertura a livello di sito e magazzino, magazzino obbligatorio
description: In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino è obbligatoria.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c52fc9955afe2a7502d0e1f9e7cdfc5b89bbb31d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559280"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="efa86-104">Pianificazione generale per copertura a livello di sito e magazzino, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="efa86-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efa86-105">In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura.</span><span class="sxs-lookup"><span data-stu-id="efa86-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="efa86-106">La dimensione magazzino è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="efa86-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="efa86-107">In questo scenario di pianificazione generale sono previste le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="efa86-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="efa86-108">La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="efa86-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="efa86-109">La dimensione magazzino è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="efa86-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="efa86-110">Le dimensioni sito e magazzino sono impostate per la pianificazione della copertura.</span><span class="sxs-lookup"><span data-stu-id="efa86-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="efa86-111">Altre dimensioni possono essere impostate anche per la pianificazione copertura.</span><span class="sxs-lookup"><span data-stu-id="efa86-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="efa86-112">Tuttavia, non sono interessate dalla funzionalità multisito.</span><span class="sxs-lookup"><span data-stu-id="efa86-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="efa86-113">Nella figura riportata di seguito è illustrato il processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="efa86-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="efa86-114">I parametri a cui viene fatto riferimento nella figura comprendono:</span><span class="sxs-lookup"><span data-stu-id="efa86-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="efa86-115">Il magazzino è impostato su **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="efa86-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="efa86-116">Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini**</span><span class="sxs-lookup"><span data-stu-id="efa86-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="efa86-117">Nella scheda dettaglio **Pianificazione generale**, vedere il campo **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="efa86-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="efa86-118">La copertura articoli viene definita per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="efa86-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="efa86-119">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="efa86-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="efa86-120">Selezionare l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fare clic su **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="efa86-120">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="efa86-121">Relazioni di ricaricamento definite per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="efa86-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="efa86-122">Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini**</span><span class="sxs-lookup"><span data-stu-id="efa86-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="efa86-123">Nella scheda dettaglio **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.</span><span class="sxs-lookup"><span data-stu-id="efa86-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="efa86-124">Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban.</span><span class="sxs-lookup"><span data-stu-id="efa86-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="efa86-125">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="efa86-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="efa86-126">Selezionare l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fare clic su **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="efa86-126">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="efa86-127">Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.</span><span class="sxs-lookup"><span data-stu-id="efa86-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Copertura a livello di sito e magazzino della domanda, magazzino obbligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="efa86-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="efa86-129">Additional resources</span></span>
--------

[<span data-ttu-id="efa86-130">Pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="efa86-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="efa86-131">Pianificazione generale: copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="efa86-131">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="efa86-132">Pianificazione generale: copertura a livello di sito, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="efa86-132">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="efa86-133">Pianificazione generale: copertura a livello di sito magazzino, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="efa86-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="efa86-134">Pianificazione generale - Come determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="efa86-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



