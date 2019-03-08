---
title: Sincronizzare ordini di lavoro con un progetto da Field Service a Finance and Operations
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "329852"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="428b4-103">Sincronizzare ordini di lavoro con un progetto da Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="428b4-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="428b4-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="428b4-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="428b4-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="428b4-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="428b4-106">Il modello **Prodotti Field Service (da Finance and Operations a Field Service)** utilizzato si basa sul modello **Prodotti (da Finance and Operations a Sales) - Diretto** di Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="428b4-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="428b4-107">Per ulteriori informazioni, vedere [Prodotti (da Finance and Operations a Sales) - Diretto](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="428b4-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="428b4-108">Questo argomento descrive solo le differenze tra i modelli **Prodotti Field Service (da Finance and Operations a Field Service)** e **Prodotti Field Service (da Finance and Operations a Field Service) - Diretto**.</span><span class="sxs-lookup"><span data-stu-id="428b4-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="428b4-109">La differenza principale è che questo modello include il mapping del numero di progetto assegnato all'ordine di lavoro in Field Service, affinché l'ordine cliente creato in Finance and Operations includa il numero di progetto e che sia possibile eseguire la fatturazione nel progetto correlato.</span><span class="sxs-lookup"><span data-stu-id="428b4-109">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="428b4-110">Inoltre, il modello utilizza la funzionalità Filtro e query avanzati.</span><span class="sxs-lookup"><span data-stu-id="428b4-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="428b4-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="428b4-111">Templates and tasks</span></span>

<span data-ttu-id="428b4-112">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="428b4-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="428b4-113">Ordini di lavoro con progetto (da Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="428b4-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="428b4-114">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="428b4-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="428b4-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="428b4-115">WorkOrderHeader</span></span>
- <span data-ttu-id="428b4-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="428b4-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="428b4-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="428b4-117">WorkOrderProduct</span></span>
- <span data-ttu-id="428b4-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="428b4-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="428b4-119">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="428b4-119">Field Service CRM solution</span></span>
<span data-ttu-id="428b4-120">Il campo **Progetto esterno** è stato aggiunto all'entità Ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="428b4-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="428b4-121">Questo campo è un lookup and buy che contrassegna l'ordine di lavoro con un progetto; l'ordine cliente verrà quindi collegato a un progetto in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="428b4-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="428b4-122">Quando **Stato sistema** passa da Aperto - In corso (690,970,000) a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà possibile aggiungere, rimuovere o cambiare il valore.</span><span class="sxs-lookup"><span data-stu-id="428b4-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="428b4-123">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="428b4-123">Template mapping in Data integration</span></span>

<span data-ttu-id="428b4-124">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="428b4-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="428b4-125">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="428b4-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="428b4-126">[![Mapping dei modelli in Integrazione dati](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="428b4-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="428b4-127">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="428b4-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="428b4-128">[![Mapping dei modelli in Integrazione dati](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="428b4-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="428b4-129">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="428b4-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="428b4-130">[![Mapping dei modelli in Integrazione dati](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="428b4-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="428b4-131">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="428b4-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="428b4-132">[![Mapping dei modelli in Integrazione dati](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="428b4-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
