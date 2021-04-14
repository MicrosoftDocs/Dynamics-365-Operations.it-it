---
title: " Creare ordini del servizio clienti"
description: In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8dc9e19ecd6b835569ba80563bce33134895cb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791657"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="47519-103"> Creare ordini del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="47519-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47519-104">In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="47519-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="47519-105">Questa procedura utilizza la società di dati dimostrativi USRT ed è destinata all'addetto degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="47519-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="47519-106">Prerequisiti: l'utente che completa la procedura viene impostato come utente del servizio clienti e il catalogo semestrale di Fabrikam è pubblicato con almeno un codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="47519-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="47519-107">Passare a **Retail e Commerce \> Clienti \> Servizio clienti**.</span><span class="sxs-lookup"><span data-stu-id="47519-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="47519-108">Nel campo **Cerca testo**, immettere i criteri di ricerca per cercare il cliente.</span><span class="sxs-lookup"><span data-stu-id="47519-108">For **SearchText**, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="47519-109">Per questa procedura di esempio, digitare "Karen" e premere **TAB**.</span><span class="sxs-lookup"><span data-stu-id="47519-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="47519-110">Selezionare Cerca.</span><span class="sxs-lookup"><span data-stu-id="47519-110">Select Search.</span></span>
    * <span data-ttu-id="47519-111">Poiché è presente un solo cliente di nome "Karen" nei dati dimostrativi, il risultato viene automaticamente selezionato.</span><span class="sxs-lookup"><span data-stu-id="47519-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="47519-112">Selezionare **Nuovo ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="47519-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="47519-113">Espandere o comprimere la sezione **intestazione ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="47519-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="47519-114">Selezionare il codice sorgente per il catalogo.</span><span class="sxs-lookup"><span data-stu-id="47519-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="47519-115">Se non sono presenti codici sorgente attivi è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="47519-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="47519-116">Selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="47519-116">Select **Add line**.</span></span>
8. <span data-ttu-id="47519-117">Nel campo **Numero articolo**, immettere il termine di ricerca per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="47519-117">For **Item number**, enter the item search term.</span></span>
    * <span data-ttu-id="47519-118">Per questa procedura di esempio impostare un numero di articolo parziale "8111" e premere TAB. Viene visualizzata la finestra pop-up per la ricerca dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="47519-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="47519-119">Selezionare il prodotto da aggiungere all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="47519-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="47519-120">Immettere la quantità di vendita.</span><span class="sxs-lookup"><span data-stu-id="47519-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="47519-121">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="47519-121">Select **Create**.</span></span>
12. <span data-ttu-id="47519-122">Selezionare **Completa** per acquisire il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="47519-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="47519-123">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="47519-123">Select **Add**.</span></span>
    * <span data-ttu-id="47519-124">Il collegamento Aggiungi è presente nella scheda Pagamenti. Espandere la scheda Pagamenti se è compressa.</span><span class="sxs-lookup"><span data-stu-id="47519-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="47519-125">Selezionare il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="47519-125">Select the payment method.</span></span>
    * <span data-ttu-id="47519-126">Selezionare il metodo di pagamento in contanti per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="47519-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="47519-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47519-127">Close the page.</span></span>
16. <span data-ttu-id="47519-128">Immettere l'importo.</span><span class="sxs-lookup"><span data-stu-id="47519-128">Enter the amount.</span></span>
    * <span data-ttu-id="47519-129">Per questa procedura immettere un importo uguale al saldo ordine che può essere presente nella pagina di riepilogo Ordine cliente a sinistra del campo dell'importo.</span><span class="sxs-lookup"><span data-stu-id="47519-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="47519-130">L'azione consente di completare l'ordine come interamente pagato.</span><span class="sxs-lookup"><span data-stu-id="47519-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="47519-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="47519-131">Select **OK**.</span></span>
18. <span data-ttu-id="47519-132">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="47519-132">Select **Submit**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="47519-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="47519-133">Additional resources</span></span>

[<span data-ttu-id="47519-134">Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="47519-134">Customize transactional emails by mode of delivery</span></span>](../customize-email-delivery-mode.md)

[<span data-ttu-id="47519-135">Modifica modalità di consegna nel POS</span><span class="sxs-lookup"><span data-stu-id="47519-135">Change mode of delivery in POS</span></span>](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]