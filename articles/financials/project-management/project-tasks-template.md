---
title: Sincronizzare le attività di progetto direttamente da Project Service Automation a Finance and Operations
description: Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 53e4eab0d455af4ac1e17754f31d46458db742c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557926"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizzare le attività di progetto direttamente da Project Service Automation a Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive il modello e l'attività sottostante che vengono utilizzati per sincronizzare le attività del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> - L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Microsoft Dynamics 365 for Finance and Operations versione 8.0.
> - Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità. Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.
> - L'integrazione dei valori effettivi è disponibile in Microsoft Dynamics 365 for Finance and Operations versione 8.0.1 o successive.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flusso di dati per Project Service Automation verso Finance and Operations

La soluzione di integrazione di Project Service Automation in Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. Il modello di integrazione disponibile con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle attività del progetto da Project Service Automation a Finance and Operations.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Modello e attività

Per accedere al modello disponibile, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le attività di progetto da Project Service Automation a Finance and Operations:

- **Nome del modello in Integrazione dati:** attività di progetto (da PSA a Fin and Ops)
- **Nome dell'attività nel progetto:** attività di progetto

Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.

## <a name="entity-set"></a>Insieme di entità

| Project Service Automation | Finance and Operations              |
|----------------------------|-------------------------------------|
| Attività di progetto              | Entità di integrazione per attività di progetto |

## <a name="entity-flow"></a>Flusso di entità

Le attività di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance and Operations come attività di progetto.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

Prima di eseguire la sincronizzazione delle attività di progetto, è necessario sincronizzare i contratti di progetto e i progetti.

## <a name="power-query"></a>Power Query

È necessario utilizzare Microsoft Power Query per filtrare i dati in Excel se si verificano le condizioni seguenti:

- Si dispone di record specifici di risorsa in un'attività di progetto.

Se è necessario utilizzare Power Query, seguire queste indicazioni:

- Il modello delle attività di progetto (da PSA a Fin and Ops) include un filtro predefinito per escludere i record specifici di risorsa da un'attività di progetto tramite l'impostazione del filtro di **IsLineTask** su **False**. Se si crea un modello personale, è necessario aggiungere questo filtro.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nella figura seguente viene mostrato un esempio dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)
