---
title: Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service
description: Questo argomento descrive i modelli e l'attività sottostante che vengono utilizzati per sincronizzare i prodotti da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 1efa4e403f5cf2cdc5fb797f05781f6d42245ed5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210020"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare i prodotti da Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

Il modello utilizzato **Prodotti Field Service (da Supply Chain Management a Field Service)** si basa sul modello **Prodotti (da Supply Chain Management a Sales) - Diretto** di Prospect to Cash. Per ulteriori informazioni, vedere [Prodotti (da Supply Chain Management a Sales) - Diretto](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Questo argomenti descrive solo le differenze tra i modelli **Prodotti Field Service (da Supply Chain Management a Field Service)** e **Prodotti (da Supply Chain Management a Sales) - Diretto**.

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati**

- Prodotti Field Service (da Supply Chain Management a Field Service)

**Nome dell'attività nel progetto di Integrazione dati**

- Prodotti - Prodotti

Il modello utilizzato **Prodotti Field Service (da Supply Chain Management a Field Service)** include un mapping che non è incluso nel modello **Prodotti (da Supply Chain Management a Sales) - Diretto**. Questo mapping assicura che il campo obbligatorio specifico di Field Service **Tipo di prodotto Field Service** sia impostato correttamente.

```Text
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Viene utilizzato il seguente mapping di valori:

```Text
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

In Supply Chain Management, il valore di **Tipo di prodotto Field Service** nell'entità di dati **Prodotti rilasciati di vendita** viene calcolato come segue:

- **Magazzino:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = True
- **Non scorte:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = False
- **Assistenza:** Tipo di prodotto = Assistenza

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Prodotti Field Service (da Supply Chain Management a Field Service): Prodotti - Prodotti

[![Mapping dei modelli in Integrazione dati](./media/FSProduct.png)](./media/FSProduct.png)
