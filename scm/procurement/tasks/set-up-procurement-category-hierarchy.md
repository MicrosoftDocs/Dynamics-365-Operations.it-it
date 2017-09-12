--- 
title: Impostare una gerarchia di categorie di approvvigionamento
description: Questa procedura illustra come creare nuovi nodi in una gerarchia di categorie di approvvigionamento e come configurare una categoria di approvvigionamento per essere utilizzata in un processo di approvvigionamento.
author: mkirknel
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b9897b1184e8159b20a45d4cedbba56baef31a3c
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="013e9-103">Impostare una gerarchia di categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="013e9-103">Set up a procurement category hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="013e9-104">Questa procedura illustra come creare nuovi nodi in una gerarchia di categorie di approvvigionamento e come configurare una categoria di approvvigionamento per essere utilizzata in un processo di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="013e9-105">Queste attività verranno in genere svolte da un responsabile degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="013e9-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="013e9-106">Prima di iniziare questa procedura, deve essere presente una gerarchia di categorie di tipo approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="013e9-107">Se si utilizza una società di dati dimostrativi, è possibile eseguire questa procedura nella società USMF.</span><span class="sxs-lookup"><span data-stu-id="013e9-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="013e9-108">Aggiungere una categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="013e9-108">Add a new procurement category</span></span>
1. <span data-ttu-id="013e9-109">Andare ad Approvvigionamento > ..</span><span class="sxs-lookup"><span data-stu-id="013e9-109">Go to Procurement and sourcing > ..</span></span> <span data-ttu-id="013e9-110">> Categorie di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-110">> Procurement categories.</span></span>
2. <span data-ttu-id="013e9-111">Fare clic su Modifica gerarchia di categorie.</span><span class="sxs-lookup"><span data-stu-id="013e9-111">Click Edit category hierarchy.</span></span>
    * <span data-ttu-id="013e9-112">La gerarchia di categorie di approvvigionamento corrente viene visualizzata nella parte sinistra della pagina.</span><span class="sxs-lookup"><span data-stu-id="013e9-112">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="013e9-113">Si sta per modificare la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="013e9-113">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="013e9-114">Fare clic su nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="013e9-114">Click New category node.</span></span>
    * <span data-ttu-id="013e9-115">Il sistema selezionare il nodo di primo livello per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="013e9-115">The system selects the top node by default.</span></span> <span data-ttu-id="013e9-116">Se si esegue la procedura come guida attività, è possibile fare clic sul pulsante Sblocca e selezionare un altro nodo padre per inserire il nuovo nodo.</span><span class="sxs-lookup"><span data-stu-id="013e9-116">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="013e9-117">Una volta eseguita l'operazione, bloccare ancora la guida attività e quindi fare clic sul nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="013e9-117">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="013e9-118">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="013e9-118">In the Name field, type a value.</span></span>
5. <span data-ttu-id="013e9-119">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="013e9-119">In the Description field, type a value.</span></span>
6. <span data-ttu-id="013e9-120">Digitare un valore nel campo Nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="013e9-120">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="013e9-121">Il nome descrittivo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="013e9-121">The friendly name is optional.</span></span> <span data-ttu-id="013e9-122">Verrà visualizzato le ricerche di categoria insieme al nome della categoria.</span><span class="sxs-lookup"><span data-stu-id="013e9-122">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="013e9-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="013e9-123">Click Save.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="013e9-124">Aggiungere prodotti alla nuova categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="013e9-124">Add products to your new procurement category</span></span>
1. <span data-ttu-id="013e9-125">Andare ad Approvvigionamento > ..</span><span class="sxs-lookup"><span data-stu-id="013e9-125">Go to Procurement and sourcing > ..</span></span> <span data-ttu-id="013e9-126">> Categorie di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-126">> Procurement categories.</span></span>
    * <span data-ttu-id="013e9-127">Selezionare il nodo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="013e9-127">Select the node you just added.</span></span> <span data-ttu-id="013e9-128">Se si esegue la procedura come guida attività, potrebbe essere necessario sbloccare quest'ultima per selezionare il nodo.</span><span class="sxs-lookup"><span data-stu-id="013e9-128">If you’re running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="013e9-129">Attivare/disattivare l'espansione della sezione Prodotti.</span><span class="sxs-lookup"><span data-stu-id="013e9-129">Toggle the expansion of the Products section.</span></span>
3. <span data-ttu-id="013e9-130">Fare clic su Aggiungi per associare i prodotti alla categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-130">Click Add to associate products with the procurement category.</span></span>
4. <span data-ttu-id="013e9-131">Selezionare il prodotto che si desidera aggiungere alla categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-131">Select the product you want to add to the procurement category.</span></span>
5. <span data-ttu-id="013e9-132">Fare clic sulla freccia per selezionare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="013e9-132">Click the arrow to select the product.</span></span>
6. <span data-ttu-id="013e9-133">Selezionare un altro prodotto da aggiungere alla categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-133">Select another product to add to the procurement category.</span></span>
7. <span data-ttu-id="013e9-134">Fare clic sulla freccia per selezionare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="013e9-134">Click the arrow to select the product.</span></span>
8. <span data-ttu-id="013e9-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="013e9-135">Click OK.</span></span>

## <a name="add-approved-and-preferred-vendors"></a><span data-ttu-id="013e9-136">Aggiungi fornitori approvati e preferiti</span><span class="sxs-lookup"><span data-stu-id="013e9-136">Add approved and preferred vendors</span></span>
1. <span data-ttu-id="013e9-137">Attiva/disattiva l'espansione della sezione Fornitori.</span><span class="sxs-lookup"><span data-stu-id="013e9-137">Toggle the expansion of the Vendors section.</span></span>
2. <span data-ttu-id="013e9-138">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="013e9-138">Click Add.</span></span>
    * <span data-ttu-id="013e9-139">È possibile aggiungere un fornitore a una categoria di approvvigionamento e specificare se un fornitore è preferito o solo approvato nella categoria.</span><span class="sxs-lookup"><span data-stu-id="013e9-139">You can add a vendor to a procurement category and specify whether a vendor is preferred or just approved for the category.</span></span> <span data-ttu-id="013e9-140">Quando si elimina un fornitore da una categoria, le transazioni storiche con il fornitore nella categoria non verranno eliminate.</span><span class="sxs-lookup"><span data-stu-id="013e9-140">When you delete a vendor from a category, the historical transactions with the vendor in the category are not deleted.</span></span>   
3. <span data-ttu-id="013e9-141">Trovare il fornitore che si desidera aggiungere alla categoria.</span><span class="sxs-lookup"><span data-stu-id="013e9-141">Find the vendor you want to add to the category.</span></span>
4. <span data-ttu-id="013e9-142">Fare clic sulla freccia per selezionare il fornitore.</span><span class="sxs-lookup"><span data-stu-id="013e9-142">Click the arrow to select the vendor.</span></span>
5. <span data-ttu-id="013e9-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="013e9-143">Click OK.</span></span>
6. <span data-ttu-id="013e9-144">Selezionare la riga fornitore da modificare.</span><span class="sxs-lookup"><span data-stu-id="013e9-144">Select the vendor row that you want to modify.</span></span>
7. <span data-ttu-id="013e9-145">Selezionare un'opzione nel campo Stato fornitore.</span><span class="sxs-lookup"><span data-stu-id="013e9-145">In the Vendor status field, select an option.</span></span>
    * <span data-ttu-id="013e9-146">L'impostazione di selezione del fornitore nella regola dei criteri categorie determina se nelle richieste di acquisto sono disponibili tutti i fornitori o solo quelli preferiti o approvati.</span><span class="sxs-lookup"><span data-stu-id="013e9-146">The vendor selection setting in the Category policy rule governs whether preferred, approved, or all vendors are available on purchase requisitions.</span></span>   

## <a name="add-additional-information-to-the-category"></a><span data-ttu-id="013e9-147">Aggiungere informazioni supplementare alla categoria</span><span class="sxs-lookup"><span data-stu-id="013e9-147">Add additional information to the category</span></span>
1. <span data-ttu-id="013e9-148">Attivare/disattivare l'espansione della sezione Gruppi di criteri di valutazione fornitore.</span><span class="sxs-lookup"><span data-stu-id="013e9-148">Toggle the expansion of the Vendor evaluation criterion groups section.</span></span>
    * <span data-ttu-id="013e9-149">La scheda consente di definire i criteri in base ai quali devono essere valutati i fornitori nella categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-149">This tab allows you to define which criteria the vendors in the procurement category should be rated against.</span></span> <span data-ttu-id="013e9-150">A questo scopo, fare clic su Aggiungi, quindi selezionare un gruppo di valutazione fornitore contenente i criteri desiderati.</span><span class="sxs-lookup"><span data-stu-id="013e9-150">To do this you would click Add and then select a vendor evaluation group that contains the criteria you want.</span></span>  
2. <span data-ttu-id="013e9-151">Attivare/disattivare l'espansione della sezione Questionari.</span><span class="sxs-lookup"><span data-stu-id="013e9-151">Toggle the expansion of the Questionnaires section.</span></span>
    * <span data-ttu-id="013e9-152">La scheda consente di aggiungere i questionari che verranno visualizzati nella richiesta, a condizione che si imposti il tipo di attività su Richiesta.</span><span class="sxs-lookup"><span data-stu-id="013e9-152">This tab allows you to add questionnaires that will appear on the requisition, as long as you set the Activity type to "Requisition".</span></span> <span data-ttu-id="013e9-153">Il richiedente deve quindi compilare un questionario prima di che venga inviata una richiesta per prodotti specifici nella categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="013e9-153">The requester then has to fill out a questionnaire before they submit a requisition for the specific product or products in the procurement category.</span></span>  
3. <span data-ttu-id="013e9-154">Attivare/disattivare l'espansione della sezione Fasce IVA articoli.</span><span class="sxs-lookup"><span data-stu-id="013e9-154">Toggle the expansion of the Item sales tax groups section.</span></span>
4. <span data-ttu-id="013e9-155">Nel campo Fascia IVA articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="013e9-155">In the Item sales tax group: field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="013e9-156">Consente di selezionare una fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="013e9-156">Select a sales tax group.</span></span>
6. <span data-ttu-id="013e9-157">Attivare/disattivare l'espansione della sezione Pagina categoria.</span><span class="sxs-lookup"><span data-stu-id="013e9-157">Toggle the expansion of the Category page section.</span></span>
    * <span data-ttu-id="013e9-158">Le pagine di categoria vengono create nella pagina Gerarchia di categorie.</span><span class="sxs-lookup"><span data-stu-id="013e9-158">Category pages are created in the Category hierarchy page.</span></span> <span data-ttu-id="013e9-159">In tali pagine sono contenute informazioni sulla categoria di approvvigionamento, ad esempio informazioni sul tipo di prodotti in una categoria, le immagini dei prodotti in una categoria e gli annunci quali gli sconti disponibili in una categoria.</span><span class="sxs-lookup"><span data-stu-id="013e9-159">They contain information about the procurement category such as information about the type of products in a category, images of products in a category, or announcements such as the discounts that are available in a category.</span></span> <span data-ttu-id="013e9-160">Le informazioni in una pagina di categoria vengono visualizzare nelle richieste di acquisto.</span><span class="sxs-lookup"><span data-stu-id="013e9-160">The information in a category page is displayed on purchase requisitions.</span></span>  
7. <span data-ttu-id="013e9-161">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="013e9-161">Close the page.</span></span>

