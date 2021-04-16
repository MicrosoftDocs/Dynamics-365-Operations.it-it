---
title: Raggruppamento righe prelievo
description: In questo argomento viene fornita una panoramica del raggruppamento delle righe prelievo.
author: Mirzaab
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: fe0e63ef742b7bfd09684a94d273a1841d24599c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828275"
---
# <a name="pick-line-grouping"></a>Raggruppamento righe prelievo

[!include [banner](../includes/banner.md)]

Il raggruppamento delle righe di prelievo consente di combinare più righe di lavoro con lo stesso articolo e posizione in un unico prelievo che viene presentato all'utente sul dispositivo mobile. Pertanto, gli addetti al magazzino possono ricevere le istruzioni più efficienti possibili, ma viene mantenuta anche la necessaria separazione delle righe di lavoro nel sistema (ad esempio, per diversi contenitori, ordini e così via).

## <a name="turn-on-the-pick-line-grouping-feature"></a>Attivare la funzionalità di raggruppamento delle righe di prelievo

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Raggruppamento righe prelievo*

## <a name="set-up-pick-line-grouping"></a>Configurare il raggruppamento delle righe prelievo

### <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome voce di menu**, immetti *Prelievo riga gruppo di vendita*.
1. Nel campo **Titolo**, immetti *Prelievo riga gruppo di vendita*. Questo titolo verrà visualizzato nel menu del dispositivo mobile.
1. Selezionare *Lavoro* nel campo **Modalità**.
1. Impostare l'opzione **Utilizza lavoro esistente** su *Sì*.
1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - Nel campo **Diretto da**, selezionare *Diretto dall'utente*.
    - Impostare l'opzione **Genera targa** su *Sì*.
    - Impostare l'opzione **Prelievo gruppo** su *Sì*.
    - Accettare i valori predefiniti per le opzioni rimanenti.

1. Seguire questi passaggi per configurare le classi di lavoro valide per la voce di menu del dispositivo mobile:

    1. Nella Scheda dettagli **Classi di lavoro**, selezionare **Nuovo**.
    2. Nel campo **ID classe di lavoro**, è possibile selezionare *Vendite* o *Prelievo SO*, a seconda del magazzino che verrà utilizzato. Per questo scenario, selezionare *Prelievo SO*.

        Il campo **Tipo ordine di lavoro** viene automaticamente impostato su *Ordini cliente*.

### <a name="set-up-a-mobile-device-menu"></a>Configurare un menu per dispositivo mobile

Segui questi passaggi per aggiungere la voce di menu appena creata al file **In uscita**.

1. Accedi a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Il riquadro dell'elenco mostra tutti i menu dei dispositivi mobili esistenti. Seleziona *In uscita* nell'elenco.
1. Nell'elenco **Menu e voci di menu disponibili**, trovare e selezionare la voce di menu *Prelievo riga gruppo di vendita* appena creata.
1. Seleziona il pulsante freccia destra per spostare la voce di menu *Prelievo riga gruppo di vendita* sull'elenco **Struttura menu**.
1. Utilizzare i pulsanti freccia su o freccia giù per spostare la voce di menu nella posizione desiderata nella struttura di menu.
1. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-a-work-template"></a>Configurare un modello di lavoro

1. Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.
1. Nella griglia **Panoramica**, trovare e selezionare il modello di lavoro da utilizzare con questa funzione. Per questo scenario, selezionare il modello *51 prelievi da approntare*.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, selezionare **Aggiungi** e quindi impostare i seguenti valori per la nuova riga:

    - Nella colonna **Tabella** selezionare *Transazioni lavoro temporanee*.
    - Nella colonna **Tabella derivata** selezionare *Transazioni lavoro temporanee*.
    - Nella colonna **Campo** selezionare *Numero articolo*.
    - Nella colonna **Direzione di ricerca**, selezionare *Crescente*.

1. Selezionare **OK** per chiudere la finestra di dialogo e salvare la selezione.
1. Viene visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?". Selezionare **Sì** per continuare.

> [!IMPORTANT]
> Affinché la funzionalità di raggruppamento delle righe di prelievo funzioni, le righe di lavoro devono essere ordinate per ID articolo. Se le righe che hanno gli stessi articoli non sono in sequenza una dopo l'altra, non verranno raggruppate.

## <a name="example"></a>Esempio

### <a name="create-picking-work"></a>Creare il lavoro di prelievo

Prima di poter impostare il raggruppamento delle righe di prelievo, è necessario creare del lavoro in uscita idoneo.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente.
1. Nel campo **Conto cliente** selezionare *US-004*.
1. Nel campo **Magazzino** della Scheda dettaglio **Generale**, selezionare *51*.
1. Selezionare **OK**.
1. Nella Scheda dettagli **Righe ordine cliente**, aggiungere le sei righe seguenti:

    - **Riga 1:** nel campo **Numero articolo** selezionare *M9200*. Nel campo **Quantità** immettere *3*
    - **Riga 2:** nel campo **Numero articolo** selezionare *M9201*. Nel campo **Quantità** immettere *3*
    - **Riga 3:** nel campo **Numero articolo** selezionare *M9202*. Nel campo **Quantità** immettere *2*
    - **Riga 4:** nel campo **Numero articolo** selezionare *M9200*. Nel campo **Quantità** immettere *1*
    - **Riga 5:** nel campo **Numero articolo** selezionare *M9200*. Nel campo **Quantità** immettere *3*
    - **Riga 6:** nel campo **Numero articolo** selezionare *M9202*. Nel campo **Quantità** immettere *7*

    Ecco un riepilogo delle quantità totali per ciascun articolo:

    - **Articolo M9200:** *7* ciascuno
    - **Articolo M9201:** *3* ciascuno
    - **Articolo M9202:** *9* ciascuno

1. Prima di rilasciare gli ordini al magazzino, è necessario assicurarsi che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli di tutti gli ordini. Rivedere l'impostazione **Direttiva ubicazione** per determinare quali ubicazioni di prelievo vengono utilizzate per il prelievo dell'ordine cliente. Se stai usando l'ambiente di dati demo Contoso per il magazzino *51*, verifica che ci siano scorte disponibili.

    È ora necessario prenotare le scorte per ogni riga.

1. Nella Scheda dettaglio **Righe ordine cliente**, seleziona una delle righe da prenotare.
1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per applicare la prenotazione. Quindi, chiudere la pagina.
1. Ripetere i passaggi da 8 a 10 per le righe rimanenti che devono essere prenotate.

    È necessario ora rilasciare l'ordine cliente al magazzino.

1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Si riceve un messaggio che informa che una spedizione e un ciclo sono stati creati e che il ciclo è stato inviato per essere eseguito in batch.

    Quando il ciclo e tutti i processi a valle sono stati completati, viene creato un ID lavoro per il lavoro che ha sei righe. Le righe sono ordinate per numero articolo.

1. Passare a **Gestione magazzino \> Lavoro \> Tutti i lavori** per visualizzare tutti i lavori creati. Prendere nota del valore **ID lavoro**, in modo da poterlo utilizzare nella procedura successiva.

### <a name="initiate-picking-from-the-mobile-device"></a>Avviare il prelievo dal dispositivo mobile

1. Accedere al dispositivo mobile come utente configurato per il magazzino *51*.
1. Sul dispositivo mobile, selezionare il menu che include la nuova voce di menu del dispositivo mobile. Per questo scenario, selezionare **In uscita**.
1. Selezionare la voce di menu **Prelievo riga gruppo di vendita** per avviare il prelievo.
1. Immetti il valore **ID lavoro** di cui hai preso nota nella procedura precedente.

    Dovresti vedere un passaggio di prelievo in cui tutte le righe di prelievo per l'articolo *M9200* sono raggruppate e dovresti ricevere un'istruzione per scegliere *7* per ognuno degli articoli *M9200*.

    > [!IMPORTANT]
    > Sul dispositivo mobile, il lavoro di prelievo per le tre righe di lavoro di prelievo è stato aggregato in un unico passaggio di prelievo per l'utente.

1. Confermare il passaggio di prelievo.
1. Passare alla pagina del lavoro per l'ID lavoro e prendere nota che tutte e tre le righe di prelievo per l'articolo *M9200* sono state chiuse contemporaneamente.
1. Tornare al dispositivo mobile e continuare con il prelievo. Dovrebbe essere visualizzata la riga di lavoro 4 per l'articolo *M9201*. Poiché nell'ordine era presente una sola riga di lavoro, non c'è nulla da aggregare.
1. Confermare il passaggio di prelievo.
1. L'ultimo passaggio di prelievo sul dispositivo mobile aggrega le ultime due righe di prelievo dall'ordine di lavoro.
1. Completare il passaggio di prelievo per *9* ciascuno dell'articolo *M9202*.
1. Confermare il passaggio di inserimento e tutte le coppie di prelievo/inserimento aggiuntive per completare il lavoro.

> [!IMPORTANT]
>
> - Le righe di lavoro possono essere raggruppate solo se sono in sequenza.
> - Sono supportate le seguenti funzionalità:
>
>   - Articoli a peso variabile
>
>    Se sul lavoro sono presenti articoli a peso variabile, riceverai un messaggio di errore prima di iniziare il prelievo.
>
>   - Prelievo di pezzi
>   - Righe di lavoro che includono lavori di rifornimento incompiuti
>   - Prelievo eccessivo
>   - Prelievo breve con riallocazione articolo


[!INCLUDE[footer-include](../../includes/footer-banner.md)]