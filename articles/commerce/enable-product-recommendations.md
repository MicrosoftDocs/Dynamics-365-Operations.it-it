---
title: Abilitare suggerimenti sul prodotto
description: In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
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
ms.openlocfilehash: b201e5481cfaf5bb6cd64a89cdb6b5a91f31447f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413339"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="5dd31-103">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="5dd31-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5dd31-104">In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5dd31-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="5dd31-105">Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="5dd31-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="5dd31-106">Verifica preliminare dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="5dd31-106">Recommendations pre-check</span></span>

<span data-ttu-id="5dd31-107">Prima di abilitare, tenere presente che i consigli sui prodotti sono supportati solo per i clienti Commerce i quali hanno migrato il loro archivio utilizzando Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5dd31-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="5dd31-108">Le seguenti configurazioni devono essere abilitate nel back office prima di abilitare i consigli:</span><span class="sxs-lookup"><span data-stu-id="5dd31-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="5dd31-109">Assicurarsi che Azure Data Lake Storage sia stato acquistato e verificato correttamente nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="5dd31-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="5dd31-110">Per ulteriori informazioni, vedere [Assicurarsi che Azure Data Lake Storage sia stato acquistato e verificato correttamente nell'ambiente](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5dd31-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="5dd31-111">Assicurarsi che l'aggiornamento dell'archivio entità sia stato automatizzato.</span><span class="sxs-lookup"><span data-stu-id="5dd31-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="5dd31-112">Per ulteriori informazioni, vedere [Assicurarsi che l'aggiornamento dell'archivio entità sia stato automatizzato](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="5dd31-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="5dd31-113">Verificare che la configurazione dell'identità di Azure AD contiene una voce per i Consigli.</span><span class="sxs-lookup"><span data-stu-id="5dd31-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="5dd31-114">Ulteriori informazioni su come eseguire questa azione sono di seguito.</span><span class="sxs-lookup"><span data-stu-id="5dd31-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="5dd31-115">Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate.</span><span class="sxs-lookup"><span data-stu-id="5dd31-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="5dd31-116">Per ulteriori informazioni su questa procedura di configurazione, vedere [Lavorare con le misure](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="5dd31-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="5dd31-117">Configurazione dell'identità di Azure AD</span><span class="sxs-lookup"><span data-stu-id="5dd31-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="5dd31-118">Questo passaggio è necessario per tutti i clienti che eseguono una configurazione di infrastruttura distribuita come servizio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="5dd31-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="5dd31-119">Per i clienti che eseguono Service Fabric (SF) questo passaggio dovrebbe essere automatico e consigliamo di verificare che l'impostazione sia configurata come previsto.</span><span class="sxs-lookup"><span data-stu-id="5dd31-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="5dd31-120">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="5dd31-120">Setup</span></span>

1. <span data-ttu-id="5dd31-121">Dal back office, cercare la pagina **Applicazioni Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5dd31-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="5dd31-122">Verificare se esiste una voce per "RaccomandationSystemApplication-1".</span><span class="sxs-lookup"><span data-stu-id="5dd31-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="5dd31-123">Se la voce non esiste, aggiungere una nuova voce con le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="5dd31-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="5dd31-124">**ID client** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="5dd31-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="5dd31-125">**Nome** - RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="5dd31-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="5dd31-126">**ID utente** - RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="5dd31-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="5dd31-127">Salvare e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5dd31-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="5dd31-128">Attivare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="5dd31-128">Turn on recommendations</span></span>

<span data-ttu-id="5dd31-129">Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="5dd31-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="5dd31-130">In Commerce headquarters cercare **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="5dd31-130">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="5dd31-131">Selezionare **Tutto** per visualizzare un elenco delle funzionalità disponibili.</span><span class="sxs-lookup"><span data-stu-id="5dd31-131">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="5dd31-132">Nella casella di ricerca, immettere **Elementi consigliati**.</span><span class="sxs-lookup"><span data-stu-id="5dd31-132">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="5dd31-133">Selezionare la funzionalità **Suggerimenti sul prodotto**.</span><span class="sxs-lookup"><span data-stu-id="5dd31-133">Select the **Product recommendations** feature.</span></span>
1. <span data-ttu-id="5dd31-134">Nel riquadro delle proprietà **Suggerimenti sul prodotto**, selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="5dd31-134">In the **Product recommendations** properties pane, select **Enable now**.</span></span>

![Attivazione dei suggerimenti](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> <span data-ttu-id="5dd31-136">Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="5dd31-136">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="5dd31-137">Potrebbero essere necessarie diverse ore prima che gli elenchi siano disponibili e possano essere visualizzati nel punto vendita (POS) o in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5dd31-137">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="5dd31-138">Configurare i parametri degli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="5dd31-138">Configure recommendation list parameters</span></span>

<span data-ttu-id="5dd31-139">Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti.</span><span class="sxs-lookup"><span data-stu-id="5dd31-139">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="5dd31-140">È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale.</span><span class="sxs-lookup"><span data-stu-id="5dd31-140">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="5dd31-141">Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="5dd31-141">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="5dd31-142">Visualizzare suggerimenti sui dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="5dd31-142">Show recommendations on POS devices</span></span>

<span data-ttu-id="5dd31-143">Dopo avere abilitato i suggerimenti nel back office di Commerce, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout.</span><span class="sxs-lookup"><span data-stu-id="5dd31-143">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="5dd31-144">Per ulteriori informazioni su questo processo, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="5dd31-144">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="5dd31-145">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="5dd31-145">Enable personalized recommendations</span></span>

<span data-ttu-id="5dd31-146">In Dynamics 365 Commerce, i rivenditori possono rendere disponibili suggerimenti personalizzati sui prodotti (noti anche come personalizzazione).</span><span class="sxs-lookup"><span data-stu-id="5dd31-146">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="5dd31-147">In questo modo, i suggerimenti personalizzati possono essere incorporati nell'esperienza del cliente online e nel punto vendita.</span><span class="sxs-lookup"><span data-stu-id="5dd31-147">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="5dd31-148">Quando la funzionalità di personalizzazione è attivata, il sistema può associare l'acquisto di un utente e le informazioni sul prodotto per generare suggerimenti personalizzati sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="5dd31-148">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="5dd31-149">Per ulteriori informazioni su suggerimenti personalizzati, vedere [Abilitare suggerimenti personalizzati](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="5dd31-149">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5dd31-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5dd31-150">Additional resources</span></span>

[<span data-ttu-id="5dd31-151">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="5dd31-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="5dd31-152">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5dd31-152">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="5dd31-153">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="5dd31-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="5dd31-154">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="5dd31-154">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="5dd31-155">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="5dd31-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="5dd31-156">Aggiungere suggerimenti sul prodotto su POS</span><span class="sxs-lookup"><span data-stu-id="5dd31-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="5dd31-157">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="5dd31-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="5dd31-158">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="5dd31-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="5dd31-159">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="5dd31-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="5dd31-160">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="5dd31-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="5dd31-161">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="5dd31-161">Product recommendations FAQ</span></span>](faq-recommendations.md)

