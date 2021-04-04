---
title: Definizioni di report in Progettazione report finanziari
description: In questo articolo vengono fornite informazioni sulle definizioni di report.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 073df430892e01d4842b2af147b0ae2765b1c66a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570344"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="edaea-103">Definizioni di report in Progettazione report finanziari</span><span class="sxs-lookup"><span data-stu-id="edaea-103">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="edaea-104">In questo articolo vengono fornite informazioni sulle definizioni di report.</span><span class="sxs-lookup"><span data-stu-id="edaea-104">This article provides information about report definitions.</span></span> <span data-ttu-id="edaea-105">Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report.</span><span class="sxs-lookup"><span data-stu-id="edaea-105">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="edaea-106">Una definizione di report prevede inoltre opzioni e impostazioni che per la personalizzazione di un report.</span><span class="sxs-lookup"><span data-stu-id="edaea-106">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="edaea-107">Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report.</span><span class="sxs-lookup"><span data-stu-id="edaea-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="edaea-108">Nella definizione di report sono inoltre disponibili varie opzioni e impostazioni per la personalizzazione di un report.</span><span class="sxs-lookup"><span data-stu-id="edaea-108">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="edaea-109">Dopo aver definito le definizioni di riga e le definizioni di colonna, è necessario combinarle in una definizione di report.</span><span class="sxs-lookup"><span data-stu-id="edaea-109">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="edaea-110">In questa fase, vengono anche definiti altri aspetti delle definizioni, ad esempio la data del report e il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="edaea-110">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="edaea-111">È quindi possibile salvare e generare un report.</span><span class="sxs-lookup"><span data-stu-id="edaea-111">You can then save and generate a report.</span></span> <span data-ttu-id="edaea-112">I report finanziari offrono i seguenti livelli di dettaglio:</span><span class="sxs-lookup"><span data-stu-id="edaea-112">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="edaea-113">Finanziario</span><span class="sxs-lookup"><span data-stu-id="edaea-113">Financial</span></span>
- <span data-ttu-id="edaea-114">Finanziario e contabile</span><span class="sxs-lookup"><span data-stu-id="edaea-114">Financial and Account</span></span>
- <span data-ttu-id="edaea-115">Finanziario, contabile e di transazione</span><span class="sxs-lookup"><span data-stu-id="edaea-115">Financial, Account, and Transaction</span></span>

<span data-ttu-id="edaea-116">A seconda della modalità di archiviazione dei dati nel sistema Microsoft Dynamics ERP, i dettagli delle transazioni potrebbero tuttavia non essere disponibili nei report.</span><span class="sxs-lookup"><span data-stu-id="edaea-116">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="edaea-117">Creare una definizione del report</span><span class="sxs-lookup"><span data-stu-id="edaea-117">Create a report definition</span></span>
1. <span data-ttu-id="edaea-118">In Progettazione report, nel menu **File** fare clic su **Nuovo**, quindi selezionare **Definizione di report**.</span><span class="sxs-lookup"><span data-stu-id="edaea-118">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="edaea-119">Specificare le informazioni appropriate nelle schede **Report**, **Output e distribuzione**, **Intestazioni e piè di pagina** e **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="edaea-119">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="edaea-120">Contenuto di una definizione di report</span><span class="sxs-lookup"><span data-stu-id="edaea-120">Contents of a report definition</span></span>
<span data-ttu-id="edaea-121">Nella seguente tabella sono descritte le schede in una definizione di report e come le informazioni vengono utilizzate.</span><span class="sxs-lookup"><span data-stu-id="edaea-121">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="edaea-122">Scheda</span><span class="sxs-lookup"><span data-stu-id="edaea-122">Tab</span></span></th>
<th><span data-ttu-id="edaea-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edaea-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="edaea-124">Report</span><span class="sxs-lookup"><span data-stu-id="edaea-124">Report</span></span></td>
<td><span data-ttu-id="edaea-125">Creare un report, configurare un report o modificare un report esistente.</span><span class="sxs-lookup"><span data-stu-id="edaea-125">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="edaea-126">Output e distribuzione</span><span class="sxs-lookup"><span data-stu-id="edaea-126">Output and Distribution</span></span></td>
<td><span data-ttu-id="edaea-127">Modificare il tipo e la destinazione di output del report.</span><span class="sxs-lookup"><span data-stu-id="edaea-127">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="edaea-128">Intestazioni e piè di pagina</span><span class="sxs-lookup"><span data-stu-id="edaea-128">Headers and Footers</span></span></td>
<td><span data-ttu-id="edaea-129">Definire e formattare le intestazioni e i piè di pagina del report.</span><span class="sxs-lookup"><span data-stu-id="edaea-129">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="edaea-130">Ad esempio, è possibile aggiungere testo o immagini nell'intestazione o nel piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="edaea-130">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="edaea-131">I report finanziari supportano file con estensione bmp, jpg e png per le immagini.</span><span class="sxs-lookup"><span data-stu-id="edaea-131">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="edaea-132">È inoltre possibile aggiungere i codici di testo automatico per inserire altre informazioni, ad esempio un nome di società, il nome del report o un numero di pagina.</span><span class="sxs-lookup"><span data-stu-id="edaea-132">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="edaea-133">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="edaea-133">Settings</span></span></td>
<td><span data-ttu-id="edaea-134">Specificare le impostazioni di definizione di report, ad esempio le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="edaea-134">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="edaea-135">Formattazione e arrotondamento di importi</span><span class="sxs-lookup"><span data-stu-id="edaea-135">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="edaea-136">Formattare report dettagli</span><span class="sxs-lookup"><span data-stu-id="edaea-136">Format detail reports</span></span></li>
<li><span data-ttu-id="edaea-137">Formattare alberi gerarchici</span><span class="sxs-lookup"><span data-stu-id="edaea-137">Format reporting trees</span></span></li>
<li><span data-ttu-id="edaea-138">Generare un report eccezioni</span><span class="sxs-lookup"><span data-stu-id="edaea-138">Generate an exception report</span></span></li>
<li><span data-ttu-id="edaea-139">Specificare la conversione valuta</span><span class="sxs-lookup"><span data-stu-id="edaea-139">Specify currency conversion</span></span></li>
<li><span data-ttu-id="edaea-140">Eseguire subtotali e filtrare dettagli dei conti</span><span class="sxs-lookup"><span data-stu-id="edaea-140">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="edaea-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="edaea-141">Additional resources</span></span>

[<span data-ttu-id="edaea-142">Creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="edaea-142">Financial reporting</span></span>](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]