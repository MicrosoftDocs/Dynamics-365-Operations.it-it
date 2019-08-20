---
title: Sincronizzare ordini di lavoro con un progetto da Field Service a Finance and Operations
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 77358513ffdf791ab10d6efe1b84f598ffb5ec26
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843411"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Sincronizzare ordini di lavoro con un progetto da Field Service a Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare ordini di lavoro con un numero di progetto da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Il modello **Ordini di lavoro con progetto (da Field Service a Finance and Operations)** utilizzato si basa sul modello **Ordini di lavoro (da Field Service a Fin and Ops)**. Per ulteriori informazioni, vedere [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

In questo argomento vengono descritte le differenze tra i due modelli:
- **Ordini di lavoro con progetto (da Field Service a Fin and Ops)**
- **Ordini di lavoro (da Field Service a Fin and Ops)**

La differenza principale è che questo modello include il mapping del numero di progetto assegnato all'ordine di lavoro in Field Service, affinché l'ordine cliente creato in Finance and Operations includa il numero di progetto e che sia possibile eseguire la fatturazione nel progetto correlato. Inoltre, il modello utilizza la funzionalità Filtro e query avanzati.

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati:**

- Ordini di lavoro con progetto (da Field Service a Fin and Ops)

**Nome dell'attività nel progetto di Integrazione dati:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service
Il campo **Progetto esterno** è stato aggiunto all'entità Ordine di lavoro. Questo campo è un lookup and buy che contrassegna l'ordine di lavoro con un progetto; l'ordine cliente verrà quindi collegato a un progetto in Finance and Operations. Quando **Stato sistema** passa da Aperto - In corso (690,970,000) a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà possibile aggiungere, rimuovere o cambiare il valore.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a>Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderHeader

[![Mapping dei modelli in Integrazione dati](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a>Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderHeaderProject

[![Mapping dei modelli in Integrazione dati](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a>Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderProduct

[![Mapping dei modelli in Integrazione dati](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a>Ordini di lavoro con progetto (da Field Service a Fin and Ops): WorkOrderService

[![Mapping dei modelli in Integrazione dati](./media/FSWOP4.png)](./media/FSWOP4.png)
