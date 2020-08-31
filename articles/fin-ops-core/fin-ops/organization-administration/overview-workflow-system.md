---
title: Panoramica del sistema del flusso di lavoro
description: Viene descritto il sistema flusso di lavoro.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 068f464fe5385486827b2f904114eb663e08b2e8
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2020
ms.locfileid: "3697971"
---
# <a name="workflow-system-overview"></a>Panoramica del sistema del flusso di lavoro

[!include [banner](../includes/banner.md)]

Viene descritto il sistema flusso di lavoro.

## <a name="what-is-workflow"></a>Flusso di lavoro e Workflow

Il termine *flusso di lavoro* può essere definito in due modi: come un sistema e come un processo aziendale.

### <a name="workflow-is-a-system"></a>Flusso di lavoro: il sistema

Il flusso di lavoro è un sistema che viene eseguito sul server oggetti applicativi (AOS). Nel sistema sono disponibili funzionalità che consentono di creare singoli flussi di lavoro o processi aziendali.

### <a name="workflow-is-a-business-process"></a>Flusso di lavoro: il processo aziendale

Un flusso di lavoro rappresenta un processo aziendale. Definisce il modo in cui un documento attraversa il sistema, o si sposta al suo interno, identificando chi deve completare un'attività, prendere una decisione o approvare un documento. Nella figura indicata di seguito viene illustrato un esempio di un flusso di lavoro per note spese.

![Flusso di lavoro con elementi assegnati a utenti](./media/workflow_user.gif)

Per meglio comprendere questo flusso di lavoro, si supponga ora che Giorgio invii una nota spese per un importo pari a USD 7.000. In questo scenario Indro deve verificare le ricevute inoltrate da Giorgio, quindi Ezio e Luisa devono approvare la nota spese. Si supponga ora che Giorgio presenti una nota spese per un importo pari a USD 11.000. In questo scenario Indro deve verificare le ricevute e Ezio, Luisa e Elena devono approvare la nota spese.

## <a name="benefits-of-using-the-workflow-system"></a>Vantaggi del sistema del flusso di lavoro

Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:

- **Processi coerenti**: è possibile definire il processo di elaborazione di documenti specifici, ad esempio richieste di acquisto e note spese. L'utilizzo del sistema di flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.
- **Visibilità dei processi**: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di istanze di flussi di lavoro. In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.
- **Elenco di lavoro centralizzato**: gli utenti possono visualizzare un elenco di lavoro centralizzato contenente le attività del flusso di lavoro e le approvazioni assegnati.


## <a name="workflow-content"></a>Contenuto del flusso di lavoro

+ [Architettura del sistema del flusso di lavoro](workflow-system-architecture.md)
+ [Elementi del flusso di lavoro](workflow-elements.md)
+ [Azioni dei processi di approvazione in un flusso di lavoro](workflow-actions.md)
+ [Creare panoramica flussi di lavoro](create-workflow.md)
+ [Configurare le proprietà del flusso di lavoro](configure-workflow-properties.md)
+ [Configurare le attività manuali in un flusso di lavoro](configure-manual-task-workflow.md)
+ [Configurare le attività automatiche in un flusso di lavoro](configure-automated-task-workflow.md)
+ [Configurare i processi di approvazione in un flusso di lavoro](configure-approval-process-workflow.md)
+ [Configurare i passaggi di approvazione in un flusso di lavoro](configure-approval-step-workflow.md)
+ [Configurare le decisioni manuali in un flusso di lavoro](configure-manual-decision-workflow.md)
+ [Configurare le decisioni condizionali in un flusso di lavoro](configure-conditional-decision-workflow.md)
+ [Configurare le attività parallele in un flusso di lavoro](configure-parallel-activity-workflow.md)
+ [Configurare i rami paralleli in un flusso di lavoro](configure-parallel-branch-workflow.md)
+ [Configurare flussi di lavoro voci](configure-line-item-workflow.md)
+ [Domande frequenti sul flusso di lavoro](workflow-FAQ.md)
