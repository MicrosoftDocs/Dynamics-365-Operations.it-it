---
title: Sincronizzare prodotti con l'unità di magazzino da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "359246"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Sincronizzare i prodotti con l'unità di magazzino da Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Il modello **Prodotti Field Service (da Finance and Operations a Field Service)** utilizzato si basa sul modello **Prodotti (da Finance and Operations a Sales) - Diretto** di Prospect to Cash. Per ulteriori informazioni, vedere [Prodotti (da Finance and Operations a Sales) - Diretto](products-template-mapping-direct.md).

Questo argomento descrive solo le differenze tra i modelli **Prodotti Field Service (da Finance and Operations a Field Service)** e **Prodotti Field Service (da Finance and Operations a Field Service) - Diretto**.

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati:**

- Prodotti Field Service con unità di magazzino (da Finance and Operations a Sales)

**Nome dell'attività nel progetto di Integrazione dati:**

- Prodotti

Il modello **Prodotti Field Service con unità di magazzino (da Finance and Operations a Field Service)** include una mappatura che non è inclusa nel modello **Prodotti Field Service (da Finance and Operations a Field Service)**. Questo mapping assicura l'inclusione dell'unità di magazzino necessaria per la sincronizzazione del livello delle scorte.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a>Prodotti Field Service con unità di magazzino (da Finance and Operations a Field Service): Prodotti

[![Mapping dei modelli in Integrazione dati](./media/FSProduct1.png)](./media/FSProduct1.png)
