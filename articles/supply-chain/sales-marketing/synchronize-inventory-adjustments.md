---
title: Sincronizzare i trasferimenti e le rettifiche delle scorte da Field Service a Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 04/30/2019
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
ms.openlocfilehash: 9f3bfe950446a6e87e34c32d2593cba0af84d8e8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838983"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Sincronizzare i trasferimenti e le rettifiche delle scorte da Field Service a Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Dynamics 365 Supply Chain Management in Dynamics 365 Field Service.

[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i trasferimenti e le rettifiche delle scorte da Field Service a Supply Chain Management.

**Modelli in Integrazione dati**
- Rettifica magazzino (da Field Service a Supply Chain Management)
- Trasferimenti scorte (da Field Service a Supply Chain Management)

**Attività nei progetti di Integrazione dati**
- Rettifiche magazzino
- Trasferimenti scorte

## <a name="table-set"></a>Set di tabelle
| Field Service                     | Gestione della supply chain                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts | Intestazioni e righe giornali di registrazione rettifica magazzino Dataverse |
| msdyn_inventoryadjustmentproducts | Intestazioni e righe giornali di registrazione trasferimento scorte Dataverse   |

## <a name="table-flow"></a>Flusso tabella
Le rettifiche di magazzino e i trasferimenti di scorte effettuati in Field Service saranno sincronizzati a Supply Chain Management dopo che l'impostazione di **Registra stato** passa da **Creato** a **Registrato**. Quando ciò accade, la rettifica o l'ordine di trasferimento verrà chiuso e diventa di sola lettura. Ciò significa che le rettifiche e i trasferimenti possono essere registrati in Supply Chain Management, ma non possono essere modificati. In Supply Chain Management, è possibile impostare un processo batch per registrare automaticamente le rettifiche e trasferire i giornali di registrazione magazzino generati durante l'integrazione. Vedere il prerequisito seguente per dettagli su come abilitare il processo batch.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service 
La colonna **Unità di magazzino** è stata aggiunta alla tabella **Prodotto**. Questo colonna è necessario in quanto l'unità di vendita e l'unità di magazzino non sono sempre uguali in Supply Chain Management e l'unità di magazzino è necessaria per le scorte di magazzino in Supply Chain Management.
Quando si imposta il prodotto su un prodotto di rettifica magazzino per le rettifiche di magazzino e i trasferimenti di scorte, l'unità verrà recuperata dal valore del prodotto di magazzino. Se viene rilevato un valore, la colonna **Unità** verrà bloccato nel prodotto di rettifica magazzino.

La colonna **Registra stato** è stato aggiunto alla tabella **Rettifica magazzino** e alla tabella **Trasferimento scorte**. Questa colonna viene utilizzata come filtro quando una rettifica o un trasferimento viene inviato a Supply Chain Management. Il valore predefinito di questa colonna è Creato (1), ma non viene inviato a Supply Chain Management. Quando si imposta il valore su Registrato (2), si ha l'invio a Supply Chain Management, ma non sarà più possibile effettuare modifiche nella rettifica o nel trasferimento o aggiungere nuove righe.

La colonna **Sequenza numerica** è stato aggiunto alla tabella **Prodotto di rettifica magazzino**. Questa colonna assicura che l'integrazione ha un numero univoco, quindi l'integrazione può creare e aggiornare la rettifica. Quando si crea il primo prodotto di rettifica magazzino, viene creato un nuovo record nella tabella di **numerazione automatica Prospect to Cash** per gestire la serie di numeri e il prefisso utilizzato.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

### <a name="supply-chain-management"></a>Gestione della supply chain
I giornali di registrazione magazzino generati tramite l'integrazione possono essere registrati automaticamente mediante un processo batch. A questo proposito, selezionare **Gestione inventario > Attività periodiche > Integrazione Dataverse > Registra giornali di registrazione magazzino integrazione**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Rettifica magazzino (da Field Service a Supply Chain Management): Rettifica magazzino

[![Mapping dei modelli in Integrazione dati](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Trasferimento scorte (da Field Service a Supply Chain Management ): Trasferimento scorte

[![Mapping dei modelli in Integrazione dati](./media/FSTrans1.png)](./media/FSTrans1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]