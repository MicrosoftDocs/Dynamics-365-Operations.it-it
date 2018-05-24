---
title: Report finanziario conto economico
description: In questo articolo viene descritto il report predefinito per i conti economici. Sono descritti inoltre i blocchi predefiniti associati a questo report.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9310508082ff710cd040b74519044f5a90c23988
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="income-statement-financial-report"></a><span data-ttu-id="97775-104">Report finanziario conto economico</span><span class="sxs-lookup"><span data-stu-id="97775-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97775-105">In questo articolo viene descritto il report predefinito per i conti economici.</span><span class="sxs-lookup"><span data-stu-id="97775-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="97775-106">Sono descritti inoltre i blocchi predefiniti associati a questo report.</span><span class="sxs-lookup"><span data-stu-id="97775-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="97775-107">Report predefinito conto economico</span><span class="sxs-lookup"><span data-stu-id="97775-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="97775-108">Report predefinito</span><span class="sxs-lookup"><span data-stu-id="97775-108">Default report</span></span>             | <span data-ttu-id="97775-109">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="97775-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="97775-110">Conto economico - Predefinito</span><span class="sxs-lookup"><span data-stu-id="97775-110">Income Statement – Default</span></span> | <span data-ttu-id="97775-111">Fornisce una visualizzazione della redditività dell'organizzazione per il periodo corrente e da inizio anno.</span><span class="sxs-lookup"><span data-stu-id="97775-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="97775-112">Blocchi predefiniti</span><span class="sxs-lookup"><span data-stu-id="97775-112">Building blocks</span></span>
<span data-ttu-id="97775-113">Il report finanziario del conto economico utilizza i seguenti blocchi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="97775-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="97775-114">Report predefinito</span><span class="sxs-lookup"><span data-stu-id="97775-114">Default report</span></span>             | <span data-ttu-id="97775-115">Definizione riga</span><span class="sxs-lookup"><span data-stu-id="97775-115">Row definition</span></span>                     | <span data-ttu-id="97775-116">Definizione colonna</span><span class="sxs-lookup"><span data-stu-id="97775-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="97775-117">Conto economico - Predefinito</span><span class="sxs-lookup"><span data-stu-id="97775-117">Income Statement - Default</span></span> | <span data-ttu-id="97775-118">Conto economico riepilogativo - Predefinito</span><span class="sxs-lookup"><span data-stu-id="97775-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="97775-119">Periodico e da inizio anno - Predefinito</span><span class="sxs-lookup"><span data-stu-id="97775-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="97775-120">Definizione riga</span><span class="sxs-lookup"><span data-stu-id="97775-120">Row definition</span></span>

<span data-ttu-id="97775-121">La definizione di riga, Conto economico riepilogativo - Predefinito, contiene una sezione per ogni parte del conto economico tradizionale.</span><span class="sxs-lookup"><span data-stu-id="97775-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="97775-122">La dimensione Categoria di conti principali viene utilizzata per creare la definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="97775-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="97775-123">Di conseguenza, chiunque può generare il report senza dover apportare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="97775-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="97775-124">Definizione colonna</span><span class="sxs-lookup"><span data-stu-id="97775-124">Column Definition</span></span>

<span data-ttu-id="97775-125">Le definizioni di colonna contengono i diversi tipi di colonna per fornire diversi livelli di dettagli e dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="97775-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="97775-126">**Periodico e da inizio anno - Tipi predefiniti di colonna:**</span><span class="sxs-lookup"><span data-stu-id="97775-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="97775-127">**DESC** - Descrizione della definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="97775-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="97775-128">**FD** I dati finanziari per il periodo corrente</span><span class="sxs-lookup"><span data-stu-id="97775-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="97775-129">**FD** I dati finanziari da inizio anno</span><span class="sxs-lookup"><span data-stu-id="97775-129">**FD** – Financial data for the year to date</span></span>



<a name="additional-resources"></a><span data-ttu-id="97775-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="97775-130">Additional resources</span></span>
--------

[<span data-ttu-id="97775-131">Creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="97775-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="97775-132">Visualizzare i report finanziari</span><span class="sxs-lookup"><span data-stu-id="97775-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="97775-133">Blog sui report finanziari di Dynamics</span><span class="sxs-lookup"><span data-stu-id="97775-133">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




