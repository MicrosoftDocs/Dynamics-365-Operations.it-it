--- 
title: Creare un catalogo di approvvigionamento
description: Questa guida indica come creare un catalogo di approvvigionamento.
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
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
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="da90d-103">Creare un catalogo di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="da90d-103">Create a procurement catalog</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="da90d-104">Questa guida indica come creare un catalogo di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="da90d-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="da90d-105">Questa attività in genere viene svolta da un responsabile degli approvvigionamenti.</span><span class="sxs-lookup"><span data-stu-id="da90d-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="da90d-106">Inoltre imparerete come i dipendenti possono usare il catalogo quando creano una richiesta.</span><span class="sxs-lookup"><span data-stu-id="da90d-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="da90d-107">Prima che possiate creare un catalogo, ci deve essere una gerarchia di categorie di approvvigionamento nel vostro sistema.</span><span class="sxs-lookup"><span data-stu-id="da90d-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="da90d-108">La gerarchia è ereditata dal nuovo catalogo, con tutti i prodotti che sono nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="da90d-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="da90d-109">Potete utilizzare questa guida nella società di dati dimostrativi USMF in cui la gerarchia di categorie di approvvigionamento è disponibile, come pure gli esempi utilizzati nei passaggi della procedura.</span><span class="sxs-lookup"><span data-stu-id="da90d-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="da90d-110">Assicurarsi che una gerarchia di categorie di approvvigionamento esista</span><span class="sxs-lookup"><span data-stu-id="da90d-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="da90d-111">Passare a Approvvigionamento > Categorie di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="da90d-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="da90d-112">Una gerarchia di categorie di approvvigionamento è disponibile nella società di dati dimostrativi USMF e prodotti sono stati aggiunti alla categoria Office machines/Computers.</span><span class="sxs-lookup"><span data-stu-id="da90d-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="da90d-113">Se si esegue la procedura come guida attività, sarà necessario sbloccare la guida per esplorare la categoria.</span><span class="sxs-lookup"><span data-stu-id="da90d-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="da90d-114">Se una gerarchia non fosse disponibile, bisognerebbe crearla facendo clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="da90d-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="da90d-115">Ciò può essere fatto una sola volta.</span><span class="sxs-lookup"><span data-stu-id="da90d-115">This can only be done once.</span></span>  
2. <span data-ttu-id="da90d-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="da90d-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="da90d-117">Creazione di un catalogo</span><span class="sxs-lookup"><span data-stu-id="da90d-117">Create a catalog</span></span>
1. <span data-ttu-id="da90d-118">Andare a Approvvigionamento > Cataloghi > Cataloghi di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="da90d-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="da90d-119">Fare clic su Nuovo catalogo di approvvigionamento per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="da90d-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="da90d-120">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="da90d-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="da90d-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="da90d-121">Click OK.</span></span>
5. <span data-ttu-id="da90d-122">Nella struttura, espandere 'CORP PROCUREMENT CATEGORIES'.</span><span class="sxs-lookup"><span data-stu-id="da90d-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="da90d-123">Nella struttura espandere 'OFFICE MACHINES'.</span><span class="sxs-lookup"><span data-stu-id="da90d-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="da90d-124">Nella struttura selezionare 'Computer'.</span><span class="sxs-lookup"><span data-stu-id="da90d-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="da90d-125">I prodotti dalla categoria di approvvigionamento sono visualizzati nella lista.</span><span class="sxs-lookup"><span data-stu-id="da90d-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="da90d-126">Se volete aggiungere un prodotto alla categoria dovete fare questo alla pagina Gerarchia di categorie di approvvigionamento o alla pagina Dettagli articolo.</span><span class="sxs-lookup"><span data-stu-id="da90d-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="da90d-127">Il tipo di aggiornamento predefinito determina se i nuovi prodotti aggiunti alla gerarchia di categorie di approvvigionamento sono immediatamente visibili nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="da90d-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="da90d-128">Se il tipo di aggiornamento è impostato su Dinamico, i cambiamenti sono immediatamente visibili.</span><span class="sxs-lookup"><span data-stu-id="da90d-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="da90d-129">Se il tipo di aggiornamento è Statico, i nuovi prodotti sono visibili alle persone che usano il catalogo solo dopo che il catalogo è stato ripubblicato.</span><span class="sxs-lookup"><span data-stu-id="da90d-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="da90d-130">L'azione Pubblica è disponibile nel riquadro azioni alla cima della pagina.</span><span class="sxs-lookup"><span data-stu-id="da90d-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="da90d-131">Se i prodotti vengono rimossi dalla gerarchia di categorie di approvvigionamento, il cambiamento è immediatamente visibile, indipendentemente dal valore nel campo Tipo di aggiornamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="da90d-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="da90d-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="da90d-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="da90d-133">Fare clic su Nascondi.</span><span class="sxs-lookup"><span data-stu-id="da90d-133">Click Hide.</span></span>
10. <span data-ttu-id="da90d-134">Nel riquadro azioni fare clic su Navigazione categoria.</span><span class="sxs-lookup"><span data-stu-id="da90d-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="da90d-135">Fare clic su Disabilita.</span><span class="sxs-lookup"><span data-stu-id="da90d-135">Click Disable.</span></span>
12. <span data-ttu-id="da90d-136">Nel riquadro azioni fare clic su Navigazione categoria.</span><span class="sxs-lookup"><span data-stu-id="da90d-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="da90d-137">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="da90d-137">Click Enable.</span></span>
14. <span data-ttu-id="da90d-138">Fare clic su Attiva catalogo.</span><span class="sxs-lookup"><span data-stu-id="da90d-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="da90d-139">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="da90d-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="da90d-140">Rendere visibile il catalogo</span><span class="sxs-lookup"><span data-stu-id="da90d-140">Make the catalog visible</span></span>
1. <span data-ttu-id="da90d-141">Andare a Approvvigionamento > Impostazioni > Criteri > Criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="da90d-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="da90d-142">Selezionare i criteri di approvvigionamento USMF.</span><span class="sxs-lookup"><span data-stu-id="da90d-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="da90d-143">Dovete selezionare i criteri di acquisto per la persona giuridica in cui al lavoratore collegato al vostro profilo utente è permesso ordinare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="da90d-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="da90d-144">Nei dati dimostrativi USMF, l'utente Admin è collegato al lavoratore chiamato Julia Funderburk, che ordina i prodotti in USMF per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="da90d-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="da90d-145">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="da90d-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="da90d-146">Selezionare il catalogo appena creato.</span><span class="sxs-lookup"><span data-stu-id="da90d-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="da90d-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="da90d-147">Click OK.</span></span>
6. <span data-ttu-id="da90d-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="da90d-148">Close the page.</span></span>
7. <span data-ttu-id="da90d-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="da90d-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="da90d-150">Usare il catalogo</span><span class="sxs-lookup"><span data-stu-id="da90d-150">Use the catalog</span></span>
1. <span data-ttu-id="da90d-151">Andare a Approvvigionamento > Richieste di acquisto > Tutte le richieste di acquisto.</span><span class="sxs-lookup"><span data-stu-id="da90d-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="da90d-152">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="da90d-152">Click New.</span></span>
3. <span data-ttu-id="da90d-153">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="da90d-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="da90d-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="da90d-154">Click OK.</span></span>
5. <span data-ttu-id="da90d-155">Fare clic su Aggiungi prodotti.</span><span class="sxs-lookup"><span data-stu-id="da90d-155">Click Add products.</span></span>
6. <span data-ttu-id="da90d-156">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="da90d-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="da90d-157">Potete utilizzare la gerarchia di categorie a sinistra o il filtro alla cima della lista per filtrare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="da90d-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="da90d-158">Fare clic su Aggiungi a righe.</span><span class="sxs-lookup"><span data-stu-id="da90d-158">Click Add to lines.</span></span>
8. <span data-ttu-id="da90d-159">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="da90d-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="da90d-160">Fare clic su Aggiungi a righe.</span><span class="sxs-lookup"><span data-stu-id="da90d-160">Click Add to lines.</span></span>
10. <span data-ttu-id="da90d-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="da90d-161">Click OK.</span></span>

