---
title: Sincronizzare prodotti con l'unità di magazzino da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "359246"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="7caea-103">Sincronizzare i prodotti con l'unità di magazzino da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="7caea-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7caea-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="7caea-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="7caea-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="7caea-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="7caea-106">Il modello **Prodotti Field Service (da Finance and Operations a Field Service)** utilizzato si basa sul modello **Prodotti (da Finance and Operations a Sales) - Diretto** di Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="7caea-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="7caea-107">Per ulteriori informazioni, vedere [Prodotti (da Finance and Operations a Sales) - Diretto](products-template-mapping-direct.md).</span><span class="sxs-lookup"><span data-stu-id="7caea-107">For more information, see [Products (Finance and Operations to Sales) – Direct](products-template-mapping-direct.md).</span></span>

<span data-ttu-id="7caea-108">Questo argomento descrive solo le differenze tra i modelli **Prodotti Field Service (da Finance and Operations a Field Service)** e **Prodotti Field Service (da Finance and Operations a Field Service) - Diretto**.</span><span class="sxs-lookup"><span data-stu-id="7caea-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7caea-109">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="7caea-109">Templates and tasks</span></span>

<span data-ttu-id="7caea-110">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="7caea-110">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="7caea-111">Prodotti Field Service con unità di magazzino (da Finance and Operations a Sales)</span><span class="sxs-lookup"><span data-stu-id="7caea-111">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="7caea-112">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="7caea-112">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="7caea-113">Prodotti</span><span class="sxs-lookup"><span data-stu-id="7caea-113">Products</span></span>

<span data-ttu-id="7caea-114">Il modello **Prodotti Field Service con unità di magazzino (da Finance and Operations a Field Service)** include una mappatura che non è inclusa nel modello **Prodotti Field Service (da Finance and Operations a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="7caea-114">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="7caea-115">Questo mapping assicura l'inclusione dell'unità di magazzino necessaria per la sincronizzazione del livello delle scorte.</span><span class="sxs-lookup"><span data-stu-id="7caea-115">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7caea-116">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="7caea-116">Template mapping in Data integration</span></span>

<span data-ttu-id="7caea-117">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7caea-117">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="7caea-118">Prodotti Field Service con unità di magazzino (da Finance and Operations a Field Service): Prodotti</span><span class="sxs-lookup"><span data-stu-id="7caea-118">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="7caea-119">[![Mapping dei modelli in Integrazione dati](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="7caea-119">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
