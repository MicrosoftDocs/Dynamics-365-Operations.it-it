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
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0ce458697fd61aabddcbf844dd0b2afbe3aa1c0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228012"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="8409f-103">EUR-00011 - Imposta dichiarazioni elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8409f-104">Questa attività illustra una panoramica dei prerequisiti necessari per la dichiarazione dell'elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="8409f-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="8409f-105">Per ulteriori informazioni sulla dichiarazione elenco vendite UE, inclusi i prerequisiti necessari, consultare la Guida.</span><span class="sxs-lookup"><span data-stu-id="8409f-105">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="8409f-106">Questa attività si applica a tutti i paesi europei.</span><span class="sxs-lookup"><span data-stu-id="8409f-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="8409f-107">La guida è stata creata utilizzando la società di dati dimostrativi DEMF e di conseguenza la Germania come paese di esempio.</span><span class="sxs-lookup"><span data-stu-id="8409f-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="8409f-108">Nella guida si utilizza anche il Portogallo come paese UE di esempio.</span><span class="sxs-lookup"><span data-stu-id="8409f-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="8409f-109">Queste attività sono destinate agli amministratori di sistema.</span><span class="sxs-lookup"><span data-stu-id="8409f-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="8409f-110">Importare configurazioni di report elettronici per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="8409f-111">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8409f-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="8409f-112">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="8409f-112">Click Set active.</span></span>
3. <span data-ttu-id="8409f-113">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="8409f-113">Click Repositories.</span></span>
4. <span data-ttu-id="8409f-114">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="8409f-114">Click Open.</span></span>
5. <span data-ttu-id="8409f-115">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="8409f-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="8409f-116">Fare clic su Filtro/ordinamento avanzato.</span><span class="sxs-lookup"><span data-stu-id="8409f-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="8409f-117">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8409f-117">Click Add.</span></span>
8. <span data-ttu-id="8409f-118">Nel campo Campo selezionare 'Nome configurazione'.</span><span class="sxs-lookup"><span data-stu-id="8409f-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="8409f-119">Nel campo Criteri, immettere 'Elenco vendite UE (DE)'.</span><span class="sxs-lookup"><span data-stu-id="8409f-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="8409f-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8409f-120">Click OK.</span></span>
11. <span data-ttu-id="8409f-121">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="8409f-121">Click Import.</span></span>
12. <span data-ttu-id="8409f-122">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="8409f-122">Click Yes.</span></span>
13. <span data-ttu-id="8409f-123">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="8409f-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="8409f-124">Fare clic su Filtro/ordinamento avanzato.</span><span class="sxs-lookup"><span data-stu-id="8409f-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="8409f-125">Fare clic su Reimposta.</span><span class="sxs-lookup"><span data-stu-id="8409f-125">Click Reset.</span></span>
16. <span data-ttu-id="8409f-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8409f-126">Click Add.</span></span>
17. <span data-ttu-id="8409f-127">Nel campo Campo selezionare 'Nome configurazione'.</span><span class="sxs-lookup"><span data-stu-id="8409f-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="8409f-128">Nel campo Criteri, immettere 'Elenco vendite UE per report righe'.</span><span class="sxs-lookup"><span data-stu-id="8409f-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="8409f-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8409f-129">Click OK.</span></span>
20. <span data-ttu-id="8409f-130">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="8409f-130">Click Import.</span></span>
21. <span data-ttu-id="8409f-131">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="8409f-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="8409f-132">Impostare codici IVA per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="8409f-133">Andare a Imposta > Imposte indirette > IVA > Codici IVA.</span><span class="sxs-lookup"><span data-stu-id="8409f-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="8409f-134">Utilizzare il filtro rapido per filtrare il campo Codice IVA in base a un valore di 'VAT19'.</span><span class="sxs-lookup"><span data-stu-id="8409f-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="8409f-135">Espandere la sezione Impostazione report.</span><span class="sxs-lookup"><span data-stu-id="8409f-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="8409f-136">Verificare che la selezione Escluso sia impostata su No.</span><span class="sxs-lookup"><span data-stu-id="8409f-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="8409f-137">Può essere necessario sbloccare la guida di attività per modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="8409f-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="8409f-138">Impostare fasce IVA per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="8409f-139">Passare a Imposta > Imposte indirette > IVA > Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="8409f-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="8409f-140">Utilizzare il filtro rapido per filtrare il campo Fascia IVA in base a un valore di 'AR-DOM'.</span><span class="sxs-lookup"><span data-stu-id="8409f-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="8409f-141">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8409f-141">Click Edit.</span></span>
4. <span data-ttu-id="8409f-142">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="8409f-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="8409f-143">Nell'elenco selezionare la prima riga.</span><span class="sxs-lookup"><span data-stu-id="8409f-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="8409f-144">Selezionare la casella di controllo Esente.</span><span class="sxs-lookup"><span data-stu-id="8409f-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="8409f-145">Nell'elenco selezionare la seconda riga.</span><span class="sxs-lookup"><span data-stu-id="8409f-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="8409f-146">Selezionare la casella di controllo Esente.</span><span class="sxs-lookup"><span data-stu-id="8409f-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="8409f-147">Nell'elenco selezionare la terza riga.</span><span class="sxs-lookup"><span data-stu-id="8409f-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="8409f-148">Selezionare la casella di controllo Esente.</span><span class="sxs-lookup"><span data-stu-id="8409f-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="8409f-149">Impostare fasce IVA articoli per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="8409f-150">Passare a Imposta > Imposte indirette > IVA > Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="8409f-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="8409f-151">Utilizzare il filtro rapido per filtrare il campo Fascia IVA articoli in base a un valore di 'FULL'.</span><span class="sxs-lookup"><span data-stu-id="8409f-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="8409f-152">Verificare che la selezione Tipo di dichiarazione sia impostata su 'Articolo'.</span><span class="sxs-lookup"><span data-stu-id="8409f-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="8409f-153">Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.</span><span class="sxs-lookup"><span data-stu-id="8409f-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="8409f-154">Utilizzare il filtro rapido per filtrare il campo Fascia IVA articoli in base a un valore di 'RED'.</span><span class="sxs-lookup"><span data-stu-id="8409f-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="8409f-155">Verificare che la selezione Tipo di dichiarazione sia impostata su 'Servizio'.</span><span class="sxs-lookup"><span data-stu-id="8409f-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="8409f-156">Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.</span><span class="sxs-lookup"><span data-stu-id="8409f-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="8409f-157">Impostare parametri paese per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="8409f-158">Passare a Imposta > Impostazione > IVA > Parametri paese.</span><span class="sxs-lookup"><span data-stu-id="8409f-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="8409f-159">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8409f-159">Click New.</span></span>
3. <span data-ttu-id="8409f-160">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="8409f-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="8409f-161">Nel campo IVA, immettere 'PT'.</span><span class="sxs-lookup"><span data-stu-id="8409f-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="8409f-162">Creare partite IVA</span><span class="sxs-lookup"><span data-stu-id="8409f-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="8409f-163">Passare a Imposta > Impostazione > IVA > Partite IVA.</span><span class="sxs-lookup"><span data-stu-id="8409f-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="8409f-164">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8409f-164">Click New.</span></span>
3. <span data-ttu-id="8409f-165">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="8409f-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="8409f-166">Nel campo Partita IVA digitare 'PT12345'.</span><span class="sxs-lookup"><span data-stu-id="8409f-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="8409f-167">Impostare parametri per la dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="8409f-168">Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="8409f-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="8409f-169">Fare clic sulla scheda Elenco vendite UE.</span><span class="sxs-lookup"><span data-stu-id="8409f-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="8409f-170">Selezionare Sì nel campo Trasferisci acquisti.</span><span class="sxs-lookup"><span data-stu-id="8409f-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="8409f-171">Espandere la sezione Regole di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="8409f-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="8409f-172">Impostare Regola di arrotondamento su '0.1'.</span><span class="sxs-lookup"><span data-stu-id="8409f-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="8409f-173">Selezionare Sì nel campo Utilizzare il valore minimo.</span><span class="sxs-lookup"><span data-stu-id="8409f-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="8409f-174">Immettere '2' nel campo Numero di decimali.</span><span class="sxs-lookup"><span data-stu-id="8409f-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="8409f-175">Espandere la sezione Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8409f-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="8409f-176">Nel campo Mapping formato file, selezionare 'Elenco vendite UE (DE)'.</span><span class="sxs-lookup"><span data-stu-id="8409f-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="8409f-177">Nel campo Mapping formato report, selezionare 'Elenco vendite UE per report righe'.</span><span class="sxs-lookup"><span data-stu-id="8409f-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="8409f-178">Fare clic sulla scheda Proprietà paese.</span><span class="sxs-lookup"><span data-stu-id="8409f-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="8409f-179">Verificare che il campo Tipo di paese sia impostato su 'Nazionale' per Paese DEU.</span><span class="sxs-lookup"><span data-stu-id="8409f-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="8409f-180">Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.</span><span class="sxs-lookup"><span data-stu-id="8409f-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="8409f-181">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8409f-181">Click New.</span></span>
13. <span data-ttu-id="8409f-182">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="8409f-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="8409f-183">Digitare 'PT' nel campo Codice Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8409f-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="8409f-184">Nel campo Tipo di paese selezionare 'UE'.</span><span class="sxs-lookup"><span data-stu-id="8409f-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="8409f-185">Fare clic sulla scheda Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="8409f-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="8409f-186">Verificare che un codice di sequenza numerica sia specificato per l'elenco vendite UE di riferimento.</span><span class="sxs-lookup"><span data-stu-id="8409f-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="8409f-187">Creare un cliente a scopo dimostrativo della dichiarazione dell'elenco vendite UE</span><span class="sxs-lookup"><span data-stu-id="8409f-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="8409f-188">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="8409f-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="8409f-189">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8409f-189">Click New.</span></span>
3. <span data-ttu-id="8409f-190">Nel campo Conto cliente digitare 'PRT-001'.</span><span class="sxs-lookup"><span data-stu-id="8409f-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="8409f-191">Nel campo Nome digitare 'Cliente dal Portogallo'.</span><span class="sxs-lookup"><span data-stu-id="8409f-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="8409f-192">Nel campo Gruppo di clienti, selezionare '10'.</span><span class="sxs-lookup"><span data-stu-id="8409f-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="8409f-193">Nel campo Fascia IVA selezionare 'AR-DOM'.</span><span class="sxs-lookup"><span data-stu-id="8409f-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="8409f-194">Nel campo Partita IVA selezionare 'PT12345'.</span><span class="sxs-lookup"><span data-stu-id="8409f-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="8409f-195">Nel campo Paese, digitare 'PRT'.</span><span class="sxs-lookup"><span data-stu-id="8409f-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="8409f-196">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8409f-196">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]