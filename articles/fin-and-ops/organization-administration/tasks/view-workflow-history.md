---
title: Visualizzare lo storico flusso di lavoro
description: Questo argomento descrive la procedura per visualizzare lo stato di un documento inviato al sistema del flusso di lavoro per l'elaborazione e l'approvazione.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16c6594161f1fecd36183a6b8f2c798f52d70a9c
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738790"
---
# <a name="view-workflow-history"></a>Visualizzare lo storico flusso di lavoro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questo argomento descrive la procedura per visualizzare lo stato di un documento inviato al sistema del flusso di lavoro per l'elaborazione e l'approvazione. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Passare a **Pannello di navigazione > Moduli > Comune > Richieste di informazioni > Flusso di lavoro > Storico flusso di lavoro**.
    - Utilizzare questo modulo per visualizzare lo stato di un documento inviato al sistema del flusso di lavoro per l'elaborazione e l'approvazione.  
    - **ID istanza** è il codice di identificazione dell'istanza del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.  
    - **Stato** è lo stato del flusso di lavoro del documento.  
    - **ID flusso di lavoro** è il codice di identificazione del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.  
    - **Documento** è il codice di identificazione del documento.  
    - **Tipo di documento** è il tipo di documento inviato per l'elaborazione.  
    - **Flusso di lavoro** è il nome del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.  
    - **Versione** è il numero di versione del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.  
    - **Data e ora creazione** è la data e ora in cui il documento è stato inviato.  
    - **Tempo trascorso** è la quantità di tempo trascorsa dall'invio del documento.  
    - Il pulsante **Riprendi** consente di riprendere il processo del flusso di lavoro relativo al documento selezionato.  
    - Il pulsante **Richiama** consente di richiamare il documento selezionato in modo che non venga elaborato.   
2. Nell'elenco fare clic sul collegamento nella riga desiderata.
    - Assicurarsi che la sezione **Elementi di lavoro** sia espansa. In questa sezione è possibile visualizzare gli elementi di lavoro associati al documento selezionato. Può contenere, ad esempio, un'attività da completare o un documento da approvare.  
    - Il pulsante **Riassegna** apre una finestra di dialogo in cui è possibile riassegnare un elemento di lavoro a un altro utente.  
    - Assicurarsi che la sezione **Dettagli tracciabilità** sia espansa. In questa sezione è possibile visualizzare lo storico flusso di lavoro del documento selezionato.  

