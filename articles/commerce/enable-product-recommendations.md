---
title: Abilitare suggerimenti sul prodotto
description: In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2dacd4a94f706be5aa65947c0b6a92e281733ca
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665028"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="348df-103">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="348df-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="348df-104">In questo argomento viene descritto come abilitare i suggerimenti sul prodotto basati su intelligenza artificiale-machine learning (AI-ML) disponibili per i clienti di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="348df-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="348df-105">Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="348df-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="348df-106">Verifica preliminare dei suggerimenti</span><span class="sxs-lookup"><span data-stu-id="348df-106">Recommendations pre-check</span></span>

<span data-ttu-id="348df-107">Prima di abilitare, tenere presente che i consigli sui prodotti sono supportati solo per i clienti Commerce i quali hanno migrato il loro archivio utilizzando Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="348df-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="348df-108">Le seguenti configurazioni devono essere abilitate nel back office prima di abilitare i consigli:</span><span class="sxs-lookup"><span data-stu-id="348df-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="348df-109">Assicurarsi che Azure Data Lake Storage sia stato acquistato e verificato correttamente nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="348df-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="348df-110">Per ulteriori informazioni, vedere [Assicurarsi che Azure Data Lake Storage sia stato acquistato e verificato correttamente nell'ambiente](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="348df-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="348df-111">Assicurarsi che l'aggiornamento dell'archivio entità sia stato automatizzato.</span><span class="sxs-lookup"><span data-stu-id="348df-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="348df-112">Per ulteriori informazioni, vedere [Assicurarsi che l'aggiornamento dell'archivio entità sia stato automatizzato](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="348df-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="348df-113">Verificare che la configurazione dell'identità di Azure AD contiene una voce per i Consigli.</span><span class="sxs-lookup"><span data-stu-id="348df-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="348df-114">Ulteriori informazioni su come eseguire questa azione sono di seguito.</span><span class="sxs-lookup"><span data-stu-id="348df-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="348df-115">Assicurarsi inoltre che le misurazioni RetailSale siano state abilitate.</span><span class="sxs-lookup"><span data-stu-id="348df-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="348df-116">Per ulteriori informazioni su questa procedura di configurazione, vedere [Lavorare con le misure](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="348df-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="348df-117">Configurazione dell'identità di Azure AD</span><span class="sxs-lookup"><span data-stu-id="348df-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="348df-118">Questo passaggio è necessario per tutti i clienti che eseguono una configurazione di infrastruttura distribuita come servizio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="348df-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="348df-119">Per i clienti che eseguono Service Fabric (SF) questo passaggio dovrebbe essere automatico e consigliamo di verificare che l'impostazione sia configurata come previsto.</span><span class="sxs-lookup"><span data-stu-id="348df-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="348df-120">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="348df-120">Setup</span></span>

1. <span data-ttu-id="348df-121">Dal back office, cercare la pagina **Applicazioni Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="348df-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="348df-122">Verificare se esiste una voce per "RaccomandationSystemApplication-1".</span><span class="sxs-lookup"><span data-stu-id="348df-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="348df-123">Se la voce non esiste, aggiungere una nuova voce con le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="348df-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="348df-124">**ID client** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="348df-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="348df-125">**Nome** - RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="348df-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="348df-126">**ID utente** - RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="348df-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="348df-127">Salvare e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="348df-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="348df-128">Attivare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="348df-128">Turn on recommendations</span></span>

<span data-ttu-id="348df-129">Per attivare i suggerimenti sul prodotto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="348df-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="348df-130">Andare a **Retail e Commerce &gt; Suggerimenti sul prodotto &gt; Parametri suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="348df-130">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="348df-131">Nell'elenco dei parametri condivisi, selezionare **Elenchi suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="348df-131">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="348df-132">Impostare l'opzione **Abilita suggerimenti** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="348df-132">Set the **Enable recommendations** option to **Yes**.</span></span>

![Attivazione dei suggerimenti](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="348df-134">Questa procedura avvia il processo di generazione di elenchi di suggerimenti sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="348df-134">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="348df-135">Potrebbero essere necessarie diverse ore prima che gli elenchi siano disponibili e possano essere visualizzati nel punto vendita (POS) o in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="348df-135">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="348df-136">Configurare i parametri degli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="348df-136">Configure recommendation list parameters</span></span>

<span data-ttu-id="348df-137">Per impostazione predefinita, l'elenco di suggerimenti sul prodotto basati su AI ML fornisce valori suggeriti.</span><span class="sxs-lookup"><span data-stu-id="348df-137">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="348df-138">È possibile modificare i valori suggeriti predefiniti in base al flusso aziendale.</span><span class="sxs-lookup"><span data-stu-id="348df-138">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="348df-139">Per ulteriori informazioni su come modificare i parametri predefiniti, accedere a [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="348df-139">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="348df-140">Visualizzare suggerimenti sui dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="348df-140">Show recommendations on POS devices</span></span>

<span data-ttu-id="348df-141">Dopo avere abilitato i suggerimenti nel back office di Commerce, è necessario aggiungere il pannello dei suggerimenti alla schermata del POS di controllo mediante lo strumento di layout.</span><span class="sxs-lookup"><span data-stu-id="348df-141">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="348df-142">Per ulteriori informazioni su questo processo, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="348df-142">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="348df-143">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="348df-143">Enable personalized recommendations</span></span>

<span data-ttu-id="348df-144">In Dynamics 365 Commerce, i rivenditori possono rendere disponibili suggerimenti personalizzati sui prodotti (noti anche come personalizzazione).</span><span class="sxs-lookup"><span data-stu-id="348df-144">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="348df-145">In questo modo, i suggerimenti personalizzati possono essere incorporati nell'esperienza del cliente online e nel punto vendita.</span><span class="sxs-lookup"><span data-stu-id="348df-145">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="348df-146">Quando la funzionalità di personalizzazione è attivata, il sistema può associare l'acquisto di un utente e le informazioni sul prodotto per generare suggerimenti personalizzati sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="348df-146">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="348df-147">Per ulteriori informazioni su suggerimenti personalizzati, vedere [Abilitare suggerimenti personalizzati](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="348df-147">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="348df-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="348df-148">Additional resources</span></span>

[<span data-ttu-id="348df-149">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="348df-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="348df-150">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="348df-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="348df-151">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="348df-151">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="348df-152">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="348df-152">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="348df-153">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="348df-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="348df-154">Aggiungere suggerimenti sul prodotto su POS</span><span class="sxs-lookup"><span data-stu-id="348df-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="348df-155">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="348df-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="348df-156">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="348df-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="348df-157">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="348df-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="348df-158">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="348df-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="348df-159">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="348df-159">Product recommendations FAQ</span></span>](faq-recommendations.md)

