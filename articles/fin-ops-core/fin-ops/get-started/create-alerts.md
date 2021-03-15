---
title: Creare regole di avviso
description: In questo argomento vengono fornite informazioni sugli avvisi e viene descritto come creare una regola di avviso in modo da essere informati sugli eventi come una data in arrivo o una specifica modifica.
author: tjvass
manager: AnnBe
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 3721416ce720167a6f78e26583de84af9c8d086b
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798429"
---
# <a name="create-alert-rules"></a>Creare regole di avviso

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Introduzione

Prima di impostare una regola di avviso, è necessario decidere quando o in quali situazioni si desidera ricevere avvisi. Dopo avere individuato l'evento per il quale si desidera ricevere una notifica, trovare la pagina in cui vengono visualizzati i dati che causano l'evento. L'evento può essere una data prossima o una specifica modifica che si verificherà. Di conseguenza, è necessario individuare la pagina in cui è specificata la data o dove viene visualizzato il campo che cambia o il nuovo record creato. Una volta ottenute queste informazioni, sarà possibile creare la regola di avviso.

Quando si crea una regola di avviso, si definiscono i criteri che devono essere soddisfatti prima dell'attivazione di un avviso. I criteri sono fondamentalmente la corrispondenza tra il verificarsi di un evento e la soddisfazione di specifiche condizioni. Quando si verifica un evento, il sistema inizia a effettuare una verifica in base alle condizioni impostate.

## <a name="ensure-the-alert-batch-jobs-are-running"></a>Assicurarsi che i processi batch di avviso siano in esecuzione

I processi batch per la modifica dei dati e gli avvisi di scadenza devono essere in esecuzione per l'elaborazione delle condizioni di avviso e l'invio delle notifiche. Per eseguire i processi batch, andare ad **Amministrazione sistema** > **Attività periodiche** > **Avvisi** e aggiungere un nuovo processo batch per **Avvisi basati su modifica** e/o **Avvisi data di scadenza**. Se è necessario un processo batch lungo e spesso in esecuzione, selezionare **Ricorrenza** e impostare **Nessuna data di fine** con un **Modello di ricorrenza** di **Minuti** e un **Conteggio** di **1**.

## <a name="events"></a>Eventi

L'evento che attiva una regola di avviso può essere una data prossima o un cambiamento specifico che si verificherà. I trigger per eventi sono definiti nella Scheda dettaglio **Invia avviso quando** della finestra di dialogo **Crea regola di avviso**. Gli eventi disponibili per un determinato campo dipendono dall'attivazione selezionata.

Ad esempio, se si imposta una regola di avviso per il campo **Data di inizio**, sono appropriati gli eventi generati dalla data di scadenza. Di conseguenza, il tipo di evento `is due in` è disponibile per tale campo. Tuttavia, per un campo come **Centro di costo** un evento basato sulla data di scadenza non è appropriato. Di conseguenza, il tipo di evento `is due in` non è disponibile per quel campo. Tuttavia, sarà disponibile il tipo di evento `has changed`.

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

Nella Scheda dettaglio **Invia avviso con** della finestra di dialogo **Crea regola di avviso**, è possibile specificare l'utente destinatario dei messaggi di avviso. Per impostazione predefinita, è selezionato il proprio ID utente. La possibilità di modificare l'utente che riceve l'avviso è limitata agli amministratori dell'organizzazione.

## <a name="alerts-as-business-events"></a>Avvisi come eventi aziendali

Gli avvisi possono essere inviati esternamente utilizzando il framework degli eventi aziendali. Quando si crea un avviso, impostare **A livello di organizzazione** su **No** e impostare **Invia esternamente** su **Sì**. Dopo aver ricevuto l'avviso che attiva l'evento aziendale, è possibile attivare un flusso integrato in Power Automate usando il trigger **Quando si verifica un evento aziendale** sul connettore Finance and Operations o inviare esplicitamente l'evento a un endpoint di eventi aziendali tramite il **Catalogo degli eventi aziendali**.

## <a name="create-an-alert-rule"></a>Crea una regola di avviso

0. Assicurarsi che i processi batch di avviso siano in esecuzione (vedere sopra).
1. Aprire la pagina contenente i dati da monitorare.
2. Nel riquadro azioni della scheda **Opzioni** del gruppo **Condividi**, selezionare **Crea regola di avviso**.
3. Nella finestra di dialogo **Crea regola di avviso**, nel campo **Campo**, selezionare il campo da monitorare.
4. Nel campo **Evento**, selezionare il tipo di evento.
5. Nella Scheda dettaglio **Invia avviso per**, selezionare l'opzione desiderata. Se si desidera inviare l'avviso come evento aziendale, impostare il valore **A livello di organizzazione** su **No**.
6. Se si desidera che la regola di avviso diventi inattiva in corrispondenza di una data specifica, selezionare una data di fine nella Scheda dettaglio **Invia avviso fino a**.
7. Nella Scheda dettaglio **Invia avviso con**, nel campo **Oggetto**, accettare la voce indice predefinita per il messaggio di posta elettronica o immettere un nuovo oggetto. Il testo diventa voce indice del messaggio di posta elettronica che si riceve quando viene attivato un avviso. Se si desidera inviare l'avviso come evento aziendale, impostare **Invia esternamente** su **Sì**.
8. Nel campo **Messaggio**, immettere un messaggio facoltativo. Il testo diventa il messaggio ricevuto quando un avviso viene attivato.
9. Selezionare **OK** per salvare le impostazioni e creare la regola di avviso.

## <a name="limitations-and-workarounds"></a>Limitazioni e soluzioni alternative

### <a name="workaround-for-creating-alerts-for-the-secondary-data-sources-of-a-form"></a>Soluzione alternativa per la creazione di avvisi per le origini dati secondarie di un modulo
Non è possibile creare avvisi per alcune origini dati secondarie nei moduli. Ad esempio, quando si creano avvisi nel modulo dei profili di registrazione di clienti o fornitori, sono disponibili solo i campi nell'intestazione (CustLedger o VendLedger) e non i conti dimensione. La soluzione alternativa per questa limitazione è utilizzare **SysTableBrowser** per aprire la tabella come origine dati primaria. 
1. Apri la tabella nel modulo **SysTableBrowser**.
    ```
        https://<EnvironmentURL>/?cmp=USMF&mi=SysTableBrowser&TableName=<TableName>
    ```
2. Crea un avviso con il modulo SysTableBrowser.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]