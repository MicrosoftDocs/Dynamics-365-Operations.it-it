---
title: Sistema del flusso di lavoro
description: Viene descritto il sistema flusso di lavoro in Microsoft Dynamics 365 for Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 770796b42e79ad616b469e1dbf5149789bff0788
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="workflow-system"></a>Sistema del flusso di lavoro

[!include [banner](../includes/banner.md)]

Viene descritto il sistema flusso di lavoro in Microsoft Dynamics 365 for Finance and Operations.

<a name="what-is-workflow"></a>Flusso di lavoro e Workflow
-----------------

Il termine *flusso di lavoro* può essere definito in due modi: come un sistema e come un processo aziendale.
### <a name="workflow-is-a-system"></a>Flusso di lavoro: il sistema

Il sistema del flusso di lavoro viene installato con Finance and Operations e viene eseguito nel server oggetti applicativi (AOS). Nel sistema sono disponibili funzionalità che consentono di creare singoli flussi di lavoro o processi aziendali.

### <a name="workflow-is-a-business-process"></a>Flusso di lavoro: il processo aziendale

Un flusso di lavoro rappresenta un processo aziendale. Definisce il modo in cui un documento attraversa il sistema, o si sposta al suo interno, identificando chi deve completare un'attività, prendere una decisione o approvare un documento. Nella figura indicata di seguito viene illustrato un esempio di un flusso di lavoro per note spese. 

![Flusso di lavoro con elementi assegnati a utenti](./media/workflow_user.gif) 

Per meglio comprendere questo flusso di lavoro, si supponga ora che Giorgio invii una nota spese per un importo pari a USD 7.000. In questo scenario Indro deve verificare le ricevute inoltrate da Giorgio, quindi Ezio e Luisa devono approvare la nota spese. Si supponga ora che Giorgio presenti una nota spese per un importo pari a USD 11.000. In questo scenario Indro deve verificare le ricevute e Ezio, Luisa e Elena devono approvare la nota spese.

## <a name="benefits-of-using-the-workflow-system"></a>Vantaggi del sistema del flusso di lavoro

Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:
-   **Processi coerenti**: è possibile definire il processo di elaborazione di documenti specifici, ad esempio richieste di acquisto e note spese. L'utilizzo del sistema di flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.
-   **Visibilità dei processi**: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di istanze di flussi di lavoro. In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.
-   **Elenco di lavoro centralizzato**: gli utenti possono visualizzare un elenco di lavoro centralizzato contenente le attività del flusso di lavoro e le approvazioni assegnati.


## <a name="workflow-content"></a>Contenuto del flusso di lavoro

+ [Architettura del flusso di lavoro](workflow-system-architecture.md)
+ [Elementi flusso di lavoro](workflow-elements.md)
+ [Azioni flusso di lavoro](workflow-actions.md)
+ [Creare un flusso di lavoro](create-workflow.md)
+ [Configurare le proprietà del flusso di lavoro](configure-workflow-properties.md)
+ [Configurare un'attività manuale in un flusso di lavoro](configure-manual-task-workflow.md)
+ [Configurare un'attività automatica in un flusso di lavoro](configure-automated-task-workflow.md)
+ [Configurare un processo di approvazione in un flusso di lavoro](configure-approval-process-workflow.md)
+ [Configurare un passaggio di approvazione in un flusso di lavoro](configure-approval-step-workflow.md)
+ [Configurare una decisione manuale in un flusso di lavoro](configure-manual-decision-workflow.md)
+ [Configurare una decisione condizionale in un flusso di lavoro](configure-conditional-decision-workflow.md)
+ [Configurare un'attività parallela in un flusso di lavoro](configure-parallel-activity-workflow.md)
+ [Configurare un ramo parallelo in un flusso di lavoro](configure-parallel-branch-workflow.md)
+ [Configurare un flusso di lavoro voci](configure-line-item-workflow.md)

