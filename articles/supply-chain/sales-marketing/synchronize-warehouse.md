---
title: Sincronizzare magazzini da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 7e6d7626c00b9d7d98ce872652653c36ce7bc975
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "842535"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Sincronizzare i magazzini da Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare magazzini da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

**Modello in Integrazione dati**
- Magazzini (da Fin and Ops a Field Service)

**Attività nel progetto di Integrazione dati**
- Magazzino

## <a name="entity-set"></a>Insieme di entità
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Magazzini                             |

## <a name="entity-flow"></a>Flusso di entità
I magazzini creati e gestiti in Finance and Operations possono essere sincronizzati a Field Service via un progetto di integrazione dei dati CDS (Common Data Service). I magazzini che si intende sincronizzare a Field Service possono essere controllati con la funzionalità Filtro e query avanzati nel progetto. I magazzini sincronizzati da Finance and Operations vengono creati in Field Service con il campo **Gestito esternamente** impostato su **Sì** e il record diventa di sola lettura.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service
Per supportare l'integrazione tra Field Service and Finance e Operations, sono richieste delle funzionalità aggiuntive nella soluzione CRM Field Service. Nella soluzione, il campo **Gestito esternamente** è stato aggiunto all'entità **Magazzino (msdyn_warehouses)**. Questo campo consente di identificare se il magazzino è gestito da Finance and Operations o se esiste solo in Field Service. Le impostazioni per questo campo sono:
- **Sì** - Il magazzino deriva da Finance and Operations e non sarà modificabile in Sales.
- **No** – Il magazzino è stato immesso direttamente in Field Service e gestito qui.

Il campo **Gestito esternamente** consente di controllare la sincronizzazione di livelli di scorte, rettifiche, trasferimenti e utilizzo negli ordini di lavoro. Solo i magazzini con **Gestito esternamente** impostato su **Sì** possono essere utilizzati per la sincronizzazione direttamente allo stesso magazzino nell'altro sistema. 

> [!NOTE]
> È possibile creare più magazzini in Field Service (con **Gestito esternamente** = No) e quindi mapparli a un singolo magazzino in Finance and Operations, con la funzionalità Filtro e query avanzati. Questa soluzione è utilizzata in situazioni in cui Field Service deve gestire il livello delle scorte dettagliato e inviare aggiornamenti a Finance and Operations. In questo caso Field Service non riceverà gli aggiornamenti del livello delle scorte da Finance and Operations. Per ulteriori informazioni, vedere [Sincronizzare rettifiche di inventario da Field Service a Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente collegati a un progetto in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping
### <a name="data-integration-project"></a>Progetto di Integrazione dati
Prima della sincronizzazione dei magazzini, assicurarsi di aggiornare la funzionalità Filtro e query avanzati nel progetto per includere solo i magazzini che si desidera spostare da Finance and Operations in Field Service. Da notare che il magazzino deve essere in Field Service per essere applicato a ordini di lavoro, rettifiche e trasferimenti.  

Per accertarsi che **Chiave di integrazione** esiste per **msdyn_workorders**:
1. Andare a Integrazione dati.
2. Selezionare la scheda **Insieme di connessione**.
3. Selezionare l'insieme di connessione utilizzato per la sincronizzazione dell'ordine di lavoro.
4. Selezionare la scheda **Chiave di integrazione**.
5. Trovare msdyn_workorders e confermare che la chiave **msdyn_name (nome)** è stata aggiunta. Se non è visualizzata, aggiungerla facendo clic su **Aggiungi chiave** e quindi su **Salva** nella parte superiore della pagina.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nella figura seguente viene illustrato il mapping di modelli in Integrazione dati.

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a>Magazzini (da Fin and Ops a Field Service): Magazzino

[![Mapping dei modelli in Integrazione dati](./media/Warehouse1.png)](./media/Warehouse1.png)
