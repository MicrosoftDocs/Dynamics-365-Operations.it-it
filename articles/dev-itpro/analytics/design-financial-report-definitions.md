---
title: Definizioni di report in Progettazione report finanziari
description: "In questo articolo vengono fornite informazioni sulle definizioni di report. Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report. Una definizione di report prevede inoltre opzioni e impostazioni che per la personalizzazione di un report."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 27f918e873317b07853c39ca97195f297c33955c
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="a3979-105">Definizioni di report in Progettazione report finanziari</span><span class="sxs-lookup"><span data-stu-id="a3979-105">Report definitions in financial report designer</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="a3979-106">In questo articolo vengono fornite informazioni sulle definizioni di report.</span><span class="sxs-lookup"><span data-stu-id="a3979-106">This article provides information about report definitions.</span></span> <span data-ttu-id="a3979-107">Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report.</span><span class="sxs-lookup"><span data-stu-id="a3979-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="a3979-108">Una definizione di report prevede inoltre opzioni e impostazioni che per la personalizzazione di un report.</span><span class="sxs-lookup"><span data-stu-id="a3979-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="a3979-109">Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report.</span><span class="sxs-lookup"><span data-stu-id="a3979-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="a3979-110">Nella definizione di report sono inoltre disponibili varie opzioni e impostazioni per la personalizzazione di un report.</span><span class="sxs-lookup"><span data-stu-id="a3979-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="a3979-111">Dopo aver definito le definizioni di riga e le definizioni di colonna, è necessario combinarle in una definizione di report.</span><span class="sxs-lookup"><span data-stu-id="a3979-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="a3979-112">In questa fase, vengono anche definiti altri aspetti delle definizioni, ad esempio la data del report e il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a3979-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="a3979-113">È quindi possibile salvare e generare un report.</span><span class="sxs-lookup"><span data-stu-id="a3979-113">You can then save and generate a report.</span></span> <span data-ttu-id="a3979-114">I report finanziari offrono i seguenti livelli di dettaglio:</span><span class="sxs-lookup"><span data-stu-id="a3979-114">Financial reporting offers the following levels of detail:</span></span>

-   <span data-ttu-id="a3979-115">Finanziario</span><span class="sxs-lookup"><span data-stu-id="a3979-115">Financial</span></span>
-   <span data-ttu-id="a3979-116">Finanziario e contabile</span><span class="sxs-lookup"><span data-stu-id="a3979-116">Financial and Account</span></span>
-   <span data-ttu-id="a3979-117">Finanziario, contabile e di transazione</span><span class="sxs-lookup"><span data-stu-id="a3979-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="a3979-118">Tuttavia, a seconda di come i dati vengono archiviati nel sistema Microsoft Dynamics ERP, i dettagli sulle transazioni potrebbero non essere disponibili nei report.</span><span class="sxs-lookup"><span data-stu-id="a3979-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="a3979-119">Creare una definizione del report</span><span class="sxs-lookup"><span data-stu-id="a3979-119">Create a report definition</span></span>
1.  <span data-ttu-id="a3979-120">In Progettazione report, nel menu **File** fare clic su **Nuovo**, quindi selezionare **Definizione di report**.</span><span class="sxs-lookup"><span data-stu-id="a3979-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2.  <span data-ttu-id="a3979-121">Specificare le informazioni appropriate nelle schede **Report**, **Output e distribuzione**, **Intestazioni e piè di pagina** e **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="a3979-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="a3979-122">Contenuto di una definizione di report</span><span class="sxs-lookup"><span data-stu-id="a3979-122">Contents of a report definition</span></span>
<span data-ttu-id="a3979-123">Nella seguente tabella sono descritte le schede in una definizione di report e come le informazioni vengono utilizzate.</span><span class="sxs-lookup"><span data-stu-id="a3979-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3979-124">Scheda</span><span class="sxs-lookup"><span data-stu-id="a3979-124">Tab</span></span></th>
<th><span data-ttu-id="a3979-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3979-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a3979-126">Report</span><span class="sxs-lookup"><span data-stu-id="a3979-126">Report</span></span></td>
<td><span data-ttu-id="a3979-127">Creare un report, configurare un report o modificare un report esistente.</span><span class="sxs-lookup"><span data-stu-id="a3979-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a3979-128">Output e distribuzione</span><span class="sxs-lookup"><span data-stu-id="a3979-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="a3979-129">Modificare il tipo e la destinazione di output del report.</span><span class="sxs-lookup"><span data-stu-id="a3979-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a3979-130">Intestazioni e piè di pagina</span><span class="sxs-lookup"><span data-stu-id="a3979-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="a3979-131">Definire e formattare le intestazioni e i piè di pagina del report.</span><span class="sxs-lookup"><span data-stu-id="a3979-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="a3979-132">Ad esempio, è possibile aggiungere testo o immagini nell'intestazione o nel piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="a3979-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="a3979-133">I report finanziari supportano file con estensione bmp, jpg e png per le immagini.</span><span class="sxs-lookup"><span data-stu-id="a3979-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="a3979-134">È inoltre possibile aggiungere i codici di testo automatico per inserire altre informazioni, ad esempio un nome di società, il nome del report o un numero di pagina.</span><span class="sxs-lookup"><span data-stu-id="a3979-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a3979-135">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="a3979-135">Settings</span></span></td>
<td><span data-ttu-id="a3979-136">Specificare le impostazioni di definizione di report, ad esempio le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="a3979-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="a3979-137">Formattazione e arrotondamento di importi</span><span class="sxs-lookup"><span data-stu-id="a3979-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="a3979-138">Formattare report dettagli</span><span class="sxs-lookup"><span data-stu-id="a3979-138">Format detail reports</span></span></li>
<li><span data-ttu-id="a3979-139">Formattare alberi gerarchici</span><span class="sxs-lookup"><span data-stu-id="a3979-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="a3979-140">Generare un report eccezioni</span><span class="sxs-lookup"><span data-stu-id="a3979-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="a3979-141">Specificare la conversione valuta</span><span class="sxs-lookup"><span data-stu-id="a3979-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="a3979-142">Eseguire subtotali e filtrare dettagli dei conti</span><span class="sxs-lookup"><span data-stu-id="a3979-142">Subtotal and filter account details</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="a3979-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3979-143">See also</span></span>
--------

[<span data-ttu-id="a3979-144">Creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="a3979-144">Financial reporting</span></span>](financial-reporting-intro.md)




