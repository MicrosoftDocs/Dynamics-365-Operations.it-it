---
title: Consolidamento degli articoli e utilizzo delle ubicazioni
description: Questo argomento fornisce informazioni sulle funzionalità che semplificano la visualizzazione e il filtraggio dell'utilizzo volumetrico delle ubicazioni nel magazzino per i responsabili del magazzino. I responsabili possono selezionare le ubicazioni e creare attività di movimentazione delle scorte direttamente dalla pagina Consolidamento articoli per consolidare gli articoli e quindi sfruttare meglio lo spazio del magazzino.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a328b20c1cfb2fc376ab4656c64cf585a5aa015
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431473"
---
# <a name="item-consolidation---location-utilization"></a>Consolidamento degli articoli e utilizzo delle ubicazioni

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sulle funzionalità che semplificano la visualizzazione e il filtraggio dell'utilizzo volumetrico delle ubicazioni nel magazzino per i responsabili del magazzino. I responsabili possono selezionare le ubicazioni e creare attività di movimentazione delle scorte direttamente dalla pagina **Consolidamento articoli** per consolidare gli articoli e quindi sfruttare meglio lo spazio del magazzino.

## <a name="turn-on-the-features"></a>Attivare le funzionalità

Prima di poter utilizzare le funzionalità descritte in questo argomento, è necessario attivarle nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle funzionalità e attivarle se sono necessarie. Attivare entrambe le funzionalità seguenti, nell'ordine indicato (entrambe le funzionalità sono per il modulo **Gestione magazzino**).

1. Stato ubicazione magazzino
2. Utilizzo ubicazione consolidamento articolo

## <a name="warehouse-location-status"></a>Stato ubicazione magazzino

La funzionalità *SStato ubicazione magazzino* aggiunge quattro nuovi campi alla pagina **Ubicazioni** per tenere traccia di ulteriori informazioni sullo stato corrente dell'ubicazione:

- **Numero articolo**: l'articolo che si trova attualmente nell'ubicazione. Se l'ubicazione contiene più articoli, questo campo sarà vuoto.
- **Data e ora dell'ultima attività**: il timestamp dell'ultima transazione di magazzino eseguita a fronte dell'ubicazione.
- **Data di aging**: la data in cui le scorte nell'ubicazione sono state portate nel magazzino. Questa data viene calcolata in base alla data di aging della targa. Sebbene questa data sia precisa per le ubicazioni tracciate in base alla targa, potrebbe non essere precisa per le ubicazioni che non sono tracciate in base alla targa.
- **Stato ubicazione**: lo stato dell'ubicazione. I valori disponibili sono quattro:

    - **Indeterminato**: il profilo dell'ubicazione non tiene traccia dello stato. Pertanto, lo stato corrente è sconosciuto.
    - **Vuoto**: al momento non ci sono scorte nell'ubicazione.
    - **Prelievo**: sono state eseguite transazioni in uscita a fronte dell'ubicazione dall'ultima volta in cui era vuota.
    - **Immagazzinamento**: sono state eseguite transazioni in entrata dall'ultima volta in cui l'ubicazione era vuota.

Questi campi consentono ai responsabili del magazzino di ottenere una migliore panoramica dello stato delle ubicazioni nel magazzino. Consentono inoltre l'uso di report e filtri più avanzati.

## <a name="set-up-item-consolidation-and-location-utilization"></a>Configurare il consolidamento degli articoli e l'utilizzo delle ubicazioni

Questa sezione descrive come preparare il sistema all'uso del consolidamento degli articoli e dell'utilizzo delle ubicazioni. Le procedure utilizzano valori campione dei dati demo standard. Se si prevede di utilizzare lo scenario di esempio fornito più avanti in questo argomento, selezionare la persona giuridica **USMF** (che contiene i dati demo standard) e creare ogni record descritto in questa sezione. Se non si prevede di utilizzare lo scenario di esempio, i valori forniti qui possono essere considerati esempi dei tipi di configurazione che è necessario completare per utilizzare le funzionalità.

### <a name="released-product"></a>Prodotto rilasciato

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nel campo **Numero articolo**, selezionare *M9201* e aprire la pagina dei dettagli.
1. Nel riquadro azioni della scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **Dimensioni fisiche**.
1. Nella pagina **Dimensioni fisiche**, nel riquadro azioni, selezionare **Nuovo**.

    Una nuova riga viene aggiunta alla griglia. Il campo **Numero articolo** è preimpostato.

1. Nel campo **Unità** selezionare *unità*. I campi rimanenti sulla riga vengono impostati automaticamente.
1. Selezionare **Salva**, quindi chiudere la pagina.

### <a name="location-profile"></a>Profilo ubicazione

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Nell'elenco dei profili di ubicazione, seleziona **FLOOR-05**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Generale**, assicurarsi che entrambe le seguenti opzioni siano impostate su *Sì*:

    - Abilita articolo nell'ubicazione
    - Abilita stato ubicazione

1. Selezionare **Salva**.

    > [!IMPORTANT]
    > Se le opzioni **Abilita articolo nell'ubicazione** e **Abilita stato ubicazione** sono già impostate su *Sì*, passare alle istruzioni per la configurazione della Scheda Dettaglio **Dimensioni** nel passaggio 10. Se le opzioni non sono già impostate su *Sì*, è necessario eseguire una verifica di coerenza per il modulo **Gestione magazzino** dopo averle impostate manualmente. In questo caso, andare al passaggio successivo.

1. Per eseguire la verifica di coerenza, andare a **Amministrazione sistema \> Attività periodiche \> Database \> Verifica coerenza**.
1. Nella finestra di dialogo **Verifica coerenza**, impostare i seguenti valori:

    - **Modulo:** *Gestione Magazzino*
    - **Verifica/Correggi:** *Verifica*
    - **Dal**: lasciare vuoto questo campo.
    - **Verifica di coerenza stato ubicazione magazzino:** selezionare questa casella di controllo.

1. Selezionare **OK**.

    > [!TIP]
    > Al termine della verifica di coerenza, viene visualizzata una notifica.. Aprire il [Centro azioni](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) per visualizzare il messaggio. Selezionare **Dettagli messaggio** per visualizzare i dettagli.
    >
    > Se il messaggio per la verifica di coerenza indica "Informazioni sullo stato dell'ubicazione errate trovate per l'ubicazione XXXX nel magazzino XX", è necessario eseguire nuovamente la verifica di coerenza. Questa volta, impostare il campo **Verifica/Correggi** su *Correggi errore*. Visualizzare i messaggi per assicurarsi che non siano stati rilevati errori.

1. Ora è necessario completare la configurazione del profilo dell'ubicazione. Tornare a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**, selezionare il profilo di ubicazione **PIANO-05**, quindi, nel riquadro azioni, selezionare **Modifica**.
1. Nella Scheda dettaglio **Dimensioni**, impostare i seguenti valori:

    - **Percentuale di utilizzo volume:** *100*
    - **Metodo volumetrico usato per ubicazione di magazzino:** *Usa volume ubicazione*
    - **Altezza effettiva ubicazione:** *10*
    - **Larghezza effettiva ubicazione:** *10*
    - **Profondità effettiva ubicazione:** *10*
    - **Peso massimo:** *100*

1. Selezionare **Salva**.

### <a name="mobile-device-menu-items"></a>Voci di menu del dispositivo mobile

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro azioni selezionare **Nuovo** per creare una voce di menu per l'ordinamento.
1. Nell'intestazione, imposta i seguenti valori:

    - **Nome voce di menu:** *Rettifica in entrata*
    - **Titolo:** *Rettifica in entrata*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *No*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Processo di creazione lavoro:** *Rettifica in entrata*
    - **Tipi di rettifica magazzino:** *Rettifica in entrata*

1. Selezionare **Salva**.

### <a name="mobile-device-menu"></a>Menu del dispositivo mobile

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nell'elenco dei menu, selezionare **Scorte**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nell'elenco **Menu e voci di menu disponibili**, trova e seleziona la voce di menu **Rettifica in entrata**.
1. Selezionare il pulsante freccia destra per spostare **Rettifica in entrata** nell'elenco **Struttura menu**. In questo modo, si aggiunge la nuova voce di menu al menu selezionato.
1. Selezionare **Salva**.

### <a name="movement-types"></a>Tipi di movimento

1. Selezionare **Gestione magazzino \> Impostazione \> Scorte \> Tipi di movimento**.
1. Nel riquadro azioni, selezionare **Nuovo**, quindi impostare i seguenti valori:

    - **Codice tipo di movimento:** *CONSOLIDARE*
    - **Descrizione:** *Consolidare ubicazioni*
    - **ID classe lavoro:** *InvMov*

1. Selezionare **Salva**.

## <a name="example-scenario"></a>Scenario di esempio

Il seguente scenario utilizza l'app di magazzino su un dispositivo mobile per creare una *rettifica in entrata* delle scorte in due ubicazioni nel magazzino.

### <a name="add-inventory-to-locations"></a>Aggiungere scorte alle ubicazioni

1. Accedere al dispositivo mobile come utente configurato per il magazzino *51*.
1. Andare a **Scorte \> Rettifica in entrata**.

    Ora si inserirà la prima rettifica dell'ubicazione.

1. Nell'attività **Rettifica in entrata** selezionare l'ubicazione per cui effettuare la rettifica delle scorte. Nel campo **UBICAZIONE** selezionare *LP-001*.
1. Confermare l'ubicazione.
1. Creare un ID targa per l'articolo che verrà aggiunto all'ubicazione. Nel campo **TARGA**, immettere *LP00101*.
1. Confermare la targa.
1. Immettere l'articolo che verrà aggiunto alla targa. Nel campo **ITEM**, immettere *M9201*.
1. Confermare l'articolo.
1. Immettere la quantità dell'elemento che verrà aggiunta. Nel campo **QUANTITÀ** immettere *10*'.
1. Confermare la quantità.

    Viene visualizzato il messaggio "Lavoro completato". Ora si inserirà la seconda rettifica dell'ubicazione.

1. Nell'attività **Rettifica in entrata** selezionare l'ubicazione per cui effettuare la rettifica delle scorte. Nel campo **UBICAZIONE** selezionare *LP-002*.
1. Confermare l'ubicazione.
1. Creare un ID targa per l'articolo che verrà aggiunto all'ubicazione. Nel campo **TARGA**, immettere *LP00201*.
1. Confermare la targa.
1. Immettere l'articolo che verrà aggiunto alla targa. Nel campo **ITEM**, immettere *M9201*.
1. Confermare l'articolo.
1. Immettere la quantità dell'elemento che verrà aggiunta. Nel campo **QUANTITÀ** immettere *15*'.
1. Confermare la quantità.

    Viene visualizzato il messaggio "Lavoro completato".

1. Selezionare il pulsante Menu (a volte indicato come hamburger o pulsante hamburger), quindi selezionare **Annulla** per uscire dall'attività **Rettifica in entrata**.

### <a name="consolidate-locations"></a>Consolidare le ubicazioni

1. Andare a **Gestione magazzino \> Attività periodiche \> Consolidamento articoli**.
1. Nell'intestazione, selezionare un magazzino per cui eseguire il consolidamento. Nel campo **Magazzino** immettere *51*.

    Viene visualizzato un record per ogni ubicazione in cui larticolo *M9201* è stato rettificato. La colonna **Percentuale di utilizzo** mostra l'utilizzo volumetrico di ogni ubicazione.

1. Per consolidare le scorte, selezionare tutte le ubicazioni che devono essere consolidate, quindi, nel riquadro azioni, selezionare **Consolida scorte**.
1. Nella finestra di dialogo **Consolida scorte**, specificare l'ubicazione e il tipo di movimento da utilizzare per creare il lavoro per il movimento delle scorte. Imposta i valori seguenti:

    - **Ubicazione:** *LP-001*
    - **Codice tipo di movimento:** *CONSOLIDARE*

1. Selezionare **OK**.
1. Viene visualizzato un messaggio informativo che mostra il lavoro di movimento creato. Prendere nota dell'ID lavoro di movimento.

### <a name="view-movement-work"></a>Visualizzare il lavoro di movimento

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Visualizzare il lavoro creato. Utilizzare l'ID lavoro di movimento del consolidamento delle scorte per filtrare o cercare nella griglia di lavoro.

    In questo scenario, un'ubicazione esistente con scorte è stata utilizzata come ubicazione di consolidamento delle scorte. Pertanto, è stato creato un solo ID lavoro.

    > [!NOTE]
   > Il sistema crea un ID lavoro per ogni movimento che deve essere completato. Se si specifica un'ubicazione che contiene già delle scorte, viene creato un solo ID lavoro. Se si specifica una nuova ubicazione, vengono creati due ID lavoro.
