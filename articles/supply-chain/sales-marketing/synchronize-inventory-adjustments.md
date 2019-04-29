---
title: Sincronizzare trasferimenti di scorte e rettifiche di magazzino da Field Service a Finance and Operations
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 75181661c41d238cdc06ffbb6969a2efd7d88d46
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "842417"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="e72d3-103">Sincronizzare rettifiche di magazzino da Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e72d3-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e72d3-104">Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="e72d3-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="e72d3-105">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="e72d3-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e72d3-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="e72d3-106">Templates and tasks</span></span>
<span data-ttu-id="e72d3-107">Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Microsoft Dynamics 365 for Field Service in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e72d3-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="e72d3-108">**Modelli in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="e72d3-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="e72d3-109">Rettifica magazzino (da Field Service a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="e72d3-109">Inventory Adjustment (Field Service to Fin and Ops)</span></span>
- <span data-ttu-id="e72d3-110">Trasferimenti scorte (da Field Service a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="e72d3-110">Inventory Transfers (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="e72d3-111">**Attività nei progetti di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="e72d3-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="e72d3-112">Rettifiche magazzino</span><span class="sxs-lookup"><span data-stu-id="e72d3-112">Inventory Adjustments</span></span>
- <span data-ttu-id="e72d3-113">Trasferimenti scorte</span><span class="sxs-lookup"><span data-stu-id="e72d3-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="e72d3-114">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="e72d3-114">Entity set</span></span>
| <span data-ttu-id="e72d3-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="e72d3-115">Field Service</span></span>                     | <span data-ttu-id="e72d3-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e72d3-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="e72d3-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="e72d3-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="e72d3-118">Intestazioni e righe giornali di registrazione rettifica magazzino CDS</span><span class="sxs-lookup"><span data-stu-id="e72d3-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="e72d3-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="e72d3-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="e72d3-120">Intestazioni e righe giornali di registrazione trasferimento scorte CDS</span><span class="sxs-lookup"><span data-stu-id="e72d3-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="e72d3-121">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="e72d3-121">Entity flow</span></span>
<span data-ttu-id="e72d3-122">Le rettifiche di magazzino e i trasferimenti di scorte effettuati in Field Service saranno sincronizzati a Finance and Operations dopo che l'impostazione di **Registra stato** passa da **Creato** a **Registrato**.</span><span class="sxs-lookup"><span data-stu-id="e72d3-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="e72d3-123">Quando ciò accade, la rettifica o l'ordine di trasferimento verrà chiuso e diventa di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e72d3-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="e72d3-124">Ciò significa che le rettifiche e i trasferimenti possono essere registrati in Finance and Operations, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="e72d3-124">This means that adjustments and transfers can be posted in Finance and Operations, but cannot be modified.</span></span> <span data-ttu-id="e72d3-125">In Finance and Operations, è possibile impostare un processo batch per registrare automaticamente le rettifiche e trasferire i giornali di registrazione magazzino generati durante l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="e72d3-125">In Finance and Operations, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="e72d3-126">Vedere il prerequisito seguente per dettagli su come abilitare il processo batch.</span><span class="sxs-lookup"><span data-stu-id="e72d3-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="e72d3-127">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="e72d3-127">Field Service CRM solution</span></span> 
<span data-ttu-id="e72d3-128">Il campo **Unità di magazzino** è stato aggiunto all'entità **Prodotto**.</span><span class="sxs-lookup"><span data-stu-id="e72d3-128">The **Inventory unit** field has been added to the **Product** entity.</span></span> <span data-ttu-id="e72d3-129">Questo campo è necessario in quanto l'unità di vendita e l'unità di magazzino non sono sempre uguali in Finance and Operations e l'unità di magazzino è necessaria per le scorte di magazzino in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e72d3-129">This field is needed because the Sales and Inventory unit is not always the same in Finance and Operations, and the Inventory Unit is needed for the Warehouse Inventory in Finance and Operations.</span></span>
<span data-ttu-id="e72d3-130">Quando si imposta il prodotto su un prodotto di rettifica magazzino per le rettifiche di magazzino e i trasferimenti di scorte, l'unità verrà recuperata dal valore del prodotto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="e72d3-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="e72d3-131">Se viene rilevato un valore, il campo **Unità** verrà bloccato nel prodotto di rettifica magazzino.</span><span class="sxs-lookup"><span data-stu-id="e72d3-131">If a value is found, the **Unit** field will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="e72d3-132">Il campo **Registra stato** è stato aggiunto all'entità **Rettifica magazzino** e all'entità **Trasferimento scorte**.</span><span class="sxs-lookup"><span data-stu-id="e72d3-132">The **Post status** field has been added to both the **Inventory adjustment** entity and the **Inventory transfer** entity.</span></span> <span data-ttu-id="e72d3-133">Questo campo viene utilizzato come filtro quando una rettifica o un trasferimento viene inviato a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e72d3-133">This field is used as a filter when an adjustment or transfer is sent to Finance and Operations.</span></span> <span data-ttu-id="e72d3-134">Il valore predefinito di questo campo è Creato (1), ma non viene inviato a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e72d3-134">The default for this field is Created (1), however it is not sent to Finance and Operations.</span></span> <span data-ttu-id="e72d3-135">Quando si imposta il valore su Registrato (2), si ha l'invio a Finance and Operations, ma non sarà più possibile effettuare modifiche nella rettifica o nel trasferimento o aggiungere nuove righe.</span><span class="sxs-lookup"><span data-stu-id="e72d3-135">When you update the value to Posted (2), it is sent to Finance and Operations, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="e72d3-136">Il campo **Sequenza numerica** è stato aggiunto all'entità **Prodotto di rettifica magazzino**.</span><span class="sxs-lookup"><span data-stu-id="e72d3-136">The **Number sequence** field has been added to the **Inventory adjustment product** entity.</span></span> <span data-ttu-id="e72d3-137">Questo campo assicura che l'integrazione ha un numero univoco, quindi l'integrazione può creare e aggiornare la rettifica.</span><span class="sxs-lookup"><span data-stu-id="e72d3-137">This field ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="e72d3-138">Quando si crea il primo prodotto di rettifica magazzino, viene creato un nuovo record nell'entità di **numerazione automatica Prospect to Cash** per gestire la serie di numeri e il prefisso utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e72d3-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="e72d3-139">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="e72d3-139">Prerequisites and mapping setup</span></span>

### <a name="finance-and-operations"></a><span data-ttu-id="e72d3-140">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e72d3-140">Finance and Operations</span></span>
<span data-ttu-id="e72d3-141">I giornali di registrazione magazzino generati tramite l'integrazione possono essere registrati automaticamente mediante un processo batch.</span><span class="sxs-lookup"><span data-stu-id="e72d3-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="e72d3-142">A questo proposito, selezionare **Gestione inventario > Attività periodiche > Integrazione CDS > Registra giornali di registrazione magazzino integrazione**.</span><span class="sxs-lookup"><span data-stu-id="e72d3-142">This is enabled from **Inventory management > Periodic tasks > CDS integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e72d3-143">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="e72d3-143">Template mapping in Data integration</span></span>

<span data-ttu-id="e72d3-144">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="e72d3-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a><span data-ttu-id="e72d3-145">Rettifica magazzino (da Field Service a Fin and Ops): Rettifica magazzino</span><span class="sxs-lookup"><span data-stu-id="e72d3-145">Inventory adjustment (Field Service to Fin and Ops): Inventory adjustment</span></span>

<span data-ttu-id="e72d3-146">[![Mapping dei modelli in Integrazione dati](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="e72d3-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a><span data-ttu-id="e72d3-147">Trasferimento scorte (da Field Service a Fin and Ops): Trasferimento scorte</span><span class="sxs-lookup"><span data-stu-id="e72d3-147">Inventory transfer (Field Service to Fin and Ops): Inventory transfer</span></span>

<span data-ttu-id="e72d3-148">[![Mapping dei modelli in Integrazione dati](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="e72d3-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
