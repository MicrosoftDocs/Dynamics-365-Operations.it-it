---
title: Impostazioni copertura
description: Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 50f47394a4d4e95b4e158ea42a630d9e6e91f05b
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="coverage-settings"></a><span data-ttu-id="b7e59-103">Impostazioni copertura</span><span class="sxs-lookup"><span data-stu-id="b7e59-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7e59-104">Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli.</span><span class="sxs-lookup"><span data-stu-id="b7e59-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="b7e59-105">È possibile specificare impostazioni di copertura in vari modi:</span><span class="sxs-lookup"><span data-stu-id="b7e59-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="b7e59-106">Specificare impostazioni di copertura per un gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="b7e59-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="b7e59-107">È possibile creare un gruppo di copertura contenente impostazioni per tutti i prodotti collegati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="b7e59-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="b7e59-108">Fare clic su **Pianificazione generale &gt; Impostazione &gt; Copertura &gt; Gruppi di copertura** per creare un gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="b7e59-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="b7e59-109">È possibile collegare un gruppo di copertura a un prodotto.</span><span class="sxs-lookup"><span data-stu-id="b7e59-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="b7e59-110">Se il collegamento è specifico a un sito, un magazzino, o a una dimensione prodotto, utilizzare il campo **Gruppo di copertura** nella pagina **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="b7e59-111">Se il collegamento è generico, indipendentemente dalle dimensioni prodotto, utilizzare **Gruppo di copertura** in **Piano** su **Dettagli prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="b7e59-112">Se non si collega un gruppo di copertura a una pianificazione generale prodotti, verrà utilizzato per impostazione predefinita il **Gruppo di copertura generale** specificato in **Parametri di pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="b7e59-113">Specificare le impostazioni di copertura per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="b7e59-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="b7e59-114">È possibile creare impostazioni di copertura per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="b7e59-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="b7e59-115">Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="b7e59-116">Selezionare il prodotto, nel **riquadro azion**i della scheda **Pianificazione** fare clic su **Gruppo di copertura**, **Copertura articolo** per aprire la pagina **Copertura articolo**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="b7e59-117">Se il prodotto è già collegato a un gruppo di copertura, è possibile ignorare le impostazioni del gruppo utilizzando il campo **Forzatura**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="b7e59-118">Le impostazioni**Copertura articoli** di copertura nella pagina hanno la priorità sulle impostazioni **Gruppo di copertura** nella pagina.</span><span class="sxs-lookup"><span data-stu-id="b7e59-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="b7e59-119">Specificare le impostazioni di copertura per un prodotto utilizzando una procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b7e59-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="b7e59-120">La procedura guidata fornisce tutte le istruzioni necessarie per l'impostazione dei principali parametri di copertura articoli.</span><span class="sxs-lookup"><span data-stu-id="b7e59-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="b7e59-121">Nella pagina **Copertura articoli**, fare clic su **Procedura guidata** per aprire la **Procedura guidata di copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

- <span data-ttu-id="b7e59-122">Specificare impostazioni di copertura per un gruppo di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b7e59-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="b7e59-123">Fare clic su **Gestione informazioni sul prodotto &gt; Comune &gt; Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-123">Click **Product information management &gt; Common &gt; Released products**.</span></span> <span data-ttu-id="b7e59-124">Nella pagina **Dettagli prodotto rilasciato** , nella scheda **Generale**, nel gruppo **Amministrazione** fare clic sul collegamento **Gruppo di dimensioni di immagazzinamento**.</span><span class="sxs-lookup"><span data-stu-id="b7e59-124">On the **Released product detail** page, on the **General** tab, in the **Administration** group, click the **Storage dimension group** link.</span></span> <span data-ttu-id="b7e59-125">Nella pagina **Gruppo di dimensioni di immagazzinamento** selezionare il campo **Piano di copertura della dimensione** per creare le impostazioni di copertura per una dimensione nel gruppo di dimensioni di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="b7e59-125">On the **Storage dimension group** page, select the **Coverage plan by dimension** field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="b7e59-126">Tutte le dimensioni prodotto, ad esempio configurazione, colore, dimensioni, stile, devono avere il campo **Piano di copertura per dimensione** selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7e59-126">All product dimensions, such as configuration, color, size, style, must have the **Coverage plan by dimension** field selected.</span></span>



<a name="additional-resources"></a><span data-ttu-id="b7e59-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b7e59-127">Additional resources</span></span>
--------

[<span data-ttu-id="b7e59-128">Piani generali</span><span class="sxs-lookup"><span data-stu-id="b7e59-128">Master plans</span></span>](master-plans.md)




