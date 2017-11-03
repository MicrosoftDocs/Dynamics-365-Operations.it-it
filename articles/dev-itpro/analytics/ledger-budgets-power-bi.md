---
title: Contenuto Power BI Effettivi rispetto al budget
description: "Questo argomento descrive il contenuto Power BI Effettivi rispetto al budget. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f09af96fb1c76d8737d2c535f1a46565a18deca0
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="4f20e-104">Contenuto Power BI Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-104">Actual vs budget Power BI content</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4f20e-105">Questo argomento descrive il contenuto Microsoft Power BI **Effettivi rispetto al budget**.</span><span class="sxs-lookup"><span data-stu-id="4f20e-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="4f20e-106">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4f20e-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span> 

# <a name="overview"></a><span data-ttu-id="4f20e-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="4f20e-107">Overview</span></span>

<span data-ttu-id="4f20e-108">Il contenuto di Power BI **Effettivi rispetto al budget** è stato creato per i singoli responsabili per il monitoraggio delle prestazioni degli effettivi rispetto al budget nella loro organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f20e-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="4f20e-109">Il contenuto di Power BI **Effettivi rispetto al budget** fornisce visibilità negli scostamenti di budget.</span><span class="sxs-lookup"><span data-stu-id="4f20e-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="4f20e-110">È possibile analizzare il budget per l'anno corrente in base a categoria di conti, codice budget, conto principale, descrizioni del conto principale o periodo fiscale per ottenere una migliore comprensione della causa di tutti gli scostamenti.</span><span class="sxs-lookup"><span data-stu-id="4f20e-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span> 

# <a name="accessing-the-power-bi-content"></a><span data-ttu-id="4f20e-111">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="4f20e-111">Accessing the Power BI content</span></span>
<span data-ttu-id="4f20e-112">Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017), i report del contenuto di Power BI **Effettivi rispetto al budget** vengono visualizzati nelle aree di lavoro **Budget contabili e previsioni** e **CFO**.</span><span class="sxs-lookup"><span data-stu-id="4f20e-112">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

# <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="4f20e-113">Report inclusi nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="4f20e-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="4f20e-114">Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Effettivi rispetto al budget**.</span><span class="sxs-lookup"><span data-stu-id="4f20e-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="4f20e-115">Report</span><span class="sxs-lookup"><span data-stu-id="4f20e-115">Report</span></span>                      | <span data-ttu-id="4f20e-116">Metriche</span><span class="sxs-lookup"><span data-stu-id="4f20e-116">Metrics</span></span> |
|-----------------------------|---------|
| <span data-ttu-id="4f20e-117">Spese - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="4f20e-118">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="4f20e-118">Total expenses this year</span></span></li><li><span data-ttu-id="4f20e-119">Spese totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="4f20e-119">Budget total expenses this year</span></span></li></ul> |
| <span data-ttu-id="4f20e-120">Ricavi - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="4f20e-121">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="4f20e-121">Total revenue this year</span></span></li><li><span data-ttu-id="4f20e-122">Ricavi totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="4f20e-122">Budget total revenue this year</span></span></li><ul> |
| <span data-ttu-id="4f20e-123">Gestione spese</span><span class="sxs-lookup"><span data-stu-id="4f20e-123">Expense</span></span>                     | <ul><li><span data-ttu-id="4f20e-124">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="4f20e-124">Total expenses this year</span></span></li><li><span data-ttu-id="4f20e-125">Obiettivo per le spese in base al budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-125">Goal for expenses based on budget</span></span> </li><ul> |
| <span data-ttu-id="4f20e-126">Ricavi</span><span class="sxs-lookup"><span data-stu-id="4f20e-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="4f20e-127">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="4f20e-127">Total revenue this year</span></span></li><li><span data-ttu-id="4f20e-128">Obiettivo per ricavi in base al budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-128">Goal for revenue based on budget</span></span> </li><ul> |
| <span data-ttu-id="4f20e-129">Reddito netto</span><span class="sxs-lookup"><span data-stu-id="4f20e-129">Net income</span></span>                  | <ul><li><span data-ttu-id="4f20e-130">Reddito netto anno in corso</span><span class="sxs-lookup"><span data-stu-id="4f20e-130">Net income this year</span></span></li><li><span data-ttu-id="4f20e-131">Obiettivo per reddito netto in base al budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-131">Goal for net income based on budget</span></span> </li><ul> |

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="4f20e-132">Estensione del contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="4f20e-132">Extending the Power BI content</span></span>
<span data-ttu-id="4f20e-133">Utilizzando i pacchetti di contenuti disponibili in Microsoft Dynamics Lifecycle Services (LCS), è possibile fornire eccezionali analisi alle persone che non accedono a Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4f20e-133">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="4f20e-134">È possibile modificare i pacchetti di contenuti affinché siano inclusi altri report o rappresentazioni e quindi pubblicate i pacchetti contenuti nel tenant Power BI.com per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="4f20e-134">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="4f20e-135">Puoi trovare il contenuto di Power BI **Effettivi rispetto al budget** della raccolta delle risorse condivise in LCS.</span><span class="sxs-lookup"><span data-stu-id="4f20e-135">You can find the **Actual vs budget** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="4f20e-136">Per ulteriori informazioni su come scaricare il contenuto e implementarlo nell'organizzazione, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="4f20e-136">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="4f20e-137">Per guardare una demo che mostra come implementare il contenuto di Power BI, vedere [Contenuto di Power BI da Microsoft e partner in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).</span><span class="sxs-lookup"><span data-stu-id="4f20e-137">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

# <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="4f20e-138">Informazioni su modelli ed entità di dati</span><span class="sxs-lookup"><span data-stu-id="4f20e-138">Understanding the data model and entities</span></span>

| <span data-ttu-id="4f20e-139">Entità</span><span class="sxs-lookup"><span data-stu-id="4f20e-139">Entity</span></span>                    | <span data-ttu-id="4f20e-140">Contenuto</span><span class="sxs-lookup"><span data-stu-id="4f20e-140">Contents</span></span> |
|---------------------------|----------|
| <span data-ttu-id="4f20e-141">Attività di contabilità generale</span><span class="sxs-lookup"><span data-stu-id="4f20e-141">General Ledger Activities</span></span> | <span data-ttu-id="4f20e-142">Importo transazione per contabilità generale</span><span class="sxs-lookup"><span data-stu-id="4f20e-142">Transaction amounts for the general ledger</span></span> |
| <span data-ttu-id="4f20e-143">Attività di budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-143">Budget Activities</span></span>         | <span data-ttu-id="4f20e-144">Importi di transazione per il registro di budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-144">Transaction amounts for the budget register</span></span> |
| <span data-ttu-id="4f20e-145">Conti principali</span><span class="sxs-lookup"><span data-stu-id="4f20e-145">Main Accounts</span></span>             | <span data-ttu-id="4f20e-146">Conti principali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="4f20e-146">Main accounts to filter reports by</span></span> |
| <span data-ttu-id="4f20e-147">Calendari fiscali</span><span class="sxs-lookup"><span data-stu-id="4f20e-147">Fiscal Calendars</span></span>          | <span data-ttu-id="4f20e-148">Calendari fiscali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="4f20e-148">Fiscal calendars to filter reports by</span></span> |
| <span data-ttu-id="4f20e-149">Contabilità generali</span><span class="sxs-lookup"><span data-stu-id="4f20e-149">Ledgers</span></span>                   | <span data-ttu-id="4f20e-150">Contabilità generale utilizzabile per filtrare il report nella contabilità generale corrente</span><span class="sxs-lookup"><span data-stu-id="4f20e-150">Ledgers that can be used to filter the report to the current ledger</span></span> |
| <span data-ttu-id="4f20e-151">Codici budget</span><span class="sxs-lookup"><span data-stu-id="4f20e-151">Budget Codes</span></span>              | <span data-ttu-id="4f20e-152">Codici budget per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="4f20e-152">Budget codes to filter reports by</span></span> |
| <span data-ttu-id="4f20e-153">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="4f20e-153">Legal Entities</span></span>            | <span data-ttu-id="4f20e-154">Persone giuridiche utilizzabili per filtrare il report nella persona giuridica corrente</span><span class="sxs-lookup"><span data-stu-id="4f20e-154">Legal entities that can be used to filter the report to the current legal entity</span></span> |

