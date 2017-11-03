---
title: Impostare codici a barre
description: Questo articolo descrive come usare i codici a barre in Microsoft Dynamics 365 for Retail.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bfb47e653cc3ef36135fd7c4f60771a354699af7
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-bar-codes"></a><span data-ttu-id="82bd1-103">Impostare codici a barre</span><span class="sxs-lookup"><span data-stu-id="82bd1-103">Set up bar codes</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="82bd1-104">Questo articolo descrive come usare i codici a barre in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="82bd1-104">This article describes how to use bar codes in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="82bd1-105">È possibile utilizzare i codici a barre per acquistare o vendere prodotti, tenere traccia delle varianti prodotto e impostare clienti e dipendenti.</span><span class="sxs-lookup"><span data-stu-id="82bd1-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="82bd1-106">È inoltre possibile utilizzare i codici a barre per emettere e approvare buoni sconto, gift card e note di credito.</span><span class="sxs-lookup"><span data-stu-id="82bd1-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="82bd1-107">È possibile impostare prodotti al dettaglio in modo che abbiano codici a barre standard o interni personalizzati.</span><span class="sxs-lookup"><span data-stu-id="82bd1-107">You can set up retail products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="82bd1-108">I prodotti possono avere più di un codice a barre.</span><span class="sxs-lookup"><span data-stu-id="82bd1-108">Products can have more than one bar code.</span></span> <span data-ttu-id="82bd1-109">Ad esempio, un prodotto può avere più codici a barre se il prodotto proviene da diversi produttori o se dispone di varianti in base a dimensioni, stile o colore.</span><span class="sxs-lookup"><span data-stu-id="82bd1-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="82bd1-110">I codici a barre possono includere il peso o il prezzo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="82bd1-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="82bd1-111">Le maschere codice a barre sono modelli utilizzati per creare codici a barre.</span><span class="sxs-lookup"><span data-stu-id="82bd1-111">Bar code masks are templates that are used to create bar codes.</span></span> <span data-ttu-id="82bd1-112">**Nota:** l'assegnazione di un codice a barre univoco a ogni combinazione di varianti consente di eseguire la scansione del codice a barre nel registratore di cassa e individuare automaticamente la variante del prodotto venduta.</span><span class="sxs-lookup"><span data-stu-id="82bd1-112">**Note:** If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="82bd1-113">È anche possibile raccogliere e visualizzare statistiche delle vendite a livello di varianti.</span><span class="sxs-lookup"><span data-stu-id="82bd1-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="82bd1-114">A ogni gruppo di dimensioni, colori e stili può essere assegnato un numero univoco che lo identifica nel codice a barre.</span><span class="sxs-lookup"><span data-stu-id="82bd1-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="82bd1-115">La maschera codice a barre viene utilizzata da Dynamics 365 for Retail per generare automaticamente codici a barre per ogni combinazione di varianti.</span><span class="sxs-lookup"><span data-stu-id="82bd1-115">Dynamics 365 for Retail uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="82bd1-116">Tale funzionalità può essere utile in presenza di un gran numero di dimensioni, colori e stili poiché le combinazioni aumentano in modo significativo con ogni codice di variante aggiunto.</span><span class="sxs-lookup"><span data-stu-id="82bd1-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="82bd1-117">Se non si utilizza questa funzionalità, è necessario assegnare manualmente i codici a barre a ogni combinazione che rappresenta una variante di prodotto.</span><span class="sxs-lookup"><span data-stu-id="82bd1-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span> <span data-ttu-id="82bd1-118">È possibile creare i codici a barre manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="82bd1-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="82bd1-119">Per creare i codici a barre, completare le seguenti attività nell'ordine in cui sono elencate.</span><span class="sxs-lookup"><span data-stu-id="82bd1-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1.  <span data-ttu-id="82bd1-120">[Impostare caratteri di maschera codice a barre](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="82bd1-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2.  <span data-ttu-id="82bd1-121">[Impostare le maschere codice a barre](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="82bd1-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3.  <span data-ttu-id="82bd1-122">Configurare le impostazioni dei codici a barre.</span><span class="sxs-lookup"><span data-stu-id="82bd1-122">Configure bar code setups.</span></span>
4.  <span data-ttu-id="82bd1-123">Creare codici a barre per prodotti.</span><span class="sxs-lookup"><span data-stu-id="82bd1-123">Create bar codes for products.</span></span>


<a name="see-also"></a><span data-ttu-id="82bd1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82bd1-124">See also</span></span>
--------

[<span data-ttu-id="82bd1-125">Impostare le maschere codice a barre</span><span class="sxs-lookup"><span data-stu-id="82bd1-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)




