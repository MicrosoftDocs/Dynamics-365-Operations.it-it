---
title: Sincronizzare trasferimenti di scorte e rettifiche di magazzino da Field Service a Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare rettifiche di magazzino e trasferimenti di scorte da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: it-it
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Sincronizzare rettifiche di magazzino da Field Service a Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare rettifiche di magazzino e trasferimenti di scorte da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il modello e le attività sottostanti seguenti sono utilizzati per sincronizzare rettifiche di magazzino e trasferimenti di scorte da Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.

**Nome dei modelli in Integrazione dati:**
- Rettifica magazzino (da Field Service a Finance and Operations)
- Trasferimenti scorte (da Field Service a Finance and Operations)

**Nomi delle attività nei progetti di Integrazione dati:**
- Rettifiche magazzino
- Trasferimenti scorte

## <a name="entity-set"></a>Insieme di entità
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   Intestazioni e righe giornali di registrazione rettifica magazzino CDS |
| msdyn_inventoryadjustmentproducts | Intestazioni e righe giornali di registrazione trasferimento scorte CDS   |

## <a name="entity-flow"></a>Flusso di entità
Le rettifiche di magazzino e i trasferimenti di scorte effettuati in Field Service saranno sincronizzati a Finance and Operations quando si cambia l'impostazione di **Registra stato** da Creato a Registrato. Quando ciò avviene, l'ordine di trasferimento o rettifica verrà bloccato e diventa di sola lettura, poiché rettifiche e trasferimenti possono essere registrati in Finance and Operations e quindi non sono modificabili.
In Finance and Operations è possibile impostare un processo batch per registrare automaticamente le rettifiche e trasferire i giornali di registrazione magazzino generati con l'integrazione. Vedere il prerequisito seguente per dettagli su come abilitare il processo batch.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service 
Il campo Unità di magazzino è stato aggiunto all'entità Prodotto. Questo campo è necessario in quanto l'unità di vendita e l'unità di magazzino non sono sempre uguali in Operations e per le scorte di magazzino in Operations è necessaria l'unità di magazzino.
Quando si imposta il prodotto su un prodotto di rettifica magazzino per le rettifiche di magazzino e i trasferimenti di scorte, l'unità verrà recuperata dal valore Prodotto di magazzino in Prodotti. Se viene rilevato un valore, il campo Unità verrà bloccato nel prodotto di rettifica magazzino.

Il campo Registra stato è stato aggiunto all'entità Rettifica magazzino e all'entità Trasferimento scorte. Questo campo viene utilizzato come filtro quando una rettifica o un trasferimento viene inviato a Operations. Per impostazione predefinita il campo è impostato su Creato (1) e non è inviato a Operations. Quando viene impostato su Registrato (2), si ha l'invio a Operations, ma non sarà più possibile effettuare modifiche nella rettifica o nel trasferimento o aggiungervi nuove righe.
Il campo Sequenza numerica è stato aggiunto all'entità Prodotto di rettifica magazzino. Questo campo consente di avere un numero univoco per l'integrazione e quindi di definire quando creare e quando aggiornare. Quando si crea il primo prodotto di rettifica magazzino, viene creato un nuovo record nell'entità di numerazione automatica Prospect to Cash per gestire la serie di numeri e il prefisso utilizzato.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

### <a name="in-finance-and-operations"></a>In Finance and Operations
I giornali di registrazione magazzino generati tramite l'integrazione possono essere registrati automaticamente mediante un processo batch. A questo proposito, selezionare Gestione inventario > Attività periodiche > Integrazione CDS > Registra giornali di registrazione magazzino integrazione.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Rettifica magazzino (da Field Service a Finance and Operations): Rettifica magazzino

[![Mapping dei modelli in Integrazione dati](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Trasferimento scorte (da Field Service a Finance and Operations): Trasferimento scorte

[![Mapping dei modelli in Integrazione dati](./media/FSTrans1.png)](./media/FSTrans1.png)

