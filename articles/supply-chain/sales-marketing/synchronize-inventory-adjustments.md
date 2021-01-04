---
title: Sincronizzare i trasferimenti e le rettifiche delle scorte da Field Service a Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
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
ms.openlocfilehash: ff64f28af570b792f73b51aa9caf06dd2445b2ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431033"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="b61b4-103">Sincronizzare i trasferimenti e le rettifiche delle scorte da Field Service a Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b61b4-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b61b4-104">Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="b61b4-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="b61b4-105">[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="b61b4-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b61b4-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="b61b4-106">Templates and tasks</span></span>
<span data-ttu-id="b61b4-107">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i trasferimenti e le rettifiche delle scorte da Field Service a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b61b4-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="b61b4-108">**Modelli in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="b61b4-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="b61b4-109">Rettifica magazzino (da Field Service a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="b61b4-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="b61b4-110">Trasferimenti scorte (da Field Service a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="b61b4-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="b61b4-111">**Attività nei progetti di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="b61b4-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="b61b4-112">Rettifiche magazzino</span><span class="sxs-lookup"><span data-stu-id="b61b4-112">Inventory Adjustments</span></span>
- <span data-ttu-id="b61b4-113">Trasferimenti scorte</span><span class="sxs-lookup"><span data-stu-id="b61b4-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="b61b4-114">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="b61b4-114">Entity set</span></span>
| <span data-ttu-id="b61b4-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="b61b4-115">Field Service</span></span>                     | <span data-ttu-id="b61b4-116">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="b61b4-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="b61b4-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="b61b4-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="b61b4-118">Intestazioni e righe giornali di registrazione rettifica magazzino CDS</span><span class="sxs-lookup"><span data-stu-id="b61b4-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="b61b4-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="b61b4-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="b61b4-120">Intestazioni e righe giornali di registrazione trasferimento scorte CDS</span><span class="sxs-lookup"><span data-stu-id="b61b4-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="b61b4-121">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="b61b4-121">Entity flow</span></span>
<span data-ttu-id="b61b4-122">Le rettifiche di magazzino e i trasferimenti di scorte effettuati in Field Service saranno sincronizzati a Supply Chain Management dopo che l'impostazione di **Registra stato** passa da **Creato** a **Registrato**.</span><span class="sxs-lookup"><span data-stu-id="b61b4-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="b61b4-123">Quando ciò accade, la rettifica o l'ordine di trasferimento verrà chiuso e diventa di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b61b4-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="b61b4-124">Ciò significa che le rettifiche e i trasferimenti possono essere registrati in Supply Chain Management, ma non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="b61b4-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="b61b4-125">In Supply Chain Management, è possibile impostare un processo batch per registrare automaticamente le rettifiche e trasferire i giornali di registrazione magazzino generati durante l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="b61b4-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="b61b4-126">Vedere il prerequisito seguente per dettagli su come abilitare il processo batch.</span><span class="sxs-lookup"><span data-stu-id="b61b4-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="b61b4-127">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="b61b4-127">Field Service CRM solution</span></span> 
<span data-ttu-id="b61b4-128">Il campo **Unità di magazzino** è stato aggiunto all'entità **Prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b61b4-128">The **Inventory unit** field has been added to the **Product** entity.</span></span> <span data-ttu-id="b61b4-129">Questo campo è necessario in quanto l'unità di vendita e l'unità di magazzino non sono sempre uguali in Supply Chain Management e l'unità di magazzino è necessaria per le scorte di magazzino in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b61b4-129">This field is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="b61b4-130">Quando si imposta il prodotto su un prodotto di rettifica magazzino per le rettifiche di magazzino e i trasferimenti di scorte, l'unità verrà recuperata dal valore del prodotto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="b61b4-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="b61b4-131">Se viene rilevato un valore, il campo **Unità** verrà bloccato nel prodotto di rettifica magazzino.</span><span class="sxs-lookup"><span data-stu-id="b61b4-131">If a value is found, the **Unit** field will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="b61b4-132">Il campo **Registra stato** è stato aggiunto all'entità **Rettifica magazzino** e all'entità **Trasferimento scorte**.</span><span class="sxs-lookup"><span data-stu-id="b61b4-132">The **Post status** field has been added to both the **Inventory adjustment** entity and the **Inventory transfer** entity.</span></span> <span data-ttu-id="b61b4-133">Questo campo viene utilizzato come filtro quando una rettifica o un trasferimento viene inviato a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b61b4-133">This field is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="b61b4-134">Il valore predefinito di questo campo è Creato (1), ma non viene inviato a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b61b4-134">The default for this field is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="b61b4-135">Quando si imposta il valore su Registrato (2), si ha l'invio a Supply Chain Management, ma non sarà più possibile effettuare modifiche nella rettifica o nel trasferimento o aggiungere nuove righe.</span><span class="sxs-lookup"><span data-stu-id="b61b4-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="b61b4-136">Il campo **Sequenza numerica** è stato aggiunto all'entità **Prodotto di rettifica magazzino**.</span><span class="sxs-lookup"><span data-stu-id="b61b4-136">The **Number sequence** field has been added to the **Inventory adjustment product** entity.</span></span> <span data-ttu-id="b61b4-137">Questo campo assicura che l'integrazione ha un numero univoco, quindi l'integrazione può creare e aggiornare la rettifica.</span><span class="sxs-lookup"><span data-stu-id="b61b4-137">This field ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="b61b4-138">Quando si crea il primo prodotto di rettifica magazzino, viene creato un nuovo record nell'entità di **numerazione automatica Prospect to Cash** per gestire la serie di numeri e il prefisso utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b61b4-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="b61b4-139">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="b61b4-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="b61b4-140">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="b61b4-140">Supply Chain Management</span></span>
<span data-ttu-id="b61b4-141">I giornali di registrazione magazzino generati tramite l'integrazione possono essere registrati automaticamente mediante un processo batch.</span><span class="sxs-lookup"><span data-stu-id="b61b4-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="b61b4-142">A questo proposito, selezionare **Gestione inventario > Attività periodiche > Integrazione CDS > Registra giornali di registrazione magazzino integrazione**.</span><span class="sxs-lookup"><span data-stu-id="b61b4-142">This is enabled from **Inventory management > Periodic tasks > CDS integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b61b4-143">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="b61b4-143">Template mapping in Data integration</span></span>

<span data-ttu-id="b61b4-144">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="b61b4-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="b61b4-145">Rettifica magazzino (da Field Service a Supply Chain Management): Rettifica magazzino</span><span class="sxs-lookup"><span data-stu-id="b61b4-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="b61b4-146">[![Mapping dei modelli in Integrazione dati](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="b61b4-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="b61b4-147">Trasferimento scorte (da Field Service a Supply Chain Management ): Trasferimento scorte</span><span class="sxs-lookup"><span data-stu-id="b61b4-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="b61b4-148">[![Mapping dei modelli in Integrazione dati](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="b61b4-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
