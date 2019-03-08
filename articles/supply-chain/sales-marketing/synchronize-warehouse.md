---
title: Sincronizzare magazzini da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 34cd18a18715d12d4002e6dbeee047467ed2a5ad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "340317"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="7838a-103">Sincronizzare i magazzini da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="7838a-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7838a-104">Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="7838a-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="7838a-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="7838a-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7838a-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="7838a-106">Templates and tasks</span></span>
<span data-ttu-id="7838a-107">Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="7838a-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="7838a-108">**Modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="7838a-108">**Template in Data integration**</span></span>
- <span data-ttu-id="7838a-109">Magazzini (da Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="7838a-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="7838a-110">**Attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="7838a-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="7838a-111">Magazzino</span><span class="sxs-lookup"><span data-stu-id="7838a-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="7838a-112">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="7838a-112">Entity set</span></span>
| <span data-ttu-id="7838a-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="7838a-113">Field Service</span></span>    | <span data-ttu-id="7838a-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7838a-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="7838a-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="7838a-115">msdyn_warehouses</span></span> | <span data-ttu-id="7838a-116">Magazzini</span><span class="sxs-lookup"><span data-stu-id="7838a-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="7838a-117">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="7838a-117">Entity flow</span></span>
<span data-ttu-id="7838a-118">I magazzini creati e gestiti in Finance and Operations possono essere sincronizzati a Field Service via un progetto di integrazione dei dati CDS (Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="7838a-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="7838a-119">I magazzini che si intende sincronizzare a Field Service possono essere controllati con la funzionalità Filtro e query avanzati nel progetto.</span><span class="sxs-lookup"><span data-stu-id="7838a-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="7838a-120">I magazzini sincronizzati da Finance and Operations vengono creati in Field Service con il campo **Gestito esternamente** impostato su **Sì** e il record diventa di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="7838a-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="7838a-121">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="7838a-121">Field Service CRM solution</span></span>
<span data-ttu-id="7838a-122">Per supportare l'integrazione tra Field Service and Finance e Operations, sono richieste delle funzionalità aggiuntive nella soluzione CRM Field Service.</span><span class="sxs-lookup"><span data-stu-id="7838a-122">To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="7838a-123">Nella soluzione, il campo **Gestito esternamente** è stato aggiunto all'entità **Magazzino (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="7838a-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="7838a-124">Questo campo consente di identificare se il magazzino è gestito da Finance and Operations o se esiste solo in Field Service.</span><span class="sxs-lookup"><span data-stu-id="7838a-124">This field helps to identify if the warehouse is handled from Finance and Operations or if it only exists in Field Service.</span></span> <span data-ttu-id="7838a-125">Le impostazioni per questo campo sono:</span><span class="sxs-lookup"><span data-stu-id="7838a-125">The settings for this field include:</span></span>
- <span data-ttu-id="7838a-126">**Sì** - Il magazzino deriva da Finance and Operations e non sarà modificabile in Sales.</span><span class="sxs-lookup"><span data-stu-id="7838a-126">**Yes** – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="7838a-127">**No** – Il magazzino è stato immesso direttamente in Field Service e gestito qui.</span><span class="sxs-lookup"><span data-stu-id="7838a-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="7838a-128">Il campo **Gestito esternamente** consente di controllare la sincronizzazione di livelli di scorte, rettifiche, trasferimenti e utilizzo negli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7838a-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="7838a-129">Solo i magazzini con **Gestito esternamente** impostato su **Sì** possono essere utilizzati per la sincronizzazione direttamente allo stesso magazzino nell'altro sistema.</span><span class="sxs-lookup"><span data-stu-id="7838a-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="7838a-130">È possibile creare più magazzini in Field Service (con **Gestito esternamente** = No) e quindi mapparli a un singolo magazzino in Finance and Operations, con la funzionalità Filtro e query avanzati.</span><span class="sxs-lookup"><span data-stu-id="7838a-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="7838a-131">Questa soluzione è utilizzata in situazioni in cui Field Service deve gestire il livello delle scorte dettagliato e inviare aggiornamenti a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7838a-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="7838a-132">In questo caso Field Service non riceverà gli aggiornamenti del livello delle scorte da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7838a-132">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="7838a-133">Per ulteriori informazioni, vedere [Sincronizzare rettifiche di inventario da Field Service a Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente collegati a un progetto in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="7838a-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="7838a-134">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="7838a-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="7838a-135">Progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="7838a-135">Data Integration project</span></span>
<span data-ttu-id="7838a-136">Prima della sincronizzazione dei magazzini, assicurarsi di aggiornare la funzionalità Filtro e query avanzati nel progetto per includere solo i magazzini che si desidera spostare da Finance and Operations in Field Service.</span><span class="sxs-lookup"><span data-stu-id="7838a-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="7838a-137">Da notare che il magazzino deve essere in Field Service per essere applicato a ordini di lavoro, rettifiche e trasferimenti.</span><span class="sxs-lookup"><span data-stu-id="7838a-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="7838a-138">Per accertarsi che **Chiave di integrazione** esiste per **msdyn_workorders**:</span><span class="sxs-lookup"><span data-stu-id="7838a-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="7838a-139">Andare a Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7838a-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="7838a-140">Selezionare la scheda **Insieme di connessione**.</span><span class="sxs-lookup"><span data-stu-id="7838a-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="7838a-141">Selezionare l'insieme di connessione utilizzato per la sincronizzazione dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7838a-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="7838a-142">Selezionare la scheda **Chiave di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="7838a-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="7838a-143">Trovare msdyn_workorders e confermare che la chiave **msdyn_name (nome)** è stata aggiunta.</span><span class="sxs-lookup"><span data-stu-id="7838a-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="7838a-144">Se non è visualizzata, aggiungerla facendo clic su **Aggiungi chiave** e quindi su **Salva** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="7838a-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7838a-145">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="7838a-145">Template mapping in Data integration</span></span>

<span data-ttu-id="7838a-146">Nella figura seguente viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7838a-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="7838a-147">Magazzini (da Finance and Operations a Field Service): Magazzino</span><span class="sxs-lookup"><span data-stu-id="7838a-147">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="7838a-148">[![Mapping dei modelli in Integrazione dati](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="7838a-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
