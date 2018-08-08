--- 
title: Creare un contratto di acquisto
description: Questa procedura descrive la creazione di un contratto di acquisto
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 46b8ff64fd950aae9178133b8aba7a9a2888b074
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="8d8c7-103">Creare un contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="8d8c7-103">Create a purchase agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8d8c7-104">Questa procedura descrive la creazione di un contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="8d8c7-104">This procedure guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="8d8c7-105">e viene in genere effettuata da un responsabile acquisti.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="8d8c7-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="8d8c7-107">È necessario impostare le classificazioni del contratto di acquisto prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="8d8c7-108">Una volta creato un contratto, è possibile utilizzarlo quando si crea un ordine fornitore. In questo modo le condizioni del contratto di acquisto verranno copiate nell'intestazione e in tutte le righe nell'ordine in cui sono interessate dal contratto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="8d8c7-109">Creare un nuovo contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="8d8c7-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="8d8c7-110">Andare ad Approvvigionamento > Contratti di acquisto > Contratti di acquisto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-110">Go to Procurement and sourcing > Purchase agreements > Purchase agreements.</span></span>
2. <span data-ttu-id="8d8c7-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-111">Click New.</span></span>
3. <span data-ttu-id="8d8c7-112">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8d8c7-113">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="8d8c7-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-114">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8d8c7-115">Nel campo Classificazione contratto di acquisto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-115">In the Purchase agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8d8c7-116">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8d8c7-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8d8c7-118">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-118">Expand the General section.</span></span>
10. <span data-ttu-id="8d8c7-119">Nel campo Data di scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-119">In the Expiration date field, enter a date.</span></span>
    * <span data-ttu-id="8d8c7-120">La data di scadenza verrà impostata per tutti le righe di impegno e determinerà il periodo di validità di ogni impegno specifico.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-120">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  
11. <span data-ttu-id="8d8c7-121">Nel campo Titolo documento digitare un nome per il contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-121">In the Document title field, type a name for your purchase agreement.</span></span>
    * <span data-ttu-id="8d8c7-122">Lasciare il campo Impegno predefinito impostato su Impegno quantità prodotto o modificarlo se non è impostato su tale valore.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-122">Leave the Default commitment field set to Product quantity commitment (or change it if it’s not set to this).</span></span>  
    * <span data-ttu-id="8d8c7-123">Il valore di impegno predefinito determina le opzioni nelle righe del contratto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-123">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="8d8c7-124">Se è necessarie un nuovo tipo di impegno durante la creazione delle righe del contratto, è necessario modificare l'impegno predefinito nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-124">If you need a new commitment type when you’re creating the agreement lines, you need to change the default commitment on the header.</span></span>  <span data-ttu-id="8d8c7-125">Sono presenti i 4 tipi di impegni seguenti. Impegno quantità prodotto - per una specifica quantità di prodotto, Impegno valore prodotto - per un importo in valuta specifico del prodotto, Impegno valore categoria prodotto - per un importo in valuta specifico in una categoria di approvvigionamento in cui l'importo può essere correlato a un articolo del catalogo oppure a un articolo fuori catalogo, Impegno valore - per un importo in valuta specifico che può essere soddisfatto da qualsiasi prodotto o da qualsiasi categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-125">There are 4 types of commitments: Product quantity commitment - for a specific quantity of a product; Product value commitment - for a specific currency amount of a product; Product category value commitment - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; Value commitment - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  
12. <span data-ttu-id="8d8c7-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-126">Click OK.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="8d8c7-127">Aggiungere un impegno</span><span class="sxs-lookup"><span data-stu-id="8d8c7-127">Add a commitment</span></span>
1. <span data-ttu-id="8d8c7-128">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-128">Click Add line.</span></span>
2. <span data-ttu-id="8d8c7-129">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="8d8c7-130">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-130">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8d8c7-131">Selezionare il prodotto per cui si desidera aggiungere un impegno.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-131">Select the product you want to add a commitment for.</span></span>
5. <span data-ttu-id="8d8c7-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-132">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8d8c7-133">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-133">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8d8c7-134">Si tratta della quantità totale accettata per l'acquisto dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-134">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
7. <span data-ttu-id="8d8c7-135">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-135">In the Unit price field, enter a number.</span></span>
8. <span data-ttu-id="8d8c7-136">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-136">Expand the Line details section.</span></span>
9. <span data-ttu-id="8d8c7-137">Impostare l'opzione Valore massimo applicato su Sì.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-137">Set the Max is enforced option to Yes.</span></span>
    * <span data-ttu-id="8d8c7-138">L'opzione Valore massimo applicato limita l'utilizzo dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-138">The Max is enforced option limits the use of the commitment.</span></span> <span data-ttu-id="8d8c7-139">È possibile acquistare una quantità pari al massimo al valore specificato nel campo Quantità per la riga.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-139">You can only purchase up to the quantity that's specified in the Quantity field for the line.</span></span>  
10. <span data-ttu-id="8d8c7-140">Comprimere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-140">Collapse the Line details section.</span></span>

## <a name="add-header-conditions"></a><span data-ttu-id="8d8c7-141">Aggiungere condizioni di intestazione</span><span class="sxs-lookup"><span data-stu-id="8d8c7-141">Add header conditions</span></span>
1. <span data-ttu-id="8d8c7-142">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-142">On the Action Pane, click Options.</span></span>
2. <span data-ttu-id="8d8c7-143">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-143">Click Change view.</span></span>
3. <span data-ttu-id="8d8c7-144">Fare clic su Visualizzazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-144">Click Header view.</span></span>
4. <span data-ttu-id="8d8c7-145">Espandere la sezione Termini.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-145">Expand the Terms section.</span></span>
5. <span data-ttu-id="8d8c7-146">Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-146">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8d8c7-147">I termini di pagamento del conto fornitore vengono visualizzati in questo punto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-147">The payment terms from the vendor account are shown here by default.</span></span>       
6. <span data-ttu-id="8d8c7-148">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-148">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8d8c7-149">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-149">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8d8c7-150">Nel campo Modalità di consegna fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-150">In the Mode of delivery field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="8d8c7-151">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-151">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="8d8c7-152">Nel campo Termini di consegna fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-152">In the Delivery terms field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="8d8c7-153">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-153">In the list, click the link in the selected row.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="8d8c7-154">Confermare e attivare il contratto</span><span class="sxs-lookup"><span data-stu-id="8d8c7-154">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="8d8c7-155">Nel riquadro azioni fare clic su Contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-155">On the Action Pane, click Purchase agreement.</span></span>
2. <span data-ttu-id="8d8c7-156">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-156">Click Confirmation.</span></span>
    * <span data-ttu-id="8d8c7-157">Impostare l'opzione Contrassegna contratto come valido su Sì.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-157">Set the Mark agreement as effective option to Yes.</span></span>  
3. <span data-ttu-id="8d8c7-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-158">Click OK.</span></span>
4. <span data-ttu-id="8d8c7-159">Nel riquadro azioni fare clic su Contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-159">On the Action Pane, click Purchase agreement.</span></span>
5. <span data-ttu-id="8d8c7-160">Fare clic su Conferme contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-160">Click Purchase agreement confirmations.</span></span>
    * <span data-ttu-id="8d8c7-161">L'opzione Anteprima/Stampa consente di generare un documento per il contratto di acquisto che successivamente è possibile stampare o inviare al fornitore.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-161">The Preview/Print option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="8d8c7-162">Se in seguito si aggiorna il contratto e lo si riconferma, entrambe le versioni verranno visualizzate in questo punto.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-162">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="8d8c7-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8d8c7-163">Close the page.</span></span>


