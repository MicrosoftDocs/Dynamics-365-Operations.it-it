---
title: Approvare fornitori per prodotti specifici
description: Questa procedura mostra come approvare i fornitori per prodotti specifici.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f2cd1badb0b924150ab51ef2efc049e6666562a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559211"
---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="8e08f-103">Approvare fornitori per prodotti specifici</span><span class="sxs-lookup"><span data-stu-id="8e08f-103">Approve vendors for specific products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e08f-104">Questa procedura mostra come approvare i fornitori per prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="8e08f-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="8e08f-105">Ciò consente di controllare quali fornitori possono essere utilizzati quando il prodotto viene aggiunto a un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="8e08f-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="8e08f-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="8e08f-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="8e08f-107">In genere questa attività sarà svolta da un responsabile acquisti.</span><span class="sxs-lookup"><span data-stu-id="8e08f-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="8e08f-108">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="8e08f-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="8e08f-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8e08f-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8e08f-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8e08f-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8e08f-111">Espandere la sezione Acquisto.</span><span class="sxs-lookup"><span data-stu-id="8e08f-111">Expand the Purchase section.</span></span>
    * <span data-ttu-id="8e08f-112">Se nel campo Fornitore è visualizzato un fornitore primario, è necessario aggiungere questo fornitore come fornitore approvato attenendosi ai passaggi che seguono.</span><span class="sxs-lookup"><span data-stu-id="8e08f-112">If there is a primary vendor shown in the Vendor field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="8e08f-113">Prendere nota del numero fornitore, se è visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8e08f-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="8e08f-114">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="8e08f-114">On the Action Pane, click Purchase.</span></span>
6. <span data-ttu-id="8e08f-115">Fare clic su Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="8e08f-115">Click Setup.</span></span>
7. <span data-ttu-id="8e08f-116">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8e08f-116">Click Add.</span></span>
8. <span data-ttu-id="8e08f-117">Nel campo Fornitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8e08f-117">In the Vendor field, enter or select a value.</span></span>
    * <span data-ttu-id="8e08f-118">Selezionare il fornitore approvato.</span><span class="sxs-lookup"><span data-stu-id="8e08f-118">Select the approved vendor.</span></span> <span data-ttu-id="8e08f-119">Almeno una delle righe deve essere il fornitore primario se ve ne era uno nel record del prodotto.</span><span class="sxs-lookup"><span data-stu-id="8e08f-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="8e08f-120">Se in precedenza si è preso nota del numero fornitore, selezionarlo in questo campo.</span><span class="sxs-lookup"><span data-stu-id="8e08f-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="8e08f-121">Nel campo Scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="8e08f-121">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="8e08f-122">Selezionare una data di qualche mese prima.</span><span class="sxs-lookup"><span data-stu-id="8e08f-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="8e08f-123">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8e08f-123">Click Add.</span></span>
11. <span data-ttu-id="8e08f-124">Nel campo Fornitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8e08f-124">In the Vendor field, enter or select a value.</span></span>
12. <span data-ttu-id="8e08f-125">Nel campo Scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="8e08f-125">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="8e08f-126">Selezionare una data diversa dalla data di scadenza precedente.</span><span class="sxs-lookup"><span data-stu-id="8e08f-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="8e08f-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-127">Close the page.</span></span>
14. <span data-ttu-id="8e08f-128">Fare clic su Fornitori approvati.</span><span class="sxs-lookup"><span data-stu-id="8e08f-128">Click Approved vendors.</span></span>
15. <span data-ttu-id="8e08f-129">Nel campo Scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="8e08f-129">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="8e08f-130">Questa data funge da filtro, pertanto è possibile visualizzare chi sono i fornitori approvati, fino a una determinata data.</span><span class="sxs-lookup"><span data-stu-id="8e08f-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="8e08f-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-131">Close the page.</span></span>
17. <span data-ttu-id="8e08f-132">Fare clic su Periodo di validità.</span><span class="sxs-lookup"><span data-stu-id="8e08f-132">Click Effective period.</span></span>
18. <span data-ttu-id="8e08f-133">Nel campo Mostra fornitori con scadenza entro immettere una data.</span><span class="sxs-lookup"><span data-stu-id="8e08f-133">In the Show vendors expired by field, enter a date.</span></span>
    * <span data-ttu-id="8e08f-134">È possibile utilizzare questa pagina per identificare i fornitori il cui stato di approvazione scadrà dopo una determinata data.</span><span class="sxs-lookup"><span data-stu-id="8e08f-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="8e08f-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-135">Close the page.</span></span>
20. <span data-ttu-id="8e08f-136">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8e08f-136">Click Edit.</span></span>
21. <span data-ttu-id="8e08f-137">Nel campo Metodo di verifica fornitore approvato selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="8e08f-137">In the Approved vendor check method field, select an option.</span></span>
    * <span data-ttu-id="8e08f-138">Questo campo consente di selezionare i criteri per le operazioni da verificare se il prodotto viene aggiunto a una riga ordine fornitore in cui il fornitore non è un fornitore approvato.</span><span class="sxs-lookup"><span data-stu-id="8e08f-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="8e08f-139">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8e08f-139">Click Save.</span></span>
23. <span data-ttu-id="8e08f-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-140">Close the page.</span></span>
24. <span data-ttu-id="8e08f-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-141">Close the page.</span></span>
25. <span data-ttu-id="8e08f-142">Andare ad Approvvigionamento > Fornitori > Relazioni fornitore/articolo > Elenco fornitori approvati per articolo.</span><span class="sxs-lookup"><span data-stu-id="8e08f-142">Go to Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item.</span></span>
    * <span data-ttu-id="8e08f-143">Questa pagina offre una panoramica di tutti i prodotti e i fornitori approvati.</span><span class="sxs-lookup"><span data-stu-id="8e08f-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="8e08f-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-144">Close the page.</span></span>
27. <span data-ttu-id="8e08f-145">Andare ad Approvvigionamento > Fornitori > Tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="8e08f-145">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
    * <span data-ttu-id="8e08f-146">È inoltre possibile iniziare da un fornitore e quindi accedere all'elenco dei prodotti approvati per quel conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="8e08f-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="8e08f-147">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8e08f-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="8e08f-148">Nel Riquadro azioni fare clic su Approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="8e08f-148">On the Action Pane, click Procurement.</span></span>
30. <span data-ttu-id="8e08f-149">Fare clic su Elenco fornitori approvati per fornitore.</span><span class="sxs-lookup"><span data-stu-id="8e08f-149">Click Approved vendor list by vendor.</span></span>
31. <span data-ttu-id="8e08f-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-150">Close the page.</span></span>
32. <span data-ttu-id="8e08f-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e08f-151">Close the page.</span></span>

