---
title: Abilitare suggerimenti sul prodotto
description: In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024958"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="0f36f-103">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="0f36f-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0f36f-104">In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f36f-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="0f36f-105">Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0f36f-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="0f36f-106">Verifica preliminare dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="0f36f-106">Recommendations pre-check</span></span>

<span data-ttu-id="0f36f-107">Prima di abilitare i suggerimenti sul prodotto, è necessario notare che questi sono supportati solo per i clienti Commerce che hanno eseguito la migrazione del proprio spazio di archiviazione utilizzando Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="0f36f-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="0f36f-108">Per i passaggi sull'abilitazione di ADLS, vedere [Come abilitare ADLS in un ambiente Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0f36f-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="0f36f-109">Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate.</span><span class="sxs-lookup"><span data-stu-id="0f36f-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="0f36f-110">Per ulteriori informazioni su questo processo di impostazione, vedere [qui.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="0f36f-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="0f36f-111">Attivare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="0f36f-111">Turn on recommendations</span></span>

<span data-ttu-id="0f36f-112">Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="0f36f-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="0f36f-113">Andare a **Retail e Commerce &gt; Suggerimenti sul prodotto &gt; Parametri suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="0f36f-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="0f36f-114">Nell'elenco dei parametri condivisi, selezionare **Elenchi suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="0f36f-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="0f36f-115">Impostare l'opzione **Abilita suggerimenti** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="0f36f-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![Abilitare i suggerimenti sul prodotto](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="0f36f-117">Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="0f36f-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="0f36f-118">Questo processo può durare varie ore ed è visibile sul POS o in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f36f-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="0f36f-119">Configurare i parametri degli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="0f36f-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="0f36f-120">Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti.</span><span class="sxs-lookup"><span data-stu-id="0f36f-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="0f36f-121">È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale.</span><span class="sxs-lookup"><span data-stu-id="0f36f-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="0f36f-122">Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="0f36f-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="0f36f-123">Visualizzare suggerimenti sui dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="0f36f-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="0f36f-124">Dopo avere abilitato i suggerimenti nel back office di Commerce, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout.</span><span class="sxs-lookup"><span data-stu-id="0f36f-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="0f36f-125">Per ulteriori informazioni su questo processo, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="0f36f-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="0f36f-126">Abilitare suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="0f36f-126">Enable personalized recommendations</span></span>

<span data-ttu-id="0f36f-127">Per ulteriori informazioni su come ricevere suggerimenti personalizzati, vedere [Abilitare suggerimenti personalizzati](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0f36f-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f36f-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0f36f-128">Additional resources</span></span>

[<span data-ttu-id="0f36f-129">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="0f36f-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="0f36f-130">Abilitare suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="0f36f-130">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="0f36f-131">Aggiungere elenchi di suggerimenti sul prodotto alle pagine</span><span class="sxs-lookup"><span data-stu-id="0f36f-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="0f36f-132">Aggiungere il pannello dei suggerimenti a dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="0f36f-132">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="0f36f-133">Panoramica del modulo di raccolta prodotti</span><span class="sxs-lookup"><span data-stu-id="0f36f-133">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="0f36f-134">Abilitare ADLS nell'ambiente Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0f36f-134">Enable ADLS in Dynamics 365 environment</span></span>](enable-ADLS-environment.md)

