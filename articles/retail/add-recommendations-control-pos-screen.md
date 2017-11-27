---
title: Aggiungere un controllo di suggerimenti alla pagina della transazione su un dispositivo POS
description: "In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47ad5dc8fd698f6f543c6a48e2c7eb01d4e148e6
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="ce158-103">Aggiungere un controllo di suggerimenti alla pagina della transazione su un dispositivo POS</span><span class="sxs-lookup"><span data-stu-id="ce158-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="ce158-104">In questo argomento viene descritto come aggiungere un controllo di suggerimenti alla schermata della transazione su un dispositivo POS mediante la funzionalità di progettazione del layout dello schermo in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="ce158-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="ce158-105">È possibile visualizzare i suggerimenti di prodotti sul proprio dispositivo POS quando si utilizza Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="ce158-105">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="ce158-106">*Suggerimenti* sono articoli a cui il cliente potrebbe essere interessato in base al relativo storico acquisti, articoli nell'elenco preferenze e che altri clienti hanno acquistato online e in punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="ce158-106">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="ce158-107">Per visualizzare i suggerimenti di prodotti, è necessario aggiungere un controllo alla schermata della transazione mediante la funzionalità di progettazione del layout dello schermo.</span><span class="sxs-lookup"><span data-stu-id="ce158-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="ce158-108">Aprire Progettazione layout</span><span class="sxs-lookup"><span data-stu-id="ce158-108">Open Layout designer</span></span>
1.  <span data-ttu-id="ce158-109">Passare a **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **POS** &gt; **Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="ce158-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="ce158-110">Utilizzare il filtro rapido per individuare la schermata a cui si desidera aggiungere il controllo.</span><span class="sxs-lookup"><span data-stu-id="ce158-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="ce158-111">Ad esempio, filtrare il campo **ID layout schermo** utilizzando un valore pari a "F2CP16: 9M".</span><span class="sxs-lookup"><span data-stu-id="ce158-111">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="ce158-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ce158-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="ce158-113">Ad esempio, selezionare "Nome: F2CP16:9M ID layout schermo: F2CP16:9M".</span><span class="sxs-lookup"><span data-stu-id="ce158-113">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="ce158-114">Fare clic su **Progettazione layout**.</span><span class="sxs-lookup"><span data-stu-id="ce158-114">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="ce158-115">Seguire i prompt per avviare Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="ce158-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="ce158-116">Quando vengono richieste le credenziali, immettere le stesse credenziali utilizzate quando la funzionalità Progettazione layout è stata avviata dalla pagina **Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="ce158-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="ce158-117">Quando si effettua l'accesso, viene visualizzata una pagina simile a quella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ce158-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="ce158-118">Il layout sarà diverso a seconda delle personalizzazioni effettuate per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="ce158-118">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="ce158-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Scegliere un'opzione di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="ce158-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="ce158-120">Sono disponibili due opzioni di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="ce158-120">There are two configurations options available.</span></span> <span data-ttu-id="ce158-121">Scegliere l'opzione che funziona in modo ottimale per il punto vendita e seguire le istruzioni rimanenti per completare l'impostazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="ce158-121">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="ce158-122">Le due opzioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce158-122">The two options are:</span></span>
-   <span data-ttu-id="ce158-123">I suggerimenti sono sempre visibili.</span><span class="sxs-lookup"><span data-stu-id="ce158-123">Recommendations are always visible.</span></span>
-   <span data-ttu-id="ce158-124">Una scheda **Suggerimenti** viene visualizzata nella griglia sul lato destro della schermata.</span><span class="sxs-lookup"><span data-stu-id="ce158-124">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="ce158-125">Per rendere i suggerimenti sempre visibili</span><span class="sxs-lookup"><span data-stu-id="ce158-125">To make recommendations always visible</span></span>

1.  <span data-ttu-id="ce158-126">Ridurre l'altezza dell'area dei dettagli delle righe di transazione in modo che sia la stessa di quella del pannello del cliente alla sua sinistra.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="ce158-126">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="ce158-127">Dal menu a sinistra, trascinare il controllo dei suggerimenti tra l'area dei dettagli delle righe di transazione e la griglia dei pulsanti in basso al centro della schermata della transazione.</span><span class="sxs-lookup"><span data-stu-id="ce158-127">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="ce158-128">Ridimensionare il controllo in modo da adattarlo a tale spazio.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="ce158-128">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="ce158-129">Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="ce158-129">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="ce158-130">In Dynamics 365 for Retail, passare a **Vendita al dettaglio** &gt; **Vendita al dettaglio IT** &gt; **Programmazioni della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="ce158-130">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="ce158-131">Nell'elenco, selezionare **1090 Registri**.</span><span class="sxs-lookup"><span data-stu-id="ce158-131">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="ce158-132">Fare clic su **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="ce158-132">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="ce158-133">Per aggiungere una scheda Suggerimenti alla griglia dei pulsanti sul lato destro della schermata</span><span class="sxs-lookup"><span data-stu-id="ce158-133">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="ce158-134">Fare clic con il pulsante destro del mouse sullo spazio vuoto sotto l'ultima scheda nella griglia dei pulsanti presente sul lato destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="ce158-134">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="ce158-135">Fare clic **Personalizza**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="ce158-135">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="ce158-136">Fare clic su **Nuova scheda**.</span><span class="sxs-lookup"><span data-stu-id="ce158-136">Click **New tab**.</span></span>
4.  <span data-ttu-id="ce158-137">Individuare la nuova scheda appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="ce158-137">Find the new tab that you just added.</span></span> <span data-ttu-id="ce158-138">Potrebbe essere necessario scorrere verso il basso.</span><span class="sxs-lookup"><span data-stu-id="ce158-138">You may need to scroll down.</span></span>
5.  <span data-ttu-id="ce158-139">Nell'elenco a discesa **Contenuti**, selezionare **Prodotti consigliati**.</span><span class="sxs-lookup"><span data-stu-id="ce158-139">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="ce158-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="ce158-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="ce158-141">Nel campo **Etichetta**, digitare un nome per la scheda dei suggerimenti. Ad esempio, digitare "Prodotti consigliati".</span><span class="sxs-lookup"><span data-stu-id="ce158-141">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="ce158-142">Nel campo **Immagine**, selezionare l'immagine che verrà visualizzata sulla scheda.</span><span class="sxs-lookup"><span data-stu-id="ce158-142">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="ce158-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce158-143">Click **OK**.</span></span> <span data-ttu-id="ce158-144">La nuova scheda viene visualizzata nella griglia dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="ce158-144">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="ce158-145">Fare clic su **X** per salvare le modifiche e chiudere Progettazione layout.</span><span class="sxs-lookup"><span data-stu-id="ce158-145">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="ce158-146">In Dynamics 365 for Retail, passare a **Vendita al dettaglio** &gt; **Vendita al dettaglio IT** &gt; **Programmazioni della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="ce158-146">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="ce158-147">Nell'elenco, selezionare **1090 Registri**.</span><span class="sxs-lookup"><span data-stu-id="ce158-147">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="ce158-148">Fare clic su **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="ce158-148">Click **Run now**.</span></span>


<a name="see-also"></a><span data-ttu-id="ce158-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce158-149">See also</span></span>
--------

[<span data-ttu-id="ce158-150">Panoramica dei suggerimenti di prodotti personalizzati</span><span class="sxs-lookup"><span data-stu-id="ce158-150">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




