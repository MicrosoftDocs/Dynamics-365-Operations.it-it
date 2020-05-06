---
title: Personalizzare la navigazione del sito
description: In questo argomento viene descritto come creare una gerarchia di navigazione online personalizzate allo scopo di organizzare i prodotti per l'esplorazione nel sito di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ae7696dcb5cdd99cd46b89ed1de1b03c16146e2d
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269661"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="eac06-103">Personalizzare la navigazione del sito</span><span class="sxs-lookup"><span data-stu-id="eac06-103">Customize site navigation</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="eac06-104">In questo argomento viene descritto come creare una gerarchia di navigazione online personalizzate allo scopo di organizzare i prodotti per l'esplorazione nel sito di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="eac06-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="eac06-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="eac06-105">Overview</span></span>

<span data-ttu-id="eac06-106">In genere le vetrine online consentono ai clienti di individuare ed esplorare prodotti navigando tra le categorie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="eac06-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="eac06-107">Questa funzionalità è in genere fornita mediante delle schede nella parte superiore della pagina o una barra di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="eac06-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="eac06-108">In Dynamics 365 Commerce, è possibile creare e gestire la struttura gerarchica della navigazione nelle categorie e i prodotti inclusi nelle varie categorie.</span><span class="sxs-lookup"><span data-stu-id="eac06-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="eac06-109">Creare una gerarchia di navigazione nei canali</span><span class="sxs-lookup"><span data-stu-id="eac06-109">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="eac06-110">Per creare una gerarchia di navigazione nei canali, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="eac06-110">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="eac06-111">Selezionare **Retail e Commerce \> Prodotti e categorie \> Gestione categorie e prodotti**.</span><span class="sxs-lookup"><span data-stu-id="eac06-111">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="eac06-112">Selezionare **Gerarchie di categorie** e quindi **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="eac06-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="eac06-113">Assegnare un nome alla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="eac06-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eac06-114">La categoria di primo livello creata è il nodo di categoria principale.</span><span class="sxs-lookup"><span data-stu-id="eac06-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="eac06-115">Non verrà visualizzata nel sito.</span><span class="sxs-lookup"><span data-stu-id="eac06-115">It won't be shown on your site.</span></span> <span data-ttu-id="eac06-116">Per creare una gerarchia di categorie in cui un singolo nodo di primo livello è visualizzato nel sito, creare e denominare la categoria come figlio della categoria principale.</span><span class="sxs-lookup"><span data-stu-id="eac06-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="eac06-117">Selezionare **Nuovo nodo di categoria** e assegnare un nome alla categoria.</span><span class="sxs-lookup"><span data-stu-id="eac06-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="eac06-118">Continuare a creare categorie di pari livello e figlio come necessario.</span><span class="sxs-lookup"><span data-stu-id="eac06-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="eac06-119">Ora è possibile assegnare prodotti a ogni categoria creata sotto la categoria di primo livello.</span><span class="sxs-lookup"><span data-stu-id="eac06-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="eac06-120">Personalizzare l'ordine delle categorie</span><span class="sxs-lookup"><span data-stu-id="eac06-120">Customize the order of categories</span></span>

<span data-ttu-id="eac06-121">Per impostazione predefinita, le categorie definite verranno visualizzate in ordine alfabetico nel sito.</span><span class="sxs-lookup"><span data-stu-id="eac06-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="eac06-122">Tuttavia, è anche possibile personalizzare l'ordine di visualizzazione delle categorie.</span><span class="sxs-lookup"><span data-stu-id="eac06-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="eac06-123">Assegnare un tipo di gerarchia di categorie</span><span class="sxs-lookup"><span data-stu-id="eac06-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="eac06-124">Selezionare **Retail e Commerce \> Prodotti e categorie \> Gestione categorie e prodotti**.</span><span class="sxs-lookup"><span data-stu-id="eac06-124">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="eac06-125">Selezionare **Gerarchie di categorie**.</span><span class="sxs-lookup"><span data-stu-id="eac06-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="eac06-126">Nel riquadro azioni, nella scheda **Gerarchia di categorie**, nel gruppo **Imposta**, selezionare **Associa tipo gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="eac06-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="eac06-127">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="eac06-127">Select **New**.</span></span>
1. <span data-ttu-id="eac06-128">Nel campo **Tipo di gerarchia di categorie**, selezionare **Gerarchia di navigazione nei canali**.</span><span class="sxs-lookup"><span data-stu-id="eac06-128">In the **Category hierarchy type** field, select **Channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="eac06-129">Nel campo **Gerarchia di categorie**, selezionare la gerarchia di navigazione nei canali creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="eac06-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="eac06-130">Pubblicare gerarchie di navigazione nuove o aggiornate</span><span class="sxs-lookup"><span data-stu-id="eac06-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="eac06-131">Per rendere disponibile la gerarchia di navigazione per la vetrina online, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="eac06-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="eac06-132">Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="eac06-132">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="eac06-133">Nell'albero a sinistra, selezionare il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="eac06-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="eac06-134">Selezionare **Pubblica aggiornamenti canale**.</span><span class="sxs-lookup"><span data-stu-id="eac06-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="eac06-135">Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="eac06-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="eac06-136">Nell'elenco trovare e selezionare **Processo 1040**.</span><span class="sxs-lookup"><span data-stu-id="eac06-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="eac06-137">Selezionare **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="eac06-137">Select **Run now**.</span></span>
1. <span data-ttu-id="eac06-138">Ripetere i passaggi 5 e 6 per i processi 1070 e 1150.</span><span class="sxs-lookup"><span data-stu-id="eac06-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="eac06-139">Visualizzare categorie nel sito</span><span class="sxs-lookup"><span data-stu-id="eac06-139">Show categories on your site</span></span>

<span data-ttu-id="eac06-140">Per visualizzare la gerarchia di categorie nella vetrina online, è necessario aggiungere il modulo Menu di navigazione nella posizione appropriata in un modello o in un frammento.</span><span class="sxs-lookup"><span data-stu-id="eac06-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="eac06-141">Il modulo Menu di navigazione visualizzerà quindi la gerarchia di navigazione, purché la gerarchia di navigazione sia stata pubblicata nel canale a cui il sito è associato.</span><span class="sxs-lookup"><span data-stu-id="eac06-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="eac06-142">Il modulo Menu di navigazione incluso nello starter kit del punto vendita consente agli utenti di accedere solo alle categorie che non hanno sottocategorie.</span><span class="sxs-lookup"><span data-stu-id="eac06-142">The navigation menu module that is included in the store starter kit lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="eac06-143">Per consentire ai clienti di accedere a categorie con sottocategorie, è necessario personalizzare il modulo Menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="eac06-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="eac06-144">Aggiungere opzioni di navigazione personalizzate</span><span class="sxs-lookup"><span data-stu-id="eac06-144">Add custom navigation options</span></span>

<span data-ttu-id="eac06-145">Nel menu di navigazione, è possibile aggiungere opzioni di navigazione che non fanno parte della gerarchia di categorie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="eac06-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="eac06-146">Ad esempio, alla fine dell'elenco di categorie di prodotti, è possibile aggiungere un elemento **Contattaci** che punta a una pagina di contatto creata per il sito.</span><span class="sxs-lookup"><span data-stu-id="eac06-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="eac06-147">Per aggiungere opzioni di navigazione personalizzate al menu di navigazione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="eac06-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="eac06-148">Nel modello o nel frammento che si desidera personalizzare, selezionare il modulo Menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="eac06-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="eac06-149">Nel riquadro delle proprietà, nella scheda **Dati**, selezionare **Aggiungi elemento** per creare un nuovo elemento di navigazione CMS.</span><span class="sxs-lookup"><span data-stu-id="eac06-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="eac06-150">Immettere il testo del collegamento e un URL</span><span class="sxs-lookup"><span data-stu-id="eac06-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="eac06-151">Ripetere i passaggi 2 e 3 per aggiungere ulteriori opzioni di navigazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="eac06-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="eac06-152">Al termine, selezionare **Salva** per salvare il modello o il frammento, quindi selezionare **Fine modifica** per archiviarlo.</span><span class="sxs-lookup"><span data-stu-id="eac06-152">When you've finished, select **Save** to save the template or fragment, and then select **Finish editing** to check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eac06-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="eac06-153">Additional resources</span></span>

[<span data-ttu-id="eac06-154">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="eac06-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="eac06-155">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="eac06-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="eac06-156">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="eac06-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="eac06-157">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="eac06-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="eac06-158">Utilizzare i moduli</span><span class="sxs-lookup"><span data-stu-id="eac06-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="eac06-159">Creare una pagina URL</span><span class="sxs-lookup"><span data-stu-id="eac06-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="eac06-160">Utilizzare i gruppi di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="eac06-160">Work with publish groups</span></span>](publish-groups.md)
