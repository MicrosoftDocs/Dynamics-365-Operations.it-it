---
title: Sincronizzare prodotti con l'unità di magazzino da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2019
ms.locfileid: "836304"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="788d5-103">Sincronizzare i prodotti con l'unità di magazzino da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="788d5-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="788d5-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="788d5-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="788d5-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="788d5-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="788d5-106">Il modello **Prodotti Field Service con unità di magazzino (da Finance and Operations a Field Service)** utilizzato è basato sul modello **Prodotti Field Service (da Finance and Operations a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="788d5-106">The used **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template is based on the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="788d5-107">Per ulteriori informazioni, vedere [Prodotti Field Service (da Finance and Operations a Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="788d5-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="788d5-108">In questo argomento vengono descritte le differenze tra i due modelli:</span><span class="sxs-lookup"><span data-stu-id="788d5-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="788d5-109">**Prodotti Field Service con unità di magazzino (da Finance and Operations a Sales)**</span><span class="sxs-lookup"><span data-stu-id="788d5-109">**Field Service Products with Inventory unit (Finance and Operations to Sales)**</span></span>
- <span data-ttu-id="788d5-110">**Prodotti Field Service (da Finance and Operations a Field Service)**</span><span class="sxs-lookup"><span data-stu-id="788d5-110">**Field Service Products (Finance and Operations to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="788d5-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="788d5-111">Templates and tasks</span></span>

<span data-ttu-id="788d5-112">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="788d5-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="788d5-113">Prodotti Field Service con unità di magazzino (da Finance and Operations a Sales)</span><span class="sxs-lookup"><span data-stu-id="788d5-113">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="788d5-114">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="788d5-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="788d5-115">Prodotti</span><span class="sxs-lookup"><span data-stu-id="788d5-115">Products</span></span>

<span data-ttu-id="788d5-116">Il modello **Prodotti Field Service con unità di magazzino (da Finance and Operations a Field Service)** include una mappatura che non è inclusa nel modello **Prodotti Field Service (da Finance and Operations a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="788d5-116">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="788d5-117">Questo mapping assicura l'inclusione dell'unità di magazzino necessaria per la sincronizzazione del livello delle scorte.</span><span class="sxs-lookup"><span data-stu-id="788d5-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="788d5-118">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="788d5-118">Template mapping in Data integration</span></span>

<span data-ttu-id="788d5-119">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="788d5-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="788d5-120">Prodotti Field Service con unità di magazzino (da Finance and Operations a Field Service): Prodotti</span><span class="sxs-lookup"><span data-stu-id="788d5-120">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="788d5-121">[![Mapping dei modelli in Integrazione dati](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="788d5-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
