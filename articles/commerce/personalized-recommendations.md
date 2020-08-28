---
title: Abilitare suggerimenti personalizzati sui prodotti
description: Questo argomento descrive come rendere disponibili suggerimenti personalizzati sui prodotti per i clienti in Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4103096f23e5568cc2bf64f21720c7c16d3e0cd1
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664860"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="22799-103">Abilitare suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="22799-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="22799-104">Questo argomento descrive come rendere disponibili suggerimenti personalizzati sui prodotti per i clienti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="22799-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="22799-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="22799-105">Overview</span></span>

<span data-ttu-id="22799-106">In Dynamics 365 Commerce, i rivenditori possono rendere disponibili suggerimenti personalizzati sui prodotti (noti anche come personalizzazione).</span><span class="sxs-lookup"><span data-stu-id="22799-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="22799-107">In questo modo, i suggerimenti personalizzati possono essere incorporati nell'esperienza cliente online e nel POS.</span><span class="sxs-lookup"><span data-stu-id="22799-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="22799-108">Quando la funzionalità di personalizzazione è attivata, il sistema può associare l'acquisto di un utente e le informazioni sul prodotto per generare suggerimenti personalizzati sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="22799-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="22799-109">Prerequisiti per la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="22799-109">Personalization prerequisites</span></span>

<span data-ttu-id="22799-110">Prima di rendere disponibili i suggerimenti consigli sui prodotti per i clienti, tenere presente che i suggerimenti sui prodotti sono supportati solo per gli utenti di Commerce che hanno migrato il loro archivio a quello di Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="22799-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="22799-111">Prima che i clienti possano ricevere suggerimenti personalizzati sui prodotti, i rivenditori devono [attivare i suggerimenti sui prodotti](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="22799-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="22799-112">Attivando i suggerimenti sui prodotti, si attiva anche la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="22799-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="22799-113">Tuttavia, se si disattiva la personalizzazione, non si disattivano gli altri tipi di suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="22799-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="22799-114">Per ulteriori informazioni relative ai suggerimenti sui prodotti, vedere [Panoramica suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="22799-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="22799-115">Attivare la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="22799-115">Turn on personalization</span></span>

<span data-ttu-id="22799-116">Per attivare la personalizzazione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="22799-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="22799-117">Andare a **Retail e Commerce \> Suggerimenti sul prodotto \> Parametri suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="22799-117">Go to **Retail and commerce \> Product recommendations \> Recommendation parameters**.</span></span>
1. <span data-ttu-id="22799-118">Nell'elenco Parametri condivisi di vendita al dettaglio, selezionare **Elenchi di suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="22799-118">In the list of Retail shared parameters, select **Recommendation lists**.</span></span>
1. <span data-ttu-id="22799-119">Impostare l'opzione **Abilita personalizzazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="22799-119">Set the **Enable personalization** option to **Yes**.</span></span>

![Attivare la personalizzazione](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="22799-121">Quando si attiva la personalizzazione, viene avviato il processo di generazione di elenchi di suggerimento personalizzati sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="22799-121">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="22799-122">Potrebbe essere necessario fino a un giorno prima che questi elenchi siano disponibili e visibili online nel POS.</span><span class="sxs-lookup"><span data-stu-id="22799-122">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="22799-123">Elenchi personalizzati</span><span class="sxs-lookup"><span data-stu-id="22799-123">Personalized lists</span></span>

<span data-ttu-id="22799-124">Oltre a consentire la personalizzazione degli elenchi generati automaticamente dal computer, il servizio di suggerimenti consente la personalizzazione dell'esperienza di individuazione dei prodotti sia online che nel POS.</span><span class="sxs-lookup"><span data-stu-id="22799-124">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="22799-125">Una volta attivata la personalizzazione, i rivenditori possono mostrare agli acquirenti elenchi personalizzati "Selezioni personalizzate" online o elenchi "Prodotti consigliati" nei terminali POS.</span><span class="sxs-lookup"><span data-stu-id="22799-125">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="22799-126">Inoltre, i rivenditori possono applicare la personalizzazione agli elenchi di suggerimenti sui prodotti esistenti e fornire la possibilità di rifiutare esplicitamente il Regolamento generale sulla protezione dei dati (GDPR) per gli utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="22799-126">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="22799-127">Se si disattiva la personalizzazione, si disattivano anche queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="22799-127">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="22799-128">Elenchi "Selezioni personalizzate" online</span><span class="sxs-lookup"><span data-stu-id="22799-128">Online "Picks for you" lists</span></span>

<span data-ttu-id="22799-129">Un elenco "Selezioni personalizzate" è un elenco AI-ML (intelligenza artificiale-machine learning) che mostra a un utente autenticato un elenco personalizzato di prodotti suggeriti.</span><span class="sxs-lookup"><span data-stu-id="22799-129">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="22799-130">Questo elenco si basa sullo storico degli acquisti omnicanale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="22799-130">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="22799-131">I suggerimenti personalizzati vengono aggiornati dinamicamente man mano che l'utente effettua più acquisti.</span><span class="sxs-lookup"><span data-stu-id="22799-131">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="22799-132">Questo tipo di elenco supporta il filtro delle categorie, di modo che i rivenditori possano mostrare le selezioni più appropriate, in base alle gerarchie di navigazione.</span><span class="sxs-lookup"><span data-stu-id="22799-132">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="22799-133">Affinché l'elenco "Selezioni personalizzate" sia visualizzato su qualsiasi pagina di e-Commerce, devono essere soddisfatti i seguenti requisiti utente:</span><span class="sxs-lookup"><span data-stu-id="22799-133">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="22799-134">Gli utenti devono aver effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="22799-134">Users must be signed in.</span></span> <span data-ttu-id="22799-135">Gli utenti anonimi non vedranno i suggerimenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="22799-135">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="22799-136">Gli utenti devono avere almeno un acquisto nel proprio account.</span><span class="sxs-lookup"><span data-stu-id="22799-136">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="22799-137">Gli utenti devono acconsentire esplicitamente a ricevere suggerimenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="22799-137">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="22799-138">La seguente illustrazione mostra un esempio di elenco "Selezioni personalizzate" in una pagina del punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="22799-138">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Elenco Selezioni personalizzate online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="22799-140">Elenchi "Prodotti consigliati" nel POS</span><span class="sxs-lookup"><span data-stu-id="22799-140">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="22799-141">Per migliorare l'esperienza di fidelizzazione dei clienti, i rivenditori possono personalizzare le pagine dei dettagli dei clienti esistenti aggiungendo un elenco contestuale "Prodotti consigliati".</span><span class="sxs-lookup"><span data-stu-id="22799-141">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="22799-142">La seguente illustrazione mostra un esempio di elenco "Prodotti consigliati" in un terminale POS.</span><span class="sxs-lookup"><span data-stu-id="22799-142">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Elenco "Prodotti consigliati" nel POS](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="22799-144">Applicare la personalizzazione a elenchi di suggerimenti esistenti</span><span class="sxs-lookup"><span data-stu-id="22799-144">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="22799-145">I rivenditori possono applicare la personalizzazione a elenchi di suggerimenti esistenti, come "Novità", "Di tendenza", "Più venduti", "Alle persone piace anche" e "Spesso acquistati insieme".</span><span class="sxs-lookup"><span data-stu-id="22799-145">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="22799-146">Quando la personalizzazione viene applicata a elenchi esistenti, gli articoli che un utente connesso ha acquistato in precedenza vengono rimossi da tali elenchi.</span><span class="sxs-lookup"><span data-stu-id="22799-146">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="22799-147">Per gli utenti anonimi e quelli che hanno rinunciato a ricevere suggerimenti personalizzati, vengono visualizzate le versioni predefinite degli elenchi esistenti.</span><span class="sxs-lookup"><span data-stu-id="22799-147">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="22799-148">Pertanto, i rivenditori non devono gestire manualmente esperienze di pagina distinte.</span><span class="sxs-lookup"><span data-stu-id="22799-148">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="22799-149">Ad esempio, un utente che ha effettuato l'accesso ha già acquistato l'orologio nero e gli stivali da lavoro marroni che compaiono nell'elenco "Di tendenza - Predefinito" nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="22799-149">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="22799-150">Pertanto, l'utente vedrà dei nuovi prodotti anziché tali prodotti, come mostrato nell'elenco "Di tendenza - Personalizzato".</span><span class="sxs-lookup"><span data-stu-id="22799-150">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Applicare la personalizzazione](./media/applypersonalization.png)

<span data-ttu-id="22799-152">Per applicare la personalizzazione a un elenco di suggerimenti esistente in Creazione di siti di Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="22799-152">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="22799-153">Aprire una pagina di Creazione di siti Web che contiene un modulo Raccolta prodotti.</span><span class="sxs-lookup"><span data-stu-id="22799-153">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="22799-154">Selezionare il modulo Raccolta prodotti nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="22799-154">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="22799-155">Selezionare l'elenco sotto **Prodotti** nel pannello di navigazione a destra.</span><span class="sxs-lookup"><span data-stu-id="22799-155">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="22799-156">Nella finestra di dialogo **Seleziona configurazione elenco di prodotti**, sotto **Tipo**, selezionare il tipo di elenco.</span><span class="sxs-lookup"><span data-stu-id="22799-156">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="22799-157">Selezionare la casella di controllo **Applica personalizzazione**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="22799-157">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Applicare la personalizzazione a un elenco Di tendenza](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="22799-159">Salvare la pagina, finalizzare la modifica e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="22799-159">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="22799-160">Dopo la pubblicazione della pagina, gli utenti che hanno effettuato l'accesso vedranno elenchi Di tendenza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="22799-160">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="22799-161">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="22799-161">Additional resources</span></span>

[<span data-ttu-id="22799-162">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="22799-162">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="22799-163">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="22799-163">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="22799-164">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="22799-164">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="22799-165">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="22799-165">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="22799-166">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="22799-166">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="22799-167">Aggiungere suggerimenti sul prodotto su POS</span><span class="sxs-lookup"><span data-stu-id="22799-167">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="22799-168">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="22799-168">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="22799-169">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="22799-169">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="22799-170">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="22799-170">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="22799-171">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="22799-171">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="22799-172">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="22799-172">Product recommendations FAQ</span></span>](faq-recommendations.md)
