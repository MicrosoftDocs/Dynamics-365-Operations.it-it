---
title: Creare regole di avviso
description: In questo argomento vengono fornite informazioni sugli avvisi e viene descritto come creare una regola di avviso in modo da essere informati sugli eventi come una data in arrivo o una specifica modifica.
author: tjvass
manager: AnnBe
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: cbf4917424e72a70a6d513b5daf45f6bf9cd57c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549677"
---
# <a name="create-alert-rules"></a>Creare regole di avviso

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Introduzione

Prima di impostare una regola di avviso, è necessario decidere quando o in quali situazioni si desidera ricevere avvisi. Dopo avere individuato l'evento per il quale si desidera ricevere una notifica, in Microsoft Dynamics 365 for Finance and Operations, trovare la pagina in cui vengono visualizzati i dati che causano l'evento. L'evento può essere una data prossima o una specifica modifica che si verificherà. Di conseguenza, è necessario individuare la pagina in cui è specificata la data o dove viene visualizzato il campo che cambia o il nuovo record creato. Una volta ottenute queste informazioni, sarà possibile creare la regola di avviso.

Quando si crea una regola di avviso, si definiscono i criteri che devono essere soddisfatti prima dell'attivazione di un avviso. È possibile considerare i criteri come una corrispondenza tra il verificarsi di un evento e la soddisfazione di specifiche condizioni. Quando si verifica un evento, il sistema inizia a effettuare una verifica in base alle condizioni impostate in Finance and Operations.

## <a name="events"></a>Eventi

L'evento che attiva una regola di avviso può essere una data prossima o un cambiamento specifico che si verificherà. I trigger per eventi sono definiti nella Scheda dettaglio **Invia avviso quando** della finestra di dialogo **Crea regola di avviso**. Gli eventi disponibili per un determinato campo dipendono dall'attivazione selezionata.

Ad esempio, se si imposta una regola di avviso per il campo **Data di inizio**, sono appropriati gli eventi generati dalla data di scadenza. Di conseguenza, il tipo di evento **in scadenza il** è disponibile per quel campo. Tuttavia, per un campo come **Centro di costo** un evento basato sulla data di scadenza non è appropriato. Di conseguenza, il tipo di evento **in scadenza il** non è disponibile per quel campo. Il tipo di evento **è stato modificato** è invece disponibile.

## <a name="event-types"></a>Tipi di evento

Possono verificarsi tre tipi di eventi:

- **Eventi di tipo di creazione e di tipo eliminazione** - Questi eventi attivano un avviso quando viene creato o eliminato un record.
- **Eventi di tipo aggiornamento** - Questi eventi attivano un avviso quando cambiano i dati in un campo specifico.
- **Eventi di tipo data di scadenza** - Questi eventi attivano un avviso all'arrivo di una data.
    
Le modifiche che si verificano possono essere eseguite da un utente. Ad esempio, un utente modifica la data di consegna di un ordine fornitore. In alternativa, le modifiche possono verificarsi come parte di un processo. Ad esempio, il campo **Stato** nella pagina viene modificato per riflettere il ciclo di vita di diversi processi nel sistema.

## <a name="conditions"></a>Condizioni

Nella Scheda dettaglio **Invia avviso** della finestra di dialogo **Crea regola di avviso**, è possibile utilizzare condizioni per controllare quando si viene avvisati del verificarsi di eventi.

Ad esempio, è possibile impostare il sistema in modo che avvisi quando lo stato degli ordini fornitore viene modificato, ma solo se lo stato corrisponde a un set di condizioni specifico. In particolare, si intende essere avvisati quando lo stato di un ordine fornitore è impostato su **Ricevuto**. Questa modifica nello stato è l'evento che attiva l'avviso.

Successivamente, è necessario decidere per quali ordini fornitore si desidera ricevere notifiche. Ad esempio, è possibile selezionare una delle opzioni riportate di seguito. Queste opzioni definiscono le condizioni per la regola di avviso.

- **Record selezionato corrente** - Si riceve un avviso quando lo stato di un ordine fornitore specifico cambia in **Ricevuto**.
- **Tutti i record** - Si riceve un avviso quando lo stato di un ordine fornitore viene modificato per un articolo nella visualizzazione della pagina attiva. È possibile utilizzare il filtro avanzato disponibile nella pagina per creare regole per uno specifico set di record. Ad esempio, è possibile creare un avviso che viene attivato per tutti gli ordini fornitore per i clienti appartenenti a un gruppo di clienti specifico.
    
## <a name="expiry-of-rule"></a>Scadenza della regola

Nella Scheda dettaglio **Invia avviso fino a** della finestra di dialogo **Crea regola di avviso**, è possibile specificare per quanto tempo deve essere attiva la regola di avviso.

## <a name="alert-contents"></a>Contenuti dell'avviso

Nella Scheda dettaglio **Invia avviso con** della finestra di dialogo **Crea regola di avviso**, è possibile specificare l'oggetto e il testo del messaggio utilizzati nei messaggi di avviso.

## <a name="user-id"></a>ID utente

Nella Scheda dettaglio **Invia avviso con** della finestra di dialogo **Crea regola di avviso**, è possibile specificare l'utente destinatario dei messaggi di avviso. Per impostazione predefinita, è selezionato il proprio ID utente. Questa opzione è limitata agli amministratori dell'organizzazione.

## <a name="create-an-alert-rule"></a>Crea una regola di avviso

1. Aprire la pagina contenente i dati da monitorare.
2. Nel riquadro azioni della scheda **Opzioni** del gruppo **Condividi**, selezionare **Crea regola di avviso**.
3. Nella finestra di dialogo **Crea regola di avviso**, nel campo **Campo**, selezionare il campo da monitorare.
4. Nel campo **Evento**, selezionare il tipo di evento.
5. Nella Scheda dettaglio **Invia avviso per**, selezionare un'opzione.
6. Se si desidera che la regola di avviso diventi inattiva in corrispondenza di una data specifica, selezionare una data di fine nella Scheda dettaglio **Invia avviso fino a**.
7. Nella Scheda dettaglio **Invia avviso con**, nel campo **Oggetto**, accettare la voce indice predefinita per il messaggio di posta elettronica o immettere un nuovo oggetto. Il testo è utilizzato come voce indice del messaggio di posta elettronica che si riceve quando viene attivato un avviso.
8. Nel campo **Messaggio**, immettere un messaggio facoltativo. Il testo viene utilizzato come il messaggio ricevuto quando un avviso viene attivato.
9. Selezionare **OK** per salvare le impostazioni e creare la regola di avviso.
