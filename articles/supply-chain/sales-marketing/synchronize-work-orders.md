---
title: Sincronizzare gli ordini di lavoro con il progetto da Field Service a Supply Chain Management
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Dynamics 365 Field Service a Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 03/12/2019
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
ms.openlocfilehash: 5ebf23c5c831e9dad5d13c72f82eb3eeb30da853
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430957"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Sincronizzare gli ordini di lavoro con il progetto da Field Service a Supply Chain Management

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Dynamics 365 Field Service a Dynamics 365 Supply Chain Management.

[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Il modello **Ordini di lavoro con progetto (da Field Service a Supply Chain Management)** utilizzato si basa sul modello **Ordini di lavoro (da Field Service a Supply Chain Management)**. Per ulteriori informazioni, vedere [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

In questo argomento vengono descritte le differenze tra i due modelli:
- **Ordini di lavoro con progetto (da Field Service a Supply Chain Management)**
- **Ordini di lavoro (da Field Service a Supply Chain Management)**

La differenza principale è che questo modello include il mapping del numero di progetto assegnato all'ordine di lavoro in Field Service, affinché l'ordine cliente creato in Supply Chain Management includa il numero di progetto e che sia possibile eseguire la fatturazione nel progetto correlato. Inoltre, il modello utilizza la funzionalità Filtro e query avanzati.

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati:**

- Ordini di lavoro con progetto (da Field Service a Supply Chain Management)

**Nome dell'attività nel progetto di Integrazione dati:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service
Il campo **Progetto esterno** è stato aggiunto all'entità Ordine di lavoro. Questo campo è un lookup and buy che contrassegna l'ordine di lavoro con un progetto; l'ordine cliente verrà quindi collegato a un progetto in Supply Chain Management. Quando **Stato sistema** passa da Aperto - In corso (690.970.000) a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà possibile aggiungere, rimuovere o cambiare il valore.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>Ordini di lavoro con progetto (da Field Service a Supply Chain Management): WorkOrderHeader

[![Mapping dei modelli in Integrazione dati](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Ordini di lavoro con progetto (da Field Service a Supply Chain Management): WorkOrderHeaderProject

[![Mapping dei modelli in Integrazione dati](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Ordini di lavoro con progetto (da Field Service a Supply Chain Management): WorkOrderProduct

[![Mapping dei modelli in Integrazione dati](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Ordini di lavoro con progetto (da Field Service a Supply Chain Management): WorkOrderService

[![Mapping dei modelli in Integrazione dati](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]