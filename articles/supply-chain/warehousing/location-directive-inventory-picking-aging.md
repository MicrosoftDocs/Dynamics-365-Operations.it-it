---
title: Aging prelievo scorte per direttiva ubicazione
description: Questo argomento spiega come utilizzare le strategie della direttiva di ubicazione first in, first out (FIFO) e last in, first out (LIFO) durante il prelievo.
author: mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8a08b1582ee5edba019031a687dba375a195d661484c0f0bdd2983fed2a0d6cd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714188"
---
# <a name="location-directive-inventory-picking-aging"></a>Aging prelievo scorte per direttiva ubicazione

[!include [banner](../includes/banner.md)]

Questo argomento spiega come utilizzare le strategie della direttiva di ubicazione first in, first out (FIFO) e last in, first out (LIFO) durante il prelievo. Queste strategie funzionano in combinazione con le date di aging registrate per le ubicazioni da tracciare quando le scorte sono entrate per la prima volta nel magazzino. La funzionalità *Aging prelievo scorte per direttiva ubicazione* utilizza la data sull'ubicazione per determinare l'aging. La funzionalità *Stato ubicazione magazzino* aggiorna la data sull'ubicazione, in base alla data della targa.

È possibile utilizzare le strategie FIFO e LIFO per spedire sia articoli di cui viene tenuta traccia in batch tracciati in batch che di articoli di cui non viene tenuta traccia in batch, in base alla data in cui le scorte sono entrate in magazzino. Questa funzionalità può essere particolarmente utile per le scorte di cui non viene tenuta traccia in batch, dove una data di scadenza non è disponibile per l'ordinamento.

Quando le scorte vengono ricevute o create per la prima volta nel magazzino, il sistema aggiorna la relativa targa di modo che la data corrente sia indicata come data di aging. Questa data viene quindi utilizzata nelle strategie della direttiva di ubicazione per identificare le scorte più vecchie o più recenti nel magazzino. Se le scorte vengono spostate in una ubicazione non rilevata mediante la targa, l'ubicazione stessa viene aggiornata con informazioni sull'aging e queste informazioni verranno quindi utilizzate dalle strategie.

## <a name="turn-on-the-feature"></a>Attivare la funzionalità

Per rendere disponibile questa funzionalità, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) in quest'ordine:

1. Stato ubicazione magazzino
1. Aging prelievo scorte per direttiva ubicazione

## <a name="feature-requirements"></a>Requisiti della funzionalità

Per utilizzare questa funzionalità, è necessario impostare l'opzione **Abilita stato ubicazione** su *Sì* per ogni [profilo di ubicazione](tasks/create-location-profile.md) che viene utilizzato per archiviare le scorte. Per impostare questa opzione per un profilo di ubicazione, andare a **Gestione magazzino \> Impostazione \> Magazzino \> Profili ubicazione** e selezionare il profilo di ubicazione. L'opzione si trova nella Scheda dettaglio **Generale**.

## <a name="feature-scenarios"></a>Scenari della funzionalità

Questa sezione fornisce esempi che mostrano come impostare e utilizzare le strategie FIFO e LIFO.

> [!TIP]
> Questa sezione fornisce due scenari, uno per FIFO e uno per LIFO. Le procedure fornite presuppongono che eseguirai entrambi gli scenari, nell'ordine in cui sono riportati. Ti consigliamo di eseguire entrambi gli scenari, in modo da poter sperimentare le differenze tra le due strategie.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare questi scenari utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

È inoltre possibile utilizzare questi scenari come indicazioni per l'utilizzo di questa funzionalità in un sistema di produzione. Tuttavia, in tal caso, devi sostituire i tuoi valori per ciascuna impostazione descritta qui.

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>Impostare gli scenari

I dati dimostrativi richiedono modifiche relative alla configurazione e alle scorte per supportare gli scenari. Segui questi passaggi per creare i dati sulle scorte necessari per gli scenari FIFO e LIFO.

1. Accedi a un sistema in cui i dati dimostrativi siano installati e seleziona la persona giuridica **USMF**.
1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nell'elenco dei profili di ubicazione, seleziona **FLOOR-05**.
1. Nella Scheda dettaglio **Generale**, imposta l'opzione **Abilita stato ubicazione** su *Sì*.
1. Selezionare **Salva**.
1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nell'elenco delle direttive di ubicazione, seleziona **Containerizzazione prelievo 63**.
1. Seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Nella Scheda dettaglio **Azioni direttiva di ubicazione**, trova la riga in cui il campo **Numero progressivo** è impostato su *1* e segui uno di questi passaggi:

    - Se stai impostando uno scenario FIFO, imposta il campo **Strategia** su *FIFO aging ubicazione*.
    - Se stai impostando uno scenario LIFO, imposta il campo **Strategia** su *LIFO aging ubicazione*.

1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.
1. Nella finestra di dialogo della query, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga e quindi imposta i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Tabella derivata:** *Ubicazioni*
    - **Campo:** *ID zona*
    - **Criteri:** *Piano*

1. Seleziona **OK** per applicare le impostazioni e chiudere la finestra di dialogo della query.
1. Seleziona **Salva** per salvare le modifiche alla direttiva di ubicazione.
1. Su un dispositivo mobile o nell'app *Dynamics 365 for Finance and Operations - Magazzino* sul tuo PC, segui questi passaggi per rimuovere le scorte esistenti dall'ubicazione del magazzino per supportare gli scenari:

    1. Accedi al magazzino *63* utilizzando un ID utente e una password appropriati.
    1. Nel menu principale, seleziona **Qualità**.
    1. Nel menu **Gestione qualità**, seleziona **Scarti**.
    1. Nella pagina **Scarti**, seleziona il campo **UBICAZIONE/TARGA**, quindi immetti *63\_1*.
    1. Premi **INVIO** o seleziona **OK**.
    1. Conferma i dettagli di **Scarti** per **Rettifica in uscita** premendo **INVIO** o selezionando **OK**.

    Quando le scorte della targa vengono rettificate, viene visualizzato il messaggio "Lavoro completato".

    Questi passaggi lasciano le scorte in due ubicazioni nei dati dimostrativi. Ogni ubicazione ha una data di aging diversa. La data di aging dell'ubicazione *FL-001* è il 15 aprile 2017 e La data di aging dell'ubicazione *FL-002* è il 29 gennaio 2017. Entrambe le ubicazioni contengono l'articolo *A0001*.

    Per visualizzare questi dati, vai a **Gestione articoli \> Richieste di informazioni e report \> Elenco scorte disponibili** e quindi filtra in base al magazzino *63* e l'articolo *A0001*. Nelle righe in cui il campo **Ubicazione** è impostato su *FL-001* o *FL-002*, seleziona una riga che ha un valore **Inventario fisico** positivo, quindi, nel riquadro azioni, seleziona **Transazioni**. Il campo **Data fisica** mostrerà una data che corrisponde a una delle date di aging menzionate in precedenza.

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>Scenario 1: impostazione e utilizzo dell'aging ubicazione FIFO

La strategia FIFO trova l'ubicazione che contiene la data di aging più vecchia e alloca il prelievo in base a tale data di aging.

1. Se non l'hai già fatto, [prepara i dati di esempio](#demo-set-up) necessari per questo scenario.
1. Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-001*.
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *63*.

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Include una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**. Per questa riga dell'ordine, imposta il campo **Numero articolo** su *A0001* e il campo **Quantità** su *1*.
1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare la quantità ordinata di questo articolo nelle scorte del magazzino selezionato.
1. Chiudi la pagina **Prenotazione**.
1. Nel riquadro azioni della pagina **Ordine cliente**, nella scheda **Magazzino**, nel gruppo **Azioni**, seleziona **Rilascia in magazzino**. Vengono visualizzati messaggi informativi. Il sistema crea una spedizione, la aggiunge a un nuovo carico e crea il lavoro richiesto.
1. Nella Scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino**, seleziona **Dettagli lavoro** per aprire il lavoro creato per questo ordine cliente. Da notare che nella riga in cui il valore **Tipo di lavoro** è *Prelievo*, il valore di **Ubicazione** è *FL-002*. Questa ubicazione contiene la targa con la data di aging più vecchia (FIFO).
1. Seleziona **Magazzino \> Dettagli spedizione**.
1. Nella Scheda dettaglio **Generale**, prendi nota dell'ID ondata, in modo da poterlo utilizzare nello scenario 2.

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>Scenario 2: impostazione e utilizzo dell'aging ubicazione LIFO

La strategia LIFO trova l'ubicazione che contiene la data di aging più recente e alloca il prelievo in base a tale data di aging. Nello scenario 2, modificherai l'impostazione per lo scenario 1 (FIFO) e riutilizzerai l'ordine cliente e l'ondata creati durante tale scenario.

1. Prima di iniziare questo scenario, imposta e completa l'intero scenario FIFO come descritto nella [sezione precedente](#fifo-demo). In questo scenario, riutilizzerai l'ondata e la maggior parte della configurazione creata per quello scenario.
1. Modifica la direttiva di ubicazione **Containerizzazione prelievo 63** di modo che utilizzi la strategia *LIFO aging ubicazione*, come descritto nella prima parte della procedura [Impostare gli scenari](#demo-set-up).

    Successivamente, modificherai l'ondata creata per l'ordine cliente nello scenario 1, di modo che utilizzi la strategia *LIFO aging ubicazione*.

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona e apri l'ondata che contiene l'ordine creato per lo scenario FIFO.
1. Nel riquadro azioni, nella scheda **Lavoro**, seleziona **Annulla** per annullare il lavoro creato per lo scenario FIFO.
1. Nel riquadro azioni, scheda **Ondata**, gruppo **Ondata**, selezionare **Elabora**.
1. Al termine dell'elaborazione, nel riquadro azioni, nella scheda **Ondata**, nel gruppo **Informazioni correlate**, seleziona **Lavoro** per aprire il lavoro creato per questa ondata.
1. Nella pagina **Lavoro**, nella scheda **Panoramica**, ci dovrebbero essere due righe. Seleziona la riga in cui il campo **Stato lavoro** è impostato su *Aperto*.
1. Da notare che nella riga in cui il valore **Tipo di lavoro** è *Prelievo*, il valore di **Ubicazione** è *FL-001*. Questa ubicazione contiene la targa con la data di aging più recente (LIFO).

In questi scenari, hai visto come la strategia di aging dell'ubicazione indirizza il lavoro verso l'ubicazione delle scorte che ha le scorte più vecchie o quelle più recenti, a seconda della strategia selezionata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]