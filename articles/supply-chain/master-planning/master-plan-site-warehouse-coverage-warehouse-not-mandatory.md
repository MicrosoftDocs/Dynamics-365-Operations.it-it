---
title: Pianificazione generale per copertura a livello di sito e magazzino, magazzino non obbligatorio
description: In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino non è impostata come obbligatoria.
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
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34a1a2cec9f86932fe2de9f3886059621903b262
ms.sourcegitcommit: dd960cf07d8be791fd27c7bb72e6baa2d63ccd51
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2019
ms.locfileid: "2578174"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="ffeef-104">Pianificazione generale per copertura a livello di sito e magazzino, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ffeef-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ffeef-105">In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura.</span><span class="sxs-lookup"><span data-stu-id="ffeef-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="ffeef-106">La dimensione magazzino non è impostata come obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="ffeef-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="ffeef-107">In questo scenario di pianificazione generale sono previste le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="ffeef-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="ffeef-108">La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="ffeef-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="ffeef-109">Questa impostazione non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="ffeef-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="ffeef-110">La dimensione magazzino non è impostata come obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="ffeef-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="ffeef-111">Il magazzino può essere noto, ma non è utilizzato nel calcolo della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="ffeef-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="ffeef-112">Le dimensioni sito e magazzino sono impostate per la pianificazione della copertura.</span><span class="sxs-lookup"><span data-stu-id="ffeef-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="ffeef-113">Altre dimensioni possono essere impostate anche per la pianificazione copertura.</span><span class="sxs-lookup"><span data-stu-id="ffeef-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="ffeef-114">Tuttavia, non sono interessate dalla funzionalità multisito.</span><span class="sxs-lookup"><span data-stu-id="ffeef-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="ffeef-115">Nella figura riportata di seguito è illustrato il processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="ffeef-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="ffeef-116">I parametri a cui viene fatto riferimento nella figura comprendono:</span><span class="sxs-lookup"><span data-stu-id="ffeef-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="ffeef-117">Il magazzino è impostato su Manuale.</span><span class="sxs-lookup"><span data-stu-id="ffeef-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="ffeef-118">Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini**</span><span class="sxs-lookup"><span data-stu-id="ffeef-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="ffeef-119">Nella scheda dettaglio **Pianificazione generale**, vedere il campo **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="ffeef-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="ffeef-120">La copertura articoli viene definita per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="ffeef-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="ffeef-121">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="ffeef-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ffeef-122">Selezionare l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fare clic su **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="ffeef-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="ffeef-123">Relazioni di ricaricamento definite per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="ffeef-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="ffeef-124">Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini**</span><span class="sxs-lookup"><span data-stu-id="ffeef-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="ffeef-125">Nella scheda dettaglio **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.</span><span class="sxs-lookup"><span data-stu-id="ffeef-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="ffeef-126">Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban.</span><span class="sxs-lookup"><span data-stu-id="ffeef-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="ffeef-127">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="ffeef-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ffeef-128">Selezionare l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fare clic su **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="ffeef-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="ffeef-129">Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.</span><span class="sxs-lookup"><span data-stu-id="ffeef-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Domanda di sito e magazzino, magazzino non obbligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="ffeef-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ffeef-131">Additional resources</span></span>
--------

[<span data-ttu-id="ffeef-132">Pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="ffeef-132">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="ffeef-133">Pianificazione generale: copertura a livello di sito magazzino, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ffeef-133">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ffeef-134">Pianificazione generale: copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ffeef-134">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ffeef-135">Pianificazione generale: copertura a livello di sito, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ffeef-135">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="ffeef-136">Pianificazione generale - Come determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="ffeef-136">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



