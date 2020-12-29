---
title: Contenuto Power BI Effettivi rispetto al budget
description: Questo argomento descrive il contenuto Power BI Effettivi rispetto al budget. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6a185da5055741ac30c7e237ef72d07084644651
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685275"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="958a2-104">Contenuto Power BI Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="958a2-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="958a2-105">Questo argomento descrive il contenuto Power BI **Effettivi rispetto al budget**.</span><span class="sxs-lookup"><span data-stu-id="958a2-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="958a2-106">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="958a2-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="958a2-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="958a2-107">Overview</span></span>

<span data-ttu-id="958a2-108">Il contenuto di Power BI **Effettivi rispetto al budget** è stato creato per i singoli responsabili per il monitoraggio delle prestazioni degli effettivi rispetto al budget nella loro organizzazione.</span><span class="sxs-lookup"><span data-stu-id="958a2-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="958a2-109">Il contenuto di Power BI **Effettivi rispetto al budget** fornisce visibilità negli scostamenti di budget.</span><span class="sxs-lookup"><span data-stu-id="958a2-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="958a2-110">È possibile analizzare il budget per l'anno corrente in base a categoria di conti, codice budget, conto principale, descrizioni del conto principale o periodo fiscale per ottenere una migliore comprensione della causa di tutti gli scostamenti.</span><span class="sxs-lookup"><span data-stu-id="958a2-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="958a2-111">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="958a2-111">Accessing the Power BI content</span></span>
<span data-ttu-id="958a2-112">I report dal contenuto di Power BI **Effettivi rispetto al budget** vengono visualizzati nelle aree di lavoro **Budget contabili e previsioni** e **Responsabile finanziario**.</span><span class="sxs-lookup"><span data-stu-id="958a2-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="958a2-113">Report inclusi nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="958a2-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="958a2-114">Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Effettivi rispetto al budget**.</span><span class="sxs-lookup"><span data-stu-id="958a2-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="958a2-115">Report</span><span class="sxs-lookup"><span data-stu-id="958a2-115">Report</span></span>                      | <span data-ttu-id="958a2-116">Metriche</span><span class="sxs-lookup"><span data-stu-id="958a2-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="958a2-117">Spese - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="958a2-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="958a2-118">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="958a2-118">Total expenses this year</span></span></li><li><span data-ttu-id="958a2-119">Spese totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="958a2-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="958a2-120">Ricavi - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="958a2-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="958a2-121">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="958a2-121">Total revenue this year</span></span></li><li><span data-ttu-id="958a2-122">Ricavi totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="958a2-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="958a2-123">Gestione spese</span><span class="sxs-lookup"><span data-stu-id="958a2-123">Expense</span></span>                     | <ul><li><span data-ttu-id="958a2-124">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="958a2-124">Total expenses this year</span></span></li><li><span data-ttu-id="958a2-125">Obiettivo per le spese in base al budget</span><span class="sxs-lookup"><span data-stu-id="958a2-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="958a2-126">Ricavi</span><span class="sxs-lookup"><span data-stu-id="958a2-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="958a2-127">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="958a2-127">Total revenue this year</span></span></li><li><span data-ttu-id="958a2-128">Obiettivo per ricavi in base al budget</span><span class="sxs-lookup"><span data-stu-id="958a2-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="958a2-129">Reddito netto</span><span class="sxs-lookup"><span data-stu-id="958a2-129">Net income</span></span>                  | <ul><li><span data-ttu-id="958a2-130">Reddito netto anno in corso</span><span class="sxs-lookup"><span data-stu-id="958a2-130">Net income this year</span></span></li><li><span data-ttu-id="958a2-131">Obiettivo per reddito netto in base al budget</span><span class="sxs-lookup"><span data-stu-id="958a2-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="958a2-132">Informazioni su modelli ed entità di dati</span><span class="sxs-lookup"><span data-stu-id="958a2-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="958a2-133">Entità</span><span class="sxs-lookup"><span data-stu-id="958a2-133">Entity</span></span>                    | <span data-ttu-id="958a2-134">Contenuto</span><span class="sxs-lookup"><span data-stu-id="958a2-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="958a2-135">Attività di contabilità generale</span><span class="sxs-lookup"><span data-stu-id="958a2-135">General Ledger Activities</span></span> | <span data-ttu-id="958a2-136">Importo transazione per contabilità generale</span><span class="sxs-lookup"><span data-stu-id="958a2-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="958a2-137">Attività di budget</span><span class="sxs-lookup"><span data-stu-id="958a2-137">Budget Activities</span></span>         | <span data-ttu-id="958a2-138">Importi di transazione per il registro di budget</span><span class="sxs-lookup"><span data-stu-id="958a2-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="958a2-139">Conti principali</span><span class="sxs-lookup"><span data-stu-id="958a2-139">Main Accounts</span></span>             | <span data-ttu-id="958a2-140">Conti principali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="958a2-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="958a2-141">Calendari fiscali</span><span class="sxs-lookup"><span data-stu-id="958a2-141">Fiscal Calendars</span></span>          | <span data-ttu-id="958a2-142">Calendari fiscali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="958a2-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="958a2-143">Contabilità generali</span><span class="sxs-lookup"><span data-stu-id="958a2-143">Ledgers</span></span>                   | <span data-ttu-id="958a2-144">Contabilità generale utilizzabile per filtrare il report nella contabilità generale corrente</span><span class="sxs-lookup"><span data-stu-id="958a2-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="958a2-145">Codici budget</span><span class="sxs-lookup"><span data-stu-id="958a2-145">Budget Codes</span></span>              | <span data-ttu-id="958a2-146">Codici budget per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="958a2-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="958a2-147">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="958a2-147">Legal Entities</span></span>            | <span data-ttu-id="958a2-148">Persone giuridiche utilizzabili per filtrare il report nella persona giuridica corrente</span><span class="sxs-lookup"><span data-stu-id="958a2-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |
