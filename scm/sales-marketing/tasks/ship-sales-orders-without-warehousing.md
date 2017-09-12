--- 
title: Spedire gli ordini cliente senza immagazzinaggio
description: La guida dimostra come aggiornare un ordine cliente quando i prodotti vengono spediti al cliente.
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3f1b9dd4b99bcbcc6cfbc5cfd8e3271fa80c628c
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="cc8b0-103">Spedire gli ordini cliente senza immagazzinaggio</span><span class="sxs-lookup"><span data-stu-id="cc8b0-103">Ship sales orders without warehousing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc8b0-104">La guida dimostra come aggiornare un ordine cliente quando i prodotti vengono spediti al cliente.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-104">This guide demonstrates how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="cc8b0-105">La guida è applicabile al flusso di evasione non impostato per gestione magazzino (né immagazzinaggio di base né avanzato) e pertanto non richiede la registrazione del prelievo prodotto prima della spedizione.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="cc8b0-106">È possibile eseguire questa procedura sui propri dati o nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="cc8b0-107">In entrambi i casi, prima di iniziare questa attività, creare un ordine cliente per un prodotto inventariato con una quantità maggiore di 1.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="cc8b0-108">Per evitare un errore di registrazione, è necessario verificare che la quantità disponibile del prodotto nel sito e nel magazzino selezionato nell'ordine copra la quantità dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you’ve selected on the order covers the order quantity.</span></span>


## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="cc8b0-109">Registrare il documento di trasporto per un ordine</span><span class="sxs-lookup"><span data-stu-id="cc8b0-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="cc8b0-110">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="cc8b0-111">Nell'elenco, trovare e selezionare l'ordine creato per l'attività.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="cc8b0-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cc8b0-113">Nel riquadro azioni fare clic su Preleva e imballa.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-113">On the Action Pane, click Pick and pack.</span></span>
5. <span data-ttu-id="cc8b0-114">Fare clic su Registra documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-114">Click Post packing slip.</span></span>
6. <span data-ttu-id="cc8b0-115">Espandere o comprimere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-115">Expand or collapse the Parameters section.</span></span>
7. <span data-ttu-id="cc8b0-116">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="cc8b0-116">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="cc8b0-117">Altre opzioni sono Consegna ora e Prelevato.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-117">Other options include Deliver now and Picked.</span></span> <span data-ttu-id="cc8b0-118">Se la riga ordine deve essere spedita parzialmente e il campo Consegna ora nella riga ordine contiene una quantità, selezionare Consegna ora.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-118">If the order line is to be shipped partially and the Deliver now field on the order line contains a quantity, you would select Deliver now.</span></span> <span data-ttu-id="cc8b0-119">Se il flusso di evasione dell'organizzazione include il prelievo come processo separato che viene gestito da e registrato con una distinta di prelievo, selezionare Prelevato.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-119">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select Picked.</span></span>  
    * <span data-ttu-id="cc8b0-120">Verificare che l'opzione Registrazione sia impostata su Sì.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-120">Check that the Posting option is set to Yes.</span></span>  
8. <span data-ttu-id="cc8b0-121">Impostare l'opzione Stampa documento di trasporto su Sì.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-121">Set the Print packing slip option to Yes.</span></span>
    * <span data-ttu-id="cc8b0-122">La scheda Panoramica contiene un elenco dei documenti di trasporto da generare nella registrazione corrente.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-122">The Overview tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="cc8b0-123">Se si spedisce un singolo ordine, in genere ci sarà un solo documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-123">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="cc8b0-124">Tuttavia, se le righe di tale ordine devono essere spedite da siti diversi, la registrazione automaticamente verrà suddivisa nel numero appropriato dei documenti.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-124">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="cc8b0-125">È una condizione obbligatoria che non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-125">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="cc8b0-126">In modo analogo, la registrazione verrà divisa in più documenti se le righe dell'ordine devono essere spedite a indirizzi di consegna diversi e i criteri di spedizione sono impostati per richiedere una divisione.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-126">Similarly, the posting will also be split into multiple documents if the order’s lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
9. <span data-ttu-id="cc8b0-127">Nella scheda Righe, selezionare la riga per la riga ordine da spedire.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-127">On the Lines tab, select the row for the order line to be shipped.</span></span>
10. <span data-ttu-id="cc8b0-128">Nel campo Aggiornamento, immettere un numero più basso della quantità originale.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-128">In the Update field, enter a number lower than the original quantity.</span></span>
11. <span data-ttu-id="cc8b0-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-129">Click OK.</span></span>
12. <span data-ttu-id="cc8b0-130">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-130">Click Yes.</span></span>
13. <span data-ttu-id="cc8b0-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-131">Close the page.</span></span>
14. <span data-ttu-id="cc8b0-132">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-132">On the Action Pane, click Options.</span></span>
15. <span data-ttu-id="cc8b0-133">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-133">Click Change view.</span></span>
16. <span data-ttu-id="cc8b0-134">Fare clic su Visualizzazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-134">Click Header view.</span></span>
    * <span data-ttu-id="cc8b0-135">Se tutte le righe dell'ordine sono state completamente spedite, lo stato dell'ordine cambia da Aperto a Consegnato.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-135">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    * <span data-ttu-id="cc8b0-136">In questo esempio, la riga ordine è stata spedita parzialmente.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-136">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="cc8b0-137">Ecco perché lo stato dell'ordine rimane Aperto.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-137">This is why the the order status remains Open.</span></span>     
    * <span data-ttu-id="cc8b0-138">Il campo Stato documento è impostato su Documento di trasporto poiché almeno una riga ordine è stata spedita.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-138">The Document status field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
17. <span data-ttu-id="cc8b0-139">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-139">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="cc8b0-140">Fare clic su Quantità riga.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-140">Click Line quantity.</span></span>
19. <span data-ttu-id="cc8b0-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-141">Close the page.</span></span>
20. <span data-ttu-id="cc8b0-142">Nel riquadro azioni fare clic su Preleva e imballa.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-142">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="cc8b0-143">Fare clic su Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-143">Click Packing slip.</span></span>
    * <span data-ttu-id="cc8b0-144">La pagina Giornale di registrazione documenti di trasporto contiene tutti i documenti di trasporto generati per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-144">The Packing slip journal page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="cc8b0-145">È possibile esaminare i dettagli di ogni documento e stamparli, se si desidera.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-145">You can review details of each document and print them, if you wish.</span></span>  

