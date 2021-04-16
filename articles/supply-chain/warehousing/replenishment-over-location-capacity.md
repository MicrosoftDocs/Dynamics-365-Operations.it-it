---
title: Rifornimento superiore alla capacità dell'ubicazione
description: Questo argomento fornisce informazioni sulla funzionalità di rifornimento superiore alla capacità dell'ubicazione. Questa funzionalità consente a tutto il lavoro di rifornimento da eseguire obbligatoriamente durante la giornata di essere creato e gestisce la disponibilità di tale lavoro di rifornimento per garantire che l'ubicazione di prelievo non esaurisca le scorte né superi la capacità.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 309df56671bf258e1669ae6d5393de01e2b500f0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823241"
---
# <a name="replenishment-over-location-capacity"></a>Rifornimento superiore alla capacità dell'ubicazione

[!include [banner](../includes/banner.md)]

Alcuni magazzini ad alto volume o con limitazioni di spazio devono spedire una quantità di un articolo in un giorno uperiore alla capacità dell'ubicazione di prelievo. La funzionalità *Rifornimento superiore alla capacità dell'ubicazione* consente a tutto il lavoro di rifornimento da eseguire obbligatoriamente durante la giornata di essere creato e gestisce la disponibilità di tale lavoro di rifornimento per garantire che l'ubicazione di prelievo non esaurisca le scorte né superi la capacità.

La funzionalità consente di creare una quantità di lavoro di rifornimento superiore alla capacità di un'ubicazione e blocca il completamento del lavoro di rifornimento quando l'ubicazione è piena. Man mano che le scorte in un'ubicazione di calano al di sotto di una soglia configurabile, viene reso disponibile ulteriore lavoro di rifornimento.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>Attivare la funzionalità Rifornimento superiore alla capacità dell'ubicazione

Per rendere disponibile questa funzionalità, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):

1. Blocco lavoro a livello di organizzazione
1. Rifornimento superiore alla capacità dell'ubicazione

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configurare la funzionalità per lo scenario di esempio

Questa sezione fornisce linee guida e un esempio che mostra come configurare questa funzionalità e preparare i dati di esempio per lo scenario di esempio illustrato più avanti in questo argomento.

### <a name="enable-sample-data"></a>Abilitare dati di esempio

Per elaborare lo [scenario di esempio](#example-scenario) utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

### <a name="location-profile"></a>Profilo ubicazione

Abilita la funzionalità di rifornimento superiore alla capacità nel profilo ubicazione.

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Nel riquadro sinistro selezionare **PICK-06**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Rifornimento**, impostare i seguenti valori:

    - **Supera la capacità di ubicazione:** *Sì*

        Se l'opzione è attivata, la capacità massima dell'ubicazione potrà superare il lavoro di rifornimento. Questo abilita anche altri campi nella Scheda dettaglio **Rifornimento**.

    - **Tipo di soglia disponibilità del lavoro:** *Quantità*

        Questo campo definisce il metodo utilizzato per determinare quando è necessario rilasciare più lavoro. È possibile rilasciare in base alla quantità o a una percentuale.

        - *Percentuale*: seleziona questa opzione per utilizzare la capacità percentuale basata su limiti di stoccaggio o metriche di volume. Selezionando questa opzione si abilita il campo **Percentuale overflow** e si disabilitano i due campi relativi alla quantità, **Quantità di overflow** e **Unità di overflow**.

            È possibile utilizzare questa opzione se le ubicazioni di prelievo utilizzano metriche volume.

            Se questa opzione è selezionata, impostare il campo **Percentuale overflow** sulla percentuale in corrispondenza della quale sarà reso disponibili più lavoro di rifornimento.

        - *Quantità*: selezionare questa opzione per utilizzare un valore di quantità specifico. Selezionando questa opzione si abilita il campo **Percentuale overflow** e si disabilitano i due campi relativi alla quantità, **Quantità di overflow** e **Unità di overflow**.

            Utilizzare questa opzione quando non si utilizza metrica di volume per le ubicazioni che vengono rifornite o quando si dispone di quantità costanti per cui si desidera portare più scorte nell'ubicazione.

           Se questa opzione è selezionata, impostare i campi **Quantità di overflow** e **Unità di overflow** per la quantità e l'unità in cui verrà reso disponibile più lavoro di rifornimento.

    - **Quantità di overflow:** *0,65*

        Questo campo definisce la quantità in cui si verifica l'overflo dell'ubicazione.

        Il lavoro sarà disponibile ogni volta che la somma della quantità disponibile e della quantità di lavoro e nell'ubicazione è inferiore a questo valore. Qualsiasi lavoro di rifornimento superiore a questo valore verrà bloccato e deve essere sbloccato manualmente.

        I limiti di stoccaggio dell'ubicazione vengono considerati quando viene calcolata la quantità di lavoro.

    - **Unità di overflow:** *PL*

        Questo campo definisce l'unità associata alla quantità di overflow.

        In questo caso, verrà reso disponibile altro lavoro di rifornimento quando l'ubicazione scende a 0,65 pallet (PL).

    - **Percentuale overflow**

        Questo campo definisce la percentuale in cui si verifica l'overflow dell'ubicazione.

        Il lavoro sarà disponibile ogni volta che la somma della quantità disponibile e della quantità di lavoro e nell'ubicazione è inferiore a questa percentuale. Qualsiasi percentuale della quantità di lavoro di rifornimento superiore a questo valore verrà bloccata e deve essere sbloccata manualmente.

        I limiti di stoccaggio dell'ubicazione vengono considerati quando viene calcolata la percentuale di quantità di lavoro. Se non vengono definiti limiti di stoccaggio per l'ubicazione, la percentuale della quantità di lavoro viene calcolata in base al volume se i limiti di volume sono definiti per il profilo dell'ubicazione.

> [!IMPORTANT]
> Se si utilizzano i dati dimostrativi per la persona giuridica **USMF** ed è stata precedentemente attivata la funzionalità *Posizionamento targa ubicazione*, è necessario disattivare l'impostazione **Abilita posizionamento targa** per il profilo di ubicazione **BULK-06** per completare i passaggi su dispositivo mobile nello scenario di esempio.

### <a name="wave-step-code"></a>Codice del passaggio ondata

> [!NOTE]
> Per configurare un codice di passaggio di ondata come descritto qui, è consigliabule prima utilizzare la [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare la funzionalità denominata *Codice passaggio ondata a livello di organizzazione*.

1. Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Codici passaggio ondata**.
1. Selezionare **Nuovo** e impostare i seguenti valori:

    - **Codice passaggio ondata:** *Rifornimento*
    - **Descrizione passaggio ondata:** *Rifornimento*
    - **Tipo di passaggio ondata:** *Rifornimento*

1. Selezionare **Salva**.

### <a name="replenishment-template"></a>Modello di rifornimento

I modelli rifornimento rappresentano un set di regole che controlla quando e come effettuare il rifornimento dell'ubicazione.

1. Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di rifornimento**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella sezione **Panoramica**, selezionare la riga in cui il campo **Modello di rifornimento** è impostato su *Riforniomento domanda*.
1. Imposta i valori seguenti:

    - **Codice passaggio ondata:** *Rifornimento*
    - **Consenti domanda ondata per utilizzare le quantità non prenotate:** *Sì*

1. Selezionare **Salva**.

### <a name="wave-template"></a>Modello ondata

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Nel riquadro sinistro, impostare il campo **Tipo di modello ondata** su *Spedizione*.
1. Selezionare il modello **61 spedizione** nell'elenco.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella scheda dettaglio **Generale**, impostare l'opzione **Automatizza rilascio lavoro di rifornimento** su *Sì*.

    Impostare questa opzione su *Sì* per creare lavoro di rifornimento basato sulla domanda e per rilasciarlo automaticamente. È necessario aggiungere il metodo ondata di rifornimento al modello di ondata e creare un modello rifornimento di tipo **Domanda ondata**. Impostare un modello di rifornimento nella pagina **Modelli di rifornimento**. Per configurare un modello di rifornimento, è necessario aggiungere il metodo di rifornimento al modello ondata.

1. Nella Scheda dettaglio **Metodi**, nella colonna **Metodi selezionati**, trova la seguente riga:

    - **Nome metodo:** *Rifornimento*
    - **Nome:** *Rifornimento*

1. Impostare il campo **Codice passagio ondata** per questa riga su *Rifornimento*.
1. Selezionare **Salva**.

## <a name="example-scenario"></a>Scenario di esempio

Dopo aver reso disponibili tutti i dati di esempio precedentemente descritti e averli configurati, è possibile utilizzare questo scenario per provare la funzionalità *Rifornimento superiore alla capacità dell'ubicazione*. I valori mostrati in questo scenario presuppongono che si stia lavorando con i dati dimostrativi standard, che sia stata selezionata la persona giuridica **USMF** e che sono stati preparati i record di esempio descritti in precedenza in questo argomento. Questo scenario serve anche come esempio che mostra come la funzionalità può essere utilizzata in uno scenario di produzione.

### <a name="create-replenishment-work"></a>Crea lavoro di rifornimento

#### <a name="create-sales-order-1"></a>Creare l'ordine cliente 1

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel riquadro azioni, scegli **Nuovo** per aprire una finestra di dialogo per la creazione di un nuovo ordine cliente.
1. Nella finestra di dialogo, imposta i seguenti valori:

    - **Conto cliente:** *US-007*
    - **Magazzino:** *61*

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Include una nuova riga vuota nella Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *T0100*
    - **Quantità:** *40*

1. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto**.
1. Chiudere la pagina.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Viene visualizzato un messaggio informativo che mostra l'ID ondata e spedizione creati. Viene inoltre creata un'ondata di rifornimento.

    Viene inoltre visualizzato un messaggio di avviso che indica "L'ID lavoro XXXX non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".

#### <a name="create-sales-order-2"></a>Creare l'ordine cliente 2

1. Nella pagina **Tutti gli ordini cliente**, nel riquadro azioni, scegliere **Nuovo** per aprire una finestra di dialogo per la creazione di un nuovo ordine cliente.
1. Nella finestra di dialogo, impostare il seguente valore:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *61*

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Include una nuova riga vuota nella Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *T0100*
    - **Quantità:** *60*

1. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto**.
1. Chiudere la pagina.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Viene visualizzato un messaggio informativo che mostra l'ID ondata e spedizione creati. Viene inoltre creata un'ondata di rifornimento.

    Viene inoltre visualizzato un messaggio di avviso che indica "L'ID lavoro XXXX non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".

#### <a name="create-sales-order-3"></a>Creare l'ordine cliente 3

1. Nella pagina **Tutti gli ordini cliente**, nel riquadro azioni, scegliere **Nuovo** per aprire una finestra di dialogo per la creazione di un nuovo ordine cliente.
1. Nella finestra di dialogo, imposta i seguenti valori:

    - **Conto cliente:** *US-004*
    - **Magazzino:** *61*

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Include una nuova riga vuota nella Scheda dettaglio **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *T0100*
    - **Quantità:** *30*

1. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto**.
1. Chiudere la pagina.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Viene visualizzato un messaggio informativo che mostra l'ID ondata e spedizione creati. Viene inoltre creata un'ondata di rifornimento.

    Viene inoltre visualizzato un messaggio di avviso che indica "L'ID lavoro XXXX non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".

#### <a name="view-work-details"></a>Visualizzare i dettagli del lavoro

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Nella sezione **Panoramica**, filtrare la colonna **Magazzino** per il magazzino *61*.
1. Dovresti vedere che sono stati creati sette ID lavoro per i tre ordini cliente della domanda.

    - Tre dei sette ID lavoro hanno un valore **Tipo di ordine di lavoro** di *Rifornimento* e quattro hanno un valore **Tipo di ordine di lavoro** di *Ordini cliente*.
    - Tutti e tre gli ID lavoro che hanno un valore **Tipo di ordine di lavoro** di *Rifornimento* hanno le stesse ubicazioni *Preleva* e *Inserisci* nella sezione **Righe**:

        - **Preleva:** *02A01R5S1B*
        - **Inserisci:** *06A01R2S1B*

    - Sono stati creati due ID lavoro per l'ordine cliente 1.

1. Prendi nota degli ID lavoro per gli ordini cliente.

A seconda delle quantità disponibili, le quantità di lavoro create potrebbero variare leggermente. Tuttavia, nel complesso, le intestazioni di lavoro create devono corrispondere a questo esempio di scenario.

#### <a name="on-hand-inventory-license-plate-id"></a>ID targa delle scorte disponibili

Più avanti in questo scenario, si utilizzerà l'app per dispositivi mobili Gestione magazzino (o un emulatore), dove sarà necessario identificare la targa per completare gli scenari di prelievo e rifornimento.

Per trovare gli ID targa necessari in seguito, attenersi alla seguente procedura.

1. Passare a **Gestione articoli \> Richieste di informazioni e report \> Scorte disponibili**.
1. Selezionare il pulsante **Mostra filtri** per aprire il riquadro del filtro.
1. Immettere i seguenti criteri di filtro per ottenere le targhe per lo scenario. Utilizzare il filtro *inizia con*.

    - **Numero articolo:** *T0100*
    - **Magazzino:** *61*

1. Selezionare **Applica**.
1. Nel riquadro azioni selezionare **Dimensioni**.
1. Nella finestra di dialogo **Visualizzazione delle dimensioni**, **Dimensioni di immagazzinamento**, selezionare tutti i valori.
1. Nella sezione **Transazioni**, selezionare **Codice articolo** e **Quantità \<\> 0**.
1. Al termine, selezionare **OK** per chiudere la finestra di dialogo.
1. La griglia **Disponibilità** mostra i numeri di targa per l'articolo *T0100* in ogni ubicazione. Prendere nota della targa che si trova in ogni ubicazione, perché questa informazione sdarà necessaria in seguito.
1. Chiudere la pagina.

### <a name="process-steps"></a>Passaggi processo

Verrà eseguito il rifornimento dell'ubicazione di magazzino per i primi due ID lavoro. Il lavoro sul terzo lavoro di rifornimento sarà bloccato fino a quando il livello di scorte nell'ubicazione di prelievo non scenderà al di sotto della soglia.

#### <a name="replenishment"></a>Rifornimento

1. Accedi all'app per dispositivi mobili Gestione magazzino come utente nel magazzino *61*. (Immettere *61* come ID utente e *1* come password).
1. Passare a **Inventario \> Rifornimento**.

    Viene richiesto di completare il primo lavoro di rifornimento. Vengono visualizzati il numero, la quantità e l'ubicazione di prelievo dell'articolo.

1. Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.
1. Selezionare il pulsante **OK** (simbolo del segno di spunta).

    Il sistema genera un numero di targa di destinazione per la nuova targa per l'articolo selezionato.

1. Selezionare **OK** per confermare il valore.

    Viene mostrato il lavoro di inserimento che indica all'utente di inserire la targa di destinazione nell'ubicazione di rifornimento. L'ubicazione *Inserisci* dovrebbe essere **06A01R2S1B**.

1. Confermare i dettagli di inserimento e selezionare **OK**.

    Viene visualizzato il messaggio "Lavoro completato" e vengono visualizzati i dettagli della successiva attività di prelievo di rifornimento: il numero dell'articolo, la quantità e l'ubicazione da cui prelevare. L'ubicazione di prelievo sarà la stessa della prima ubicazione di rifornimento. Pertanto, la targa avrà lo stesso ID targa utilizzato per la prima attività del lavoro di rifornimento.

1. Ripetere i passaggi precedenti per completare il lavoro di rifornimento per la seconda attività del lavoro. La quantità e la targa di destinazione differiranno dalla quantità e dalla targa di destinazione per la prima attività del lavoro.

Al termine del secondo lavoro di rifornimento, viene visualizzato il messaggio "Lavoro completato". Il dispositivo mobile informa inoltre che non è disponibile alcun lavoro, anche se rimangono alcuni lavori di rifornimento. Questo comportamento si verifica perché il lavoro di rifornimento ha uno stato di disponibilità di *Tenuto* ed è quindi contrassegnato come **bloccato**.

Lo stato *Tenuto* è stato attivato perché il profilo di ubicazione per l'ubicazione di prelievo a cui viene assegnato il lavoro ha un valore **Quantità di overflow** di *0,65 PL*. Le due precedenti attività di rifornimento hanno riempito l'ubicazione quasi fino al limite di overflow per l'articolo *T0100*. (La conversione di unità per l'articolo è *1 PL = 100 ea*.) Pertanto, il lavoro di rifornimento rimanente provocherebbe il superamento del limite di overflow per l'ubicazione.

Fino a quando non viene prelevata una quantità sufficiente di scorte dall'ubicazione per portarla al di sotto della soglia di rilascio di lavoro sulla voce di menu del dispositivo mobile, questo lavoro di rifornimento rimarrà bloccato.

#### <a name="sales-order-pick"></a>Prelievo ordine cliente

Prima che l'attività di rifornimento rimanente possa essere completata, le scorte nell'ubicazione di prelievo devono diminuire fino a un livello in cui è possibile sbloccare il rimanente lavoro di rifornimento. In altre parole, la somma della quantità di scorte disponibili nell'ubicazione e la quantità di rifornimento non possono superare il valore **Quantità di overflow**. Quando questa somma è inferiore alla quantità di overflow, il restante lavoro di rifornimento verrà sbloccato.

1. Accedi all'app per dispositivi mobili Gestione magazzino come utente nel magazzino *61*. (Immettere *61* come ID utente e *1* come password).
1. Passare a **In uscita \> Prelievo vendite**.
1. Immettere il primo ID lavoro per l'ordine cliente 1.

    Fare riferimento agli ID lavoro per gli ordini cliente annotati in precedenza, nella pagina **Dettagli del lavoro**. L'ID lavoro inserito qui genererà il lavoro di prelievo per una quantità di 10 ea da due ubicazioni separate.

1. Selezionare **OK**.

    La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare per la prima ubicazione.

1. Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.
1. Selezionare il pulsante **OK** (simbolo del segno di spunta).

    La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare per la successiva ubicazione.

1. Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.
1. Selezionare il pulsante **OK** (simbolo del segno di spunta).

    La pagina **Ordini cliente: inserisci** indica di stoccare entrambi i lavori di prelievo completati nell'ubicazione di staging in uscita.

1. Selezionare **OK**.

    Viene visualizzato il messaggio "Lavoro completato".

1. Immettere il secondo ID lavoro per l'ordine cliente 1.

    Esiste solo un'attività di prelievo per questo ID lavoro.

1. Selezionare **OK**.

    La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare.

1. Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.

    La targa specificata sarà una delle targhe generate dal sistema dalle attività di lavoro di rifornimento. Per assicurarsi di acquisire l'ID targa corretto, controllare il livello di scorte nella pagibna **Scorte disponibili** per l'articolo, l'ubicazione e la quantità.

1. Selezionare il pulsante **OK** (simbolo del segno di spunta).
1. Confermare le istruzioni per l'attività di isnerimento nell'ubicazione di staging in uscita.
1. Selezionare **OK**.

    Viene visualizzato il messaggio "Lavoro completato".

L'ordine cliente 2 è bloccato dal prelievo perché l'attività di rifornimento a cui è collegato non è stata completata. Attualmente, vi è ancora una quantità di 30 ea nell'ubicazione di prelievo e la quantità di rifornimento per l'ordine cliente 2 è di 60 ea. La somma delle scorte disponibili e delle scorte di rifornimento (90 ea) supera la quantità di overflow di 0,65 PL (o 65 ea). Prima di completare il lavoro di rifornimento, è necessario eseguire il prelievo per l'ordine cliente 3.

1. Immettere l'ID lavoro per l'ordine cliente 3.

    Esiste solo un'attività di prelievo per questo ID lavoro.

1. Selezionare **OK**.

    La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare.

1. Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.

    La targa specificata sarà una delle targhe generate dal sistema dalle attività di lavoro di rifornimento. Per assicurarsi di acquisire l'ID targa corretto, controllare il livello di scorte nella pagibna **Scorte disponibili** per l'articolo, l'ubicazione e la quantità.

1. Selezionare il pulsante **OK** (simbolo del segno di spunta).
1. Confermare le istruzioni per l'attività di isnerimento nell'ubicazione di staging in uscita.
1. Selezionare **OK**.

    Viene visualizzato il messaggio "Lavoro completato".

Non appena la somma della quantità disponibile nell'ubicazione di prelievo e la quantità di rifornimento è inferiore alla soglia, sarà possibile elaborare il restante lavoro di rifornimento.

Tornare alla pagina **Dettagli del lavoro** e notare che la disponibilità del lavoro di rifornimento per la parte finale di rifornimento (per l'ordine cliente 2) è *Aperto*, perché ora c'è abbastanza spazio nell'ubicazione per accettare il rifornimento.

Ora puoi elaborare questo lavoro di rifornimento tramite il dispositivo mobile.

1. Passare a **Inventario \> Rifornimento**.

    Viene richiesto di completare il lavoro di rifornimento rimanente. Vengono visualizzati il numero, la quantità e l'ubicazione di prelievo dell'articolo.

1. Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.
1. Selezionare il pulsante **OK** (simbolo del segno di spunta).

    Il sistema genera un numero di targa di destinazione per la nuova targa per l'articolo selezionato.

1. Selezionare **OK** per confermare il valore.

    Viene mostrato il lavoro di inserimento che indica all'utente di inserire la targa di destinazione nell'ubicazione di rifornimento. L'ubicazione *Inserisci* dovrebbe essere **06A01R2S1B**.

1. Confermare i dettagli di inserimento e selezionare **OK**.

    Vengono visualizzati i messaggi "Lavoro completato" e "Nessun lavoro disponibile".

Ora è possibile scegliere l'ordine cliente 2. Si è sbloccato quando sono stati completati i lavori di rifornimento collegati all'ordine cliente.

1. Immettere l'ID lavoro per l'ordine cliente 2.

    Esiste solo un'attività di prelievo per questo ID lavoro.

1. Selezionare **OK**.

    La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare.

1. Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.

    La targa specificata sarà la targa generata dal sistema dall'attività di lavoro di rifornimento. Per assicurarsi di acquisire l'ID targa corretto, controllare il livello di scorte nella pagibna **Scorte disponibili** per l'articolo, l'ubicazione e la quantità.

1. Selezionare il pulsante **OK** (simbolo del segno di spunta).
1. Confermare le istruzioni per l'attività di isnerimento nell'ubicazione di staging in uscita.
1. Selezionare **OK**.

    Viene visualizzato il messaggio "Lavoro completato".

## <a name="notes-and-tips"></a>Note e suggerimenti

- Questa funzionalità funziona con tutti i tipi di rifornimento: domanda ondata, min / max, domanda di carico e assegnazione.
- È possibile sovrascrivere manualmente la disponibilità del lavoro di rifornimento per ciascuna intestazione di lavoro dalla pagina **Dettagli del lavoro** se si desidera.
- Quando il sistema imposta la disponibilità del lavoro di rifornimento, considera qualsiasi inventario che si trova già nell'ubicazione prima del completamento di qualsiasi lavoro
- Ogni lavoro dell'ordine cliente è collegato a un lavoro di rifornimento specifico. Non esiste una corrispondente funzionalità di disponibilità del lavoro di vendita.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]