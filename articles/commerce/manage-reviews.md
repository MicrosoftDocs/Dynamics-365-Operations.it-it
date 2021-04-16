---
title: Gestire valutazioni e revisioni
description: In questo argomento viene descritto come gestire valutazioni e recensioni in Creazione di siti Web di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 60ad0dd821dc91576a59cf73ec46da4aefd34a2f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794261"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="d6ba4-103">Gestire valutazioni e revisioni</span><span class="sxs-lookup"><span data-stu-id="d6ba4-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d6ba4-104">In questo argomento viene descritto come gestire valutazioni e recensioni in Creazione di siti Web di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-104">This topic explains how to manage ratings and reviews in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="d6ba4-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d6ba4-105">Overview</span></span>

<span data-ttu-id="d6ba4-106">Dynamics 365 Commerce utilizza il servizio cognitivo di Microsoft Azure per moderare automaticamente il testo delle recensioni censurando le parole volgari.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="d6ba4-107">Inoltre, i moderatori possono Creazione di siti Web di Dynamics 365 Commerce per implementare le seguenti attività manuali:</span><span class="sxs-lookup"><span data-stu-id="d6ba4-107">In addition, moderators can use Dynamics 365 Commerce site builder to implement the following manual tasks:</span></span>

- <span data-ttu-id="d6ba4-108">Moderare le recensioni rispondendo alle stesse o rimuovendole.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="d6ba4-109">Eliminare le recensioni di un cliente su richiesta del cliente.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="d6ba4-110">Importare in blocco i dati di valutazioni e recensioni per tutti i prodotti in un modello di Microsoft Power BI, di modo che i trend di valutazioni e recensioni possano essere analizzati.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="d6ba4-111">Leggere una recensione</span><span class="sxs-lookup"><span data-stu-id="d6ba4-111">Read a review</span></span> 

<span data-ttu-id="d6ba4-112">Per leggere una recensione in Creazione di siti Web di Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-112">To read to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d6ba4-113">Andare a **Home \> Recensioni \> Moderazione**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-113">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d6ba4-114">Utilizzare il campo di ricerca nell'angolo superiore destro della pagina per filtrare le recensioni visualizzate per ID prodotto, nome di prodotto o testo della recensione.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-114">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="d6ba4-115">Ulteriori filtri consentono di limitare le recensioni per periodo, valutazione, canale o stato (rimossa, risposta o segnalata).</span><span class="sxs-lookup"><span data-stu-id="d6ba4-115">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Home page di moderazione](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="d6ba4-117">Rispondere a una recensione</span><span class="sxs-lookup"><span data-stu-id="d6ba4-117">Respond to a review</span></span> 

<span data-ttu-id="d6ba4-118">Talvolta, i clienti che hanno acquistato un prodotto esprimono la loro soddisfazione o insoddisfazione o non capiscono come utilizzare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-118">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="d6ba4-119">In veste di moderatore, è possibile pubblicare una risposta a una recensione.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-119">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="d6ba4-120">Questa risposta viene visualizzata insieme alla recensione nel sito.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-120">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="d6ba4-121">Per rispondere a una recensione in Creazione di siti Web di Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-121">To respond to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d6ba4-122">Andare a **Home \> Recensioni \> Moderazione**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-122">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d6ba4-123">Individuare e selezionare la recensione che richiede una risposta.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-123">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="d6ba4-124">Nel riquadro delle proprietà a destra, selezionare **Aggiungi una risposta**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-124">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="d6ba4-125">Immettere il testo della risposta e il nome che deve essere visibile alla persona che risponde.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-125">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="d6ba4-126">Il nome predefinito della persona che risponde è **Moderatore**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-126">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="d6ba4-127">Al termine, selezionare **Registra risposta**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-127">When you've finished, select **Post response**.</span></span>

![Rispondere a una recensione](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="d6ba4-129">Rimuovere una recensione</span><span class="sxs-lookup"><span data-stu-id="d6ba4-129">Take down a review</span></span> 

<span data-ttu-id="d6ba4-130">Talvolta, i moderatori rimuovono le recensioni dei clienti per un motivo commerciale.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-130">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="d6ba4-131">Per rimuovere una recensione in Creazione di siti Web di Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-131">To take down a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d6ba4-132">Andare a **Home \> Recensioni \> Moderazione**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-132">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d6ba4-133">Individuare e selezionare la recensione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-133">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="d6ba4-134">Nel riquadro delle proprietà a destra, selezionare il motivo della rimozione sotto **Rimuovere una recensione** e quindi selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-134">In the properties pane on the right, select a takedown reason under **Takedown Review**, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="d6ba4-135">Eliminare le recensioni di un cliente su richiesta del cliente.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-135">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="d6ba4-136">Talvolta, i clienti desiderano eliminare in modo permanente i dati delle loro recensioni e valutazioni da un sito Web di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-136">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="d6ba4-137">Un moderatore che riceve una richiesta di rimozione da un cliente può rimuovere i dati del cliente mediante la funzionalità di eliminazione di recensioni.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-137">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="d6ba4-138">Per trovare ed eliminare i dati di un cliente, il moderatore richiede l'indirizzo di posta elettronica che il cliente ha utilizzato per accedere e fornire le recensioni.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-138">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="d6ba4-139">Per trovare ed eliminare dati dei clienti in Creazione di siti Web di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-139">To find and delete customer data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d6ba4-140">Andare a **Home \> Recensioni \> Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-140">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="d6ba4-141">Nella casella **Cerca utenti per indirizzo di posta elettronica**, immettere l'indirizzo di posta elettronica del cliente e quindi selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-141">In the **Search for users by email address** box, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="d6ba4-142">Se il cliente svolge una qualsiasi attività di recensione (ad esempio invio di recensioni, voti sull'utilità delle recensioni di un altro cliente o commenti sulla recensione di un altro cliente), i risultati sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-142">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="d6ba4-143">Per ogni elemento, è presente un pulsante **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-143">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="d6ba4-144">Per ogni elemento che deve essere eliminato, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-144">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="d6ba4-145">Quando viene richiesto di confermare, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-145">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Eliminare i dati di un cliente](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="d6ba4-147">La rimozione completa di dati dal sistema può richiedere fino a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-147">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="d6ba4-148">I moderatori devono informare i clienti di tale durata.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-148">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="d6ba4-149">Se i clienti hanno modificato il relativo nome nelle impostazioni dell'account, molteplici elementi possono essere visualizzati nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-149">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="d6ba4-150">In questo caso, per eliminare completamente i dati del cliente, il moderatore deve selezionare **Elimina** per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-150">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="d6ba4-151">Scaricare i dati di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="d6ba4-151">Download ratings and reviews data</span></span>

<span data-ttu-id="d6ba4-152">Creazione di siti Web di Commerce consente ai moderatori di importare in blocco i dati di valutazioni e recensioni, di modo che possano analizzare le tendenze.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-152">Commerce site builder lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="d6ba4-153">Un modello di Power BI che include le metriche di base è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-153">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="d6ba4-154">I moderatori possono utilizzare questo modello per collegare i dati importati in blocco e visualizzare un dashboard.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-154">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="d6ba4-155">Non devono creare un dashboard personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-155">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="d6ba4-156">I moderatori possono inoltre personalizzare il modello di Power BI in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-156">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="d6ba4-157">Per scaricare i dati di valutazioni e recensioni in Creazione di siti Web di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-157">To download ratings and reviews data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d6ba4-158">Andare a **Home \> Recensioni \> Report**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-158">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="d6ba4-159">Selezionare **Scarica dati di recensioni** per scaricare in blocco i dati di valutazioni e recensioni in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-159">Select **Download review data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="d6ba4-160">Visualizzare le tendenze di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="d6ba4-160">View ratings and reviews trends</span></span>

<span data-ttu-id="d6ba4-161">I moderatori possono scaricare il modello di Power BI in modo da poter visualizzare le tendenze in un dashboard.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-161">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="d6ba4-162">Per visualizzare le tendenze di valutazioni e recensioni in Creazione di siti Web di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-162">To view ratings and reviews trends in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d6ba4-163">Andare a **Home \> Recensioni \> Report**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-163">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="d6ba4-164">Selezionare **Modello di PowerBI** per scaricare il modello.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-164">Select **PowerBI template** to download the template.</span></span>

    ![Scaricare il modello di Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="d6ba4-166">Aprire il modello scaricato utilizzando l'app Power BI.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-166">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="d6ba4-167">Chiudere la finestra di dialogo **Accedi a contenuto Web** e il messaggio di errore "Aggiorna" visualizzati.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-167">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="d6ba4-168">Andare a **Home**, selezionare **Modifica query** e quindi selezionare **Impostazioni origine dati**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-168">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="d6ba4-169">Nella finestra di dialogo **Impostazioni origine dati**, selezionare **Cambia origine**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-169">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="d6ba4-170">Nel campo **URL**, immettere il percorso dei dati delle recensioni scaricati nella procedura precedente (ad esempio **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="d6ba4-170">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Campo URL nella finestra di dialogo Valori separati da virgola](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="d6ba4-172">Selezionare **OK** e quindi selezionare **Applica modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-172">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="d6ba4-173">L'applicazione delle modifiche all'origine dati può durare fino a due minuti.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-173">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="d6ba4-174">Selezionare **Foglio tendenze** per visualizzare le tendenze di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-174">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Tendenze di valutazioni e recensioni](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="d6ba4-176">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d6ba4-176">Additional resources</span></span>

[<span data-ttu-id="d6ba4-177">Panoramica valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="d6ba4-177">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="d6ba4-178">Consentire l'utilizzo di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="d6ba4-178">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="d6ba4-179">Configurare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="d6ba4-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="d6ba4-180">Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="d6ba4-180">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]