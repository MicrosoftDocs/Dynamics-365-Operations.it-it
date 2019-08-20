---
title: Sincronizzare prodotti con l'unità di magazzino da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 78e8d8fa609b015cf2fceaf498279fe091325dbb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835696"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="77b4a-103">Sincronizzare i prodotti con l'unità di magazzino da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="77b4a-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="77b4a-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="77b4a-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="77b4a-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="77b4a-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="77b4a-106">Il modello **Prodotti Field Service con unità di magazzino (da Fin and Ops a Field Service)** utilizzato è basato sul modello **Prodotti Field Service (da Fin and Ops a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="77b4a-106">The used **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template is based on the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="77b4a-107">Per ulteriori informazioni, vedere [Prodotti Field Service (da Finance and Operations a Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="77b4a-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="77b4a-108">In questo argomento vengono descritte le differenze tra i due modelli:</span><span class="sxs-lookup"><span data-stu-id="77b4a-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="77b4a-109">**Prodotti Field Service con unità di magazzino (da Fin and Ops a Sales)**</span><span class="sxs-lookup"><span data-stu-id="77b4a-109">**Field Service Products with Inventory unit (Fin and Ops to Sales)**</span></span>
- <span data-ttu-id="77b4a-110">**Prodotti Field Service (da Fin and Ops a Field Service)**</span><span class="sxs-lookup"><span data-stu-id="77b4a-110">**Field Service Products (Fin and Ops to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="77b4a-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="77b4a-111">Templates and tasks</span></span>

<span data-ttu-id="77b4a-112">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="77b4a-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="77b4a-113">Prodotti Field Service con unità di magazzino (da Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="77b4a-113">Field Service Products with Inventory unit (Fin and Ops to Sales)</span></span>

<span data-ttu-id="77b4a-114">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="77b4a-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="77b4a-115">Prodotti</span><span class="sxs-lookup"><span data-stu-id="77b4a-115">Products</span></span>

<span data-ttu-id="77b4a-116">Il modello **Prodotti Field Service con unità di magazzino (da Fin and Ops a Field Service)** include una mappatura che non è inclusa nel modello **Prodotti Field Service (da Fin and Ops a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="77b4a-116">The **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="77b4a-117">Questo mapping assicura l'inclusione dell'unità di magazzino necessaria per la sincronizzazione del livello delle scorte.</span><span class="sxs-lookup"><span data-stu-id="77b4a-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="77b4a-118">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="77b4a-118">Template mapping in Data integration</span></span>

<span data-ttu-id="77b4a-119">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="77b4a-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-fin-and-ops-to-field-service-products"></a><span data-ttu-id="77b4a-120">Prodotti Field Service con unità di magazzino (da Fin and Ops a Field Service): Prodotti</span><span class="sxs-lookup"><span data-stu-id="77b4a-120">Field Service Products with Inventory unit (Fin and Ops to Field Service): Products</span></span>

<span data-ttu-id="77b4a-121">[![Mapping dei modelli in Integrazione dati](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="77b4a-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
