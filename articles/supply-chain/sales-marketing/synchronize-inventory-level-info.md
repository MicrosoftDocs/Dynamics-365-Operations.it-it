---
title: Sincronizzare informazioni sul livello delle scorte da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: b81694f1ed56d8542de46203ac5faf5fae2b6645
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "356785"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a>Sincronizzare le informazioni sul livello di scorte da Finance and Operations a Field Service 

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare i livelli delle scorte disponibili da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.

**Modello in Integrazione dati**
- Inventario prodotti (da Finance and Operations a Field Service)
  
**Attività nel progetto di Integrazione dati**
- Inventario prodotti

Le attività di sincronizzazione seguenti sono necessarie per la sincronizzazione dei livelli delle scorte:
- Magazzini (da Finance and Operations a Field Service) 
- Prodotti Field Service con unità di magazzino (da Finance and Operations a Sales) 

## <a name="entity-set"></a>Insieme di entità

| Field Service                      | Finance and Operations                 |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Disponibilità scorte in base al magazzino CDS     |

## <a name="entity-flow"></a>Flusso di entità
Le informazioni sul livello delle scorte da Finance and Operations sono inviate a Field Service per i prodotti selezionati. Le informazioni sul livello delle scorte includono: 
- Quantità disponibile (quantità corrente fisica registrata presente nel magazzino)
- Quantità in ordinazione (quantità registrata totale in odinazione, ad esempio ordini cliente)
- Quantità ordinata (quantità ordinata registrata totale, ad esempio ordini fornitore)

Queste informazioni vengono acquisite per prodotto rilasciato per ogni magazzino e sincronizzate in base al rilevamento delle modifiche, quando il livello delle scorte cambia.

In Field Service, la soluzione di integrazione crea giornali di registrazione magazzino per il delta, di modo che i livelli in Field Service corrispondano a quelli in Finance and Operations.

Finance and Operations sarà il master per i livelli delle scorte. È quindi importante impostare l'integrazione per ordini di lavoro, trasferimenti e rettifiche da Field Service a Finance and Operations se questa funzionalità è utilizzata in Field Service, insieme alla sincronizzazione dei livelli delle scorte da Finance and Operations.

I prodotti e i magazzini in cui i livelli delle scorte sono gestiti da Finance and Operations possono essere controllati con Filtro e query avanzati (Power Query).

> [!NOTE]
> È possibile creare più magazzini in Field Service (con **Gestito esternamente = No**) e quindi mapparli a un singolo magazzino in Finance and Operations, con la funzionalità Filtro e query avanzati. Questa soluzione è utilizzata in situazioni in cui Field Service deve gestire il livello delle scorte dettagliato e inviare aggiornamenti solo a Finance and Operations. In questo caso Field Service non riceverà gli aggiornamenti del livello delle scorte da Finance and Operations. Per ulteriori informazioni, vedere [Sincronizzare rettifiche di inventario da Field Service a Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente collegati a un progetto in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service
L'entità **Inventario prodotti esterno** è utilizzata solo per il backend nell'integrazione. Questa entità riceve i valori del livello delle scorte da Finance and Operations nell'integrazione, trasforma tali valori in giornali di registrazione manuali, quindi modifica i prodotti di magazzino nel magazzino.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

### <a name="data-integration-project"></a>Progetto di Integrazione dati
È possibile applicare filtri con Filtro e query avanzati di modo che solo certi prodotti e magazzini inviino informazioni sul livello delle scorte da Finance and Operations a Field Service.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a>Inventario prodotti (da Field Service a Finance and Operations): Inventario prodotti

[![Mapping dei modelli in Integrazione dati](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)
