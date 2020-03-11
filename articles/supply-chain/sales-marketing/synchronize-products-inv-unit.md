---
title: Sincronizzare i prodotti con l'unità di magazzino da Supply Chain Management a Field Service
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 741b823d6cc5dbd23cda4f07e463f28d6bbe77d6
ms.sourcegitcommit: a2f9dce06322dada6b5f1c82051ef2359f8c0f12
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "3081866"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="1d494-103">Sincronizzare i prodotti con l'unità di magazzino da Supply Chain Management a Field Service</span><span class="sxs-lookup"><span data-stu-id="1d494-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1d494-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="1d494-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="1d494-105">[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="1d494-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="1d494-106">Il modello **Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service)** utilizzato è basato sul modello **Prodotti Field Service (da Supply Chain Management a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="1d494-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="1d494-107">Per ulteriori informazioni, vedere [Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="1d494-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="1d494-108">In questo argomento vengono descritte le differenze tra i due modelli:</span><span class="sxs-lookup"><span data-stu-id="1d494-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="1d494-109">**Prodotti Field Service con l'unità di magazzino (Supply Chain Management a Sales)**</span><span class="sxs-lookup"><span data-stu-id="1d494-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="1d494-110">**Prodotti Field Service (da Supply Chain Management a Field Service)**</span><span class="sxs-lookup"><span data-stu-id="1d494-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="1d494-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="1d494-111">Templates and tasks</span></span>

<span data-ttu-id="1d494-112">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="1d494-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="1d494-113">Prodotti Field Service con l'unità di magazzino (Supply Chain Management a Sales)</span><span class="sxs-lookup"><span data-stu-id="1d494-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="1d494-114">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="1d494-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="1d494-115">Prodotti</span><span class="sxs-lookup"><span data-stu-id="1d494-115">Products</span></span>

<span data-ttu-id="1d494-116">Il modello **Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service)** include un mapping che non è previsto nel modello **Prodotti Field Service (da Supply Chain Management a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="1d494-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Managementto Field Service)** template.</span></span> <span data-ttu-id="1d494-117">Questo mapping assicura l'inclusione dell'unità di magazzino necessaria per la sincronizzazione del livello delle scorte.</span><span class="sxs-lookup"><span data-stu-id="1d494-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```Text
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="1d494-118">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="1d494-118">Template mapping in Data integration</span></span>

<span data-ttu-id="1d494-119">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="1d494-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="1d494-120">Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service): Prodotti</span><span class="sxs-lookup"><span data-stu-id="1d494-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="1d494-121">[![Mapping dei modelli in Integrazione dati](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="1d494-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
