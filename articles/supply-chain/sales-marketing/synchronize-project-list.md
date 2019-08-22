---
title: Sincronizzare l'elenco di progetti da Finance and Operations a Field Service
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 535094821ca7efa33bf40f2057fac8ffc17bb822
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843555"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Sincronizzare l'elenco dei progetti da Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

**Modello in Integrazione dati**
- Progetti (da Fin and Ops a Field Service)

**Attività nel progetto di Integrazione dati**
- Progetti

Le attività di sincronizzazione seguenti sono necessarie prima della sincronizzazione dell'elenco di progetti:
- Conti (da Sales a Fin and Ops) 

## <a name="entity-set"></a>Insieme di entità
| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Progetti                |

## <a name="entity-flow"></a>Flusso di entità
I progetti sono creati in Finance and Operations. I progetti con **Tipo di progetto** impostato su **Tempistica e materiali** e **Fase progetto** impostato su **In corso** saranno sincronizzati all'entità **Progetto esterno** in Field Service, incluse le informazioni Numero progetto, Nome progetto, Fase progetto e Conto cliente. L'elenco **Progetto esterno** viene utilizzato per associare gli ordini di assistenza Field Service ai progetti Finance and Operations.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service
L'entità **Progetto esterno** ottiene tutti i progetti da Finance and Operations. Il campo **Progetto esterno** è stato aggiunto all'entità **Ordine di lavoro**. Questo campo è un lookup, quindi contrassegnando l'ordine di lavoro con un progetto, l'ordine cliente verrà collegato a un progetto in Finance and Operations. Quando **Stato sistema** passa da **Aperto - In corso (690,970,000)** a uno stato superiore, il campo **Progetto esterno** verrà bloccato e non sarà più possibile aggiungere, rimuovere o cambiare il valore.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping
### <a name="finance-and-operations"></a>Finance and Operations
Abilitare il rilevamento delle modifiche per progetti entità di dati.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati


### <a name="projects-fin-and-ops-to-field-service-projects"></a>Progetti (da Fin and Ops a Field Service): Progetti

[![Mapping dei modelli in Integrazione dati](./media/FSProject1.png)](./media/FSProject1.png)
