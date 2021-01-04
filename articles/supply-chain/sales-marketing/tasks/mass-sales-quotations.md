---
title: Creazione di massa offerte di vendita
description: Questa procedura dimostra la creazione efficientemente delle offerte che offrono un set di prodotti o servizi che devono essere inviati a più clienti.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 227ff0dd03f8917f4551ce08067ef26c6204b059
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430948"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="7f1fb-103">Creazione di massa offerte di vendita</span><span class="sxs-lookup"><span data-stu-id="7f1fb-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7f1fb-104">Questa procedura dimostra la creazione efficientemente delle offerte che offrono un set di prodotti o servizi che devono essere inviati a più clienti.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="7f1fb-105">La creazione di offerta di massa è basata sui modelli di offerta.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="7f1fb-106">È possibile eseguire questa procedura sui propri dati o nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="7f1fb-107">Creare un modello di offerta</span><span class="sxs-lookup"><span data-stu-id="7f1fb-107">Create a quotation template</span></span>
1. <span data-ttu-id="7f1fb-108">Passare a Vendite e marketing > Impostazione > Offerte > Gruppi di modelli.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="7f1fb-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-109">Click New.</span></span>
3. <span data-ttu-id="7f1fb-110">Nel campo ID gruppo, immettere un ID di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="7f1fb-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7f1fb-112">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-112">Click Save.</span></span>
6. <span data-ttu-id="7f1fb-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-113">Close the page.</span></span>
7. <span data-ttu-id="7f1fb-114">Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="7f1fb-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-115">Click New.</span></span>
9. <span data-ttu-id="7f1fb-116">Nel campo Tipo di conto selezionare "Cliente".</span><span class="sxs-lookup"><span data-stu-id="7f1fb-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="7f1fb-117">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="7f1fb-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-118">Click OK.</span></span>
    * <span data-ttu-id="7f1fb-119">Perché un'offerta diventi modello è necessario eseguire i passaggi di configurazione nell'intestazione dell'offerta.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="7f1fb-120">Questa operazione deve essere effettuata prima di aggiungere le righe all'offerta.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="7f1fb-121">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="7f1fb-122">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-122">Click Change view.</span></span>
14. <span data-ttu-id="7f1fb-123">Fare clic su Visualizzazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-123">Click Header view.</span></span>
15. <span data-ttu-id="7f1fb-124">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="7f1fb-125">Nel campo ID gruppo, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="7f1fb-126">Digitare un valore nel campo Nome modello.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="7f1fb-127">Selezionare Sì nel campo Attivo.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="7f1fb-128">Solo i modelli attivi possono essere utilizzati quando si applica un modello a una nuova offerta di vendita.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="7f1fb-129">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="7f1fb-130">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-130">Click Change view.</span></span>
21. <span data-ttu-id="7f1fb-131">Fare clic su Visualizzazione riga.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-131">Click Line view.</span></span>
22. <span data-ttu-id="7f1fb-132">Nel campo Articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="7f1fb-133">Digitare un valore nel campo Articolo.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="7f1fb-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-134">Close the page.</span></span>
25. <span data-ttu-id="7f1fb-135">Nel campo Percentuale sconto immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="7f1fb-136">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-136">Click Add line.</span></span>
27. <span data-ttu-id="7f1fb-137">Nel campo Articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="7f1fb-138">Digitare un valore nel campo Articolo.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="7f1fb-139">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-139">Close the page.</span></span>
30. <span data-ttu-id="7f1fb-140">Nel campo Prezzo unitario, immettere un nuovo prezzo o modificare quello corrente.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="7f1fb-141">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-141">Click Add line.</span></span>
32. <span data-ttu-id="7f1fb-142">Nel campo Articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="7f1fb-143">Digitare un valore nel campo Articolo.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="7f1fb-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-144">Close the page.</span></span>
35. <span data-ttu-id="7f1fb-145">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="7f1fb-146">Nel campo Sconto, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="7f1fb-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="7f1fb-148">Applicare il modello per creare una singola offerta</span><span class="sxs-lookup"><span data-stu-id="7f1fb-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="7f1fb-149">Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="7f1fb-150">Si noti che l'offerta appena creata è contrassegnata come modello.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="7f1fb-151">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-151">Click New.</span></span>
3. <span data-ttu-id="7f1fb-152">Nel campo Tipo di conto selezionare "Cliente".</span><span class="sxs-lookup"><span data-stu-id="7f1fb-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="7f1fb-153">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="7f1fb-154">Espandere la sezione Modello.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-154">Expand the Template section.</span></span>
6. <span data-ttu-id="7f1fb-155">Nel campo ID gruppo, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="7f1fb-156">Nel campo Nome modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="7f1fb-157">Nel campo Metodo di calcolo, selezionare "In base ai valori del modello".</span><span class="sxs-lookup"><span data-stu-id="7f1fb-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="7f1fb-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-158">Click OK.</span></span>
    * <span data-ttu-id="7f1fb-159">La nuova offerta ora è stata creata in base ai dati e ai termini del modello.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="7f1fb-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-160">Close the page.</span></span>
11. <span data-ttu-id="7f1fb-161">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="7f1fb-162">Applicare il modello per creare offerte in massa</span><span class="sxs-lookup"><span data-stu-id="7f1fb-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="7f1fb-163">Passare a Vendite e marketing > Offerte di vendita > Aggiornamento offerta > Creazione di massa offerte.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="7f1fb-164">Nel campo Tipo di conto selezionare "Cliente".</span><span class="sxs-lookup"><span data-stu-id="7f1fb-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="7f1fb-165">Nel campo ID gruppo, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="7f1fb-166">Nel campo Nome modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="7f1fb-167">Nel campo Metodo di calcolo, selezionare "In base ai valori del modello".</span><span class="sxs-lookup"><span data-stu-id="7f1fb-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="7f1fb-168">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="7f1fb-169">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-169">Click Filter.</span></span>
8. <span data-ttu-id="7f1fb-170">Nel campo Criteri, impostare il filtro per coprire un intervallo di clienti che si desidera includere nella creazione di massa offerte.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="7f1fb-171">Utilizzare il seguente formato "Customer1..CustomerN.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="7f1fb-172">Ad esempio, è possibile impostare il filtro su US-001..US-004</span><span class="sxs-lookup"><span data-stu-id="7f1fb-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="7f1fb-173">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-173">Click OK.</span></span>
10. <span data-ttu-id="7f1fb-174">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-174">Click OK.</span></span>
11. <span data-ttu-id="7f1fb-175">Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="7f1fb-176">Verificare che le offerte siano state create per tutti i clienti specificati nella routine di aggiornamento di massa, in base al modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="7f1fb-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  

