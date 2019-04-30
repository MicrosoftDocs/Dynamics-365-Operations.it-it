---
title: Sincronizzare trasferimenti di scorte e rettifiche di magazzino da Field Service a Finance and Operations
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 75181661c41d238cdc06ffbb6969a2efd7d88d46
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "842417"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Sincronizzare rettifiche di magazzino da Field Service a Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare le rettifiche di magazzino e i trasferimenti di scorte da Microsoft Dynamics 365 for Field Service in Microsoft Dynamics 365 for Finance and Operations.

**Modelli in Integrazione dati**
- Rettifica magazzino (da Field Service a Fin and Ops)
- Trasferimenti scorte (da Field Service a Fin and Ops)

**Attività nei progetti di Integrazione dati**
- Rettifiche magazzino
- Trasferimenti scorte

## <a name="entity-set"></a>Insieme di entità
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   Intestazioni e righe giornali di registrazione rettifica magazzino CDS |
| msdyn_inventoryadjustmentproducts | Intestazioni e righe giornali di registrazione trasferimento scorte CDS   |

## <a name="entity-flow"></a>Flusso di entità
Le rettifiche di magazzino e i trasferimenti di scorte effettuati in Field Service saranno sincronizzati a Finance and Operations dopo che l'impostazione di **Registra stato** passa da **Creato** a **Registrato**. Quando ciò accade, la rettifica o l'ordine di trasferimento verrà chiuso e diventa di sola lettura. Ciò significa che le rettifiche e i trasferimenti possono essere registrati in Finance and Operations, ma non possono essere modificati. In Finance and Operations, è possibile impostare un processo batch per registrare automaticamente le rettifiche e trasferire i giornali di registrazione magazzino generati durante l'integrazione. Vedere il prerequisito seguente per dettagli su come abilitare il processo batch.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service 
Il campo **Unità di magazzino** è stato aggiunto all'entità **Prodotto**. Questo campo è necessario in quanto l'unità di vendita e l'unità di magazzino non sono sempre uguali in Finance and Operations e l'unità di magazzino è necessaria per le scorte di magazzino in Finance and Operations.
Quando si imposta il prodotto su un prodotto di rettifica magazzino per le rettifiche di magazzino e i trasferimenti di scorte, l'unità verrà recuperata dal valore del prodotto di magazzino. Se viene rilevato un valore, il campo **Unità** verrà bloccato nel prodotto di rettifica magazzino.

Il campo **Registra stato** è stato aggiunto all'entità **Rettifica magazzino** e all'entità **Trasferimento scorte**. Questo campo viene utilizzato come filtro quando una rettifica o un trasferimento viene inviato a Finance and Operations. Il valore predefinito di questo campo è Creato (1), ma non viene inviato a Finance and Operations. Quando si imposta il valore su Registrato (2), si ha l'invio a Finance and Operations, ma non sarà più possibile effettuare modifiche nella rettifica o nel trasferimento o aggiungere nuove righe.

Il campo **Sequenza numerica** è stato aggiunto all'entità **Prodotto di rettifica magazzino**. Questo campo assicura che l'integrazione ha un numero univoco, quindi l'integrazione può creare e aggiornare la rettifica. Quando si crea il primo prodotto di rettifica magazzino, viene creato un nuovo record nell'entità di **numerazione automatica Prospect to Cash** per gestire la serie di numeri e il prefisso utilizzato.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

### <a name="finance-and-operations"></a>Finance and Operations
I giornali di registrazione magazzino generati tramite l'integrazione possono essere registrati automaticamente mediante un processo batch. A questo proposito, selezionare **Gestione inventario > Attività periodiche > Integrazione CDS > Registra giornali di registrazione magazzino integrazione**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a>Rettifica magazzino (da Field Service a Fin and Ops): Rettifica magazzino

[![Mapping dei modelli in Integrazione dati](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a>Trasferimento scorte (da Field Service a Fin and Ops): Trasferimento scorte

[![Mapping dei modelli in Integrazione dati](./media/FSTrans1.png)](./media/FSTrans1.png)
