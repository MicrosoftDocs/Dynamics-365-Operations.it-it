---
title: Conferma e trasferimento
description: Questo argomento spiega come utilizzare la funzione di conferma e trasferimento, che consente agli utenti di spedire carichi dal magazzino prima di completare tutto il lavoro associato a tali carichi.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate,WHSWorkTemplateTable,WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6104e457a62f340951c187d0f2dbe48b0dffdf7f
ms.sourcegitcommit: d25d0feb3f8a5a760eba50ba5f46e1db02737d25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "3677412"
---
# <a name="confirm-and-transfer"></a>Conferma e trasferimento

[!include [banner](../includes/banner.md)]

La funzionalità di *conferma e trasferimento* consente agli utenti di spedire carichi dal magazzino prima di completare tutto il lavoro associato a tali carichi. Quando viene ricevuta una spedizione che include righe di carico che non sono state ritirate completamente, all'utente che conferma viene richiesto di dividere le quantità rimanenti su un nuovo carico o di annullare le quantità incomplete.

Sistemi impostati per consentire scenari di supporto della suddivisione del carico in cui i carichi pianificati e parzialmente caricati devono essere adattati a causa di circostanze nuove o mutevoli.

Il client include una logica che consente di chiudere e confermare un carico parzialmente caricato come spedito. Tutte le spedizioni rimanenti e le righe di carico (comprese le quantità di righe complete o parziali) vengono quindi trasferite a un carico e una spedizione appena creati, se è necessario il rollover e la configurazione lo consente. Le nuove spedizioni e i carichi vengono creati automaticamente in base ai criteri iniziali per la spedizione e la creazione del carico e i loro attributi principali rimangono invariati. Esiste anche un'opzione per annullare automaticamente le quantità rimanenti se un ordine di lavoro non è stato ancora creato e l'utente ritiene che questo annullamento sia necessario.

Questa funzionalità supporta scenari in cui il carico completo non rientra in un singolo camion o in cui parte del carico deve lasciare il magazzino prima che il resto del carico sia pronto per la spedizione. In questi scenari, i prodotti rimanenti possono essere trasferiti su un nuovo carico e quindi su un nuovo camion. Poiché questa funzionalità può essere utilizzata con carichi altrimenti destinati a richiedere la spedizione a pieno carico, offre ulteriore flessibilità in modo che i responsabili del trasporto possano risolvere scenari non standard o imprevisti.

Quando un carico viene suddiviso, la funzionalità *Conferma e trasferisci* esegue queste azioni:

- Nuovi carichi e spedizioni vengono creati come richiesto. Ogni carico o spedizione avrà la maggior parte degli stessi attributi del carico o della spedizione originale. L'eccezione è lo stato del carico, che verrà ricalcolato in base allo stato del lavoro.
- L'utente viene informato che è stato creato un nuovo carico. L'utente viene inoltre informato dell'ID del nuovo carico.
- Le righe di carico, le intestazioni del lavoro e le righe di lavoro che sono state divise vengono aggiornate con le nuove informazioni di carico e spedizione.
- Se un'intera spedizione viene suddivisa, la spedizione viene mantenuta e vengono aggiornati solo i riferimenti di carico. Se la spedizione deve essere divisa, viene creata una nuova spedizione.

Quando le quantità rimanenti vengono annullate, tutte le quantità della riga di carico che non sono state prelevate e alle quali non sono associati lavori non annullati vengono rimosse dal carico. Se è in corso un lavoro, l'utente può solo dividere il carico. Le quantità rimanenti non possono essere annullate.

È possibile dividere solo i carichi che soddisfano tutti i seguenti criteri:

- Una o più righe di carico hanno quantità prelevate.
- Lo stato del carico è inferiore a quello caricato.
- Non ci sono dati sulla riga di carico. Questi dati vengono creati tramite il consolidamento della targa nell'ubicazione di gestione temporanea e la funzionalità *Conferma e trasferisci* non supporta il consolidamento della targa.
- Nessun inventario è attualmente in attesa di imballaggio in un'ubicazione di imballaggio. La funzionalità *Conferma e trasferisci* non supporta le scorte prelevate presso la stazione di imballaggio ma che non sono state ancora imballate.

> [!NOTE]
> Questa funzionalità differisce dalla funzionalità del carico di trasporto, che dovrebbe essere utilizzata nei magazzini che non possono mai pianificare e creare carichi prima del prelievo, ma che invece caricano lo spazio di trasporto disponibile al termine del prelievo.
>
> Utilizza la funzionalità *Conferma e trasferisci* in situazioni in cui i carichi sono generalmente pianificati e creati in anticipo, ma a volte si verificano eccezioni in cui il carico non si adatta al trasporto disponibile (come un camion).

## <a name="turn-on-confirm-and-transfer"></a>Attivare Conferma e trasferisci

Prima di poter utilizzare la funzionalità *Conferma e trasferisci*, deve essere attivata nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Conferma e trasferisci*

## <a name="set-up-confirm-and-transfer"></a>Configurare Conferma e trasferisci

Per utilizzare la funzionalità *Conferma e trasferisci*, è necessario attivarla in ogni relativo modello di carico. Inoltre, a seconda delle esigenze, è consigliabile preparare i tuoi modelli di lavoro per supportare la funzionalità. Se vuoi analizzare lo scenario di esempio fornito più avanti in questo argomento, configura il sistema come descritto in questa sezione. Tale scenario è basato su dati dimostrativi **USMF**.

### <a name="prepare-your-load-templates"></a>Preparare i modelli di carico

1. Accedere a **Gestione magazzino \> Impostazione \> Carico \> Modelli di carico**.
1. Nel riquadro azioni seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Seleziona la casella di controllo **Consenti divisione del carico durante la conferma della spedizione** per ciascun modello esistente in cui vuoi attivare la funzione. In alternativa, seleziona **Nuovo** per creare un nuovo modello e configurarlo come richiesto. Ogni carico creato utilizzando quel modello erediterà questa funzionalità. Se stai lavorando con dati dimostrativi **USMF**, attiva la funzionalità per il modello di carico **Contenitore da 20'** .

### <a name="prepare-your-work-templates"></a>Preparare i modelli di lavoro

Questa configurazione non è richiesta in tutte le situazioni. L'esempio che viene mostrato qui garantisce che il lavoro possa essere suddiviso dalla spedizione per supportare lo scenario di esempio fornito più avanti in questo argomento. Esistono anche altri modi per ottenere questo risultato.

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nella griglia nella parte superiore della pagina, seleziona un modello di lavoro esistente in cui vuoi configurare la funzionalità *Conferma e trasferisci*. Se stai lavorando con dati dimostrativi **USMF**, seleziona il modello di lavoro **51 prelievi da approntare**. In alternativa, crea un nuovo modello di lavoro.
1. Nel riquadro azioni, seleziona **Modifica query** per aprire la finestra di dialogo **Vendite**.
1. Nella finestra di dialogo **Vendite**, nella scheda **Ordinamento**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Transazioni lavoro temporanee*
    - **Tabella derivata:** *Transazioni lavoro temporanee*
    - **Campo:** *ID spedizione*
    - **Direzione di ricerca:** *Crescente*

1. Seleziona **OK** per salvare le impostazioni e chiudi la finestra di dialogo **Vendite**.
1. Se ricevi un messaggio che indica che il raggruppamento verrà reimpostato, selezionare **Sì** per continuare.
1. Nella griglia nella parte superiore della pagina **Modelli di lavoro**, seleziona il modello appena modificato, quindi nel riquadro azioni seleziona **Suddivisioni intestazione lavoro**.
1. Nel riquadro azioni seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Nella griglia, imposta i seguenti valori:

    - **Nome tabella:** *Transazioni lavoro temporanee*
    - **Nome campo:** *ID spedizione*
    - **Raggruppa per questo campo:** seleziona questa casella di controllo.

1. Nel riquadro azioni selezionare **Salva**.
1. Chiudere la pagina.

## <a name="scenario"></a>Scenario

Questo scenario mostra un esempio in cui il processo di prelievo non è ancora completato, ma gli articoli che sono stati prelevati finora devono essere caricati su un camion e spediti comunque. Pertanto, l'utente può dividere le righe di carico non prelevato su un nuovo carico. Tutte le relazioni con i dati verranno quindi automaticamente aggiornate.

> [!NOTE]
> I valori specifici descritti in questo scenario sono basati su dati dimostrativi **USMF**. È consigliabile utilizzare questi dati dimostrativi mentre stai dimostrando o imparando a utilizzare la funzione. Se non stai usando dati dimostrativi **USMF**, sostituisci i tuoi valori come richiesto.

### <a name="step-1-create-a-load-that-has-multiple-load-lines"></a>Passaggio 1: creare un carico con più righe di carico

Prima di poter utilizzare questa funzionalità, devi disporre di un carico contenente più righe di carico. Devi anche verificare che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli degli ordini cliente che crei. Rivedi la configurazione della direttiva di ubicazione (**Gestione magazzino \> Impostazione \> Direttive di ubicazione**) e prendi nota delle ubicazioni di prelievo utilizzate per il prelievo degli ordini cliente. Se è necessario regolare le scorte, crea movimenti manuali, utilizza il rifornimento o utilizza qualsiasi altro flusso, come richiesto.

Per creare un carico idoneo, crea innanzitutto tre ordini cliente seguendo questi passaggi.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel riquadro azioni, scegli **Nuovo** per aprire la finestra di dialogo **Crea ordine cliente**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori (come minimo):

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-004* (*Cave Wholesales*).
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *51*.

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo **Crea ordine cliente**.
1. Viene aperto il nuovo ordine cliente. Nella griglia **Righe ordine cliente**, aggiungi una riga che abbia i seguenti valori:

    - **Numero articolo:** *M9200*
    - **Quantità:** *40*
    - **Unità:** *unità*

1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nel riquadro azioni, seleziona **Prenota lotto** per aprire la pagina **Prenotazione**.
1. Prenota le scorte sulla riga di vendita, quindi chiudi la pagina **Prenotazione**.
1. Ripeti i passaggi da 1 a 4 per aggiungere un secondo ordine cliente per lo stesso cliente e magazzino.
1. Aggiungi due righe di vendita con i seguenti valori. Dopo aver aggiunto ciascuna riga, prenota le scorte per la stessa come descritto nei passaggi da 6 a 8.

    - **Riga 1:** imposta il campo **Numero articolo** su *M9200*, il campo **Quantità** su *30* e il campo **Unità** su *unità*.
    - **Riga 2:** imposta il campo **Numero articolo** su *M9201*, il campo **Quantità** su *20* e il campo **Unità** su *unità*.

1. Ripeti i passaggi da 1 a 4 per aggiungere un terzo ordine cliente per lo stesso cliente e magazzino.
1. Aggiungi due righe di vendita con i seguenti valori. Dopo aver aggiunto ciascuna riga, prenota le scorte per la stessa come descritto nei passaggi da 6 a 8.

    - **Riga 1:** imposta il campo **Numero articolo** su *M9201*, il campo **Quantità** su *20* e il campo **Unità** su *unità*.
    - **Riga 2:** imposta il campo **Numero articolo** su *M9202*, il campo **Quantità** su *60* e il campo **Unità** su *unità*.

#### <a name="load-planning-workbench"></a>Workbench pianificazione carico

Il workbench di pianificazione del carico utilizzerà l'ID modello di carico per creare le spedizioni e rilasciare le righe dell'ordine cliente nel magazzino.

1. Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.
1. Nel campo **Magazzino** selezionare *51*.

    Ora allestirai il carico per gli ordini cliente appena creati.

1. Nella scheda **Righe di vendita**, nella griglia, seleziona le righe di vendita per i nuovi ordini cliente.
1. Nel riquadro azioni, nella scheda **Domanda e offerta**, nel gruppo **Aggiungi** seleziona **Al nuovo carico**.
1. Nella finestra di dialogo **Assegnazione modello di carico**,nel campo **ID modello di carico** seleziona *Contenitore da 20'*.
1. Selezionare **OK**.
1. Nella sezione **Carichi** della pagina **Workbench pianificazione carico**, nella griglia, trova l'ID carico appena creato per il magazzino *51*. Scorri verso destra fino a visualizzare la colonna **Consenti divisione del carico durante la conferma della spedizione**. La casella di controllo deve essere selezionata per il tuo carico.
1. Seleziona il carico.
1. Nel menu **Rilascia** sopra la griglia, seleziona **Rilascia in magazzino** per creare lavoro.
1. Nella finestra di dialogo **Rilascia carico in magazzino**, verifica che la Scheda dettaglio **Record da includere** mostri il tuo ID carico.
1. Selezionare **OK**.

    Potresti ricevere un messaggio "Operazione di elaborazione" mentre il sistema crea le spedizioni e il lavoro.

1. Nella sezione **Carichi** della pagina **Workbench pianificazione carico**, il tuo carico ora dovrebbe avere uno stato di carico di *In ondata*. Seleziona il carico, quindi nel menu **Informazioni correlate** sopra la griglia, seleziona **Dettagli ondata** per visualizzare gli ID spedizione che sono stati creati. Una volta completata l'operazione, chiudi la pagina **Ondate**.
1. Nella sezione **Carichi** della pagina **Workbench pianificazione carico**, seleziona il carico, quindi nel menu **Informazioni correlate** sopra la griglia, seleziona **Dettagli lavoro** per visualizzare il lavoro creato per gli ordini cliente.
1. Prendi nota degli ID lavoro che sono stati creati. Potrebbe essere necessario scorrere verso destra per visualizzare il numero dell'ordine cliente e l'ID spedizione associati all'ID lavoro.

### <a name="step-2-set-up-the-execution-flow-for-mobile-devices"></a>Passaggio 2: impostare il flusso di esecuzione per i dispositivi mobili

Le attività dei dispositivi mobili richiederanno l'immissione di informazioni da parte dell'utente, come l'ID lavoro o l'ID targa. Nei campi, queste informazioni sono in genere fornite agli utenti del magazzino sotto forma di codici a barre che si trovano sulla documentazione, l'imballaggio o il racking. Per completare i passaggi del dispositivo mobile per gli scenari, verifica di aver identificato gli ID di lavoro per le transazioni e gli ID targa per l'articolo e l'ubicazione nelle transazioni.

1. Accedi al dispositivo mobile utilizzando un ID utente e una password per il magazzino *51*.
1. Seleziona **In uscita**.
1. Seleziona **Prelievo vendite**.
1. Hai la possibilità di inserire l'ID lavoro o l'ID targa. Immetti l'ID di lavoro per il primo ordine cliente, quindi seleziona **Immetti**.
1. Nel campo **Ubi**, immetti l'ubicazione visualizzata per confermare l'ubicazione di prelievo. Quindi seleziona **Immetti**.
1. Nel campo **Targa**, immetti l'ID targa. L'ID della targa deve corrispondere all'articolo, al magazzino e all'ubicazione dell'articolo che viene prelevato dall'ubicazione selezionata. Al termine, seleziona **Immetti**.
1. Nel campo **Articolo**, immetti il numero dell'articolo per confermare l'articolo che viene prelevato, quindi seleziona **Immetti**.
1. Nel campo **Qtà**, immetti la quantità dell'articolo per confermare l'articolo che viene prelevato, quindi seleziona **Immetti**.
1. Nel campo **Targa destinazione**, immetti l'ID targa destinazione. Le targhe di destinazione sono definite dall'utente. Assicurati di inserire un ID targa che potrai ricordare. È consigliabile utilizzare la data corrente più una sequenza di due cifre (AAAMMGG\#\#) come formato, ad esempio *19112301*. Al termine, seleziona **Immetti**.
1. Rivedi le informazioni visualizzate. Queste informazioni sono le informazioni *Prelievo* che ora diventeranno i dati *Stoccaggio* per la transazione di stoccaggio. Al termine, seleziona **Immetti**.

    - Ricevi un messaggio di tipo **Lavoro completato**.

1. Ripeti i passaggi da 4 a 10 per l'ID lavoro del secondo ordine cliente.

Il prossimo passaggio consiste nel caricare le due targhe prelevate sul camion.

1. Accedi al dispositivo mobile utilizzando un ID utente e una password per il magazzino *51*.
1. Seleziona **In uscita**.
1. Seleziona **Caricamento vendite**.
1. Immettere l'ID targa di destinazione definito dall'utente creato per il primo ID di lavoro nella procedura precedente. Quindi seleziona **Immetti** per posizionare la targa di destinazione nell'ubicazione **STAGE**.
1. Immetti nuovamente l'ID targa di destinazione, quindi seleziona **Immetti** per mettere la targa nell'ubicazione **PORTELLONE**.
1. Ripeti i passaggi da 4 a 5 per l'ID targa di destinazione creato per il secondo ID lavoro.

I due ID di lavoro verranno ora chiusi (caricati).

### <a name="step-3-confirm-the-outbound-shipment"></a>Passaggio 3: confermare la spedizione in uscita

In questo passaggio, confermerai i due ordini cliente e il lavoro che sono stati completati per il carico in modo da spedire gli articoli prelevati del carico e creerai un nuovo carico per gli articoli non prelevati. La conferma della spedizione in uscita deve essere effettuata nella pagina **Dettagli carico**.

1. Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.
1. Nella sezione **Carichi**, nella griglia, seleziona la riga per l'ID carico creato.
1. Seleziona il collegamento ID carico per aprire la pagina **Dettagli carico**.
1. Nella pagina **Dettagli carico**, nel riquadro azioni, nella scheda **Spedisci e ricevi** e nel gruppo **Conferma**, seleziona **Spedizione in uscita** per iniziare la conferma.
1. Nella finestra di dialogo **Conferma spedizione**, nel campo **Metodi di divisione del carico durante la conferma spedizione**, seleziona *Dividi la quantità in un nuovo carico*.
1. Selezionare **OK**.

    È possibile che venga visualizzato il messaggio "Operazione di elaborazione".

    Ricevi messaggi informativi che indicano che la spedizione per il tuo carico è stata confermata e che un nuovo carico è stato creato dalla quantità suddivisa.

Aggiorna la pagina **Workbench pianificazione carico** per vedere il carico appena creato.

Puoi anche confermare che le relazioni di transazione sono state aggiornate nei modi seguenti:

- Le rimanenti righe di spedizione (non elaborate) e le righe di spedizione vengono aggiornate con il nuovo ID carico.
- L'ordine cliente è collegato al nuovo ID carico.
- Il carico originale non include le righe di carico rimanenti.
- Il lavoro rimanente è stato aggiornato con il nuovo ID carico.
- L'ondata rimane la stessa.
- Lo stato del nuovo carico è stato aggiornato correttamente. Se lo stato del lavoro è _In corso_, anche lo stato del carico dovrebbe essere _In corso_.

## <a name="notes-and-tips"></a>Note e suggerimenti

- Puoi anche attivare il parametro **Consenti divisione del carico durante la conferma della spedizione** dopo che il carico è stato creato con il parametro **Modello di carico** disattivato ma prima dell'inizio del processo di caricamento. Vai al carico desiderato, quindi, nella vista dell'intestazione, attiva il parametro.
- L'opzione **Dividi quantità in un nuovo carico** funziona anche quando alcune delle rimanenti intestazioni di lavoro hanno uno stato di *In corso*. Pertanto, è ancora possibile utilizzare la funzionalità anche se i lavoratori stanno già eseguendo gli ordini di prelievo.
- Se selezioni **Annulla quantità non soddisfatta** mentre è rimasto lavoro con uno stato di *Aperto* o *In corso*, viene visualizzato il seguente messaggio di errore: "Impossibile annullare la quantità rimanente per il carico. Lavoro esistente per il carico".
- Se selezioni **Annulla quantità non soddisfatta** quando non vi sono lavori rimanenti ma sul carico sono presenti righe di carico non rilasciate, viene visualizzato il seguente messaggio di errore: "Impossibile confermare la spedizione per carico poiché la quantità per l'articolo supera la percentuale definita per la consegna in corso". Per evitare l'errore, puoi impostare la percentuale **In consegna** sulla riga di carico non rilasciata al 100 percento. Le righe non rilasciate non verranno spostate in un nuovo carico, ma il carico corrente verrà confermato con una consegna insufficiente. In questo caso, non sarà possibile rilasciare nuovamente l'ordine originale. Pertanto, dovrai gestirlo in qualche altro modo.
