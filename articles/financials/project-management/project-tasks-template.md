---
title: "Sincronizzare le attività di progetto da Project Service Automation"
description: "Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
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
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: it-it
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a><span data-ttu-id="cba26-103">Sincronizzare le attività di progetto in Project Service Automation direttamente con le attività di progetto di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cba26-103">Synchronize project tasks from Project Service Automation directly to project activities in Finance and Operations</span></span>

<span data-ttu-id="cba26-104">Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cba26-104">This topic describes the template and underlying task that is used to synchronize project tasks directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="cba26-105">L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Dynamics 365 for Finance and Operations versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="cba26-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="cba26-106">Flusso di dati per Project Service Automation verso Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cba26-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="cba26-107">La soluzione di integrazione di Project Service Automation in Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cba26-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="cba26-108">Il modello di integrazione disponibile con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle attività del progetto da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cba26-108">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="cba26-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cba26-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="cba26-110">[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="cba26-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="cba26-111">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="cba26-111">Template and task</span></span>

<span data-ttu-id="cba26-112">Per accedere al modello disponibile, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="cba26-112">To access the template, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="cba26-113">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le attività di progetto da Project Service Automation a Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="cba26-113">The following template and underlying task is used to synchronize project tasks from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="cba26-114">-**Nome del modello in Integrazione dati:** Attività di progetto (da PSA a Fin and Ops) - **Nome dell'attività del progetto:** Attività di progetto</span><span class="sxs-lookup"><span data-stu-id="cba26-114">-**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops) -**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="cba26-115">Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.</span><span class="sxs-lookup"><span data-stu-id="cba26-115">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="cba26-116">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="cba26-116">Entity set</span></span>

|<span data-ttu-id="cba26-117">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="cba26-117">Project Service Automation</span></span>               | <span data-ttu-id="cba26-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cba26-118">Finance and Operations</span></span>                |
|-----------------------------------------|---------------------------------------|
| <span data-ttu-id="cba26-119">Attività di progetto</span><span class="sxs-lookup"><span data-stu-id="cba26-119">Project Tasks</span></span>                           | <span data-ttu-id="cba26-120">Entità di integrazione per attività di progetto</span><span class="sxs-lookup"><span data-stu-id="cba26-120">Integration entity for project task.</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="cba26-121">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="cba26-121">Entity flow</span></span>

<span data-ttu-id="cba26-122">Le attività di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance and Operations come attività di progetto.</span><span class="sxs-lookup"><span data-stu-id="cba26-122">Project tasks are managed in Project Service Automation, and they are synchronized to Finance and Operations as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="cba26-123">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="cba26-123">Prerequisites and mapping setup</span></span>

<span data-ttu-id="cba26-124">Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.</span><span class="sxs-lookup"><span data-stu-id="cba26-124">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="cba26-125">Power Query</span><span class="sxs-lookup"><span data-stu-id="cba26-125">Power Query</span></span>

<span data-ttu-id="cba26-126">È necessario utilizzare Microsoft Power Query per filtrare i dati se si verificano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cba26-126">You must use Microsoft Power Query to filter data if these conditions are met:</span></span>

- <span data-ttu-id="cba26-127">Si dispone di record specifici di risorsa in un'attività di progetto.</span><span class="sxs-lookup"><span data-stu-id="cba26-127">You have resource specific records within a project task.</span></span>

<span data-ttu-id="cba26-128">Se è necessario utilizzare Power Query, seguire queste indicazioni:</span><span class="sxs-lookup"><span data-stu-id="cba26-128">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="cba26-129">Il modello delle attività di progetto (da PSA a Fin and Ops) include un filtro predefinito per escludere i record specifici di risorsa dall'interno di un'attività di progetto tramite l'impostazione del filtro in **IsLineTask** su **False**.</span><span class="sxs-lookup"><span data-stu-id="cba26-129">The Project tasks (PSA to Fin and Ops) template has a default filter to exclude resource specific records from within a project task by setting the filter on the **IsLineTask** to **False**.</span></span> <span data-ttu-id="cba26-130">Se si crea un modello personale, è necessario aggiungere questo filtro.</span><span class="sxs-lookup"><span data-stu-id="cba26-130">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cba26-131">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="cba26-131">Template mapping in Data integration</span></span>

<span data-ttu-id="cba26-132">Nella figura seguente viene mostrato un esempio dei mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="cba26-132">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="cba26-133">Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cba26-133">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="cba26-134">[![Mapping del modello](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="cba26-134">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>


