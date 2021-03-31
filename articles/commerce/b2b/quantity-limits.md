---
title: Impostare limiti di quantità di prodotti per i siti di e-commerce B2B
description: Questo argomento descrive come impostare i limiti di quantità dei prodotti per i siti di e-commerce business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1208b968e476ccbc7a726facf1db896c7bf3c36f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211179"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a><span data-ttu-id="8ef0d-103">Impostare limiti di quantità di prodotti per i siti di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="8ef0d-103">Set product quantity limits for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8ef0d-104">Questo argomento descrive come impostare i limiti di quantità dei prodotti per i siti di e-commerce business-to-business (B2B).</span><span class="sxs-lookup"><span data-stu-id="8ef0d-104">This topic describes how to set product quantity limits for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="8ef0d-105">La maggior parte dei prodotti ha un'unità di misura che ne definisce il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-105">Most products have a unit of measure that defines their grouping.</span></span> <span data-ttu-id="8ef0d-106">Il raggruppamento influisce sul modo in cui i prodotti possono essere venduti.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-106">The grouping affects how the products can be sold.</span></span> <span data-ttu-id="8ef0d-107">Alcuni prodotti potrebbero avere un raggruppamento aggiuntivo per le quantità.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-107">Some products might have an additional grouping for quantities.</span></span> <span data-ttu-id="8ef0d-108">Questo raggruppamento determina se i prodotti possono essere venduti come unità singole o multiple e se esiste un limite di quantità di ordine minimo o massimo che deve essere rispettato.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-108">This grouping determines whether the products can be sold as individual units or multiples, and whether there is a minimum or maximum order quantity limit that must be followed.</span></span>

<span data-ttu-id="8ef0d-109">La funzione di limitazione della quantità garantisce che le quantità minime, massime, multiple e standard configurate in Microsoft Dynamics 365 Commerce (nelle impostazioni predefinite dell'ordine o nelle impostazioni del sito di Creazione di siti di Commerce) vengono applicate agli ordini dei clienti effettuati su un sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-109">The quantity limiting feature ensures that the minimum, maximum, multiple, and standard quantities that are configured in Microsoft Dynamics 365 Commerce (in the default order settings or the Commerce site builder site settings) are applied to customer orders that are placed on an e-commerce site.</span></span> <span data-ttu-id="8ef0d-110">I limiti di quantità di prodotto non sono attualmente supportati per il punto vendita (POS) e i servizi cliente.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-110">Product quantity limits aren't currently supported for the point of sale (POS) and call centers.</span></span>

<span data-ttu-id="8ef0d-111">Molti rivenditori offrono l'opzione degli ordini cliente, detti anche ordini speciali, per soddisfare vari requisiti di prodotti ed evasione.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-111">Many retailers provide the option of customer orders (also known as special orders) to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="8ef0d-112">Di seguito sono riportati alcuni scenari comuni:</span><span class="sxs-lookup"><span data-stu-id="8ef0d-112">Here are some typical scenarios:</span></span>

- <span data-ttu-id="8ef0d-113">Un cliente desidera che i prodotti con varianti specifiche vengano venduti in multipli di poche unità.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-113">A customer wants products of specific variants to be sold in multiples of a few.</span></span>
- <span data-ttu-id="8ef0d-114">Un cliente desidera prelevare i prodotti da un punto vendita o da una posizione diversa dal punto vendita o posizione in cui il cliente ha acquisito i prodotti.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-114">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span> <span data-ttu-id="8ef0d-115">Tuttavia, gli standard di imballaggio per i punti vendita differiscono dagli standard di imballaggio per la distribuzione delle vendite online.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-115">However, the packing standards for the stores differ from the packing standards for online sales distribution.</span></span>
- <span data-ttu-id="8ef0d-116">Un cliente desidera acquistare un prodotto in edizione limitata con un limite di quantità massima per gli articoli che possono essere acquistati.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-116">A customer wants to buy a limited-edition product that has a maximum quantity limit for items that can be purchased.</span></span>

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a><span data-ttu-id="8ef0d-117">Attivare la funzionalità delle impostazioni predefinite dell'ordine in Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="8ef0d-117">Turn on the default order settings feature in Commerce headquarters</span></span>

<span data-ttu-id="8ef0d-118">Prima di poter impostare i limiti di quantità del prodotto, è necessario attivare la funzione delle impostazioni predefinite dell'ordine in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-118">Before you can set product quantity limits, the default order settings feature must be turned on in Commerce headquarters.</span></span>

<span data-ttu-id="8ef0d-119">Segui questi passaggi per attivare la funzionalità delle impostazioni predefinite dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-119">To turn on the default order settings feature, follow these steps.</span></span>

1. <span data-ttu-id="8ef0d-120">Andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-120">Go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="8ef0d-121">Trova e seleziona la funzionalità **Supporta le impostazioni predefinite dell'ordine e del sito nell'ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-121">Find and select the **Support the Site and Default order settings in the customer order** feature.</span></span>
1. <span data-ttu-id="8ef0d-122">Nella parte inferiore del riquadro di destra, seleziona **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-122">At the bottom of the right pane, select **Enable now**.</span></span> 

## <a name="define-quantity-settings"></a><span data-ttu-id="8ef0d-123">Definire le impostazioni di quantità</span><span class="sxs-lookup"><span data-stu-id="8ef0d-123">Define quantity settings</span></span> 

<span data-ttu-id="8ef0d-124">È possibile definire le impostazioni di quantità nella pagina **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-124">You can define the quantity settings on the **Default order settings** page.</span></span>

<span data-ttu-id="8ef0d-125">Per definire le impostazioni di quantità segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-125">To define the quantity settings, follow these steps.</span></span> 

1. <span data-ttu-id="8ef0d-126">Vai a Prodotto **Retail e Commerce \> Prodotti e categorie \> Prodotti rilasciati per categorie**.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-126">Go to Product **Retail and Commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="8ef0d-127">Seleziona un prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-127">Select a released product.</span></span>
1. <span data-ttu-id="8ef0d-128">Nella scheda **Gestione articoli** del riquadro azioni, nel gruppo **Impostazioni ordine**, seleziona **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-128">On the Action Pane, on the **Manage inventory** tab, in the **Order settings** group, select **Default order settings**.</span></span> 
1. <span data-ttu-id="8ef0d-129">Nella pagina **Impostazioni ordine predefinite** nella scheda dettaglio **Ordine cliente** nella sezione **Quantità di vendita** imposta le quantità di vendita del prodotto:</span><span class="sxs-lookup"><span data-stu-id="8ef0d-129">On the **Default order settings** page, on the **Sales order** FastTab, in the **Sales quantity** section, set the product sales quantities:</span></span>

    - <span data-ttu-id="8ef0d-130">**Multiplo** - La quantità che il prodotto può essere acquistato in multipli.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-130">**Multiple** – The quantity that the product can be bought in multiples of.</span></span>
    - <span data-ttu-id="8ef0d-131">**Quantità ordine minima** - Il numero minimo di prodotti che devono essere acquistati.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-131">**Minimum Order Quantity** – The minimum number of products that must be purchased.</span></span>
    - <span data-ttu-id="8ef0d-132">**Quantità ordine massima** - Il numero massimo di prodotti che possono essere acquistati.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-132">**Maximum Order Quantity** – The maximum number of products that can be purchased.</span></span>
    - <span data-ttu-id="8ef0d-133">**Quantità ordine standard** - La quantità predefinita che viene inserita automaticamente quando il prodotto viene selezionato.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-133">**Standard Order Quantity** – The default quantity that is automatically entered when the product is selected.</span></span>

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a><span data-ttu-id="8ef0d-134">Attivare la funzione dei limiti di quantità degli ordini B2B in Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="8ef0d-134">Turn on the B2B order quantity limits feature in Commerce site builder</span></span>

<span data-ttu-id="8ef0d-135">Per attivare la funzione dei limiti di quantità degli ordini B2B in Creazione di siti di Commerce, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-135">To turn on the B2B order quantity limits feature in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="8ef0d-136">Vai a **Impostazioni sito \> Estensioni**</span><span class="sxs-lookup"><span data-stu-id="8ef0d-136">Go to **Site settings \> Extensions**</span></span>
1. <span data-ttu-id="8ef0d-137">Sotto **Abilita limiti quantità ordine**, seleziona **Abilitato per clienti B2B** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-137">Under **Enable Order Quantity Limits**, select **Enabled for B2B customers** in the drop-down menu.</span></span> 

> [!NOTE] 
> <span data-ttu-id="8ef0d-138">Le impostazioni aggiornati del generatore di siti avranno effetto solo dopo l'aggiornamento del file app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="8ef0d-138">Updated site builder settings take effect only after the app.settings.json file has been updated.</span></span> <span data-ttu-id="8ef0d-139">Per ulteriori informazioni, vedi [SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="8ef0d-139">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ef0d-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8ef0d-140">Additional resources</span></span>

[<span data-ttu-id="8ef0d-141">Impostare un sito di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="8ef0d-141">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="8ef0d-142">Creare gerarchie di modellazione per le organizzazioni B2B</span><span class="sxs-lookup"><span data-stu-id="8ef0d-142">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="8ef0d-143">Gestione degli utenti partner commerciali sui siti di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="8ef0d-143">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="8ef0d-144">Configura il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="8ef0d-144">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]