---
title: Sincronizzare l'elenco dei progetti da Supply Chain Management a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
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
ms.openlocfilehash: d80fce409ee92973a6134d96ce839b9722980918
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430816"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Sincronizzare l'elenco dei progetti da Supply Chain Management a Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare i progetti da Supply Chain Management a Field Service.

**Modello in Integrazione dati**
- Progetti (da Supply Chain Management a Field Service)

**Attività nel progetto di Integrazione dati**
- Progetti

Le attività di sincronizzazione seguenti sono necessarie prima della sincronizzazione dell'elenco di progetti:
- Conti (da Sales a Supply Chain Management) 

## <a name="entity-set"></a>Insieme di entità
| Field Service           | Gestione della supply chain  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Progetti                |

## <a name="entity-flow"></a>Flusso di entità
I progetti vengono creati in Supply Chain Management. I progetti con **Tipo di progetto** impostato su **Tempistica e materiali** e **Fase progetto** impostato su **In corso** saranno sincronizzati all'entità **Progetto esterno** in Field Service, incluse le informazioni Numero progetto, Nome progetto, Fase progetto e Conto cliente. L'elenco **Progetto esterno** viene utilizzato per associare gli ordini di assistenza Field Service ai progetti Supply Chain Management.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service
L'entità **Progetto esterno** ottiene tutti i progetti da Supply Chain Management. Il campo **Progetto esterno** è stato aggiunto all'entità **Ordine di lavoro**. Questo è un campo di ricerca e pertanto contrassegnando l'ordine di lavoro con un progetto, l'ordine cliente verrà collegato a un progetto in Supply Chain Management. Quando **Stato sistema** passa da **Aperto - In corso (690,970,000)** a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà più possibile aggiungere, rimuovere o cambiare il valore.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping
### <a name="supply-chain-management"></a>Gestione della supply chain
Abilitare il rilevamento delle modifiche per progetti entità di dati.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati


### <a name="projects-supply-chain-management-to-field-service-projects"></a>Progetti (da Supply Chain Management a Field Service): Progetti

[![Mapping dei modelli in Integrazione dati](./media/FSProject1.png)](./media/FSProject1.png)
