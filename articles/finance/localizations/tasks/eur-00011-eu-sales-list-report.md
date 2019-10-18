---
title: EUR-00011 - Generare la dichiarazione Elenco vendite UE
description: In questa procedura vengono descritti i passaggi per generare il report elenco vendite UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7038af3977797a0be2523f2414800400757b7007
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183707"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a><span data-ttu-id="2d716-103">EUR-00011 - Generare la dichiarazione Elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="2d716-103">EUR-00011 Generate the EU sales list report</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2d716-104">In questa procedura vengono descritti i passaggi per generare il report elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="2d716-104">This procedure walks you through generating the EU sales list report.</span></span> <span data-ttu-id="2d716-105">È incluso il trasferimento delle transazioni commerciali intracomunitarie nell'elenco vendite UE e l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="2d716-105">This includes transferring intra-community trade transactions to the EU sales list and running the report.</span></span> <span data-ttu-id="2d716-106">Questa procedura include inoltre la creazione di una transazione commerciale intracomunitaria per fini dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="2d716-106">This procedure also includes creating an intra-community trade transaction for demo purposes.</span></span> <span data-ttu-id="2d716-107">Per ulteriori informazioni sulla dichiarazione elenco vendite UE, inclusi i prerequisiti necessari, consultare la Guida.</span><span class="sxs-lookup"><span data-stu-id="2d716-107">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="2d716-108">Questa procedura si applica a tutti i paesi europei.</span><span class="sxs-lookup"><span data-stu-id="2d716-108">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="2d716-109">La procedura è stata creata utilizzando la società di dati dimostrativi DEMF e di conseguenza la Germania come paese di esempio.</span><span class="sxs-lookup"><span data-stu-id="2d716-109">The procedure was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="2d716-110">Nella procedura si utilizza anche il Portogallo come paese UE di esempio.</span><span class="sxs-lookup"><span data-stu-id="2d716-110">The procedure also uses Portugal as an exemplar EU country/region.</span></span> <span data-ttu-id="2d716-111">Prima di poter completare questa procedura, è necessario configurare la dichiarazione dell'elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="2d716-111">Before you can complete this procedure, you must configure EU sales list reporting.</span></span>

<span data-ttu-id="2d716-112">Questa procedura è destinata ai contabili.</span><span class="sxs-lookup"><span data-stu-id="2d716-112">This procedure is intended for accountants.</span></span>


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a><span data-ttu-id="2d716-113">Creare una transazione di vendita intracomunitaria per fini dimostrativi</span><span class="sxs-lookup"><span data-stu-id="2d716-113">Create an intra-community sales transaction for demo purposes</span></span>
1. <span data-ttu-id="2d716-114">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="2d716-114">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="2d716-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d716-115">Click New.</span></span>
3. <span data-ttu-id="2d716-116">Nel campo Conto cliente digitare 'PRT-001'.</span><span class="sxs-lookup"><span data-stu-id="2d716-116">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="2d716-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2d716-117">Click OK.</span></span>
5. <span data-ttu-id="2d716-118">Nel campo Numero articolo digitare "D0001".</span><span class="sxs-lookup"><span data-stu-id="2d716-118">In the Item number field, type 'D0001'.</span></span>
6. <span data-ttu-id="2d716-119">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="2d716-119">Expand the Line details section.</span></span>
7. <span data-ttu-id="2d716-120">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2d716-120">Click the Setup tab.</span></span>
8. <span data-ttu-id="2d716-121">Nel campo Fascia IVA articoli digitare 'FULL'.</span><span class="sxs-lookup"><span data-stu-id="2d716-121">In the Item sales tax group field, type 'FULL'.</span></span>
9. <span data-ttu-id="2d716-122">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="2d716-122">Click Add line.</span></span>
10. <span data-ttu-id="2d716-123">Nel campo Numero articolo digitare "D0003".</span><span class="sxs-lookup"><span data-stu-id="2d716-123">In the Item number field, type 'D0003'.</span></span>
11. <span data-ttu-id="2d716-124">Nel campo Fascia IVA articoli digitare 'RED'.</span><span class="sxs-lookup"><span data-stu-id="2d716-124">In the Item sales tax group field, type 'RED'.</span></span>
12. <span data-ttu-id="2d716-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2d716-125">Click Save.</span></span>
13. <span data-ttu-id="2d716-126">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="2d716-126">On the Action Pane, click Invoice.</span></span>
14. <span data-ttu-id="2d716-127">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="2d716-127">Click Invoice.</span></span>
15. <span data-ttu-id="2d716-128">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="2d716-128">Expand the Parameters section.</span></span>
16. <span data-ttu-id="2d716-129">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="2d716-129">In the Quantity field, select 'All'.</span></span>
17. <span data-ttu-id="2d716-130">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="2d716-130">Expand the Setup section.</span></span>
18. <span data-ttu-id="2d716-131">Nel campo Data fattura impostare la data su '01/11/2016'.</span><span class="sxs-lookup"><span data-stu-id="2d716-131">In the Invoice date field, set the date to '01/11/2016'.</span></span>
19. <span data-ttu-id="2d716-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2d716-132">Click OK.</span></span>
20. <span data-ttu-id="2d716-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2d716-133">Click OK.</span></span>

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a><span data-ttu-id="2d716-134">Trasferire le transazioni commerciali intracomunitarie nell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="2d716-134">Transfer intra-community trade transactions to the EU sales list</span></span>
1. <span data-ttu-id="2d716-135">Passare a Imposta > Dichiarazioni > Commercio estero > Elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="2d716-135">Go to Tax > Declarations > Foreign trade > EU sales list.</span></span>
2. <span data-ttu-id="2d716-136">Fare clic su Trasferisci.</span><span class="sxs-lookup"><span data-stu-id="2d716-136">Click Transfer.</span></span>
3. <span data-ttu-id="2d716-137">Selezionare Sì nel campo Articolo per trasferire le transazioni articolo.</span><span class="sxs-lookup"><span data-stu-id="2d716-137">Select Yes in the Item field to transfer item transactions.</span></span>
4. <span data-ttu-id="2d716-138">Selezionare Sì nel campo Servizio per trasferire le transazioni servizio.</span><span class="sxs-lookup"><span data-stu-id="2d716-138">Select Yes in the Service field to transfer service transactions.</span></span>
    * <span data-ttu-id="2d716-139">È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da trasferire.</span><span class="sxs-lookup"><span data-stu-id="2d716-139">You can also specify additional filters on intra-community trade transactions to transfer.</span></span>  
5. <span data-ttu-id="2d716-140">Fare clic su Trasferisci.</span><span class="sxs-lookup"><span data-stu-id="2d716-140">Click Transfer.</span></span>
    * <span data-ttu-id="2d716-141">Verificare che la transazione di vendita intracomunitaria venga trasferita correttamente nell'elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="2d716-141">Verify that the intra-community sales transaction is successfully transferred to the EU sales list.</span></span>  

## <a name="generate-the-eu-sales-list-report"></a><span data-ttu-id="2d716-142"> Genera report elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="2d716-142">Generate the EU sales list report</span></span>
1. <span data-ttu-id="2d716-143">Fare clic su Dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="2d716-143">Click Reporting.</span></span>
2. <span data-ttu-id="2d716-144">Nel campo Periodo di reporting selezionare 'Mensile'.</span><span class="sxs-lookup"><span data-stu-id="2d716-144">In the Reporting period field, select 'Monthly'.</span></span>
3. <span data-ttu-id="2d716-145">Nel campo Data iniziale impostare la data su '01/01/2016'.</span><span class="sxs-lookup"><span data-stu-id="2d716-145">In the From date field, set the date to '01/01/2016'.</span></span>
4. <span data-ttu-id="2d716-146">Selezionare Sì nel campo Genera file.</span><span class="sxs-lookup"><span data-stu-id="2d716-146">Select Yes in the Generate file field.</span></span>
5. <span data-ttu-id="2d716-147">Selezionare Sì nel campo Genera report.</span><span class="sxs-lookup"><span data-stu-id="2d716-147">Select Yes in the Generate report field.</span></span>
6. <span data-ttu-id="2d716-148">Nel campo Nome file digitare 'EUSalesList'.</span><span class="sxs-lookup"><span data-stu-id="2d716-148">In the File name field, type 'EUSalesList'.</span></span>
7. <span data-ttu-id="2d716-149">Nel campo Nome file report digitare 'EUSalesList'.</span><span class="sxs-lookup"><span data-stu-id="2d716-149">In the Report file name field, type 'EUSalesList'.</span></span>
8. <span data-ttu-id="2d716-150">Nel campo ID registrazione elenco vendite UE, immettere '123'.</span><span class="sxs-lookup"><span data-stu-id="2d716-150">In the EU Sales List Registration ID field, type '123'.</span></span>
    * <span data-ttu-id="2d716-151">Questo campo è disponibile solo per la Germania.</span><span class="sxs-lookup"><span data-stu-id="2d716-151">This field is only available for Germany.</span></span>  
    * <span data-ttu-id="2d716-152">È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da includere nel report.</span><span class="sxs-lookup"><span data-stu-id="2d716-152">You can also specify additional filters on intra-community trade transactions to include in the report.</span></span>  
9. <span data-ttu-id="2d716-153">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2d716-153">Click OK.</span></span>
    * <span data-ttu-id="2d716-154">Verificare che le finestre popup vengano visualizzate per confermare che il file e il report di controllo vengano scaricati.</span><span class="sxs-lookup"><span data-stu-id="2d716-154">Verify that pop-up windows appear to confirm that the file and the control report are being downloaded.</span></span>  

## <a name="mark-eu-sales-list-lines-as-reported"></a><span data-ttu-id="2d716-155">Contrassegnare le righe dell'elenco vendite UE come dichiarate</span><span class="sxs-lookup"><span data-stu-id="2d716-155">Mark EU sales list lines as Reported</span></span>
1. <span data-ttu-id="2d716-156">Fare clic su Contrassegna.</span><span class="sxs-lookup"><span data-stu-id="2d716-156">Click Mark.</span></span>
2. <span data-ttu-id="2d716-157">Fare clic su Contrassegna come dichiarato.</span><span class="sxs-lookup"><span data-stu-id="2d716-157">Click Mark as reported.</span></span>
3. <span data-ttu-id="2d716-158">Nell'elenco, selezionare la riga per il campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="2d716-158">In the list, select the row for the Invoice date field.</span></span>
4. <span data-ttu-id="2d716-159">Nel campo Criteri, immettere '01/01/2016..01/31/2016'.</span><span class="sxs-lookup"><span data-stu-id="2d716-159">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="2d716-160">Nell'elenco, selezionare la riga per il campo Stato relazione.</span><span class="sxs-lookup"><span data-stu-id="2d716-160">In the list, select the row for the Reporting status field.</span></span>
6. <span data-ttu-id="2d716-161">Nel campo Criteri, selezionare 'Incluso'.</span><span class="sxs-lookup"><span data-stu-id="2d716-161">In the Criteria field, select 'Included'.</span></span>
    * <span data-ttu-id="2d716-162">È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da contrassegnare come dichiarate.</span><span class="sxs-lookup"><span data-stu-id="2d716-162">You can also specify additional filters on intra-community trade transactions to mark as Reported.</span></span>  
7. <span data-ttu-id="2d716-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2d716-163">Click OK.</span></span>
8. <span data-ttu-id="2d716-164">Selezionare 'Dichiarato' nel campo Selezione.</span><span class="sxs-lookup"><span data-stu-id="2d716-164">In the Selection field, select 'Reported'.</span></span>

## <a name="mark-eu-sales-list-lines-as-closed"></a><span data-ttu-id="2d716-165">Contrassegnare le righe dell'elenco vendite UE come chiuse</span><span class="sxs-lookup"><span data-stu-id="2d716-165">Mark EU sales list lines as Closed</span></span>
1. <span data-ttu-id="2d716-166">Fare clic su Contrassegna.</span><span class="sxs-lookup"><span data-stu-id="2d716-166">Click Mark.</span></span>
2. <span data-ttu-id="2d716-167">Fare clic su Contrassegna come chiuso.</span><span class="sxs-lookup"><span data-stu-id="2d716-167">Click Mark as closed.</span></span>
3. <span data-ttu-id="2d716-168">Nell'elenco, contrassegnare la riga per il campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="2d716-168">In the list, mark the row for the Invoice date field.</span></span>
4. <span data-ttu-id="2d716-169">Nel campo Criteri, immettere '01/01/2016..01/31/2016'.</span><span class="sxs-lookup"><span data-stu-id="2d716-169">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="2d716-170">Nell'elenco, contrassegnare la riga per il campo Stato relazione.</span><span class="sxs-lookup"><span data-stu-id="2d716-170">In the list, mark the row for the Reporting status field.</span></span>
6. <span data-ttu-id="2d716-171">Nel campo Criteri, selezionare 'Dichiarato'.</span><span class="sxs-lookup"><span data-stu-id="2d716-171">In the Criteria field, select ‘Reported’.</span></span>
    * <span data-ttu-id="2d716-172">È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da contrassegnare come chiuse.</span><span class="sxs-lookup"><span data-stu-id="2d716-172">You can also specify additional filters on intra-community trade transactions to mark as Closed.</span></span>  
7. <span data-ttu-id="2d716-173">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2d716-173">Click OK.</span></span>
8. <span data-ttu-id="2d716-174">Selezionare 'Chiuso' nel campo Selezione.</span><span class="sxs-lookup"><span data-stu-id="2d716-174">In the Selection field, select 'Closed'.</span></span>

