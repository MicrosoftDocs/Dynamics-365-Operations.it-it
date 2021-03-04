---
title: flusso di lavoro delle richieste di acquisto
description: Il processo del flusso di lavoro fa avanzare le richieste di acquisto nei vari passaggi della procedura di revisione, dallo stato iniziale di Bozza fino allo stato finale di Approvata. Nel momento in cui si crea e si invia una richiesta di acquisto per la revisione, ha inizio il processo del flusso di lavoro. In seguito all'approvazione della richiesta di acquisto, è possibile generare un ordine fornitore per le righe della richiesta di acquisto e inviarlo al fornitore per evasione dell'ordine.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, WorkflowParticipantExpenToken
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2234
ms.assetid: dad3ba5a-2892-45d2-874a-300896f59b34
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a9dceb3f9e71163dcaf8b8763317110ef019844
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430994"
---
# <a name="purchase-requisition-workflow"></a>flusso di lavoro delle richieste di acquisto

[!include [banner](../includes/banner.md)]

Il processo del flusso di lavoro fa avanzare le richieste di acquisto nei vari passaggi della procedura di revisione, dallo stato iniziale di Bozza fino allo stato finale di Approvata. Nel momento in cui si crea e si invia una richiesta di acquisto per la revisione, ha inizio il processo del flusso di lavoro. In seguito all'approvazione della richiesta di acquisto, è possibile generare un ordine fornitore per le righe della richiesta di acquisto e inviarlo al fornitore per evasione dell'ordine.

Prima di poter inviare una richiesta di acquisto per la revisione, è necessario configurare un flusso di lavoro. Il processo del flusso di lavoro può includere uno o più passaggi di revisione in qualsiasi ordine. Il processo del flusso di lavoro può anche essere configurato in modo da ignorare le attività di revisione e da approvare automaticamente la richiesta di acquisto. È possibile configurare il processo del flusso di lavoro per inoltrare la richiesta di acquisto come singolo documento oppure è possibile inoltrare righe singole di richiesta di acquisto agli opportuni revisori. È inoltre possibile creare uno scenario in cui la richiesta di acquisto viene inviata come documento singolo ad alcuni revisori, mentre ad altri revisori vengono inviate specifiche righe della richiesta di acquisto.  

Se le righe della richiesta di acquisto vengono revisionate singolarmente, si dovrà completare il processo di revisione per tutte le righe della richiesta di acquisto prima che il processo dei flussi di lavoro possa passare alla fase successiva e prima che il processo di revisione dell'intera richiesta di acquisto possa essere completato. Dopo il completamento del processo di revisione della richiesta di acquisto e di tutte le righe, lo stato complessivo della richiesta di acquisto viene aggiornato in **Approvata**.  

È possibile configurare il flusso di lavoro in modo che rappresenti il processo aziendale per le richieste di acquisto nell'organizzazione. Quando si configura il processo del flusso di lavoro per le richieste di acquisto, considerare le seguenti questioni:

-   Le spese da rivedere.
-   Le spese che possono essere approvate automaticamente.
-   Chi dovrà rivedere e approvare le richieste di spesa. A quale ruolo sono assegnati questi utenti.
-   Quale processo deve essere seguito se un revisore non è disponibile?

Negli esempi seguenti vengono illustrati due modi in cui è possibile configurare un flusso di lavoro per le richieste di acquisto.

## <a name="example-1-route-a-purchase-requisition-as-a-single-document-for-review"></a>Esempio 1: indirizzare una richiesta di acquisto come documento singolo per la revisione
La figura di seguito mostra i possibili passaggi di una richiesta di acquisto nel contesto del processo di revisione del flusso di lavoro come singolo documento. Le righe della richiesta di acquisto non vengono inviate singolarmente. I ruoli seguenti sono inclusi nel processo del flusso di lavoro per questo esempio:

-   **Richiedente**: utente che richiede gli articoli o i servizi. Il richiedente può preparare la richiesta di acquisto oppure può prepararla un altro lavoratore per conto del richiedente. Questo lavoratore è detto preparatore. Il preparatore è responsabile della gestione della richiesta di acquisto durante l'intero processo di revisione. Solo il preparatore della richiesta di acquisto può modificarla.

**Nota:** è necessario concedere a un lavoratore le autorizzazioni appropriate affinché possa creare una richiesta di acquisto per conto di altri. Utilizzare la pagina **Autorizzazione richieste di acquisto** per impostare le autorizzazioni.

-   **Addetto acquisti**: utente che esegue una revisione dell'approvvigionamento e può approvare il documento.
-   **Il superiore del richiedente**: utente che esegue una revisione manageriale e può approvare il documento.

![Processo di revisione del flusso di lavoro della richiesta di acquisto](./media/purchreqworkflowoverview_submission.gif)  
In questo esempio il processo del flusso di lavoro per la richiesta di acquisto include i passaggi seguenti:

1.  Il preparatore invia una richiesta di acquisto per la revisione.
2.  L'addetto acquisti riceve una notifica. Tramite la notifica all'addetto acquisti viene chiesto di verificare i dati contenuti nella richiesta di acquisto. In caso di eventuali informazioni obbligatorie mancanti, l'addetto acquisti può aggiungerle o restituire la richiesta di acquisto al preparatore affinché le aggiunga. Una volta inserite tutte le informazioni obbligatorie, la richiesta di acquisto può avanzare al passaggio successivo del processo di revisione.
3.  Il superiore del richiedente rivede la richiesta di acquisto. La richiesta di acquisto potrebbe essere inviata al superiore del richiedente se, ad esempio, l'importo della richiesta di acquisto supera il limite di spesa per le richieste di acquisto. Il superiore del richiedente può approvare o rifiutare la richiesta di acquisto oppure restituirla al preparatore per le modifiche.

## <a name="example-2-route-the-individual-purchase-requisition-lines-for-review"></a>Esempio 2: indirizzare le singole righe della richiesta di acquisto per la revisione
L'esempio della figura che segue mostra la modalità di invio delle singole righe di una richiesta di acquisto in un flusso di lavoro. In generale, il processo per ogni riga è lo stesso del processo di una richiesta di acquisto sottoposta a revisione come documento singolo. Prima che il flusso di lavoro possa essere completato per l'intera richiesta di acquisto, è tuttavia necessario che il processo del flusso di lavoro venga completato individualmente per ogni riga.  

In questo esempio un lavoratore immette una richiesta per poster e T-shirt per una campagna di marketing. Il costo dei poster viene suddiviso tra il reparto marketing e il reparto vendite. Se il costo dei poster o delle T-shirt supera l'autorizzazione di limite di firma per i responsabili di reparto, la richiesta di acquisto dovrà essere rivista dal responsabile del gruppo.  

I ruoli seguenti sono inclusi nel processo del flusso di lavoro per questo esempio:

-   **Richiedente**: utente che richiede gli articoli o i servizi. Il richiedente può preparare la richiesta di acquisto oppure può prepararla un altro lavoratore per conto del richiedente. Questo lavoratore è detto preparatore. Il preparatore è responsabile della gestione della richiesta di acquisto durante l'intero processo di revisione. Solo il preparatore della richiesta di acquisto può modificarla.

**Nota:** è necessario concedere a un lavoratore le autorizzazioni appropriate affinché possa creare una richiesta di acquisto per conto di altri. Utilizzare la pagina **Autorizzazione richieste di acquisto** per impostare le autorizzazioni.

-   **Addetto acquisti**: utente che esegue una revisione dell'approvvigionamento e può approvare il documento.
-   **Il superiore del richiedente**: utente che esegue una revisione manageriale e può approvare il documento.
-   **Responsabile reparto**: utente che esegue una revisione di spesa e può approvare il documento.
-   **Responsabile gruppo**: utente che esegue una revisione di autorizzazione della firma e può approvare il documento.

![Processo di revisione del flusso di lavoro per la righe della richiesta di acquisto](./media/purchreqlineworkflowoverview.gif)  
In questo esempio il processo del flusso di lavoro per le righe della richiesta di acquisto include i passaggi seguenti:

1.  Il preparatore invia una richiesta di acquisto per la revisione. Ogni riga viene inviata al revisore configurato per riceverla nel processo del flusso di lavoro.
2.  L'addetto acquisti riceve una notifica. Tramite la notifica all'addetto acquisti viene chiesto di verificare che i dati nella richiesta di acquisto e nelle righe della richiesta di acquisto. Quando la richiesta di acquisto viene aperta dall'addetto acquisti tutte le righe sono visibili, ma un indicatore visivo mostra le righe che sono state inviate all'addetto acquisti per la revisione. In caso di eventuali informazioni obbligatorie mancanti, l'addetto acquisti può aggiungerle o restituire una riga della richiesta di acquisto al preparatore affinché la aggiunga. Una volta inserite tutte le informazioni obbligatorie, la riga della richiesta di acquisto può avanzare al passaggio successivo del processo di revisione. Le righe della richiesta di acquisto possono continuare ad avanzare nel processo di revisione indipendentemente le une dalle altre.
3.  Il superiore del richiedente rivede e approva le righe della richiesta di acquisto. L'approvazione potrebbe essere inviata al superiore del richiedente se, ad esempio, l'importo in una riga della richiesta di acquisto supera il limite di spesa per le righe delle richieste di acquisto. Il superiore può approvare o rifiutare una o entrambe le righe della richiesta di acquisto.
4.  Il responsabile del reparto marketing rivede le righe della richiesta di acquisto per i poster e le T-shirt. Il responsabile del reparto vendite rivede la riga della richiesta di acquisto solo per i poster, essendo questo il solo costo addebitato al reparto vendite.
5.  Il responsabile del gruppo rivede e approva la riga della richiesta di acquisto per le T-shirt solo se l'approvazione del responsabile del gruppo è necessaria perché, ad esempio, l'importo della riga della richiesta di acquisto supera il limite di approvazione del responsabile reparto. Non è necessario che il responsabile del gruppo approvi la riga della richiesta di acquisto per i poster.

> [!NOTE]
> La valuta di sistema deve essere impostata se il flusso di lavoro dell'intestazione per una richiesta di acquisto richiede le approvazioni relative ai limiti di firma.

## <a name="configuring-a-workflow-for-purchase-requisitions"></a>Configurazione di un flusso di lavoro per le richieste di acquisto
Per inviare una richiesta di acquisto per la revisione, è necessario configurare i processi del flusso di lavoro della richiesta di acquisto. Il processo del flusso di lavoro definito consente di controllare l'interazione tra l'utente che ha richiesto gli articoli (il richiedente) e il revisore e l'approvatore nel flusso di lavoro. L'invio della richiesta di acquisto dipende dalle condizioni specificate nella configurazione del flusso di lavoro. Ad esempio, queste condizioni determinano il momento in cui la richiesta di acquisto deve essere inviata, l'utente o il ruolo a cui deve essere indirizzata e le azioni che gli utenti possono eseguire.  

Negli esempi inclusi in questo argomento viene illustrato come è possibile inviare una richiesta di acquisto tramite un flusso di lavoro come documento singolo o come singole righe della richiesta di acquisto. È inoltre possibile configurare un flusso di lavoro per le richieste di acquisto che rifletta il processo di revisione per i controlli interni delle richieste di acquisto definito nell'organizzazione.  

I partecipanti o i revisori cui è assegnata un'attività in un flusso di lavoro possono essere membri di un gruppo specifico di utenti, di utenti con un ruolo di sicurezza specifico, di utenti associati all'autore dell'invio in una gerarchia direttiva, di utenti denominati o di utenti che dispongono di responsabilità specifiche di spesa.

### <a name="purchase-requisition-expenditure-reviewers"></a>Revisori spese richieste fornitore

Le configurazioni del revisore spese consentono di inviare le spese per la revisione in modo dinamico in base all'utente assegnato a un ruolo di progetto o a una dimensione finanziaria cui viene addebitata la spesa. Per determinare la persona cui inviare la spesa, il processo del flusso di lavoro fa riferimento al ruolo di progetto o al proprietario della dimensione finanziaria specificato.  

È possibile definire una o più configurazioni del revisore spese, quindi selezionare una configurazione durante la creazione di un flusso di lavoro. È possibile configurare i valori del revisore spese per ogni persona giuridica dell'organizzazione. Dopo aver definito le configurazioni del revisore spese, è possibile assegnare una configurazione all'attività del flusso di lavoro.  

Non è necessario definire configurazioni del revisore spese. È possibile invece assegnare utente o gruppi di utenti specifici come revisori quando si definisce il flusso di lavoro. In presenza tuttavia di un'organizzazione complessa, i revisori spese possono contribuire a migliorare l'efficienza del processo di approvazione, Inoltre, se si impostano i revisori spese, non è necessario aggiornare le assegnazioni dei revisori del flusso di lavoro ogni volta che un revisore cambia i ruoli di processo.  

È possibile impostare i revisori spese nella pagina **Revisori spese per la richiesta di acquisto**. Creare una configurazione del revisore spese e immettere i valori per ogni persona giuridica dell'organizzazione. Per le richieste di acquisto assegnate a un progetto, è possibile specificare il ruolo responsabile della revisione delle richieste di acquisto: controller di progetto, manager di progetto o responsabile vendite di progetto. Le spese verranno inviate all'utente assegnato al ruolo specificato. È inoltre possibile inviare la spesa al proprietario della dimensione finanziaria selezionando l'opzione appropriata relativa alla dimensione finanziaria nella scheda **Distribuzioni organizzazione**.  

Per utilizzare uno dei revisori spese definiti in un flusso di lavoro, è necessario impostare l'opzione **Tipo di partecipante** su **Partecipanti alla spesa** nelle proprietà **Assegnazione** dell'elemento del flusso di lavoro rilevante.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Creare una richiesta per il consumo](tasks/create-requisition-consumption.md)

[Definizione di flussi di lavoro di processi aziendali per le richieste di acquisto](https://www.microsoft.com/download/details.aspx?id=101821)

[Flussi di lavoro di approvvigionamento](procurement-sourcing-workflows.md)

[Panoramica delle richieste di acquisto](purchase-requisitions-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]