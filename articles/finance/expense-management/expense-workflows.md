---
title: Impostare flussi di lavoro per le spese
description: È possibile impostare un processo del flusso di lavoro utilizzato per rivedere e approvare i documenti viaggi e spese.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178466"
---
# <a name="set-up-workflows-for-expense"></a>Impostare flussi di lavoro per le spese

[!include [banner](../includes/banner.md)]

 È possibile impostare un processo del flusso di lavoro utilizzato per rivedere e approvare i documenti viaggi e spese. I documenti per cui è possibile definire flussi di lavoro includono note spese, richieste di viaggio e richieste di anticipo contanti.

Un flusso di lavoro rappresenta un processo aziendale. Definisce il modo in cui un documento attraversa il sistema e stabilisce chi deve completare un'attività o approvare un documento. Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:

-   **Processi coerenti**: è possibile definire il processo di approvazione per documenti specifici, ad esempio richieste di acquisto e note spese. L'utilizzo del sistema flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.

-   Visibilità dei processi: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di una specifica istanza di flusso di lavoro. In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.

-   Elenco di lavoro centralizzato: gli utenti possono visualizzare un elenco di lavoro centralizzato contenente le attività del flusso di lavoro e le approvazioni loro assegnati. 

**Tipi di flussi di lavoro che è possibile creare**

Nella tabella riportata di seguito sono elencati i tipi di flussi di lavoro che è possibile creare in **Spesa**.


|              <strong>Tipo</strong>              |                   <strong>Utilizzare questo tipo per:</strong>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <strong>Nota spese</strong>         |            Creare flussi di lavoro di approvazione per le note spese.             |
|  <strong>Registrazione automatica nota spese</strong>   |        Creare flussi di lavoro di registrazione automatica per le note spese.        |
|       <strong>Voce di spesa</strong>        |     Creare flussi di lavoro di approvazione per le voci delle note spese.      |
| <strong>Registrazione automatica voce di spesa</strong> | Creare flussi di lavoro di registrazione automatica per le voci delle note spese. |
|       <strong>Richiesta di acquisto viaggio</strong>       |          Creare flussi di lavoro di approvazione per le richieste di viaggio.           |
|      <strong>Richiesta di anticipo contanti</strong>      |         Creare flussi di lavoro di approvazione per richieste di anticipo contanti.          |
|        <strong>Recupero IVA</strong>        | Creare flussi di lavoro di approvazione per il recupero dell'imposta sul valore aggiunto (IVA).  |
