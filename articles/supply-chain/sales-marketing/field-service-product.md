---
title: Sincronizzare i prodotti in Finance and Operations con i prodotti in Field Service
description: Questo argomento descrive i modelli e l'attività sottostante che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 06d7ff272ecb79abded3c3d3ade1f6bc0ef1f095
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742357"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="e5bd7-103">Sincronizzare prodotti in Finance and Operations con prodotti in Field Service</span><span class="sxs-lookup"><span data-stu-id="e5bd7-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e5bd7-104">Questo argomento descrive i modelli e l'attività sottostante che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="e5bd7-105">Il modello utilizzato **Prodotti Field Service (da Fin and Ops a Field Service)** si basa sul modello **Prodotti (da Fin and Ops a Sales) - Direct** da Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="e5bd7-106">Per ulteriori informazioni, vedere [Prodotti (da Fin and Ops a Sales) - Diretto](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="e5bd7-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="e5bd7-107">Questo argomenti descrive solo le differenze tra i modelli **Prodotti Field Service (da Fin and Ops a Field Service)** e **Prodotti (da Fin and Ops a Sales) - Diretto**.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e5bd7-108">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="e5bd7-108">Templates and tasks</span></span>

<span data-ttu-id="e5bd7-109">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="e5bd7-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="e5bd7-110">Prodotti Field Service (da Fin and Ops a Field Service)</span><span class="sxs-lookup"><span data-stu-id="e5bd7-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="e5bd7-111">**Nome dell'attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="e5bd7-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="e5bd7-112">Prodotti - Prodotti</span><span class="sxs-lookup"><span data-stu-id="e5bd7-112">Products - Products</span></span>

<span data-ttu-id="e5bd7-113">Il modello utilizzato **Prodotti Field Service (da Fin and Ops a Field Service)** include un mapping che non è incluso nel modello **Prodotti (da Fin and Ops a Sales) - Diretto**.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="e5bd7-114">Questo mapping assicura che il campo obbligatorio specifico di Field Service **Tipo di prodotto Field Service** sia impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="e5bd7-115">Viene utilizzato il seguente mapping di valori:</span><span class="sxs-lookup"><span data-stu-id="e5bd7-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="e5bd7-116">In Finance and Operations, il valore di **Tipo di prodotto Field Service** nell'entità di dati **Prodotti rilasciati di vendita** viene calcolato come segue:</span><span class="sxs-lookup"><span data-stu-id="e5bd7-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="e5bd7-117">**Magazzino:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = True</span><span class="sxs-lookup"><span data-stu-id="e5bd7-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="e5bd7-118">**Non scorte:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = False</span><span class="sxs-lookup"><span data-stu-id="e5bd7-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="e5bd7-119">**Assistenza:** Tipo di prodotto = Assistenza</span><span class="sxs-lookup"><span data-stu-id="e5bd7-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e5bd7-120">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="e5bd7-120">Template mapping in Data integration</span></span>

<span data-ttu-id="e5bd7-121">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a><span data-ttu-id="e5bd7-122">Prodotti Field Service (da Fin and Ops a Field Service): Prodotti - Prodotti</span><span class="sxs-lookup"><span data-stu-id="e5bd7-122">Field Service Products (Fin and Ops to Field Service): Products - Products</span></span>

<span data-ttu-id="e5bd7-123">[![Mapping dei modelli in Integrazione dati](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="e5bd7-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
