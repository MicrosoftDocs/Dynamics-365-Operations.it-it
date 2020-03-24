---
title: Abilitare suggerimenti sul prodotto
description: In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 879fccb063ca0b74e0f022a9edf6a15f7d1311ae
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127884"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="639ca-103">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="639ca-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="639ca-104">In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="639ca-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="639ca-105">Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="639ca-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="639ca-106">Verifica preliminare dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="639ca-106">Recommendations pre-check</span></span>

<span data-ttu-id="639ca-107">Prima di abilitare i suggerimenti sul prodotto, è necessario notare che questi sono supportati solo per i clienti Commerce che hanno eseguito la migrazione del proprio spazio di archiviazione utilizzando Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="639ca-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="639ca-108">Per i passaggi sull'abilitazione di ADLS, vedere [Come abilitare ADLS in un ambiente Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="639ca-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="639ca-109">Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate.</span><span class="sxs-lookup"><span data-stu-id="639ca-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="639ca-110">Per ulteriori informazioni su questo processo di impostazione, vedere [qui.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="639ca-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="639ca-111">Attivare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="639ca-111">Turn on recommendations</span></span>

<span data-ttu-id="639ca-112">Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="639ca-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="639ca-113">Andare a **Retail e Commerce &gt; Suggerimenti sul prodotto &gt; Parametri suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="639ca-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="639ca-114">Nell'elenco dei parametri condivisi, selezionare **Elenchi suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="639ca-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="639ca-115">Impostare l'opzione **Abilita suggerimenti** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="639ca-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![Abilitare i suggerimenti sul prodotto](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="639ca-117">Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="639ca-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="639ca-118">Questo processo può durare varie ore ed è visibile sul POS o in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="639ca-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="639ca-119">Configurare i parametri degli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="639ca-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="639ca-120">Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti.</span><span class="sxs-lookup"><span data-stu-id="639ca-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="639ca-121">È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale.</span><span class="sxs-lookup"><span data-stu-id="639ca-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="639ca-122">Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="639ca-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="639ca-123">Visualizzare suggerimenti sui dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="639ca-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="639ca-124">Dopo avere abilitato i suggerimenti nel back office di Commerce, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout.</span><span class="sxs-lookup"><span data-stu-id="639ca-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="639ca-125">Per ulteriori informazioni su questo processo, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="639ca-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="639ca-126">Abilitare suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="639ca-126">Enable personalized recommendations</span></span>

<span data-ttu-id="639ca-127">Per ulteriori informazioni su come ricevere suggerimenti personalizzati, vedere [Abilitare suggerimenti personalizzati](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="639ca-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="639ca-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="639ca-128">Additional resources</span></span>

[<span data-ttu-id="639ca-129">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="639ca-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="639ca-130">Abilitare ADLS in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="639ca-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="639ca-131">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="639ca-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="639ca-132">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="639ca-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="639ca-133">Aggiungere elenchi di suggerimenti a un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="639ca-133">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="639ca-134">Aggiungere suggerimenti sul prodotto su POS</span><span class="sxs-lookup"><span data-stu-id="639ca-134">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="639ca-135">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="639ca-135">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="639ca-136">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="639ca-136">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="639ca-137">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="639ca-137">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="639ca-138">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="639ca-138">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="639ca-139">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="639ca-139">Product recommendations FAQ</span></span>](faq-recommendations.md)

