---
title: Regola Rilascia in magazzino
description: Questo articolo fornisce informazioni sulla funzionalità della regola Rilascia in magazzino, che offre flessibilità durante il rilascio al magazzino. Aggiunge un'opzione di configurazione che controlla se il sistema consente il rilascio di righe ordine parzialmente prenotate.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: c011938438be32e8a3169d90561ab329da32e32a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895469"
---
# <a name="release-to-warehouse-rule"></a>Regola Rilascia in magazzino

[!include [banner](../includes/banner.md)]

La funzionalità *Regola Rilascia in magazzino* offre flessibilità durante il rilascio in magazzino. Aggiunge un'opzione di configurazione per ciascun magazzino. È possibile utilizzare questa opzione per specificare se è possibile rilasciare righe ordine parzialmente prenotate per quel magazzino. La funzionalità funziona insieme a funzionalità di cross-docking avanzate in situazioni in cui una parte della quantità di una riga ordine è contrassegnata rispetto a una fonte di approvvigionamento, ma la parte rimanente può essere elaborata nel magazzino. Pertanto, la riga può essere rilasciata in modo che l'elaborazione del magazzino della quantità di scorte disponibili possa continuare.

## <a name="turn-on-and-initialize-the-release-to-warehouse-rule-feature"></a>Attivare e inizializzare la funzione Regola Rilascia in magazzino

### <a name="turn-on-the-feature"></a>Attivare la funzionalità

Prima di poter utilizzare la funzionalità *Regola Rilascia in magazzino*, tale funzionalità deve essere attivata nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Regola Rilascia in magazzino*

### <a name="initialize-the-feature"></a>Inizializzare la funzione

Dopo aver attivato la funzione nel sistema, è necessario inizializzarla per impostare la regola sullo stato iniziale corretto per tutti i magazzini.

- Per i magazzini che non sono abilitati per la gestione del magazzino, la regola è inizialmente impostata su **Non applicabile**.
- Per i magazzini che sono abilitati per la gestione del magazzino, la regola è inizialmente impostata su **Consenti prenotazione parziale**

Per inizializzare la funzionalità e impostare la regola di rilascio in magazzino per tutti i magazzini, attieniti alla seguente procedura.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella pagina **Parametri di gestione magazzino**, nella scheda **Generale**, nella sezione **Informazioni sulla società**, seleziona il collegamento per la regola **Inizializza rilascio in magazzino**. (Se questo collegamento non viene visualizzato, la funzione non è attivata o è già stata inizializzata.)
1. Quando viene richiesto di confermare l'azione, seleziona **Sì** per inizializzare la funzionalità.

## <a name="set-the-release-to-warehouse-rule-for-each-warehouse"></a><a name="set-option-warehouse"></a>Impostare la regola di rilascio in magazzino per ciascun magazzino

Dopo l'attivazione e l'inizializzazione della funzionalità, tutti i magazzini avranno un'impostazione iniziale, come descritto nella sezione precedente. È possibile modificare questa impostazione per singoli magazzini seguendo questi passaggi.

1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
1. Seleziona il magazzino da configurare.
1. Seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Nella Scheda dettaglio **Magazzino**, nella sezione **Prenotazioni**, il campo **Requisito per la prenotazione di scorte** controlla se è consentito il rilascio parziale degli ordini. Selezionare uno dei seguenti valori:

    - **Non applicabile**: quando la funzionalità viene attivata e inizializzata per la prima volta, questo valore viene assegnato automaticamente a tutti i magazzini non abilitati per la gestione del magazzino. Questo valore non può essere modificato. Questo valore non è disponibile per i magazzini abilitati per la gestione del magazzino.
    - **Consenti prenotazione parziale**: gli ordini possono essere rilasciati quando tutte le quantità sono prenotate. Il sistema valuterà se la quantità senza prenotazione deve essere contrassegnata per il cross-dockin avanzato e contrassegnerà tale quantità come richiesto. Se non esiste alcun contrassegno, il sistema creerà lavoro solo per la quantità prenotata. Quando la funzionalità viene attivata e inizializzata per la prima volta, questo valore viene assegnato automaticamente a tutti i magazzini abilitati per la gestione del magazzino. Questo valore non è disponibile per i magazzini non abilitati per la gestione del magazzino.
    - **Richiedi prenotazione completa**: gli ordini possono essere rilasciati solo se l'intera quantità è prenotata. Non possono essere rilasciati se la quantità totale non è né fisicamente prenotata né pianificata per il cross-docking. Questo valore non è disponibile per i magazzini non abilitati per la gestione del magazzino.

1. Selezionare **Salva**.

## <a name="scenarios"></a>Scenari

Questa sezione fornisce due scenari che è possibile elaborare per apprendere cosa fa questa funzionalità e come utilizzarla.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare questi scenari utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

È inoltre possibile utilizzare questi scenari come indicazioni per l'utilizzo di questa funzionalità quando si lavora su un sistema di produzione. Tuttavia, in questo caso, è necessario sostituire i propri valori e potrebbero mancare alcuni tipi di record richiesti forniti dai dati demo standard.

### <a name="scenario-1-require-full-release-no-planned-cross-docking"></a><a name="scenario1"></a>Scenario 1: richiedi il rilascio completo (nessun cross-docking pianificato)

Questo scenario mostra come funziona la funzionalità per i magazzini impostati su **Richiedi prenotazione completa**.

1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
1. Per il magazzino _62_, imposta il campo **Requisito per la prenotazione di scorte** su **Richiedi prenotazione completa**, come descritto in precedenza nella sezione [Impostare la regola di rilascio in magazzino per ciascun magazzino](#set-option-warehouse) in questo articolo.
1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su _US-004_.
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona _62_.

1. Scegli **OK** per creare il nuovo ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Include una riga vuota nella griglia nella sezione **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *2*

1. Seleziona **Aggiungi riga** per aggiungere una nuova riga, quindi imposta i seguenti valori:

    - **Numero articolo:** *A0002*
    - **Quantità:** *2*

1. Seleziona la prima riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Non prenotare la seconda riga ordine.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.
1. Nota che viene visualizzato il seguente messaggio di errore: "La quantità completa deve essere fisicamente prenotata." Pertanto, il sistema non crea alcun lavoro, spedizione o carico per l'ordine.

    > [!NOTE]
    > Riceverai lo stesso messaggio di errore se prenoti parzialmente la seconda riga.

### <a name="scenario-2-allow-partial-release"></a>Scenario 2: consentire il rilascio parziale

Questo scenario mostra come funziona la funzionalità per i magazzini impostati su **Consenti rilascio parziale**.

1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
1. Per il magazzino _62_, imposta il campo **Requisito per la prenotazione di scorte** su **Consenti prenotazione parziale**, come descritto in precedenza nella sezione [Impostare la regola di rilascio in magazzino per ciascun magazzino](#set-option-warehouse) in questo articolo.
1. Come hai fatto nello [scenario precedente](#scenario1), vai a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente** e creare un ordine cliente per l'account cliente _US-004_ dal magazzino _62_. Aggiungi le seguenti due righe ordine:

    - **Riga 1:** imposta il campo **Numero articolo** su _A0001_, il campo **Quantità** su _2_ e il campo **Unità** su _Pcs_.
    - **Riga 2:** imposta il campo **Numero articolo** su _A0002_, il campo **Quantità** su _2_ e il campo **Unità** su _Pcs_.

1. Come hai fatto nello [scenario precedente](#scenario1), prenota l'intera quantità per la riga ordine 1, ma non prenotare la riga ordine 2.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.
1. Nota che questa volta non ricevi un messaggio di errore. Al contrario, il sistema crea lavoro, spedizioni e carichi secondo necessità e mostra i risultati.
1. Per visualizzare le informazioni di spedizione, caricamento e lavoro, utilizza il menu **Magazzino** sopra la griglia:

    - **Riga 1:** sono disponibili tre opzioni: **Dettagli di spedizione**, **Dettagli di carico** e **Dettagli di lavoro**. Seleziona ciascuna opzione per visualizzare i dettagli della spedizione, del carico e del lavoro creati al momento del rilascio dell'ordine nel magazzino.
    - **Riga 2:** solo l'opzione **Dettagli di lavoro** è disponibile. Selezionalo e nota che non è stato creato alcun lavoro perché non sono state prenotate scorte. Pertanto, non è stata creata alcuna spedizione o carico.

> [!NOTE]
> Lo stesso risultato è previsto quando la seconda riga è parzialmente prenotata. In questo caso, il lavoro verrà creato per la quantità di riga prenotata ma non per la quantità senza prenotazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]