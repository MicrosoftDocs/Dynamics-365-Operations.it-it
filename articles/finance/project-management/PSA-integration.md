---
title: Panoramica Project Service Automation
description: In questo argomento vengono fornite informazioni sulla soluzione di integrazione di Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250555"
---
# <a name="project-service-automation-overview"></a>Panoramica Project Service Automation

[!include[banner](../includes/banner.md)]

La soluzione di integrazione di Project Service Automation con Finance utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Dynamics 365 Finance e Dynamics 365 Project Service Automation tramite Common Data Service. I modelli di integrazione disponibili con la funzionalità Integrazione dati abilita il flusso di progetti, contratti di progetto, righe di contratto di progetto, punti cardine delle righe di contratto di progetto, attività di progetto, categorie di transazione di spesa, stime orarie e delle spese da Project Service Automation a Finance.

> [!NOTE]
> - Se si utilizza la versione 7.3.0, è necessario installare KB 4074835. In questo modo sarà possibile integrare i progetti a prezzo fisso.
> - Se si utilizza la versione 7.3.0 e si eseguono transazioni di tipo commissione da Project Service Automation, è necessario installare KB 4345320 per includere tali commissioni nella fattura di progetto.
> - Se si utilizza la versione 8.0, sarà possibile utilizzare l'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità.
> - Se si utilizza la versione 8.0.1 o successiva, sarà possibile sincronizzare i numeri effettivi.

Prima di poter integrare Project Service Automation con Finance, è necessario configurare i parametri di integrazione Project Service Automation. Per ulteriori informazioni, vedere [Parametri di integrazione di Project Service Automation](PSA-parameters.md).

Questa soluzione di integrazione consente la sincronizzazione diretta negli scenari seguenti:

- Gestire i contratti di progetto in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance.
- Creare progetti in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance.
- Gestire le righe dei contratti di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.
- Gestire i punti cardine delle righe dei contratti di progetto in Project Service Automation e sincronizzarli direttamente da Project Service Automation in Finance.
- Gestire le attività di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.
- Gestire le categorie di transazione delle spese in Finance e sincronizzarle direttamente da Finance in Project Service Automation.
- Creare stime di ore di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.
- Creare stime di spese di progetto in Project Service Automation e sincronizzarle direttamente da Project Service Automation in Finance.
- Creare tempi di progetto, spese di progetto e valori effettivi di commissione in Project Service Automation e creare transazioni di progetto nel giornale di registrazione di integrazione di Project Service Automation in modo da poterli registrare in Finance.

## <a name="data-synchronization"></a>Sincronizzazione dati

La figura seguente mostra il modo in cui i dati vengono sincronizzati nell'ambito dell'integrazione tra Project Service Automation e Finance.

> [!NOTE]
> Non tutti i modelli sono disponibili al momento. I modelli verranno rilasciati man mano che vengono completati.

[![Iintegrazione di Project Service Automation con Finance](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance"></a>Requisiti di sistema per Finance

Per utilizzare la soluzione di integrazione di Project Service Automation con Finance, è necessario installare Enterprise Edition 7.3 con aggiornamento 12 della piattaforma o versione successiva.

## <a name="system-requirements-for-project-service-automation"></a>Requisiti di sistema per Project Service Automation

Per utilizzare la soluzione di integrazione di Project Service Automation con Finance, è necessario installare i componenti seguenti:

- Dynamics 365 Project Service Automation 9.0.0.0 o versione successiva
- Soluzione Prospect to cash per Dynamics 365 Sales versione 1.14.0.0 (v14) o versione successiva
- Soluzione Project Service Automation con Finance per Dynamics 365 Project Service Automation versione 1.0.0.0 o versione successiva

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a>Installare la soluzione di integrazione Project Service Automation in Finance nell'istanza di Project Service Automation

Scaricare la soluzione di integrazione di Project Service Automation con Finance dall'[Area download Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) e seguire le istruzioni incluse con la soluzione.
