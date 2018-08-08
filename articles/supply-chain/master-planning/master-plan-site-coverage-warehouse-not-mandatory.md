---
title: Pianificazione generale per la copertura a livello di sito, magazzino non obbligatorio
description: In questo argomento viene descritto come viene pianificato un articolo con dimensione sito impostata per la copertura.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9475a7fbe40d7feb60c23e0d7164222469dffa75
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="f8bb8-103">Pianificazione generale per la copertura a livello di sito, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f8bb8-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8bb8-104">In questo argomento viene descritto come viene pianificato un articolo con dimensione sito impostata per la copertura.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="f8bb8-105">In questo scenario di pianificazione generale sono previste le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="f8bb8-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="f8bb8-106">La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="f8bb8-107">La dimensione magazzino non è impostata come obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="f8bb8-108">Il magazzino può essere noto, ma non è utilizzato nel calcolo della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="f8bb8-109">La dimensione sito non è impostata per la pianificazione di copertura.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="f8bb8-110">La dimensione magazzino non è impostata per la pianificazione di copertura.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="f8bb8-111">Di conseguenza, la fornitura e la domanda verranno aggregate in base al sito e, forse, anche in base ad altre dimensioni pianificate per la copertura.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="f8bb8-112">Nella figura riportata di seguito è illustrato il processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="f8bb8-113">I parametri a cui viene fatto riferimento nella figura comprendono:</span><span class="sxs-lookup"><span data-stu-id="f8bb8-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="f8bb8-114">La copertura articoli viene definita per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="f8bb8-115">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f8bb8-116">Selezionare l'articolo, quindi fare clic su **Pianifica &gt;  Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="f8bb8-117">Relazioni di ricaricamento definite per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="f8bb8-118">Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini**</span><span class="sxs-lookup"><span data-stu-id="f8bb8-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="f8bb8-119">Nella scheda **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="f8bb8-120">Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="f8bb8-121">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f8bb8-122">Selezionare l'articolo, quindi fare clic su **Pianifica &gt; Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="f8bb8-123">Nel modulo **Impostazioni ordine predefinite** vedere il campo **Tipo di ordine predefinito**.</span><span class="sxs-lookup"><span data-stu-id="f8bb8-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Copertura a livello di sito della domanda, magazzino non obbligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="f8bb8-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f8bb8-125">Additional resources</span></span>
--------

[<span data-ttu-id="f8bb8-126">Pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="f8bb8-126">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="f8bb8-127">Pianificazione generale: copertura a livello di sito, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f8bb8-127">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f8bb8-128">Pianificazione generale: copertura a livello di sito magazzino, magazzino non obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f8bb8-128">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f8bb8-129">Pianificazione generale: copertura a livello di sito magazzino, magazzino obbligatorio</span><span class="sxs-lookup"><span data-stu-id="f8bb8-129">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f8bb8-130">Pianificazione generale - Come determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="f8bb8-130">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




