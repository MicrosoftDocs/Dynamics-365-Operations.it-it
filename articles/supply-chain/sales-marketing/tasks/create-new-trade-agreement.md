--- 
title: Creare un nuovo accordo commerciale
description: Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico.
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0d0e5c5d680fcbac5407883a1d6365a4f312dda9
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="fc1fb-103">Creare un nuovo accordo commerciale</span><span class="sxs-lookup"><span data-stu-id="fc1fb-103">Create a new trade agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc1fb-104">Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="fc1fb-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="fc1fb-106">Se si utilizzano i propri dati, prima di iniziare questa guida è necessario assicurarsi che sia presente un nome di giornale di registrazione per accordi commerciali in cui la relazione predefinita sia impostata su "Prezzo (vend.)".</span><span class="sxs-lookup"><span data-stu-id="fc1fb-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="fc1fb-107">Creare e registrare un nuovo giornale di registrazione degli accordi commerciali</span><span class="sxs-lookup"><span data-stu-id="fc1fb-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="fc1fb-108">Andare a Vendite e marketing > Prezzi e sconti > Giornale di registrazione accordi commerciali.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-108">Go to Sales and marketing > Prices and discounts > Trade agreement journals.</span></span>
2. <span data-ttu-id="fc1fb-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-109">Click New.</span></span>
3. <span data-ttu-id="fc1fb-110">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fc1fb-111">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fc1fb-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fc1fb-113">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-113">Click Lines.</span></span>
7. <span data-ttu-id="fc1fb-114">Nel campo Conto selezionare "Tabella".</span><span class="sxs-lookup"><span data-stu-id="fc1fb-114">In the Account code field, select 'Table'.</span></span>
    * <span data-ttu-id="fc1fb-115">In questo esempio viene aggiornato il prezzo per un cliente specifico ed è pertanto necessario scegliere Tabella.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-115">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="fc1fb-116">Se si aggiorna il prezzo di listino del prodotto, è necessario selezionare Tutti, in modo che il nuovo prezzo sia valido per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-116">If you were updating the product's list price, you would select All, so that the new price is valid for all customers.</span></span> <span data-ttu-id="fc1fb-117">Se si differenziano i prezzi per segmenti di clienti diversi, è necessario selezionare Gruppo.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-117">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="fc1fb-118">Per selezionare Gruppo, è necessario impostare i gruppi di prezzi del cliente.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-118">To select Group, you must have set up Customer price groups.</span></span>  
8. <span data-ttu-id="fc1fb-119">Nel campo Selezione del conto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-119">In the Account selection field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="fc1fb-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-120">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="fc1fb-121">Nel campo Codice articolo selezionare "Tabella".</span><span class="sxs-lookup"><span data-stu-id="fc1fb-121">In the Item code field, select 'Table'.</span></span>
    * <span data-ttu-id="fc1fb-122">Quando si immette un accordo commerciale di tipo "Prezzo (vend.)", è necessario selezionare "Tabella" nel campo Codice articolo.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-122">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the Item code field.</span></span> <span data-ttu-id="fc1fb-123">Ciò è dovuto al fatto che un prezzo è un valore assoluto e non può essere lo stesso per tutti i prodotti o per un gruppo di prodotti.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-123">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>  
11. <span data-ttu-id="fc1fb-124">Nel campo Relazione articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-124">In the Item relation field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="fc1fb-125">Nell'elenco selezionare il prodotto da includere nell'accordo.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-125">In the list, select the product you want to include in the agreement.</span></span>
    * <span data-ttu-id="fc1fb-126">Prendere nota del prodotto selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-126">Make a note of which product you've selected.</span></span>  
13. <span data-ttu-id="fc1fb-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="fc1fb-128">Nel campo Da immettere una quantità minima.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-128">In the From field, enter a minimum quantity.</span></span>
    * <span data-ttu-id="fc1fb-129">Se il cliente deve ordinare una quantità minima prima di ottenere il nuovo prezzo, è necessario specificare la quantità in questo campo.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-129">If the customer has to order a minimum quantity  before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    * <span data-ttu-id="fc1fb-130">Immettere un valore nel campo A per specificare la quantità massima sopra cui il prezzo del contratto non sarà valido.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-130">Enter a value in the To field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="fc1fb-131">Se si offrono prezzi e sconti in base a più intervalli di quantità, specificare ogni intervallo come una coppia di quantità minima e massima nel campo "Da" e "A" rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-131">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the 'From' and 'To' fields respectively.</span></span>  
15. <span data-ttu-id="fc1fb-132">Nel campo Importo in valuta immettere un prezzo.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-132">In the Amount in currency field, enter a price.</span></span>
16. <span data-ttu-id="fc1fb-133">Nel campo Dal immettere una data di inizio validità dell'accordo.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-133">In the From date field, enter a date from which this agreement will be valid.</span></span>
17. <span data-ttu-id="fc1fb-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-134">Click Save.</span></span>
18. <span data-ttu-id="fc1fb-135">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-135">Click Validate.</span></span>
19. <span data-ttu-id="fc1fb-136">Fare clic su Convalida le righe selezionate.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-136">Click Validate selected lines.</span></span>
20. <span data-ttu-id="fc1fb-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-137">Click OK.</span></span>
21. <span data-ttu-id="fc1fb-138">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-138">Click Post.</span></span>
22. <span data-ttu-id="fc1fb-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-139">Click OK.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="fc1fb-140">Visualizzare accordi commerciali per un prodotto</span><span class="sxs-lookup"><span data-stu-id="fc1fb-140">View trade agreements for a product</span></span>
1. <span data-ttu-id="fc1fb-141">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-141">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="fc1fb-142">Nell'elenco individuare e selezionare il prodotto il cui prezzo è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-142">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="fc1fb-143">Nel riquadro azioni fare clic su Vendi.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-143">On the Action Pane, click Sell.</span></span>
4. <span data-ttu-id="fc1fb-144">Fare clic su Visualizza accordi commerciali.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-144">Click View trade agreements.</span></span>
    * <span data-ttu-id="fc1fb-145">Esaminare i dettagli dell'accordo commerciale sui prezzi creato.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-145">Review the details of the price trade agreement you have just created.</span></span>    
5. <span data-ttu-id="fc1fb-146">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fc1fb-146">Close the page.</span></span>


