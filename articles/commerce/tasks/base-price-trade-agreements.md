---
title: Prezzo di base e accordi commerciali
description: In questa procedura vengono descritti i passaggi per creare accordi commerciali sui prezzi di vendita specifici del canale.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bab25988a9d4aad4d4e36fd9bdffbbf52473435e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259471"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="e8b8d-103">Prezzo di base e accordi commerciali</span><span class="sxs-lookup"><span data-stu-id="e8b8d-103">Base price and trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8b8d-104">In questa procedura vengono descritti i passaggi per creare accordi commerciali sui prezzi di vendita specifici del canale.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="e8b8d-105">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="e8b8d-106">Nel **pannello di navigazione** andare a **Moduli > Retail e Commerce > Prezzi e sconti > Gruppi di prezzi > Tutti i gruppi di prezzi**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-106">In the **Navigation pane**, go to **Modules > Retail and Commerce > Pricing and discounts management > Price groups > All price groups**.</span></span> <span data-ttu-id="e8b8d-107">I gruppi di prezzi indicano come gli accordi commerciali sono assegnati ai canali specifici.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="e8b8d-108">Utilizzando i gruppi di prezzi per assegnare gli accordi commerciali a un canale si abilita la determinazione dei prezzi specifici del canale.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="e8b8d-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-109">Click **New**.</span></span>
3. <span data-ttu-id="e8b8d-110">Digitare un valore nel campo **Gruppi di prezzi**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-110">In the **Price groups** field, type a value.</span></span>
4. <span data-ttu-id="e8b8d-111">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="e8b8d-112">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-112">Click **Save**.</span></span>
6. <span data-ttu-id="e8b8d-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-113">Close the page.</span></span>
7. <span data-ttu-id="e8b8d-114">Nel **pannello di navigazione**, andare a **Moduli > Retail e Commerce > Canali > Punti vendita > Tutti i punti vendita**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-114">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
8. <span data-ttu-id="e8b8d-115">Nell'elenco selezionare 'New York'.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="e8b8d-116">Nel riquadro azioni fare clic su **Punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-116">On the Action Pane, click **Store**.</span></span>
10. <span data-ttu-id="e8b8d-117">Fare clic su **Gruppi di prezzi**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-117">Click **Price groups**.</span></span>
11. <span data-ttu-id="e8b8d-118">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-118">Click **New**.</span></span>
12. <span data-ttu-id="e8b8d-119">Nel campo **Gruppi di prezzi** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-119">In the **Price groups** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="e8b8d-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="e8b8d-121">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-121">Click **Save**.</span></span>
15. <span data-ttu-id="e8b8d-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-122">Close the page.</span></span>
16. <span data-ttu-id="e8b8d-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-123">Close the page.</span></span>
17. <span data-ttu-id="e8b8d-124">Nel **pannello di navigazione** andare a **Moduli > Retail e Commerce > Prodotti e categorie > Prodotti rilasciati per categoria**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-124">In the **Navigation pane**, go to **Modules > Retail and Commerce > Products and categories > Released products by category**.</span></span>
18. <span data-ttu-id="e8b8d-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="e8b8d-126">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-126">Click **Edit**.</span></span>
20. <span data-ttu-id="e8b8d-127">Espandere la Scheda dettaglio **Vendi**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-127">Expand the **Sell** fastTab.</span></span>
21. <span data-ttu-id="e8b8d-128">Immettere un numero nel campo **Prezzo**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-128">In the **Price** field, enter a number.</span></span> <span data-ttu-id="e8b8d-129">Il prezzo viene utilizzato se non viene trovato alcun accordo commerciale applicabile.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="e8b8d-130">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-130">Click **Save**.</span></span>
23. <span data-ttu-id="e8b8d-131">Nel **riquadro azioni** fare clic su **Vendi**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-131">On the **Action Pane**, click **Sell**.</span></span>
24. <span data-ttu-id="e8b8d-132">Fare clic su **Crea accordi commerciali**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-132">Click **Create trade agreements**.</span></span>
25. <span data-ttu-id="e8b8d-133">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-133">Click **New**.</span></span>
26. <span data-ttu-id="e8b8d-134">Nel campo **Nome** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-134">In the **Name** field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="e8b8d-135">Nell'elenco selezionare **Commercio**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-135">In the list, select **Commerce**.</span></span> <span data-ttu-id="e8b8d-136">Nei dati dimostrativi, il nome del giornale di registrazione **Commercio** dispone della relazione predefinita di **Prezzo (vend.)**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-136">In the demo data, the **Commerce** journal name has the default relation of **Price (sales)**.</span></span> <span data-ttu-id="e8b8d-137">Questo significa che per tutte le nuove righe create verranno utilizzati per impostazione predefinita gli accordi commerciali sui prezzi di vendita.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="e8b8d-138">Nel **riquadro azioni** fare clic su **Righe**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-138">On the **Action pane**, click **Lines**.</span></span>
29. <span data-ttu-id="e8b8d-139">Nel campo **Tipo di codice parte**, seleziona 'Gruppo'.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-139">In the **Party code type** field, select 'Group'.</span></span>
30. <span data-ttu-id="e8b8d-140">Nel campo **Selezione del conto** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-140">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="e8b8d-141">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-141">In the list, find and select the desired record.</span></span> <span data-ttu-id="e8b8d-142">In tal modo viene completato il collegamento dal canale al gruppo di prezzi all'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="e8b8d-143">Nel campo **Relazione articolo**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-143">In the **Item relation** field, type a value.</span></span>
33. <span data-ttu-id="e8b8d-144">Nel campo **Importo in valuta** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-144">In the **Amount in currency** field, enter a number.</span></span>
34. <span data-ttu-id="e8b8d-145">Nella Scheda dettaglio **Dettagli**, selezionare o deselezionare la casella di controllo **Trova successivo**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-145">In the **Details** fastTab, check or uncheck the **Find next** checkbox.</span></span> <span data-ttu-id="e8b8d-146">Quando **Trova successivo** è impostato su "Sì", il motore di determinazione dei prezzi continua la ricerca di accordi commerciali applicabili con un prezzo di vendita inferiore.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-146">When **Find next** is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="e8b8d-147">Quando **Trova successivo** è impostato su "No" il motore dei determinazione dei prezzi non esegue alcuna ricerca e utilizza l'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-147">When **Find next** is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="e8b8d-148">Fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-148">Click **Post**.</span></span>
36. <span data-ttu-id="e8b8d-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-149">Click **OK**.</span></span>
37. <span data-ttu-id="e8b8d-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-150">Close the page.</span></span>
38. <span data-ttu-id="e8b8d-151">Nel **riquadro azioni** fare clic su Vendi.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-151">On the **Action Pane**, click Sell.</span></span>
39. <span data-ttu-id="e8b8d-152">Fare clic su **Prezzo di vendita**.</span><span class="sxs-lookup"><span data-stu-id="e8b8d-152">Click **Sales price**.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]