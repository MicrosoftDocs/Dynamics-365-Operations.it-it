---
title: Cluster di stoccaggio
description: I cluster di stoccaggio offrono un modo per prelevare più targhe contemporaneamente e portarle per lo stoccaggio in ubicazioni diverse. Possono essere molto utili per le attività di vendita al dettaglio, dove le targhe in genere non sono pallet completi di inventario.
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: c2b12798a6ef9c2d4aa022e0c270d8191b2cf4e7fc844042ed88c4eb9f5b98a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741910"
---
# <a name="putaway-clusters"></a>Cluster di stoccaggio

[!include [banner](../includes/banner.md)]

I cluster di stoccaggio offrono un modo per prelevare più targhe contemporaneamente e portarle per lo stoccaggio in ubicazioni diverse. Questo processo è spesso denominato *milk run*. I cluster di stoccaggio possono essere molto utili per le attività di vendita al dettaglio, dove le targhe in genere non sono pallet completi di inventario. 

## <a name="turn-on-the-cluster-putaway-feature"></a>Attivare la funzione stoccaggio cluster

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Funzione stoccaggio cluster*

## <a name="setup-for-the-example-scenario"></a>Configurazione per lo scenario di esempio

### <a name="cluster-profiles"></a>Profili cluster

Il profilo del cluster di stoccaggio determina dove andrà un articolo, in base all'ubicazione assegnata all'articolo al momento del ricevimento. Se sono richiesti cluster diversi, è necessario creare cluster di stoccaggio diversi, uno per ciascuna voce di menu del dispositivo mobile.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Profili cluster**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella visualizzazione **Intestazione**, impostare i seguenti valori:

    - **ID profilo del cluster di stoccaggio:** *Stoccaggio cluster*
    - **Nome ID profilo del cluster di stoccaggio:** *Stoccaggio cluster*
    - **Tipo di cluster:** *Stoccaggio*
    - **Numero sequenza:** accetta il valore predefinito.

1. Selezionare **Salva** per rendere disponibili i campi richiesti nella Scheda dettaglio **Generale**.
1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Tempistica assegnazione cluster:** *Al ricevimento*

        Questo campo definisce se il cluster di stoccaggio deve essere assegnato immediatamente quando viene ricevuto l'inventario o se deve essere ordinato in un secondo momento.

    - **Regola di assegnazione cluster:** *Manuale*

        Questo campo indica se l'assegnazione del cluster deve essere determinata automaticamente dal sistema o manualmente dall'utente.

    - **Codice direttiva:** lascia vuoto questo campo.
    - **Individuazione cluster di stoccaggio:** *Ricezione*

        Sono disponibili i valori seguenti:

        - **Ricezione** – L'ubicazione viene individuata immediatamente durante l'entrata.
        - **Chiusura cluster** - L'ubicazione viene individuata alla chiusura del cluster.
        - **Diretto dall'utente** - Viene trovata una posizione quando la targa viene prelevata dal cluster per lo stoccaggio. In questo caso, non viene specificata alcuna ubicazione quando viene creato il lavoro di stoccaggio. Durante lo stoccaggio stesso, l'utente deve scansionare la targa o l'ID di lavoro per avviare la fase di stoccaggio. Il sistema quindi trova di nuovo l'ubicazione di stoccaggio e dice all'utente dove collocare la quantità prelevata.

    - **Cluster di stoccaggio per utente:** *No*

        Questo campo definisce se ogni cluster deve essere univoco per ogni utente quando i cluster vengono assegnati automaticamente. È disponibile solo quando il campo **Regola di assegnazione cluster** è impostato su *Automatico*.

    - **Limitazione di unità:** Lasciare vuoto questo campo.

        Questo campo definisce l'unità che deve essere ricevuta affinché il profilo sia valido. Se è lasciato vuoto, tutte le unità sono valide.

    - **Interruzione unità di lavoro:** *Individuale*

        Questo campo definisce se tutto l'inventario deve essere consolidato (utilizzando l'ID cluster e la targa) su una targa quando un cluster viene chiuso e se deve essere riposto come una singola targa o separatamente sulle targhe che sono state ricevute. Questo campo non è disponibile quando il campo **Individuazione cluster di stoccaggio** è impostato su *Ricezione*.

    - **Il cluster persiste come targa padre:** *No*

        Se questa opzione è impostata su *Sì*, una volta completato il passaggio di inserimento, l'ID cluster diventerà una targa padre e tutti gli elementi sull'ID cluster verranno collegati a quella targa padre.

1. Nella Scheda dettaglio **Ordinamento cluster** è possibile definire i criteri di ordinamento dello stoccaggio. Selezionare **Nuovo** nella barra degli strumenti per aggiungere una riga e quindi impostare i seguenti valori:

    - **Numero sequenza:** accetta il valore predefinito.
    - **Nome campo:** *WMSLocationId*

        Questo campo definisce il campo che questa riga deve utilizzare come criterio di ordinamento.

    - **Ordinamento:** *Crescente*

        Questo campo definisce se l'ordinamento deve essere eseguito in ordine crescente o decrescente.

1. Nella Scheda dettaglio **Modello di lavoro cluster**, selezionare **Nuovo** nella barra degli strumenti per aggiungere una riga e quindi impostare i seguenti valori:

    - **Tipo di ordine di lavoro:** *Ordini fornitore*
    - **Modello di lavoro:** *61 PO Diretto*

1. Nel riquadro azioni selezionare **Salva** e quindi **Modifica**.
1. Nella finestra di dialogo **Stoccaggio cluster**, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una seconda riga alla quey. Quindi aggiornare le righe della query come mostrato nella tabella seguente.

    | Tabella | Tabella derivata | Campo | Criteri |
    |---|---|---|---|
    | Lavoro | Lavoro | Magazzino | *61* |
    | Lavoro | Lavoro | ID lavoro | Lascia vuoto il campo. |

1. Selezionare **OK** per salvare la query e chiudere finestra dialogo.
1. Nel riquadro azioni selezionare **Salva** e chiudere la pagina.

> [!IMPORTANT]
> I campi nel profilo del cluster che appaiono inattivi quando **Genera ID cluster** è impostato su *Sì* non sono disponibili e non verranno presi in considerazione quando viene utilizzata questa funzione.

### <a name="mobile-device-menu-items"></a>Voci di menu del dispositivo mobile

Per questa funzione sono disponibili due nuove voci di menu del dispositivo mobile. La voce di menu **Ricevi e ordina cluster** viene utilizzata per ordinare l'inventario ricevuto in un cluster di stoccaggio al momento della ricezione. La voce di menu **Stoccaggio cluster** viene utilizzata per riporre il cluster dopo che è stato assegnato.

#### <a name="receive-and-sort-cluster"></a>Ricevi e ordina cluster

Creare una nuova voce di menu del dispositivo mobile per la ricezione dell'inventario e l'ordinamento in un cluster. Questa voce di menu creerà il lavoro in entrata dopo la ricezione dell'inventario, il che indica che la voce di menu di ricezione verrà utilizzata per i cluster di stoccaggio.

> [!NOTE]
> La voce di menu **Ricevi e ordina cluster** può essere utilizzata con le seguenti voci di menu di ricezione:
>
> - Ricevimento riga ordine acquisto
> - Ricevimento articolo ordine acquisto
> - Ricezione articoli di carico

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella visualizzazione **Intestazione**, impostare i seguenti valori:

    - **Nome voce di menu:** *Ricevi e ordina cluster*
    - **Titolo:** *Ricevi e ordina cluster*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *No*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Processo di creazione lavoro:** *Ricevimento articolo ordine acquisto*
    - **Genera targa:** *Sì*
    - **Assegna cluster di stoccaggio:** *Sì*

        > [!NOTE]
        > L'opzione **Assegna cluster di stoccaggio** è disponibile solo per un'attività *Processo di creazione lavoro* composta da un unico passaggio in ricezione.

    Accettare i valori predefiniti per i campi rimanenti.

1. Nel riquadro azioni selezionare **Salva**.

#### <a name="cluster-putaway"></a>Stoccaggio cluster

Creare una nuova voce di menu del dispositivo mobile per stoccare il cluster dopo che è stato assegnato.

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella visualizzazione **Intestazione**, impostare i seguenti valori:

    - **Nome voce di menu:** *Stoccaggio cluster*
    - **Titolo:** *Stoccaggio cluster*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *Sì*

1. Nella Scheda dettaglio **Generale**, impostare il campo **Diretto da** su *Stoccaggio cluster*. Accettare i valori predefiniti per i campi rimanenti.
1. Nella Scheda dettaglio **Classi di lavoro** impostare la classe di lavoro valida per questa voce di menu del dispositivo mobile:

    - **ID classe lavoro:** *Acquisto*
    - **Tipo di ordine di lavoro:** *Ordini fornitore*

1. Nel riquadro azioni selezionare **Salva**.

### <a name="mobile-device-menu"></a>Menu del dispositivo mobile

Aggiungere le voci di menu appena create al menu in entrata dell'app per dispositivi mobili.

1. Accedi a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nell'elenco dei menu, selezionare **In entrata**.
1. Nell'elenco **Menu e voci di menu disponibili**, trovare e selezionare la voce di menu **Ricevi e ordina cluster**.
1. Selezionare il pulsante freccia destra per spostare la voce di menu selezionata nell'elenco **Struttura menu**.
1. Utilizzare il pulsante freccia su o freccia giù per spostare la voce di menu nella posizione desiderata nel menu.
1. Nel riquadro azioni selezionare **Salva**.
1. Ripetere i passaggi da 4 a 7 per aggiungere le voci di menu rimanenti:

    - Assegna cluster
    - Stoccaggio cluster

## <a name="example-scenario"></a>Scenario di esempio

Questo scenario simula l'elaborazione del cluster di stoccaggio.

### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:

    - **Conto fornitore:** *1001*
    - **Magazzino:** *61*

1. Selezionare **OK**.

    Viene visualizzata la pagina **Tutti gli ordini fornitore**.

1. Nella pagina **Tutti gli ordini fornitore** nella Scheda dettaglio **Righe ordine fornitore**, utilizzare il pulsante **Aggiungi riga** per aggiungere le seguenti righe:

    - Riga ordine fornitore 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *10*

    - Riga ordine fornitore 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *20*

    - Riga ordine fornitore 3:

        - **Numero articolo:** *M9215*
        - **Quantità:** *30*

1. Nel riquadro azioni selezionare **Salva**.
1. Prendere nota del numero di ordine fornitore.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>Ricevi inventario e stoccalo dal dispositivo mobile

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>Ricevi e ordina l'inventario in un cluster

1. Accedi all'app per dispositivi mobili Gestione magazzino come utente configurato per il magazzino *61*.
1. Nel menu principale, selezionare **In entrata**.
1. Nel menu **In entrata** selezionare **Ricevi e ordina cluster**.
1. Nel campo **Numero ordine fornitore**, immettere il numero dell'ordine fornitore.
1. Selezionare **OK** (il simbolo del segno di spunta).
1. Selezionare il campo **Articolo**, quindi inserire il numero articolo *A0001* e selezionare **OK**.
1. Selezionare il campo **Qtà** inserire *10* utilizzando il tastierino numerico, quindi selezionare il pulsante del segno di spunta.
1. Nella pagina delle attività **Qtà** selezionare **OK** (il pulsante con il segno di spunta) per confermare la quantità inserita.
1. Nella pagina delle attività **Articolo** selezionare **OK** per confermare che l'articolo *A0001* è stato inserito.
1. Selezionare il campo **ID cluster** e inserire un valore per assegnare un ID al cluster che si sta creando.

    L'ID immesso qui verrà utilizzato quando vengono ricevuti i due articoli rimanenti nell'ordine fornitore.

1. Selezionare **OK**.

    Viene visualizzata la pagina delle attività **Numero ordine fornitore** e viene visualizzato un messaggio "Lavoro completato".

    L'articolo *A0001* è stato ricevuto nell'ubicazione *RECV* e assegnato all'ID cluster immesso nel passaggio 10.

1. Ripetere i passaggi da 4 a 11 per ricevere i due articoli rimanenti dall'ordine fornitore e assegnarli all'ID cluster:

    - Quantità *20* per l'articolo *A0002*
    - Quantità *30* per l'articolo *M9215*

#### <a name="close-the-cluster"></a>Chiudi il cluster

Prima di poter stoccare gli articoli nel cluster, è necessario chiudere il cluster.

1. In Supply Chain Management, andare a **Gestione magazzino \> Lavoro \> In uscita \> Cluster di lavoro**.
1. Nella pagina **Cluster di lavoro** nella sezione **Cluster di lavoro** cercare nel campo **ID cluster** per l'ID cluster immesso in precedenza.
1. Se il cluster non viene visualizzato, potrebbe essere già stato chiuso. Per determinare se il cluster è stato chiuso, selezionare la casella di controllo **Mostra lavoro chiuso** e cercare l'ID cluster immesso in precedenza. Eseguire quindi uno dei passaggi seguenti:

    - Se il cluster è stato chiuso, saltare i passaggi rimanenti di questa procedura e passare alla procedura successiva, [Stocca il cluster](#put-the-cluster-away).
    - Se il cluster non è stato chiuso, seguire i passaggi rimanenti di questa procedura per chiudere manualmente il cluster. Quindi passare alla procedura successiva.

1. Nella sezione **Cluster di lavoro** selezionare l'ID cluster immesso in precedenza.
1. Nel riquadro azioni selezionare **Chiudi cluster**.

    Dopo che il cluster è stato chiuso, non viene più visualizzato nella sezione **Cluster di lavoro** (a meno che la casella di controllo **Mostra lavoro chiuso** sia selezionata).

#### <a name="put-the-cluster-away"></a>Stocca cluster

1. Accedi all'app per dispositivi mobili Gestione magazzino come utente configurato per il magazzino *61*.
1. Nel menu principale, selezionare **In entrata**.
1. Nel menu **In entrata** selezionare **Stoccaggio cluster**.
1. Selezionare **ID cluster** e inserire l'ID cluster immesso in precedenza per il cluster chiuso.
1. Selezionare **OK**.

    Viene visualizzata la pagina **Stoccaggio cluster: Prelievo**. Mostra l'ID cluster, la posizione di prelievo, gli articoli (il valore *Multiplo* verrà visualizzato) e la quantità totale nel cluster che deve essere prelevata.

1. Selezionare **OK**.

    Viene visualizzata la pagina **Stoccaggio cluster: Stoccaggio**. Le istruzioni **Stoccaggio** identificano l'ID cluster, l'ubicazione di stoccaggio, gli articoli, la quantità totale e gli ID targa per gli articoli ricevuti nel cluster.

    Sono disponibili le opzioni standard per ignorare o passare questo passaggio.

    ![Pagina Stoccaggio cluster: Stoccaggio.](media/Cluster_putaway-Put.png "Pagina Stoccaggio cluster: Stoccaggio")

1. Selezionare **OK** per confermare lo stoccaggio del cluster.

    Viene ricevuto un messaggio "Cluster completato".

## <a name="notes-and-tips"></a>Note e suggerimenti

Per i casi in cui l'ID cluster diventa la targa padre per un pallet annidato, la posizione di stoccaggio viene fornita automaticamente quando l'ID cluster viene scansionato. Non è necessario scansionare ulteriori targhe, anche se la generazione della targa è impostata su manuale.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]