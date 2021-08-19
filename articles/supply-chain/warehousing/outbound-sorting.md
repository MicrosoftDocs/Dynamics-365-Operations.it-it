---
title: Ordinamento in uscita
description: Questo argomento fornisce informazioni sull'ordinamento in uscita. Questa funzionalità semplifica la gestione di piccoli contenitori e aiuta i lavoratori a pianificare e organizzare meglio la capacità dei pallet nel camion.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: a3644964e43b7a1b34aa3bfab4e9172c1cb55bc8ef1d87cc7b5e2733effcb316
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726515"
---
# <a name="outbound-sorting"></a>Ordinamento in uscita

[!include [banner](../includes/banner.md)]

Questa funzionalità semplifica la gestione di piccoli contenitori e aiuta i lavoratori a pianificare e organizzare meglio la capacità dei pallet nel camion. Quando si utilizza l'ordinamento in uscita, è possibile ordinare i contenitori imballati nel pallet corretto dopo che sono stati in una stazione di imballaggio. È anche possibile creare una gerarchia di imballaggio.

Questa funzionalità consente di creare pallet da contenitori imballati mediante la funzionalità di imballaggio. Il contenitore non viene inviato al luogo di spedizione finale in quanto si trova nel flusso di imballaggio originale. Al contrario, i lavoratori possono chiudere il contenitore e spostarlo in un'ubicazione di tipo di ordinamento. Possono quindi ordinare i contenitori in posizioni, ognuna delle quali ha una targa. Dopo che i contenitori sono stati ordinati, è possibile creare lavoro per inviare l'intera targa alla banchina di spedizione finale o alle ubicazioni di gestione temporanea, in base alle direttive di ubicazione o alle proprie esigenze. Inoltre, l'azione di chiusura della posizione di ordinamento può spostare immediatamente le scorte nell'ubicazione di spedizione finale e prelevarle per l'ordine.

## <a name="turn-on-the-outbound-sorting-feature"></a>Attivare la funzionalità Ordinamento in uscita

Prima di poter utilizzare questa funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Ordinamento in uscita*

## <a name="setup"></a>Configurazione

Per questo scenario, è necessario utilizzare i dati dimostrativi **USMF** standard e il magazzino *62*. È inoltre necessario completare la configurazione descritta nelle sottosezioni seguenti.

### <a name="set-up-a-wave-template"></a>Impostare un modello di ondata

Questa configurazione elabora automaticamente l'ondata e crea lavoro quando una riga viene rilasciata nel magazzino.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Nell'elenco di modelli, selezionare **Magazzino 62**.
1. Nella Scheda dettaglio **Generale**, assicurarsi che l'opzione **Elabora ondata al rilascio in magazzino** sia impostata su *Sì*.

### <a name="set-up-a-worker"></a>Configurare un lavoratore

La stazione di imballaggio è considerata un'ubicazione. I lavoratori che accedono alla stazione di imballaggio vedono e lavorano solo su spedizioni e contenitori pianificati in quella specifica ubicazione di imballaggio. Un utente che accede a Microsoft Dynamics 365 deve essere configurato come lavoratore in Gestione magazzino. Se il nome dell'utente non appare nell'elenco di utenti di lavoro, utilizzare la seguente procedura per aggiungerlo.

> [!NOTE]
> Questi passaggi presuppongono che l'utente esista già nel sistema e che sia stato associato come dipendente o lavoratore nel modulo **Risorse umane**.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoratore**.
1. Selezionare **Nuovo**.
1. Nel campo **Lavoratore**, selezionare l'utente di destinazione nell'elenco di dipendenti.
1. Selezionare **Select**.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Utenti**, selezionare **Nuovo** per creare un account per dispositivo mobile e impostarne i seguenti valori:

    - **ID utente:** immettere un ID univoco.
    - **Nome utente:** immettere un nome per l'ID.
    - **Magazzino predefinito:** *62*
    - **Nome menu:** *Principale*

1. Nel riquadro azioni selezionare **Salva**.
1. Viene visualizzata la finestra di dialogo **Imposta password** dove è possibile creare una semplice password che l'utente può utilizzare per accedere all'app per dispositivi mobili. Imposta i valori seguenti:

    - **Password:** immettere una password semplice.
    - **Conferma password:** immettere di nuovo la stessa password.

1. Selezionare **Imposta password**.

    Una notifica nel Centro azioni indica che la password è stata impostata per l'utente creato.

### <a name="create-a-location-type"></a>Creare un tipo di ubicazione

1. Andare a **Gestione magazzino \> Impostazione \> Magazzino \> Tipi di ubicazione**.
1. Nel riquadro azioni selezionare **Nuovo** per creare un tipo di ubicazione e impostarne i seguenti valori:

    - **Tipo di ubicazione:** *ORDINAMENTO*
    - **Descrizione:** *Ordinamento*

1. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-warehouse-management-parameters"></a>Impostare i parametri di Gestione magazzino

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Generale** della Scheda dettaglio **Tipi di ubicazione**, impostare il campo **Tipo di ubicazione di ordinamento** su *ORDINAMENTO*.
1. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-a-location-profile"></a>Impostare un profilo di ubicazione

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **ID profilo ubicazione:** *Ordinamento*
    - **Nome:** *Ordinamento*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Formato ubicazione:** *ASRB* (Sezione-Scaffale-Ripiano-Contenitore)
    - **Tipo di ubicazione:** *ORDINAMENTO*
    - **Usa rilevamento targa:** *Sì*
    - **Consenti articoli combinati:** *Sì* (quando si imposta questa opzione su *Sì*, l'opzione **Consenti batch inventario combinati** è automaticamente impostata su *Sì* e non può essere modificata in modo indipendente).

1. Selezionare **Salva**.

### <a name="set-up-a-location"></a>Impostare un'ubicazione

1. Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.
1. Nell'intestazione, deselezionare la casella di controllo **Genera cifre di controllo per ubicazione**.
1. Nel riquadro azioni selezionare **Nuovo** per creare un'ubicazione e impostarne i seguenti valori:

    - **Magazzino:** *62*
    - **Ubicazione:** *SORT*
    - **ID profilo ubicazione:** *ORDINAMENTO*

1. Selezionare **Salva**.

### <a name="set-up-an-outbound-sorting-template"></a>Impostare un modello di ordinamento in uscita

Il modello di ordinamento in uscita determina se il lavoro viene creato al di fuori dell'ubicazione di ordinamento e se l'ordinamento viene eseguito manualmente o automaticamente.

Per questo scenario, si creerà un modello di ordinamento in uscita per creare pallet dopo la stazione di imballaggio.

1. Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Modello di ordinamento in uscita**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione del nuovo modello, impostare i seguenti valori:

    - **ID modello di ordinamento in uscita:** *AutoWork*
    - **Descrizione:** *Creazione automatica di lavoro*
    - **Tipo di modello di ordinamento in uscita:** *Contenitore*
    - **Magazzino:** *62*
    - **Ubicazione:** *SORT*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Ordina tipo di verifica:** selezionare *Scansione posizione*
    - **Crea lavoro in posizione chiusa:** *Sì*

        Se questa opzione è impostata su *Sì*, quando la posizione è chiusa, verrà creato il lavoro per spostare le scorte nell'ubicazione di spedizione finale. Se è impostata su *No*, le scorte verranno immediatamente prelevate nell'ordine quando la posizione viene chiusa.

    - **Assegnazione di posizione:** *Automatica*

        Se questo campo è impostato su *Manuale*, l'utente deve sempre indicare in quale posizione le scorte devono essere ordinate. Se è impostato su *Automatica*, il sistema inserisce automaticamente le scorte in una posizione quando possibile, in base alle suddivisioni del modello di ordinamento.

1. Nel riquadro azioni selezionare **Salva** per rendere l'opzione **Modifica query** disponibile.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con i seguenti valori:

    - **Tabella:** *Spedizioni*
    - **Tabella derivata:** *Spedizioni*
    - **Campo:** *Servizio trasporto*

        Dopo aver selezionato questo valore, è possibile che venga visualizzato il messaggio seguente: "Il servizio di trasporto non è un campo indice. Vuoi aggiungere l'ordinamento su questo? " Selezionare **Sì**.

    - **Direzione di ricerca:** *Crescente*

1. Selezionare **OK**.
1. È possibile che venga visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?". Selezionare **Sì**.

    Il pulsante **Interruzioni del modello di ordinamento in uscita** nel riquadro azioni diventa disponibile.

1. Nel riquadro azioni selezionare **Interruzioni del modello di ordinamento in uscita**.
1. Nella finestra di dialogo **Criteri di ordinamento in uscita**, impostare i seguenti valori:

    - **Nome tabella di riferimento:** *Spedizioni*
    - **Nome campo di riferimento:** *Servizio trasporto*
    - **Raggruppa per campo:** selezionare questa casella di controllo per raggruppare le spedizioni per servizio di trasporto.

1. Selezionare **OK** per salvare le impostazioni e chiudere la finestra di dialogo.

### <a name="set-up-container-packing-policies"></a>Impostare i criteri di imballaggio dei contenitori

1. Passare a **Gestione magazzino \> Impostazioni \> Contenitori \> Criteri imballaggio contenitore**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione dei nuovi criteri, impostare i seguenti valori:

    - **Criteri imballaggio contenitore:** *Ordinamento*
    - **Descrizione:** *Ordinamento*

1. Nella Scheda dettaglio **Panoramica**, impostare i seguenti valori:

    - **Magazzino:** *62*
    - **Ubicazione predefinita per ordinamento:** *ORDINAMENTO*
    - **Unità peso:** *kg*
    - **Criteri chiusura contenitore:** *Rilascio automatico*
    - **Criteri rilascio contenitore:** *assegnare il contenitore alla posizione di ordinamento in uscita*

1. Selezionare **Salva**.

### <a name="set-up-packing-profiles"></a>Impostare i profili imballaggio

Creare un nuovo profilo di imballaggio che verrà utilizzato insieme alla funzionalità di ordinamento.

1. Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Profili imballaggio**.
1. Nel riquadro azioni selezionare **Nuovo** per creare una riga e impostarne i seguenti valori:

    - **ID profilo imballaggio:** *Ordinamento*
    - **Descrizione:** *Ordinamento*
    - **Criteri imballaggio contenitore:** *Ordinamento*
    - **Modalità ID contenitore:** *Auto*
    - **Tipo di contenitore:** *Scatola-grande*
    - **Creazione automatica contenitore alla chiusura del contenitore:** deselezionato (= *No*)

1. Selezionare **Salva**.

### <a name="set-up-work-classes"></a>Impostare classi di lavoro

Impostare una classe di lavoro che verrà utilizzata insieme all'ordinamento.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.
1. Nel riquadro azioni selezionare **Nuovo** per creare una classe di lavoro per l'ordinamento e impostarne i seguenti valori:

    - **ID classe lavoro:** *Ordinamento*
    - **Descrizione:** *Ordinamento*
    - **Tipo ordine di lavoro:** *Prelievo scorte ordinate*

1. Selezionare **Salva**.

### <a name="set-up-mobile-device-menu-items"></a>Configurare voci di menu per dispositivo mobile

#### <a name="set-up-a-new-pallet-menu-item"></a>Configurare una voce di menu per pallet

Creare una voce di menu per dispositivo mobile per creare pallet durante l'ordinamento.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Nome voce di menu:** *Creazione pallet*
    - **Titolo:** *Creazione pallet*
    - **Modalità:** *Indiretta*
    - **Utilizza lavoro esistente:** *No*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Codice attività:** *Ordinamento in uscita*

        Quando questo campo è impostato su *Ordinamento in uscita*, il campo **ID modello di ordinamento in uscita** è visualizzato.

    - **Utilizza guida processo:** *Sì*

        Quando il campo **Codice attività** è impostato su *Ordinamento in uscita*, questa opzione viene automaticamente impostata su *Sì*.

    - **ID modello di ordinamento in uscita:** *AutoWork*

1. Selezionare **Salva**.

#### <a name="set-up-a-new-loading-menu-item"></a>Configurare una voce di menu per il carico

Ora creeremo una voce di menu che consente agli utenti di spostare gli articoli di magazzino ordinati nell'ubicazione di spedizione.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Nome voce di menu:** *Carica da ordinamento*
    - **Titolo:** *Carica da ordinamento*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *Sì*

1. Nella Scheda dettaglio **Generale**, impostare il campo **Diretto da** su *Diretto dall'utente*.
1. Nella Scheda dettaglio **Classi di lavoro**, selezionare **Nuovo**, quindi impostare i seguenti valori:

    - **ID classe lavoro:** *ORDINAMENTO*
    - **Tipo ordine di lavoro:** *Prelievo scorte ordinate*

1. Selezionare **Salva**.

### <a name="set-up-the-mobile-device-menu"></a>Configurare il menu per dispositivo mobile

È ora necessario aggiungere le nuove voci di menu al menu del dispositivo mobile.

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Selezionare il menu **In uscita**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella colonna **Menu e voci di menu disponibili**, trovare e selezionare **Creazione pallet**.
1. Selezionare il pulsante freccia DESTRA per spostare **Creazione pallet** nella colonna **Struttura menu**.
1. Utilizzare i pulsanti freccia SU e GIÙ per inserire la voce di menu **Creazione pallet** nella posizione desiderata nel menu del dispositivo mobile.
1. Selezionare **Salva**.
1. Ripetere questa procedura per aggiungere la voce di menu **Carica da ordinamento** al menu **In uscita**.

### <a name="set-up-location-directives"></a>Imposta direttive ubicazione

Le *direttive ubicazione* sono regole che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte. Ora è necessario creare una regola per gestire il lavoro di ordinamento.

#### <a name="set-up-a-single-sku-directive"></a>Configurare una direttiva per una singola SKU

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, impostare il campo **Tipo ordine di lavoro** su *Prelievo scorte ordinate*.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Sequenza:** *1*
    - **Nome:** *Portellone*

1. Nella Scheda dettaglio **Direttive ubicazione**, impostare i seguenti valori:

    - **Tipo di lavoro:** *Inserire*
    - **Sito:** *6*
    - **Magazzino:** *62*
    - **Più SKU:** *No*

1. Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Righe**.
1. Nella Scheda dettaglio **Righe**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga. Accettare i valori predefiniti per tutti gli altri campi.

    - **Sequenza:** *1*
    - **Da:** *0*
    - **A:** *1.000.000*

1. Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Azioni direttiva ubicazione**.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga. Accettare i valori predefiniti per tutti gli altri campi.

    - **Sequenza:** *1*
    - **Nome:** *Portellone*

1. Selezionare **Salva**.
1. Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trovare la riga in cui il campo **Campo** è impostato su *Ubicazione*. Impostare il campo **Criteri** per questa riga su *Portellone*.
1. Selezionare **OK** per salvare le impostazioni e chiudere l'editor di query.

#### <a name="set-up-a-multiple-sku-directive"></a>Configurare una direttiva per più SKU

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, impostare il campo **Tipo ordine di lavoro** su *Prelievo scorte ordinate*.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Sequenza:** *2*
    - **Nome:** *Multi portellone*

1. Nella Scheda dettaglio **Direttive ubicazione**, impostare i seguenti valori:

    - **Tipo di lavoro:** *Inserire*
    - **Sito:** *6*
    - **Magazzino:** *62*
    - **Più SKU:** *Sì*

1. Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Righe**.
1. Nella Scheda dettaglio **Righe**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga. Accettare i valori predefiniti per tutti gli altri campi.

    - **Sequenza:** *1*
    - **Da:** *0*
    - **A:** *1.000.000*

1. Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Azioni direttiva ubicazione**.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga. Accettare i valori predefiniti per tutti gli altri campi.

    - **Sequenza:** *1*
    - **Nome:** *Multi portellone*

1. Selezionare **Salva**.
1. Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trovare la riga in cui il campo **Campo** è impostato su *Ubicazione*. Impostare il campo **Criteri** per questa riga su *Portellone*.
1. Selezionare **OK** per salvare le impostazioni e chiudere l'editor di query.

### <a name="set-up-work-templates"></a>Imposta modelli di lavoro

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Impostare il campo **Tipo ordine di lavoro** su *Prelievo scorte ordinate*.
1. Nel riquadro azioni selezionare **Nuovo** per creare un modello di lavoro.
1. Nella scheda **Panoramica**, impostare i seguenti valori:

    - **Sequenza:** *1*
    - **Modello di lavoro** *Ordinamento*
    - **Descrizione modello di lavoro:** *Ordinamento*

1. Seleziona **Salva** per rendere la Scheda dettaglio **Dettagli modello di lavoro** disponibile.
1. Nella Scheda dettaglio **Dettagli modello di lavoro**, selezionare **Nuovo** per aggiungere una riga e quindi impostarne i seguenti valori:

    - **Tipo di lavoro:** *Prelevare*
    - **ID classe lavoro:** *ORDINAMENTO*

1. Selezionare di nuovo **Nuovo** per aggiungere una seconda riga e quindi impostare i seguenti valori:

    - **Tipo di lavoro:** *Inserire*
    - **ID classe lavoro:** *ORDINAMENTO*

1. Selezionare **Salva**.

## <a name="scenario"></a>Scenario

Questo scenario simula una situazione in cui i contenitori imballati devono essere ordinati automaticamente in posizioni diverse (pallet) dopo la stazione di imballaggio, a seconda del servizio di trasporto per la spedizione. Dopo che tutti gli articoli del carico sono stati imballati e ordinati per indirizzo, i pallet verranno spostati verso il portellone.

### <a name="create-sales-orders-and-picking-work"></a>Creare ordini cliente e lavoro di prelievo

#### <a name="create-sales-order-1"></a>Creare l'ordine cliente 1

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-005*
    - **Magazzino:** *62*

1. Selezionare **OK** per chiudere la finestra di dialogo.

    Viene aperto il nuovo ordine cliente.

1. Passa alla visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:

    - **Vettore spedizione:** *Air cargo*
    - **Servizio trasporto:** *Air*

1. Tornare alla visualizzazione **Righe**.
1. Se una nuova riga vuota non viene aggiunta automaticamente alla griglia nella Scheda dettaglio **Righe ordine cliente**, selezionare **Aggiungi riga** per aggiungerne una.
1. Nella nuova riga ordine, impostare i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *2*

1. Mentre la nuova riga ordine è ancora selezionata nella Scheda dettaglio **Righe ordine cliente**, nel menu **Inventario** sopra la griglia, selezionare **Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.
1. Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine. Prendere nota del numero ID ondata e del numero ID spedizione.

#### <a name="sales-order-2"></a>Ordine cliente 2

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-006*
    - **Magazzino:** *62*

1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Dovrebbe includere una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**. Impostare i seguenti valori in questa riga ordine:

    - **Articolo:** *A0001*
    - **Quantità:** *1*

1. Nella scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, impostare il campo **Modalità di consegna** su *Flowe-STD*.
1. Nella Scheda dettaglio **Righe ordine cliente**, selezionare **Aggiungi riga**, quindi impostare i seguenti valori nella seconda riga ordine.

    - **Articolo:** *A0002*
    - **Quantità:** *1*

1. Nella scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, impostare il valore del campo **Modalità di consegna** su *Air C-Air*.
1. Nella Scheda dettaglio **Righe ordine cliente**, selezionare la prima riga ordine. Quindi, nel menu **Scorte** sopra la griglia, selezionare **Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nella Scheda dettaglio **Righe ordine cliente**, selezionare la seconda riga ordine. Quindi, nel menu **Scorte** sopra la griglia, selezionare **Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.
1. Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine. Si noti che sono stati creati due numeri ID ondata e due numeri ID spedizione, uno per ciascuna modalità di consegna per le righe ordine cliente.

#### <a name="get-the-work-ids-from-the-work-details"></a>Ottenere gli ID lavoro dai dettagli del lavoro

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. La pagina mostra gli ID lavoro creati dagli ordini cliente. Utilizzare gli ID ondata e gli ID spedizione dagli ordini cliente creati per trovare l'ID lavoro per ogni ondata e spedizione. Prendere nota di questi ID lavoro, in quanto saranno necessari nei passaggi successivi. Si noti che sono stati creati due ID lavoro per il secondo ordine cliente. Se vengono prelevati articoli differenti in diverse ubicazioni, vengono generati ID lavoro distinti.

### <a name="pick-items-for-the-sales-orders"></a>Prelevare articoli per gli ordini cliente

Completare il lavoro creato utilizzando il dispositivo mobile per spostare gli articoli nella stazione di imballaggio.

1. Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Prelievo vendite**.
1. Nel campo **ID**, immettere l'ID lavoro creato per l'ordine cliente 1.
1. Selezionare **OK**.
1. Nella pagina **Ordini cliente - Prelievo**, immettere una targa di destinazione creata per l'ordine cliente 1. Si noti che sono visualizzati l'ubicazione di prelievo (*bulk-001*), l'articolo (*A0001*) e la quantità (*2 pezzi*).
1. Selezionare **OK**.
1. Esaminare le informazioni nella pagina **Ordini cliente - Stoccaggio**. Il campo **Ubicazione** deve indicare che gli articoli prelevati vengono spostati all'ubicazione *Imballaggio*.
1. Selezionare **OK**.

    Nella pagina **Esegui scansione ID lavoro/ID targa**, viene visualizzato il messaggio "Lavoro completato", che indica che l'ID lavoro dell'ordine cliente 1 è stato completato.

    Ora si sceglierà l'ordine cliente 2.

1. Nel campo **ID**, immettere l'ID lavoro creato per l'ordine cliente 2, dove la riga 1 include l'articolo *A0001*.
1. Selezionare **OK**.
1. Nella pagina **Ordini cliente - Prelievo**, immettere una targa di destinazione. Si noti che sono visualizzati l'ubicazione di prelievo (*bulk-001*), l'articolo (*A0001*) e la quantità (*1 pezzo*).
1. Selezionare **OK**.
1. Esaminare le informazioni nella pagina **Ordini cliente - Stoccaggio**. Il campo **Ubicazione** deve indicare che gli articoli prelevati vengono spostati all'ubicazione *Imballaggio*.
1. Selezionare **OK**.

    Nella pagina **Esegui scansione ID lavoro/ID targa**, viene visualizzato il messaggio "Lavoro completato". Questo messaggio indica che l'ID lavoro della riga 1 dell'ordine cliente 2 è stato completato.

1. Nel campo **ID**, immettere l'ID lavoro creato per l'ordine cliente 2, dove la riga 2 include l'articolo *A0002*.
1. Selezionare **OK**.
1. Nella pagina **Ordini cliente - Prelievo**, immettere una targa di destinazione. Si noti che sono visualizzati l'ubicazione di prelievo (*bulk-002*), l'articolo (*A0001*) e la quantità (*1 pezzo*).
1. Selezionare **OK**.
1. Esaminare le informazioni nella pagina **Ordini cliente - Stoccaggio**. Il campo **Ubicazione** deve indicare che gli articoli prelevati vengono spostati all'ubicazione *Imballaggio*.
1. Selezionare **OK**.

    Nella pagina **Esegui scansione ID lavoro/ID targa**, viene visualizzato il messaggio "Lavoro completato". Questo messaggio indica che l'ID lavoro della riga 2 dell'ordine cliente 2 è stato completato.

### <a name="pack-sales-orders-into-containers"></a>Imballare ordini cliente in contenitori

#### <a name="pack-sales-order-1-into-containers"></a>Imballare l'ordine cliente 1 in contenitori

1. Andare a **Gestione magazzino \> Imballaggio e containerizzazione \> Imballaggio**.

    Viene visualizzata la finestra di dialogo **Seleziona stazione di imballaggio**. Per impostazione predefinita, il campo **Lavoratore** deve essere impostato sul nome del lavoratore impostato in precedenza.

1. Impostare i seguenti valori per visualizzare e lavorare su spedizioni e contenitori pianificati nell'ubicazione di imballaggio specifica:

    - **Sito:** *6*
    - **Magazzino:** *62*
    - **Ubicazione:** *Imballaggio*
    - **ID profilo imballaggio:** *Ordinamento*

1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Nella pagina **Imballaggio**, nel campo **Targa o spedizione**, immettere la targa di destinazione per l'ordine cliente 1. Quindi premere il tasto **TAB** o **INVIO** della tastiera per uscire dal campo.
1. Nel riquadro azioni selezionare **Nuovo contenitore**.
1. Accettare tutte le impostazioni predefinite e selezionare **OK**. Prendere nota dell'ID contenitore.
1. Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:

    - **Quantità:** *1*
    - **Identificatore:** articolo *A0001*

1. Nel riquadro azioni selezionare **Chiudi contenitore**.
1. Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.
1. Selezionare **OK**. Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.
1. Creare un secondo contenitore per aggiungere il secondo articolo della targa per l'ordine cliente 1 a un nuovo contenitore.
1. Nel riquadro azioni selezionare **Nuovo contenitore**.
1. Accettare tutte le impostazioni predefinite e selezionare **OK**. Prendere nota dell'ID contenitore.
1. Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:

    - **Quantità:** *1*
    - **Identificatore:** articolo *A0001*

1. Nel riquadro azioni selezionare **Chiudi contenitore**.
1. Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.
1. Selezionare **OK**. Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.

#### <a name="pack-sales-order-2-into-containers"></a>Imballare l'ordine cliente 2 in contenitori

1. Nella pagina **Imballaggio**, nel campo **Targa o spedizione**, immettere la targa di destinazione per la riga 1 dell'ordine cliente 2. Quindi premere il tasto **TAB** o **INVIO** della tastiera per uscire dal campo.
1. Nel riquadro azioni selezionare **Nuovo contenitore**.
1. Accettare tutte le impostazioni predefinite e selezionare **OK**. Prendere nota dell'ID contenitore.
1. Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:

    - **Quantità:** *1*
    - **Identificatore:** articolo *A0001*

1. Nel riquadro azioni selezionare **Chiudi contenitore**.
1. Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.
1. Selezionare **OK**. Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.
1. Nel campo **Targa o spedizione**, immettere la targa di destinazione per la riga 2 dell'ordine cliente 2. Quindi premere il tasto **TAB** o **INVIO** della tastiera per uscire dal campo.
1. Nel riquadro azioni selezionare **Nuovo contenitore**.
1. Accettare tutte le impostazioni predefinite e selezionare **OK**. Prendere nota dell'ID contenitore.
1. Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:

    - **Quantità:** *1*
    - **Identificatore:** articolo *A0002*

1. Nel riquadro azioni selezionare **Chiudi contenitore**.
1. Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.
1. Selezionare **OK**. Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.

Per visualizzare i dettagli del contenitore, selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Contenitori** e cercare gli ID contenitore creati durante l'imballaggio.

### <a name="sort-the-containers"></a>Ordinare i contenitori

> [!IMPORTANT]
> Quando si accede alla voce di menu **Creazione pallet** nell'app per dispositivi mobili per eseguire l'ordinamento in uscita, viene visualizzato il pulsante **Completo**. *Non utilizzare il pulsante **Completo** per ordinare o chiudere la posizione.*
>
> Il pulsante **Completo** è disponibile per impostazione predefinita e non può essere disabilitato o rimosso dalla pagina. Non è utilizzato per la funzionalità *Ordinamento in uscita*.

#### <a name="sort-the-first-container"></a>Ordinare il primo contenitore

1. Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Creazione pallet**.
1. Nel campo **Targa/Con**, immettere il primo ID contenitore associato all'ordine cliente 1.
1. Selezionare **OK**.
1. Poiché al momento non esistono posizioni di ordinamento, è necessario specificarne una. Nel campo **ID posizione ordinamento**, immettere *SP01*.
1. Poiché nessuna targa è attualmente associata alla posizione di ordinamento *SP01*, è necessario specificarne una. Nel campo **TARGA**, immettere *PLP01*.
1. Selezionare **OK**.
1. Poiché la convalida della posizione di ordinamento è attivata, è necessario immettere nuovamente l'ID posizione di ordinamento. Nel campo **ID posizione ordinamento**, immettere *SP01*.
1. Selezionare **OK**.

    Viene visualizzato il messaggio "Lavoro completato".

> [!TIP]
> Per visualizzare la posizione di ordinamento e la targa nella stessa, selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Assegnazioni di posizioni di ordinamento in uscita**.
>
> La pagina **Assegnazioni di posizioni di ordinamento in uscita** mostra tutte le posizioni di ordinamento attualmente attive. Il campo **Transazioni posizioni di ordinamento** mostra la targa associata a ciascuna posizione di ordinamento e i contenitori che si trovano nella posizione di ordinamento. Si noti che esiste attualmente una posizione di ordinamento e che la Scheda dettaglio **Criteri di posizione di ordinamento** mostra un criterio di **Spedizione - Servizio trasporto - Aereo**.

#### <a name="sort-the-remaining-containers"></a>Ordinare i contenitori rimanenti

1. Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Creazione pallet**.
1. Nel campo **Targa/Con**, immettere il secondo ID contenitore associato all'ordine cliente 1.
1. Selezionare **OK**. Poiché il modello di ordinamento è configurato per l'ordinamento automatico ed esiste già una posizione di ordinamento con criteri corrispondenti, si viene automaticamente indirizzati alla posizione di ordinamento corretta.
1. Selezionare **OK**.
1. Confermare l'ID posizione di ordinamento per indicare che le scorte sono nell'ubicazione corretta. Nel campo **ID posizione ordinamento**, immettere *SP01*.
1. Selezionare **OK**.

    Il lavoro è completato per il secondo contenitore dell'ordine cliente 1. Ora si ordineranno i contenitori rimanenti dell'ordine cliente 2.

1. Nel campo **Targa/Con**, immettere l'ID contenitore del contenitore dell'ordine cliente 2 che contiene l'articolo *A0001*. Poiché il servizio di trasporto differisce, viene richiesto di immettere una nuova posizione di ordinamento e di assegnare una targa a quella posizione. Utilizzare la posizione ordinamento *SP02* e la targa *PLP02*.
1. Selezionare **OK**.
1. Confermare la posizione di ordinamento immettendo *SP02* nel campo **ID posizione di ordinamento**.
1. Selezionare **OK**.

    Il lavoro è completato per il contenitore.

1. Nel campo **Targa/Con**, immettere l'ID contenitore per il contenitore rimanente dell'ordine cliente 2 che contiene l'articolo *A0002*. Poiché il servizio di trasporto è uguale a quello dell'ordine cliente 1, il sistema mostra la posizione di ordinamento esistente che ha criteri corrispondenti.
1. Selezionare **OK**.
1. Confermare la posizione di ordinamento immettendo *SP01* nel campo **ID posizione di ordinamento**.
1. Selezionare **OK**.

    Il lavoro è completato per il contenitore.

### <a name="close-the-outbound-sorting-positions"></a>Chiudere le posizioni di ordinamento in uscita

Quando tutte le scorte sono state ordinate, la posizione deve essere chiusa prima di poter creare il lavoro. Verrà creato un lavoro di prelievo delle scorte ordinate per portare le scorte al portellone.

#### <a name="close-a-position-from-the-mobile-device"></a>Chiudere una posizione dal dispositivo mobile

1. Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Creazione pallet**.
1. Nel campo **Targa/Con**, immettere un ID contenitore che è stato ordinato per ordinare la posizione *SP01*.
1. Selezionare **OK**.
1. Viene visualizzato il seguente messaggio: "Il contenitore è già ordinato nella posizione SP01. Chiudere la posizione?". Selezionare **Chiudi**.

    Il lavoro è completato.

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a>Chiudere una posizione dalle assegnazioni delle posizioni di ordinamento in uscita

1. Selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Assegnazioni di posizioni di ordinamento in uscita**.
1. Nella colonna sinistra selezionare **SP02**. Questa riga della posizione di ordinamento in uscita è quella che verrà chiusa.
1. Nel riquadro azioni selezionare **Chiudi posizione**. Il record della posizione di ordinamento viene chiuso e non è più visualizzato.

    > [!TIP]
    > Per visualizzare tutti i record della posizione chiusa, selezionare la casella di controllo **Mostra chiuso**.

### <a name="sorted-inventory-picking"></a>Prelievo scorte ordinate

È necessario completare il lavoro di prelievo dell'inventario ordinato. Al termine, le scorte saranno prelevate nell'ordine cliente. A quel punto, si applicano tutti gli altri processi di magazzino.

1. Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Carica da ordinamento**.
1. Immettere l'ID targa di destinazione dalla prima posizione di ordinamento, *SP01*. Impostare il campo **ID** su *PLP01*.
1. Selezionare **OK**.
1. La pagina **Prelievo scorte ordinate: Prelievo** mostra il lavoro di prelievo che deve essere eseguito. Prelevare dall'ubicazione *ORDINAMENTO* e dalla targa di destinazione *PLP01*, che ha più articoli e una quantità pari a *3*.
1. Selezionare **OK**.
1. La pagina **Prelievo scorte ordinate: Stoccaggio** mostra il lavoro di stoccaggio che deve essere eseguito. Stoccare nell'ubicazione *Portellone* e nella targa di destinazione *PLP01*, che ha più articoli e una quantità pari a *3*.
1. Selezionare **OK**.

    Il lavoro è completato.

1. Immettere l'ID targa di destinazione della seconda posizione di ordinamento, *SP02*. Impostare il campo **ID** su *PLP02*.
1. Selezionare **OK**.
1. La pagina **Prelievo scorte ordinate: Prelievo** mostra il lavoro di prelievo che deve essere eseguito. Prelevare dall'ubicazione *ORDINAMENTO* e dalla targa di destinazione *PLP02*, che ha più articoli e una quantità pari a *1*.
1. Selezionare **OK**.
1. La pagina **Prelievo scorte ordinate: Stoccaggio** mostra il lavoro di stoccaggio che deve essere eseguito. Stoccare nell'ubicazione *Portellone* e nella targa di destinazione *PLP02*, che ha più articoli e una quantità pari a *1*.
1. Selezionare **OK**.

    Il lavoro è completato.

Da questo momento, si applicano tutti gli altri processi di magazzino.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]