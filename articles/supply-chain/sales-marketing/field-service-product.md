---
title: Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service
description: Questo argomento descrive i modelli e l'attività sottostante che vengono utilizzati per sincronizzare i prodotti da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 45a989604d829db715756b6cd206a5675a18acf2
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909993"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="3939f-103">Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service</span><span class="sxs-lookup"><span data-stu-id="3939f-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3939f-104">Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare i prodotti da Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="3939f-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="3939f-105">Il modello utilizzato **Prodotti Field Service (da Supply Chain Management a Field Service)** si basa sul modello **Prodotti (da Supply Chain Management a Sales) - Diretto** di Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="3939f-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="3939f-106">Per ulteriori informazioni, vedere [Prodotti (da Supply Chain Management a Sales) - Diretto](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="3939f-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="3939f-107">Questo argomenti descrive solo le differenze tra i modelli **Prodotti Field Service (da Supply Chain Management a Field Service)** e **Prodotti (da Supply Chain Management a Sales) - Diretto**.</span><span class="sxs-lookup"><span data-stu-id="3939f-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="3939f-108">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="3939f-108">Templates and tasks</span></span>

<span data-ttu-id="3939f-109">**Nome del modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="3939f-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="3939f-110">Prodotti Field Service (da Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="3939f-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="3939f-111">**Nome dell'attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="3939f-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="3939f-112">Prodotti - Prodotti</span><span class="sxs-lookup"><span data-stu-id="3939f-112">Products - Products</span></span>

<span data-ttu-id="3939f-113">Il modello utilizzato **Prodotti Field Service (da Supply Chain Management a Field Service)** include un mapping che non è incluso nel modello **Prodotti (da Supply Chain Management a Sales) - Diretto**.</span><span class="sxs-lookup"><span data-stu-id="3939f-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="3939f-114">Questo mapping assicura che il campo obbligatorio specifico di Field Service **Tipo di prodotto Field Service** sia impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3939f-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="3939f-115">Viene utilizzato il seguente mapping di valori:</span><span class="sxs-lookup"><span data-stu-id="3939f-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="3939f-116">In Supply Chain Management, il valore di **Tipo di prodotto Field Service** nell'entità di dati **Prodotti rilasciati di vendita** viene calcolato come segue:</span><span class="sxs-lookup"><span data-stu-id="3939f-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="3939f-117">**Magazzino:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = True</span><span class="sxs-lookup"><span data-stu-id="3939f-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="3939f-118">**Non scorte:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = False</span><span class="sxs-lookup"><span data-stu-id="3939f-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="3939f-119">**Assistenza:** Tipo di prodotto = Assistenza</span><span class="sxs-lookup"><span data-stu-id="3939f-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="3939f-120">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="3939f-120">Template mapping in Data integration</span></span>

<span data-ttu-id="3939f-121">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="3939f-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="3939f-122">Prodotti Field Service (da Supply Chain Management a Field Service): Prodotti - Prodotti</span><span class="sxs-lookup"><span data-stu-id="3939f-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="3939f-123">[![Mapping dei modelli in Integrazione dati](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="3939f-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]