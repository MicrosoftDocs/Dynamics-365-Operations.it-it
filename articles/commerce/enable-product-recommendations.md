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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770141"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="368b7-103">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="368b7-103">Enable product recommendations</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="368b7-104">In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="368b7-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="368b7-105">Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="368b7-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="368b7-106">Verifica preliminare dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="368b7-106">Recommendations pre-check</span></span>
<span data-ttu-id="368b7-107">Prima di abilitare i suggerimenti sul prodotto, è necessario notare che questi sono supportati solo per i clienti F&O che supportano la build 10.0.6 e che hanno eseguito la migrazione del proprio spazio di archiviazione utilizzando BDL.</span><span class="sxs-lookup"><span data-stu-id="368b7-107">Before enabling, please note that product recommendations are only supported for F&O customers supporting build 10.0.6 and have migrated their storage to using BDL.</span></span> 

<span data-ttu-id="368b7-108">Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate.</span><span class="sxs-lookup"><span data-stu-id="368b7-108">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="368b7-109">Per ulteriori informazioni su questo processo di impostazione, vedere [qui.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="368b7-109">To Learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="368b7-110">Attivare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="368b7-110">Turn on recommendations</span></span>

<span data-ttu-id="368b7-111">Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="368b7-111">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="368b7-112">Andare a **Vendita al dettaglio** &gt; **Suggerimenti sul prodotto** &gt; **Parametri suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="368b7-112">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation parameters**.</span></span>
1. <span data-ttu-id="368b7-113">Nell'elenco dei parametri di vendita al dettaglio condivisi, selezionare **Elenchi suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="368b7-113">In the list of retail shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="368b7-114">Impostare l'opzione **Abilita suggerimenti** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="368b7-114">Set the **Enable recommendations** option to **Yes**.</span></span>

![Abilitare i suggerimenti sul prodotto](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="368b7-116">Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="368b7-116">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="368b7-117">Questo processo può durare varie ore ed è visibile sul POS o in Dynamics 365 for Commerce.</span><span class="sxs-lookup"><span data-stu-id="368b7-117">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 for Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="368b7-118">Configurare i parametri degli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="368b7-118">Configure recommendation list parameters</span></span>
<span data-ttu-id="368b7-119">Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti.</span><span class="sxs-lookup"><span data-stu-id="368b7-119">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="368b7-120">È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale.</span><span class="sxs-lookup"><span data-stu-id="368b7-120">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="368b7-121">Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="368b7-121">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="368b7-122">Visualizzare suggerimenti sui dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="368b7-122">Show recommendations on POS devices</span></span>
<span data-ttu-id="368b7-123">Dopo avere abilitato i suggerimenti nel back office, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout.</span><span class="sxs-lookup"><span data-stu-id="368b7-123">After enabling recommendations in the back office, the recommendations pannel must be added to the control POS screen via the layout tool.</span></span> <span data-ttu-id="368b7-124">Per ulteriori informazioni su questo processo, vedere [qui.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span><span class="sxs-lookup"><span data-stu-id="368b7-124">To learn about this process, go [here.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span></span>


## <a name="additional-resources"></a><span data-ttu-id="368b7-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="368b7-125">Additional resources</span></span>

[<span data-ttu-id="368b7-126">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="368b7-126">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="368b7-127">Aggiungere elenchi di suggerimenti sul prodotto alle pagine</span><span class="sxs-lookup"><span data-stu-id="368b7-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="368b7-128">Aggiungere il pannello dei suggerimenti a dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="368b7-128">Add recommendations panel to POS devices</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


