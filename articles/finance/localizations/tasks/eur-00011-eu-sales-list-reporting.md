---
title: EUR-00011 - Imposta dichiarazioni elenco vendite UE
description: Questa attività illustra una panoramica dei prerequisiti necessari per la dichiarazione dell'elenco vendite UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c312e14247c42acd5e0de5df02833275d9e3a4f1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140699"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="f11c1-103">EUR-00011 - Imposta dichiarazioni elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f11c1-104">Questa attività illustra una panoramica dei prerequisiti necessari per la dichiarazione dell'elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="f11c1-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="f11c1-105">Per ulteriori informazioni sulla dichiarazione elenco vendite UE, inclusi i prerequisiti necessari, consultare la Guida.</span><span class="sxs-lookup"><span data-stu-id="f11c1-105">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="f11c1-106">Questa attività si applica a tutti i paesi europei.</span><span class="sxs-lookup"><span data-stu-id="f11c1-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="f11c1-107">La guida è stata creata utilizzando la società di dati dimostrativi DEMF e di conseguenza la Germania come paese di esempio.</span><span class="sxs-lookup"><span data-stu-id="f11c1-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="f11c1-108">Nella guida si utilizza anche il Portogallo come paese UE di esempio.</span><span class="sxs-lookup"><span data-stu-id="f11c1-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="f11c1-109">Queste attività sono destinate agli amministratori di sistema.</span><span class="sxs-lookup"><span data-stu-id="f11c1-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="f11c1-110">Importare configurazioni di report elettronici per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="f11c1-111">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="f11c1-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f11c1-112">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-112">Click Set active.</span></span>
3. <span data-ttu-id="f11c1-113">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="f11c1-113">Click Repositories.</span></span>
4. <span data-ttu-id="f11c1-114">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="f11c1-114">Click Open.</span></span>
5. <span data-ttu-id="f11c1-115">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="f11c1-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="f11c1-116">Fare clic su Filtro/ordinamento avanzato.</span><span class="sxs-lookup"><span data-stu-id="f11c1-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="f11c1-117">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="f11c1-117">Click Add.</span></span>
8. <span data-ttu-id="f11c1-118">Nel campo Campo selezionare 'Nome configurazione'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="f11c1-119">Nel campo Criteri, immettere 'Elenco vendite UE (DE)'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="f11c1-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f11c1-120">Click OK.</span></span>
11. <span data-ttu-id="f11c1-121">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="f11c1-121">Click Import.</span></span>
12. <span data-ttu-id="f11c1-122">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="f11c1-122">Click Yes.</span></span>
13. <span data-ttu-id="f11c1-123">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="f11c1-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="f11c1-124">Fare clic su Filtro/ordinamento avanzato.</span><span class="sxs-lookup"><span data-stu-id="f11c1-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="f11c1-125">Fare clic su Reimposta.</span><span class="sxs-lookup"><span data-stu-id="f11c1-125">Click Reset.</span></span>
16. <span data-ttu-id="f11c1-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="f11c1-126">Click Add.</span></span>
17. <span data-ttu-id="f11c1-127">Nel campo Campo selezionare 'Nome configurazione'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="f11c1-128">Nel campo Criteri, immettere 'Elenco vendite UE per report righe'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="f11c1-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f11c1-129">Click OK.</span></span>
20. <span data-ttu-id="f11c1-130">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="f11c1-130">Click Import.</span></span>
21. <span data-ttu-id="f11c1-131">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="f11c1-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="f11c1-132">Impostare codici IVA per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="f11c1-133">Andare a Imposta > Imposte indirette > IVA > Codici IVA.</span><span class="sxs-lookup"><span data-stu-id="f11c1-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="f11c1-134">Utilizzare il filtro rapido per filtrare il campo Codice IVA in base a un valore di 'VAT19'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="f11c1-135">Espandere la sezione Impostazione report.</span><span class="sxs-lookup"><span data-stu-id="f11c1-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="f11c1-136">Verificare che la selezione Escluso sia impostata su No.</span><span class="sxs-lookup"><span data-stu-id="f11c1-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="f11c1-137">Può essere necessario sbloccare la guida di attività per modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="f11c1-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="f11c1-138">Impostare fasce IVA per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="f11c1-139">Passare a Imposta > Imposte indirette > IVA > Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="f11c1-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="f11c1-140">Utilizzare il filtro rapido per filtrare il campo Fascia IVA in base a un valore di 'AR-DOM'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="f11c1-141">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="f11c1-141">Click Edit.</span></span>
4. <span data-ttu-id="f11c1-142">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="f11c1-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="f11c1-143">Nell'elenco selezionare la prima riga.</span><span class="sxs-lookup"><span data-stu-id="f11c1-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="f11c1-144">Selezionare la casella di controllo Esente.</span><span class="sxs-lookup"><span data-stu-id="f11c1-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="f11c1-145">Nell'elenco selezionare la seconda riga.</span><span class="sxs-lookup"><span data-stu-id="f11c1-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="f11c1-146">Selezionare la casella di controllo Esente.</span><span class="sxs-lookup"><span data-stu-id="f11c1-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="f11c1-147">Nell'elenco selezionare la terza riga.</span><span class="sxs-lookup"><span data-stu-id="f11c1-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="f11c1-148">Selezionare la casella di controllo Esente.</span><span class="sxs-lookup"><span data-stu-id="f11c1-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="f11c1-149">Impostare fasce IVA articoli per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="f11c1-150">Passare a Imposta > Imposte indirette > IVA > Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="f11c1-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="f11c1-151">Utilizzare il filtro rapido per filtrare il campo Fascia IVA articoli in base a un valore di 'FULL'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="f11c1-152">Verificare che la selezione Tipo di dichiarazione sia impostata su 'Articolo'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="f11c1-153">Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="f11c1-154">Utilizzare il filtro rapido per filtrare il campo Fascia IVA articoli in base a un valore di 'RED'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="f11c1-155">Verificare che la selezione Tipo di dichiarazione sia impostata su 'Servizio'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="f11c1-156">Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="f11c1-157">Impostare parametri paese per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="f11c1-158">Passare a Imposta > Impostazione > IVA > Parametri paese.</span><span class="sxs-lookup"><span data-stu-id="f11c1-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="f11c1-159">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-159">Click New.</span></span>
3. <span data-ttu-id="f11c1-160">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="f11c1-161">Nel campo IVA, immettere 'PT'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="f11c1-162">Creare partite IVA</span><span class="sxs-lookup"><span data-stu-id="f11c1-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="f11c1-163">Passare a Imposta > Impostazione > IVA > Partite IVA.</span><span class="sxs-lookup"><span data-stu-id="f11c1-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="f11c1-164">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-164">Click New.</span></span>
3. <span data-ttu-id="f11c1-165">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="f11c1-166">Nel campo Partita IVA digitare 'PT12345'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="f11c1-167">Impostare parametri per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="f11c1-168">Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="f11c1-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="f11c1-169">Fare clic sulla scheda Elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="f11c1-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="f11c1-170">Selezionare Sì nel campo Trasferisci acquisti.</span><span class="sxs-lookup"><span data-stu-id="f11c1-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="f11c1-171">Espandere la sezione Regole di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="f11c1-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="f11c1-172">Impostare Regola di arrotondamento su '0.1'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="f11c1-173">Selezionare Sì nel campo Utilizzare il valore minimo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="f11c1-174">Immettere '2' nel campo Numero di decimali.</span><span class="sxs-lookup"><span data-stu-id="f11c1-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="f11c1-175">Espandere la sezione Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="f11c1-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="f11c1-176">Nel campo Mapping formato file, selezionare 'Elenco vendite UE (DE)'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="f11c1-177">Nel campo Mapping formato report, selezionare 'Elenco vendite UE per report righe'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="f11c1-178">Fare clic sulla scheda Proprietà paese.</span><span class="sxs-lookup"><span data-stu-id="f11c1-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="f11c1-179">Verificare che il campo Tipo di paese sia impostato su 'Nazionale' per Paese DEU.</span><span class="sxs-lookup"><span data-stu-id="f11c1-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="f11c1-180">Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="f11c1-181">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-181">Click New.</span></span>
13. <span data-ttu-id="f11c1-182">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="f11c1-183">Digitare 'PT' nel campo Codice Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f11c1-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="f11c1-184">Nel campo Tipo di paese selezionare 'UE'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="f11c1-185">Fare clic sulla scheda Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="f11c1-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="f11c1-186">Verificare che un codice di sequenza numerica sia specificato per l'elenco vendite UE di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f11c1-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="f11c1-187">Creare un cliente a scopo dimostrativo della dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="f11c1-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="f11c1-188">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="f11c1-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="f11c1-189">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f11c1-189">Click New.</span></span>
3. <span data-ttu-id="f11c1-190">Nel campo Conto cliente digitare 'PRT-001'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="f11c1-191">Nel campo Nome digitare 'Cliente dal Portogallo'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="f11c1-192">Nel campo Gruppo di clienti, selezionare '10'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="f11c1-193">Nel campo Fascia IVA selezionare 'AR-DOM'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="f11c1-194">Nel campo Partita IVA selezionare 'PT12345'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="f11c1-195">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="f11c1-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="f11c1-196">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f11c1-196">Click Save.</span></span>

