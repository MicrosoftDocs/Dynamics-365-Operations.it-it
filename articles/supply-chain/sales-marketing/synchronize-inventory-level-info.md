---
title: Sincronizzare le informazioni sul livello di scorte da Supply Chain Management a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 1228339c12d26f7b91875d15f0daa8da2869cba0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431031"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a><span data-ttu-id="14b4c-103">Sincronizzare le informazioni sul livello di scorte da Supply Chain Management a Field Service</span><span class="sxs-lookup"><span data-stu-id="14b4c-103">Synchronize inventory level information from Supply Chain Management to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="14b4c-104">Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="14b4c-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="14b4c-105">[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="14b4c-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="14b4c-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="14b4c-106">Templates and tasks</span></span>
<span data-ttu-id="14b4c-107">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i livelli delle scorte disponibili da Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="14b4c-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="14b4c-108">**Modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="14b4c-108">**Template in Data integration**</span></span>
- <span data-ttu-id="14b4c-109">Inventario prodotti (da Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="14b4c-109">Product Inventory (Supply Chain Management to Field Service)</span></span>
  
<span data-ttu-id="14b4c-110">**Attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="14b4c-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="14b4c-111">Inventario prodotti</span><span class="sxs-lookup"><span data-stu-id="14b4c-111">Product inventory</span></span>

<span data-ttu-id="14b4c-112">Le attività di sincronizzazione seguenti sono necessarie per la sincronizzazione dei livelli delle scorte:</span><span class="sxs-lookup"><span data-stu-id="14b4c-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="14b4c-113">Magazzini (da Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="14b4c-113">Warehouses (Supply Chain Management to Field Service)</span></span> 
- <span data-ttu-id="14b4c-114">Prodotti Field Service con l'unità di magazzino (Supply Chain Management a Sales)</span><span class="sxs-lookup"><span data-stu-id="14b4c-114">Field Service products with Inventory unit (Supply Chain Management to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="14b4c-115">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="14b4c-115">Entity set</span></span>

| <span data-ttu-id="14b4c-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="14b4c-116">Field Service</span></span>                      | <span data-ttu-id="14b4c-117">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="14b4c-117">Supply Chain Management</span></span>                |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="14b4c-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="14b4c-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="14b4c-119">Disponibilità scorte in base al magazzino CDS</span><span class="sxs-lookup"><span data-stu-id="14b4c-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="14b4c-120">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="14b4c-120">Entity flow</span></span>
<span data-ttu-id="14b4c-121">Le informazioni sul livello delle scorte da Finance and Operations sono inviate a Field Service per i prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="14b4c-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="14b4c-122">Le informazioni sul livello delle scorte includono:</span><span class="sxs-lookup"><span data-stu-id="14b4c-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="14b4c-123">Quantità disponibile (quantità corrente fisica registrata presente nel magazzino)</span><span class="sxs-lookup"><span data-stu-id="14b4c-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="14b4c-124">Quantità in ordinazione (quantità registrata totale in odinazione, ad esempio ordini cliente)</span><span class="sxs-lookup"><span data-stu-id="14b4c-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="14b4c-125">Quantità ordinata (quantità ordinata registrata totale, ad esempio ordini fornitore)</span><span class="sxs-lookup"><span data-stu-id="14b4c-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="14b4c-126">Queste informazioni vengono acquisite per prodotto rilasciato per ogni magazzino e sincronizzate in base al rilevamento delle modifiche, quando il livello delle scorte cambia.</span><span class="sxs-lookup"><span data-stu-id="14b4c-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="14b4c-127">In Field Service, la soluzione di integrazione crea giornali di registrazione magazzino per il delta, di modo che i livelli in Field Service corrispondano a quelli in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="14b4c-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Supply Chain Management.</span></span>

<span data-ttu-id="14b4c-128">Supply Chain Management sarà il master per i livelli delle scorte.</span><span class="sxs-lookup"><span data-stu-id="14b4c-128">Supply Chain Management will act as the master for inventory levels.</span></span> <span data-ttu-id="14b4c-129">È quindi importante impostare l'integrazione per ordini di lavoro, trasferimenti e rettifiche da Field Service a Supply Chain Management se questa funzionalità è utilizzata in Field Service, insieme alla sincronizzazione dei livelli delle scorte da Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="14b4c-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Supply Chain Management if this functionality is used in Field Service, together with synchronization of inventory levels from Supply Chain Management.</span></span>

<span data-ttu-id="14b4c-130">I prodotti e i magazzini in cui i livelli delle scorte sono gestiti da Supply Chain Management possono essere controllati con Filtro e query avanzati (Power Query).</span><span class="sxs-lookup"><span data-stu-id="14b4c-130">The products and warehouses where inventory levels are mastered from Supply Chain Management can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="14b4c-131">È possibile creare più magazzini in Field Service (con **Gestito esternamente = No**) e quindi mapparli a un singolo magazzino in Supply Chain Management, con la funzionalità Filtro e query avanzati.</span><span class="sxs-lookup"><span data-stu-id="14b4c-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Supply Chain Management, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="14b4c-132">Questa soluzione è utilizzata in situazioni in cui Field Service deve gestire il livello delle scorte dettagliato e inviare aggiornamenti solo a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="14b4c-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Supply Chain Management.</span></span> <span data-ttu-id="14b4c-133">In questo caso Field Service non riceverà gli aggiornamenti del livello delle scorte da Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="14b4c-133">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="14b4c-134">Per ulteriori informazioni, vedere [Sincronizzare rettifiche di inventario da Field Service a Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente collegati a un progetto in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="14b4c-134">For additional information, see [Synchronize inventory adjustments from Field Service to Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="14b4c-135">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="14b4c-135">Field Service CRM solution</span></span>
<span data-ttu-id="14b4c-136">L'entità **Inventario prodotti esterno** è utilizzata solo per il backend nell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="14b4c-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="14b4c-137">Questa entità riceve i valori del livello delle scorte da Supply Chain Management nell'integrazione, trasforma tali valori in giornali di registrazione manuali, quindi modifica i prodotti di magazzino nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="14b4c-137">This entity receives the inventory level values from Supply Chain Management in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="14b4c-138">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="14b4c-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="14b4c-139">Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="14b4c-139">Data integration</span></span>
<span data-ttu-id="14b4c-140">Affinché il progetto funzioni, verificare che la chiave di integrazione sia aggiornata con msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="14b4c-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="14b4c-141">Passare a **Integrazione dati > Set di connessione**.</span><span class="sxs-lookup"><span data-stu-id="14b4c-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="14b4c-142">Selezionare il set di connessione utilizzato.</span><span class="sxs-lookup"><span data-stu-id="14b4c-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="14b4c-143">Nella scheda **Chiave di integrazione**, assicurarsi di aggiungere le seguenti chiavi a msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="14b4c-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="14b4c-144">msdynce_productnumber (numero prodotto)</span><span class="sxs-lookup"><span data-stu-id="14b4c-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="14b4c-145">msdynce_warehouseid (ID magazzino)</span><span class="sxs-lookup"><span data-stu-id="14b4c-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="14b4c-146">Progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="14b4c-146">Data integration project</span></span>
<span data-ttu-id="14b4c-147">È possibile applicare filtri con Filtro e query avanzati di modo che solo certi prodotti e magazzini inviino informazioni sul livello delle scorte da Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="14b4c-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Supply Chain Management to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="14b4c-148">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="14b4c-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a><span data-ttu-id="14b4c-149">Inventario prodotti (da Supply Chain Management a Field Service): Inventario prodotti</span><span class="sxs-lookup"><span data-stu-id="14b4c-149">Product inventory (Supply Chain Management to Field Service): Product inventory</span></span>

<span data-ttu-id="14b4c-150">[![Mapping dei modelli in Integrazione dati](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="14b4c-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
