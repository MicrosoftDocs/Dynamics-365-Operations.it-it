---
title: Sincronizzare l'elenco di progetti da Finance and Operations a Field Service
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: it-it
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="276ec-103">Sincronizzare l'elenco di progetti da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="276ec-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="276ec-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="276ec-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="276ec-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="276ec-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="276ec-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="276ec-106">Templates and tasks</span></span>
<span data-ttu-id="276ec-107">Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="276ec-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="276ec-108">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="276ec-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="276ec-109">Progetti (da Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="276ec-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="276ec-110">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="276ec-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="276ec-111">Progetti</span><span class="sxs-lookup"><span data-stu-id="276ec-111">Projects</span></span>

<span data-ttu-id="276ec-112">Le attività di sincronizzazione seguenti sono necessarie prima della sincronizzazione dell'elenco di progetti:</span><span class="sxs-lookup"><span data-stu-id="276ec-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="276ec-113">Conti (da Sales a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="276ec-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="276ec-114">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="276ec-114">Entity set</span></span>
<span data-ttu-id="276ec-115">Field Service   Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="276ec-115">Field Service   Finance and Operations</span></span>

| <span data-ttu-id="276ec-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="276ec-116">Field Service</span></span>           | <span data-ttu-id="276ec-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="276ec-117">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="276ec-118">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="276ec-118">msdynce_externalprojects</span></span> | <span data-ttu-id="276ec-119">Progetti</span><span class="sxs-lookup"><span data-stu-id="276ec-119">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="276ec-120">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="276ec-120">Entity flow</span></span>
<span data-ttu-id="276ec-121">I progetti sono creati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="276ec-121">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="276ec-122">I progetti con **Tipo di progetto** Tempistica e materiali e **Fase progetto** In corso saranno sincronizzati all'entità **Progetto esterno** in Field Service, incluse le informazioni Numero progetto, Nome progetto, Fase progetto e Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="276ec-122">Projects with **Project type** Time and material and **Project stage** In process will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage and Customer account information.</span></span> <span data-ttu-id="276ec-123">L'elenco di **Progetto esterno** viene utilizzato per associare gli ordini di assistenza Field Service ai progetti Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="276ec-123">The list of **External Project** is used to pair Field service Work orders with Finance and Operations projects.</span></span>
<span data-ttu-id="276ec-124">Soluzione CRM Field Service Progetto esterno è una nuova entità che ottiene tutti i progetti da Operations.</span><span class="sxs-lookup"><span data-stu-id="276ec-124">Field Service CRM solution The External Project is a new entity that gets all the Projects from Operations.</span></span>
<span data-ttu-id="276ec-125">Il campo Progetto esterno è stato aggiunto all'entità Ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="276ec-125">The External Project field has been added to the Work Order entity.</span></span> <span data-ttu-id="276ec-126">Questo campo è un lookup and buy che contrassegna l'ordine di lavoro con un progetto; l'ordine cliente verrà quindi collegato a un progetto in Operations.</span><span class="sxs-lookup"><span data-stu-id="276ec-126">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Operations.</span></span> <span data-ttu-id="276ec-127">Quando Stato sistema passa da Aperto - In corso (690,970,000) a uno stato superiore, il campo Progetto esterno verrà bloccato e non sarà possibile aggiungere, rimuovere o cambiare il valore.</span><span class="sxs-lookup"><span data-stu-id="276ec-127">Ones the System Status changes Open – In Progress(690,970,000) to a higher status the External Project field will be locked and you can't add, remove or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="276ec-128">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="276ec-128">Prerequisites and mapping setup</span></span>
### <a name="in-finance-and-operations"></a><span data-ttu-id="276ec-129">In Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="276ec-129">In Finance and Operations</span></span>
<span data-ttu-id="276ec-130">Abilitare il rilevamento delle modifiche per progetti entità di dati</span><span class="sxs-lookup"><span data-stu-id="276ec-130">Enable change tracking for Data entity Projects</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="276ec-131">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="276ec-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="276ec-132">Progetti (da Finance and Operations a Field Service): Progetti</span><span class="sxs-lookup"><span data-stu-id="276ec-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="276ec-133">[![Mapping dei modelli in Integrazione dati](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="276ec-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>

