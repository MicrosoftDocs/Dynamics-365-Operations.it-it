---
title: Sincronizzare i prodotti con l'unità di magazzino da Supply Chain Management a Field Service
description: Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 1312015fe5b9b95a341e9e7170dfc5106f47f0875f89224983e5ec61dd8de5ff
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717869"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Sincronizzare i prodotti con l'unità di magazzino da Supply Chain Management a Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.

[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Il modello **Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service)** utilizzato è basato sul modello **Prodotti Field Service (da Supply Chain Management a Field Service)**. Per ulteriori informazioni, vedere [Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service](field-service-product.md).

In questo argomento vengono descritte le differenze tra i due modelli: 
- **Prodotti Field Service con l'unità di magazzino (Supply Chain Management a Sales)**
- **Prodotti Field Service (da Supply Chain Management a Field Service)** 

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati:**

- Prodotti Field Service con l'unità di magazzino (Supply Chain Management a Sales)

**Nome dell'attività nel progetto di Integrazione dati:**

- Prodotti

Il modello **Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service)** include un mapping che non è previsto nel modello **Prodotti Field Service (da Supply Chain Management a Field Service)**. Questo mapping assicura l'inclusione dell'unità di magazzino necessaria per la sincronizzazione del livello delle scorte.

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service): Prodotti

[![Mapping modello in Integrazione dati.](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]