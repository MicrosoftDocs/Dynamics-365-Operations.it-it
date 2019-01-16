---
title: Sincronizzare l'elenco di progetti da Finance and Operations a Field Service
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: it-it
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Sincronizzare l'elenco di progetti da Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modelli e attività
Il seguente modello e le attività sottostanti sono utilizzati per sincronizzare progetti da Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

**Nome del modello in Integrazione dati:**
- Progetti (da Finance and Operations a Field Service)

**Nomi delle attività nel progetto di Integrazione dati:**
- Progetti

Le attività di sincronizzazione seguenti sono necessarie prima della sincronizzazione dell'elenco di progetti:
- Conti (da Sales a Finance and Operations) 

## <a name="entity-set"></a>Insieme di entità
Field Service   Finance and Operations

| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Progetti                |

## <a name="entity-flow"></a>Flusso di entità
I progetti sono creati in Finance and Operations. I progetti con **Tipo di progetto** Tempistica e materiali e **Fase progetto** In corso saranno sincronizzati all'entità **Progetto esterno** in Field Service, incluse le informazioni Numero progetto, Nome progetto, Fase progetto e Conto cliente. L'elenco di **Progetto esterno** viene utilizzato per associare gli ordini di assistenza Field Service ai progetti Finance and Operations.
Soluzione CRM Field Service Progetto esterno è una nuova entità che ottiene tutti i progetti da Operations.
Il campo Progetto esterno è stato aggiunto all'entità Ordine di lavoro. Questo campo è un lookup and buy che contrassegna l'ordine di lavoro con un progetto; l'ordine cliente verrà quindi collegato a un progetto in Operations. Quando Stato sistema passa da Aperto - In corso (690,970,000) a uno stato superiore, il campo Progetto esterno verrà bloccato e non sarà possibile aggiungere, rimuovere o cambiare il valore.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping
### <a name="in-finance-and-operations"></a>In Finance and Operations
Abilitare il rilevamento delle modifiche per progetti entità di dati

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Progetti (da Finance and Operations a Field Service): Progetti

[![Mapping dei modelli in Integrazione dati](./media/FSProject1.png)](./media/FSProject1.png)

