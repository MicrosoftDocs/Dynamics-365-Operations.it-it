---
title: Aggiungere suggerimenti alla schermata della transazione
description: In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 38099909f169391c17760ac381af07f0848fc384
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797481"
---
# <a name="add-recommendations-to-the-transaction-screen"></a><span data-ttu-id="e02d1-103">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="e02d1-103">Add recommendations to the transaction screen</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="e02d1-104">In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e02d1-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="e02d1-105">Per ulteriori informazioni sulle funzionalità di suggerimenti sul prodotto, leggere i [suggerimenti sul prodotto nella documentazione POS](product.md).</span><span class="sxs-lookup"><span data-stu-id="e02d1-105">For more information about product recommendations, read the  [product recommendations on POS documentation](product.md).</span></span>


<span data-ttu-id="e02d1-106">È possibile visualizzare i suggerimenti sul prodotto sul proprio dispositivo POS quando si utilizza Commerce.</span><span class="sxs-lookup"><span data-stu-id="e02d1-106">You can display product recommendations on your POS device when you use Commerce.</span></span> <span data-ttu-id="e02d1-107">Per visualizzare i suggerimenti di prodotti, è necessario aggiungere un controllo alla schermata della transazione mediante la funzionalità di progettazione del layout dello schermo.</span><span class="sxs-lookup"><span data-stu-id="e02d1-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="e02d1-108">Aprire Progettazione layout</span><span class="sxs-lookup"><span data-stu-id="e02d1-108">Open Layout designer</span></span>

1. <span data-ttu-id="e02d1-109">Passare a **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **POS** &gt; **Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-109">Go to **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="e02d1-110">Utilizzare il filtro rapido per individuare la schermata a cui si desidera aggiungere il controllo.</span><span class="sxs-lookup"><span data-stu-id="e02d1-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="e02d1-111">Ad esempio, filtrare il campo **ID layout schermo** utilizzando il valore **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="e02d1-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e02d1-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="e02d1-113">Ad esempio, selezionare **Nome: F2CP16:9M ID layout schermo: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="e02d1-114">Fare clic su **Progettazione layout**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="e02d1-115">Seguire i prompt per avviare Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="e02d1-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="e02d1-116">Quando vengono richieste le credenziali, immettere le stesse credenziali utilizzate quando la funzionalità Progettazione layout è stata avviata dalla pagina **Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="e02d1-117">Quando si effettua l'accesso, viene visualizzata una pagina simile a quella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e02d1-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="e02d1-118">Il layout sarà diverso a seconda delle personalizzazioni effettuate per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="e02d1-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="e02d1-119">[![Progettazione layout](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="e02d1-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="e02d1-120">Scelta di un'opzione visualizzata</span><span class="sxs-lookup"><span data-stu-id="e02d1-120">Choose a display option</span></span>

<span data-ttu-id="e02d1-121">Sono disponibili due opzioni di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="e02d1-121">There are two configurations options available.</span></span> <span data-ttu-id="e02d1-122">Scegliere l'opzione che funziona in modo ottimale per il punto vendita e seguire le istruzioni rimanenti per completare l'impostazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="e02d1-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="e02d1-123">Le due opzioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e02d1-123">The two options are:</span></span>

- <span data-ttu-id="e02d1-124">I suggerimenti sono sempre visibili.</span><span class="sxs-lookup"><span data-stu-id="e02d1-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="e02d1-125">Una scheda **Suggerimenti** viene visualizzata nella griglia sul lato destro della schermata.</span><span class="sxs-lookup"><span data-stu-id="e02d1-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="e02d1-126">Rendere i suggerimenti sempre visibili</span><span class="sxs-lookup"><span data-stu-id="e02d1-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="e02d1-127">Ridurre l'altezza dell'area dei dettagli delle righe di transazione in modo che sia la stessa di quella del pannello del cliente alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="e02d1-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="e02d1-128">[![Altezza ridotta dell'area dei dettagli delle righe di transazione](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="e02d1-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="e02d1-129">Dal menu a sinistra, trascinare il controllo dei suggerimenti tra l'area dei dettagli delle righe di transazione e la griglia dei pulsanti in basso al centro della schermata della transazione.</span><span class="sxs-lookup"><span data-stu-id="e02d1-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="e02d1-130">Ridimensionare il controllo in modo da adattarlo a tale spazio.</span><span class="sxs-lookup"><span data-stu-id="e02d1-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="e02d1-131">[![Controllo per suggerimenti aggiunto al layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="e02d1-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="e02d1-132">Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="e02d1-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="e02d1-133">In Commerce, passare a **Retail e Commerce** &gt; **Vendita al dettaglio e commercio IT** &gt; **Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-133">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="e02d1-134">Nell'elenco, selezionare **1090 Registri**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="e02d1-135">Fare clic su **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="e02d1-136">Aggiunta di una scheda Suggerimenti alla griglia dei pulsanti sul lato destro della schermata</span><span class="sxs-lookup"><span data-stu-id="e02d1-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="e02d1-137">Fare clic con il pulsante destro del mouse sullo spazio vuoto sotto l'ultima scheda nella griglia dei pulsanti presente sul lato destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="e02d1-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="e02d1-138">Fare clic su **Personalizza**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-138">Click **Customize**.</span></span>

    <span data-ttu-id="e02d1-139">[![Finestra di dialogo Personalizzazione - Controllo scheda](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="e02d1-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="e02d1-140">Fare clic su **Nuova scheda**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-140">Click **New tab**.</span></span>
4. <span data-ttu-id="e02d1-141">Individuare la nuova scheda appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="e02d1-141">Find the new tab that you just added.</span></span> <span data-ttu-id="e02d1-142">Potrebbe essere necessario scorrere verso il basso.</span><span class="sxs-lookup"><span data-stu-id="e02d1-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="e02d1-143">Nell'elenco a discesa **Contenuti**, selezionare **Prodotti consigliati**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="e02d1-144">[![Selezione di Prodotti consigliati nel campo Contenuto](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="e02d1-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="e02d1-145">Nel campo **Etichetta**, digitare un nome per la scheda dei suggerimenti. Ad esempio, digitare "Prodotti consigliati".</span><span class="sxs-lookup"><span data-stu-id="e02d1-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="e02d1-146">Nel campo **Immagine**, selezionare l'immagine che verrà visualizzata sulla scheda.</span><span class="sxs-lookup"><span data-stu-id="e02d1-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="e02d1-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-147">Click **OK**.</span></span> <span data-ttu-id="e02d1-148">La nuova scheda viene visualizzata nella griglia dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="e02d1-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="e02d1-149">Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="e02d1-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="e02d1-150">In Commerce, passare a **Retail e Commerce** &gt; **Vendita al dettaglio e commercio IT** &gt; **Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-150">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="e02d1-151">Nell'elenco, selezionare **1090 Registri**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="e02d1-152">Fare clic su **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="e02d1-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e02d1-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e02d1-153">Additional resources</span></span>

[<span data-ttu-id="e02d1-154">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="e02d1-154">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="e02d1-155">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e02d1-155">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="e02d1-156">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="e02d1-156">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="e02d1-157">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="e02d1-157">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="e02d1-158">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="e02d1-158">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="e02d1-159">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="e02d1-159">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="e02d1-160">Aggiungere suggerimenti sul prodotto nel POS</span><span class="sxs-lookup"><span data-stu-id="e02d1-160">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="e02d1-161">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="e02d1-161">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="e02d1-162">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="e02d1-162">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="e02d1-163">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="e02d1-163">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="e02d1-164">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="e02d1-164">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]