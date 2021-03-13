---
title: Sincronizzare l'elenco dei progetti da Supply Chain Management a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 12708b35be87baf1ad13296b56507f3246f96394
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010874"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="3ef6b-103">Sincronizzare l'elenco dei progetti da Supply Chain Management a Field Service</span><span class="sxs-lookup"><span data-stu-id="3ef6b-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3ef6b-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="3ef6b-105">[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="3ef6b-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="3ef6b-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="3ef6b-106">Templates and tasks</span></span>
<span data-ttu-id="3ef6b-107">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i progetti da Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="3ef6b-108">**Modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="3ef6b-108">**Template in Data integration**</span></span>
- <span data-ttu-id="3ef6b-109">Progetti (da Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="3ef6b-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="3ef6b-110">**Attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="3ef6b-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="3ef6b-111">Progetti</span><span class="sxs-lookup"><span data-stu-id="3ef6b-111">Projects</span></span>

<span data-ttu-id="3ef6b-112">Le attività di sincronizzazione seguenti sono necessarie prima della sincronizzazione dell'elenco di progetti:</span><span class="sxs-lookup"><span data-stu-id="3ef6b-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="3ef6b-113">Conti (da Sales a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="3ef6b-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="3ef6b-114">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="3ef6b-114">Entity set</span></span>
| <span data-ttu-id="3ef6b-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="3ef6b-115">Field Service</span></span>           | <span data-ttu-id="3ef6b-116">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="3ef6b-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="3ef6b-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="3ef6b-117">msdynce_externalprojects</span></span> | <span data-ttu-id="3ef6b-118">Progetti</span><span class="sxs-lookup"><span data-stu-id="3ef6b-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="3ef6b-119">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="3ef6b-119">Entity flow</span></span>
<span data-ttu-id="3ef6b-120">I progetti vengono creati in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="3ef6b-121">I progetti con **Tipo di progetto** impostato su **Tempistica e materiali** e **Fase progetto** impostato su **In corso** saranno sincronizzati all'entità **Progetto esterno** in Field Service, incluse le informazioni Numero progetto, Nome progetto, Fase progetto e Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="3ef6b-122">L'elenco **Progetto esterno** viene utilizzato per associare gli ordini di assistenza Field Service ai progetti Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="3ef6b-123">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="3ef6b-123">Field Service CRM solution</span></span>
<span data-ttu-id="3ef6b-124">L'entità **Progetto esterno** ottiene tutti i progetti da Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="3ef6b-125">Il campo **Progetto esterno** è stato aggiunto all'entità **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="3ef6b-126">Questo è un campo di ricerca e pertanto contrassegnando l'ordine di lavoro con un progetto, l'ordine cliente verrà collegato a un progetto in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="3ef6b-127">Quando **Stato sistema** passa da **Aperto - In corso (690,970,000)** a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà più possibile aggiungere, rimuovere o cambiare il valore.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="3ef6b-128">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="3ef6b-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="3ef6b-129">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="3ef6b-129">Supply Chain Management</span></span>
<span data-ttu-id="3ef6b-130">Abilitare il rilevamento delle modifiche per progetti entità di dati.</span><span class="sxs-lookup"><span data-stu-id="3ef6b-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="3ef6b-131">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="3ef6b-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="3ef6b-132">Progetti (da Supply Chain Management a Field Service): Progetti</span><span class="sxs-lookup"><span data-stu-id="3ef6b-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="3ef6b-133">[![Mapping dei modelli in Integrazione dati](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="3ef6b-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
