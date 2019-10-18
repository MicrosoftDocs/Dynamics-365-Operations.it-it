---
title: Sincronizzare le attività di progetto direttamente da Project Service Automation a Finance and Operations
description: Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Microsoft Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
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
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 977037f0e2b313ebf05a3e1616d34567f82e82d7
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250394"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="139c2-103">Sincronizzare le attività di progetto direttamente da Project Service Automation a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="139c2-103">Synchronize project tasks directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="139c2-104">Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Dynamics 365 Project Service Automation a Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="139c2-104">This topic describes the template and underlying task that are used to synchronize project tasks directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="139c2-105">L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili nella versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="139c2-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="139c2-106">Se si utilizza Enterprise Edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="139c2-106">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="139c2-107">Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="139c2-107">If you must reset the accounting distributions, we recommended that you also install KB 4131710.</span></span>
> - <span data-ttu-id="139c2-108">L'integrazione dei numeri effettivi è disponibile nella versione 8.0.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="139c2-108">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="139c2-109">Flusso di dati per Project Service Automation verso Finance</span><span class="sxs-lookup"><span data-stu-id="139c2-109">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="139c2-110">La soluzione di integrazione di Project Service Automation a Finance utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="139c2-110">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="139c2-111">Il modello di integrazione disponibile con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle attività del progetto da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="139c2-111">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance.</span></span>

<span data-ttu-id="139c2-112">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance.</span><span class="sxs-lookup"><span data-stu-id="139c2-112">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="139c2-113">[![Flusso di dati per l'integrazione di Project Service Automation con Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="139c2-113">[![Data flow for Project Service Automation integration with Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="139c2-114">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="139c2-114">Template and task</span></span>

<span data-ttu-id="139c2-115">Per accedere al modello disponibile, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="139c2-115">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="139c2-116">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le attività di progetto da Project Service Automation a Finance:</span><span class="sxs-lookup"><span data-stu-id="139c2-116">The following template and underlying task are used to synchronize project tasks from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="139c2-117">**Nome del modello in Integrazione dati:** attività di progetto (da PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="139c2-117">**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="139c2-118">**Nome dell'attività nel progetto:** attività di progetto</span><span class="sxs-lookup"><span data-stu-id="139c2-118">**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="139c2-119">Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.</span><span class="sxs-lookup"><span data-stu-id="139c2-119">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="139c2-120">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="139c2-120">Entity set</span></span>

| <span data-ttu-id="139c2-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="139c2-121">Project Service Automation</span></span> | <span data-ttu-id="139c2-122">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="139c2-122">Finance</span></span>                             |
|----------------------------|-------------------------------------|
| <span data-ttu-id="139c2-123">Attività di progetto</span><span class="sxs-lookup"><span data-stu-id="139c2-123">Project Tasks</span></span>              | <span data-ttu-id="139c2-124">Entità di integrazione per attività di progetto</span><span class="sxs-lookup"><span data-stu-id="139c2-124">Integration entity for project task</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="139c2-125">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="139c2-125">Entity flow</span></span>

<span data-ttu-id="139c2-126">Le attività di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance come attività di progetto.</span><span class="sxs-lookup"><span data-stu-id="139c2-126">Project tasks are managed in Project Service Automation, and they are synchronized to Finance as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="139c2-127">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="139c2-127">Prerequisites and mapping setup</span></span>

<span data-ttu-id="139c2-128">Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.</span><span class="sxs-lookup"><span data-stu-id="139c2-128">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="139c2-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="139c2-129">Power Query</span></span>

<span data-ttu-id="139c2-130">È necessario utilizzare Microsoft Power Query per filtrare i dati in Excel se si verificano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="139c2-130">You must use Microsoft Power Query for Excel to filter data if this condition is met:</span></span>

- <span data-ttu-id="139c2-131">Si dispone di record specifici di risorsa in un'attività di progetto.</span><span class="sxs-lookup"><span data-stu-id="139c2-131">You have resource-specific records in a project task.</span></span>

<span data-ttu-id="139c2-132">Se è necessario utilizzare Power Query, seguire queste indicazioni:</span><span class="sxs-lookup"><span data-stu-id="139c2-132">If you must use Power Query, follow this guideline:</span></span>

- <span data-ttu-id="139c2-133">Il modello delle attività di progetto (da PSA a Fin and Ops) include un filtro predefinito per escludere i record specifici di risorsa da un'attività di progetto tramite l'impostazione del filtro di **IsLineTask** su **False**.</span><span class="sxs-lookup"><span data-stu-id="139c2-133">The Project tasks (PSA to Fin and Ops) template has a default filter that excludes resource-specific records from a project task by setting the filter on **IsLineTask** to **False**.</span></span> <span data-ttu-id="139c2-134">Se si crea un modello personale, è necessario aggiungere questo filtro.</span><span class="sxs-lookup"><span data-stu-id="139c2-134">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="139c2-135">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="139c2-135">Template mapping in Data integration</span></span>

<span data-ttu-id="139c2-136">Nella figura seguente viene mostrato un esempio dei mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="139c2-136">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="139c2-137">Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="139c2-137">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="139c2-138">[![Mapping del modello](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="139c2-138">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>
