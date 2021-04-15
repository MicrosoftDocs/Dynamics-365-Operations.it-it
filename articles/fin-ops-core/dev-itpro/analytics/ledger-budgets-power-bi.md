---
title: Contenuto Power BI Effettivi rispetto al budget
description: Questo argomento descrive il contenuto Power BI Effettivi rispetto al budget. Spiega come accedere ai report e fornisce informazioni sul modello di dati.
author: panolte
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9cc52f4cdab3084c9ac43078b0b0d534119ab514
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744241"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="dd3e6-104">Contenuto Power BI Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd3e6-105">Questo argomento descrive il contenuto **Effettivo rispetto al budget** di Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="dd3e6-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="dd3e6-106">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="dd3e6-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="dd3e6-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="dd3e6-107">Overview</span></span>

<span data-ttu-id="dd3e6-108">Il contenuto di Power BI **Effettivi rispetto al budget** è stato creato per i singoli responsabili per il monitoraggio delle prestazioni degli effettivi rispetto al budget nella loro organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd3e6-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="dd3e6-109">Il contenuto di Power BI **Effettivi rispetto al budget** fornisce visibilità negli scostamenti di budget.</span><span class="sxs-lookup"><span data-stu-id="dd3e6-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="dd3e6-110">È possibile analizzare il budget per l'anno corrente in base a categoria di conti, codice budget, conto principale, descrizioni del conto principale o periodo fiscale per ottenere una migliore comprensione della causa di tutti gli scostamenti.</span><span class="sxs-lookup"><span data-stu-id="dd3e6-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="dd3e6-111">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="dd3e6-111">Accessing the Power BI content</span></span>
<span data-ttu-id="dd3e6-112">I report dal contenuto di Power BI **Effettivi rispetto al budget** vengono visualizzati nelle aree di lavoro **Budget contabili e previsioni** e **Responsabile finanziario**.</span><span class="sxs-lookup"><span data-stu-id="dd3e6-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="dd3e6-113">Report inclusi nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="dd3e6-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="dd3e6-114">Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Effettivi rispetto al budget**.</span><span class="sxs-lookup"><span data-stu-id="dd3e6-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="dd3e6-115">Report</span><span class="sxs-lookup"><span data-stu-id="dd3e6-115">Report</span></span>                      | <span data-ttu-id="dd3e6-116">Metriche</span><span class="sxs-lookup"><span data-stu-id="dd3e6-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="dd3e6-117">Spese - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="dd3e6-118">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="dd3e6-118">Total expenses this year</span></span></li><li><span data-ttu-id="dd3e6-119">Spese totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="dd3e6-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="dd3e6-120">Ricavi - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="dd3e6-121">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="dd3e6-121">Total revenue this year</span></span></li><li><span data-ttu-id="dd3e6-122">Ricavi totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="dd3e6-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="dd3e6-123">Gestione spese</span><span class="sxs-lookup"><span data-stu-id="dd3e6-123">Expense</span></span>                     | <ul><li><span data-ttu-id="dd3e6-124">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="dd3e6-124">Total expenses this year</span></span></li><li><span data-ttu-id="dd3e6-125">Obiettivo per le spese in base al budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="dd3e6-126">Ricavi</span><span class="sxs-lookup"><span data-stu-id="dd3e6-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="dd3e6-127">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="dd3e6-127">Total revenue this year</span></span></li><li><span data-ttu-id="dd3e6-128">Obiettivo per ricavi in base al budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="dd3e6-129">Reddito netto</span><span class="sxs-lookup"><span data-stu-id="dd3e6-129">Net income</span></span>                  | <ul><li><span data-ttu-id="dd3e6-130">Reddito netto anno in corso</span><span class="sxs-lookup"><span data-stu-id="dd3e6-130">Net income this year</span></span></li><li><span data-ttu-id="dd3e6-131">Obiettivo per reddito netto in base al budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="dd3e6-132">Informazioni su modelli ed entità di dati</span><span class="sxs-lookup"><span data-stu-id="dd3e6-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="dd3e6-133">Entità</span><span class="sxs-lookup"><span data-stu-id="dd3e6-133">Entity</span></span>                    | <span data-ttu-id="dd3e6-134">Contenuto</span><span class="sxs-lookup"><span data-stu-id="dd3e6-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="dd3e6-135">Attività di contabilità generale</span><span class="sxs-lookup"><span data-stu-id="dd3e6-135">General Ledger Activities</span></span> | <span data-ttu-id="dd3e6-136">Importo transazione per contabilità generale</span><span class="sxs-lookup"><span data-stu-id="dd3e6-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="dd3e6-137">Attività di budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-137">Budget Activities</span></span>         | <span data-ttu-id="dd3e6-138">Importi di transazione per il registro di budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="dd3e6-139">Conti principali</span><span class="sxs-lookup"><span data-stu-id="dd3e6-139">Main Accounts</span></span>             | <span data-ttu-id="dd3e6-140">Conti principali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="dd3e6-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="dd3e6-141">Calendari fiscali</span><span class="sxs-lookup"><span data-stu-id="dd3e6-141">Fiscal Calendars</span></span>          | <span data-ttu-id="dd3e6-142">Calendari fiscali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="dd3e6-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="dd3e6-143">Contabilità generali</span><span class="sxs-lookup"><span data-stu-id="dd3e6-143">Ledgers</span></span>                   | <span data-ttu-id="dd3e6-144">Contabilità generale utilizzabile per filtrare il report nella contabilità generale corrente</span><span class="sxs-lookup"><span data-stu-id="dd3e6-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="dd3e6-145">Codici budget</span><span class="sxs-lookup"><span data-stu-id="dd3e6-145">Budget Codes</span></span>              | <span data-ttu-id="dd3e6-146">Codici budget per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="dd3e6-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="dd3e6-147">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="dd3e6-147">Legal Entities</span></span>            | <span data-ttu-id="dd3e6-148">Persone giuridiche utilizzabili per filtrare il report nella persona giuridica corrente</span><span class="sxs-lookup"><span data-stu-id="dd3e6-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]