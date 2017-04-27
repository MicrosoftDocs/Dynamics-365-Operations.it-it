---
title: Panoramica del sistema del flusso di lavoro
description: Viene descritto il sistema flusso di lavoro in Microsoft Dynamics 365 for Operations.
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 08c36f02f88fef7508730b6c01a1c99a0f77fb0c
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-system-overview"></a>Panoramica del sistema del flusso di lavoro

[!include[banner](../includes/banner.md)]


Viene descritto il sistema flusso di lavoro in Microsoft Dynamics 365 for Operations.

<a name="what-is-workflow"></a>Flusso di lavoro e Workflow
-----------------

Il termine *flusso di lavoro* può essere definito in due modi: come un sistema e come un processo aziendale.
### <a name="workflow-is-a-system"></a>Flusso di lavoro: il sistema

Il sistema del flusso di lavoro viene installato con Dynamics 365 for Operations e viene eseguito esecuzione nel server oggetti applicativi (AOS). Nel sistema sono disponibili funzionalità che consentono di creare singoli flussi di lavoro o processi aziendali.

### <a name="workflow-is-a-business-process"></a>Flusso di lavoro: il processo aziendale

Un flusso di lavoro rappresenta un processo aziendale. Definisce il modo in cui un documento attraversa il sistema, o si sposta al suo interno, identificando chi deve completare un'attività, prendere una decisione o approvare un documento. Nella figura indicata di seguito viene illustrato un esempio di un flusso di lavoro per note spese. ![Flusso di lavoro con elementi assegnati a utenti](./media/workflow_user.gif) Per meglio comprendere questo flusso di lavoro, si supponga ora che Giorgio invii una nota spese per un importo pari a USD 7.000. In questo scenario Indro deve verificare le ricevute inoltrate da Giorgio, quindi Ezio e Luisa devono approvare la nota spese. Si supponga ora che Giorgio presenti una nota spese per un importo pari a USD 11.000. In questo scenario Indro deve verificare le ricevute e Ezio, Luisa e Elena devono approvare la nota spese.
Vantaggi del sistema del flusso di lavoro
-------------------------------------

Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:
-   **Processi coerenti**: è possibile definire il processo di elaborazione di documenti specifici, ad esempio richieste di acquisto e note spese. L'utilizzo del sistema di flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.
-   **Visibilità dei processi**: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di istanze di flussi di lavoro. In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.
-   **Elenco di lavoro centralizzato**: gli utenti possono visualizzare un elenco di lavoro centralizzato contenente le attività del flusso di lavoro e le approvazioni assegnati.





