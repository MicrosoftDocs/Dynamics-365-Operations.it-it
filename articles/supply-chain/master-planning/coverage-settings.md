---
title: Impostazioni della copertura
description: In questo argomento vengono fornite informazioni sulle impostazioni di copertura utilizzate dalla programmazione generale per calcolare le richieste articolo.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538896"
---
# <a name="coverage-settings"></a><span data-ttu-id="3b387-103">Impostazioni della copertura</span><span class="sxs-lookup"><span data-stu-id="3b387-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b387-104">Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli.</span><span class="sxs-lookup"><span data-stu-id="3b387-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="3b387-105">È possibile specificare impostazioni di copertura in vari modi:</span><span class="sxs-lookup"><span data-stu-id="3b387-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="3b387-106">Specificare impostazioni di copertura per un gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="3b387-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="3b387-107">È possibile creare un gruppo di copertura contenente impostazioni per tutti i prodotti collegati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3b387-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="3b387-108">Per creare un gruppo di copertura, fare clic su **Pianificazione generale &gt; Impostazione &gt; Copertura &gt; Gruppi di copertura**.</span><span class="sxs-lookup"><span data-stu-id="3b387-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="3b387-109">È possibile collegare un gruppo di copertura a un prodotto.</span><span class="sxs-lookup"><span data-stu-id="3b387-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="3b387-110">Se il collegamento è specifico a un sito, un magazzino, o a una dimensione prodotto, utilizzare il campo **Gruppo di copertura** nella pagina **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="3b387-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="3b387-111">Se il collegamento è generico, indipendentemente dalle dimensioni prodotto, utilizzare il campo **Gruppo di copertura** in **Piano** su **Dettagli prodotto**.</span><span class="sxs-lookup"><span data-stu-id="3b387-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="3b387-112">Per impostazione predefinita, se non si collega un gruppo di copertura a una pianificazione generale prodotti, verrà utilizzato il Gruppo di copertura generale specificato in **Parametri di pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="3b387-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="3b387-113">Specificare le impostazioni di copertura per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="3b387-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="3b387-114">È possibile creare impostazioni di copertura per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="3b387-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="3b387-115">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="3b387-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="3b387-116">Selezionare il prodotto, nel riquadro azioni della scheda **Pianificazione** fare clic su **Gruppo di copertura**, **Copertura articolo** per aprire la pagina **Copertura articolo**.</span><span class="sxs-lookup"><span data-stu-id="3b387-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="3b387-117">Se il prodotto è già collegato a un gruppo di copertura, è possibile ignorare le impostazioni del gruppo utilizzando il campo **Forzatura**.</span><span class="sxs-lookup"><span data-stu-id="3b387-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="3b387-118">Le impostazioni**Copertura articoli** di copertura nella pagina hanno la priorità sulle impostazioni **Gruppo di copertura** nella pagina.</span><span class="sxs-lookup"><span data-stu-id="3b387-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="3b387-119">Specificare le impostazioni di copertura per un prodotto utilizzando una procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="3b387-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="3b387-120">La procedura guida l'utente passo dopo passo nel processo di impostazione dei parametri di copertura degli articoli principali.</span><span class="sxs-lookup"><span data-stu-id="3b387-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="3b387-121">Nella pagina **Copertura articoli**, nel riquadro azioni selezionare **Procedura guidata** per aprire la **Procedura guidata di copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="3b387-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="3b387-122">Specificare impostazioni di copertura per un gruppo di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="3b387-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="3b387-123">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="3b387-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="3b387-124">Nella pagina **Dettagli prodotto rilasciato** , nella scheda dettagli **Generale**, nella sezione **Amministrazione** selezionare il collegamento nel campo **Gruppo di dimensioni di immagazzinamento**.</span><span class="sxs-lookup"><span data-stu-id="3b387-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="3b387-125">Nella pagina **Gruppi di dimensioni di immagazzinamento** selezionare la casella di controllo **Piano di copertura della dimensione** per creare le impostazioni di copertura per una dimensione nel gruppo di dimensioni di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="3b387-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="3b387-126">Per tutte le dimensioni prodotto, ad esempio configurazione, colore, dimensioni, stile, il campo **Piano di copertura per dimensione** deve essere selezionato.</span><span class="sxs-lookup"><span data-stu-id="3b387-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3b387-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3b387-127">Additional resources</span></span>

[<span data-ttu-id="3b387-128">Piani generali</span><span class="sxs-lookup"><span data-stu-id="3b387-128">Master plans</span></span>](master-plans.md)
