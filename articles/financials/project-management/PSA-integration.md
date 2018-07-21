---
title: Project Service Automation
description: "Questa soluzione utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Microsoft Dynamics 365 for Finance and Operations e Microsoft Dynamics 365 per Project Service Automation tramite Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: it-it
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="a700f-103">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="a700f-103">Project Service Automation</span></span>

<span data-ttu-id="a700f-104">La soluzione di integrazione tra Project Service Automation e Finance and Operations utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Microsoft Dynamics 365 for Finance and Operations e Microsoft Dynamics 365 per Project Service Automation tramite Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="a700f-104">The Project Service Automation to Finance and Operations integration solution uses the Data Integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via the Common Data Service (CDS).</span></span> <span data-ttu-id="a700f-105">I modelli di integrazione disponibili con la funzionalità Integrazione dati abilita il flusso di progetti, contratti di progetto, righe di contratto di progetto, punti cardine delle righe di contratto di progetto, attività di progetto, categorie di transazione di spesa, stime orarie e delle spese da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-105">The integration templates that are available with the Data Integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="a700f-106">Se si utilizza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, è necessario installare KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="a700f-106">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="a700f-107">In questo modo sarà possibile integrare i progetti a prezzo fisso.</span><span class="sxs-lookup"><span data-stu-id="a700f-107">This will allow you to integrate fixed price projects.</span></span>
>
> <span data-ttu-id="a700f-108">Se si utilizza Dynamics 365 for Finance and Operations versione 8.0, sarà possibile utilizzare l'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a700f-108">If you are using Dynamics 365 for Finance and Operations version 8.0, you will be able to use project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
>
> <span data-ttu-id="a700f-109">Se si utilizza Dynamics 365 for Finance and Operations versione 8.0.1, sarà possibile sincronizzare i valori effettivi.</span><span class="sxs-lookup"><span data-stu-id="a700f-109">If you are using Dynamics 365 for Finance and Operations version 8.0.1, you will be able to synchronize actuals.</span></span>
>
> <span data-ttu-id="a700f-110">Se si utilizza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a700f-110">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="a700f-111">Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="a700f-111">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

<span data-ttu-id="a700f-112">Prima di poter integrare Project Service Automation con Finance and Operations, è necessario configurare i parametri di integrazione Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a700f-112">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="a700f-113">Per ulteriori informazioni, vedere Parametri di integrazione di Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a700f-113">For more information, see Project Service Automation integration parameters.</span></span>

<span data-ttu-id="a700f-114">Questa soluzione di integrazione consente la sincronizzazione diretta negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="a700f-114">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="a700f-115">Gestire i contratti di progetto in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-115">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="a700f-116">Creare progetti in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-116">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="a700f-117">Gestire righe di contratti di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-117">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="a700f-118">Gestire attività cardine di righe di contratti di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-118">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="a700f-119">Gestire attività di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-119">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="a700f-120">Gestire le categorie di transazione delle spese in Finance and Operations e sincronizzarle direttamente da Finance and Operations in Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="a700f-120">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="a700f-121">Creare stime di ore di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-121">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="a700f-122">Creare stime di spese di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-122">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="a700f-123">Sincronizzazione dati</span><span class="sxs-lookup"><span data-stu-id="a700f-123">Data synchronization</span></span>
<span data-ttu-id="a700f-124">La figura seguente mostra il modo in cui i dati vengono sincronizzati nell'ambito dell'integrazione tra Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a700f-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="a700f-125">Non tutti i modelli sono disponibili al momento.</span><span class="sxs-lookup"><span data-stu-id="a700f-125">Not all templates are currently available.</span></span> <span data-ttu-id="a700f-126">I modelli verranno rilasciati man mano che vengono completati.</span><span class="sxs-lookup"><span data-stu-id="a700f-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="a700f-127">[![Integrazione di Project Service Automation con Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="a700f-127">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="a700f-128">Requisiti di sistema di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a700f-128">System requirements for Finance and Operations</span></span>

<span data-ttu-id="a700f-129">Per utilizzare la soluzione di integrazione di Project Service Automation con Finance and Operations, è necessario installare Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 con aggiornamento 12 della piattaforma o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a700f-129">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="a700f-130">Requisiti di sistema per Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="a700f-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="a700f-131">Per utilizzare la soluzione di integrazione di Project Service Automation con Finance and Operations, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a700f-131">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="a700f-132">Microsoft Dynamics 365 for Project Service Automation versione 9.0.0.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a700f-132">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later.</span></span>
- <span data-ttu-id="a700f-133">Soluzione Prospect to cash per Dynamics 365 for Sales versione 1.14.0.0 (v14) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a700f-133">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>
- <span data-ttu-id="a700f-134">Soluzione Project Service Automation to Operations per Dynamics 365 for Project Service Automation versione 1.0.0.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a700f-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation version 1.0.0.0 or later.</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="a700f-135">Installare la soluzione di integrazione Project Service Automation in Finance and Operations nell'istanza di Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="a700f-135">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>



