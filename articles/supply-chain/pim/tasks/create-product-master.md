--- 
title: Creare una rappresentazione generale prodotto
description: Creare una rappresentazione generale prodotto per le varianti predefinite.
author: BibiSp
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
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e8d438da1524850c115f5c38865fac2f19f3ff5
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-master"></a><span data-ttu-id="c4c47-103">Creare una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="c4c47-103">Create a product master</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c4c47-104">Creare una rappresentazione generale prodotto per le varianti predefinite.</span><span class="sxs-lookup"><span data-stu-id="c4c47-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="c4c47-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c4c47-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c4c47-106">Questa procedura è destinata al responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4c47-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="c4c47-107">Creare una nuova rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="c4c47-107">Create a new product master</span></span>
1. <span data-ttu-id="c4c47-108">Andare a Gestione informazioni sul prodotto > Prodotti > Rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4c47-108">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="c4c47-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c4c47-109">Click New.</span></span>
3. <span data-ttu-id="c4c47-110">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c4c47-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c4c47-111">Il numero deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="c4c47-111">The number must be unique.</span></span> <span data-ttu-id="c4c47-112">Per il campo Numero prodotto è possibile impostare una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="c4c47-112">A number sequence can be set for the Product number field.</span></span> <span data-ttu-id="c4c47-113">In questo caso, l'utente non deve immettere alcun valore.</span><span class="sxs-lookup"><span data-stu-id="c4c47-113">In this case, the user doesn't have to enter a value.</span></span>  
4. <span data-ttu-id="c4c47-114">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4c47-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="c4c47-115">Immettere un nome descrittivo per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4c47-115">Enter a descriptive product name.</span></span> <span data-ttu-id="c4c47-116">Il valore predefinito è il nome di ricerca, ma tale valore può essere modificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c4c47-116">The value defaults to the search name, but this can be changed by the user.</span></span>  
5. <span data-ttu-id="c4c47-117">Nel campo Gruppo di dimensioni prodotto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c4c47-117">In the Product dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c4c47-118">Il gruppo di dimensioni prodotto determina quale delle 4 dimensioni possono essere utilizzate per creare varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4c47-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="c4c47-119">In questo esempio viene utilizzato un gruppo con colore e dimensione.</span><span class="sxs-lookup"><span data-stu-id="c4c47-119">This example uses a group with color and size.</span></span>  
6. <span data-ttu-id="c4c47-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c4c47-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="c4c47-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c4c47-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c4c47-122">La tecnologia di configurazione predefinita è Variante predefinita.</span><span class="sxs-lookup"><span data-stu-id="c4c47-122">The default configuration technology is Predefined variant.</span></span> <span data-ttu-id="c4c47-123">Tale impostazione verrà utilizzata per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="c4c47-123">This will be used for this example.</span></span>  
8. <span data-ttu-id="c4c47-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c4c47-124">Click OK.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="c4c47-125">Selezionare gruppi di dimensione prodotto</span><span class="sxs-lookup"><span data-stu-id="c4c47-125">Select product dimension groups</span></span>
1. <span data-ttu-id="c4c47-126">Nel campo Gruppo di colori fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c4c47-126">In the Color group field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="c4c47-127">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c4c47-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c4c47-128">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c4c47-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c4c47-129">Nel campo Gruppo di dimensioni fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c4c47-129">In the Size group field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c4c47-130">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c4c47-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="c4c47-131">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c4c47-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="c4c47-132">Aggiungere gruppi di dimensioni</span><span class="sxs-lookup"><span data-stu-id="c4c47-132">Add dimension groups</span></span>
1. <span data-ttu-id="c4c47-133">Nel riquadro azioni fare clic su Prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4c47-133">On the Action Pane, click Product.</span></span>
2. <span data-ttu-id="c4c47-134">Fare clic su gruppi di dimensioni per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c4c47-134">Click Dimension groups to open the drop dialog.</span></span>
3. <span data-ttu-id="c4c47-135">Nel campo Gruppo di dimensioni di immagazzinamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c4c47-135">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c4c47-136">Le dimensioni di immagazzinamento consentono di controllare il modo in cui gli articoli vengono immagazzinati e prelevati dal magazzino.</span><span class="sxs-lookup"><span data-stu-id="c4c47-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="c4c47-137">Ad esempio, una dimensione di immagazzinamento può includere il sito e il magazzino.</span><span class="sxs-lookup"><span data-stu-id="c4c47-137">For example, a storage dimension can include Site and Warehouse.</span></span>  
4. <span data-ttu-id="c4c47-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c4c47-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="c4c47-139">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c4c47-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c4c47-140">Nel campo Gruppo di dimensioni di tracciabilità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c4c47-140">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c4c47-141">Il gruppo di dimensioni di tracciabilità determina quali dimensioni di tracciabilità è possibile aggiungere a un prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4c47-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="c4c47-142">Ad esempio, numero batch e numero di serie vengono utilizzati per tenere traccia degli articoli di magazzino.</span><span class="sxs-lookup"><span data-stu-id="c4c47-142">For example, the batch number and serial number are used to track inventory items.</span></span>  
7. <span data-ttu-id="c4c47-143">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c4c47-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="c4c47-144">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c4c47-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="c4c47-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c4c47-145">Click OK.</span></span>
10. <span data-ttu-id="c4c47-146">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c4c47-146">Click Save.</span></span>
11. <span data-ttu-id="c4c47-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c4c47-147">Close the page.</span></span>


