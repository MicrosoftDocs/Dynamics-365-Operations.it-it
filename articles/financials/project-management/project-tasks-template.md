---
title: "Sincronizzare le attività di progetto da Project Service Automation"
description: "Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: it-it
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a>Sincronizzare le attività di progetto in Project Service Automation direttamente con le attività di progetto di Finance and Operations

Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.

> [!NOTE]
> L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Dynamics 365 for Finance and Operations versione 8.0.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flusso di dati per Project Service Automation verso Finance and Operations

La soluzione di integrazione di Project Service Automation in Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. Il modello di integrazione disponibile con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle attività del progetto da Project Service Automation a Finance and Operations.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Modello e attività

Per accedere al modello disponibile, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le attività di progetto da Project Service Automation a Finance and Operations:

-**Nome del modello in Integrazione dati:** Attività di progetto (da PSA a Fin and Ops) - **Nome dell'attività del progetto:** Attività di progetto

Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.

## <a name="entity-set"></a>Insieme di entità

|Project Service Automation               | Finance and Operations                |
|-----------------------------------------|---------------------------------------|
| Attività di progetto                           | Entità di integrazione per attività di progetto   |

## <a name="entity-flow"></a>Flusso di entità

Le attività di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance and Operations come attività di progetto.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.

## <a name="power-query"></a>Power Query

È necessario utilizzare Microsoft Power Query per filtrare i dati se si verificano le condizioni seguenti:

- Si dispone di record specifici di risorsa in un'attività di progetto.

Se è necessario utilizzare Power Query, seguire queste indicazioni:

- Il modello delle attività di progetto (da PSA a Fin and Ops) include un filtro predefinito per escludere i record specifici di risorsa dall'interno di un'attività di progetto tramite l'impostazione del filtro in **IsLineTask** su **False**. Se si crea un modello personale, è necessario aggiungere questo filtro.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nella figura seguente viene mostrato un esempio dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)


