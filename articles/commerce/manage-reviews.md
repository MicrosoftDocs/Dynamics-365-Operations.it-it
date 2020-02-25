---
title: Gestire valutazioni e recensioni
description: In questo argomento viene descritto come gestire valutazioni e recensioni utilizzando lo strumento di moderazione di valutazioni e recensioni di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027244"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="854e9-103">Gestire valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="854e9-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="854e9-104">In questo argomento viene descritto come gestire valutazioni e recensioni utilizzando lo strumento di moderazione di valutazioni e recensioni di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="854e9-104">This topic explains how to manage ratings and reviews by using the Microsoft Dynamics 365 Commerce ratings and reviews moderation tool.</span></span>

## <a name="overview"></a><span data-ttu-id="854e9-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="854e9-105">Overview</span></span>

<span data-ttu-id="854e9-106">Dynamics 365 Commerce utilizza il servizio cognitivo di Microsoft Azure per moderare automaticamente il testo delle recensioni censurando le parole volgari.</span><span class="sxs-lookup"><span data-stu-id="854e9-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="854e9-107">Inoltre, i moderatori possono utilizzare lo strumento di moderazione di valutazioni e recensioni per le seguenti attività manuali:</span><span class="sxs-lookup"><span data-stu-id="854e9-107">In addition, moderators can use the ratings and reviews moderation tool for the following manual tasks:</span></span>

- <span data-ttu-id="854e9-108">Moderare le recensioni rispondendo alle stesse o rimuovendole.</span><span class="sxs-lookup"><span data-stu-id="854e9-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="854e9-109">Eliminare le recensioni di un cliente su richiesta del cliente.</span><span class="sxs-lookup"><span data-stu-id="854e9-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="854e9-110">Importare in blocco i dati di valutazioni e recensioni per tutti i prodotti in un modello di Microsoft Power BI, di modo che i trend di valutazioni e recensioni possano essere analizzati.</span><span class="sxs-lookup"><span data-stu-id="854e9-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="access-ratings-and-reviews-moderation-features"></a><span data-ttu-id="854e9-111">Accedere alle funzionalità di moderazione di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="854e9-111">Access ratings and reviews moderation features</span></span>

<span data-ttu-id="854e9-112">Per accedere alle funzionalità di moderazione di valutazioni e recensioni nello strumento di gestione del sito di e-commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="854e9-112">To access ratings and reviews moderation features in the e-Commerce site management tool, follow these steps.</span></span>

1. <span data-ttu-id="854e9-113">Accedere a [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="854e9-113">Sign in to [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="854e9-114">Aprire il progetto contenente l'ambiente in cui si desidera inizializzare e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="854e9-114">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="854e9-115">Nella sezione **Ambienti**, selezionare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="854e9-115">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="854e9-116">In **Funzionalità ambiente**, selezionare **Gestione vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="854e9-116">Under **Environment features**, select **Retail manage**.</span></span>
1. <span data-ttu-id="854e9-117">Nella scheda **e-Commerce** sotto **Collegamenti**, selezionare **Strumento di gestione del sito di e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="854e9-117">On the **e-Commerce** tab under **Links**, select **e-Commerce Site management tool**.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="854e9-118">Leggere una recensione</span><span class="sxs-lookup"><span data-stu-id="854e9-118">Read a review</span></span> 

1. <span data-ttu-id="854e9-119">Andare a **Home \> Recensioni \> Moderazione**.</span><span class="sxs-lookup"><span data-stu-id="854e9-119">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="854e9-120">Utilizzare il campo di ricerca nell'angolo superiore destro della pagina per filtrare le recensioni visualizzate per ID prodotto, nome di prodotto o testo della recensione.</span><span class="sxs-lookup"><span data-stu-id="854e9-120">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="854e9-121">Ulteriori filtri consentono di limitare le recensioni per periodo, valutazione, canale o stato (rimossa, risposta o segnalata).</span><span class="sxs-lookup"><span data-stu-id="854e9-121">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Home page di moderazione](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="854e9-123">Rispondere a una recensione</span><span class="sxs-lookup"><span data-stu-id="854e9-123">Respond to a review</span></span> 

<span data-ttu-id="854e9-124">Talvolta, i clienti che hanno acquistato un prodotto esprimono la loro soddisfazione o insoddisfazione o non capiscono come utilizzare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="854e9-124">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="854e9-125">In veste di moderatore, è possibile pubblicare una risposta a una recensione.</span><span class="sxs-lookup"><span data-stu-id="854e9-125">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="854e9-126">Questa risposta viene visualizzata insieme alla recensione nel sito.</span><span class="sxs-lookup"><span data-stu-id="854e9-126">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="854e9-127">Per rispondere a una recensione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-127">To respond to a review, follow these steps.</span></span>

1. <span data-ttu-id="854e9-128">Andare a **Home \> Recensioni \> Moderazione**.</span><span class="sxs-lookup"><span data-stu-id="854e9-128">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="854e9-129">Individuare e selezionare la recensione che richiede una risposta.</span><span class="sxs-lookup"><span data-stu-id="854e9-129">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="854e9-130">Nel riquadro delle proprietà a destra, selezionare **Aggiungi una risposta**.</span><span class="sxs-lookup"><span data-stu-id="854e9-130">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="854e9-131">Immettere il testo della risposta e il nome che deve essere visibile alla persona che risponde.</span><span class="sxs-lookup"><span data-stu-id="854e9-131">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="854e9-132">Il nome predefinito della persona che risponde è **Moderatore**.</span><span class="sxs-lookup"><span data-stu-id="854e9-132">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="854e9-133">Al termine, selezionare **Registra risposta**.</span><span class="sxs-lookup"><span data-stu-id="854e9-133">When you've finished, select **Post response**.</span></span>

![Rispondere a una recensione](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="854e9-135">Rimuovere una recensione</span><span class="sxs-lookup"><span data-stu-id="854e9-135">Take down a review</span></span> 

<span data-ttu-id="854e9-136">Talvolta, i moderatori rimuovono le recensioni dei clienti per un motivo commerciale.</span><span class="sxs-lookup"><span data-stu-id="854e9-136">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="854e9-137">Per rimuovere una recensione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-137">To take down a review, follow these steps.</span></span>

1. <span data-ttu-id="854e9-138">Andare a **Home \> Recensioni \> Moderazione**.</span><span class="sxs-lookup"><span data-stu-id="854e9-138">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="854e9-139">Individuare e selezionare la recensione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="854e9-139">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="854e9-140">Nel riquadro delle proprietà a destra, selezionare il motivo della rimozione e quindi selezionare **Rimuovere**.</span><span class="sxs-lookup"><span data-stu-id="854e9-140">In the properties pane on the right, select a takedown reason, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="854e9-141">Eliminare le recensioni di un cliente su richiesta del cliente.</span><span class="sxs-lookup"><span data-stu-id="854e9-141">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="854e9-142">Talvolta, i clienti desiderano eliminare in modo permanente i dati delle loro recensioni e valutazioni da un sito Web di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="854e9-142">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="854e9-143">Un moderatore che riceve una richiesta di rimozione da un cliente può rimuovere i dati del cliente mediante la funzionalità di eliminazione di recensioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-143">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="854e9-144">Per trovare ed eliminare i dati di un cliente, il moderatore richiede l'indirizzo di posta elettronica che il cliente ha utilizzato per accedere e fornire le recensioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-144">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="854e9-145">Per trovare ed eliminare i dati dei clienti, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-145">To find and delete customer data, follow these steps.</span></span>

1. <span data-ttu-id="854e9-146">Andare a **Home \> Recensioni \> Elimina**.</span><span class="sxs-lookup"><span data-stu-id="854e9-146">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="854e9-147">Nel campo **Cerca utenti per indirizzo di posta elettronica**, immettere l'indirizzo di posta elettronica del cliente e quindi selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="854e9-147">In the **Search for users by email address** field, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="854e9-148">Se il cliente svolge una qualsiasi attività di recensione (ad esempio invio di recensioni, voti sull'utilità delle recensioni di un altro cliente o commenti sulla recensione di un altro cliente), i risultati sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="854e9-148">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="854e9-149">Per ogni elemento, è presente un pulsante **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="854e9-149">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="854e9-150">Per ogni elemento che deve essere eliminato, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="854e9-150">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="854e9-151">Quando viene richiesto di confermare, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="854e9-151">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Eliminare i dati di un cliente](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="854e9-153">La rimozione completa di dati dal sistema può richiedere fino a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="854e9-153">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="854e9-154">I moderatori devono informare i clienti di tale durata.</span><span class="sxs-lookup"><span data-stu-id="854e9-154">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="854e9-155">Se i clienti hanno modificato il relativo nome nelle impostazioni dell'account, molteplici elementi possono essere visualizzati nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="854e9-155">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="854e9-156">In questo caso, per eliminare completamente i dati del cliente, il moderatore deve selezionare **Elimina** per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="854e9-156">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="854e9-157">Scaricare i dati di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="854e9-157">Download ratings and reviews data</span></span>

<span data-ttu-id="854e9-158">Lo strumento di moderazione di valutazioni e recensioni consente ai moderatori di importare in blocco i dati di valutazioni e recensioni, di modo che possano analizzare le tendenze.</span><span class="sxs-lookup"><span data-stu-id="854e9-158">The ratings and reviews moderation tool lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="854e9-159">Un modello di Power BI che include le metriche di base è disponibile.</span><span class="sxs-lookup"><span data-stu-id="854e9-159">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="854e9-160">I moderatori possono utilizzare questo modello per collegare i dati importati in blocco e visualizzare un dashboard.</span><span class="sxs-lookup"><span data-stu-id="854e9-160">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="854e9-161">Non devono creare un dashboard personalizzato.</span><span class="sxs-lookup"><span data-stu-id="854e9-161">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="854e9-162">I moderatori possono inoltre personalizzare il modello di Power BI in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="854e9-162">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="854e9-163">Per scaricare i dati di valutazioni e recensioni, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-163">To download ratings and reviews data, follow these steps.</span></span>

1. <span data-ttu-id="854e9-164">Andare a **Home \> Recensioni \> Report**.</span><span class="sxs-lookup"><span data-stu-id="854e9-164">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="854e9-165">Selezionare **Scarica dati di recensioni** per scaricare in blocco i dati di valutazioni e recensioni in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="854e9-165">Select **Download reviews data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="854e9-166">Visualizzare le tendenze di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="854e9-166">View ratings and reviews trends</span></span>

<span data-ttu-id="854e9-167">I moderatori possono scaricare il modello di Power BI in modo da poter visualizzare le tendenze in un dashboard.</span><span class="sxs-lookup"><span data-stu-id="854e9-167">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="854e9-168">Per visualizzare le tendenze di valutazioni e recensioni, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-168">To view ratings and reviews trends, follow these steps.</span></span>

1. <span data-ttu-id="854e9-169">Andare a **Home \> Recensioni \> Report**.</span><span class="sxs-lookup"><span data-stu-id="854e9-169">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="854e9-170">Selezionare **Modello di PowerBI** per scaricare il modello.</span><span class="sxs-lookup"><span data-stu-id="854e9-170">Select **PowerBI template** to download the template.</span></span>

    ![Scaricare il modello di Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="854e9-172">Aprire il modello scaricato utilizzando l'app Power BI.</span><span class="sxs-lookup"><span data-stu-id="854e9-172">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="854e9-173">Chiudere la finestra di dialogo **Accedi a contenuto Web** e il messaggio di errore "Aggiorna" visualizzati.</span><span class="sxs-lookup"><span data-stu-id="854e9-173">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="854e9-174">Andare a **Home**, selezionare **Modifica query** e quindi selezionare **Impostazioni origine dati**.</span><span class="sxs-lookup"><span data-stu-id="854e9-174">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="854e9-175">Nella finestra di dialogo **Impostazioni origine dati**, selezionare **Cambia origine**.</span><span class="sxs-lookup"><span data-stu-id="854e9-175">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="854e9-176">Nel campo **URL**, immettere il percorso dei dati delle recensioni scaricati nella procedura precedente (ad esempio **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="854e9-176">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Campo URL nella finestra di dialogo Valori separati da virgola](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="854e9-178">Selezionare **OK** e quindi selezionare **Applica modifiche**.</span><span class="sxs-lookup"><span data-stu-id="854e9-178">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="854e9-179">L'applicazione delle modifiche all'origine dati può durare fino a due minuti.</span><span class="sxs-lookup"><span data-stu-id="854e9-179">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="854e9-180">Selezionare **Foglio tendenze** per visualizzare le tendenze di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="854e9-180">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Tendenze di valutazioni e recensioni](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="854e9-182">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="854e9-182">Additional resources</span></span>

[<span data-ttu-id="854e9-183">Panoramica valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="854e9-183">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="854e9-184">Consentire l'utilizzo di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="854e9-184">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="854e9-185">Configurare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="854e9-185">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="854e9-186">Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="854e9-186">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
