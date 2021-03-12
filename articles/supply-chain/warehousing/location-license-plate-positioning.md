---
title: Posizionamento targa ubicazione
description: Il posizionamento della targa consente di vedere dove si trova una targa in un'ubicazione multi-pallet, ad esempio un'ubicazione che utilizza scaffalature per pallet a doppia profondità.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6d94d37368b8fc3ff7dbe4c1845acd52bf2a64ee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004679"
---
# <a name="location-license-plate-positioning"></a>Posizionamento targa ubicazione

[!include [banner](../includes/banner.md)]

Il posizionamento della targa consente di vedere dove si trova una targa in un'ubicazione multi-pallet, ad esempio un'ubicazione che utilizza scaffalature per pallet a doppia profondità.

La funzionalità aggiunge un numero progressivo a ciascuna targa che viene inserita in un'ubicazione di stoccaggio. Questo numero di sequenza viene utilizzato per ordinare le targhe nell'ubicazione di stoccaggio. Pertanto, la funzionalità supporta in modo intelligente scenari in cui i clienti utilizzano un sistema di scaffalature a gravità e devono sapere, ai fini del prelievo, quale targa è rivolta verso la parte anteriore.

Questo argomento presenta uno scenario che mostra come impostare e utilizzare la funzionalità.

## <a name="turn-on-the-location-license-plate-positioning-feature"></a>Attivare la funzionalità di posizionamento della targa di ubicazione

Prima di poter utilizzare il posizionamento di ubicazione della targa, tale funzionalità deve essere attivata nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Posizionamento della targa di ubicazione*

## <a name="example-scenario"></a>Scenario di esempio

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare lo scenario utilizzando i valori suggeriti qui, devi utilizzare un sistema in cui sono installati i dati di esempio standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

### <a name="set-up-the-feature-for-this-scenario"></a>Impostare la funzionalità per questo scenario

Completa le seguenti procedure per impostare la funzionalità *Posizionamento della targa di ubicazione* per lo scenario presentato in questo argomento.

#### <a name="location-profiles"></a>Profili ubicazione

La funzionalità deve essere attivata nel profilo di ubicazione per ogni ubicazione in cui verrà utilizzata.

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Nell'elenco dei profili di ubicazione nel riquadro sinistro, seleziona **BULK-06**.
1. Nella Scheda dettaglio **Generale**, due nuove opzioni sono state aggiunte dalla funzionaità. Imposta i valori seguenti:

    - **Abilita posizione targa:** *Sì*

        Quando questa opzione è impostata su *Sì*, la posizione della targa verrà mantenuta per le targhe nell'ubicazione.

    - **Visualizza posizione targa dispositivo mobile:** *Sì*

        Quando questa opzione è impostata su *Sì*, la posizione della targa verrà mostrata agli utenti dei dispositivi mobili durante la regolazione e il conteggio. È possibile modificare l'impostazione di questa opzione solo quando la funzionalità è attivata.

1. Selezionare **Salva**.

#### <a name="location-directives"></a>Direttive ubicazione

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, verifica che il campo **Tipo di ordine di lavoro** sia impostato su *Ordini cliente*.
1. Nell'elenco delle direttive di ubicazione, seleziona **61 Prelievo ordine cliente**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Righe**, seleziona la riga che ha un valore **Numero progressivo** pari a *2*.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona la riga che ha un calore **Nome** di *Preleva per meno di pallet* (dovrebbe essere l'unica riga) e modificane il valore **Numero progressivo** su *2*.
1. Seleziona **Nuovo** sopra la griglia per aggiungere una riga per una nuova azione di direttiva di ubicazione.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero progressivo:** *1*
    - **Nome:** *Posizione di prelievo 1*

1. Con la nuova riga ancora selezionata, seleziona **Modifica query** sopra la griglia.
1. Nell'editor di query, seleziona la scheda **Join**.
1. Espandi il join della tabella **Ubicazioni** per mostrare il join sulla tabella **Dimensioni inventariali**.
1. Espandi il join della tabella **Dimensioni inventariali** per mostrare il join sulla tabella **Scorte disponibili**.
1. Seleziona **Dimensioni inventariali**, quindi seleziona **Aggiungi join tabella**.
1. Nell'elenco delle tabelle che appare, nella colonna **Relazione**, seleziona **Targa**. Quindi seleziona **Seleziona** per aggiungere **Targa** al join della tabella **Dimensioni inventariali**.
1. Mentre **Targa** è ancora selezionato, seleziona **Aggiungi join tabella**.
1. Nell'elenco delle tabelle che appare, nella colonna **Relazione**, seleziona **Posizionamento targa ubicazione (targa)**. Quindi seleziona **Seleziona** per aggiungere **Posizionamento targa ubicazione** al join della tabella **Dimensioni inventariali**.

    ![Join di tabella](media/LpTableJoin.png "Join di tabella")

1. Seleziona **OK** per confermare le tabelle con join aggiornate e chiudere l'editor delle query.
1. Nella scheda dettaglio **Azioni direttiva di ubicazione**, seleziona **Modifica query** nuovamente per riaprire l'editor di query.
1. Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Posizionamento della targa di ubicazione*
    - **Tabella derivata:** *Posizionamento della targa di ubicazione*
    - **Campo:** *Posizione targa*
    - **Criteri:** *1*

    ![Nuovo intervallo](media/LpPositionCriteria.png "Nuovo intervallo")

1. Seleziona **OK** per confermare le modifiche e chiudere l'editor di query.

### <a name="set-up-sample-data-for-this-scenario"></a>Impostare i dati di esempio per questo scenario

Per questo scenario, l'utente deve accedere all'app per dispositivi mobili di magazzino utilizzando un lavoratore impostato per il magazzino *61* per eseguire lavori. L'utente deve anche completare le transazioni.

Perché la funzionalità *Posizionamento targa ubicazione* aggiunge un nuovo identificatore per le posizioni della targa in un'ubicazione, è necessario prima creare alcuni dati per supportare lo scenario.

#### <a name="spot-count-the-first-location"></a>Conteggio ciclo a campione della prima ubicazione

1. Apri l'app per dispositivi mobili magazzino e accedi al magazzino *61*.
1. Vai a **Inventario \> Conteggio ciclo a campione**.
1. Nella pagina **Conteggio ciclo a campione**, imposta il campo **Posizione** su *01A01R1S1B*.
1. Selezionare **OK**.

    La pagina mostra l'ubicazione che hai inserito. Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"

1. Seleziona **Aggiorna** per aggiungere un conteggio nell'ubicazione.
1. Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Articolo**, quindi immetti il valore *A0001*.
1. Selezionare **OK**.
1. Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Targa**, quindi immetti il valore *LP1001* (o qualsiasi altro numero di targa a tua scelta).

    La pagina **Conteggio ciclo: aggiungi nuova targa o articolo** mostra **Posizione targa 1**.

1. Selezionare **OK**.

    È ora necessario specificare la quantità dell'articolo conteggiato sulla targa.

1. Imposta il campo **Qtà** su *10*.
1. Selezionare **OK**.

    La pagina mostra l'ubicazione che hai inserito. Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"

1. Seleziona **Aggiorna** per aggiungere un altro conteggio nell'ubicazione.
1. Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Articolo**, quindi immetti il valore *A0002*.
1. Selezionare **OK**.
1. Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Targa**, quindi immetti il valore *LP1002* (o qualsiasi altro numero di targa a tua scelta, a condizione che differisca dal numero di targa specificato in precedenza).
1. Modifica la posizione della targa impostando il campo **Posizione targa** su *2*.
1. Selezionare **OK**.
1. Specifica la quantità dell'articolo conteggiato sulla targa impostando il campo **Qtà** su *10*.
1. Selezionare **OK**.

    La pagina mostra l'ubicazione che hai inserito. Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"

1. Selezionare **OK**.

Il lavoro è ora completato.

#### <a name="spot-count-the-second-location"></a>Conteggio ciclo a campione della seconda ubicazione

1. Nella pagina **Conteggio ciclo a campione**, imposta il campo **Posizione** su *01A01R1S2B*.
1. Selezionare **OK**.

    La pagina mostra l'ubicazione che hai inserito. Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"

1. Seleziona **Aggiorna** per aggiungere un conteggio nell'ubicazione.
1. Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Articolo**, quindi immetti il valore *A0002*.
1. Selezionare **OK**.
1. Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Targa**, quindi immetti il valore *LP1003* (o qualsiasi altro numero di targa a tua scelta, a condizione che differisca da entrambi i numeri di targa specificati nella procedura precedente).

    La pagina **Conteggio ciclo: aggiungi nuova targa o articolo** mostra **Posizione targa 1**.

1. Selezionare **OK**.
1. Specifica la quantità dell'articolo conteggiato sulla targa impostando il campo **Qtà** su *10*.
1. Selezionare **OK**.

    La pagina mostra l'ubicazione che hai inserito. Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"

1. Selezionare **OK**.

Il lavoro è ora completato.

#### <a name="work-details"></a>Dettagli lavoro

> [!NOTE]
> I conteggi ciclo dell'app per dispositivi mobili creano un lavoro di conteggio ciclo in Microsoft Dynamics 365. Il lavoro richiede che i conteggi vengano accettati prima che vengano registrati nell'inventario.

1. Accedere a Dynamics 365 Supply Chain Management.
1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Nella scheda **Panoramica**, cerca le righe che hanno i seguenti valori:

    - **Tipo di ordine di lavoro:** *Conteggio ciclo*
    - **Magazzino:** *61*
    - **Stato del lavoro:** *Revisione in sospeso*

    Due ID lavoro dovrebbero essere stati creati per queste righe. I conteggi per entrambi questi ID di lavoro devono essere accettati.

1. Nella griglia, seleziona il primo ID di lavoro per il tipo di ordine di lavoro *Conteggio ciclo*.
1. Nella scheda **Lavoro** del riquadro azioni, nel gruppo **Lavoro**, seleziona **Conteggio ciclo**.

    Vengono visualizzate due righe, una per ogni articolo e targa. I valori nei campi **Quantità conteggiata**, **Ubicazione**, **Targa** e **Articolo** devono corrispondere alle voci di conteggio create sul dispositivo mobile. Se uno di questi campi non è visibile, seleziona **Visualizza dimensioni** nel riquadro azioni per aggiungerli alla griglia.

1. Seleziona entrambe le righe.
1. Nel riquadro azioni, seleziona **Accetta conteggio**.
1. Si riceve un messaggio "Registrazione - Giornale di registrazione". Seleziona **Dettagli messaggio** per visualizzare il numero di giornale di registrazione pubblicato.
1. Chiudi i dettagli del messaggio.
1. Aggiorna la pagina **Lavoro**.

    Il primo ID lavoro è stato chiuso e non viene più visualizzato.

    > [!TIP]
    > Per visualizzare il lavoro chiuso, seleziona la casella di controllo **Mostra chiuso** sopra la griglia.

    Ora accetterai il lavoro per la targa nell'ubicazione *01A01R1S2B*.

1. Nella scheda **Panoramica**, seleziona il secondo ID di lavoro per il tipo di ordine di lavoro *Conteggio ciclo*.
1. Nella scheda **Lavoro** del riquadro azioni, nel gruppo **Lavoro**, seleziona **Conteggio ciclo**.

    Viene visualizzata una riga, per l'articolo e la targa. I valori nei campi **Quantità conteggiata**, **Ubicazione**, **Targa** e **Articolo** devono corrispondere alle voci di conteggio create sul dispositivo mobile.

1. Seleziona la riga.
1. Nel riquadro azioni, seleziona **Accetta conteggio**.
1. Si riceve un messaggio "Registrazione - Giornale di registrazione". Seleziona **Dettagli messaggio** per visualizzare il numero di giornale di registrazione pubblicato.
1. Chiudi i dettagli del messaggio.
1. Aggiorna la pagina **Lavoro**.

    Il secondo ID lavoro è stato chiuso e non viene più visualizzato.

    > [!TIP]
    > Per visualizzare il lavoro chiuso, seleziona la casella di controllo **Mostra chiuso** sopra la griglia.

#### <a name="on-hand-by-location"></a>Disponibili per ubicazione

1. Vai a **Gestione magazzino \> Richieste di informazioni e report \> Disponibili per ubicazione**.
1. Imposta i valori seguenti:

    - **Sito:** *6*
    - **Magazzino:** *61*
    - **Aggiorna informazioni in ubicazioni:** *Sì*

1. Notare che l'ubicazione *01A01R1S1B* ha due targhe:

    - **A0001**, dove il campo **Posizione targa** è impostato su *1*
    - **A0002**, dove il campo **Posizione targa** è impostato su *2*

1. Notare che l'ubicazione *01A01R1S2B* ha una targa:

    - **A0002**, dove il campo **Posizione targa** è impostato su *1*

### <a name="sales-order-scenario"></a>Scenario dell'ordine cliente

Ora che la funzionalità *Posizionamento targa di ubicazione* è stata impostata e le scorte sono in transito, è necessario creare un ordine cliente per generare il lavoro di prelievo che indirizzerà l'operatore di magazzino a prelevare l'articolo *A0002* dall'ubicazione di inventario in cui si trova l'ID pallet *1*.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-004*
    - **Magazzino:** *61*

1. Selezionare **OK**.
1. Una nuova riga viene aggiunta alla griglia nella Scheda dettaglio **Righe ordine cliente**. Nella nuova riga, imposta i seguenti valori:

    - **Numero articolo:** *A0002*
    - **Quantità:** *1*

1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare le scorte per la riga dell'ordine.
1. Chiudi la pagina **Prenotazione**.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.

    Ricevi un messaggio informativi che indica l'ID ondata e l'ID spedizione creati per l'ordine cliente.

1. Nella scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino** sopra la griglia, seleziona **Dettagli lavoro**.
1. La pagina **Lavoro** viene visualizzata e mostra il lavoro creato per la riga delle vendite. Prendi nota dell'ID lavoro mostrato.

### <a name="sales-picking-scenario"></a>Scenario di raccolta delle vendite

1. Apri l'app per dispositivi mobili e accedi al magazzino *61*.
1. Vai a **In uscita \> Prelievo vendite**.
1. Nella pagina **Esegui scansione ID lavoro/ID targa**, seleziona il campo **ID**, quindi immetti l'ID lavoro dalla riga di vendita.
1. Si noti che il lavoro di prelievo indirizza l'utente a prelevare l'articolo *A0002* dall'ubicazione *01A01R1S2B*. Ricevi questa istruzione perché l'articolo *A0002* è su una targa che è in posizione *1* in quella ubicazione.

    ![Ubicazione posizione 1](media/LocationLicensePlatePositioning.png "Ubicazione posizione 1")

1. Immetti l'ID targa creato per l'ubicazione, quindi segui le istruzioni per selezionare l'ordine cliente.
