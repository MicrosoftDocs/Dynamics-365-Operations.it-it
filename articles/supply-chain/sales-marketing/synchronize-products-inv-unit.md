---
title: Sincronizzare i prodotti con l'unità di magazzino da Supply Chain Management a Field Service
description: Questo articolo descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: Henrikan
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
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5f7658eacd20aa69a64d6288e9d29e53b6ccb002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887256"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Sincronizzare i prodotti con l'unità di magazzino da Supply Chain Management a Field Service

[!include[banner](../includes/banner.md)]

Questo articolo descrive i modelli e l'attività sottostante utilizzati per sincronizzare prodotti con unità di magazzino da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.

[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Il modello **Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service)** utilizzato è basato sul modello **Prodotti Field Service (da Supply Chain Management a Field Service)**. Per ulteriori informazioni, vedere [Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service](field-service-product.md).

In questo articolo vengono descritte le differenze tra i due modelli: 
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