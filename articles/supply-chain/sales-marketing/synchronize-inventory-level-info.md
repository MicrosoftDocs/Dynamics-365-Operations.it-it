---
title: Sincronizzare informazioni sul livello delle scorte da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: b81694f1ed56d8542de46203ac5faf5fae2b6645
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "356785"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="d981b-103">Sincronizzare le informazioni sul livello di scorte da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="d981b-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d981b-104">Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="d981b-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="d981b-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="d981b-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d981b-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="d981b-106">Templates and tasks</span></span>
<span data-ttu-id="d981b-107">Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare i livelli delle scorte disponibili da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="d981b-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="d981b-108">**Modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="d981b-108">**Template in Data integration**</span></span>
- <span data-ttu-id="d981b-109">Inventario prodotti (da Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="d981b-109">Product Inventory (Finance and Operations to Field Service)</span></span>
  
<span data-ttu-id="d981b-110">**Attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="d981b-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="d981b-111">Inventario prodotti</span><span class="sxs-lookup"><span data-stu-id="d981b-111">Product inventory</span></span>

<span data-ttu-id="d981b-112">Le attività di sincronizzazione seguenti sono necessarie per la sincronizzazione dei livelli delle scorte:</span><span class="sxs-lookup"><span data-stu-id="d981b-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="d981b-113">Magazzini (da Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="d981b-113">Warehouses (Finance and Operations to Field Service)</span></span> 
- <span data-ttu-id="d981b-114">Prodotti Field Service con unità di magazzino (da Finance and Operations a Sales)</span><span class="sxs-lookup"><span data-stu-id="d981b-114">Field Service products with Inventory unit (Finance and Operations to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="d981b-115">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="d981b-115">Entity set</span></span>

| <span data-ttu-id="d981b-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="d981b-116">Field Service</span></span>                      | <span data-ttu-id="d981b-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d981b-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="d981b-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="d981b-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="d981b-119">Disponibilità scorte in base al magazzino CDS</span><span class="sxs-lookup"><span data-stu-id="d981b-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="d981b-120">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="d981b-120">Entity flow</span></span>
<span data-ttu-id="d981b-121">Le informazioni sul livello delle scorte da Finance and Operations sono inviate a Field Service per i prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="d981b-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="d981b-122">Le informazioni sul livello delle scorte includono:</span><span class="sxs-lookup"><span data-stu-id="d981b-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="d981b-123">Quantità disponibile (quantità corrente fisica registrata presente nel magazzino)</span><span class="sxs-lookup"><span data-stu-id="d981b-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="d981b-124">Quantità in ordinazione (quantità registrata totale in odinazione, ad esempio ordini cliente)</span><span class="sxs-lookup"><span data-stu-id="d981b-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="d981b-125">Quantità ordinata (quantità ordinata registrata totale, ad esempio ordini fornitore)</span><span class="sxs-lookup"><span data-stu-id="d981b-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="d981b-126">Queste informazioni vengono acquisite per prodotto rilasciato per ogni magazzino e sincronizzate in base al rilevamento delle modifiche, quando il livello delle scorte cambia.</span><span class="sxs-lookup"><span data-stu-id="d981b-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="d981b-127">In Field Service, la soluzione di integrazione crea giornali di registrazione magazzino per il delta, di modo che i livelli in Field Service corrispondano a quelli in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d981b-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Finance and Operations.</span></span>

<span data-ttu-id="d981b-128">Finance and Operations sarà il master per i livelli delle scorte.</span><span class="sxs-lookup"><span data-stu-id="d981b-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="d981b-129">È quindi importante impostare l'integrazione per ordini di lavoro, trasferimenti e rettifiche da Field Service a Finance and Operations se questa funzionalità è utilizzata in Field Service, insieme alla sincronizzazione dei livelli delle scorte da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d981b-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Finance and Operations if this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="d981b-130">I prodotti e i magazzini in cui i livelli delle scorte sono gestiti da Finance and Operations possono essere controllati con Filtro e query avanzati (Power Query).</span><span class="sxs-lookup"><span data-stu-id="d981b-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="d981b-131">È possibile creare più magazzini in Field Service (con **Gestito esternamente = No**) e quindi mapparli a un singolo magazzino in Finance and Operations, con la funzionalità Filtro e query avanzati.</span><span class="sxs-lookup"><span data-stu-id="d981b-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="d981b-132">Questa soluzione è utilizzata in situazioni in cui Field Service deve gestire il livello delle scorte dettagliato e inviare aggiornamenti solo a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d981b-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Finance and Operations.</span></span> <span data-ttu-id="d981b-133">In questo caso Field Service non riceverà gli aggiornamenti del livello delle scorte da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d981b-133">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="d981b-134">Per ulteriori informazioni, vedere [Sincronizzare rettifiche di inventario da Field Service a Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente collegati a un progetto in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="d981b-134">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="d981b-135">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="d981b-135">Field Service CRM solution</span></span>
<span data-ttu-id="d981b-136">L'entità **Inventario prodotti esterno** è utilizzata solo per il backend nell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="d981b-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="d981b-137">Questa entità riceve i valori del livello delle scorte da Finance and Operations nell'integrazione, trasforma tali valori in giornali di registrazione manuali, quindi modifica i prodotti di magazzino nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="d981b-137">This entity receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="d981b-138">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="d981b-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration-project"></a><span data-ttu-id="d981b-139">Progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="d981b-139">Data integration project</span></span>
<span data-ttu-id="d981b-140">È possibile applicare filtri con Filtro e query avanzati di modo che solo certi prodotti e magazzini inviino informazioni sul livello delle scorte da Finance and Operations a Field Service.</span><span class="sxs-lookup"><span data-stu-id="d981b-140">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d981b-141">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="d981b-141">Template mapping in Data integration</span></span>

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a><span data-ttu-id="d981b-142">Inventario prodotti (da Field Service a Finance and Operations): Inventario prodotti</span><span class="sxs-lookup"><span data-stu-id="d981b-142">Product inventory (Finance and Operations to Field Service): Product inventory</span></span>

<span data-ttu-id="d981b-143">[![Mapping dei modelli in Integrazione dati](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="d981b-143">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>