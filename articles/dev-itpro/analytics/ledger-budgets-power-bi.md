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
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c801544e9e37a528203f5a1730aa8cb526d63dbf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "343491"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="b94b1-104">Contenuto Power BI Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b94b1-105">Questo argomento descrive il contenuto Power BI **Effettivi rispetto al budget**.</span><span class="sxs-lookup"><span data-stu-id="b94b1-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="b94b1-106">Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b94b1-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="b94b1-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b94b1-107">Overview</span></span>

<span data-ttu-id="b94b1-108">Il contenuto di Power BI **Effettivi rispetto al budget** è stato creato per i singoli responsabili per il monitoraggio delle prestazioni degli effettivi rispetto al budget nella loro organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b94b1-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="b94b1-109">Il contenuto di Power BI **Effettivi rispetto al budget** fornisce visibilità negli scostamenti di budget.</span><span class="sxs-lookup"><span data-stu-id="b94b1-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="b94b1-110">È possibile analizzare il budget per l'anno corrente in base a categoria di conti, codice budget, conto principale, descrizioni del conto principale o periodo fiscale per ottenere una migliore comprensione della causa di tutti gli scostamenti.</span><span class="sxs-lookup"><span data-stu-id="b94b1-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="b94b1-111">Accesso al contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="b94b1-111">Accessing the Power BI content</span></span>
<span data-ttu-id="b94b1-112">I report dal contenuto di Power BI **Effettivi rispetto al budget** vengono visualizzati nelle aree di lavoro **Budget contabili e previsioni** e **Responsabile finanziario**.</span><span class="sxs-lookup"><span data-stu-id="b94b1-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="b94b1-113">Report inclusi nel contenuto Power BI</span><span class="sxs-lookup"><span data-stu-id="b94b1-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="b94b1-114">Nella seguente tabella sono descritti i dettagli sulle metriche disponibili in ogni pagina del report nel contenuto di Power BI **Effettivi rispetto al budget**.</span><span class="sxs-lookup"><span data-stu-id="b94b1-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="b94b1-115">Report</span><span class="sxs-lookup"><span data-stu-id="b94b1-115">Report</span></span>                      | <span data-ttu-id="b94b1-116">Metriche</span><span class="sxs-lookup"><span data-stu-id="b94b1-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="b94b1-117">Spese - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="b94b1-118">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="b94b1-118">Total expenses this year</span></span></li><li><span data-ttu-id="b94b1-119">Spese totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="b94b1-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="b94b1-120">Ricavi - Effettivi rispetto al budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="b94b1-121">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="b94b1-121">Total revenue this year</span></span></li><li><span data-ttu-id="b94b1-122">Ricavi totali budget anno in corso</span><span class="sxs-lookup"><span data-stu-id="b94b1-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="b94b1-123">Gestione spese</span><span class="sxs-lookup"><span data-stu-id="b94b1-123">Expense</span></span>                     | <ul><li><span data-ttu-id="b94b1-124">Spese totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="b94b1-124">Total expenses this year</span></span></li><li><span data-ttu-id="b94b1-125">Obiettivo per le spese in base al budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="b94b1-126">Ricavi</span><span class="sxs-lookup"><span data-stu-id="b94b1-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="b94b1-127">Ricavi totali anno in corso</span><span class="sxs-lookup"><span data-stu-id="b94b1-127">Total revenue this year</span></span></li><li><span data-ttu-id="b94b1-128">Obiettivo per ricavi in base al budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="b94b1-129">Reddito netto</span><span class="sxs-lookup"><span data-stu-id="b94b1-129">Net income</span></span>                  | <ul><li><span data-ttu-id="b94b1-130">Reddito netto anno in corso</span><span class="sxs-lookup"><span data-stu-id="b94b1-130">Net income this year</span></span></li><li><span data-ttu-id="b94b1-131">Obiettivo per reddito netto in base al budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="b94b1-132">Informazioni su modelli ed entità di dati</span><span class="sxs-lookup"><span data-stu-id="b94b1-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="b94b1-133">Entità</span><span class="sxs-lookup"><span data-stu-id="b94b1-133">Entity</span></span>                    | <span data-ttu-id="b94b1-134">Contenuto</span><span class="sxs-lookup"><span data-stu-id="b94b1-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="b94b1-135">Attività di contabilità generale</span><span class="sxs-lookup"><span data-stu-id="b94b1-135">General Ledger Activities</span></span> | <span data-ttu-id="b94b1-136">Importo transazione per contabilità generale</span><span class="sxs-lookup"><span data-stu-id="b94b1-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="b94b1-137">Attività di budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-137">Budget Activities</span></span>         | <span data-ttu-id="b94b1-138">Importi di transazione per il registro di budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="b94b1-139">Conti principali</span><span class="sxs-lookup"><span data-stu-id="b94b1-139">Main Accounts</span></span>             | <span data-ttu-id="b94b1-140">Conti principali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="b94b1-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="b94b1-141">Calendari fiscali</span><span class="sxs-lookup"><span data-stu-id="b94b1-141">Fiscal Calendars</span></span>          | <span data-ttu-id="b94b1-142">Calendari fiscali per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="b94b1-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="b94b1-143">Contabilità generali</span><span class="sxs-lookup"><span data-stu-id="b94b1-143">Ledgers</span></span>                   | <span data-ttu-id="b94b1-144">Contabilità generale utilizzabile per filtrare il report nella contabilità generale corrente</span><span class="sxs-lookup"><span data-stu-id="b94b1-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="b94b1-145">Codici budget</span><span class="sxs-lookup"><span data-stu-id="b94b1-145">Budget Codes</span></span>              | <span data-ttu-id="b94b1-146">Codici budget per filtrare i report per</span><span class="sxs-lookup"><span data-stu-id="b94b1-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="b94b1-147">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="b94b1-147">Legal Entities</span></span>            | <span data-ttu-id="b94b1-148">Persone giuridiche utilizzabili per filtrare il report nella persona giuridica corrente</span><span class="sxs-lookup"><span data-stu-id="b94b1-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |
