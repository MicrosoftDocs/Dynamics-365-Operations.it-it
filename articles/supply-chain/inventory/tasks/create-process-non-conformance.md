---
title: Creare ed elaborare non conformità
description: In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 933efff1be545816504ab31f7a3135bf79996d7b8a50dac9fcc5b994e57a8965
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747963"
---
# <a name="create-and-process-nonconformances"></a>Creare ed elaborare non conformità

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente. In genere, la gestione della non conformità viene eseguita da un addetto alla qualità. Come prerequisito, è necessario disporre di un ordine di controllo qualità. (Per informazioni su come creare un ordine di controllo qualità, vedere [Verificare la qualità delle merci](inspect-quality-goods.md).)

Prima che un utente possa elaborare l'approvazione di una non conformità, è necessario che gli venga assegnato un lavoratore nel campo **Persona** della pagina **Utenti**. Inoltre, prima che l'utente possa utilizzare le note del documento, l'opzione **Attiva gestione documenti** deve essere impostata su *Sì* nelle relative opzioni utente.

## <a name="create-a-nonconformance"></a>Creare una non conformità

Per creare una non conformità, eseguire i passaggi indicati di seguito:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea non conformità**, nel campo **Tipo di problema** selezionare il tipo di problema riscontrato durante il processo di ispezione.
1. Selezionare **OK**.

## <a name="approve-or-reject-a-nonconformance"></a>Approvare o respingere una non conformità

Per approvare o respingere una non conformità, effettuare le operazioni seguenti:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.

    > [!NOTE]
    > È possibile aggiungere una correzione solo alle non conformità approvate.

1. Nel riquadro azioni selezionare **Funzioni \> Approva non conformità** per approvare la non conformità o **Funzioni \> Respingi non conformità** per respingerla. È possibile associare non conformità approvate a [operazioni correlate](../quality-operations.md). In questo modo, è possibile registrare il lavoro svolto come parte della gestione delle non conformità e dell'elaborazione della gestione delle correzioni.
1. Ti viene chiesto di confermare la selezione. Selezionare **Sì** per continuare.

## <a name="add-operations-and-other-details-to-nonconformances"></a>Aggiungere operazioni e altri dettagli alle non conformità

Dopo aver creato una non conformità, è possibile iniziare ad aggiungere operazioni correlate e specificare ulteriori informazioni su tali operazioni. È possibile aggiungere operazioni correlate solo alle non conformità approvate.

Oltre alle informazioni di base, è possibile aggiungere i seguenti dettagli a un'operazione:

- **Articoli** - È possibile creare un elenco di articoli che vengono consumati per eseguire la correzione. Ad esempio, gli articoli potrebbero essere prodotti necessari per riparare apparecchiature o ingredienti necessari per la rilavorazione di un prodotto finito.
- **Spese gestione qualità** - È possibile creare un elenco di spese sostenute o fatturate a fonti esterne.
- **Foglio presenze** - È possibile creare un registro del tempo che ogni lavoratore dedica all'operazione.

Le impostazioni rimanenti sono facoltative. Il costo di ogni articolo, le spese di gestione qualità e il foglio presenze vengono sommati e visualizzati nell'operazione. Non puoi modificare direttamente il campo **Costo** dell'operazione.

### <a name="create-an-operation-for-a-nonconformance"></a>Creare un'operazione per una non conformità

Per creare un'operazione per una non conformità, eseguire i passaggi indicati di seguito:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.

    > [!NOTE]
    > È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.

1. Nel riquadro azioni, seleziona **Operazioni correlate**.
1. Nella pagina **Operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Operazione** - Selezionare il codice dell'operazione che verrà eseguita per la non conformità.
    - **Motivo** - Immettere una descrizione dettagliata che spieghi perché l'operazione è richiesta.
    - **Ordine cliente** - Se il codice operazione selezionato è correlato al tipo di ordine cliente, selezionare l'ordine cliente a cui si sta collegando l'operazione.
    - **Ordine fornitore** - Se il codice operazione selezionato è correlato al tipo di ordine fornitore, selezionare l'ordine fornitore a cui si sta collegando l'operazione.

1. Chiudere le pagine.

### <a name="add-items-to-an-operation"></a>Aggiungere articoli a un'operazione

Per aggiungere articoli a un'operazione, segui questi passaggi.

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.

    > [!NOTE]
    > È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.

1. Nel riquadro azioni, seleziona **Operazioni correlate**.
1. Nella pagina **Operazioni correlate** selezionare l'operazione a cui si desidera aggiungere articoli.
1. Nel riquadro azioni seleziona **Articoli**.
1. Nella pagina **Operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Numero articolo** - Seleziona il prodotto che verrà consumato come parte dell'operazione selezionata.
    - **Quantità** - Immettere il numero di articoli che verranno consumati.

    > [!NOTE]
    > È possibile visualizzare il costo dell'articolo nel campo **Costo** della scheda **Generale**. Il costo che vi viene mostrato deriva dal costo che è impostato nella pagina **Prodotto rilasciato**. Il costo non può essere aggiornato direttamente nella pagina **Elementi operazioni correlate**. Il costo di tutti gli articoli aggiunti alla pagina **Elementi operazioni correlate** viene automaticamente aggiunto al campo **Costo** nella pagina **Operazioni correlate**.

1. Ripeti il passaggio precedente per ogni articolo aggiuntivo che devi aggiungere.
1. Chiudere le pagine.

### <a name="add-quality-charges-to-an-operation"></a>Aggiungere spese di gestione qualità a un'operazione

Per aggiungere spese di gestione qualità a un'operazione, segui questi passaggi.

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.

    > [!NOTE]
    > È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.

1. Nel riquadro azioni, seleziona **Operazioni correlate**.
1. Nella pagina **Operazioni correlate** selezionare l'operazione a cui si desidera aggiungere le spese di gestione qualità.
1. Nel riquadro azioni, seleziona **Spese gestione qualità**.
1. Nella pagina **Spese operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Codice spese** - Seleziona le spese di gestione qualità che desideri aggiungere.
    - **Descrizione** - Immettere una descrizione dettagliata delle spese.
    - **Valore spese** – Immettere l'importo delle spese.

1. Ripeti il passaggio precedente per ogni spese aggiuntiva che devi aggiungere.
1. Chiudere le pagine.

> [!NOTE]
> L'importo nel campo **Valore spese** viene automaticamente sommato per tutti le spese di gestione qualità e aggiunto a qualsiasi altro importo nel campo **Costo** della pagina **Operazioni correlate**.

### <a name="create-a-timesheet-on-an-operation"></a>Creare un foglio presenze su un'operazione

Per aggiungere un foglio presenze a un'operazione, segui questi passaggi.

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.

    > [!NOTE]
    > È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.

1. Nel riquadro azioni, seleziona **Operazioni correlate**.
1. Nella pagina **Operazioni correlate** selezionare l'operazione a cui si desidera aggiungere un foglio presenze.
1. Nel riquadro azioni selezionare **Foglio presenze**.
1. Nella pagina **Fogli presenze operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Data** - Specificare la data in cui è stato svolto il lavoro. Per impostazione predefinita, il campo è impostato sulla corrente.
    - **Lavoratore** – Selezionare il lavoratore che ha svolto il lavoro. Per impostazione predefinita, questo campo è impostato sul lavoratore assegnato all'utente corrente.
    - **Ore operazione** - Immettere il numero di ore lavorate nell'operazione selezionata.
    - **Fatturato** - Selezionare questa casella di controllo se il tempo è stato addebitato a un cliente o fornitore su una fattura.

    > [!NOTE]
    > Puoi visualizzare il costo nel campo **Costo** della scheda **Generale**. Il costo viene calcolato utilizzando la tariffa definita nella pagina **Parametri di Gestione articoli**.

1. Ripeti il passaggio precedente per ogni foglio presenze aggiuntiva che devi aggiungere.
1. Chiudere le pagine.

> [!NOTE]
> L'importo nel campo **Costo** viene automaticamente sommato per tutte le righe del foglio presenze e aggiunto a qualsiasi altro importo nel campo **Costo** della pagina **Operazioni correlate**.

## <a name="add-a-correction-to-a-nonconformance"></a>Aggiungere una correzione a una non conformità

Per aggiungere una correzione a una non conformità, effettuare le operazioni seguenti.

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.

    > [!NOTE]
    > È possibile aggiungere una correzione solo alle non conformità approvate.

1. Nel riquadro azioni, seleziona **Correzioni**.
1. Nella pagina **Correzioni**, nel riquadro azioni seleziona **Nuovo** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Diagnostica** - Seleziona il tipo di diagnostica che identifica il tipo di correzione che stai creando.
    - **Lavoratore** – Seleziona la persona responsabile della correzione.
    - **Priorità di correzione** - Selezionare un'opzione per indicare come assegnare la priorità alla correzione (*Bassa*, *Normale* o *Alta*).
    - **Data richiesta** - Immettere la data in cui è stata richiesta l'azione correttiva.
    - **Data pianificata** - Immettere la data in cui si prevede di completare la correzione.
    - **Soluzione a breve termine** - Selezionare questa casella di controllo se l'azione correttiva corregge la non conformità solo per un breve periodo.

1. Chiudere le pagine.

## <a name="mark-a-correction-as-completed"></a>Contrassegnare una correzione come completata

Per contrassegnare la correzione a una non conformità come completata, effettuare le operazioni seguenti.

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.

    > [!NOTE]
    > È possibile aggiungere una correzione solo alle non conformità approvate.

1. Nel riquadro azioni, seleziona **Correzioni**.
1. Nella pagina **Correzioni**, nella griglia selezionare la correzione che si desidera contrassegnare come completata.
1. Nel riquadro azioni fare clic su **Contrassegna come completata**.
1. Ti viene chiesto di confermare la selezione. Selezionare **OK** per continuare. Il campo **Data e ora di completamento** è impostato sulla data e l'ora correnti e la casella di controllo **Completato** è selezionata.
1. Chiudere la pagina.

## <a name="reopen-a-completed-correction"></a>Riaprire una correzione completata

Per riaprire una correzione completata, effettuare le operazioni seguenti.

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.
1. Nell'elenco selezionare la non conformità che si desidera aggiornare.
1. Nel riquadro azioni, seleziona **Correzioni**.
1. Nella pagina **Correzioni**, nella griglia selezionare la correzione che si desidera riaprire.
1. Nel riquadro azioni fare clic su **Riapri**.
1. Ti viene chiesto di confermare la selezione. Selezionare **OK** per continuare. Il valore viene cancellato dal campo **Data e ora di completamento** e la casella di controllo **Completato** viene deselezionata.
1. Chiudere la pagina.

È ora possibile apportare ulteriori modifiche o aggiornamenti alla correzione. Quando hai finito, puoi contrassegnare di nuovo la correzione come completata.

## <a name="close-a-nonconformance"></a>Chiudere una non conformità

Per chiudere una non conformità, eseguire i passaggi indicati di seguito:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.
1. Seleziona un ordine di controllo qualità nella griglia.
1. Nel riquadro azioni seleziona **Richieste di informazioni \> Non conformità**.
1. Nella pagina **Non conformità**, selezionare la non conformità di destinazione nella griglia.
1. Nel riquadro azioni seleziona **Funzioni \> Chiudi non conformità**.
1. Ti viene chiesto di confermare la selezione. Selezionare **Sì** per continuare.
1. Chiudere le pagine.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica gestione qualità](../quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](../enable-quality-management.md)
- [Lavoratori responsabili dell'approvazione delle non conformità](../quality-responsible-workers.md)
- [Aree di quarantena per non conformità](../quality-quarantine-zones.md)
- [Tipi di diagnostica per non conformità](../quality-diagnostic-types.md)
- [Spese di gestione qualità per non conformità](../quality-charges.md)
- [Operazioni per non conformità](../quality-operations.md)
- [Gestione qualità per i processi di magazzino](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
