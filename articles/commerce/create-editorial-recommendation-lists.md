---
title: Creare manualmente suggerimenti mirati
description: In questo argomento viene illustrato come i merchandiser possono creare e gestire manualmente elenchi di prodotti per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9826785700dcc1a35e6199b7aeff4e06b6d9da39
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665059"
---
# <a name="manually-create-curated-recommendations"></a><span data-ttu-id="dbced-103">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="dbced-103">Manually create curated recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dbced-104">In questo argomento viene illustrato come i merchandiser possono creare e gestire manualmente elenchi di suggerimenti per prodotti per i clienti di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dbced-104">This topic explains how merchandizers can manually create and manage product recommendations lists for Microsoft Dynamics 365 Commerce customers.</span></span>

<span data-ttu-id="dbced-105">Gli elenchi curati sono raccolte di singoli contenuti creati e gestiti da persone.</span><span class="sxs-lookup"><span data-stu-id="dbced-105">Curated lists are collections of individual content, created and curated by people.</span></span>  

## <a name="create-a-new-list"></a><span data-ttu-id="dbced-106">Crea un nuovo elenco</span><span class="sxs-lookup"><span data-stu-id="dbced-106">Create a new list</span></span>

<span data-ttu-id="dbced-107">Per creare un elenco curato di suggerimenti sul prodotto, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbced-107">To create a curated product recommendation list, follow these steps.</span></span>

1. <span data-ttu-id="dbced-108">Andare a **Retail e Commerce &gt; Suggerimenti sul prodotto &gt; Elenchi di suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="dbced-108">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation lists**.</span></span>
1. <span data-ttu-id="dbced-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dbced-109">Select **New**.</span></span>
1. <span data-ttu-id="dbced-110">Nel campo **ID elenco** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="dbced-110">In the **List Id** field, enter a value.</span></span>
1. <span data-ttu-id="dbced-111">Nel campo **Nome elenco** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="dbced-111">In the **List name** field, enter a value.</span></span>
    - <span data-ttu-id="dbced-112">Il campo **Nome elenco** indica il titolo dell'elenco che verrà visualizzato nella sezione degli elenchi curati del modulo **Raccolta prodotto**.</span><span class="sxs-lookup"><span data-stu-id="dbced-112">The **List name** is the title of the list that will appear in the curated lists section of the **Product collection** module.</span></span>
1. <span data-ttu-id="dbced-113">Per aggiungere prodotti all'elenco, selezionare **Aggiungi prodotti**.</span><span class="sxs-lookup"><span data-stu-id="dbced-113">To add products to the list, select **Add products**.</span></span>
1. <span data-ttu-id="dbced-114">Per modificare l'ordine dei prodotti nell'elenco, immettere un valore nella colonna **Ordine di visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="dbced-114">To change the order of the products in the list, enter a value in the **Display order** column.</span></span>
    - <span data-ttu-id="dbced-115">Se due prodotti hanno lo stesso valore di ordine di visualizzazione, l'ordine finale di quei due risultati può differire dal back office.</span><span class="sxs-lookup"><span data-stu-id="dbced-115">If two products have the same display order value, then the final order of those two results may differ from the back office.</span></span>
1. <span data-ttu-id="dbced-116">Selezionare **Salva** per salvare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="dbced-116">Select **Save** to save the list.</span></span>

## <a name="example-list"></a><span data-ttu-id="dbced-117">Esempio di elenco</span><span class="sxs-lookup"><span data-stu-id="dbced-117">Example List</span></span>

![Esempio di elenco curato nel back office](./media/examplecuratedrecolist.png)

## <a name="additional-resources"></a><span data-ttu-id="dbced-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dbced-119">Additional resources</span></span>

[<span data-ttu-id="dbced-120">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="dbced-120">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="dbced-121">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dbced-121">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="dbced-122">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="dbced-122">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="dbced-123">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="dbced-123">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="dbced-124">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="dbced-124">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="dbced-125">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="dbced-125">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="dbced-126">Aggiungere suggerimenti sul prodotto nel POS</span><span class="sxs-lookup"><span data-stu-id="dbced-126">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="dbced-127">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="dbced-127">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="dbced-128">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="dbced-128">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="dbced-129">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="dbced-129">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="dbced-130">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="dbced-130">Product recommendations FAQ</span></span>](faq-recommendations.md)
