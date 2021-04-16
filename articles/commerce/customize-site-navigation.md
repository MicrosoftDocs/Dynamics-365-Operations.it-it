---
title: Personalizzare la navigazione del sito
description: In questo argomento viene descritto come creare una gerarchia di navigazione online personalizzate allo scopo di organizzare i prodotti per l'esplorazione nel sito di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5bc50243ac3845adc60bfc173fc532fb28f3cdf6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799351"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="93b11-103">Personalizzare la navigazione del sito</span><span class="sxs-lookup"><span data-stu-id="93b11-103">Customize site navigation</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="93b11-104">In questo argomento viene descritto come creare una gerarchia di navigazione online personalizzate allo scopo di organizzare i prodotti per l'esplorazione nel sito di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93b11-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="93b11-105">In genere le vetrine online consentono ai clienti di individuare ed esplorare prodotti navigando tra le categorie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="93b11-105">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="93b11-106">Questa funzionalità è in genere fornita mediante delle schede nella parte superiore della pagina o una barra di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="93b11-106">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="93b11-107">In Dynamics 365 Commerce, è possibile creare e gestire la struttura gerarchica della navigazione nelle categorie e i prodotti inclusi nelle varie categorie.</span><span class="sxs-lookup"><span data-stu-id="93b11-107">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="93b11-108">Creare una gerarchia di navigazione nei canali</span><span class="sxs-lookup"><span data-stu-id="93b11-108">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="93b11-109">Per creare una gerarchia di navigazione nei canali, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="93b11-109">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="93b11-110">Selezionare **Retail e Commerce \> Prodotti e categorie \> Gestione categorie e prodotti**.</span><span class="sxs-lookup"><span data-stu-id="93b11-110">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="93b11-111">Selezionare **Gerarchie di categorie** e quindi **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="93b11-111">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="93b11-112">Assegnare un nome alla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="93b11-112">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93b11-113">La categoria di primo livello creata è il nodo di categoria principale.</span><span class="sxs-lookup"><span data-stu-id="93b11-113">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="93b11-114">Non verrà visualizzata nel sito.</span><span class="sxs-lookup"><span data-stu-id="93b11-114">It won't be shown on your site.</span></span> <span data-ttu-id="93b11-115">Per creare una gerarchia di categorie in cui un singolo nodo di primo livello è visualizzato nel sito, creare e denominare la categoria come figlio della categoria principale.</span><span class="sxs-lookup"><span data-stu-id="93b11-115">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="93b11-116">Selezionare **Nuovo nodo di categoria** e assegnare un nome alla categoria.</span><span class="sxs-lookup"><span data-stu-id="93b11-116">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="93b11-117">Continuare a creare categorie di pari livello e figlio come necessario.</span><span class="sxs-lookup"><span data-stu-id="93b11-117">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="93b11-118">Ora è possibile assegnare prodotti a ogni categoria creata sotto la categoria di primo livello.</span><span class="sxs-lookup"><span data-stu-id="93b11-118">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="93b11-119">Personalizzare l'ordine delle categorie</span><span class="sxs-lookup"><span data-stu-id="93b11-119">Customize the order of categories</span></span>

<span data-ttu-id="93b11-120">Per impostazione predefinita, le categorie definite verranno visualizzate in ordine alfabetico nel sito.</span><span class="sxs-lookup"><span data-stu-id="93b11-120">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="93b11-121">Tuttavia, è anche possibile personalizzare l'ordine di visualizzazione delle categorie.</span><span class="sxs-lookup"><span data-stu-id="93b11-121">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="93b11-122">Assegnare un tipo di gerarchia di categorie</span><span class="sxs-lookup"><span data-stu-id="93b11-122">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="93b11-123">Selezionare **Retail e Commerce \> Prodotti e categorie \> Gestione categorie e prodotti**.</span><span class="sxs-lookup"><span data-stu-id="93b11-123">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="93b11-124">Selezionare **Gerarchie di categorie**.</span><span class="sxs-lookup"><span data-stu-id="93b11-124">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="93b11-125">Nel riquadro azioni, nella scheda **Gerarchia di categorie**, nel gruppo **Imposta**, selezionare **Associa tipo gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="93b11-125">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="93b11-126">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="93b11-126">Select **New**.</span></span>
1. <span data-ttu-id="93b11-127">Nel campo **Tipo di gerarchia di categorie**, selezionare **Gerarchia di navigazione nei canali**.</span><span class="sxs-lookup"><span data-stu-id="93b11-127">In the **Category hierarchy type** field, select **Channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="93b11-128">Nel campo **Gerarchia di categorie**, selezionare la gerarchia di navigazione nei canali creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="93b11-128">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="93b11-129">Pubblicare gerarchie di navigazione nuove o aggiornate</span><span class="sxs-lookup"><span data-stu-id="93b11-129">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="93b11-130">Per rendere disponibile la gerarchia di navigazione per la vetrina online, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="93b11-130">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="93b11-131">Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="93b11-131">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="93b11-132">Nell'albero a sinistra, selezionare il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="93b11-132">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="93b11-133">Selezionare **Pubblica aggiornamenti canale**.</span><span class="sxs-lookup"><span data-stu-id="93b11-133">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="93b11-134">Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="93b11-134">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="93b11-135">Nell'elenco trovare e selezionare **Processo 1040**.</span><span class="sxs-lookup"><span data-stu-id="93b11-135">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="93b11-136">Selezionare **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="93b11-136">Select **Run now**.</span></span>
1. <span data-ttu-id="93b11-137">Ripetere i passaggi 5 e 6 per i processi 1070 e 1150.</span><span class="sxs-lookup"><span data-stu-id="93b11-137">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="93b11-138">Visualizzare categorie nel sito</span><span class="sxs-lookup"><span data-stu-id="93b11-138">Show categories on your site</span></span>

<span data-ttu-id="93b11-139">Per visualizzare la gerarchia di categorie nella vetrina online, è necessario aggiungere il modulo Menu di navigazione nella posizione appropriata in un modello o in un frammento.</span><span class="sxs-lookup"><span data-stu-id="93b11-139">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="93b11-140">Il modulo Menu di navigazione visualizzerà quindi la gerarchia di navigazione, purché la gerarchia di navigazione sia stata pubblicata nel canale a cui il sito è associato.</span><span class="sxs-lookup"><span data-stu-id="93b11-140">The navigation menu module will then show your navigation hierarchy, provided that you've published your navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="93b11-141">Il modulo Menu di navigazione incluso nella libreria di modelli del punto vendita consente agli utenti di accedere solo alle categorie che non hanno sottocategorie.</span><span class="sxs-lookup"><span data-stu-id="93b11-141">The navigation menu module that is included in the module library lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="93b11-142">Per consentire ai clienti di accedere a categorie con sottocategorie, è necessario personalizzare il modulo Menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="93b11-142">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="93b11-143">Aggiungere opzioni di navigazione personalizzate</span><span class="sxs-lookup"><span data-stu-id="93b11-143">Add custom navigation options</span></span>

<span data-ttu-id="93b11-144">Nel menu di navigazione, è possibile aggiungere opzioni di navigazione che non fanno parte della gerarchia di categorie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="93b11-144">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="93b11-145">Ad esempio, alla fine dell'elenco di categorie di prodotti, è possibile aggiungere un elemento **Contattaci** che punta a una pagina di contatto creata per il sito.</span><span class="sxs-lookup"><span data-stu-id="93b11-145">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="93b11-146">Per aggiungere opzioni di navigazione personalizzate al menu di navigazione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="93b11-146">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="93b11-147">Nel modello o nel frammento che si desidera personalizzare, selezionare il modulo Menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="93b11-147">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="93b11-148">Nel riquadro delle proprietà, nella scheda **Dati**, selezionare **Aggiungi elemento** per creare un nuovo elemento di navigazione CMS.</span><span class="sxs-lookup"><span data-stu-id="93b11-148">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="93b11-149">Immettere il testo del collegamento e un URL</span><span class="sxs-lookup"><span data-stu-id="93b11-149">Enter link text and a URL.</span></span>
1. <span data-ttu-id="93b11-150">Ripetere i passaggi 2 e 3 per aggiungere ulteriori opzioni di navigazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="93b11-150">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="93b11-151">Al termine, selezionare **Salva** per salvare il modello o il frammento, quindi selezionare **Fine modifica** per archiviarlo.</span><span class="sxs-lookup"><span data-stu-id="93b11-151">When you've finished, select **Save** to save the template or fragment, and then select **Finish editing** to check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93b11-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="93b11-152">Additional resources</span></span>

[<span data-ttu-id="93b11-153">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="93b11-153">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="93b11-154">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="93b11-154">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="93b11-155">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="93b11-155">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="93b11-156">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="93b11-156">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="93b11-157">Utilizzare i moduli</span><span class="sxs-lookup"><span data-stu-id="93b11-157">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="93b11-158">Creare una pagina URL</span><span class="sxs-lookup"><span data-stu-id="93b11-158">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="93b11-159">Utilizzare i gruppi di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="93b11-159">Work with publish groups</span></span>](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
