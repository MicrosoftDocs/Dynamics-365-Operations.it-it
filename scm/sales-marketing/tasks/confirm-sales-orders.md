--- 
title: Confermare ordini cliente
description: Questa procedura descrive come confermare gli ordini cliente.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7cab69222c5004e6a62c632a9e85085403434ffd
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="confirm-sales-orders"></a><span data-ttu-id="06707-103">Confermare ordini cliente</span><span class="sxs-lookup"><span data-stu-id="06707-103">Confirm sales orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="06707-104">Questa procedura descrive come confermare gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="06707-105">Verrà illustrato come confermare un singolo ordine e come confermare più ordini cliente contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="06707-105">You’ll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="06707-106">Queste attività verranno in genere eseguite dal gestore degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="06707-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="06707-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="06707-108">Prima di iniziare, assicurarsi che siano presenti più ordini cliente aperti per lo stesso cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="06707-109">Se si utilizza USMF, è possibile utilizzare il cliente US-027.</span><span class="sxs-lookup"><span data-stu-id="06707-109">If you’re using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="06707-110">Confermare un unico ordine cliente</span><span class="sxs-lookup"><span data-stu-id="06707-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="06707-111">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-111">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="06707-112">Nell'elenco individuare e selezionare l'ordine che si desidera confermare.</span><span class="sxs-lookup"><span data-stu-id="06707-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="06707-113">Fare clic sul collegamento sul numero di ordine cliente per aprire l'ordine selezionato.</span><span class="sxs-lookup"><span data-stu-id="06707-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="06707-114">Nel riquadro azioni fare clic su Vendi.</span><span class="sxs-lookup"><span data-stu-id="06707-114">On the Action Pane, click Sell.</span></span>
5. <span data-ttu-id="06707-115">Fare clic su Conferma ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-115">Click Confirm sales order.</span></span>
6. <span data-ttu-id="06707-116">Espandere o comprimere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="06707-116">Expand or collapse the Parameters section.</span></span>
    * <span data-ttu-id="06707-117">Assicurarsi che il campo Registrazione impostato su Sì sia attivo.</span><span class="sxs-lookup"><span data-stu-id="06707-117">Make sure that the Posting Yes field is active.</span></span>  
7. <span data-ttu-id="06707-118">Impostare l'opzione Stampa la conferma su Sì.</span><span class="sxs-lookup"><span data-stu-id="06707-118">Set the Print confirmation option to Yes.</span></span>
    * <span data-ttu-id="06707-119">Il campo Verifica limite di credito specifica il metodo utilizzato per calcolare il credito residuo del cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-119">The Check credit limit field specifies the method that’s used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="06707-120">Per impostazione predefinita il codice viene copiato dalla pagina dei parametri Contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="06707-120">By default, it’s copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="06707-121">Se si desidera ignorare la verifica del limite di credito quando si conferma un ordine cliente specifico, impostare Verifica limite di credito su Nessuna.</span><span class="sxs-lookup"><span data-stu-id="06707-121">If you want to skip the credit limit check when confirming a specific sales order, set the Check credit limit to None.</span></span> <span data-ttu-id="06707-122">Tuttavia, è necessario tenere presente che anche se questo campo è impostato su Nessuna, la verifica del limite di credito verrà comunque eseguita se l'opzione Limite di credito obbligatorio viene selezionata nell'anagrafica cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-122">However, you should be aware that even with if this field is set to None, the credit limit check will still be performed if the Mandatory credit limit option is selected on the customer master data.</span></span>  
8. <span data-ttu-id="06707-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="06707-123">Click OK.</span></span>
9. <span data-ttu-id="06707-124">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="06707-124">Click Yes.</span></span>
10. <span data-ttu-id="06707-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="06707-125">Close the page.</span></span>
11. <span data-ttu-id="06707-126">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="06707-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="06707-127">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="06707-127">Click Change view.</span></span>
13. <span data-ttu-id="06707-128">Fare clic su Visualizzazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="06707-128">Click Header view.</span></span>
    * <span data-ttu-id="06707-129">Quando un ordine viene confermato, lo stato del documento viene impostato su Conferma.</span><span class="sxs-lookup"><span data-stu-id="06707-129">When an order is confirmed, the Document status is set to Confirmation.</span></span>  
14. <span data-ttu-id="06707-130">Nel riquadro azioni fare clic su Vendi.</span><span class="sxs-lookup"><span data-stu-id="06707-130">On the Action Pane, click Sell.</span></span>
15. <span data-ttu-id="06707-131">Fare clic su Conferma ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-131">Click Sales order confirmation.</span></span>
16. <span data-ttu-id="06707-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="06707-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="06707-133">Confermare più ordini cliente contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="06707-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="06707-134">Andare a Vendite e marketing > Ordini cliente > Conferma ordine > Conferma ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-134">Go to Sales and marketing > Sales orders > Order confirmation > Confirm sales order.</span></span>
2. <span data-ttu-id="06707-135">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="06707-135">Click Select.</span></span>
3. <span data-ttu-id="06707-136">Nell'elenco sulla scheda Intervallo individuare e selezionare il record che fa riferimento al campo Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="06707-136">In the list on the Range tab, find and select the record that references the Customer account field.</span></span>
4. <span data-ttu-id="06707-137">Nel campo Criteri fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="06707-137">In the Criteria field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="06707-138">Nell'elenco individuare e selezionare il conto cliente con più ordini per cui si desidera eseguire la conferma in massa.</span><span class="sxs-lookup"><span data-stu-id="06707-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span>
    * <span data-ttu-id="06707-139">Se si utilizza USMF, è possibile selezionare il conto US-027.</span><span class="sxs-lookup"><span data-stu-id="06707-139">If you’re using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="06707-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="06707-140">Click OK.</span></span>
    * <span data-ttu-id="06707-141">Nella scheda Panoramica viene visualizzato un elenco di ordini che soddisfano i criteri di query.</span><span class="sxs-lookup"><span data-stu-id="06707-141">The Overview tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="06707-142">Tali ordini verranno inclusi nella conferma.</span><span class="sxs-lookup"><span data-stu-id="06707-142">These will be included in the confirmation.</span></span>  
    * <span data-ttu-id="06707-143">Il campo Aggiorna riepilogo per specifica il parametro da cui più ordini devono essere riepilogati in un documento di conferma.</span><span class="sxs-lookup"><span data-stu-id="06707-143">The Summary update for field specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="06707-144">Per impostazione predefinita, l'opzione viene copiata dai valori predefiniti per l'impostazione di aggiornamento riepilogativo nella pagina dei parametri della contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="06707-144">By default, the option is copied from the Default values for summary update setting on the Accounts receivable parameters page.</span></span>  
7. <span data-ttu-id="06707-145">Nel campo Aggiorna riepilogo per selezionare "Ordine".</span><span class="sxs-lookup"><span data-stu-id="06707-145">In the Summary update for field, select 'Order'.</span></span>
    * <span data-ttu-id="06707-146">I parametri minimi necessari per creare gli aggiornamenti riepilogativi sono quelli relativi al conto fatture e alla valuta.</span><span class="sxs-lookup"><span data-stu-id="06707-146">The minimum parameters that are required to create summary updates are Invoice account and Currency.</span></span> <span data-ttu-id="06707-147">Ciò significa che gli aggiornamenti di riepilogo con conti fatture e valute diversi non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="06707-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="06707-148">I parametri aggiuntivi possono essere impostati nella pagina Parametri aggiornamento riepilogativo, a cui è possibile accedere dalla pagina Parametri contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="06707-148">Additional parameters can be set up in the Summary update parameters page which is accessible from the Accounts receivable parameters page.</span></span>  
8. <span data-ttu-id="06707-149">Nel campo Ordine cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="06707-149">In the Sales order field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="06707-150">Nell'elenco selezionare il numero di ordine che si desidera come ordine riepilogativo.</span><span class="sxs-lookup"><span data-stu-id="06707-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="06707-151">Fare clic su Disponi.</span><span class="sxs-lookup"><span data-stu-id="06707-151">Click Arrange.</span></span>
11. <span data-ttu-id="06707-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="06707-152">Click OK.</span></span>
12. <span data-ttu-id="06707-153">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="06707-153">Click OK.</span></span>

