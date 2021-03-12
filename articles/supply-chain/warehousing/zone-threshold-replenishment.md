---
title: Rifornimento soglia di zona
description: Il rifornimento basato su zone utilizza una strategia di rifornimento minimo/massimo (min/massimo), ma valuta intere zone di magazzino anziché solo singole ubicazioni. Pertanto, i responsabili del magazzino possono apprendere più rapidamente quando sono necessarie scorte aggiuntive in una zona di prelievo.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 2e83d6885bf7400916d633a49d3b19b8843b0269
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965504"
---
# <a name="zone-threshold-replenishment"></a>Rifornimento soglia di zona

[!include [banner](../includes/banner.md)]

Il rifornimento basato su zone utilizza una strategia di [rifornimento](replenishment.md) minimo/massimo (min/massimo), ma valuta intere zone di magazzino anziché solo singole ubicazioni. Pertanto, i responsabili del magazzino possono apprendere più rapidamente quando sono necessarie scorte aggiuntive in una zona di prelievo.

L'impostazione per questa funzione è simile all'impostazione per il rifornimento in base all'ubicazione. Tuttavia, quando si imposta un modello per il rifornimento minimo/massimo, è anche possibile specificare se la soglia deve essere valutata per ubicazione o per zona. Se si imposta una valutazione basata su zone, è necessario aggiungere zone specifiche alla query di selezione delle zone.

Come il rifornimento min/max basato sull'ubicazione, il rifornimento min/max basato sulla zona si basa sull'impostazione di una soglia minima di scorte che attiva la creazione del lavoro di rifornimento per gli articoli selezionati. Questo lavoro di rifornimento aumenterà le scorte fino alla soglia massima specificata per la zona.

> [!NOTE]
> I processi di rifornimento della zona per le varianti di prodotto non sono supportati nella versione corrente.


A differenza del rifornimento min/max basato sull'ubicazione, il rifornimento min/max basato sulla zona non richiede ubicazioni fisse per valutare se le ubicazioni devono contenere un articolo specifico. Pertanto, il rifornimento in base alla zona consente di utilizzare il rifornimento minimo/massimo anche se non disponi di ubicazioni fisse per ciascun articolo o variante dell'articolo nel magazzino. Quando una quantità nella zona scende al di sotto della soglia minima specificata, viene creato il lavoro di rifornimento. Le direttive sull'ubicazione determineranno in quale ubicazione specifica devono essere posizionate le scorte

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a>Attiva la funzione di rifornimento della soglia di zona

Prima di poter utilizzare la funzionalità *Rifornimento soglia di zona*, deve essere attivata nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Rifornimento soglia di zona*

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a>Impostare il rifornimento basato su zone

Per impostare un rifornimento basato sulla zona, è necessario configurare diverse parti del sistema. Questa sezione introduce le varie impostazioni e fornisce valori di dati dimostrativi che puoi immettere se desideri analizzare lo scenario alla fine di questo argomento.

### <a name="set-up-directive-codes"></a>Impostare i codici direttiva

I [codici direttiva](control-warehouse-location-directives.md) ti consentono di essere più specifico quando definisci il modello di ubicazione utilizzato in un modello di lavoro. Ogni codice stabilisce un valore comune a cui è possibile fare riferimento quando si configura ciascun tipo di modello.

#### <a name="view-and-edit-directive-codes"></a>Visualizzare e modificare i codici direttiva

Per visualizzare o modificare i codici direttiva, vai a **Gestione magazzino \> Impostazione \> Codici direttiva**.

#### <a name="prepare-demo-data-directive-codes"></a>Preparare i codici direttiva per i dati dimostrativi

Questo esempio mostra come preparare un codice direttiva. Se prevedi di analizzare lo scenario alla fine di questo argomento, utilizza i valori dei dati dimostrativi forniti qui. Altrimenti, usa i tuoi valori.

1. Seleziona la persona giuridica **USMF** che deve utilizzare i dati dimostrativi.
1. Vai a **Gestione magazzino \> Impostazioni \> Codici di direttiva**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Codice direttiva:** _Rifornimento zona_
    - **Descrizione della direttiva:** _Rifornimento zona_

1. Seleziona **Salva** per salvare il nuovo codice.

### <a name="set-up-replenishment-templates"></a>Imposta modelli rifornimento

I [modelli di rifornimento basato su quantità minima e massima](tasks/set-up-min-max-replenishment-process.md) sono il meccanismo principale per il mantenimento di livelli ottimali di ubicazioni di prelievo. In questi modelli, devi impostare le regole che verranno utilizzate per rifornire le scorte nel magazzino. Il rifornimento per il quale è possibile utilizzare i modelli include il rifornimento basato sulla zona.

#### <a name="view-and-edit-replenishment-templates"></a>Visualizzare e modificare i modelli di rifornimento

Un modello di rifornimento è un set di regole che controlla quando e come effettuare il rifornimento dell'ubicazione. Selezioni un modello per controllare quando e come viene effettuato il rifornimento. Per visualizzare o modificare i modelli di rifornimento, vai a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento**.

#### <a name="prepare-a-demo-data-replenishment-template"></a>Preparare un modello di rifornimento dei dati dimostrativi

Questo esempio mostra come preparare un modello di rifornimento. Se prevedi di analizzare lo scenario alla fine di questo argomento, utilizza i valori dei dati dimostrativi forniti qui. Altrimenti, usa i tuoi valori.

1. Seleziona la persona giuridica **USMF** che deve utilizzare i dati dimostrativi.
1. Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di rifornimento**.
1. Seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia **Panoramica**.
1. Nella nuova riga, imposta i seguenti valori. Accetta i valori predefiniti per tutti gli altri campi.

    - **Modello rifornimento:** _Rifornimento min/max zona_
    - **Descrizione:** _Rifornimento min/max zona_
    - **Tipo di rifornimento:** _Minimo o massimo_

1. Selezionare **Salva**.
1. Mentre la nuova riga è ancora selezionata nella griglia **Panoramica**, seleziona **Nuovo** sopra la griglia **Dettagli del modello rifornimento** per aggiungere una riga associata al modello di rifornimento *Rifornimento min/max zona* che hai appena creato.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero sequenza:** Immetti _1_.
    - **Descrizione:** Immetti _Rifornimento zona prelievo_.
    - **Unità di rifornimento:** Seleziona _EA_.
    - **Tipo di richiesta:** lascia vuoto questo campo.
    - **Codice direttiva:** questo campo collega il modello di rifornimento a una direttiva di ubicazione. Seleziona il codice direttiva per i dati dimostrativi che hai creato in precedenza (_Rifornimento zona_).
    - **Modello di lavoro**: lasciare vuoto questo campo.
    - **Quantità minima:** questo campo imposta la quantità a cui verrà attivato il rifornimento. Immetti _50_.
    - **Quantità massima:** questo campo imposta la quantità massima di un articolo che può essere presente in una zona. Il lavoro di rifornimento generato aumenterà le scorte fino a questa quantità. Immetti _150_.
    - **Unità:** questo campo imposta l'unità per i valori minimo e massimo. Seleziona _ea_.
    - **Incremento della domanda:** seleziona _Arrotonda_.
    - **Rifornisci ubicazioni fisse vuote:** seleziona questa casella di controllo.
    - **Rifornisci solo ubicazioni fisse:** seleziona questa casella di controllo.
    - **Modalità query prodotto:** seleziona _Query prodotto_.
    - **Ambito soglia di rifornimento:** questo campo definisce se il modello deve valutare per zona o per ubicazione specifica. Seleziona _Zona_.
    - **Magazzino:** seleziona _61_.

1. Seleziona **Seleziona prodotti** sopra la griglia **Dettagli modello di rifornimento**.
1. Nella finestra di dialogo **Query prodotto**, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** _Articoli_
    - **Tabella derivata:** _Articoli_
    - **Campo:** _Numero articolo_
    - **Criteri:** _A0001_

1. Seleziona **OK** per salvare la query e chiudere la finestra dialogo.
1. Seleziona **Seleziona zone da rifornire** sopra la griglia **Dettagli modello di rifornimento**.
1. Nella finestra di dialogo **Query zona**, nella scheda **Intervallo**, aggiungi una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** _Zona magazzino_
    - **Tabella derivata:** _Zona magazzino_
    - **Campo:** _ID zona_
    - **Criteri:** _PIANO_

1. Seleziona **OK** per salvare la query e chiudere la finestra dialogo.

### <a name="set-up-location-directives"></a>Imposta direttive ubicazione

A differenza del rifornimento min/max basato sull'ubicazione, il rifornimento min/max basato sulla zona richiede l'impostazione di entrambe le direttive sull'ubicazione di prelievo e sull'ubicazione di stoccaggio, poiché il sistema valuta l'intera zona anziché solo l'ubicazione di prelievo per il lavoro in uscita.

#### <a name="view-and-edit-location-directives"></a>Visualizzare e modificare le direttive sull'ubicazione

Per visualizzare o modificare le direttive sull'ubicazione, vai a **Gestione magazzino \> Impostazione \> Direttive ubicazione**.

Per esempi che mostrano come utilizzare le impostazioni per creare le direttive sull'ubicazione di prelievo richieste e le direttive sull'ubicazione di stoccaggio, vedi la sezione successiva.

#### <a name="prepare-demo-data-location-directives"></a>Preparare le direttive sull'ubicazione per i dati dimostrativi

Per preparare i dati dimostrativi in modo che possano essere utilizzati nello scenario alla fine di questo argomento, è necessario creare due direttive di ubicazione: una per il prelievo e una per lo stoccaggio.

##### <a name="create-a-replenishment-pick-directive"></a>Creare una direttiva di prelievo di rifornimento

1. Seleziona la persona giuridica **USMF** che deve utilizzare i dati dimostrativi.
1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, imposta il campo **Tipo di ordine di lavoro** su _Rifornimento_.
1. Nel riquadro azioni seleziona **Nuova** per creare una nuova direttiva.
1. Imposta i valori seguenti:

    - **Numero sequenza:** accetta il valore predefinito.
    - **Nome:** immetti _Prelievo zona_.
    - **Tipo di lavoro:** seleziona _Prelievo_.
    - **Sito:** Seleziona _6_.
    - **Magazzino:** seleziona _61_.
    - **Codice direttiva:** lascia vuoto questo campo.
    - **Più SKU:** imposta questa opzione su _No_.

1. Seleziona **Salva** per creare una direttiva con le impostazioni che hai configurato finora.
1. Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero sequenza:** Immetti _1_.
    - **Da quantità:** immetti _0_.
    - **A quantità:** immetti _10000000_.
    - **Unità:** lascia vuoto questo campo.
    - **Trova quantità:** seleziona _Nessuna_.
    - **Limita per unità:** deseleziona questa casella di controllo.
    - **Arrotonda a unità:** deseleziona questa casella di controllo.
    - **Individua quantità di imballaggio:** deseleziona questa casella di controllo.
    - **Consenti divisione:** seleziona questa casella di controllo.

1. Seleziona **Salva** per salvare la nuova riga.
1. Mentre la tua nuova riga è ancora selezionata nella griglia **Righe**, seleziona **Nuova** nella Scheda dettaglio **Azioni direttiva ubicazione** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero sequenza:** Immetti _1_.
    - **Nome:** immetti _Preleva da blocco_.
    - **Utilizzo ubicazioni fisse:** seleziona _Ubicazioni fisse e non fisse_.
    - **Consenti inventario negativo:** deseleziona questa casella di controllo.
    - **Lotto abilitato:** deseleziona questa casella di controllo.
    - **Strategia:** seleziona _Nessuna_.

1. Seleziona **Salva** per salvare la nuova azione.
1. Con la nuova azione ancora selezionata, seleziona **Modifica query** sopra la griglia **Azioni direttiva ubicazione**.
1. Viene visualizzata una finestra di dialogo della query, in cui è possibile selezionare le ubicazioni da rifornire. Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** _Ubicazioni_
    - **Tabella derivata:** _Ubicazioni_
    - **Campo:** _ID zona_
    - **Criteri:** _BULK_

1. Seleziona **OK** per salvare la query e chiudere la finestra dialogo.
1. Seleziona **Salva** per salvare la direttiva di ubicazione.

##### <a name="create-a-replenishment-put-directive"></a>Creare una direttiva di stoccaggio di rifornimento

1. Nella pagina **Direttive di ubicazione**, nel riquadro sinistro, verifica che il campo **Tipo di ordine di lavoro** sia è ancora impostato su _Rifornimento_.
1. Nel riquadro azioni seleziona **Nuova** per creare un'altra nuova direttiva.
1. Imposta i valori seguenti:

    - **Numero sequenza:** accetta il valore predefinito.
    - **Nome:** immetti _Stoccaggio zona_.
    - **Tipo di ordine di lavoro:** seleziona _Stoccaggio_.
    - **Sito:** Seleziona _6_.
    - **Magazzino:** seleziona _61_.
    - **Codice direttiva:** seleziona _Rifornimento zona_ per collegare questa direttiva di ubicazione con il modello di rifornimento creato in precedenza utilizzando il codice creato in precedenza.
    - **Più SKU:** imposta questa opzione su _No_.

1. Seleziona **Salva** per creare una direttiva con le impostazioni che hai configurato finora.
1. Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero sequenza:** Immetti _1_.
    - **Da quantità:** immetti _0_.
    - **A quantità:** immetti _10000000_.
    - **Unità:** lascia vuoto questo campo.
    - **Trova quantità:** seleziona _Nessuna_.
    - **Limita per unità:** deseleziona questa casella di controllo.
    - **Arrotonda a unità:** deseleziona questa casella di controllo.
    - **Individua quantità di imballaggio:** deseleziona questa casella di controllo.
    - **Consenti divisione:** seleziona questa casella di controllo.

1. Seleziona **Salva** per salvare la nuova riga.
1. Mentre la tua nuova riga è ancora selezionata nella griglia **Righe**, seleziona **Nuova** nella Scheda dettaglio **Azioni direttiva ubicazione** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero sequenza:** Immetti _1_.
    - **Nome:** immetti _Stoccaggio zona_.
    - **Utilizzo ubicazioni fisse:** seleziona _Ubicazioni fisse e non fisse_.
    - **Consenti inventario negativo:** deseleziona questa casella di controllo.
    - **Lotto abilitato:** deseleziona questa casella di controllo.
    - **Strategia:** seleziona _Consolida_.

1. Seleziona **Salva** per salvare la nuova azione.
1. Con la nuova azione ancora selezionata, seleziona **Modifica query** sopra la griglia **Azioni direttiva ubicazione**.
1. Viene visualizzata una finestra di dialogo della query, in cui è possibile selezionare la zona da rifornire. Questa zona deve essere la stessa zona specificata nel modello di rifornimento. Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** _Ubicazioni_
    - **Tabella derivata:** _Ubicazioni_
    - **Campo:** _ID zona_
    - **Criteri:** _PIANO_

1. Seleziona **OK** per salvare la query e chiudere la finestra dialogo.
1. Seleziona **Salva** per salvare la direttiva di ubicazione.

## <a name="scenario"></a>Scenario

Questa sezione fornisce uno scenario di esempio che mostra come utilizzare la funzione.

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a>Preparare i dati di esempio richiesti per lo scenario di esempio

Prima di iniziare ad analizzare lo scenario, devi attivare i dati di esempio e impostare la funzionalità come descritto in questa sezione e nelle sezioni precedenti di questo argomento.

#### <a name="use-the-usmf-legal-entity"></a>Utilizzare la persona giuridica USMF

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

#### <a name="prepare-additional-sample-data"></a>Preparare altri dati di esempio

Dopo aver selezionato la persona giuridica **USMF**, aggiungi i dati di esempio aggiuntivi richiesti, come descritto nella sezione [Impostare il rifornimento basato su zone](#setup) precedente in questo argomento.

#### <a name="check-your-on-hand-inventory"></a>Controllare le scorte disponibili

Segui questi passaggi per verificare che il sistema includa scorte sufficienti per supportare lo scenario di esempio.

1. Verifica che vi siano scorte disponibili per l'articolo *A0001* in due diverse ubicazioni nella zona di prelievo (*PIANO*) specificata nel modello di rifornimento. Tuttavia, le scorte totali dovrebbe essere inferiori alla quantità minima richiesta (*50*) specificata nel modello di rifornimento. In questo modo, puoi simulare il modo in cui si verifica il calcolo per l'intera zona anziché solo per una singola ubicazione. **Utilizza uno qualsiasi dei processi di magazzino per regolare le scorte in base alle esigenze.**
1. Verifica che ci siano abbastanza scorte dell'articolo *A0001* in un'ubicazione in blocco specificata nella direttiva sull'ubicazione di prelievo zona in cui il lavoro di rifornimento dovrebbe prelevare gli articoli dall'ID zona *MASSA*. Le scorte totali devono essere superiori alla quantità massima richiesta (*150*) specificata nel modello di rifornimento.
1. Facoltativo ma consigliato: attieniti alla seguente procedura per creare un giornale di registrazione delle scorte:

    1. Vai a **Gestione magazzino \> Inserimenti nel giornale di registrazione \> Articoli \> Rettifica di magazzino**.
    1. Selezionare **Nuovo**.
    1. Nella finestra di dialogo **Crea giornale di registrazione magazzino**, nel campo **Magazzino**, seleziona *61*.
    1. Selezionare **OK**.
    1. Nella Scheda dettaglio **Righe giornale di registrazione**, utilizza il pulsante **Nuova** per aggiungere tre righe alla griglia e impostare i seguenti valori. Dopo aver completato l'impostazione di ciascuna riga, seleziona **Salva**.

        - **Riga 1:**

            - **Numero articolo:** *A0001*
            - **Sito:** *6*
            - **Magazzino:** *61*
            - **Ubicazione:** *02A01R1S1B*
            - **Targa:** seleziona una targa esistente nell'elenco o crea una nuova targa.
            - **Quantità:** *1000*

        - **Riga 2:**

            - **Numero articolo:** *A0001*
            - **Sito:** *6*
            - **Magazzino:** *61*
            - **Ubicazione:** *07A01R2S1B*
            - **Targa:** seleziona una targa esistente nell'elenco o crea una nuova targa.
            - **Quantità:** *15*

        - **Riga 3:**

            - **Numero articolo:** *A0001*
            - **Sito:** *6*
            - **Magazzino:** *61*
            - **Ubicazione:** *07A01R1S1B*
            - **Targa:** seleziona una targa esistente nell'elenco o crea una nuova targa.
            - **Quantità:** *10*

    1. Nel riquadro azioni seleziona **Convalida**. Risolvi eventuali errori rilevati prima di andare al passaggio successivo.
    1. Nel riquadro azioni seleziona **Registra** per registrare le scorte nel magazzino.

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a>Scenario di esempio: eseguire il rifornimento min/max basato sulla zona

Dopo che tutti i dati di esempio dei prerequisiti sono presenti, puoi attivare il rifornimento seguendo questi passaggi.

1. Vai a **Gestione magazzino \> Rifornimento \> Rifornimenti**.
1. Nella finestra di dialogo **Rifornimento**, nella Scheda dettaglio **Record da includere**, seleziona **Filtro**.
1. Nella finestra di dialogo **Richiesta di informazioni**, nella scheda **Intervallo**, modifica la riga della tabella predefinita nel modo seguente:

    - **Tabella:** seleziona _Modelli di rifornimento_.
    - **Tabella derivata:** seleziona _Modelli di rifornimento_.
    - **Campo:** seleziona _Modello di rifornimento_.
    - **Criteri:** seleziona _Rifornimento min/max zona_. Questo modello di rifornimento è il modello di rifornimento creato durante la preparazione dei dati dimostrativi per questo scenario.

1. Seleziona **OK** per salvare la query e tornare alla finestra dialogo **Rifornimento**.
1. Seleziona **OK** per eseguire il modello di rifornimento.

Il lavoro di rifornimento viene ora creato per prelevare le scorte dalla zona *MASSA* e rifornirle nella zona *PIANO*.

## <a name="notes-and-tips"></a>Note e suggerimenti

Ecco alcune note e suggerimenti per utilizzare la funzionalità:

- Per impostare il lavoro di rifornimento che va nella zona desiderata, puoi collegare le righe del modello di rifornimento e le direttive di ubicazione in uno dei seguenti modi:

    - Modifica la query dell'intestazione della direttiva di ubicazione e filtra le righe del modello di rifornimento selezionato.
    - Utilizza un codice direttiva sulla riga del modello di rifornimento e associalo alla direttiva di ubicazione di stoccaggio.

- Se stai utilizzando ubicazioni dinamiche, il lavoro di rifornimento verrà creato per la prima ubicazione disponibile o per un'ubicazione che contiene già scorte, se l'azione della direttiva ubicazione è impostata per utilizzare la strategia **Consolida**.
- Se stai utilizzando ubicazioni fisse anziché zone, è consigliabile utilizzare [rifornimento min/max standard](tasks/set-up-min-max-replenishment-process.md).
