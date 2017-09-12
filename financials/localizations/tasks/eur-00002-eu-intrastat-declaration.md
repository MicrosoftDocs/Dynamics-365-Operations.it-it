--- 
title: Generare una dichiarazione Intrastat UE
description: Questa procedura illustra i passaggi necessari per esportare la dichiarazione Intrastat in formato di file elettronico e per visualizzare l'anteprima dei dati della dichiarazione in formato Excel.
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f74da78232c477224c8fa753e9755b7f9d13174d
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="generate-an-eu-intrastat-declaration"></a><span data-ttu-id="7bf44-103">Generare una dichiarazione Intrastat UE</span><span class="sxs-lookup"><span data-stu-id="7bf44-103">Generate an EU Intrastat declaration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7bf44-104">Questa procedura illustra i passaggi necessari per esportare la dichiarazione Intrastat in formato di file elettronico e per visualizzare l'anteprima dei dati della dichiarazione in formato Excel.</span><span class="sxs-lookup"><span data-stu-id="7bf44-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="7bf44-105">Prima di poter completare questa procedura, è necessario trasferire le transazioni a Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7bf44-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="7bf44-106">Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.</span><span class="sxs-lookup"><span data-stu-id="7bf44-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="7bf44-107">Importare le configurazioni con le impostazioni</span><span class="sxs-lookup"><span data-stu-id="7bf44-107">Import configurations with settings</span></span>
1. <span data-ttu-id="7bf44-108">Andare a Aree di lavoro > Creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="7bf44-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="7bf44-109">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="7bf44-109">Click Set active.</span></span>
3. <span data-ttu-id="7bf44-110">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="7bf44-110">Click Repositories.</span></span>
4. <span data-ttu-id="7bf44-111">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="7bf44-111">Click Open.</span></span>
5. <span data-ttu-id="7bf44-112">Aprire il filtro della colonna Nome configurazione.</span><span class="sxs-lookup"><span data-stu-id="7bf44-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="7bf44-113">Applicare un filtro sul campo "Nome configurazione" in base a un valore "Intrastat (DE)" utilizzando l'operatore di filtro "inizia con".</span><span class="sxs-lookup"><span data-stu-id="7bf44-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="7bf44-114">È necessario selezionare il nome di configurazione applicabile al paese della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="7bf44-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="7bf44-115">Questa procedura utilizza la persona giuridica tedesca (DEMF) come esempio, quindi deve essere scelto "Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="7bf44-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="7bf44-116">Fare clic su Importa, quindi su Sì.</span><span class="sxs-lookup"><span data-stu-id="7bf44-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="7bf44-117">Aprire il filtro della colonna Nome configurazione.</span><span class="sxs-lookup"><span data-stu-id="7bf44-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="7bf44-118">Applicare un filtro sul campo "Nome configurazione" in base a un valore "report Intrastat" utilizzando l'operatore di filtro "inizia con".</span><span class="sxs-lookup"><span data-stu-id="7bf44-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="7bf44-119">Fare clic su Importa, quindi su Sì.</span><span class="sxs-lookup"><span data-stu-id="7bf44-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="7bf44-120">Impostare Parametri per il commercio estero</span><span class="sxs-lookup"><span data-stu-id="7bf44-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="7bf44-121">Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero</span><span class="sxs-lookup"><span data-stu-id="7bf44-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="7bf44-122">Espandere la sezione Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="7bf44-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="7bf44-123">Nel campo Mapping formato file immettere o selezionare un valore Intrastat (DE)</span><span class="sxs-lookup"><span data-stu-id="7bf44-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="7bf44-124">Nel campo Mapping formato report immettere o selezionare un valore Report Intrastat</span><span class="sxs-lookup"><span data-stu-id="7bf44-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="7bf44-125">Espandere la sezione Regole di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="7bf44-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="7bf44-126">È necessario impostare le regole di arrotondamento che sono applicabili nel paese per la dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7bf44-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="7bf44-127">Immettere un numero nel campo Regola di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="7bf44-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="7bf44-128">Inserire la precisione di arrotondamento, ad esempio, immettere "0,01".</span><span class="sxs-lookup"><span data-stu-id="7bf44-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="7bf44-129">Nel campo Numero di decimali per l'importo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="7bf44-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="7bf44-130">Ad esempio, immettere "2".</span><span class="sxs-lookup"><span data-stu-id="7bf44-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="7bf44-131">Nel campo Arrotondamento sotto 1 kg selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="7bf44-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="7bf44-132">Ad esempio, selezionare "Arrotondamento fino a 1 kg".</span><span class="sxs-lookup"><span data-stu-id="7bf44-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="7bf44-133">Immettere un numero nel campo Regola di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="7bf44-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="7bf44-134">Ad esempio, impostare "1" per l'arrotondamento del peso all'intero.</span><span class="sxs-lookup"><span data-stu-id="7bf44-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="7bf44-135">Espandere la sezione Limite minimo.</span><span class="sxs-lookup"><span data-stu-id="7bf44-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="7bf44-136">Immettere un numero nel campo Peso.</span><span class="sxs-lookup"><span data-stu-id="7bf44-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="7bf44-137">Ad esempio, impostare "10" come peso minimo.</span><span class="sxs-lookup"><span data-stu-id="7bf44-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="7bf44-138">Nel campo Importo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="7bf44-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="7bf44-139">Ad esempio, impostare "200" come quantità minima.</span><span class="sxs-lookup"><span data-stu-id="7bf44-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="7bf44-140">Nel campo Voce doganale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7bf44-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="7bf44-141">Impostare Compressione di Intrastat</span><span class="sxs-lookup"><span data-stu-id="7bf44-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="7bf44-142">Passare a Imposta > Impostazioni > Commercio estero > Compressione di Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7bf44-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="7bf44-143">Fare clic su Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="7bf44-143">Click Remove.</span></span>
3. <span data-ttu-id="7bf44-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7bf44-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7bf44-145">Ad esempio, selezionare Voce doganale nella sezione Disponibile.</span><span class="sxs-lookup"><span data-stu-id="7bf44-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="7bf44-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7bf44-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="7bf44-147">Generare la dichiarazione Intrastat</span><span class="sxs-lookup"><span data-stu-id="7bf44-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="7bf44-148">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7bf44-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="7bf44-149">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="7bf44-149">Click Validate.</span></span>
    * <span data-ttu-id="7bf44-150">La convalida viene effettuata in base al campo Verifica impostazione nella pagina Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="7bf44-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="7bf44-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7bf44-151">Click OK.</span></span>
4. <span data-ttu-id="7bf44-152">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="7bf44-152">Click Update.</span></span>
5. <span data-ttu-id="7bf44-153">Fare clic su Limite minimo.</span><span class="sxs-lookup"><span data-stu-id="7bf44-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="7bf44-154">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="7bf44-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="7bf44-155">Ad esempio, immettere 1 gennaio 2015.</span><span class="sxs-lookup"><span data-stu-id="7bf44-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="7bf44-156">Selezionare Sì nel campo Comprimi.</span><span class="sxs-lookup"><span data-stu-id="7bf44-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="7bf44-157">Immettere una data nel campo Data di fine.</span><span class="sxs-lookup"><span data-stu-id="7bf44-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="7bf44-158">Ad esempio, immettere 31 gennaio 2015.</span><span class="sxs-lookup"><span data-stu-id="7bf44-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="7bf44-159">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7bf44-159">Click OK.</span></span>
10. <span data-ttu-id="7bf44-160">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="7bf44-160">Click Update.</span></span>
11. <span data-ttu-id="7bf44-161">Fare clic su Comprimi.</span><span class="sxs-lookup"><span data-stu-id="7bf44-161">Click Compress.</span></span>
    * <span data-ttu-id="7bf44-162">La compressione si verifica in base a come si configurano le impostazioni di compressione di intrastate.</span><span class="sxs-lookup"><span data-stu-id="7bf44-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="7bf44-163">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="7bf44-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="7bf44-164">Ad esempio, immettere 1 gennaio 2015.</span><span class="sxs-lookup"><span data-stu-id="7bf44-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="7bf44-165">Immettere una data nel campo Data di fine.</span><span class="sxs-lookup"><span data-stu-id="7bf44-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="7bf44-166">Ad esempio, immettere 31 gennaio 2015.</span><span class="sxs-lookup"><span data-stu-id="7bf44-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="7bf44-167">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7bf44-167">Click OK.</span></span>
15. <span data-ttu-id="7bf44-168">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="7bf44-168">Click Update.</span></span>
16. <span data-ttu-id="7bf44-169">Fare clic su Rigenera numeri progressivi.</span><span class="sxs-lookup"><span data-stu-id="7bf44-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="7bf44-170">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7bf44-170">Click OK.</span></span>
18. <span data-ttu-id="7bf44-171">Fare clic su Output.</span><span class="sxs-lookup"><span data-stu-id="7bf44-171">Click Output.</span></span>
19. <span data-ttu-id="7bf44-172">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="7bf44-172">Click Report.</span></span>
20. <span data-ttu-id="7bf44-173">Nel campo Dal immettere la prima data del periodo di reporting.</span><span class="sxs-lookup"><span data-stu-id="7bf44-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="7bf44-174">Ad esempio, impostare la data su 1 gennaio 2015.</span><span class="sxs-lookup"><span data-stu-id="7bf44-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="7bf44-175">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="7bf44-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="7bf44-176">Ad esempio, immettere 31 gennaio 2015.</span><span class="sxs-lookup"><span data-stu-id="7bf44-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="7bf44-177">Selezionare Sì nel campo Genera file.</span><span class="sxs-lookup"><span data-stu-id="7bf44-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="7bf44-178">Digitare un valore nel campo Nome file.</span><span class="sxs-lookup"><span data-stu-id="7bf44-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="7bf44-179">Selezionare Sì nel campo Genera report.</span><span class="sxs-lookup"><span data-stu-id="7bf44-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="7bf44-180">Digitare un valore nel campo Nome file report.</span><span class="sxs-lookup"><span data-stu-id="7bf44-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="7bf44-181">Selezionare un'opzione nel campo Direzione.</span><span class="sxs-lookup"><span data-stu-id="7bf44-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="7bf44-182">Ad esempio, selezionare "Spedizioni".</span><span class="sxs-lookup"><span data-stu-id="7bf44-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="7bf44-183">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7bf44-183">Click OK.</span></span>

