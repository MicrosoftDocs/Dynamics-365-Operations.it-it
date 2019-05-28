---
title: Azioni nei processi di approvazione in un flusso di lavoro
description: In questo articolo vengono illustrate le azioni che ciascun partecipante a un processo di approvazione del flusso di lavoro può eseguire.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 829ee16b8fd72a0808a657419524487d9c1b3123
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560477"
---
# <a name="actions-in-workflow-approval-processes"></a>Azioni nei processi di approvazione in un flusso di lavoro

[!include [banner](../includes/banner.md)]

In questo articolo vengono illustrate le azioni che ciascun partecipante a un processo di approvazione del flusso di lavoro può eseguire.

Un flusso di lavoro può coinvolgere più gruppi di persone: l'iniziatore, gli assegnatari di attività, i decisori e gli approvatori. Nell'esempio di flusso di lavoro relativo alle note spese indicato di seguito, Giorgio è l'iniziatore, i membri della coda sono gli assegnatari dell'attività, Gianni è un decisore ed Ezio, Luisa ed Elena sono gli approvatori.

[![Workflow\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)

Nelle sezioni seguenti vengono descritte le azioni del flusso di lavoro che ogni gruppo può eseguire.

## <a name="actions-that-an-originator-can-perform"></a>Azioni eseguibili da un iniziatore

L'iniziatore avvia un'istanza del flusso di lavoro inviando un documento per l'elaborazione. Per inviare ad esempio una nota spese, Giorgio dovrà fare clic sul pulsante **Invia** nella pagina **Nota spese** per inviare la nota spese.

## <a name="actions-that-a-task-assignee-can-perform"></a>Azioni eseguibili da un assegnatario dell'attività

Un'attività può essere assegnata a più utenti o a una coda di elementi di lavoro monitorata da più persone, ma solo una persona può completare un'attività. Si supponga ad esempio che Giorgio invii una nota spese e che inoltri le ricevute al reparto responsabile delle note spese della sua organizzazione per la verifica.

I membri del reparto responsabile delle note spese di Adventure Works monitorano la coda. Si supponga che Giulia, un membro del reparto, accetti l'attività di verifica della nota spese e delle ricevute di Giorgio. Potrà ora effettuare una delle seguenti azioni: completare, rifiutare, delegare, richiedere la modifica, riassegnare o rilasciare.

> [!NOTE]
> Le azioni disponibili variano in base al modo in cui l'attività è stata progettata dallo sviluppatore software.

### <a name="complete"></a>Completare

Quando un utente completa un'attività, il documento inviato per l'elaborazione viene assegnato all'utente successivo nel flusso di lavoro, se presente. Se non è richiesta un'ulteriore elaborazione, il processo del flusso di lavoro viene completato.

Si supponga ad esempio che Giulia, un membro del reparto responsabile delle note spese di Adventure Works, accetti l'attività di revisione della nota spese e delle ricevute di Giorgio. Dopo che Giulia avrà completato la revisione, il documento verrà assegnato a Gianni.

### <a name="reject"></a>Rifiuta

Quando un utente rifiuta un documento, il processo del flusso di lavoro viene completato.

Si supponga ad esempio che Giulia, un membro del reparto responsabile delle note spese di Adventure Works, accetti l'attività di revisione della nota spese e delle ricevute di Giorgio. Se Giulia rifiuta la nota spese, il processo del flusso di lavoro viene completato.

Giorgio può quindi inviare di nuovo la nota spese. È possibile apportare modifiche prima, oppure può inviare la versione originale. Se Giorgio invia di nuovo la nota spese, il processo del flusso di lavoro avrà inizio dall'attività di revisione manuale.

### <a name="delegate"></a>Delegato

Quando un utente delega un'attività, questa viene assegnata a un altro utente.

Si supponga ad esempio che Giulia, un membro del reparto responsabile delle note spese di Adventure Works, accetti l'attività di revisione della nota spese e delle ricevute di Giorgio. Giulia delega l'attività a Mauro, suo assistente.

Mauro agisce quindi per conto di Giulia. Ciò significa che dopo il completamento della revisione da parte di Mauro, la nota spese viene assegnata a Gianni, come se l'attività fosse stata completata da Giulia.

### <a name="request-change"></a>Richiedere una modifica

Quando un utente richiede una modifica di un documento inviato, quest'ultimo viene inviato di nuovo all'iniziatore.

Si supponga ad esempio che Giulia, un membro del reparto responsabile delle note spese di Adventure Works, accetti l'attività di revisione della nota spese e delle ricevute di Giorgio. Giulia nota alcuni errori nella nota spese e richiede alcune modifiche. La nota spese viene nuovamente inviata a Giorgio.

Giorgio può quindi inviare di nuovo la nota spese. È possibile apportare le modifiche richieste prima, oppure può inviare la versione originale. Se Giorgio reinvia la nota spese, un membro della coda di elementi lavoro dovrà nuovamente revisionare la nota spese e le ricevute.

### <a name="reassign"></a>Riassegna

I membri di una coda di elementi di lavoro possono riassegnare i documenti presenti nella coda in un'altra cosa.

Si supponga ad esempio che Giulia, membro del reparto responsabile delle note spese di Adventure Works, monitori la coda. Per bilanciare il carico di lavoro, può assegnare la nota spese e le ricevute incluse a un'altra coda.

### <a name="release"></a>Rilascio

Occasionalmente, un membro della coda di elementi di lavoro potrebbe accettare un'attività, ma poi decidere che non può completarla. In questo caso, la persona che accetta l'attività può rilasciare il documento alla coda di elementi di lavoro.

Si supponga ad esempio che Giulia, un membro del reparto responsabile delle note spese di Adventure Works, accetti l'attività di revisione della nota spese e delle ricevute di Giorgio. Se Giulia decide di non poter completare l'attività, può rilasciare il documento. La nota spese viene restituita alla coda in modo che altri membri del reparto responsabile delle note spese di Adventure Works possano completare l'attività.

## <a name="actions-that-a-decision-maker-can-perform"></a>Azioni eseguibili da un decisore

Solitamente, un documento viene assegnato a un decisore perché, in genere, è necessario che risponda a una domanda. La risposta tipica a questa domanda è **Sì** o **No** oppure **Vero** o **Falso**. Se il decisore non seleziona una di queste opzioni, può delegare la decisione.

### <a name="choice-1-or-choice-2"></a>\[Prima scelta\] o \[Seconda scelta\]

Un decisore deve rispondere a una domanda relativa al documento. La risposta tipica a questa domanda è **Sì** o **No** oppure **Vero** o **Falso**. La risposta selezionata dal decisore determinerà quale ramo del flusso di lavoro verrà utilizzato per elaborare il documento.

Si supponga ad esempio che la nota spese di Giorgio verrà assegnata a Gianni. Gianni deve decidere se le informazioni contenute nel documento richiedono una chiamata al manager di Giorgio. In caso affermativo, la nota spese verrà assegnata a Renata, che dovrà chiamare il manager di Giorgio. In caso negativo, la nota spese verrà assegnata a Ezio per l'approvazione.

### <a name="delegate"></a>Delegare

Se un decisore delega una decisione, il documento viene assegnato a un altro utente che dovrà prendere la decisione.

Si supponga ad esempio che la nota spese di Giorgio verrà assegnata a Gianni. Gianni delega la decisione a Maria, sua assistente.

Maria agisce quindi per conto di Gianni. Se Maria decide che è necessaria una chiamata al responsabile di Giorgio, la nota spese verrà assegnata a Renata, che dovrà chiamare il manager dipendenti. In caso contrario, la nota spese verrà assegnata a Ezio per l'approvazione.

## <a name="actions-that-an-approver-can-perform"></a>Azioni eseguibili da un approvatore

Quando un documento viene assegnato a un approvatore, quest'ultimo può eseguire una delle seguenti azioni: approvare, rifiutare, delegare oppure richiedere una modifica.

### <a name="approve"></a>Approvare

Quando un approvatore approva un documento, questo viene assegnato all'utente successivo nel flusso di lavoro, se presente. Se non è richiesta un'ulteriore elaborazione, il processo del flusso di lavoro viene completato.

Si supponga ad esempio che Giorgio abbia presentato un documento pari a USD 6.000 assegnato a Ezio. Quando Ezio approva il documento, questo viene assegnato a Luisa per l'approvazione. Dopo che Luisa ha approvato la nota spese, il processo del flusso di lavoro termina.

### <a name="reject"></a>Rifiuta

Quando un approvatore rifiuta un documento, il processo del flusso di lavoro viene completato.

Si supponga ad esempio che Giorgio abbia presentato un documento pari a USD 12.000 assegnato a Luisa. Se Luisa rifiuta la nota spese, il processo del flusso di lavoro viene completato.

Giorgio può quindi inviare di nuovo la nota spese. È possibile apportare le modifiche richieste prima, oppure può inviare la versione originale della nota spese. Se Giorgio presenta di nuovo la nota spese, il processo del flusso di lavoro viene avviato dal processo di approvazione.

### <a name="delegate"></a>Delegare

Quando un approvatore delega un documento, quest'ultimo viene assegnato a un altro utente per l'approvazione.

Si supponga ad esempio che Giorgio abbia presentato un documento pari a USD 12.000 assegnato a Ezio. Ezio delega la nota spese a Elena.

Elena agisce quindi per conto di Ezio. Ciò significa che dopo l'approvazione da parte di Elena, il documento verrà assegnato a Luisa per l'approvazione, come se fosse stato approvato da Ezio. Dopo che Luisa avrà approvato il documento, verrà inviato a Elena per l'approvazione.

### <a name="request-change"></a>Richiedi modifica

Quando un approvatore richiede una modifica di un documento, quest'ultimo viene inviato di nuovo all'iniziatore.

Si supponga ad esempio che Giorgio abbia presentato un documento pari a USD 12.000 assegnato a Luisa. Se Luisa richiede una modifica, la nota spese viene restituita a Giorgio.

Giorgio può quindi inviare di nuovo la nota spese. È possibile apportare le modifiche richieste prima, oppure può inviare la versione originale della nota spese. Se Giorgio presenta di nuovo la nota spese, questa viene inviata a Ezio per l'approvazione, in quanto Ezio è il primo approvatore nel processo di approvazione.
