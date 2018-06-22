---
title: Project Service Automation
description: "Questa soluzione utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Microsoft Dynamics 365 for Finance and Operations e Microsoft Dynamics 365 per Project Service Automation tramite Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: it-it
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a>Project Service Automation

La soluzione di integrazione tra Project Service Automation e Finance and Operations utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Microsoft Dynamics 365 for Finance and Operations e Microsoft Dynamics 365 per Project Service Automation tramite Common Data Service (CDS). I modelli di integrazione disponibili con la funzionalità Integrazione dati abilita il flusso di progetti, contratti di progetto, righe di contratto di progetto, punti cardine delle righe di contratto di progetto, attività di progetto, categorie di transazione di spesa, stime orarie e delle spese da Project Service Automation a Finance and Operations.

> [!NOTE] 
> Se si utilizza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, è necessario installare KB 4074835. In questo modo sarà possibile integrare i progetti a prezzo fisso.
>
> Se si utilizza Dynamics 365 for Finance and Operations versione 8.0, sarà possibile utilizzare l'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità.
>
> Se si utilizza Dynamics 365 for Finance and Operations versione 8.0.1, sarà possibile sincronizzare i valori effettivi.
>
> Se si utilizza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità. Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.

Prima di poter integrare Project Service Automation con Finance and Operations, è necessario configurare i parametri di integrazione Project Service Automation. Per ulteriori informazioni, vedere Parametri di integrazione di Project Service Automation.

Questa soluzione di integrazione consente la sincronizzazione diretta negli scenari seguenti:

- Gestire i contratti di progetto in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance and Operations.
- Creare progetti in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance and Operations.
- Gestire righe di contratti di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.
- Gestire attività cardine di righe di contratti di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.
- Gestire attività di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.
- Gestire le categorie di transazione delle spese in Finance and Operations e sincronizzarle direttamente da Finance and Operations in Project Service Automation.
- Creare stime di ore di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.
- Creare stime di spese di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance and Operations.

## <a name="data-synchronization"></a>Sincronizzazione dati
La figura seguente mostra il modo in cui i dati vengono sincronizzati nell'ambito dell'integrazione tra Project Service Automation e Finance and Operations.

> [!NOTE]
> Non tutti i modelli sono disponibili al momento. I modelli verranno rilasciati man mano che vengono completati.

[![Integrazione di Project Service Automation con Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Requisiti di sistema di Finance and Operations

Per utilizzare la soluzione di integrazione di Project Service Automation con Finance and Operations, è necessario installare Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 con aggiornamento 12 della piattaforma o versione successiva.

## <a name="system-requirements-for-project-service-automation"></a>Requisiti di sistema per Project Service Automation

Per utilizzare la soluzione di integrazione di Project Service Automation con Finance and Operations, è necessario installare i componenti seguenti:

- Microsoft Dynamics 365 for Project Service Automation versione 9.0.0.0 o versione successiva.
- Soluzione Prospect to cash per Dynamics 365 for Sales versione 1.14.0.0 (v14) o versione successiva.
- Soluzione Project Service Automation to Operations per Dynamics 365 for Project Service Automation versione 1.0.0.0 o versione successiva.

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Installare la soluzione di integrazione Project Service Automation in Finance and Operations nell'istanza di Project Service Automation



