--- 
title: " Creare ordini del servizio clienti"
description: In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.
author: josaw1
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
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 62f88cc2e28405a9d2eb43819fb09d83a64658b6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="create-call-center-orders"></a><span data-ttu-id="33209-103"> Creare ordini del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="33209-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="33209-104">In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="33209-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="33209-105">Questa procedura utilizza la società di dati dimostrativi USRT ed è destinata all'addetto degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="33209-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="33209-106">Prerequisiti: l'utente che completa la procedura viene impostato come utente del servizio clienti e il catalogo semestrale di Fabrikam è pubblicato con almeno un codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="33209-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="33209-107">Passare a Vendita al dettaglio e commercio > Clienti > Servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="33209-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="33209-108">Nel campo Cerca testo, immettere i criteri di ricerca per cercare il cliente.</span><span class="sxs-lookup"><span data-stu-id="33209-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="33209-109">Per questa procedura di esempio, digitare 'karen' e premere TAB.</span><span class="sxs-lookup"><span data-stu-id="33209-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="33209-110">Fare clic su Cerca.</span><span class="sxs-lookup"><span data-stu-id="33209-110">Click Search.</span></span>
    * <span data-ttu-id="33209-111">Poiché è presente un solo cliente di nome Karen, i dati dimostrativi verranno automaticamente selezionati.</span><span class="sxs-lookup"><span data-stu-id="33209-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="33209-112">Fare clic su Nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="33209-112">Click New sales order.</span></span>
5. <span data-ttu-id="33209-113">Espandere o comprimere la sezione Intestazione ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="33209-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="33209-114">Selezionare il codice sorgente per il catalogo.</span><span class="sxs-lookup"><span data-stu-id="33209-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="33209-115">Se non sono presenti codici sorgente attivi è possibile chiudere il campo Origine e ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="33209-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="33209-116">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="33209-116">Click Add line.</span></span>
8. <span data-ttu-id="33209-117">Nel campo Numero articolo, immettere il termine di ricerca per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="33209-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="33209-118">Per questa procedura di esempio impostare un numero di articolo parziale "8111"e premere TAB.</span><span class="sxs-lookup"><span data-stu-id="33209-118">For this sample procedure enter a partial item number of '8111' and press tab.</span></span> <span data-ttu-id="33209-119">Verrà visualizzata la finestra pop-up per la ricerca dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="33209-119">This will pop up the item search window.</span></span>  
9. <span data-ttu-id="33209-120">Selezionare il prodotto da aggiungere all'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="33209-120">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="33209-121">Immettere la quantità di vendita.</span><span class="sxs-lookup"><span data-stu-id="33209-121">Enter the sales quantity.</span></span>
11. <span data-ttu-id="33209-122">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="33209-122">Click Create.</span></span>
12. <span data-ttu-id="33209-123">Fare clic su Completa per acquisire il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="33209-123">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="33209-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="33209-124">Click Add.</span></span>
    * <span data-ttu-id="33209-125">Il collegamento Aggiungi è presente nella scheda Pagamenti.</span><span class="sxs-lookup"><span data-stu-id="33209-125">The Add link is in the Payments tab.</span></span> <span data-ttu-id="33209-126">Espandere la scheda Pagamenti se è compressa.</span><span class="sxs-lookup"><span data-stu-id="33209-126">Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="33209-127">Selezionare il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="33209-127">Select the payment method.</span></span>
    * <span data-ttu-id="33209-128">Selezionare il metodo di pagamento in contanti per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="33209-128">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="33209-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="33209-129">Close the page.</span></span>
16. <span data-ttu-id="33209-130">Immettere l'importo.</span><span class="sxs-lookup"><span data-stu-id="33209-130">Enter the amount.</span></span>
    * <span data-ttu-id="33209-131">Per questa procedura immettere un importo uguale al saldo ordine che può essere presente nella pagina di riepilogo Ordine cliente a sinistra del campo dell'importo.</span><span class="sxs-lookup"><span data-stu-id="33209-131">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="33209-132">In tal modo sarà possibile completare l'ordine come interamente pagato.</span><span class="sxs-lookup"><span data-stu-id="33209-132">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="33209-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="33209-133">Click OK.</span></span>
18. <span data-ttu-id="33209-134">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="33209-134">Click Submit.</span></span>


