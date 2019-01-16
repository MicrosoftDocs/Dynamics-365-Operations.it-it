---
title: Sincronizzare magazzini da Finance and Operations a Field Service
description: "Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: it-it
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="b36e0-103">Sincronizzare magazzini da Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="b36e0-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b36e0-104">Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="b36e0-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="b36e0-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="b36e0-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b36e0-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="b36e0-106">Templates and tasks</span></span>
<span data-ttu-id="b36e0-107">Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="b36e0-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="b36e0-108">**Nome del modello in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="b36e0-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="b36e0-109">Magazzini (da Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="b36e0-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="b36e0-110">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="b36e0-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="b36e0-111">Magazzino</span><span class="sxs-lookup"><span data-stu-id="b36e0-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="b36e0-112">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="b36e0-112">Entity set</span></span>
| <span data-ttu-id="b36e0-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="b36e0-113">Field Service</span></span>    | <span data-ttu-id="b36e0-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b36e0-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="b36e0-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="b36e0-115">msdyn_warehouses</span></span> | <span data-ttu-id="b36e0-116">Magazzini</span><span class="sxs-lookup"><span data-stu-id="b36e0-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="b36e0-117">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="b36e0-117">Entity flow</span></span>
<span data-ttu-id="b36e0-118">I magazzini creati e gestiti in Finance and Operations possono essere sincronizzati a Field Service via un progetto di integrazione dei dati CDS (Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="b36e0-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="b36e0-119">I magazzini desiderati che vengono sincronizzati a Field Service possono essere controllati con la funzionalità Filtro e query avanzati nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b36e0-119">The desired warehouses that synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="b36e0-120">I magazzini sincronizzati da Finance and Operations vengono creati in Field Service con il campo Gestito esternamente impostato su Sì e il record diventa di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b36e0-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the field Is maintained externally set to Yes and the record is made read only.</span></span>
<span data-ttu-id="b36e0-121">Soluzione CRM Field Service Per supportare l'integrazione tra Field Service e Finance and Operations, sono necessarie funzionalità aggiuntive della soluzione CRM Field Service.</span><span class="sxs-lookup"><span data-stu-id="b36e0-121">Field Service CRM solution To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="b36e0-122">La soluzione include le modifiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="b36e0-122">The solution includes the following changes.</span></span>
<span data-ttu-id="b36e0-123">Il campo **Gestito esternamente** è stato aggiunto all'entità **Magazzino (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="b36e0-123">The field **Is Maintained Externally** has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="b36e0-124">Questo campo consente di identificare se il magazzino è gestito da Operations o se esiste solo in Field Service.</span><span class="sxs-lookup"><span data-stu-id="b36e0-124">This field helps to identify If the Warehouse is handled from Operations or if It only exists in Field Service.</span></span>
- <span data-ttu-id="b36e0-125">Sì - Il magazzino deriva da Finance and Operations e non sarà modificabile in Sales.</span><span class="sxs-lookup"><span data-stu-id="b36e0-125">Yes – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="b36e0-126">No – Il magazzino è stato immesso direttamente in Field Service e gestito qui.</span><span class="sxs-lookup"><span data-stu-id="b36e0-126">No – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="b36e0-127">Il campo **Gestito esternamente** consente di controllare la sincronizzazione di livelli di scorte, rettifiche, trasferimenti e utilizzo negli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b36e0-127">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers and usage on work orders.</span></span> <span data-ttu-id="b36e0-128">Solo i magazzini con **Gestito esternamente** = Sì possono essere utilizzati per la sincronizzazione direttamente allo stesso magazzino nell'altro sistema.</span><span class="sxs-lookup"><span data-stu-id="b36e0-128">Only warehouses with **Is Externally Maintained** = Yes can be used to synchronize directly to the same warehouse in the other system.</span></span> 

<span data-ttu-id="b36e0-129">Nota: è possibile creare più magazzini in Field Service (con **Gestito esternamente** = No) e quindi mapparli a un singolo magazzino in Finance and Operations, con la funzionalità Filtro e query avanzati.</span><span class="sxs-lookup"><span data-stu-id="b36e0-129">Note: It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="b36e0-130">Questa soluzione è utilizzata in situazioni in cui Field Service deve gestire il livello delle scorte dettagliato e inviare aggiornamenti a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b36e0-130">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="b36e0-131">In questo caso Field Service non riceverà gli aggiornamenti del livello delle scorte da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b36e0-131">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="b36e0-132">Vedere ulteriori informazioni in Sincronizzare rettifiche di inventario da Field Service a Finance and Operations e Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente collegati a un progetto in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b36e0-132">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="b36e0-133">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="b36e0-133">Prerequisites and mapping setup</span></span>
### <a name="in-the-data-integration-project"></a><span data-ttu-id="b36e0-134">Nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="b36e0-134">In the Data Integration project</span></span>
<span data-ttu-id="b36e0-135">Prima della sincronizzazione dei magazzini, assicurarsi di aggiornare la funzionalità Filtro e query avanzati nel progetto per includere solo i magazzini che si desidera spostare da Finance and Operations in Field Service.</span><span class="sxs-lookup"><span data-stu-id="b36e0-135">Before synchronization of the warehouses make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="b36e0-136">Da notare che il magazzino deve essere in Field Service per essere applicato a ordini di lavoro, rettifiche e trasferimenti.</span><span class="sxs-lookup"><span data-stu-id="b36e0-136">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments and transfers.</span></span>  

<span data-ttu-id="b36e0-137">Assicurarsi che **Chiave di integrazione** esista per **msdyn_workorders**</span><span class="sxs-lookup"><span data-stu-id="b36e0-137">Ensure the **Integration key** exist for **msdyn_warehouses**</span></span>
1. <span data-ttu-id="b36e0-138">Andare a Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="b36e0-138">Go to Data Integration</span></span>
2. <span data-ttu-id="b36e0-139">Selezionare la scheda **Insieme di connessioneµµµ**</span><span class="sxs-lookup"><span data-stu-id="b36e0-139">Select **Connection Set** tab</span></span>
3. <span data-ttu-id="b36e0-140">Selezionare l'insieme di connessione utilizzato per Sincronizzazione ordine di lavoroµµµ</span><span class="sxs-lookup"><span data-stu-id="b36e0-140">Select the Connection set used for Work order synchronization</span></span>
4. <span data-ttu-id="b36e0-141">Selezionare la scheda **Chiave di integrazione**</span><span class="sxs-lookup"><span data-stu-id="b36e0-141">Select **Integration key** tab</span></span>
5. <span data-ttu-id="b36e0-142">Trovare msdyn_workorders e verificare che la chiave **msdyn_name (nome)** sia stata aggiunta.</span><span class="sxs-lookup"><span data-stu-id="b36e0-142">Find msdyn_warehouses and check that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="b36e0-143">Se non è visualizzata, aggiungerla facendo clic su **Aggiungi chiave**µµµ e su **Salva** nella parte superiore della pagina</span><span class="sxs-lookup"><span data-stu-id="b36e0-143">If it is not shown, add it by click **Add key** and click **Save** in the top of the page</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b36e0-144">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="b36e0-144">Template mapping in Data integration</span></span>

<span data-ttu-id="b36e0-145">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="b36e0-145">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="b36e0-146">Magazzini (da Finance and Operations a Field Service): Magazzino</span><span class="sxs-lookup"><span data-stu-id="b36e0-146">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="b36e0-147">[![Mapping dei modelli in Integrazione dati](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="b36e0-147">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>

