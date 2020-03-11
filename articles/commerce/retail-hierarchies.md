---
title: Gerarchie Commerce
description: Questo articolo descrive le gerarchie in Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e1b9fc647ccaa3caeec0d0e3a8594fd6a2a8be0f
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070738"
---
# <a name="commerce-hierarchies"></a><span data-ttu-id="f5eb5-103">Gerarchie Commerce</span><span class="sxs-lookup"><span data-stu-id="f5eb5-103">Commerce hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f5eb5-104">Questo articolo descrive le gerarchie in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-104">This article describes hierarchies in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f5eb5-105">È possibile creare una gerarchia di categorie per organizzare i prodotti venduti tramite i canali.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-105">You can create a category hierarchy to organize the products that you sell through your channels.</span></span> <span data-ttu-id="f5eb5-106">È possibile utilizzare le gerarchie di prodotti per classificare o raggruppare prodotti.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-106">You can use product hierarchies to categorize or group products.</span></span> <span data-ttu-id="f5eb5-107">Tali prodotti possono essere utilizzati per creare gli assortimenti prodotti e i programmi fedeltà dei clienti.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-107">You can then use these products to create product assortments and customer loyalty programs.</span></span> <span data-ttu-id="f5eb5-108">È inoltre possibile assegnare al prodotto attributi e proprietà, assegnare una struttura del prezzo, includere i prodotti nelle promozioni prodotto e utilizzare i prodotti per la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-108">You can also assign product attributes and properties, assign a pricing structure, include the products in product promotions, and use the products for reporting.</span></span> <span data-ttu-id="f5eb5-109">È possibile creare una gerarchia di categorie per rappresentare tutti i prodotti e le categorie nell'organizzazione, quindi utilizzare tale gerarchia di categorie per più scopi.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-109">You can create one category hierarchy to represent all the products and categories in your organization, and then use that category hierarchy for multiple purposes.</span></span> <span data-ttu-id="f5eb5-110">In alternativa, è possibile creare più gerarchie di categorie per scopi specifici, quali promozioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-110">Alternatively, you can create multiple category hierarchies for special purposes, such as product promotions.</span></span> <span data-ttu-id="f5eb5-111">Quando si crea una gerarchia di prodotti, è necessario assegnare un tipo di gerarchia di categorie per identificare lo scopo della gerarchia di categorie.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-111">When you create a product hierarchy, you must assign a category hierarchy type to identify the purpose of the category hierarchy.</span></span> <span data-ttu-id="f5eb5-112">Ad esempio, quando si esplorano i prodotti per categoria online o punto di vendita (POS), viene fatto riferimento solo alle gerarchie di prodotti alle quali è stato assegnato il tipo **Gerarchia di navigazione di Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-112">For example, only product hierarchies that are assigned the **Commerce navigation hierarchy** type are referenced when you browse products by category online or in point of sale (POS).</span></span>

## <a name="hierarchy-types"></a><span data-ttu-id="f5eb5-113">Tipo di gerarchie</span><span class="sxs-lookup"><span data-stu-id="f5eb5-113">Hierarchy types</span></span>

<span data-ttu-id="f5eb5-114">Nella seguente tabella vengono riportati i tipi di gerarchie di categorie disponibili e lo scopo generale di ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-114">The following table lists the types of category hierarchies that are available and the general purpose of each type.</span></span>

| <span data-ttu-id="f5eb5-115">Tipo di gerarchia di categorie</span><span class="sxs-lookup"><span data-stu-id="f5eb5-115">Category hierarchy type</span></span>       | <span data-ttu-id="f5eb5-116">Scopo</span><span class="sxs-lookup"><span data-stu-id="f5eb5-116">Purpose</span></span> |
|-------------------------------|---------|
| <span data-ttu-id="f5eb5-117">Gerarchia prodotti</span><span class="sxs-lookup"><span data-stu-id="f5eb5-117">Product hierarchy</span></span>      | <span data-ttu-id="f5eb5-118">Utilizzare questo tipo di gerarchia per definire la gerarchia di prodotti generale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-118">Use this hierarchy type to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="f5eb5-119">È possibile utilizzare questo tipo di gerarchia per la vendita, la determinazione dei prezzi, le promozioni, il reporting e la pianificazione degli assortimenti.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-119">You can use this hierarchy type for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="f5eb5-120">A questo tipo di gerarchia può essere assegnata solo una gerarchia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-120">Only one product hierarchy can be assigned this hierarchy type.</span></span> |
| <span data-ttu-id="f5eb5-121">Gerarchia supplementare</span><span class="sxs-lookup"><span data-stu-id="f5eb5-121">Supplemental hierarchy</span></span> | <span data-ttu-id="f5eb5-122">Utilizzare questo tipo di gerarchia per tutte le gerarchie di categorie aggiuntive che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-122">Use this hierarchy type for any additional category hierarchies that you want to create.</span></span> <span data-ttu-id="f5eb5-123">Ad esempio, in primavera, è disponibile una promozione per costumi da bagno.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-123">For example, in the spring, you have a promotion for swimwear.</span></span> <span data-ttu-id="f5eb5-124">Pertanto, i costumi da bagno vengono inclusi in una gerarchia di categorie separata e viene applicato un prezzo promozionale alle varie categorie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-124">Therefore, you include your swimwear products in a separate category hierarchy and apply the promotional pricing to the various product categories.</span></span> |
| <span data-ttu-id="f5eb5-125">Gerarchia di navigazione</span><span class="sxs-lookup"><span data-stu-id="f5eb5-125">Navigation hierarchy</span></span>   | <span data-ttu-id="f5eb5-126">Utilizzare questo tipo di gerarchia per raggruppare e organizzare i prodotti in categorie in modo che possano essere esplorati online o nei POS.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-126">Use this hierarchy type to group and organize products into categories so that the products can be browsed online or in POS.</span></span> |

<span data-ttu-id="f5eb5-127">Utilizzando una gerarchia di categorie per strutturare i prodotti, è possibile impostare e gestire gli attributi del prodotto e le proprietà a livello di categoria.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-127">By using a category hierarchy to structure your products, you can set up and maintain product attributes and properties at the category level.</span></span> <span data-ttu-id="f5eb5-128">Tali attributi e proprietà includono le impostazioni per le dimensioni prodotto e le impostazioni del POS.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-128">These attributes and properties include settings for product dimensions and POS settings.</span></span> <span data-ttu-id="f5eb5-129">Tutti i prodotti assegnati alle categorie ereditano automaticamente gli attributi e le proprietà definiti.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-129">Any products that you assign to the categories automatically inherit the attributes and properties that you define.</span></span> <span data-ttu-id="f5eb5-130">È inoltre possibile copiare le impostazioni delle proprietà per qualsiasi prodotto a più prodotti in una categoria selezionata contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f5eb5-130">You can also copy the property settings for any product to multiple products in a selected category at the same time.</span></span>
