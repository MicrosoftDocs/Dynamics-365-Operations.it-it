---
title: Sincronizzare i prodotti in Finance and Operations con i prodotti in Field Service
description: "Questo argomento descrive i modelli e l'attività sottostante che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08cfd2cfa24bef0f0c92126f5d1052a12ceba37a
ms.openlocfilehash: 699830ce6cd993f3dd3fd4ff744ce5a8b9645c32
ms.contentlocale: it-it
ms.lasthandoff: 04/11/2018

---

# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a>Sincronizzare i prodotti in Finance and Operations con i prodotti in Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e l'attività sottostante che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.

Il modello utilizzato **Prodotti Field Service (da Fin and Ops a Field Service)** si basa sul modello **Prodotti (da Fin and Ops a Sales) - Direct** da Prospect to Cash. Per ulteriori informazioni, vedere [Prodotti (da Fin and Ops a Sales) - Diretto](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Questo argomenti descrive solo le differenze tra i modelli **Prodotti Field Service (da Fin and Ops a Field Service)** e **Prodotti (da Fin and Ops a Sales) - Diretto**.

## <a name="templates-and-tasks"></a>Modelli e attività

**Nome del modello in Integrazione dati:**

- Prodotti Field Service (da Fin and Ops a Field Service)

**Nome dell'attività nel progetto di Integrazione dati:**

- Prodotti - Prodotti

Il modello utilizzato **Prodotti Field Service (da Fin and Ops a Field Service)** include un mapping che non è incluso nel modello **Prodotti (da Fin and Ops a Sales) - Diretto**. Questo mapping assicura che il campo obbligatorio specifico di Field Service **Tipo di prodotto Field Service** sia impostato correttamente.

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Viene utilizzato il seguente mapping di valori:

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

In Finance and Operations, il valore di **Tipo di prodotto Field Service** nell'entità di dati **Prodotti rilasciati di vendita** viene calcolato come segue:

- **Magazzino:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = True
- **Non scorte:** Tipo di prodotto = gruppo di modelli Prodotto e articolo, Prodotto stoccato = False
- **Assistenza:** Tipo di prodotto = Assistenza

