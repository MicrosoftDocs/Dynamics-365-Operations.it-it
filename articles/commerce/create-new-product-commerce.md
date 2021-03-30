---
title: Creare un nuovo prodotto in Commerce
description: In questo argomento viene descritto come creare un nuovo prodotto in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: cb0137468d690649abb18b9d19673ff740d52e5d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207921"
---
# <a name="create-a-new-product-in-commerce"></a><span data-ttu-id="36deb-103">Creare un nuovo prodotto in Commerce</span><span class="sxs-lookup"><span data-stu-id="36deb-103">Create a new product in Commerce</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="36deb-104">In questo argomento viene descritto come creare un nuovo prodotto in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="36deb-104">This topic describes how to create a new product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="36deb-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="36deb-105">Overview</span></span>

<span data-ttu-id="36deb-106">Un prodotto viene principalmente definito da un numero prodotto, un nome e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="36deb-106">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="36deb-107">Tuttavia, anche altri dati sono necessari per descrivere un prodotto o servizio:</span><span class="sxs-lookup"><span data-stu-id="36deb-107">However, other data is also required in order to describe a product or service:</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="36deb-108">Creare un nuovo prodotto</span><span class="sxs-lookup"><span data-stu-id="36deb-108">Create a new product</span></span>

1. <span data-ttu-id="36deb-109">Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Prodotti per categoria**.</span><span class="sxs-lookup"><span data-stu-id="36deb-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Products by category**.</span></span>
1. <span data-ttu-id="36deb-110">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="36deb-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="36deb-111">Nell'elenco a discesa **Tipo prodotto**, selezionare **Articolo** o **Servizio**.</span><span class="sxs-lookup"><span data-stu-id="36deb-111">In the **Product type** drop-down list, select either **Item** or **Service**.</span></span>
1. <span data-ttu-id="36deb-112">Nell'elenco a discesa **Sottotipo di prodotto**, selezionare **Prodotto** (se il prodotto non avrà varianti) o **Rappresentazione generale prodotto** (se il prodotto avrà varianti).</span><span class="sxs-lookup"><span data-stu-id="36deb-112">In the **Product subtype** drop-down list, select either **Product** (if the product will have no variants) or **Product master** (if the product will have variants).</span></span>
1. <span data-ttu-id="36deb-113">Nella casella **Numero prodotto**, immettere un numero di prodotto se non è già prepopolato.</span><span class="sxs-lookup"><span data-stu-id="36deb-113">In the **Product number** box, enter a product number if one is not already prepopulated.</span></span>
1. <span data-ttu-id="36deb-114">Nella casella **Nome prodotto** immettere un nome di prodotto.</span><span class="sxs-lookup"><span data-stu-id="36deb-114">In the **Product name** box, enter a product name.</span></span>
1. <span data-ttu-id="36deb-115">Nella casella **Nome di ricerca** immettere un nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="36deb-115">In the **Search name** box, enter a search name.</span></span>
1. <span data-ttu-id="36deb-116">Nell'elenco a discesa **Categoria di vendite al dettaglio**, selezionare una categoria appropriata.</span><span class="sxs-lookup"><span data-stu-id="36deb-116">In the **Retail category** drop-down list, select an appropriate category.</span></span>
1. <span data-ttu-id="36deb-117">Se il prodotto è un kit, selezionare **Sì** per **Kit di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="36deb-117">If the product is a kit, select **Yes** for **Product kit**.</span></span>
1. <span data-ttu-id="36deb-118">Se il sottotipo di prodotto è rappresentazione generale prodotto, impostare **Gruppo di dimensioni prodotto** per includere le varianti supportate.</span><span class="sxs-lookup"><span data-stu-id="36deb-118">If the product subtype is product master, set the **Product dimension group** to include the supported variants.</span></span> <span data-ttu-id="36deb-119">Le opzioni includono **Colore**, **Dimensione**, **Stile** e **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="36deb-119">Options include **Color**, **Size**, **Style**, and **Configuration**.</span></span> <span data-ttu-id="36deb-120">Potrebbe essere necessario creare ulteriori gruppi di dimensioni prodotto, se necessario.</span><span class="sxs-lookup"><span data-stu-id="36deb-120">You may need to create additional product dimension groups if needed.</span></span>
1. <span data-ttu-id="36deb-121">Nell'elenco a discesa **Tecnologia di configurazione**, selezionare un'opzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="36deb-121">In the **Configuration technology** drop-down list, select an appropriate option.</span></span>
1. <span data-ttu-id="36deb-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="36deb-122">Select **OK**.</span></span>

<span data-ttu-id="36deb-123">L'immagine seguente mostra un esempio di prodotto aggiunto.</span><span class="sxs-lookup"><span data-stu-id="36deb-123">The following image shows an example product being added.</span></span>

![Creare un prodotto](media/create-new-product.png)

<span data-ttu-id="36deb-125">Una volta aggiunto un prodotto, è possibile impostare ulteriori dati per lo stesso, ad esempio **Descrizione prodotto**, **Gruppi di varianti**, **Gruppi di dimensioni**, **Attributi del prodotto** e **Prodotti correlati**.</span><span class="sxs-lookup"><span data-stu-id="36deb-125">Once a product is added, additional data can be set for it, such as **Product description**, **Variant groups**, **Dimension groups**, **Product attributes**, and **Related products**.</span></span>

<span data-ttu-id="36deb-126">L'immagine seguente mostra dettagli aggiuntivi di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="36deb-126">The following image shows a product's additional details.</span></span>

![Dettagli prodotto](media/create-new-product-2.png)

### <a name="create-product-variants"></a><span data-ttu-id="36deb-128">Crea varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="36deb-128">Create product variants</span></span>

<span data-ttu-id="36deb-129">Se il sottotipo di prodotto è **Rappresentazione generale prodotto**, dovranno essere create varianti specifiche.</span><span class="sxs-lookup"><span data-stu-id="36deb-129">If the product subtype is **Product master**, specific variants will need to be created.</span></span> 

<span data-ttu-id="36deb-130">Per creare delle varianti, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="36deb-130">To create product variants, follow these steps.</span></span>

1. <span data-ttu-id="36deb-131">Nel riquadro azioni selezionare **Varianti prodotto**.</span><span class="sxs-lookup"><span data-stu-id="36deb-131">On the action pane, select **Product variants**.</span></span>
1. <span data-ttu-id="36deb-132">Se sono stati selezionati gruppi di varianti nel riquadro azioni, selezionare \**Suggerimenti varianti*.</span><span class="sxs-lookup"><span data-stu-id="36deb-132">If variant groups have been selected on the action pane, select \**Variant suggestions*.</span></span>
1. <span data-ttu-id="36deb-133">Selezionare le varianti che si desidera supportare per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="36deb-133">Select the variants you would like to support for the product.</span></span>
1. <span data-ttu-id="36deb-134">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="36deb-134">Select **Create**.</span></span>

## <a name="release-a-product"></a><span data-ttu-id="36deb-135">Rilasciare un prodotto</span><span class="sxs-lookup"><span data-stu-id="36deb-135">Release a product</span></span>

<span data-ttu-id="36deb-136">Per vendere un prodotto, deve essere prima rilasciato a una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="36deb-136">To sell a product it must first be released to a legal entity.</span></span>

1. <span data-ttu-id="36deb-137">Dalla pagina del prodotto, selezionare **Rilascia prodotti**.</span><span class="sxs-lookup"><span data-stu-id="36deb-137">From the product page, select **Release products**.</span></span>

    ![Rilasciare un prodotto](media/create-new-product-3.png)

1. <span data-ttu-id="36deb-139">Selezionare il prodotto da rilasciare, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36deb-139">Select the product to release, and then select **Next**.</span></span>

    ![Scegliere il prodotto da rilasciare](media/create-new-product-4.png)

1. <span data-ttu-id="36deb-141">Selezionare il set di varianti di prodotto da rilasciare, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36deb-141">Select the set of product variants to release, and then select **Next**.</span></span>

    ![Scegliere le varianti da rilasciare](media/create-new-product-5.png)

1. <span data-ttu-id="36deb-143">Selezionare la persona giuridica, quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36deb-143">Select the legal entity, and then select **Next**.</span></span>

    ![Scegli persona giuridica](media/create-new-product-6.png)

1. <span data-ttu-id="36deb-145">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="36deb-145">Select **Finish**.</span></span>

    ![Terminare il rilascio del prodotto](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a><span data-ttu-id="36deb-147">Configurare un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="36deb-147">Configure a released product</span></span>

<span data-ttu-id="36deb-148">Una volta rilasciato il prodotto, sarà necessario eseguire un'ulteriore configurazione che include l'aggiunta di un prezzo al prodotto.</span><span class="sxs-lookup"><span data-stu-id="36deb-148">Once a product is released, it will then require further configuration that includes adding a price to the product.</span></span>

1. <span data-ttu-id="36deb-149">Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Prodotti rilasciati per categoria**.</span><span class="sxs-lookup"><span data-stu-id="36deb-149">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="36deb-150">Selezionare il nodo della categoria di prodotto per il prodotto che è stato rilasciato, quindi selezionare il prodotto dall'elenco dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="36deb-150">Select the product category node for the product that was released, and then select the product from the product list.</span></span>
1. <span data-ttu-id="36deb-151">Nel riquadro azioni selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="36deb-151">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="36deb-152">Nella sezione **Acquisti**, configurare tutte le proprietà richieste tra cui **Unità**, **Prezzo** e **Quantità**.</span><span class="sxs-lookup"><span data-stu-id="36deb-152">In the **Purchase** section, configure any required properties including **Unit**, **Price**,  and **Quantity**.</span></span>
1. <span data-ttu-id="36deb-153">Nel riquadro azioni, selezionare **Convalida** per assicurarsi che non vengano segnalati errori per i campi mancanti.</span><span class="sxs-lookup"><span data-stu-id="36deb-153">On the action pane, select **Validate** to ensure that no errors are reported for missing fields.</span></span>
1. <span data-ttu-id="36deb-154">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="36deb-154">On the action pane, select **Save**.</span></span>

<span data-ttu-id="36deb-155">L'immagine seguente illustra un esempio di configurazione per un prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="36deb-155">The following image shows an example configuration for a released product.</span></span>

![Configurare un prodotto rilasciato](media/create-new-product-8.png)

## <a name="additional-resources"></a><span data-ttu-id="36deb-157">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="36deb-157">Additional resources</span></span>

[<span data-ttu-id="36deb-158">Creare persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="36deb-158">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="36deb-159">Creare un gruppo di varianti</span><span class="sxs-lookup"><span data-stu-id="36deb-159">Create a variant group</span></span>](create-variant-group.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]