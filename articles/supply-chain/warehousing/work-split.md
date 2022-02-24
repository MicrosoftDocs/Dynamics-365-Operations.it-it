---
title: Divisione lavoro
description: In questo argomento vengono fornite informazioni sulla funzionalità di suddivisione del lavoro. Questa funzionalità consente di suddividere gli ordini di lavoro di grandi dimensioni in diversi ordini di lavoro più piccoli che è possibile quindi assegnare a più lavoratori di magazzino. In questo modo, lo stesso lavoro può essere prelevato contemporaneamente da più magazzinieri.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8a530f3887c3c66295177d480a8c486dd0984153
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965529"
---
# <a name="work-split"></a>Divisione lavoro

La funzionalità di suddivisione del lavoro consente di suddividere gli ID ordini di lavoro di grandi dimensioni (ossia ordini di lavoro con molte righe) in diversi ID ordini di lavoro più piccoli che è possibile quindi assegnare a più lavoratori di magazzino. In questo modo, lo stesso numero di creazione lavoro può essere prelevato contemporaneamente da più magazzinieri.

> [!IMPORTANT]
> È possibile suddividere solo gli ordini di lavoro con stato *Aperto* o *In corso*.

## <a name="turn-on-the-work-split-functionality"></a>Attivare la funzionalità di suddivisione del lavoro

Prima di poter utilizzare la funzionalità di suddivisione del lavoro, è necessario attivare la funzionalità e la relativa funzionalità prerequisito nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle funzioni e se necessario abilitarle.

Innanzitutto, attivare la funzionalità prerequisito *Blocco del lavoro a livello di organizzazione* se non è già attivata. Nell'area di lavoro **Gestione funzionalità**, questa funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Blocco del lavoro a livello di organizzazione*

> [!NOTE]
> Quando questa funzione è attivata, un aggiornamento dei dati viene applicato automaticamente dopo che la funzione è stata attivata in tutte le persone giuridiche.

Quindi, attivare la funzionalità *Suddivisione lavoro* che è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Suddivisione lavoro*

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a>Miglioramenti ai dettagli del lavoro e a tutte le pagine di lavoro

La funzionalità *Suddivisione lavoro* aggiunge i seguenti due pulsanti alla scheda **Lavoro** nel riquadro azioni delle pagine **Dettagli lavoro** e **Tutto il lavoro**:

- **Suddivisione lavoro** – Dividere l'ID lavoro corrente in più ID lavoro di dimensioni minori che possono essere elaborati da lavoratori separati.
- **Annulla sessione di suddivisione lavoro** - Annullare la sessione di suddivisione del lavoro e rendere il lavoro disponibile per l'elaborazione.

![Pulsanti Suddivisione lavoro e Annulla sessione di suddivisione lavoro](media/Work_split_buttons.png "Pulsanti Suddivisione lavoro e Annulla sessione di suddivisione lavoro")

> [!IMPORTANT]
> Il pulsante **Suddivisione lavoro** non sarà disponibile se viene soddisfatta una delle seguenti condizioni:
>
> - Lo stato del lavoro è diverso da *Aperto* o *In corso*.
> - Un ID contenitore è associato all'ID lavoro. Un contenitore non può essere suddiviso sistematicamente, perché richiede azioni fisiche.
> - Il lavoro è associato a un cluster.
> - Il tipo di ordine di lavoro è diverso da uno dei seguenti tipi:
>
>    - Gestione ordini cliente
>    - Prelievo materie prime
>    - Uscita di trasferimento
>
> - Il lavoro è attualmente suddiviso da un altro utente. Se si tenta di aprire la pagina di suddivisione per il lavoro già suddiviso da un altro utente, viene visualizzato il seguente messaggio di errore: "Il lavoro con ID \#\#\#\# è attualmente suddiviso. Riprovare tra qualche minuto. Se si continua a ricevere questo messaggio, contattare un supervisore."

Un nuovo motivo di blocco del lavoro, *Suddivisione lavoro*, indica quando l'ID lavoro è suddiviso. È mostrato nella pagina **Suddivisione lavoro** e nell'app del magazzino se un utente tenta di eseguire il lavoro. Quando vengono utilizzati motivi di blocco, il nome del campo **Ciclo bloccato** dell'ID lavoro viene modificato in **Bloccato**.

## <a name="initiate-a-work-split"></a>Iniziare una suddivisione del lavoro

La funzione aggiunge una nuova pagina **Suddivisione lavoro** che consente agli utenti di suddividere le righe di lavoro dell'ID lavoro. Quando la pagina viene aperta per la prima volta, mostra le righe che hanno uno stato di lavoro di *Aperto* e che sono disponibili per essere suddivise. Nel riquadro azioni selezionare **Suddivisione lavoro** per elaborare il lavoro selezionato.

Per suddividere il lavoro, seguire questi passaggi.

1. Aprire una delle pagine di lavoro seguenti:

    - **Dettagli lavoro** (**Gestione magazzino \> Lavoro \> Dettagli lavoro**)
    - **Tutti i lavori** (**Gestione magazzino \> Lavoro \> Tutti i lavori**)

1. Nella griglia, selezionare un ID lavoro da suddividere. Il campo **Tipo di ordine di lavoro** deve essere impostato su uno dei seguenti valori:

    - Gestione ordini cliente
    - Prelievo materie prime
    - Uscita di trasferimento

1. Nella scheda **Lavoro** del riquadro azioni, nel gruppo **Lavoro**, selezionare **Suddivisione lavoro**.

    La pagina **Suddivisione lavoro** viene visualizzata che mostra le righe di lavoro aperte e disponibili per la suddivisione. Per impostazione predefinita, vengono visualizzate solo le righe di lavoro disponibili. Per visualizzare tutte le righe per l'ID lavoro (ad esempio, le righe che hanno un tipo di lavoro *Stoccaggio*), selezionare la casella di controllo **Mostra tutte le righe** sopra la griglia.

    Viene visualizzato il seguente messaggio: "Gli utenti non possono elaborare le righe del lavoro finché non si termina la suddivisione e si chiude questa pagina".

    Il campo **Motivo del blocco di lavoro** per il lavoro corrente sarà impostato su *Suddivisione lavoro* e il lavoro verrà bloccato.

    ![Motivo del blocco](media/Blocking_reason.png "Motivo del blocco")

1. Selezionare le righe da rimuovere dall'ID lavoro corrente e aggiungerle a un nuovo ID lavoro. Si verificano gli eventi seguenti:

    - Quando si suddivide il lavoro, la riga o le righe selezionate dall'ID lavoro originale vengono annullate e quindi copiate in un nuovo ID lavoro.
    - La struttura del modello di lavoro esistente e la posizione dello stoccaggio (e anche le future coppie prelievo/stoccaggio) vengono preservate. I valori per i seguenti campi ID lavoro vengono copiati dal lavoro originale al nuovo lavoro:

        - ID carico
        - ID spedizione
        - Tipo ordine di lavoro
        - Numero ordine
        - Sito
        - Magazzino
        - Priorità lavoro
        - ID pool lavoro
        - ID ondata
        - Numero creazione lavoro

    - I seguenti campi non vengono copiati nel nuovo ID lavoro:

        - **ID lavoro** - Viene generato un nuovo ID lavoro dalla sequenza numerica appropriata.
        - **Stato lavoro** - Questo campo è impostato su *Aperto*.
        - **Bloccato da** - Questo campo è inizialmente impostato su vuoto.
        - **ID targa di destinazione** - Questo campo è lasciato vuoto.
        - **Data e ora di creazione** - Questo campo è impostato sulla data e l'ora correnti.
        - **Ciclo bloccato/Congelato** - Questo campo viene ricalcolato per l'ID lavoro originale e il nuovo ID lavoro.

1. Nel riquadro azioni, selezionare **Suddivisione lavoro**.

Durante la suddivisione del lavoro, viene visualizzato il seguente messaggio: "Operazione di elaborazione - Suddivisione lavoro". Mentre questo messaggio è visibile, è possibile annullare l'operazione selezionando **Annulla** nella finestra del messaggio.

Se la casella di controllo **Mostra tutte le righe** è deselezionata, la riga che era stata suddivisa e annullata non apparirà più nella griglia. Se la casella di controllo è selezionata, il valore del campo **Stato lavoro** per quella riga cambia in *Annullato*.

Viene visualizzata la seguente notifica per indicare che il nuovo ID lavoro è stato creato: "Il lavoro \#\#\#\# è stato creato con la suddivisione dal lavoro originale \#\#\#\#."

Altre righe di lavoro dell'ID lavoro originale (come righe di *stoccaggio*) saranno regolate come richiesto per riflettere le righe di lavoro che sono state annullate. Ad esempio, se l'ID lavoro originale aveva una riga di *stoccaggio* per una quantità di 15 e le righe di *prelievo* che hanno una quantità totale di 10 sono state annullate, la nuova quantità di *prelievo* dell'ID lavoro originale sarà ora 5.

Il nuovo lavoro non verrà assegnato immediatamente a nessun utente. Tuttavia, è possibile assegnarlo a un utente ora, come richiesto, utilizzando la funzionalità standard della pagina **Dettagli lavoro**.

> [!IMPORTANT]
> È possibile suddividere solo gli ID lavoro che contengono due o più righe di lavoro disponibili. Se si seleziona **Suddivisione lavoro** quando è presente una sola riga di lavoro, verrà visualizzato il seguente messaggio di errore: "Almeno una riga di lavoro deve rimanere sul lavoro iniziale". In questo caso, non si verificherà alcuna suddivisione.

## <a name="finish-a-work-split"></a>Finire una suddivisione del lavoro

Per finire la suddivisione del lavoro, il motivo di blocco *Suddivisione lavoro* deve essere rimosso. Sono disponibili due modi per eseguire questa operazione:

- L'utente che sta suddividendo il lavoro chiude la pagina **Suddivisione lavoro** selezionando il pulsante **Chiudi** (**X**) nell'angolo in alto a destra. Quando la pagina è chiusa, il motivo del blocco *Suddivisione lavoro* verrà rimosso. Lo stato *Bloccato* di questo lavoro verrà ricalcolato e, se non ci sono motivi di blocco rimanenti per questo lavoro, il lavoro verrà sbloccato.
- Un utente apre l'ID lavoro e seleziona il pulsante **Annulla sessione di suddivisione lavoro** nel riquadro azioni. Il motivo di blocco *Suddivisione lavoro* verrà rimosso e lo stato *Bloccato* di questo lavoro verrà ricalcolato, proprio come quando la pagina **Suddivisione lavoro** viene chiusa.

Dopo che il motivo di blocco *Suddivisione lavoro* viene rimosso, il lavoro può essere eseguito sul dispositivo mobile, a condizione che lo stato **Bloccato** è impostato su *No* sull'ID lavoro.

## <a name="user-blocking-on-the-warehouse-app"></a>Blocco dell'utente sull'app warehouse

Se si tenta di usare l'app del magazzino per eseguire un lavoro di prelievo per un ID lavoro suddiviso, viene visualizzato il seguente messaggio di errore: "Il lavoro con ID \#\#\#\# è attualmente suddiviso." Se viene visualizzato questo messaggio di errore, selezionare **Annulla**. È quindi possibile continuare a elaborare altri lavori.

## <a name="other-blocked-operations"></a>Altre operazioni bloccate

Tutte le operazioni che modificano le righe di lavoro, le transazioni di inventario del lavoro o i collegamenti di rifornimento correlati al lavoro che viene suddiviso non avranno esito positivo e verrà visualizzato il seguente messaggio di errore: "Il lavoro con ID \#\#\#\# è attualmente suddiviso."
