---
title: Panoramica Project Service Automation
description: In questo argomento vengono fornite informazioni sulla soluzione di integrazione di Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250555"
---
# <a name="project-service-automation-overview"></a><span data-ttu-id="034d6-103">Panoramica Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="034d6-103">Project Service Automation overview</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="034d6-104">La soluzione di integrazione di Project Service Automation con Finance utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Dynamics 365 Finance e Dynamics 365 Project Service Automation tramite Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="034d6-104">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Dynamics 365 Finance and Dynamics 365 Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="034d6-105">I modelli di integrazione disponibili con la funzionalità Integrazione dati abilita il flusso di progetti, contratti di progetto, righe di contratto di progetto, punti cardine delle righe di contratto di progetto, attività di progetto, categorie di transazione di spesa, stime orarie e delle spese da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-105">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="034d6-106">Se si utilizza la versione 7.3.0, è necessario installare KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="034d6-106">If you're using version 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="034d6-107">In questo modo sarà possibile integrare i progetti a prezzo fisso.</span><span class="sxs-lookup"><span data-stu-id="034d6-107">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="034d6-108">Se si utilizza la versione 7.3.0 e si eseguono transazioni di tipo commissione da Project Service Automation, è necessario installare KB 4345320 per includere tali commissioni nella fattura di progetto.</span><span class="sxs-lookup"><span data-stu-id="034d6-108">If you're using version 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="034d6-109">Se si utilizza la versione 8.0, sarà possibile utilizzare l'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="034d6-109">If you're using version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="034d6-110">Se si utilizza la versione 8.0.1 o successiva, sarà possibile sincronizzare i numeri effettivi.</span><span class="sxs-lookup"><span data-stu-id="034d6-110">If you're using version 8.0.1 or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="034d6-111">Prima di poter integrare Project Service Automation con Finance, è necessario configurare i parametri di integrazione Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="034d6-111">Before you can integrate Project Service Automation Finance, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="034d6-112">Per ulteriori informazioni, vedere [Parametri di integrazione di Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="034d6-112">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="034d6-113">Questa soluzione di integrazione consente la sincronizzazione diretta negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="034d6-113">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="034d6-114">Gestire i contratti di progetto in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-114">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="034d6-115">Creare progetti in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-115">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="034d6-116">Gestire le righe dei contratti di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-116">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="034d6-117">Gestire i punti cardine delle righe dei contratti di progetto in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-117">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="034d6-118">Gestire le attività di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-118">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="034d6-119">Gestire le categorie di transazione delle spese in Finance e sincronizzarle direttamente da Finance in Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="034d6-119">Maintain expense transaction categories in Finance, and synchronize them directly from Finance to Project Service Automation.</span></span>
- <span data-ttu-id="034d6-120">Creare stime di ore di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-120">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="034d6-121">Creare stime di spese di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-121">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="034d6-122">Creare tempi di progetto, spese di progetto e valori effettivi di commissione in Project Service Automation e creare transazioni di progetto nel giornale di registrazione di integrazione di Project Service Automation in modo da poterli registrare in Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-122">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="034d6-123">Sincronizzazione dati</span><span class="sxs-lookup"><span data-stu-id="034d6-123">Data synchronization</span></span>

<span data-ttu-id="034d6-124">La figura seguente mostra il modo in cui i dati vengono sincronizzati nell'ambito dell'integrazione tra Project Service Automation e Finance.</span><span class="sxs-lookup"><span data-stu-id="034d6-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance.</span></span>

> [!NOTE]
> <span data-ttu-id="034d6-125">Non tutti i modelli sono disponibili al momento.</span><span class="sxs-lookup"><span data-stu-id="034d6-125">Not all templates are currently available.</span></span> <span data-ttu-id="034d6-126">I modelli verranno rilasciati man mano che vengono completati.</span><span class="sxs-lookup"><span data-stu-id="034d6-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="034d6-127">[![Iintegrazione di Project Service Automation con Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="034d6-127">[![Project Service Automation integration with Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance"></a><span data-ttu-id="034d6-128">Requisiti di sistema per Finance</span><span class="sxs-lookup"><span data-stu-id="034d6-128">System requirements for Finance</span></span>

<span data-ttu-id="034d6-129">Per utilizzare la soluzione di integrazione di Project Service Automation con Finance, è necessario installare Enterprise Edition 7.3 con aggiornamento 12 della piattaforma o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="034d6-129">To use the Project Service Automation to Finance integration solution, you must install Enterprise edition 7.3 with Platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="034d6-130">Requisiti di sistema per Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="034d6-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="034d6-131">Per utilizzare la soluzione di integrazione di Project Service Automation con Finance, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="034d6-131">To use the Project Service Automation to Finance integration solution, you must install the following components:</span></span>

- <span data-ttu-id="034d6-132">Dynamics 365 Project Service Automation 9.0.0.0 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="034d6-132">Dynamics 365 Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="034d6-133">Soluzione Prospect to cash per Dynamics 365 Sales versione 1.14.0.0 (v14) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="034d6-133">Prospect to cash solution for Dynamics 365 Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="034d6-134">Soluzione Project Service Automation con Finance per Dynamics 365 Project Service Automation versione 1.0.0.0 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="034d6-134">Project Service Automation to Finance solution for Dynamics 365 Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="034d6-135">Installare la soluzione di integrazione Project Service Automation in Finance nell'istanza di Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="034d6-135">Install the Project Service Automation to Finance integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="034d6-136">Scaricare la soluzione di integrazione di Project Service Automation con Finance dall'[Area download Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) e seguire le istruzioni incluse con la soluzione.</span><span class="sxs-lookup"><span data-stu-id="034d6-136">Download the Project Service Automation to Finance integration solution from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>
