---
title: Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service
description: Questo argomento descrive i modelli e l'attività sottostante che vengono utilizzati per sincronizzare i prodotti da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 45a989604d829db715756b6cd206a5675a18acf2
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909993"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante utilizzati per sincronizzare i prodotti da Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

Il modello utilizzato **Prodotti Field Service (da Supply Chain Management a Field Service)** si basa sul modello **Prodotti (da Supply Chain Management a Sales) - Diretto** di Prospect to Cash. Per ulteriori informazioni, vedere [Prodotti (da Supply Chain Management a Sales) - Diretto](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Questo argomenti descrive solo le differenze tra i modelli **Prodotti Field Service (da Supply Chain Management a Field Service)** e **Prodotti (da Supply Chain Management a Sales) - Diretto**.

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati**

- Prodotti Field Service (da Supply Chain Management a Field Service)

**Nome dell'attività nel progetto di Integrazione dati**

- Prodotti - Prodotti

Il modello utilizzato **Prodotti Field Service (da Supply Chain Management a Field Service)** include un mapping che non è incluso nel modello **Prodotti (da Supply Chain Management a Sales) - Diretto**. Questo mapping assicura che il campo obbligatorio specifico di Field Service **Tipo di prodotto Field Service** sia impostato correttamente.

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Viene utilizzato il seguente mapping di valori:

```plaintext
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]