---
title: Richieste di categorie da parte dei fornitori
description: Questo argomento descrive come i fornitori possono richiedere le categorie di approvvigionamento per il proprio conto. Descrive inoltre il processo di approvazione completato dagli agenti di approvvigionamento.
author: GalynaFedorova
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9874151a5d82cc3441741489065877b78bab7bf5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671212"
---
# <a name="category-requests-from-vendors"></a>Richieste di categorie da parte dei fornitori

[!include [banner](../includes/banner.md)]

Il processo di richiesta di categorie consente ai fornitori di richiedere che nuove categorie di approvvigionamento siano associate al proprio conto. Tali categorie di approvvigionamento possono quindi essere utilizzate dai relativi processi di approvvigionamento. Per ulteriori informazioni, vedere [Panoramica sui cataloghi di approvvigionamento](procurement-catalogs.md).

Le richieste di categorie vengono avviate dai fornitori nell'area di lavoro **Informazioni fornitore**. Vengono quindi inviate alla tua agenzia per la revisione e l'approvazione. Le categorie approvate vengono aggiunte all'elenco delle categorie di approvvigionamento per il conto del fornitore.

## <a name="turn-the-category-requests-from-vendors-feature-on-or-off"></a>Attivare o disattivare la funzionalità Richieste di categoria dai fornitori

A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. Gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Consenti ai fornitori di richiedere categorie di approvvigionamento tramite la collaborazione fornitore nell'area di lavoro* [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Se questa funzionalità è attivata, è comunque possibile aggiungere manualmente le categorie di approvvigionamento ai conti fornitore. Per informazioni, vedere [Approvare i fornitori per categorie specifiche di approvvigionamento](tasks/approve-vendors-specific-procurement-categories.md).

## <a name="vendor-collaboration-requirements"></a>Requisiti di collaborazione fornitore

Prima che un fornitore possa interagire con le richieste di categorie, deve essere impostato per la collaborazione fornitore.

Il fornitore deve avere almeno un utente di collaborazione fornitore. Solo gli utenti fornitori con il ruolo di sicurezza *Amministratore fornitore (esterno)* possono creare e inviare richieste di categoria.

Per ulteriori informazioni, vedere [Impostare e gestire la collaborazione fornitore](set-up-maintain-vendor-collaboration.md).

## <a name="set-up-the-vendor-category-request-workflow"></a>Impostare il flusso di lavoro Richiesta categoria fornitore

Il flusso di lavoro *Richiesta categoria fornitore* deve essere impostato nei flussi di lavoro di approvvigionamento. I fornitori invieranno nuove richieste di categorie che puoi esaminare e approvare. Le categorie di approvvigionamento richieste vengono aggiunte a un conto fornitore dopo l'approvazione di una richiesta di categoria.

L'esempio seguente mostra come impostare un semplice flusso di lavoro *Richiesta categoria fornitore* con un unico approvatore. È necessario rivedere i processi interni per determinare la configurazione del flusso di lavoro appropriata per la propria agenzia.

1. Passare a **Approvvigionamento \> Impostazioni \> Flussi di lavoro di approvvigionamento**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo, seleziona **Flusso di lavoro richiesta categoria fornitore** per aprire l'editor del flusso di lavoro.
1. Accedi all'editor del flusso di lavoro.
1. Nel riquadro azioni, seleziona **Proprietà**.
1. Nella pagina **Proprietà** del flusso di lavoro, nel campo **Istruzioni di invio**, immettere il testo dell'istruzione. Le istruzioni saranno visibili ai fornitori quando inviano una richiesta di categoria.
1. Chiudi la pagina **Proprietà**.
1. Trascina l'elemento del flusso di lavoro **Approva nuova richiesta categoria** sul canvas.
1. Trascina un collegamento dall'elemento del flusso di lavoro **Inizio** all'elemento del flusso di lavoro **Approva nuova richiesta categoria**.
1. Trascina un collegamento dall'elemento del flusso di lavoro **Approva nuova richiesta categoria** all'elemento del flusso di lavoro **Fine**.
1. Tocca due volte (o fai doppio clic) sul elemento del flusso di lavoro **Approva nuova richiesta categoria**.
1. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) l'elemento del flusso di lavoro **Passaggio 1**, quindi seleziona **Proprietà**.
1. Nella pagina **Proprietà** del elemento del flusso di lavoro, nel campo **Argomento elemento di lavoro**, immettere il testo dell'argomento. Questo testo verrà mostrato come il valore di campo **Soggetto** nella pagina **Elementi di lavoro assegnati all'utente**.
1. Nel campo **Istruzioni elemento di lavoro** immettere le istruzioni. Le istruzioni saranno visibili agli approvatori quando selezionano **Flusso di lavoro** nel riquadro azioni di una richiesta di categoria.
1. Nel riquadro sinistro, fare clic su **Assegnazione**.
1. Nella scheda **Tipo di assegnazione**, impostare **Assegna utenti a questo elemento del flusso di lavoro** su *Utente*.
1. Sulla scheda **Utente**, nell'elenco **Utenti disponibili**, selezionare un approvatore. Ad esempio, seleziona un utente nel reparto Approvvigionamento.
1. Seleziona il pulsante freccia destra  (**\>**) per spostare l'approvatore nell'elenco **Utenti selezionati**.
1. Chiudi la pagina **Proprietà**.
1. Seleziona **Salva e chiudi**.
1. Nel campo **Note sulla versione** , immettere note sul flusso di lavoro.
1. Selezionare **OK** per salvare il flusso di lavoro.
1. Se sei pronto per iniziare a testare il flusso di lavoro, seleziona **Attiva la nuova versione**. Altrimenti, seleziona **Non attivare la nuova versione**.
1. Per completare l'impostazione del flusso di lavoro, selezionare **OK**.

> [!TIP]
> Se la tua agenzia non richiede l'approvazione delle richieste di categorie, devi configurare il flusso di lavoro per l'approvazione automatica.

Per ulteriori informazioni su come impostare i flussi di lavoro, vedere [Panoramica del sistema del flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

## <a name="create-and-submit-a-category-request"></a>Creare e inviare una richiesta di categoria

Questa sezione descrive come i fornitori possono utilizzare l'area di lavoro **Informazioni fornitore** per creare, modificare, visualizzare e inviare richieste di categoria.

### <a name="start-a-new-request"></a>Avviare una nuova richiesta

Per avviare una nuova richiesta di categoria, segui questi passaggi.

1. Nell'area di lavoro **Informazioni fornitore**, seleziona il riquadro **Richieste categorie**.
1. Nella pagina **Richieste categorie**, nel riquadro azioni selezionare **Nuova richiesta categoria**.
1. Nella finestra di dialogo **Nuova richiesta categoria**, trova la categoria che desideri applicare spostandoti nell'albero e/o utilizzando il filtro in cima all'elenco. Seleziona la casella di controllo per ciascuna categoria pertinente.

    Notare i punti seguenti:

    - Le categorie attualmente attive nel tuo conto fornitore vengono visualizzate come selezionate e non possono essere rimosse.
    - È possibile richiedere più categorie di approvvigionamento in una singola richiesta di categoria.

1. Selezionare **OK** per creare la bozza di richiesta.

    La nuova bozza di richiesta viene ora visualizzata nella pagina **Richieste categorir**.

1. Apri la nuova bozza di richiesta per esaminarla e modificarla come richiesto.

    - Per visualizzare l'elenco delle categorie attualmente incluse nella richiesta, seleziona la Scheda dettaglio **Categorie richieste**.
    - Per visualizzare le categorie attive, apri il Dettaglio informazioni **Categorie attive** sul lato destro della pagina.
    - Per aggiungere una categoria alla richiesta, selezionare **Aggiungi** sulla barra degli strumenti della Scheda dettagli **Categorie richieste**.
    - Per rimuovere una categoria dalla richiesta, selezionare la categoria nella Scheda dettaglio **Categorie richieste** , quindi selezionare **Rimuovi** sulla barra degli strumenti.
    - Per allegare un documento alla richiesta, selezionare **Allegati** nel riquadro azioni. I documenti allegati saranno disponibili per gli approvatori quando esaminano la richiesta di categoria.
    - Per rimuovere un documento allegato alla richiesta, selezionare **Allegati** nel riquadro azioni. Selezionare il documento da rimuovere, quindi seleziona **Elimina** nel riquadro azioni.

1. Se sei pronto per inviare la richiesta, seleziona **Invia** nel riquadro azioni. Altrimenti, basta chiudere la pagina e saltare i passaggi rimanenti di questa procedura. È quindi possibile tornare alla richiesta in un secondo momento.
1. Leggi le istruzioni per l'invio visualizzate, quindi seleziona **Invia**.
1. Immettere tutte le informazioni aggiuntive necessarie nella casella **Commento**. Per completare la richiesta, selezionare **Invia**.

### <a name="edit-a-draft-or-recalled-request"></a>Modificare una bozza o una richiesta richiamata

Per modificare una bozza o una richiesta di categoria richiamata, segui questi passaggi.

1. Nell'area di lavoro **Informazioni fornitore**, seleziona il riquadro **Richieste categorie**.
1. Seleziona la bozza o la richiesta richiamata per aprirla.
1. Modificare la richiesta come richiesto, quindi chiuderla o inviarla come descritto nella procedura precedente.

### <a name="submit-a-draft-or-recalled-request"></a>Inviare una bozza o una richiesta richiamata

Per inviare una bozza o una richiesta di categoria richiamata, segui questi passaggi.

1. Nell'area di lavoro **Informazioni fornitore**, seleziona il riquadro **Richieste categorie**.
1. Seleziona la bozza o la richiesta richiamata che desideri inviare.
1. Nel riquadro azioni, selezionare **Invia**.
1. Leggi le istruzioni per l'invio visualizzate, quindi seleziona **Invia**.
1. Immettere tutte le informazioni aggiuntive necessarie nella casella **Commento**. Per completare la richiesta, selezionare **Invia**.

    Lo stato della richiesta di categoria viene modificato in uno dei seguenti valori:

    - _Revisione in sospeso_: la richiesta è nel flusso di lavoro.
    - _In attesa di approvazione_ - È richiesta l'approvazione.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>Richiamare una richiesta inviata che non è stata ancora approvata

Per richiamare una richiesta di categoria che è stata inviata ma non è stata ancora approvata, segui questi passaggi.

1. Nell'area di lavoro **Informazioni fornitore**, seleziona il riquadro **Richieste categorie**.
1. Seleziona la richiesta in sospeso che desideri richiamare.
1. Nel riquadro azioni fare clic su **Richiama**.
1. Immettere tutte le informazioni aggiuntive necessarie nella casella **Immettere un commento**. Per completare la richiesta, selezionare **Invia**.

    Lo stato della richiesta di categoria viene modificato in _Annullato_. La richiesta rimarrà in questo stato finché non la elimini o la reinvii.

### <a name="delete-a-draft-or-recalled-request"></a>Eliminare una bozza o una richiesta richiamata

Per eliminare una bozza o una richiesta di categoria richiamata, segui questi passaggi.

1. Nell'area di lavoro **Informazioni fornitore**, seleziona il riquadro **Richieste categorie**.
1. Seleziona la bozza o la richiesta richiamata che desideri eliminare.
1. Nel riquadro azioni selezionare **Elimina**.
1. Selezionare **Sì** per confermare l'eliminazione.

### <a name="view-completed-requests"></a>Visualizzare le richieste completate

Per visualizzare le richieste completate, apri l'area di lavoro **Informazioni fornitore** e seleziona il riquadro **Richieste categorie**. Le richieste di categorie che sono state completate avranno uno dei seguenti stati:

- _Approvato_: la richiesta è stata approvata. Per visualizzare le nuove categorie aggiunte, torna all'area di lavoro **Informazioni fornitore**, apri l'elenco a discesa **Più dettagli** nel riquadro sinistro, quindi seleziona **Categorie**.
- _Rifiutato_: la richiesta è stata rifiutata. È possibile creare una nuova richiesta di categoria in base alle esigenze.

## <a name="review-category-requests"></a>Rivedere le richieste di categoria

Questa sezione spiega come approvare, rifiutare e delegare le richieste di categoria inviate dai fornitori e come visualizzare le richieste completate. Queste azioni del flusso di lavoro riguardano l'intera richiesta di categoria.

### <a name="view-category-requests"></a>Visualizzare le richieste di categoria

Per visualizzare le richieste di categoria, segui questi passaggi.

1. Vai a **Approvvigionamento \> Fornitori \> Richieste collaborazione fornitore \> Richieste categorie**.

    La pagina **Richieste categorie** viene visualizzata. La visualizzazione della pagina predefinita mostra le richieste di categoria con stato *Azione in sospeso*.

1. Per visualizzare tutte le richieste, selezionare *Tutti* nel **Mostra richieste** campo.
1. Apri una richiesta per esaminarla e modificarla come richiesto.

    - Per visualizzare l'elenco delle categorie attualmente incluse nella richiesta, seleziona la Scheda dettaglio **Categorie richieste**.
    - Per visualizzare le categorie attive, apri il Dettaglio informazioni **Categorie attive** sul lato destro della pagina.
    - Se sono stati inviati documenti, il pulsante **Allegati** (graffetta) nel riquadro azioni mostra un conteggio dei documenti allegati. Per visualizzare i documenti allegati, selezionare il pulsante **Allegati**. Quindi selezionare il documento da visualizzare e selezionare **Apri** per vederlo.
    - Per allegare un documento alla richiesta, selezionare **Allegati** nel riquadro azioni. I documenti allegati saranno disponibili per gli approvatori quando esaminano la richiesta di categoria.
    - Per rimuovere un documento allegato alla richiesta, selezionare **Allegati** nel riquadro azioni. Selezionare il documento da rimuovere, quindi seleziona **Elimina** nel riquadro azioni.
    - Per visualizzare lo storico flusso di lavoro seleziona **Flusso di lavoro** nel riquadro azioni. Nelle opzioni del flusso di lavoro selezionare **Altro** poi **Storico flusso di lavoro**. La pagina **Storico flusso di lavoro** viene visualizzata.

### <a name="approve-a-pending-category-request"></a>Approvare una richiesta di categoria in sospeso

Per approvare una richiesta di categoria in sospeso, segui questi passaggi.

1. Vai a **Approvvigionamento \> Fornitori \> Richieste collaborazione fornitore \> Richieste categorie**.
1. Seleziona la richiesta in sospeso da approvare.
1. Rivedi la richiesta di categoria
1. Facoltativo: nella scheda dettaglio **Generale**, nel campo **Codice motivo** selezionare un codice motivo. Quindi, in **Commento motivo** immettere un commento sul codice motivo.
1. Nel riquadro azioni selezionare **Flusso di lavoro**.
1. Nelle opzioni del flusso di lavoro selezionare **Approva**.
1. Immettere tutte le informazioni aggiuntive necessarie nel campo **Commento**. Per completare la richiesta, selezionare **Approva**.

    Lo stato della richiesta di categoria viene modificato in _Approvato_ e le categorie di approvvigionamento vengono aggiunte al conto fornitore.

### <a name="reject-a-pending-category-request"></a>Rifutare una richiesta di categoria in sospeso

Per rifiutare una richiesta di categoria in sospeso, segui questi passaggi.

1. Vai a **Approvvigionamento \> Fornitori \> Richieste collaborazione fornitore \> Richieste categorie**.
1. Seleziona la richiesta in sospeso da rifiutare.
1. Rivedi la richiesta di categoria
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella scheda dettaglio **Generale**, nel campo **Codice motivo** selezionare un codice motivo. Quindi, in **Commento motivo** immettere un commento sul codice motivo.
1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni selezionare **Flusso di lavoro**.
1. Nelle opzioni del flusso di lavoro selezionare **Altro** poi **Rifiuta**.
1. Immettere tutte le informazioni aggiuntive necessarie nel campo **Commento**. Per completare la richiesta, selezionare **Rifiuta**.

    Lo stato della richiesta di categoria viene modificato in _Rifiutato_. A questo punto, il fornitore può creare una nuova richiesta di categoria in base alle esigenze.

### <a name="delegate-a-pending-category-request"></a>Delegare una richiesta di categoria in sospeso

Per delegare una richiesta di categoria in sospeso a un altro utente, attenersi alla seguente procedura.

1. Vai a **Approvvigionamento \> Fornitori \> Richieste collaborazione fornitore \> Richieste categorie**.
1. Seleziona la richiesta in sospeso che desideri approvare.
1. Nel riquadro azioni selezionare **Flusso di lavoro**.
1. Nelle opzioni del flusso di lavoro selezionare **Altro** poi **Delega**.
1. Nel campo **Utente** selezionare l'utente a cui assegnare la richiesta di categoria per la revisione.
1. Immettere tutte le informazioni aggiuntive necessarie nel campo **Commento**.
1. Per completare la delega, selezionare **Delega**. L'utente selezionato può ora esaminare la richiesta di categoria.

### <a name="view-procurement-categories-for-a-vendor"></a>Visualizzare le categorie di approvvigionamento per un fornitore

Per visualizzare Le categorie di approvvigionamento di un fornitore dopo l'approvazione di una richiesta di categoria, segui questi passaggi.

1. Andare ad **Approvvigionamento \> Fornitori \> Tutti i fornitori**.
1. Nella pagina **Tutti i fornitori** selezionare il fornitore per il quale si desidera visualizzare le categorie di approvvigionamento.
1. Nel riquadro azioni, apri la scheda **Generale** e, nel gruppo **Imposta**, seleziona **Categorie**.

    Viene visualizzata la pagina **Categorie**. La Scheda dettaglio **Approvvigionamento** mostra le categorie di approvvigionamento aggiunte tramite la richiesta di categoria.

1. Nella Scheda dettagflio **Approvvigionamento** è possibile apportare modifiche se necessario. Ad esempio, puoi impostare il campo **Stato categoria fornitore** su _Preferito_.
