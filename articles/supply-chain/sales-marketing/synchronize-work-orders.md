---
title: Sincronizzare ordini di lavoro da Finance and Operations a Field Service
description: "Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations."
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
ms.openlocfilehash: f5bd6b8c554688d0d1b2bfd93a34a60a95412bf3
ms.contentlocale: it-it
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="c5879-103">Sincronizzare ordini di lavoro con un progetto da Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c5879-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c5879-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c5879-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="c5879-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="c5879-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="c5879-106">Il modello **Prodotti Field Service (da Finance and Operations a Field Service)** utilizzato si basa sul modello **Prodotti (da Finance and Operations a Sales) - Diretto** di Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="c5879-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="c5879-107">Per ulteriori informazioni, vedere [Prodotti (da Finance and Operations a Sales) - Diretto](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="c5879-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="c5879-108">Questo argomento descrive solo le differenze tra i modelli **Prodotti Field Service (da Finance and Operations a Field Service)** e **Prodotti Field Service (da Finance and Operations a Field Service) - Diretto**.</span><span class="sxs-lookup"><span data-stu-id="c5879-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="c5879-109">La differenza principale è che questo modello include il mapping del numero di progetto assegnato all'ordine di lavoro in Field Service, affinché l'ordine cliente creato in Finance and Operations includa il numero di progetto e che sia possibile eseguire la fatturazione nel progetto correlato.</span><span class="sxs-lookup"><span data-stu-id="c5879-109">The main difference is that this template include mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="c5879-110">Inoltre, il modello utilizza la funzionalità Filtro e query avanzati.</span><span class="sxs-lookup"><span data-stu-id="c5879-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c5879-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="c5879-111">Templates and tasks</span></span>

<span data-ttu-id="c5879-112">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="c5879-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="c5879-113">Ordini di lavoro con progetto (da Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="c5879-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="c5879-114">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="c5879-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="c5879-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c5879-115">WorkOrderHeader</span></span>
- <span data-ttu-id="c5879-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c5879-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="c5879-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c5879-117">WorkOrderProduct</span></span>
- <span data-ttu-id="c5879-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c5879-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="c5879-119">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="c5879-119">Field Service CRM solution</span></span>
<span data-ttu-id="c5879-120">Il campo **Progetto esterno** è stato aggiunto all'entità Ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c5879-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="c5879-121">Questo campo è un lookup and buy che contrassegna l'ordine di lavoro con un progetto; l'ordine cliente verrà quindi collegato a un progetto in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c5879-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="c5879-122">Quando **Stato sistema** passa da Aperto - In corso (690,970,000) a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà possibile aggiungere, rimuovere o cambiare il valore.</span><span class="sxs-lookup"><span data-stu-id="c5879-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c5879-123">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="c5879-123">Template mapping in Data integration</span></span>

<span data-ttu-id="c5879-124">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="c5879-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="c5879-125">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c5879-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="c5879-126">[![Mapping dei modelli in Integrazione dati](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="c5879-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="c5879-127">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c5879-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="c5879-128">[![Mapping dei modelli in Integrazione dati](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="c5879-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="c5879-129">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c5879-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="c5879-130">[![Mapping dei modelli in Integrazione dati](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="c5879-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="c5879-131">Ordini di lavoro con progetto (da Field Service a Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c5879-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="c5879-132">[![Mapping dei modelli in Integrazione dati](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="c5879-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>

