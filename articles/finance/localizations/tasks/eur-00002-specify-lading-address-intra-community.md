---
title: EUR-00002 Specifica di un indirizzo di carico per una transazione intracomunitaria
description: In questa procedura viene illustrato come specificare un indirizzo di carico per una transazione per il commercio intracomunitario.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid,  VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9b657629e53488bbac222428cdb88c21deb2847c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227997"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="8a1cd-103">EUR-00002 Specifica di un indirizzo di carico per una transazione intracomunitaria</span><span class="sxs-lookup"><span data-stu-id="8a1cd-103">EUR-00002 Specifying a lading address for an intra-community transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8a1cd-104">In questa procedura viene illustrato come specificare un indirizzo di carico per una transazione per il commercio intracomunitario.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="8a1cd-105">Ad esempio, una società in Germania ordina articoli da un fornitore con un indirizzo commerciale tedesco.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="8a1cd-106">Tale fornitore ha un magazzino in Italia e spedisce gli articoli da lì.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="8a1cd-107">Questa consegna deve essere dichiarata in Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="8a1cd-108">Lo stesso comportamento è valido per i resi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="8a1cd-109">Questa procedura si applica a tutti i paesi europei.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="8a1cd-110">L'attività è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Germania.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="8a1cd-111">Prima di poter completare questa procedura, è necessario configurare la dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="8a1cd-112">Questa procedura è destinata ai contabili.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="8a1cd-113">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="8a1cd-114">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="8a1cd-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-115">Click New.</span></span>
3. <span data-ttu-id="8a1cd-116">Immettere o selezionare un valore</span><span class="sxs-lookup"><span data-stu-id="8a1cd-116">Enter or select a value</span></span>
    * <span data-ttu-id="8a1cd-117">Selezionare, ad esempio, DE-001.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-117">For example, select DE-001.</span></span> <span data-ttu-id="8a1cd-118">Tale fornitore dispone di un indirizzo commerciale tedesco.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="8a1cd-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-119">Click OK.</span></span>
5. <span data-ttu-id="8a1cd-120">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="8a1cd-121">Nel campo Numero articolo immettere o selezionare il valore D0001.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="8a1cd-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-122">Click Save.</span></span>
8. <span data-ttu-id="8a1cd-123">Nel riquadro azioni fare clic su Ricevi.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="8a1cd-124">Fare clic su Dettagli trasporto.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-124">Click Transportation details.</span></span>
10. <span data-ttu-id="8a1cd-125">Nel campo Data/ora carico immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="8a1cd-126">Fare clic su Aggiungi indirizzo.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-126">Click Add address.</span></span>
12. <span data-ttu-id="8a1cd-127">Fare clic su Nuovo quindi creare il nuovo indirizzo con scopo Carico.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="8a1cd-128">Digitare 'Italiano' nel campo Nome o descrizione.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="8a1cd-129">Selezionare il valore Carico.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="8a1cd-130">Tenere presente che lo scopo dell'indirizzo deve esse Carico.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="8a1cd-131">Nel campo Paese immettere o selezionare un valore ITA.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="8a1cd-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-132">Click Save.</span></span>
17. <span data-ttu-id="8a1cd-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-133">Close the page.</span></span>
18. <span data-ttu-id="8a1cd-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-134">Click Save.</span></span>
    * <span data-ttu-id="8a1cd-135">Verificare che l'indirizzo di carico sia corretto.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="8a1cd-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-136">Close the page.</span></span>
20. <span data-ttu-id="8a1cd-137">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="8a1cd-138">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-138">Click Confirm.</span></span>
22. <span data-ttu-id="8a1cd-139">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="8a1cd-140">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-140">Click Invoice.</span></span>
24. <span data-ttu-id="8a1cd-141">Digitare un valore nel campo Numero.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="8a1cd-142">Immettere una data nel campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="8a1cd-143">Fare clic su Predefinito da: Quantità entrata prodotti per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="8a1cd-144">Nel campo Quantità predefinita per le righe, selezionare 'Quantità ordinata'.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="8a1cd-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-145">Click OK.</span></span>
29. <span data-ttu-id="8a1cd-146">Fare clic su Dettagli trasporto.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-146">Click Transportation details.</span></span>
    * <span data-ttu-id="8a1cd-147">Verificare che le merci siano state spedite dall'Italia.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="8a1cd-148">Se necessario, è possibile modificare i dettagli di carico.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="8a1cd-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-149">Close the page.</span></span>
31. <span data-ttu-id="8a1cd-150">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-150">Click Post.</span></span>
32. <span data-ttu-id="8a1cd-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-151">Close the page.</span></span>
33. <span data-ttu-id="8a1cd-152">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="8a1cd-153">Fare clic su Trasferisci.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-153">Click Transfer.</span></span>
35. <span data-ttu-id="8a1cd-154">Selezionare Sì nel campo Fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="8a1cd-155">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-155">Click OK.</span></span>
37. <span data-ttu-id="8a1cd-156">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-156">Click the General tab.</span></span>
    * <span data-ttu-id="8a1cd-157">Individuare una riga creata di recente e verificare che il mittente abbia spedito le merci dall'Italia.</span><span class="sxs-lookup"><span data-stu-id="8a1cd-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]