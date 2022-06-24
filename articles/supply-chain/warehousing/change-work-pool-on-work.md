---
title: Modifica pool di lavoro nel lavoro
description: Questo articolo spiega come utilizzare il pulsante Modifica pool di lavoro per gli elementi di lavoro per modificare il pool di lavoro del lavoro esistente.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 817b45e8f5af957801a0af04e50acf20ba16c26d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900624"
---
# <a name="change-work-pool-on-work"></a>Modifica pool di lavoro nel lavoro

[!include [banner](../includes/banner.md)]

È possibile utilizzare i pool di lavoro per organizzare il lavoro in gruppi. Ad esempio, è possibile creare un pool di lavoro per classificare il lavoro che si verifica in un'ubicazione specifica del magazzino.

La funzionalità *Modifica pool di lavoro nel lavoro* aggiunge un pulsante **Modifica pool di lavoro** nel riquadro azioni per gli elementi di lavoro. Pertanto, i responsabili del magazzino possono facilmente modificare il pool di lavoro del lavoro esistente. Questa funzionalità consente ai manager di reagire rapidamente ai cambiamenti nello shop floor del magazzino e aiuta a migliorare la loro capacità di adattarsi alle situazioni mutevoli e alla necessità di trasferire il lavoro a un altro pool di lavoro.

## <a name="turn-the-change-work-pool-on-work-feature-on-or-off"></a>Attivare o disattivare la funzionalità Modifica pool di lavoro nel lavoro

A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Modifica pool di lavoro nel lavoro* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-the-change-work-pool-on-work-feature"></a>Configurare la funzionalità Modifica pool di lavoro nel lavoro

Per utilizzare questa funzionalità, è necessario configurare alcuni pool di lavoro. Si potrebbe inoltre configurare i modelli di lavoro in modo che assegnino automaticamente un pool. Se vuoi analizzare lo scenario di esempio fornito più avanti in questo articolo, configura il sistema come descritto in questa sezione.

### <a name="set-up-work-pools"></a>Configurare pool di lavoro

I pool di lavoro consentono di organizzare gli elementi di lavoro per tipo. Per utilizzare la funzionalità *Modifica pool di lavoro nel lavoro*, è necessario disporre di almeno due pool di lavoro disponibili. Per visualizzare e aggiungere pool di lavoro, effettuare le operazioni indicate di seguito.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Pool di lavoro**.
1. Se usi idati dimostrativi della società **USMF** e lo scenario di esempio più avanti in questo articolo, aggiungi due pool di lavoro con le seguenti impostazioni:

    - Pool di lavoro 1:

        - **ID pool di lavoro:** *Webshop*
        - **Descrizione:** *Negozio Web*

    - Pool di lavoro 2:

        - **ID pool di lavoro:** *CallCenter*
        - **Descrizione** *Servizio clienti*

1. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-work-templates"></a>Imposta modelli di lavoro

Per ciascuno dei modelli di lavoro, è possibile impostare un pool di lavoro predefinito, come richiesto. Per ogni modello pertinente, si assegna un pool di lavoro nella colonna **ID pool di lavoro**. In questo caso, tutti gli elementi di lavoro generati utilizzando un determinato modello ereditano automaticamente il pool di lavoro assegnato. Se usi i dati dimostrativi della società **USMF** e lo scenario di esempio più avanti in questo articolo, procedi come segue.

1. Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nel riquadro azioni seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Modificare il modello impostando i seguenti valori:

    - **Modello di lavoro:** *62 Prelievo da imballare*
    - **ID pool di lavoro:** *Webshop*

1. Selezionare **Salva**.

## <a name="example-scenario"></a>Scenario di esempio

Questo scenario mostra come modificare il flusso di elaborazione per un elemento di lavoro esistente modificandone il pool di lavoro. Utilizza i dati demo della società **USMF** e le impostazioni suggerite in precedenza in questo articolo.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Creare un ordine cliente e rilasciarlo nel magazzino

1. Confermare che l'inventario disponibile sia sufficiente per gli articoli *A0001* e *A0002* nel magazzino *62*. Vai a **Gestione inventario \> Richieste di informazioni e report \> Elenco scorte disponibili** e modificare i filtri come mostrato di seguito:

    - Il valore **Magazzino** inizia con *62*.
    - Il valore **Numero articolo** è *A001* o *A002*.

    Tutti i dati dimostrativi devono avere una quantità pari a 10.

    Successivamente, è necessario creare un ordine cliente.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-007*
    - **Magazzino:** *62*

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Dovrebbe includere una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *2*

1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.
1. Chiudere la pagina.
1. Nella Scheda dettaglio **Righe ordine cliente**, selezionare **Aggiungi riga** per aggiungere un'altra riga all'ordine cliente. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *A0002*
    - **Quantità:** *2*

1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.
1. Chiudere la pagina.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.
1. Ricevere messaggi informativi che mostrano l'ID ondata e l'ID spedizione creati dal rilascio. Prendere nota dell'ID ondata.

### <a name="review-the-outbound-wave"></a>Esaminare l'ondata in uscita

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Nella griglia, cercare l'ID ondata creata dal rilascio dell'ordine cliente.
1. Selezionare l'ID ondata per visualizzare i dettagli.
1. Nella Scheda dettaglio **Righe ondata**, assicurarsi che venga visualizzato un ID spedizione per l'ordine cliente.

    > [!TIP]
    > Se l'opzione **Elabora ondata al rilascio in magazzino** è impostata su *No* nella configurazione per il modello dell'ondata di spedizione, è necessario elaborare manualmente l'ondata selezionando **Processo** nella scheda **Ondata** del riquadro azioni per creare lavoro.

1. Assicurarsi che l'ondata sia stata elaborata. Questa elaborazione crea il lavoro richiesto.

### <a name="view-work-details-and-change-the-work-pool"></a>Visualizzare i dettagli del lavoro e modificare il pool di lavoro

È possibile usare la pagina **Dettagli lavoro** per visualizzare il lavoro creato e gestire il pool di lavoro.

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Selezionare la riga per il lavoro appena creato. La colonna **Numero ordine** mostrerà il numero dell'ordine cliente.

    Il campo **ID pool di lavoro** verrà impostato sull'ID del pool di lavoro impostato nel modello di lavoro.

    > [!TIP]
    > Se il campo **ID pool di lavoro** non è visibile, aggiungere la colonna alla griglia e quindi aggiornare la pagina.

1. Per modificare il pool di lavoro associato all'ID lavoro, nel riquadro azioni, nella scheda **Lavoro**, selezionare **Modifica ID pool di lavoro**.
1. Nella finestra di dialogo **Modifica pool di lavoro**, nella Scheda dettaglio **Parametri**, nel campo **ID pool di lavoro**, selezionare *CallCenter*.
1. Selezionare **OK** per applicare la modifica.
1. Si noti che il valore del campo **ID pool di lavoro** è stato ora cambiato in *CallCenter*.

> [!IMPORTANT]
> Quando viene visualizzata la finestra di dialogo **Modifica pool di lavoro**, il campo **ID pool di lavoro** potrebbe essere vuoto per impostazione predefinita. Se il campo è vuoto quando si seleziona **OK** per applicare le modifiche, si rimuoverà il pool di lavoro completamente dal lavoro.
>
> Oltre a cambiare pool di lavoro, è possibile utilizzare questa procedura per aggiungere un pool di lavoro a qualsiasi elemento di lavoro che non ne ha uno o per rimuovere un pool di lavoro da qualsiasi elemento di lavoro che ne ha uno.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]