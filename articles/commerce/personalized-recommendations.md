---
title: Abilitare suggerimenti personalizzati sui prodotti
description: Questo argomento descrive come rendere disponibili suggerimenti personalizzati sui prodotti per i clienti in Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f535cf0bc3c733426af22cf453ffe97f721f8d9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000585"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="313cf-103">Abilitare suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="313cf-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="313cf-104">Questo argomento descrive come rendere disponibili suggerimenti personalizzati sui prodotti per i clienti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="313cf-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="313cf-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="313cf-105">Overview</span></span>

<span data-ttu-id="313cf-106">In Dynamics 365 Commerce, i rivenditori possono rendere disponibili suggerimenti personalizzati sui prodotti (noti anche come personalizzazione).</span><span class="sxs-lookup"><span data-stu-id="313cf-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="313cf-107">In questo modo, i suggerimenti personalizzati possono essere incorporati nell'esperienza cliente online e nel POS.</span><span class="sxs-lookup"><span data-stu-id="313cf-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="313cf-108">Quando la funzionalità di personalizzazione è attivata, il sistema può associare l'acquisto di un utente e le informazioni sul prodotto per generare suggerimenti personalizzati sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="313cf-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="313cf-109">Prerequisiti per la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="313cf-109">Personalization prerequisites</span></span>

<span data-ttu-id="313cf-110">Prima di rendere disponibili i suggerimenti consigli sui prodotti per i clienti, tenere presente che i suggerimenti sui prodotti sono supportati solo per gli utenti di Commerce che hanno migrato il loro archivio a quello di Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="313cf-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="313cf-111">Prima che i clienti possano ricevere suggerimenti personalizzati sui prodotti, i rivenditori devono [attivare i suggerimenti sui prodotti](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="313cf-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="313cf-112">Attivando i suggerimenti sui prodotti, si attiva anche la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="313cf-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="313cf-113">Tuttavia, se si disattiva la personalizzazione, non si disattivano gli altri tipi di suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="313cf-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="313cf-114">Per ulteriori informazioni relative ai suggerimenti sui prodotti, vedere [Panoramica suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="313cf-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="313cf-115">Attivare la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="313cf-115">Turn on personalization</span></span>

<span data-ttu-id="313cf-116">Per attivare la personalizzazione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="313cf-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="313cf-117">In Commerce headquarters cercare **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="313cf-117">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="313cf-118">Selezionare **Tutto** per visualizzare un elenco delle funzionalità disponibili.</span><span class="sxs-lookup"><span data-stu-id="313cf-118">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="313cf-119">Nella casella di ricerca, immettere **Elementi consigliati**.</span><span class="sxs-lookup"><span data-stu-id="313cf-119">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="313cf-120">Selezionare la funzionalità **Suggerimenti sul prodotto personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="313cf-120">Select the **Personalized product recommendations** feature.</span></span>
1. <span data-ttu-id="313cf-121">Nel riquadro delle proprietà **Suggerimenti sul prodotto personalizzato**, selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="313cf-121">In the **Personalized product recommendations** properties pane, select **Enable now**.</span></span>

![Attivare la personalizzazione](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> <span data-ttu-id="313cf-123">Quando si attiva la personalizzazione, viene avviato il processo di generazione di elenchi di suggerimento personalizzati sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="313cf-123">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="313cf-124">Potrebbe essere necessario fino a un giorno prima che questi elenchi siano disponibili e visibili online nel POS.</span><span class="sxs-lookup"><span data-stu-id="313cf-124">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="313cf-125">Elenchi personalizzati</span><span class="sxs-lookup"><span data-stu-id="313cf-125">Personalized lists</span></span>

<span data-ttu-id="313cf-126">Oltre a consentire la personalizzazione degli elenchi generati automaticamente dal computer, il servizio di suggerimenti consente la personalizzazione dell'esperienza di individuazione dei prodotti sia online che nel POS.</span><span class="sxs-lookup"><span data-stu-id="313cf-126">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="313cf-127">Una volta attivata la personalizzazione, i rivenditori possono mostrare agli acquirenti elenchi personalizzati "Selezioni personalizzate" online o elenchi "Prodotti consigliati" nei terminali POS.</span><span class="sxs-lookup"><span data-stu-id="313cf-127">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="313cf-128">Inoltre, i rivenditori possono applicare la personalizzazione agli elenchi di suggerimenti sui prodotti esistenti e fornire la possibilità di rifiutare esplicitamente il Regolamento generale sulla protezione dei dati (GDPR) per gli utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="313cf-128">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="313cf-129">Se si disattiva la personalizzazione, si disattivano anche queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="313cf-129">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="313cf-130">Elenchi "Selezioni personalizzate" online</span><span class="sxs-lookup"><span data-stu-id="313cf-130">Online "Picks for you" lists</span></span>

<span data-ttu-id="313cf-131">Un elenco "Selezioni personalizzate" è un elenco AI-ML (intelligenza artificiale-machine learning) che mostra a un utente autenticato un elenco personalizzato di prodotti suggeriti.</span><span class="sxs-lookup"><span data-stu-id="313cf-131">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="313cf-132">Questo elenco si basa sullo storico degli acquisti omnicanale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="313cf-132">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="313cf-133">I suggerimenti personalizzati vengono aggiornati dinamicamente man mano che l'utente effettua più acquisti.</span><span class="sxs-lookup"><span data-stu-id="313cf-133">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="313cf-134">Questo tipo di elenco supporta il filtro delle categorie, di modo che i rivenditori possano mostrare le selezioni più appropriate, in base alle gerarchie di navigazione.</span><span class="sxs-lookup"><span data-stu-id="313cf-134">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="313cf-135">Affinché l'elenco "Selezioni personalizzate" sia visualizzato su qualsiasi pagina di e-Commerce, devono essere soddisfatti i seguenti requisiti utente:</span><span class="sxs-lookup"><span data-stu-id="313cf-135">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="313cf-136">Gli utenti devono aver effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="313cf-136">Users must be signed in.</span></span> <span data-ttu-id="313cf-137">Gli utenti anonimi non vedranno i suggerimenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="313cf-137">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="313cf-138">Gli utenti devono avere almeno un acquisto nel proprio account.</span><span class="sxs-lookup"><span data-stu-id="313cf-138">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="313cf-139">Gli utenti devono acconsentire esplicitamente a ricevere suggerimenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="313cf-139">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="313cf-140">La seguente illustrazione mostra un esempio di elenco "Selezioni personalizzate" in una pagina del punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="313cf-140">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Elenco Selezioni personalizzate online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="313cf-142">Elenchi "Prodotti consigliati" nel POS</span><span class="sxs-lookup"><span data-stu-id="313cf-142">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="313cf-143">Per migliorare l'esperienza di fidelizzazione dei clienti, i rivenditori possono personalizzare le pagine dei dettagli dei clienti esistenti aggiungendo un elenco contestuale "Prodotti consigliati".</span><span class="sxs-lookup"><span data-stu-id="313cf-143">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="313cf-144">La seguente illustrazione mostra un esempio di elenco "Prodotti consigliati" in un terminale POS.</span><span class="sxs-lookup"><span data-stu-id="313cf-144">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Elenco "Prodotti consigliati" nel POS](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="313cf-146">Applicare la personalizzazione a elenchi di suggerimenti esistenti</span><span class="sxs-lookup"><span data-stu-id="313cf-146">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="313cf-147">I rivenditori possono applicare la personalizzazione a elenchi di suggerimenti esistenti, come "Novità", "Di tendenza", "Più venduti", "Alle persone piace anche" e "Spesso acquistati insieme".</span><span class="sxs-lookup"><span data-stu-id="313cf-147">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="313cf-148">Quando la personalizzazione viene applicata a elenchi esistenti, gli articoli che un utente connesso ha acquistato in precedenza vengono rimossi da tali elenchi.</span><span class="sxs-lookup"><span data-stu-id="313cf-148">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="313cf-149">Per gli utenti anonimi e quelli che hanno rinunciato a ricevere suggerimenti personalizzati, vengono visualizzate le versioni predefinite degli elenchi esistenti.</span><span class="sxs-lookup"><span data-stu-id="313cf-149">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="313cf-150">Pertanto, i rivenditori non devono gestire manualmente esperienze di pagina distinte.</span><span class="sxs-lookup"><span data-stu-id="313cf-150">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="313cf-151">Ad esempio, un utente che ha effettuato l'accesso ha già acquistato l'orologio nero e gli stivali da lavoro marroni che compaiono nell'elenco "Di tendenza - Predefinito" nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="313cf-151">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="313cf-152">Pertanto, l'utente vedrà dei nuovi prodotti anziché tali prodotti, come mostrato nell'elenco "Di tendenza - Personalizzato".</span><span class="sxs-lookup"><span data-stu-id="313cf-152">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Applicare la personalizzazione](./media/applypersonalization.png)

<span data-ttu-id="313cf-154">Per applicare la personalizzazione a un elenco di suggerimenti esistente in Creazione di siti di Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="313cf-154">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="313cf-155">Aprire una pagina di Creazione di siti Web che contiene un modulo Raccolta prodotti.</span><span class="sxs-lookup"><span data-stu-id="313cf-155">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="313cf-156">Selezionare il modulo Raccolta prodotti nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="313cf-156">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="313cf-157">Selezionare l'elenco sotto **Prodotti** nel pannello di navigazione a destra.</span><span class="sxs-lookup"><span data-stu-id="313cf-157">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="313cf-158">Nella finestra di dialogo **Seleziona configurazione elenco di prodotti**, sotto **Tipo**, selezionare il tipo di elenco.</span><span class="sxs-lookup"><span data-stu-id="313cf-158">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="313cf-159">Selezionare la casella di controllo **Applica personalizzazione**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="313cf-159">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Applicare la personalizzazione a un elenco Di tendenza](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="313cf-161">Salvare la pagina, finalizzare la modifica e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="313cf-161">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="313cf-162">Dopo la pubblicazione della pagina, gli utenti che hanno effettuato l'accesso vedranno elenchi Di tendenza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="313cf-162">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="313cf-163">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="313cf-163">Additional resources</span></span>

[<span data-ttu-id="313cf-164">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="313cf-164">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="313cf-165">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="313cf-165">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="313cf-166">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="313cf-166">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="313cf-167">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="313cf-167">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="313cf-168">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="313cf-168">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="313cf-169">Aggiungere suggerimenti sul prodotto su POS</span><span class="sxs-lookup"><span data-stu-id="313cf-169">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="313cf-170">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="313cf-170">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="313cf-171">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="313cf-171">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="313cf-172">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="313cf-172">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="313cf-173">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="313cf-173">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="313cf-174">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="313cf-174">Product recommendations FAQ</span></span>](faq-recommendations.md)
