---
title: Rifiuto esplicito dei suggerimenti personalizzati
description: Questo argomento descrive come è possibile consentire ai clienti di rifiutare esplicitamente i suggerimenti personalizzati in Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 01/28/2020
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
ms.openlocfilehash: 8e7b800218f68167901d86d61ae483680a04cfab
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025258"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="309f1-103">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="309f1-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="309f1-104">Questo argomento descrive come è possibile consentire ai clienti di rifiutare esplicitamente i suggerimenti personalizzati in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="309f1-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="309f1-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="309f1-105">Overview</span></span>

<span data-ttu-id="309f1-106">Durante la creazione dell'account, la ricezione di suggerimenti personalizzati è impostata automaticamente per i nuovi clienti.</span><span class="sxs-lookup"><span data-stu-id="309f1-106">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="309f1-107">Tuttavia, Dynamics 365 Commerce offre vari modi ai rivenditori per consentire agli utenti di rifiutare questi suggerimenti e limitare il trattamento dei loro dati personali.</span><span class="sxs-lookup"><span data-stu-id="309f1-107">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="309f1-108">Per gli utenti autenticati che rinunciano a ricevere suggerimenti personalizzati, la visualizzazione degli elenchi personalizzati viene sospesa immediatamente.</span><span class="sxs-lookup"><span data-stu-id="309f1-108">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="309f1-109">Inoltre, tutti i dati personali raccolti per la personalizzazione verranno rimossi dai modelli di suggerimenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="309f1-109">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="309f1-110">Per ulteriori informazioni sui suggerimenti personalizzati relativi ai prodotti, vedere [Abilitare i suggerimenti personalizzati](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="309f1-110">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="309f1-111">Metodi di implementazione di un'esperienza di rifiuto esplicito</span><span class="sxs-lookup"><span data-stu-id="309f1-111">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="309f1-112">I rivenditori hanno a disposizione 3 metodi di implementazione di un'esperienza di rifiuto esplicito.</span><span class="sxs-lookup"><span data-stu-id="309f1-112">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="309f1-113">Rifiuto per conto degli utenti</span><span class="sxs-lookup"><span data-stu-id="309f1-113">Opting out on behalf of users</span></span>

<span data-ttu-id="309f1-114">Nella gestione degli account nel back office di Commerce, i rivenditori possono attivare il rifiuto per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="309f1-114">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="309f1-115">Dalla home page del back office, cercare **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="309f1-115">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="309f1-116">Cercare e seleziona un cliente, quindi selezionare la scheda dettaglio **Vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="309f1-116">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Scheda dettaglio Vendita al dettaglio](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="309f1-118">Sotto **Privacy**, impostare l'opzione **Disabilita personalizzazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="309f1-118">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Impostazioni di privacy](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="309f1-120">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="309f1-120">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="309f1-121">Esperienza di rifiuto basata su moduli</span><span class="sxs-lookup"><span data-stu-id="309f1-121">Module-based opt-out experience</span></span>

<span data-ttu-id="309f1-122">I rivenditori possono consentire agli utenti autenticati di rifiutare personalmente i suggerimenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="309f1-122">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="309f1-123">Per fornire questa esperienza di rifiuto, aggiungere il modulo di rifiuto esplicito dell'utente alle pagine del profilo dell'account cliente.</span><span class="sxs-lookup"><span data-stu-id="309f1-123">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="309f1-124">Estensioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="309f1-124">Custom extensions</span></span>

<span data-ttu-id="309f1-125">I rivenditori possono creare estensioni personalizzate per gestire l'esperienza di rifiuto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="309f1-125">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="309f1-126">Per ulteriori informazioni, vedere [Chiamare API Retail Server](e-commerce-extensibility/call-retail-server-apis.md)e [Estendibilità del canale online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="309f1-126">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="309f1-127">Ottenere una copia digitale dei dati dei suggerimenti personalizzati per conto di un utente autenticato</span><span class="sxs-lookup"><span data-stu-id="309f1-127">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="309f1-128">È possibile che i clienti vogliano ottenere una copia digitale dei propri dati personali e una vista esportata dei risultati dei loro suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="309f1-128">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="309f1-129">Se un cliente richiede queste informazioni, il rivenditore deve creare un'estensione personalizzata che chiama l'API Retail Server e che esegue una query per i risultati completi dall'elenco **Selezioni personalizzate** in base all'ID del cliente.</span><span class="sxs-lookup"><span data-stu-id="309f1-129">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="309f1-130">I risultati possono quindi essere esportati in formato CSV e condivisi con il cliente.</span><span class="sxs-lookup"><span data-stu-id="309f1-130">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="309f1-131">L'esempio seguente mostra come un rivenditore può eseguire questa attività.</span><span class="sxs-lookup"><span data-stu-id="309f1-131">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="309f1-132">Il rivenditore crea un'estensione personalizzata per estrarre i dati dei suggerimenti personali per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="309f1-132">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="309f1-133">Per informazioni su come creare moduli, clonare moduli esistenti, chiamare le API Retail Server e chiamare azioni sui dati, vedere [Estendibilità del canale online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="309f1-133">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="309f1-134">L'estensione personalizzata chiama l'azione **get-recommendations** sui dati core e passa le informazioni richieste alla stessa, in base ai requisiti dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="309f1-134">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="309f1-135">Nel caso dell'elenco **Selezioni personalizzate**, l'estensione deve passare il nome di elenco e l'ID cliente corretti all'azione dati.</span><span class="sxs-lookup"><span data-stu-id="309f1-135">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="309f1-136">Un modo per creare l'estensione personalizzata è clonare il modulo di raccolta prodotti esistente utilizzato per restituire i risultati dei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="309f1-136">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="309f1-137">Clonando questo modulo esistente, un rivenditore può modificare il codice esistente e aggiungere un nuovo pulsante che esporta i risultati dei suggerimenti in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="309f1-137">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="309f1-138">Per ulteriori informazioni, vedere [Clonare un modulo di starter kit](e-commerce-extensibility/clone-starter-module.md)e [Moduli Raccolta prodotti](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="309f1-138">For more information, see [Clone a starter kit module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="309f1-139">Per una visualizzazione completa della libreria API Retail Server, vedere [API utente e clienti Retail Server](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="309f1-139">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="309f1-140">Dopo aver creato l'estensione personalizzata, il rivenditore può esportare un file CSV di tutti i risultati dei suggerimenti, in base all'ID cliente univoco dell'utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="309f1-140">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="309f1-141">Il rivenditore può condividere il file CSV esportato che contiene l'elenco personalizzato completo dei prodotti consigliati con l'utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="309f1-141">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="309f1-142">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="309f1-142">Additional resources</span></span>

[<span data-ttu-id="309f1-143">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="309f1-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="309f1-144">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="309f1-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="309f1-145">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="309f1-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="309f1-146">Aggiungere elenchi di suggerimenti sul prodotto alle pagine</span><span class="sxs-lookup"><span data-stu-id="309f1-146">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="309f1-147">Aggiungere il pannello dei suggerimenti a dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="309f1-147">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="309f1-148">Panoramica del modulo di raccolta prodotti</span><span class="sxs-lookup"><span data-stu-id="309f1-148">Product collection module overview</span></span>](product-collection-module-overview.md)
