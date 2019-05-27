---
title: Sincronizzare ordini di lavoro con un progetto da Field Service a Finance and Operations
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536735"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="7128f-103">Sincronizzare ordini di lavoro con un progetto da Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7128f-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7128f-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7128f-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="7128f-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="7128f-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="7128f-106">Il modello **Ordini di lavoro con progetto (da Field Service a Finance and Operations)** utilizzato si basa sul modello **Ordini di lavoro (da Field Service a Fin and Ops)**.</span><span class="sxs-lookup"><span data-stu-id="7128f-106">The used **Work Orders with Project (Field Service to Fin and Ops)** template is based on the **Work Orders (Field Service to Fin and Ops)** template.</span></span> <span data-ttu-id="7128f-107">Per ulteriori informazioni, vedere [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente in Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="7128f-107">For more information, see [Synchronize work orders in Field Service to sales orders in Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="7128f-108">In questo argomento vengono descritte le differenze tra i due modelli:</span><span class="sxs-lookup"><span data-stu-id="7128f-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="7128f-109">**Ordini di lavoro con progetto (da Field Service a Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="7128f-109">**Work Orders with Project (Field Service to Fin and Ops)**</span></span>
- <span data-ttu-id="7128f-110">**Ordini di lavoro (da Field Service a Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="7128f-110">**Work Orders (Field Service to Fin and Ops)**</span></span>

<span data-ttu-id="7128f-111">La differenza principale è che questo modello include il mapping del numero di progetto assegnato all'ordine di lavoro in Field Service, affinché l'ordine cliente creato in Finance and Operations includa il numero di progetto e che sia possibile eseguire la fatturazione nel progetto correlato.</span><span class="sxs-lookup"><span data-stu-id="7128f-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="7128f-112">Inoltre, il modello utilizza la funzionalità Filtro e query avanzati.</span><span class="sxs-lookup"><span data-stu-id="7128f-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7128f-113">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="7128f-113">Templates and tasks</span></span>

<span data-ttu-id="7128f-114">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="7128f-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="7128f-115">Ordini di lavoro con progetto (da Field Service a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7128f-115">Work Orders with Project (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="7128f-116">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="7128f-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="7128f-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="7128f-117">WorkOrderHeader</span></span>
- <span data-ttu-id="7128f-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="7128f-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="7128f-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="7128f-119">WorkOrderProduct</span></span>
- <span data-ttu-id="7128f-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="7128f-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="7128f-121">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="7128f-121">Field Service CRM solution</span></span>
<span data-ttu-id="7128f-122">Il campo **Progetto esterno** è stato aggiunto all'entità Ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7128f-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="7128f-123">Questo campo è un lookup and buy che contrassegna l'ordine di lavoro con un progetto; l'ordine cliente verrà quindi collegato a un progetto in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7128f-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="7128f-124">Quando **Stato sistema** passa da Aperto - In corso (690,970,000) a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà possibile aggiungere, rimuovere o cambiare il valore.</span><span class="sxs-lookup"><span data-stu-id="7128f-124">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7128f-125">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="7128f-125">Template mapping in Data integration</span></span>

<span data-ttu-id="7128f-126">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7128f-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a><span data-ttu-id="7128f-127">Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="7128f-127">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeader</span></span>

<span data-ttu-id="7128f-128">[![Mapping dei modelli in Integrazione dati](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="7128f-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a><span data-ttu-id="7128f-129">Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="7128f-129">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeaderProject</span></span>

<span data-ttu-id="7128f-130">[![Mapping dei modelli in Integrazione dati](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="7128f-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a><span data-ttu-id="7128f-131">Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="7128f-131">Work Orders with Project (Field Service to Fin and Ops): WorkOrderProduct</span></span>

<span data-ttu-id="7128f-132">[![Mapping dei modelli in Integrazione dati](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="7128f-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a><span data-ttu-id="7128f-133">Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="7128f-133">Work Orders with Project (Field Service to Fin and Ops): WorkOrderService</span></span>

<span data-ttu-id="7128f-134">[![Mapping dei modelli in Integrazione dati](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="7128f-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
