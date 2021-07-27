---
title: Flussi di lavoro di approvazione del giornale di registrazione magazzino
description: In questo argomento viene descritto come configurare e usare i flussi di approvazione del giornale di registrazione magazzino per i diversi tipi di transazioni dell'inventario fisico. I flussi di lavoro del giornale di registrazione magazzino aiutano a garantire che solo i giornali di registrazione magazzino approvati possano essere registrati nelle transazioni.
author: sherry-zheng
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTableWorkflowDropDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: bcb242214efab3fd632ea0b9e0f3329bb7821dc0
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354763"
---
# <a name="inventory-journal-approval-workflows"></a>Flussi di lavoro di approvazione del giornale di registrazione magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come configurare e usare i flussi di approvazione del giornale di registrazione magazzino per i diversi tipi di transazioni dell'inventario fisico, ad esempio le uscite ed entrate, i movimenti inventario, la creazione delle distinte base (DBA) e la riconciliazione dell'inventario fisico. I flussi di lavoro del giornale di registrazione magazzino aiutano a garantire che solo i giornali di registrazione magazzino approvati possano essere registrati nelle transazioni.

> [!NOTE]
> I flussi di lavoro di approvazione del giornale di registrazione magazzino si applicano solo alle transazioni registrate utilizzando il modulo Gestione articoli. Non funzionano con i giornali di registrazione magazzino attivati dal modulo Gestione magazzino.

## <a name="turn-on-the-inventory-journal-approval-workflows-feature"></a>Attivare la funzionalità dei flussi di lavoro di approvazione del giornale di registrazione magazzino

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione articoli e magazzino*
- **Nome funzionalità:** *Flusso di lavoro di approvazione del giornale di registrazione inventario*

## <a name="create-your-inventory-journal-approval-workflows"></a>Creare i flussi di lavoro di approvazione del giornale di registrazione magazzino

Per impostare questa funzione, è necessario creare un flusso di lavoro per ciascuno dei tipi di giornali di registrazione magazzino che si desidera controllare. Poiché diversi tipi di giornali di registrazione magazzino possono avere gerarchie di approvazione e passaggi del flusso di lavoro diversi, è possibile configurare singoli flussi di lavoro per ciascun tipo di giornale di registrazione magazzino.

I flussi di lavoro supportano il controllo della versione e ognuno ha un ID flusso di lavoro e una versione attiva. È possibile scegliere di attivare ogni nuova versione del flusso di lavoro immediatamente dopo la creazione o mantenerla inattiva. Se sono necessari flussi di lavoro diversi per lo stesso tipo di giornale di registrazione, creare più flussi di lavoro per quel tipo di giornale di registrazione e quindi assegnare ciascuno di questi a un nome di giornale di registrazione diverso che utilizza quel tipo.

Per creare i flussi di lavoro di approvazione del giornale di registrazione magazzino:

1. Andare a **Gestione articoli \> Impostazioni\> Flussi di lavoro gestione articoli**.
1. Nel Riquadro azioni seleziona **Nuovo**.
1. Scegliere il tipo di giornale di registrazione magazzino per cui configurare un flusso di lavoro:
    - **Giornale di registrazione conteggio tag scorte**
    - **Giornale di registrazione modifiche proprietà inventario**
    - **Giornale di registrazione movimenti scorte**
    - **Giornale di registrazione trasferimento scorte**
    - **Giornale di registrazione conteggi scorte**
    - **Giornale di registrazione DBA magazzino**
    - **Giornale di registrazione di rettifica magazzino**

    ![La finestra di dialogo Crea flusso di lavoro.](media/journal-workflow-create-workflow.png "La finestra di dialogo Crea flusso di lavoro")

1. L'app dell'editor del flusso di lavoro viene avviata sul computer. (È possibile che venga richiesto di approvare questa azione.) Usarla per progettare il flusso di lavoro in base alle necessità. Per i dettagli su come utilizzare l'editor del flusso di lavoro, vedere [Panoramica del sistema di flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).
1. Dopo aver salvato e chiuso l'app dell'editor del flusso di lavoro, è necessario scegliere se attivare questa versione del flusso di lavoro o mantenerla inattiva.

> [!NOTE]
> I flussi di lavoro forniscono il controllo della versione, il che significa che è possibile visualizzare un elenco di versioni create e scegliere quale è attiva. Per visualizzare l'elenco delle versioni disponibili e scegliere quale attivare, selezionare un flusso di lavoro elencato nella pagina **Flussi di lavoro gestione articoli**. Nel riquadro azioni, aprire la scheda **Flusso di lavoro** e selezionare **Versioni**. È possibile attivare una sola versione alla volta per ciascun ID flusso di lavoro.

## <a name="assign-approval-workflows-to-inventory-journal-names"></a>Assegnare flussi di lavoro di approvazione a nomi del giornale di registrazione magazzino

Il passaggio successivo consiste nell'assegnare un flusso di lavoro del giornale di registrazione magazzino a ciascun nome del giornale di registrazione magazzino. Per ciascun tipo di giornale di registrazione magazzino, è possibile configurare più nomi di giornali di registrazione magazzino.

Per associare un flusso di lavoro del giornale di registrazione magazzino al nome di un giornale di registrazione magazzino:

1. Andare a **Gestione articoli \> Impostazioni \> Nomi giornale di registrazione \> Inventario**.
1. Selezionare il nome di un giornale di registrazione dalla colonna dell'elenco per aprire la relativa pagina delle impostazioni.
1. Nella Scheda dettaglio **Generale**, impostare **Flusso di lavoro di approvazione** su **Sì**. Se viene richiesto di approvare l'azione, selezionare **Sì**.

    ![Assegnare un flusso di lavoro al nome di un giornale di registrazione.](media/journal-workflow-journal-name.png "Assegnare un flusso di lavoro al nome di un giornale di registrazione")

1. Aprire l'elenco a discesa **Flusso di lavoro** e selezionare il flusso di lavoro appropriato. L'elenco mostra ogni flusso di lavoro attivo creato usando l'app dell'editor del flusso di lavoro.

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a>Creare un giornale di registrazione magazzino e inviarlo per l'approvazione

Dopo aver associato un nome di giornale di registrazione magazzino al relativo flusso di lavoro di approvazione del giornale di registrazione magazzino, sarà possibile creare nuovi giornali di registrazione magazzino che utilizzano quel nome e quindi inviarli per l'approvazione utilizzando quel flusso di lavoro. Non sarà possibile registrare il giornale di registrazione magazzino fino a quando non sarà stato approvato dagli approvatori configurati nel flusso di lavoro.

1. Nel riquadro di navigazione, espandere **Gestione articoli \> Inserimenti nel giornale di registrazione \> Articoli** e quindi selezionare un tipo di giornale di registrazione magazzino.
1. Selezionare **Nuovo** per creare un nuovo giornale di registrazione del tipo selezionato.
1. Si apre la finestra di dialogo **Crea giornale di registrazione inventario**. Compilare il modulo come richiesto e selezionare **OK** per salvare il giornale di registrazione.
1. Completare il giornale di registrazione come richiesto.
1. Quando si crea o si apre un giornale di registrazione magazzino a cui è associato un flusso di lavoro di approvazione, il pulsante **Flusso di lavoro** sarà attivo nel riquadro azioni. Quando si è pronti per inviare il giornale di registrazione per l'approvazione, selezionare il pulsante **Flusso di lavoro** per aprire una finestra di dialogo a discesa, quindi selezionare **Invia**. La richiesta di approvazione verrà quindi indirizzata al responsabile dell'approvazione pertinente, che verrà avvisato utilizzando il metodo di notifica configurato per il flusso di lavoro.

    ![Sottoporre un giornale di registrazione ad approvazione.](media/journal-workflow-inventory-journal.png "Sottoporre un giornale di registrazione ad approvazione")

Per richiamare una richiesta di approvazione, aprire il giornale di registrazione pertinente, selezionare il pulsante **Flusso di lavoro** e quindi selezionare **Richiama**. Ciò ripristinerà il flusso di lavoro.

Quando il giornale di registrazione è stato approvato, sarà possibile registrarlo. Per registrare il giornale, selezionare **Registra** dal riquadro azioni. Se il pulsante **Registra** non è attivo, il giornale di registrazione non è stato ancora approvato.

## <a name="respond-to-an-inventory-journal-approval-request"></a>Rispondere a una richiesta di approvazione del giornale di registrazione magazzino

Il responsabile approvazione dovrebbe ricevere un messaggio ogni volta che è necessaria la sua approvazione (come configurato nel flusso di lavoro pertinente). Quindi può approvare o rifiutare una richiesta di approvazione del giornale di registrazione procedendo come segue:

1. Nel riquadro di navigazione, espandere **Gestione articoli \> Inserimenti nel giornale di registrazione \> Articoli** e quindi selezionare un tipo di giornale di registrazione magazzino.
1. Aprire il giornale di registrazione pertinente ed esaminarlo.
1. Selezionare il pulsante **Flusso di lavoro** nel riquadro azioni per aprire una finestra di dialogo a discesa. Selezionare una delle seguenti opzioni:
    - **Approva**: per approvare la richiesta.
    - **Rifiuta**: per rifiutare la richiesta.
    - **Altro \> Richiedi modifica**: per inviare un messaggio al richiedente chiedendo di cambiare qualcosa di specifico e inviare nuovamente.
    - **Altro \> Delega**: per delegare l'approvazione a un altro utente.
    - **Altro \> Richiama**: per richiamare la richiesta di approvazione (reimposta il flusso di lavoro).
    - **Altro \> Storico flusso di lavoro**: per visualizzare lo storico di questo flusso di lavoro di approvazione.

## <a name="review-the-approval-history"></a>Rivedere lo storico delle approvazioni

Come con altri tipi di flussi di lavoro, è possibile utilizzare la pagina **Storico flusso di lavoro** per visualizzare lo storico del flusso di lavoro di approvazione per qualsiasi giornale di registrazione.

Per rivedere lo storico del flusso di lavoro per un giornale di registrazione:

1. Nel riquadro di navigazione, espandere **Gestione articoli \> Inserimenti nel giornale di registrazione \> Articoli** e quindi selezionare un tipo di giornale di registrazione magazzino.
1. Aprire il giornale di registrazione rilevante.
1. Selezionare il pulsante **Flusso di lavoro** nel riquadro azioni per aprire una finestra di dialogo a discesa. Selezionare **Storico flusso di lavoro**. Per ulteriori informazioni, vedere [Visualizzare lo storico flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md)..


[!INCLUDE[footer-include](../../includes/footer-banner.md)]