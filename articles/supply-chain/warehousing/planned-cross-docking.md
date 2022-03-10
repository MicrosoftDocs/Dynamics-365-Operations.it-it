---
title: Cross-docking pianificato
description: Questo argomento descrive il cross-docking pianificato avanzato, in cui la quantità di scorte richiesta per un ordine viene indirizzata direttamente dalla ricevuta o dalla creazione alla banchina di uscita o alla zona di transito corretta. Tutte le scorte rimanenti dall'origine in entrata vengono indirizzate all'ubicazione di magazzino corretta attraverso il normale processo di stoccaggio.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: c28639a4a575f5f356bf947ba8e0aee6bcd256b4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573035"
---
# <a name="planned-cross-docking"></a>Cross-docking pianificato

[!include [banner](../includes/banner.md)]

Questo argomento descrive il cross docking pianificato avanzato. Il cross-docking è un processo di magazzino in cui la quantità di scorte richiesta per un ordine viene indirizzata direttamente dalla ricevuta o dalla creazione alla banchina di uscita o alla zona di transito corretta. Tutte le scorte rimanenti dall'origine in entrata vengono indirizzate all'ubicazione di magazzino corretta attraverso il normale processo di stoccaggio.

Il cross-docking consente ai lavoratori di saltare lo stoccaggio in entrata e il prelievo in uscita delle scorte già contrassegnate per un ordine in uscita. Pertanto, il numero di volte in cui l'inventario viene toccato viene ridotto al minimo, ove possibile. Inoltre, poiché vi è una minore interazione con il sistema, i risparmi di tempo e spazio nello shop floor del magazzino aumentano.

Prima di poter eseguire il cross-docking, devi configurare un nuovo modello di cross-docking, in cui sono specificati l'origine di approvvigionamento e altri set di requisiti per il cross-docking. Quando viene creato l'ordine di uscita, la riga deve essere contrassegnata a fronte di un ordine di entrata che contiene lo stesso articolo. Puoi selezionare il campo Codice direttiva nel modello di cross-docking, in modo simile al modo in cui si impostano gli ordini di rifornimento e fornitore.

Al momento della ricezione dell'ordine in entrata, la configurazione del cross-docking identifica automaticamente la necessità di cross-docking e crea il lavoro di movimentazione per la quantità richiesta, in base all'impostazione della direttiva di ubicazione.

> [!NOTE]
> Le transazioni di magazzino *non* sono esenti da registrazione quando viene annullato il lavoro di cross-docking, anche se l'impostazione per questa funzionalità è attivata nei parametri di gestione del magazzino.

## <a name="turn-on-the-planned-cross-docking-features"></a>Attivare le funzionalità di cross docking pianificato

Se il sistema in uso non include già le funzionalità descritte in questo argomento, vedere [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attivare le seguenti funzionalità nel seguente ordine:

1. *Cross-docking pianificato*
1. *Modelli di cross-docking con direttive di ubicazione*
    > [!NOTE]
    > Questa funzionalità abilita il campo **Codice direttiva** affinché sia specificato nel modello di cross-docking, in modo simile al modo in cui si impostano i modelli di rifornimento. L'abilitazione di questa funzionalità impedisce di aggiungere un codice direttiva nelle righe del modello di lavoro cross-docking per la riga *Stoccaggio* finale. Ciò garantisce che la posizione di stoccaggio finale possa essere determinata durante la creazione del lavoro prima di considerare i modelli di lavoro.

## <a name="setup"></a>Attrezzaggio

### <a name="regenerate-load-posting-methods"></a>Rigenerare i metodi di registrazione del carico

Il cross-docking pianificato è implementato come metodo di registrazione del carico. Dopo aver attivato la funzionalità, è necessario rigenerare i metodi.

1. Accedi a **Gestione magazzino** \> Impostazione \> Metodi di registrazione carico.
1. Nel riquadro azioni, seleziona **Rigenera metodi**.

    Quando la rigenerazione è completa, dovresti vedere un metodo che ha un valore **Nome del metodo** di *planCrossDocking*.

1. Chiudere la pagina.

### <a name="create-a-cross-docking-template"></a>Creare un modello di cross-docking

1. Vai a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di cross-docking**.
1. Nel riquadro azioni seleziona **Nuovo** per creare un modello.
1. Nell'intestazione, imposta i seguenti valori:

    - **Sequenza:** *1*

        Questo campo definisce l'ordine in cui vengono valutati i modelli.

    - **ID modello di cross-docking:** *51*
    - **Descrizione:** *Magazzino 51*
    - **Criteri di rilascio della domanda:** *Prima del ricevimento della fornitura*
    - **Magazzino:** *51*

1. L'impostazione sulla Scheda dettaglio **Pianificazione** controlla il funzionamento del modello. Imposta i valori seguenti:

    - **Fabbisogno della domanda:** *Nessuno*

        Questo campo definisce il fabbisogno di scorte della domanda. Se la domanda deve essere collegata all'offerta prima del rilascio, seleziona *Contrassegno*. Se la domanda deve essere prenotata dall'ordine a fronte dell'offerta prima del rilascio, seleziona *Prenotazione ordine*.

    - **Tipo di individuazione:** *Ubicazioni di spedizione*

        Questo campo definisce se il lavoro di cross-docking deve utilizzare le ubicazioni di transito/carico dalla spedizione o se deve utilizzare le direttive di ubicazione per trovare le proprie ubicazioni di transizione/carico.

    - **Modello di lavoro**: lasciare vuoto questo campo.

        Questo campo definisce il modello di lavoro che deve essere utilizzato quando viene creato il lavoro di cross-docking.

    - **Riconvalida al ricevimento della fornitura:** *No*

        Questa opzione definisce se la fornitura deve essere riconvalidata al momento del ricevimento. Se questa opzione è impostata su *Sì*, vengono controllati sia l'intervallo di tempo massimo sia l'intervallo di giorni di scadenza.

    - **Codice direttiva:** lascia vuoto questo campo

        Questa opzione è abilitata tramite la funzionalità *Modelli di cross docking con direttive di ubicazione*. Il sistema utilizza le direttive di ubicazione per determinare l'ubicazione migliore in cui spostare l'inventario cross-docking. È possibile configurarla assegnando un codice direttiva a ciascun modello di cross-docking pertinente. Se il codice direttiva è impostato, il sistema cercherà direttive di ubicazione in base al codice direttiva quando viene generato il lavoro. In questo modo, puoi limitare le direttive di ubicazione utilizzate per un particolare modello di cross-docking.

    - **Convalida finestra temporale:** *Sì*

        Questa opzione definisce se la finestra temporale massima deve essere valutata quando viene selezionata una fonte di approvvigionamento. Se questa opzione è impostata su *Sì*, diventano disponibili i campi correlati alle finestre di tempo massimo e minimo.

    - **Intervallo di tempo massimo:** *5*

        Il campo definisce il periodo massimo consentito tra l'arrivo della fornitura e la partenza della domanda.

    - **Unità intervallo di tempo massimo:** *Giorni*
    - **Intervallo di tempo minimo:** *0*

        Il campo definisce il periodo minimo consentito tra l'arrivo della fornitura e la partenza della domanda.

    - **Unità intervallo di tempo minimo:** *Giorni*
    - **Intervallo giorni di scadenza:** *0*

        *Criteri FEFO (first out first first out):* questo campo definisce il numero massimo di giorni tra la data di scadenza del lotto in scadenza al momento che è attualmente nel magazzino e il lotto in ricezione.

1. Nella Scheda dettaglio **Fonti di approvvigionamento**, si specificano i tipi di fornitura validi per questo modello. Seleziona **Nuovo**, quindi imposta i seguenti valori:

    - **Numero progressivo:** *1*
    - **Fonte di approvvigionamento:** *Ordine fornitore*

> [!NOTE]
> È possibile impostare una query per verificare se un determinato modello di cross-docking è utilizzato. La query per i modelli di cross-docking ha solo la tabella *Invent Table* (articoli) e la tabella *WHSInventTable* (articoli WHS) inner join. Se vuoi aggiungere altre tabelle alla query, puoi unirle usando solo join *exist* o *not exist*. Quando si filtrano le tabelle unite, viene recuperato un record dalla tabella principale per ogni record corrispondente nella tabella unita. Se il tipo di join è *exist*, la ricerca termina dopo che è stata trovata la prima corrispondenza. Ad esempio, se unisci la tabella della riga dell'ordine cliente alla tabella degli articoli, il sistema convalida e restituisce gli articoli per i quali almeno una riga dell'ordine cliente presenta la condizione definita. In sostanza, i dati vengono recuperati dalla tabella padre (articoli), non dalla tabella figlio (riga ordine cliente). Pertanto, il filtro in base a documenti di origine come righe di ordini cliente o clienti non può essere eseguito immediatamente.

### <a name="create-a-work-class"></a>Creare una classe di lavoro

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.
1. Nel riquadro azioni seleziona **Nuova** per creare una nuova classe di lavoro.
1. Imposta i valori seguenti:

    - **ID classe lavoro:** *CrossDock*
    - **Descrizione:** *Cross-docking*
    - **Tipo di ordine di lavoro:** *Cross docking*

### <a name="create-a-work-template"></a>Creare un modello di lavoro

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Imposta il campo **Tipo ordine di lavoro** su *Cross-docking*.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla scheda **Panoramica**.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero progressivo:** *1*
    - **Modello di lavoro:** *Cross-docking 51*
    - **Descrizione modello di lavoro:** *Cross-docking 51*

1. Seleziona **Salva** per rendere la Scheda dettaglio **Dettagli modello di lavoro** disponibile.
1. Nella Scheda dettaglio **Dettagli modello di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tipo di lavoro:** *Prelevare*
    - **ID classe lavoro:** *CrossDock*

1. Seleziona **Nuova** per aggiungere un'altra riga, quindi imposta i seguenti valori:

    - **Tipo di lavoro:** *Inserire*
    - **ID classe lavoro:** *CrossDock*

1. Seleziona **Salva** e verifica che la casella di controllo **Valido** sia selezionata per il modello *51 Cross-docking*.
1. Opzionale: Seleziona **Modifica query** se vuoi impostare criteri per controllare quando e dove viene utilizzato il modello di lavoro.

    Puoi impostare una query per verificare se un determinato modello di lavoro è utilizzato. Ad esempio, è possibile specificare che un modello può essere utilizzato per il lavoro solo in un'ubicazione specifica. Se desideri che il modello di lavoro cross-docking venga applicato in un'ubicazione specifica, è necessario filtrare in base al campo **Ubicazione di partenza** e non al campo **Ubicazione** perché la creazione del lavoro per i processi in entrata (acquisto, cross-docking e riapprovvigionamento) inizia dalla riga di inserimento. Quando viene creato il lavoro, la direttiva di ubicazione imposta il campo **Ubicazione** sull'ubicazione di stoccaggio. Tuttavia, l'ubicazione di prelievo è memorizzata nel campo **Ubicazione di inizio**.

> [!NOTE]
> Gli ID della classe di lavoro per i tipi di lavoro *Preleva* e *Inserisci* devono essere gli stessi.

### <a name="create-location-directives"></a>Creare direttive di ubicazione

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, imposta il campo **Tipo di ordine di lavoro** su *Cross-docking*.
1. Nel riquadro azioni, seleziona **Nuovo**, quindi imposta i seguenti valori:

    - **Numero progressivo:** *1*
    - **Nome:** *51 inserisci cross-docking*
    - **Tipo di lavoro:** *Inserire*
    - **Sito:** *5*
    - **Magazzino:** *51*

1. Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.
1. Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Da quantità:** *1*
    - **A quantità:** *1000000*

1. Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Nome:** *Baydoor*
    - **Utilizzo ubicazioni fisse:** *Ubicazioni fisse e non fisse*

1. Seleziona **Salva** per rendere il pulsante **Modifica query** nella barra degli strumenti **Azioni direttiva ubicazione** disponibile.
1. Seleziona **Modifica query** per aprire l'editor di query.
1. Nella scheda **Intervallo**, verifica che siano configurate le seguenti due righe:

    - Riga 1:

        - **Tabella:** *Ubicazioni*
        - **Tabella derivata:** *Ubicazioni*
        - **Campo:** *Magazzino*
        - **Criteri:** *51*

    - Riga 2:

        - **Tabella:** *Ubicazioni*
        - **Tabella derivata:** *Ubicazioni*
        - **Campo:** *Ubicazione*
        - **Criteri:** *Baydoor*

1. Seleziona **OK** per chiudere l'editor di query.

### <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nell'elenco delle voci di menu nel riquadro sinistro, seleziona **Stoccaggio dell'ordine fornitore**.
1. Selezionare **Modifica**.
1. Nella Scheda dettaglio **Classi di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **ID classe lavoro:** *CrossDock*
    - **Tipo di ordine di lavoro:** *Cross docking*

1. Selezionare **Salva**.

## <a name="scenario"></a>Scenario

### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

Segui questi passaggi per creare un ordine fornitore come fonte di approvvigionamento.

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:

    - **Conto fornitore:** *104*
    - **Magazzino:** *51*

1. Seleziona **OK** e prendi nota del numero dell'ordine.
1. Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine fornitore**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *5*

### <a name="create-a-sales-order"></a>Crea un ordine cliente

Segui questi passaggi per creare un ordine cliente come origine della domanda.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-002*
    - **Magazzino:** *51*

1. Selezionare **OK**.
1. Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *3*

### <a name="create-planned-cross-docking"></a>Creare cross-docking pianificato

Segui questi passaggi per creare il cross-docking pianificato dall'ordine cliente.

1. Nella pagina **Dettagli ordine cliente** per l'ordine cliente appena creato, nel riquadro azioni, nella scheda **Magazzino** del gruppo **Azioni**, seleziona **Rilascia in magazzino**.

    L'operazione di rilascio in magazzino crea una riga di spedizione e di carico per la riga ordine client e tenta di allocare le scorte.
    
    Viene visualizzato un messaggio informativo. Viene inoltre visualizzato il seguente messaggio di avviso: "Nessun lavoro creato per l'ondata XXXX. Vedi il registro della cronologia di creazione del lavoro per i dettagli. " Questo comportamento è previsto perché non sono presenti scorte nel magazzino.

1. Nella scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino**, seleziona **Dettagli spedizione**.

    La pagina **Dettagli spedizione** viene visualizzata e mostra la spedizione creata per l'ordine cliente.

1. Nella Scheda dettaglio **Righe di carico**, il campo **Quantità cross-dockin pianificata** è impostato su *3*. Poiché non erano disponibili scorte nel magazzino, ma una fonte di approvvigionamento valida arriverà entro l'intervallo di tempo definito nel modello di cross-docking, la quantità cross-docking è stata creata.
1. Nella Scheda dettaglio **Righe di carico**, seleziona **Cross-docking pianificato** per visualizzare i dettagli del cross-docking creato.

## <a name="process-the-cross-docking"></a>Elaborare il cross-docking

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>Ricezione dell'ordine fornitore nell'app per dispositivi mobili di magazzino

Il sistema riceverà la quantità di 5 dall'ordine fornitore nell'ubicazione di ricevimento e creerà due parti del lavoro.

Il primo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Cross docking* ed è collegato all'ordine cliente. Ha una quantità di 3 ed è diretto al luogo di spedizione finale in modo che possa essere spedito immediatamente.

Il secondo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Ordini fornitore* ed è collegato all'ordine fornitore. Ha la quantità rimanente di 2 che non era cross-docking ed è indirizzata allo stoccaggio.

1. Accedi al dispositivo mobile come un utente in magazzino *51*.
1. Vai a **In entrata \> Entrata acquisto**.
1. Nel campo **Numero ordine fornitore**, inserisci il numero dell'ordine fornitore.
1. Nel campo **Qtà** immetti *5*.
1. Selezionare **OK**.
1. Nella pagina successiva, imposta il campo **Articolo** su *A0001*.
1. Selezionare **OK**.
1. Nella pagina successiva, conferma i valori **Numero ordine fornitore**, **Articolo** e **Quantità** selezionando **OK**.

    Ricevi un messaggio di tipo Lavoro completato.

1. Seleziona **Annulla** per uscire.

### <a name="put-away-to-cross-docking-and-bulk"></a>Stoccaggio su cross-docking e in blocco

Attualmente, entrambi gli ID lavoro hanno la stessa targa di destinazione. Per completare i passaggi successivi, è necessario ottenere l'ID lavoro e l'ID targa di destinazione. È possibile ottenere queste informazioni dai dettagli di lavoro per la riga ordine fornitore e la riga ordine cliente. In alternativa, puoi andare a **Gestione magazzino \> Lavoro \> Dettagli del lavoro** e filtrsre per il lavoro in cui il valore **Magazzino** è *51*.

1. Sul dispositivo mobile, vai a **In entrata \> Stoccaggio acquisto** e immetti la targa di destinazione dal lavoro.
1. Nel campo **ID**, immetti l'ID targa di destinazione dai dettagli di lavoro.

    La pagina di preliveo di cross-docking mostra l'ubicazione di prelievo (*RECV*), la targa di destinazione (*targa*), l'articolo (*A0001*) e la quantità (*3*).

1. Selezionare **OK**.
1. Nel campo **Targa di destinazione**, immetti una targa di destinazione per l'ID targa che deve essere inserito (cross-docking) nell'ubicazione di spedizione. È possibile selezionare qualsiasi ID targa di propria scelta.
1. Selezionare **OK**.
1. Nella pagina successiva, nel campo **ID**, immetti l'ID targa di destinazione.
1. Selezionare **OK**.
1. Conferma il lavoro per selezionare la quantità rimanente di 2, quindi seleziona **OK**.
1. Nella pagina successiva, seleziona **Fatto** per terminare il processo di raccolta e iniziare il processo di stoccaggio.

    L'app per dispositivi mobili mostra l'ubicazione e la targa in cui collocare l'oggetto.

1. Conferma il comando **Inserisci** dello stoccaggio in blocco selezionando **OK**.
1. Nella pagina successiva, confermare il cross-docking **Inserisci** selezionando **OK**.

    Ricevi un messaggio di tipo Lavoro completato.

1. Seleziona **Annulla** per uscire.

La seguente illustrazione mostra come il lavoro cross-docking completato potrebbe apparire in Microsoft Dynamics 365 Supply Chain Management.

![Lavoro di cross docking completato.](media/PlannedCrossDockingWork.png "Lavoro di cross docking completato")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
