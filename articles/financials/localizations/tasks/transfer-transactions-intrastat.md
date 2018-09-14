--- 
title: Trasferire transazioni a Intrastat
description: Questa procedura illustra come impostare i parametri Intrastat e trasferire le transazioni a Intrastat.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 13cc9dc2119ad3dc85d580e92edee7bb9ef2075c
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="817af-103">Trasferire transazioni a Intrastat</span><span class="sxs-lookup"><span data-stu-id="817af-103">Transfer transactions to the Intrastat</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="817af-104">Questa procedura illustra come impostare i parametri Intrastat e trasferire le transazioni a Intrastat.</span><span class="sxs-lookup"><span data-stu-id="817af-104">This procedure walks you through how to set up Intrastat parameters and transfer transactions to Intrastat.</span></span> <span data-ttu-id="817af-105">Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.</span><span class="sxs-lookup"><span data-stu-id="817af-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="create-new-and-update-existing-commodity-code"></a><span data-ttu-id="817af-106">Creare un nuovo codice voce doganale e aggiornarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="817af-106">Create new and update existing commodity code</span></span>
1. <span data-ttu-id="817af-107">Scegliere Gestione informazioni sul prodotto > Impostazioni > Categorie e attributi > Gerarchie di categorie.</span><span class="sxs-lookup"><span data-stu-id="817af-107">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="817af-108">Nell'elenco trovare o selezionare il record "Codici voci doganali Intrastat".</span><span class="sxs-lookup"><span data-stu-id="817af-108">In the list, find or select the record "Intrastat commodity codes."</span></span>
3. <span data-ttu-id="817af-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="817af-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="817af-110">Nella struttura selezionare "un record".</span><span class="sxs-lookup"><span data-stu-id="817af-110">In the tree, select 'a record'.</span></span>
    * <span data-ttu-id="817af-111">Ad esempio, selezionare "Intrastat\Altoparlante".</span><span class="sxs-lookup"><span data-stu-id="817af-111">For example, select 'Intrastat\Speaker'.</span></span>  
5. <span data-ttu-id="817af-112">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="817af-112">Click Edit.</span></span>
6. <span data-ttu-id="817af-113">Espandere la sezione Commercio estero.</span><span class="sxs-lookup"><span data-stu-id="817af-113">Expand the Foreign trade section.</span></span>
7. <span data-ttu-id="817af-114">Nel campo Unità aggiuntive immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-114">In the Additional units field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-115">Selezionare, ad esempio, "pz".</span><span class="sxs-lookup"><span data-stu-id="817af-115">For example, choose 'pcs'.</span></span>  
8. <span data-ttu-id="817af-116">Selezionare Sì nel campo Peso non applicabile.</span><span class="sxs-lookup"><span data-stu-id="817af-116">Select Yes in the Weight not applicable field.</span></span>
9. <span data-ttu-id="817af-117">Nella struttura selezionare "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="817af-117">In the tree, select 'Intrastat'.</span></span>
10. <span data-ttu-id="817af-118">Fare clic su nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="817af-118">Click New category node.</span></span>
11. <span data-ttu-id="817af-119">Nel campo Nome immettere il nome della voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-119">In the Name field, enter the name of commodity.</span></span>
    * <span data-ttu-id="817af-120">Ad esempio, immettere "Altra merce".</span><span class="sxs-lookup"><span data-stu-id="817af-120">For example, type 'Other commodity'.</span></span>  
12. <span data-ttu-id="817af-121">Nel campo Codice immettere il codice voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-121">In the Code field, enter the commodity code.</span></span>
    * <span data-ttu-id="817af-122">Ad esempio, digitare "995 00 00".</span><span class="sxs-lookup"><span data-stu-id="817af-122">For example, type '995 00 00'.</span></span>  
13. <span data-ttu-id="817af-123">Digitare un valore nel campo Nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="817af-123">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="817af-124">Ad esempio, digitare "Altro".</span><span class="sxs-lookup"><span data-stu-id="817af-124">For example, type 'Other'.</span></span>  
14. <span data-ttu-id="817af-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817af-125">Click Save.</span></span>
15. <span data-ttu-id="817af-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="817af-126">Close the page.</span></span>

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a><span data-ttu-id="817af-127">Assegnare il codice voce doganale alla gerarchia di prodotti e al prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="817af-127">Assign commodity code to product hierarchy and released product</span></span>
1. <span data-ttu-id="817af-128">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="817af-128">Use the Quick Filter to find records.</span></span> <span data-ttu-id="817af-129">Ad esempio, applicare un filtro al campo Nome in base al valore "vendite".</span><span class="sxs-lookup"><span data-stu-id="817af-129">For example, filter on the Name field with a value of 'sales'.</span></span>
2. <span data-ttu-id="817af-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="817af-130">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="817af-131">Nella struttura espandere "un nodo di categoria".</span><span class="sxs-lookup"><span data-stu-id="817af-131">In the tree, expand 'a category node'.</span></span>
    * <span data-ttu-id="817af-132">Ad esempio, espandere "Gerarchia di vendita\Audio home".</span><span class="sxs-lookup"><span data-stu-id="817af-132">For example, expand 'Sales hierarchy\Home audio'.</span></span>  
4. <span data-ttu-id="817af-133">Nella struttura selezionare "la categoria da assegnare al codice voce doganale".</span><span class="sxs-lookup"><span data-stu-id="817af-133">In the tree, select 'the category to assign to the commodity code'.</span></span>
    * <span data-ttu-id="817af-134">Ad esempio, selezionare "Gerarchia di vendita\Audio home\Altoparlanti".</span><span class="sxs-lookup"><span data-stu-id="817af-134">For example, select 'Sales hierarchy\Home audio\Speakers.</span></span>  
5. <span data-ttu-id="817af-135">Espandere la sezione Codici voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-135">Expand the Commodity codes section.</span></span>
6. <span data-ttu-id="817af-136">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="817af-136">Click Add.</span></span>
7. <span data-ttu-id="817af-137">Nel campo Seleziona gerarchia selezionare "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="817af-137">In the Select hierarchy field, select 'Intrastat'.</span></span>
8. <span data-ttu-id="817af-138">Nell'elenco trovare e selezionare il codice voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-138">In the list, find and select the commodity code</span></span>
    * <span data-ttu-id="817af-139">Ad esempio, selezionare "Altoparlante 920 20 34".</span><span class="sxs-lookup"><span data-stu-id="817af-139">For example, select '920 20 34 Speaker'.</span></span>  
9. <span data-ttu-id="817af-140">Fare clic su SelectCodes.</span><span class="sxs-lookup"><span data-stu-id="817af-140">Click SelectCodes.</span></span>
10. <span data-ttu-id="817af-141">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-141">Click OK.</span></span>
11. <span data-ttu-id="817af-142">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="817af-142">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="817af-143">Nell'elenco selezionare il prodotto rilasciato che verrà assegnato al codice voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-143">In the list, choose the released product that you will assign to the commodity code.</span></span>
    * <span data-ttu-id="817af-144">Selezionare, ad esempio, "D0001".</span><span class="sxs-lookup"><span data-stu-id="817af-144">For example, choose 'D0001'.</span></span>  
13. <span data-ttu-id="817af-145">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="817af-145">Click Edit.</span></span>
14. <span data-ttu-id="817af-146">Espandere la sezione Commercio estero.</span><span class="sxs-lookup"><span data-stu-id="817af-146">Expand the Foreign trade section.</span></span>
15. <span data-ttu-id="817af-147">Nel campo Voce doganale immettere il codice voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-147">In the Commodity field, enter the commodity code</span></span>
    * <span data-ttu-id="817af-148">Ad esempio, selezionare il valore "Altoparlante 920 20 34".</span><span class="sxs-lookup"><span data-stu-id="817af-148">For example, select value '920 20 34 Speaker'.</span></span>    
16. <span data-ttu-id="817af-149">Nel campo Perc. spese immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="817af-149">In the Charges percentage field, enter a number.</span></span>
    * <span data-ttu-id="817af-150">Ad esempio, immettere "3".</span><span class="sxs-lookup"><span data-stu-id="817af-150">For example, enter '3'.</span></span>  
17. <span data-ttu-id="817af-151">Nel campo Paese immettere o selezionare un paese di origine</span><span class="sxs-lookup"><span data-stu-id="817af-151">In the Country/region field, enter or select a country or region of origin</span></span>
    * <span data-ttu-id="817af-152">Selezionare, ad esempio, "AUT".</span><span class="sxs-lookup"><span data-stu-id="817af-152">For example, select 'AUT'.</span></span>  
18. <span data-ttu-id="817af-153">Espandere la sezione Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="817af-153">Expand the Manage inventory section.</span></span>
19. <span data-ttu-id="817af-154">Immettere un peso in kg. nel campo Peso netto.</span><span class="sxs-lookup"><span data-stu-id="817af-154">In the Net weight field, enter a weight in kg.</span></span>
    * <span data-ttu-id="817af-155">Ad esempio, immettere "2,5".</span><span class="sxs-lookup"><span data-stu-id="817af-155">For example, enter '2.5'.</span></span>  
20. <span data-ttu-id="817af-156">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817af-156">Click Save.</span></span>

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a><span data-ttu-id="817af-157">Impostare i codici transazione Intrastat e i parametri per il commercio estero</span><span class="sxs-lookup"><span data-stu-id="817af-157">Set up Intrastat transaction codes and foreign trade parameters</span></span>
1. <span data-ttu-id="817af-158">Passare a Imposta > Impostazione > Commercio estero > Codici transazioni</span><span class="sxs-lookup"><span data-stu-id="817af-158">Go to Tax > Setup > Foreign trade > Transaction codes</span></span>
2. <span data-ttu-id="817af-159">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="817af-159">Click New.</span></span>
3. <span data-ttu-id="817af-160">Nel campo Codice transazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-160">In the Transaction code field, type a value.</span></span>
    * <span data-ttu-id="817af-161">Ad esempio, impostare "21" per il codice transazione utilizzato come reso.</span><span class="sxs-lookup"><span data-stu-id="817af-161">For example, enter '21' for the transaction code used as return.</span></span>  
4. <span data-ttu-id="817af-162">Nel campo Nome digitare il nome del codice transazione.</span><span class="sxs-lookup"><span data-stu-id="817af-162">In the Name field, type the name of transaction code.</span></span>
    * <span data-ttu-id="817af-163">Ad esempio, immettere "Reso".</span><span class="sxs-lookup"><span data-stu-id="817af-163">For example, enter 'Return'.</span></span>  
5. <span data-ttu-id="817af-164">Selezionare un'opzione nel campo Importo statistico.</span><span class="sxs-lookup"><span data-stu-id="817af-164">In the Statistical amount field, select an option.</span></span>
    * <span data-ttu-id="817af-165">Ad esempio, selezionare "Vuoto" che indica che il valore statistico da dichiarare per le transazioni con il codice transazione "21" sarà sempre zero.</span><span class="sxs-lookup"><span data-stu-id="817af-165">For example, select 'Empty' which indicates that the Statistical value to be reported for transactions with Transaction code of "21" will always be zero.</span></span>  
6. <span data-ttu-id="817af-166">Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero</span><span class="sxs-lookup"><span data-stu-id="817af-166">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
7. <span data-ttu-id="817af-167">Nel campo Codice transazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-167">In the Transaction code field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-168">Ad esempio, selezionare "11".</span><span class="sxs-lookup"><span data-stu-id="817af-168">For example, select '11'.</span></span>  
8. <span data-ttu-id="817af-169">Nel campo Nota di accredito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-169">In the Credit note field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-170">Questo valore identifica anche il reso fisico.</span><span class="sxs-lookup"><span data-stu-id="817af-170">This value also identifies the physical return.</span></span> <span data-ttu-id="817af-171">La nota di accredito per il reso fisico verrà trasferita nel giornale di registrazione Intrastat con la direzione opposta.</span><span class="sxs-lookup"><span data-stu-id="817af-171">The credit note for the physical return will be transferred in the Intrastat journal with opposite direction.</span></span> <span data-ttu-id="817af-172">Ad esempio, il reso di arrivo viene trasferito come spedizione.</span><span class="sxs-lookup"><span data-stu-id="817af-172">For example, the return of arrival is transferred as dispatch.</span></span>   <span data-ttu-id="817af-173">In caso contrario, la nota di accredito viene considerata una correzione e viene trasferita con la stessa direzione e segno opposto.</span><span class="sxs-lookup"><span data-stu-id="817af-173">Otherwise, the credit note is considered a correction and is transferred with the same direction and opposite sign.</span></span> <span data-ttu-id="817af-174">Ad esempio, la correzione di arrivo viene trasferita come arrivo con importo negativo e il flag attivo è impostato su "Correzione".</span><span class="sxs-lookup"><span data-stu-id="817af-174">For example, the correction of arrival is transferred as an arrival with negative amount and the active flag is set to "Correction".</span></span>  
9. <span data-ttu-id="817af-175">Espandere la sezione Trasferimento.</span><span class="sxs-lookup"><span data-stu-id="817af-175">Expand the Transfer section.</span></span>
10. <span data-ttu-id="817af-176">Selezionare Sì nel campo Articoli con codice voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-176">Select Yes in the Items with commodity code field.</span></span>
    * <span data-ttu-id="817af-177">Selezionare questa opzione per trasferire solo le transazioni con un codice di voce doganale assegnato.</span><span class="sxs-lookup"><span data-stu-id="817af-177">Select this option to transfer only the transactions with a commodity code assigned.</span></span> <span data-ttu-id="817af-178">Le transazioni senza un codice di voce doganale non verranno trasferite a Intrastat.</span><span class="sxs-lookup"><span data-stu-id="817af-178">Transactions without a commodity code won't be transferred to Intrastat.</span></span>  
11. <span data-ttu-id="817af-179">Nel campo Trasferisci se è soddisfatto il criterio per selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="817af-179">In the Transfer when meeting criterion for field, select an option.</span></span>
    * <span data-ttu-id="817af-180">Ad esempio, selezionare "Uno di quelli selezionati".</span><span class="sxs-lookup"><span data-stu-id="817af-180">For example, select 'One of the selected'.</span></span>  
12. <span data-ttu-id="817af-181">Espandere la sezione Gerarchia di codici di voce doganale.</span><span class="sxs-lookup"><span data-stu-id="817af-181">Expand the Commodity code hierarchy section.</span></span>
13. <span data-ttu-id="817af-182">Fare clic sulla scheda Proprietà paese.</span><span class="sxs-lookup"><span data-stu-id="817af-182">Click the Country/region properties tab.</span></span>
14. <span data-ttu-id="817af-183">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="817af-183">Click New.</span></span>
15. <span data-ttu-id="817af-184">Nel campo Paese/regione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-184">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-185">Ad esempio, selezionare il valore "FRA".</span><span class="sxs-lookup"><span data-stu-id="817af-185">For example, select the value 'FRA'.</span></span>  
16. <span data-ttu-id="817af-186">Nel campo Codice Intrastat immettere il codice ISO del paese.</span><span class="sxs-lookup"><span data-stu-id="817af-186">In the Intrastat code field, enter the ISO code for the country.</span></span>
    * <span data-ttu-id="817af-187">Ad esempio, digitare "FR".</span><span class="sxs-lookup"><span data-stu-id="817af-187">For example, type 'FR'.</span></span>  
17. <span data-ttu-id="817af-188">Nel campo Tipo di paese selezionare 'UE'.</span><span class="sxs-lookup"><span data-stu-id="817af-188">In the Country/region type field, select 'EU'.</span></span>
18. <span data-ttu-id="817af-189">Fare clic sulla scheda Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="817af-189">Click the Number sequences tab.</span></span>

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a><span data-ttu-id="817af-190">Impostare le modalità di consegna e le regole per l'inclusione delle spese in Intrastat</span><span class="sxs-lookup"><span data-stu-id="817af-190">Set up Modes of delivery and rules for including charges in Intrastat</span></span>
1. <span data-ttu-id="817af-191">Passare a Vendite e marketing > Impostazione > Distribuzione > Modi di consegna</span><span class="sxs-lookup"><span data-stu-id="817af-191">Go to Sales and marketing > Setup > Distribution > Modes of delivery</span></span>
2. <span data-ttu-id="817af-192">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="817af-192">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="817af-193">Selezionare, ad esempio, "20 via aerea".</span><span class="sxs-lookup"><span data-stu-id="817af-193">For example, select '20 Air'.</span></span>  
3. <span data-ttu-id="817af-194">Espandere la sezione Commercio estero.</span><span class="sxs-lookup"><span data-stu-id="817af-194">Expand the Foreign trade section.</span></span>
4. <span data-ttu-id="817af-195">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="817af-195">Click Edit.</span></span>
5. <span data-ttu-id="817af-196">Nel campo Trasporto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-196">In the Transport field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-197">Ad esempio, selezionare "02".</span><span class="sxs-lookup"><span data-stu-id="817af-197">For example, select '02'.</span></span>  
6. <span data-ttu-id="817af-198">Passare a Contabilità clienti > Impostazione spese > Codice spese.</span><span class="sxs-lookup"><span data-stu-id="817af-198">Go to Accounts receivable > Charges setup > Charges code.</span></span>
7. <span data-ttu-id="817af-199">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="817af-199">Use the Quick Filter to find records.</span></span> <span data-ttu-id="817af-200">Ad esempio, filtrare il campo Codice spese in base al valore "spese di trasporto".</span><span class="sxs-lookup"><span data-stu-id="817af-200">For example, filter on the Charges code field with a value of 'freight'.</span></span>
8. <span data-ttu-id="817af-201">Espandere la sezione Commercio estero.</span><span class="sxs-lookup"><span data-stu-id="817af-201">Expand the Foreign trade section.</span></span>
9. <span data-ttu-id="817af-202">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="817af-202">Click Edit.</span></span>
10. <span data-ttu-id="817af-203">Selezionare Sì nel campo Valore fattura Intrastat.</span><span class="sxs-lookup"><span data-stu-id="817af-203">Select Yes in the Intrastat invoice value field.</span></span>
    * <span data-ttu-id="817af-204">L'importo verrà trasferito nel campo Spese fattura e verrà compendiato con l'importo trasferito nel campo Importo fattura.</span><span class="sxs-lookup"><span data-stu-id="817af-204">The amount will be transferred to the  Invoice charges field and will be summarized with the amount transferred in the Invoice amount field.</span></span>    <span data-ttu-id="817af-205">Selezionare Sì nel campo Valore statistico Intrastat se l'importo delle modifiche deve essere trasferito nel campo Spese statistiche e compendiato con Importo statistico.</span><span class="sxs-lookup"><span data-stu-id="817af-205">Select Yes in the Intrastat statistical value field if the amount of changes need to be transferred to the field Statistical charges and summarized with Statistical amount.</span></span>  

## <a name="sell-products-for-eu-customers"></a><span data-ttu-id="817af-206">Vendere prodotti per i clienti UE</span><span class="sxs-lookup"><span data-stu-id="817af-206">Sell products for EU customers</span></span>
1. <span data-ttu-id="817af-207">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="817af-207">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="817af-208">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="817af-208">Click New.</span></span>
3. <span data-ttu-id="817af-209">Nel campo Conto cliente selezionare un cliente UE.</span><span class="sxs-lookup"><span data-stu-id="817af-209">In the Customer account field, select an EU customer</span></span>
    * <span data-ttu-id="817af-210">Ad esempio, selezionare "Litware Retail DE-012".</span><span class="sxs-lookup"><span data-stu-id="817af-210">For example, select "DE-012 Litware Retail".</span></span>  
4. <span data-ttu-id="817af-211">Espandere la sezione Consegna.</span><span class="sxs-lookup"><span data-stu-id="817af-211">Expand the Delivery section.</span></span>
5. <span data-ttu-id="817af-212">Nel campo Modalità di consegna immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-212">In the Mode of delivery field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-213">Selezionare, ad esempio, "20 via aerea".</span><span class="sxs-lookup"><span data-stu-id="817af-213">For example, select '20 Air'.</span></span>  
6. <span data-ttu-id="817af-214">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-214">Click OK.</span></span>
7. <span data-ttu-id="817af-215">Posizionare il cursore nella prima riga di righe di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="817af-215">Place the cursor on the first row of sales order lines.</span></span>
8. <span data-ttu-id="817af-216">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-216">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-217">Selezionare, ad esempio, "D001".</span><span class="sxs-lookup"><span data-stu-id="817af-217">For example, select 'D001'.</span></span>  
9. <span data-ttu-id="817af-218">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="817af-218">Expand the Line details section.</span></span>
10. <span data-ttu-id="817af-219">Fare clic sulla scheda Commercio estero.</span><span class="sxs-lookup"><span data-stu-id="817af-219">Click the Foreign trade tab.</span></span>
    * <span data-ttu-id="817af-220">Il trasporto viene compilato automaticamente dalla Modalità di consegna scelta.</span><span class="sxs-lookup"><span data-stu-id="817af-220">The transport is filled automatically from the chosen Mode of delivery.</span></span>  
11. <span data-ttu-id="817af-221">Nel campo Porto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-221">In the Port field, enter or select a value.</span></span>
12. <span data-ttu-id="817af-222">Fare clic su Dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="817af-222">Click Financials.</span></span>
    * <span data-ttu-id="817af-223">In base alle impostazioni, questo importo verrà incluso nel valore di fattura Intrastat.</span><span class="sxs-lookup"><span data-stu-id="817af-223">As per the settings, this amount will be included in Intrastat invoice value.</span></span>  
13. <span data-ttu-id="817af-224">Fare clic su Gestisci spese.</span><span class="sxs-lookup"><span data-stu-id="817af-224">Click Maintain charges.</span></span>
14. <span data-ttu-id="817af-225">Nel campo Codice spese immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-225">In the Charges code field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-226">Selezionare, ad esempio, "SPESE DI TRASPORTO".</span><span class="sxs-lookup"><span data-stu-id="817af-226">For example, select 'FREIGHT'.</span></span>  
15. <span data-ttu-id="817af-227">Selezionare la casella di controllo Conserva.</span><span class="sxs-lookup"><span data-stu-id="817af-227">Select the Keep check box.</span></span>
16. <span data-ttu-id="817af-228">Nel campo Valore spese immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="817af-228">In the Charges value field, enter a number.</span></span>
    * <span data-ttu-id="817af-229">Ad esempio, immettere "10".</span><span class="sxs-lookup"><span data-stu-id="817af-229">For example, enter '10'.</span></span>  
17. <span data-ttu-id="817af-230">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817af-230">Click Save.</span></span>
18. <span data-ttu-id="817af-231">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="817af-231">Close the page.</span></span>
19. <span data-ttu-id="817af-232">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="817af-232">On the Action Pane, click Invoice.</span></span>
20. <span data-ttu-id="817af-233">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="817af-233">Click Invoice.</span></span>
21. <span data-ttu-id="817af-234">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="817af-234">Expand the Parameters section.</span></span>
22. <span data-ttu-id="817af-235">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="817af-235">In the Quantity field, select 'All'.</span></span>
23. <span data-ttu-id="817af-236">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="817af-236">Expand the Setup section.</span></span>
24. <span data-ttu-id="817af-237">Immettere una data nel campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="817af-237">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="817af-238">Ad esempio, immettere "31-01-2015".</span><span class="sxs-lookup"><span data-stu-id="817af-238">For example, enter '2015-01-31'.</span></span>  
25. <span data-ttu-id="817af-239">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-239">Click OK.</span></span>
26. <span data-ttu-id="817af-240">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-240">Click OK.</span></span>
27. <span data-ttu-id="817af-241">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="817af-241">Close the page.</span></span>
28. <span data-ttu-id="817af-242">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="817af-242">Click New.</span></span>
29. <span data-ttu-id="817af-243">Nel campo Conto cliente selezionare un cliente UE.</span><span class="sxs-lookup"><span data-stu-id="817af-243">In the Customer account field, select an EU customer.</span></span>
    * <span data-ttu-id="817af-244">Ad esempio, selezionare "DE-013 Trey Wholesales".</span><span class="sxs-lookup"><span data-stu-id="817af-244">For example, select 'DE-013 Trey Wholesales'</span></span>  
30. <span data-ttu-id="817af-245">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-245">Click OK.</span></span>
31. <span data-ttu-id="817af-246">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="817af-246">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="817af-247">Selezionare, ad esempio, "D0001".</span><span class="sxs-lookup"><span data-stu-id="817af-247">For example, select 'D0001'.</span></span>  
32. <span data-ttu-id="817af-248">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817af-248">Click Save.</span></span>
33. <span data-ttu-id="817af-249">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="817af-249">Click Invoice.</span></span>
34. <span data-ttu-id="817af-250">Immettere una data nel campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="817af-250">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="817af-251">Ad esempio, immettere la data "31-01-2015".</span><span class="sxs-lookup"><span data-stu-id="817af-251">For example, enter the date '2015-01-31'.</span></span>  
35. <span data-ttu-id="817af-252">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-252">Click OK.</span></span>
36. <span data-ttu-id="817af-253">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-253">Click OK.</span></span>

## <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="817af-254">Trasferire transazioni a Intrastat</span><span class="sxs-lookup"><span data-stu-id="817af-254">Transfer transactions to the Intrastat</span></span>
1. <span data-ttu-id="817af-255">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="817af-255">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
2. <span data-ttu-id="817af-256">Fare clic su Trasferisci.</span><span class="sxs-lookup"><span data-stu-id="817af-256">Click Transfer.</span></span>
3. <span data-ttu-id="817af-257">Selezionare Sì nel campo Fattura cliente.</span><span class="sxs-lookup"><span data-stu-id="817af-257">Select Yes in the Customer invoice field.</span></span>
4. <span data-ttu-id="817af-258">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="817af-258">Click Filter.</span></span>
5. <span data-ttu-id="817af-259">Nell'elenco contrassegnare la riga con Data.</span><span class="sxs-lookup"><span data-stu-id="817af-259">In the list, mark the row with Date</span></span>
6. <span data-ttu-id="817af-260">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="817af-260">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="817af-261">Ad esempio, immettere il filtro per il periodo gennaio 2015 (il valore esatto dipende dal formato della data): 1/1/2015..31/1/2015</span><span class="sxs-lookup"><span data-stu-id="817af-261">For example, enter the filter for the period January 2015 (the exact value depends on your date format): 1/1/2015..1/31/2015</span></span>  
7. <span data-ttu-id="817af-262">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-262">Click OK.</span></span>
8. <span data-ttu-id="817af-263">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="817af-263">Click OK.</span></span>
9. <span data-ttu-id="817af-264">Trovare e selezionare il record trasferito nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="817af-264">In the list, find and selected the transferred record.</span></span>
10. <span data-ttu-id="817af-265">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="817af-265">Click the General tab.</span></span>
    * <span data-ttu-id="817af-266">Esaminare i dati del trasferimento, inclusi paese di destinazione/spedizione, paese di origine, peso, quantità, quantità di unità supplementari, voce doganale, codice transazione, importi fattura e importi statistici.</span><span class="sxs-lookup"><span data-stu-id="817af-266">Review transferred data, including country\region of destination/dispatch, country of origin, weight, quantity, quantity in additional units, commodity, transaction code, invoice amounts and statistical amounts.</span></span>   <span data-ttu-id="817af-267">Se necessario, è possibile modificare i dati.</span><span class="sxs-lookup"><span data-stu-id="817af-267">You can modify data if necessary.</span></span>  


