---
title: Sincronizzare le informazioni sul livello di scorte da Supply Chain Management a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
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
ms.openlocfilehash: 1228339c12d26f7b91875d15f0daa8da2869cba0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431031"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Sincronizzare le informazioni sul livello di scorte da Supply Chain Management a Field Service 

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le informazioni sul livello di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.

[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i livelli delle scorte disponibili da Supply Chain Management a Field Service.

**Modello in Integrazione dati**
- Inventario prodotti (da Supply Chain Management a Field Service)
  
**Attività nel progetto di Integrazione dati**
- Inventario prodotti

Le attività di sincronizzazione seguenti sono necessarie per la sincronizzazione dei livelli delle scorte:
- Magazzini (da Supply Chain Management a Field Service) 
- Prodotti Field Service con l'unità di magazzino (Supply Chain Management a Sales) 

## <a name="entity-set"></a>Insieme di entità

| Field Service                      | Gestione della supply chain                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Disponibilità scorte in base al magazzino CDS     |

## <a name="entity-flow"></a>Flusso di entità
Le informazioni sul livello delle scorte da Finance and Operations sono inviate a Field Service per i prodotti selezionati. Le informazioni sul livello delle scorte includono: 
- Quantità disponibile (quantità corrente fisica registrata presente nel magazzino)
- Quantità in ordinazione (quantità registrata totale in odinazione, ad esempio ordini cliente)
- Quantità ordinata (quantità ordinata registrata totale, ad esempio ordini fornitore)

Queste informazioni vengono acquisite per prodotto rilasciato per ogni magazzino e sincronizzate in base al rilevamento delle modifiche, quando il livello delle scorte cambia.

In Field Service, la soluzione di integrazione crea giornali di registrazione magazzino per il delta, di modo che i livelli in Field Service corrispondano a quelli in Supply Chain Management.

Supply Chain Management sarà il master per i livelli delle scorte. È quindi importante impostare l'integrazione per ordini di lavoro, trasferimenti e rettifiche da Field Service a Supply Chain Management se questa funzionalità è utilizzata in Field Service, insieme alla sincronizzazione dei livelli delle scorte da Supply Chain Management.

I prodotti e i magazzini in cui i livelli delle scorte sono gestiti da Supply Chain Management possono essere controllati con Filtro e query avanzati (Power Query).

> [!NOTE]
> È possibile creare più magazzini in Field Service (con **Gestito esternamente = No**) e quindi mapparli a un singolo magazzino in Supply Chain Management, con la funzionalità Filtro e query avanzati. Questa soluzione è utilizzata in situazioni in cui Field Service deve gestire il livello delle scorte dettagliato e inviare aggiornamenti solo a Supply Chain Management. In questo caso Field Service non riceverà gli aggiornamenti del livello delle scorte da Supply Chain Management. Per ulteriori informazioni, vedere [Sincronizzare rettifiche di inventario da Field Service a Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizzare gli ordini di lavoro in Field Service con gli ordini cliente collegati a un progetto in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service
L'entità **Inventario prodotti esterno** è utilizzata solo per il backend nell'integrazione. Questa entità riceve i valori del livello delle scorte da Supply Chain Management nell'integrazione, trasforma tali valori in giornali di registrazione manuali, quindi modifica i prodotti di magazzino nel magazzino.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

### <a name="data-integration"></a>Integrazione dati
Affinché il progetto funzioni, verificare che la chiave di integrazione sia aggiornata con msdynce_externalproductinventories.
1.  Passare a **Integrazione dati > Set di connessione**.
2.  Selezionare il set di connessione utilizzato.
3.  Nella scheda **Chiave di integrazione**, assicurarsi di aggiungere le seguenti chiavi a msdynce_externalproductinventories:
      - msdynce_productnumber (numero prodotto)
      - msdynce_warehouseid (ID magazzino)
      
### <a name="data-integration-project"></a>Progetto di Integrazione dati
È possibile applicare filtri con Filtro e query avanzati di modo che solo certi prodotti e magazzini inviino informazioni sul livello delle scorte da Supply Chain Management a Field Service.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>Inventario prodotti (da Supply Chain Management a Field Service): Inventario prodotti

[![Mapping dei modelli in Integrazione dati](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]