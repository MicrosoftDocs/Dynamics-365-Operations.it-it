---
title: " Creare ordini del servizio clienti"
description: In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1675d21f1e4176839feace76359afdbdc336c99
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023039"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="5b92f-103"> Creare ordini del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="5b92f-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5b92f-104">In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="5b92f-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="5b92f-105">Questa procedura utilizza la società di dati dimostrativi USRT ed è destinata all'addetto degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="5b92f-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="5b92f-106">Prerequisiti: l'utente che completa la procedura viene impostato come utente del servizio clienti e il catalogo semestrale di Fabrikam è pubblicato con almeno un codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5b92f-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="5b92f-107">Passare a Retail e Commerce > Clienti > Servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="5b92f-107">Go to Retail and Commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="5b92f-108">Nel campo Cerca testo, immettere i criteri di ricerca per cercare il cliente.</span><span class="sxs-lookup"><span data-stu-id="5b92f-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="5b92f-109">Per questa procedura di esempio, digitare 'karen' e premere TAB.</span><span class="sxs-lookup"><span data-stu-id="5b92f-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="5b92f-110">Fare clic su Cerca.</span><span class="sxs-lookup"><span data-stu-id="5b92f-110">Click Search.</span></span>
    * <span data-ttu-id="5b92f-111">Poiché è presente un solo cliente di nome Karen, i dati dimostrativi verranno automaticamente selezionati.</span><span class="sxs-lookup"><span data-stu-id="5b92f-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="5b92f-112">Fare clic su Nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="5b92f-112">Click New sales order.</span></span>
5. <span data-ttu-id="5b92f-113">Espandere o comprimere la sezione Intestazione ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="5b92f-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="5b92f-114">Selezionare il codice sorgente per il catalogo.</span><span class="sxs-lookup"><span data-stu-id="5b92f-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="5b92f-115">Se non sono presenti codici sorgente attivi è possibile chiudere il campo Origine e ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="5b92f-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="5b92f-116">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="5b92f-116">Click Add line.</span></span>
8. <span data-ttu-id="5b92f-117">Nel campo Numero articolo, immettere il termine di ricerca per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="5b92f-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="5b92f-118">Per questa procedura di esempio impostare un numero di articolo parziale "8111"e premere TAB. Verrà visualizzata la finestra pop-up per la ricerca dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="5b92f-118">For this sample procedure enter a partial item number of '8111' and press tab. This will pop up the item search window.</span></span>  
9. <span data-ttu-id="5b92f-119">Selezionare il prodotto da aggiungere all'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="5b92f-119">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="5b92f-120">Immettere la quantità di vendita.</span><span class="sxs-lookup"><span data-stu-id="5b92f-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="5b92f-121">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="5b92f-121">Click Create.</span></span>
12. <span data-ttu-id="5b92f-122">Fare clic su Completa per acquisire il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="5b92f-122">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="5b92f-123">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5b92f-123">Click Add.</span></span>
    * <span data-ttu-id="5b92f-124">Il collegamento Aggiungi è presente nella scheda Pagamenti. Espandere la scheda Pagamenti se è compressa.</span><span class="sxs-lookup"><span data-stu-id="5b92f-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="5b92f-125">Selezionare il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5b92f-125">Select the payment method.</span></span>
    * <span data-ttu-id="5b92f-126">Selezionare il metodo di pagamento in contanti per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="5b92f-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="5b92f-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5b92f-127">Close the page.</span></span>
16. <span data-ttu-id="5b92f-128">Immettere l'importo.</span><span class="sxs-lookup"><span data-stu-id="5b92f-128">Enter the amount.</span></span>
    * <span data-ttu-id="5b92f-129">Per questa procedura immettere un importo uguale al saldo ordine che può essere presente nella pagina di riepilogo Ordine cliente a sinistra del campo dell'importo.</span><span class="sxs-lookup"><span data-stu-id="5b92f-129">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="5b92f-130">In tal modo sarà possibile completare l'ordine come interamente pagato.</span><span class="sxs-lookup"><span data-stu-id="5b92f-130">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="5b92f-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5b92f-131">Click OK.</span></span>
18. <span data-ttu-id="5b92f-132">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="5b92f-132">Click Submit.</span></span>
