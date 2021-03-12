---
title: Creare un nuovo accordo commerciale
description: Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e49793fc7f6b3f37bafae05770d4b23d24171329
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974887"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="a7ef3-103">Creare un nuovo accordo commerciale</span><span class="sxs-lookup"><span data-stu-id="a7ef3-103">Create a new trade agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7ef3-104">Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="a7ef3-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="a7ef3-106">Se si utilizzano i propri dati, prima di iniziare questa guida è necessario assicurarsi che sia presente un nome di giornale di registrazione per accordi commerciali in cui la relazione predefinita sia impostata su "Prezzo (vend.)".</span><span class="sxs-lookup"><span data-stu-id="a7ef3-106">If you're using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to "Price (sales)".</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="a7ef3-107">Creare e registrare un nuovo giornale di registrazione degli accordi commerciali</span><span class="sxs-lookup"><span data-stu-id="a7ef3-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="a7ef3-108">Andare a **Pannello di navigazione > Moduli > Vendite e marketing > Prezzi e sconti > Giornali di registrazione accordi commerciali**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-108">Go to **Navigation pane > Modules > Sales and marketing > Prices and discounts > Trade agreement journals**.</span></span>
2. <span data-ttu-id="a7ef3-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-109">Click **New**.</span></span>
3. <span data-ttu-id="a7ef3-110">Nel campo **Nome** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-110">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a7ef3-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a7ef3-112">In **Riquadro azioni** fai clic su **Righe**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-112">On **Action Pane**, click **Lines**.</span></span>
6. <span data-ttu-id="a7ef3-113">Nel campo **Codice conto** selezionare "Tabella".</span><span class="sxs-lookup"><span data-stu-id="a7ef3-113">In the **Account code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="a7ef3-114">In questo esempio viene aggiornato il prezzo per un cliente specifico ed è pertanto necessario scegliere Tabella.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-114">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="a7ef3-115">Se si aggiorna il prezzo di listino del prodotto, è necessario selezionare "Tutti", in modo che il nuovo prezzo sia valido per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-115">If you were updating the product's list price, you would select 'All', so that the new price is valid for all customers.</span></span> <span data-ttu-id="a7ef3-116">Se si differenziano i prezzi per segmenti di clienti diversi, è necessario selezionare Gruppo.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-116">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="a7ef3-117">Per selezionare Gruppo, è necessario impostare i gruppi di prezzi del cliente.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-117">To select Group, you must have set up Customer price groups.</span></span>  

7. <span data-ttu-id="a7ef3-118">Nel campo **Selezione del conto** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-118">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a7ef3-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="a7ef3-120">Nel campo **Codice articolo** selezionare "Tabella".</span><span class="sxs-lookup"><span data-stu-id="a7ef3-120">In the **Item code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="a7ef3-121">Quando si immette un accordo commerciale di tipo "Prezzo (vend.)", è necessario selezionare "Tabella" nel campo **Codice articolo**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-121">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the **Item code** field.</span></span> <span data-ttu-id="a7ef3-122">Ciò è dovuto al fatto che un prezzo è un valore assoluto e non può essere lo stesso per tutti i prodotti o per un gruppo di prodotti.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-122">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>
    
10. <span data-ttu-id="a7ef3-123">Nel campo **Relazione articolo** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-123">In the **Item relation** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a7ef3-124">Nell'elenco selezionare il prodotto da includere nell'accordo.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-124">In the list, select the product you want to include in the agreement.</span></span> <span data-ttu-id="a7ef3-125">Prendere nota del prodotto selezionato.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-125">Make a note of which product you've selected.</span></span>  
12. <span data-ttu-id="a7ef3-126">Nel campo **Da** immettere una quantità minima.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-126">In the **From** field, enter a minimum quantity.</span></span>
    - <span data-ttu-id="a7ef3-127">Se il cliente deve ordinare una quantità minima prima di ottenere il nuovo prezzo, è necessario specificare la quantità in questo campo.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-127">If the customer has to order a minimum quantity before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    - <span data-ttu-id="a7ef3-128">Immettere un valore nel campo **A** per specificare la quantità massima sopra cui il prezzo del contratto non sarà valido.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-128">Enter a value in the **To** field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="a7ef3-129">Se si offrono prezzi e sconti in base a più intervalli di quantità, specificare ogni intervallo come una coppia di quantità minima e massima nel campo **Da** e **A** rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-129">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the **From** and **To** fields respectively.</span></span>
13. <span data-ttu-id="a7ef3-130">Nel campo **Importo in valuta** immettere un prezzo.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-130">In the **Amount in currency field**, enter a price.</span></span>
14. <span data-ttu-id="a7ef3-131">Sotto la sezione **Dettagli**, nel campo **Dal** immettere una data di inizio validità dell'accordo.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-131">Under the **Details** section, in the **From date** field, enter a date from which this agreement will be valid.</span></span>
15. <span data-ttu-id="a7ef3-132">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-132">Click **Save**.</span></span>
16. <span data-ttu-id="a7ef3-133">Fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-133">Click **Validate**.</span></span>
17. <span data-ttu-id="a7ef3-134">Fare clic su **Convalida le righe selezionate**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-134">Click **Validate selected lines**.</span></span>
18. <span data-ttu-id="a7ef3-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-135">Click **OK**.</span></span>
19. <span data-ttu-id="a7ef3-136">Fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-136">Click **Post**.</span></span>
20. <span data-ttu-id="a7ef3-137">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-137">Click **OK**.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="a7ef3-138">Visualizzare accordi commerciali per un prodotto</span><span class="sxs-lookup"><span data-stu-id="a7ef3-138">View trade agreements for a product</span></span>
1. <span data-ttu-id="a7ef3-139">Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-139">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="a7ef3-140">Nell'elenco individuare e selezionare il prodotto il cui prezzo è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-140">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="a7ef3-141">Nel **riquadro azioni** fare clic su **Vendi**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-141">On the **Action Pane**, click **Sell**.</span></span>
4. <span data-ttu-id="a7ef3-142">Fare clic su **Visualizza accordi commerciali**.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-142">Click **View trade agreements**.</span></span>
    
    <span data-ttu-id="a7ef3-143">Esaminare i dettagli dell'accordo commerciale sui prezzi creato.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-143">Review the details of the price trade agreement you have just created.</span></span>    

5. <span data-ttu-id="a7ef3-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a7ef3-144">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a7ef3-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a7ef3-145">Additional resources</span></span>

### <a name="whitepaper"></a><span data-ttu-id="a7ef3-146">White paper</span><span class="sxs-lookup"><span data-stu-id="a7ef3-146">Whitepaper</span></span>
<span data-ttu-id="a7ef3-147">Per ulteriori informazioni, scarica il seguente white paper (scritto per supportare AX2012, ma è ancora valido per Dynamics 365 Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="a7ef3-147">For more information, download the following white paper (written to support AX2012, but still applies for Dynamics 365 Supply Chain Management)</span></span>
- [<span data-ttu-id="a7ef3-148">Accordi commerciali</span><span class="sxs-lookup"><span data-stu-id="a7ef3-148">Trade agreements</span></span>](https://mbs.microsoft.com/files/public/CS/AX2012R3/TradeagreementsinAX.pdf)

### <a name="community-blogs"></a><span data-ttu-id="a7ef3-149">Blog della community</span><span class="sxs-lookup"><span data-stu-id="a7ef3-149">Community blogs</span></span>
- [<span data-ttu-id="a7ef3-150">Prezzi di vendita in Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a7ef3-150">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
