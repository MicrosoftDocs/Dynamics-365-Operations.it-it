---
title: Sincronizzare prodotti con l'unità di magazzino da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 080672b9a6acd9fd6137580b5b7e14d12cfccf19
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1535861"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Sincronizzare i prodotti con l'unità di magazzino da Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Il modello **Prodotti Field Service con unità di magazzino (da Fin and Ops a Field Service)** utilizzato è basato sul modello **Prodotti Field Service (da Fin and Ops a Field Service)**. Per ulteriori informazioni, vedere [Prodotti Field Service (da Finance and Operations a Field Service)](field-service-product.md).

In questo argomento vengono descritte le differenze tra i due modelli: 
- **Prodotti Field Service con unità di magazzino (da Fin and Ops a Sales)**
- **Prodotti Field Service (da Fin and Ops a Field Service)** 

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati:**

- Prodotti Field Service con unità di magazzino (da Fin and Ops a Sales)

**Nome dell'attività nel progetto di Integrazione dati:**

- Prodotti

Il modello **Prodotti Field Service con unità di magazzino (da Fin and Ops a Field Service)** include una mappatura che non è inclusa nel modello **Prodotti Field Service (da Fin and Ops a Field Service)**. Questo mapping assicura l'inclusione dell'unità di magazzino necessaria per la sincronizzazione del livello delle scorte.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="field-service-products-with-inventory-unit-fin-and-ops-to-field-service-products"></a>Prodotti Field Service con unità di magazzino (da Fin and Ops a Field Service): Prodotti

[![Mapping dei modelli in Integrazione dati](./media/FSProduct1.png)](./media/FSProduct1.png)
