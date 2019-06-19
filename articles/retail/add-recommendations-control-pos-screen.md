---
title: Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS
description: In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f17da3db6fbc19548544a0c6c090a0b6db093673
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606851"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="f4090-103">Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="f4090-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="f4090-104">Durante la nuova progettazione della funzionalità del servizio di suggerimenti prodotto con un algoritmo migliore e nuove funzionalità orientate alla vendita al dettaglio, verrà rimossa la versione corrente di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="f4090-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="f4090-105">Per ulteriori informazioni vedere [Funzionalità rimosse o deprecate](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="f4090-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span>

<span data-ttu-id="f4090-106">In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f4090-106">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="f4090-107">È possibile visualizzare i suggerimenti di prodotti sul proprio dispositivo POS quando si utilizza Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f4090-107">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="f4090-108">*Suggerimenti* sono articoli a cui il cliente potrebbe essere interessato in base al relativo storico acquisti, articoli nell'elenco preferenze e che altri clienti hanno acquistato online e in punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="f4090-108">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="f4090-109">Per visualizzare i suggerimenti di prodotti, è necessario aggiungere un controllo alla schermata della transazione mediante la funzionalità di progettazione del layout dello schermo.</span><span class="sxs-lookup"><span data-stu-id="f4090-109">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="f4090-110">Aprire Progettazione layout</span><span class="sxs-lookup"><span data-stu-id="f4090-110">Open Layout designer</span></span>

1. <span data-ttu-id="f4090-111">Passare a **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **POS** &gt; **Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="f4090-111">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="f4090-112">Utilizzare il filtro rapido per individuare la schermata a cui si desidera aggiungere il controllo.</span><span class="sxs-lookup"><span data-stu-id="f4090-112">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="f4090-113">Ad esempio, filtrare il campo **ID layout schermo** utilizzando il valore **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="f4090-113">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="f4090-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f4090-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="f4090-115">Ad esempio, selezionare **Nome: F2CP16:9M ID layout schermo: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="f4090-115">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="f4090-116">Fare clic su **Progettazione layout**.</span><span class="sxs-lookup"><span data-stu-id="f4090-116">Click **Layout designer**.</span></span>
5. <span data-ttu-id="f4090-117">Seguire i prompt per avviare Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="f4090-117">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="f4090-118">Quando vengono richieste le credenziali, immettere le stesse credenziali utilizzate quando la funzionalità Progettazione layout è stata avviata dalla pagina **Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="f4090-118">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="f4090-119">Quando si effettua l'accesso, viene visualizzata una pagina simile a quella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="f4090-119">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="f4090-120">Il layout sarà diverso a seconda delle personalizzazioni effettuate per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="f4090-120">The layout will be different depending on the customizations that were made for your store.</span></span>

    <span data-ttu-id="f4090-121">[![Progettazione layout](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="f4090-121">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="f4090-122">Scelta di un'opzione visualizzata</span><span class="sxs-lookup"><span data-stu-id="f4090-122">Choose a display option</span></span>

<span data-ttu-id="f4090-123">Sono disponibili due opzioni di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="f4090-123">There are two configurations options available.</span></span> <span data-ttu-id="f4090-124">Scegliere l'opzione che funziona in modo ottimale per il punto vendita e seguire le istruzioni rimanenti per completare l'impostazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="f4090-124">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="f4090-125">Le due opzioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4090-125">The two options are:</span></span>

- <span data-ttu-id="f4090-126">I suggerimenti sono sempre visibili.</span><span class="sxs-lookup"><span data-stu-id="f4090-126">Recommendations are always visible.</span></span>
- <span data-ttu-id="f4090-127">Una scheda **Suggerimenti** viene visualizzata nella griglia sul lato destro della schermata.</span><span class="sxs-lookup"><span data-stu-id="f4090-127">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="f4090-128">Rendere i suggerimenti sempre visibili</span><span class="sxs-lookup"><span data-stu-id="f4090-128">Make recommendations always visible</span></span>

1. <span data-ttu-id="f4090-129">Ridurre l'altezza dell'area dei dettagli delle righe di transazione in modo che sia la stessa di quella del pannello del cliente alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="f4090-129">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>

    <span data-ttu-id="f4090-130">[![Altezza ridotta dell'area dei dettagli delle righe di transazione](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="f4090-130">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="f4090-131">Dal menu a sinistra, trascinare il controllo dei suggerimenti tra l'area dei dettagli delle righe di transazione e la griglia dei pulsanti in basso al centro della schermata della transazione.</span><span class="sxs-lookup"><span data-stu-id="f4090-131">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="f4090-132">Ridimensionare il controllo in modo da adattarlo a tale spazio.</span><span class="sxs-lookup"><span data-stu-id="f4090-132">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="f4090-133">[![Controllo per suggerimenti aggiunto al layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="f4090-133">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>

3. <span data-ttu-id="f4090-134">Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="f4090-134">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="f4090-135">In Dynamics 365 for Retail, passare a **Vendita al dettaglio** &gt; **Vendita al dettaglio IT** &gt; **Programmazioni della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="f4090-135">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="f4090-136">Nell'elenco, selezionare  **1090 Registri**.</span><span class="sxs-lookup"><span data-stu-id="f4090-136">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="f4090-137">Fare clic su **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="f4090-137">Click **Run now**.</span></span>

### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="f4090-138">Aggiunta di una scheda Suggerimenti alla griglia dei pulsanti sul lato destro della schermata</span><span class="sxs-lookup"><span data-stu-id="f4090-138">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="f4090-139">Fare clic con il pulsante destro del mouse sullo spazio vuoto sotto l'ultima scheda nella griglia dei pulsanti presente sul lato destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="f4090-139">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2. <span data-ttu-id="f4090-140">Fare clic su **Personalizza**.</span><span class="sxs-lookup"><span data-stu-id="f4090-140">Click **Customize**.</span></span>

    <span data-ttu-id="f4090-141">[![Finestra di dialogo Personalizzazione - Controllo scheda](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="f4090-141">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="f4090-142">Fare clic su **Nuova scheda**.</span><span class="sxs-lookup"><span data-stu-id="f4090-142">Click **New tab**.</span></span>
4. <span data-ttu-id="f4090-143">Individuare la nuova scheda appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="f4090-143">Find the new tab that you just added.</span></span> <span data-ttu-id="f4090-144">Potrebbe essere necessario scorrere verso il basso.</span><span class="sxs-lookup"><span data-stu-id="f4090-144">You may need to scroll down.</span></span>
5. <span data-ttu-id="f4090-145">Nell'elenco a discesa **Contenuti**, selezionare **Prodotti consigliati**.</span><span class="sxs-lookup"><span data-stu-id="f4090-145">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="f4090-146">[![Selezione di Prodotti consigliati nel campo Contenuto](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="f4090-146">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="f4090-147">Nel campo **Etichetta**, digitare un nome per la scheda dei suggerimenti. Ad esempio, digitare "Prodotti consigliati".</span><span class="sxs-lookup"><span data-stu-id="f4090-147">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="f4090-148">Nel campo **Immagine**, selezionare l'immagine che verrà visualizzata sulla scheda.</span><span class="sxs-lookup"><span data-stu-id="f4090-148">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="f4090-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4090-149">Click **OK**.</span></span> <span data-ttu-id="f4090-150">La nuova scheda viene visualizzata nella griglia dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="f4090-150">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="f4090-151">Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="f4090-151">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="f4090-152">In Dynamics 365 for Retail, passare a **Vendita al dettaglio** &gt; **Vendita al dettaglio IT** &gt; **Programmazioni della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="f4090-152">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="f4090-153">Nell'elenco, selezionare **1090 Registri**.</span><span class="sxs-lookup"><span data-stu-id="f4090-153">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="f4090-154">Fare clic su **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="f4090-154">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f4090-155">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f4090-155">Additional resources</span></span>

[<span data-ttu-id="f4090-156">Panoramica dei suggerimenti sul prodotto personalizzati</span><span class="sxs-lookup"><span data-stu-id="f4090-156">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)
