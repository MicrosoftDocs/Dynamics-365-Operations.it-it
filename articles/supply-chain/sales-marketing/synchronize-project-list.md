---
title: Sincronizzare l'elenco di progetti da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "842606"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="d8a60-103">Sincronizzare l'elenco dei progetti da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="d8a60-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d8a60-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="d8a60-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="d8a60-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="d8a60-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d8a60-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="d8a60-106">Templates and tasks</span></span>
<span data-ttu-id="d8a60-107">Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="d8a60-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="d8a60-108">**Modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="d8a60-108">**Template in Data integration**</span></span>
- <span data-ttu-id="d8a60-109">Progetti (da Fin and Ops a Field Service)</span><span class="sxs-lookup"><span data-stu-id="d8a60-109">Projects (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="d8a60-110">**Attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="d8a60-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="d8a60-111">Progetti</span><span class="sxs-lookup"><span data-stu-id="d8a60-111">Projects</span></span>

<span data-ttu-id="d8a60-112">Le attività di sincronizzazione seguenti sono necessarie prima della sincronizzazione dell'elenco di progetti:</span><span class="sxs-lookup"><span data-stu-id="d8a60-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="d8a60-113">Conti (da Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="d8a60-113">Accounts (Sales to Fin and Ops)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="d8a60-114">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="d8a60-114">Entity set</span></span>
| <span data-ttu-id="d8a60-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="d8a60-115">Field Service</span></span>           | <span data-ttu-id="d8a60-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d8a60-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="d8a60-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="d8a60-117">msdynce_externalprojects</span></span> | <span data-ttu-id="d8a60-118">Progetti</span><span class="sxs-lookup"><span data-stu-id="d8a60-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="d8a60-119">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="d8a60-119">Entity flow</span></span>
<span data-ttu-id="d8a60-120">I progetti sono creati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d8a60-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="d8a60-121">I progetti con **Tipo di progetto** impostato su **Tempistica e materiali** e **Fase progetto** impostato su **In corso** saranno sincronizzati all'entità **Progetto esterno** in Field Service, incluse le informazioni Numero progetto, Nome progetto, Fase progetto e Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="d8a60-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="d8a60-122">L'elenco **Progetto esterno** viene utilizzato per associare gli ordini di assistenza Field Service ai progetti Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d8a60-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="d8a60-123">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="d8a60-123">Field Service CRM solution</span></span>
<span data-ttu-id="d8a60-124">L'entità **Progetto esterno** ottiene tutti i progetti da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d8a60-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="d8a60-125">Il campo **Progetto esterno** è stato aggiunto all'entità **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="d8a60-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="d8a60-126">Questo campo è un lookup, quindi contrassegnando l'ordine di lavoro con un progetto, l'ordine cliente verrà collegato a un progetto in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d8a60-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="d8a60-127">Quando **Stato sistema** passa da **Aperto - In corso (690,970,000)** a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà più possibile aggiungere, rimuovere o cambiare il valore.</span><span class="sxs-lookup"><span data-stu-id="d8a60-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="d8a60-128">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="d8a60-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="d8a60-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d8a60-129">Finance and Operations</span></span>
<span data-ttu-id="d8a60-130">Abilitare il rilevamento delle modifiche per progetti entità di dati.</span><span class="sxs-lookup"><span data-stu-id="d8a60-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d8a60-131">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="d8a60-131">Template mapping in Data integration</span></span>


### <a name="projects-fin-and-ops-to-field-service-projects"></a><span data-ttu-id="d8a60-132">Progetti (da Fin and Ops a Field Service): Progetti</span><span class="sxs-lookup"><span data-stu-id="d8a60-132">Projects (Fin and Ops to Field Service): Projects</span></span>

<span data-ttu-id="d8a60-133">[![Mapping dei modelli in Integrazione dati](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="d8a60-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
