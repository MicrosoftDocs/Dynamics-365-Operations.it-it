---
title: Elaborare, rivedere e registrare gli sconti
description: In questo argomento viene descritto come elaborare le transazioni di gestione degli sconti, calcolare gli sconti, rivedere le transazioni generate, registrare le transazioni e rivedere le registrazioni.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 524aec8025378391057275f77e31191f88e4a98b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690276"
---
# <a name="process-review-and-post-rebates"></a>Elaborare, rivedere e registrare gli sconti

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come elaborare le transazioni di gestione degli sconti, calcolare gli sconti, rivedere le transazioni generate, registrare le transazioni e rivedere le registrazioni.

## <a name="change-the-status-of-a-deal"></a>Modificare lo stato di una transazione

Puoi assegnare uno stato a ciascuna transazione per tenerne traccia. Lo stato ha solo scopo informativo.

1. Seleziona una transazione (ad esempio, nella pagina [**Tutte le transazioni di gestione degli sconti**](rebate-management-deals.md)).
1. Nel riquadro azioni, nella scheda **Transazioni di gestione degli sconti**, nel gruppo **Gestisci** seleziona **Cambia stato**.
1. Nella finestra di dialogo **Cambia stato** imposta il campo **Stato sconto** su un nuovo stato.
1. Selezionare **OK**.

## <a name="calculate-fifo-purchase-prices"></a>Calcolare i prezzi di acquisto FIFO

L'attività periodica **Calcola il prezzo di acquisto FIFO** deve essere eseguita per calcolare gli sconti per [transazioni](rebate-management-deals.md) dove il campo **Base prezzo** è impostato su *FIFO*. Il sistema utilizzerà la regola FIFO (first in, first out) per calcolare il valore delle scorte vendute. Questo valore verrà quindi utilizzato per calcolare gli sconti del fornitore.

Vai a **Gestione degli sconti \> Attività periodiche \> Calcola il prezzo di acquisto FIFO**. Nella finestra di dialogo che appare, seleziona **OK** per eseguire il calcolo.

## <a name="create-source-transactions"></a>Creare transazioni di origine

È possibile creare gli ordini cliente o gli ordini fornitore con transazioni di origine prima o dopo aver creato un contratto di gestione sconti applicabile.

Puoi impostare ogni riga della transazione in modo che crei automaticamente un accantonamento di sconto registrando la consegna o la fattura per un ordine cliente o un ordine fornitore. Imposta il campo **Tipo di transazione** per la riga della transazione *Consegna* o *Fattura*, e imposta l'opzione **Elabora alla registrazione** su *Sì*. Se il campo **Tipo di transazione** è impostato su *Ordine*, l'elaborazione al momento della registrazione è disabilitata. Per le transazioni di origine create dopo l'attivazione di una transazione, è comunque possibile elaborare l'accantonamento come descritto nella sezione [Elaborare le transazioni della gestione degli sconti](#process-deals) più avanti in questo argomento.

### <a name="enable-price-details"></a>Abilita dettagli prezzo

Prima di poter creare transazioni di origine, è necessario abilitare l'opzione **Abilita dettagli prezzo** per gli effetti attivi del conto.

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
1. Nella scheda **Prezzi**, nella Scheda dettaglio **Dettagli prezzo**, imposta l'opzione **Abilita dettagli prezzo** su *Sì*.

### <a name="create-a-source-transaction"></a>Creare una transazione di origine

Per creare una transazione di origine completa i passaggi seguenti.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo**.

    Per riprodurre la modalità in cui saranno generate le richieste di sconto, devi creare un ordine cliente, in cui il prodotto e la quantità qualificheranno il cliente in questione per uno sconto.

1. Nel campo **Conto cliente** inserisci o seleziona un cliente che si qualificherà per una transazione di sconto.
1. Seleziona **OK** per creare l'ordine cliente.
1. Nella Scheda dettaglio **Righe ordine cliente**, aggiungi una riga e imposta i seguenti campi:

    - **Numero articolo** – Specifica un articolo che si qualifica per uno sconto.
    - **Quantità** – Specifica una quantità che si qualifica per una transazione di sconto che include una riga in cui il campo **Base** è impostato su *Quantità*.
    - **Prezzo unitario** – Specifica un prezzo che si qualifica per una transazione di sconto che include una riga in cui il campo **Base** è impostato su *Valore*.
    - **Sito** – Seleziona un sito in cui il prodotto è disponibile e che si qualifica per una transazione di sconto.
    - **Magazzino** – Seleziona un magazzino in cui il prodotto è disponibile e che si qualifica per una transazione di sconto.

1. Nella scheda dettaglio **Righe ordine cliente**, nella barra degli strumenti seleziona **Riga ordine cliente \> Dettagli prezzo**. Questo comando è disponibile solo se hai abilitato i dettagli prezzo come descritto nella sezione precedente.
1. Nella pagina **Dettagli prezzo**, seleziona la scheda dettaglio **Gestione sconti**. In questa scheda sono elencate tutte le transazioni di gestione sconti che si applicano alla riga ordine corrente e viene visualizzato l'importo stimato dello sconto nella valuta dell'ordine. Nota che gli importi sono solo stime delle attestazioni di sconto future. Gli importi effettivi dello sconto potrebbero differire. Ecco alcuni dei fattori che potrebbero influenzare gli importi effettivi:

    - Il volume totale delle vendite che il cliente ha raggiunto in base a un accordo con sconto periodico.
    - Se il cliente ha restituito tutte le quantità o le quantità parziali.
    - Se l'ordine cliente applicabile ha raggiunto il tipo di transazione (*Ordine, consegna*, o *Fattura*) definito per la transazione di gestione sconti.
    - Il valore **Output** della transazione. Verrà mostrato un importo di sconto vuoto per le transazioni in cui il campo **Output** è impostato su *Articolo*.

1. Nella scheda dettaglio **Dettaglio** nota che la sezione **Stima margine** include i seguenti campi. Questi campi vengono aggiunti da Gestione sconti. Tutti mostrano valori per unità (mentre i campi della scheda dettaglio **Gestione sconti** mostra i valori totali per la riga).

    - **Importo sconti di gestione sconti** (solo ordini cliente)
    - **Importo royalty di gestione sconti** (solo ordini cliente)
    - **Importo sconti fornitore di gestione sconti** (ordini cliente e ordini fornitore)

1. Chiudi la pagina **Dettagli prezzo**.
1. Se l'ordine cliente non dovesse essere idoneo per gli sconti appena visualizzati, segui questi passaggi per escludere gli sconti. (Tuttavia, di solito non si escludono gli sconti.)

    1. Nella Scheda dettaglio **Righe ordine cliente**, selezionare la riga pertinente.
    1. Nella scheda dettaglio **Dettagli riga** nella scheda **Prezzo e sconto** imposta l'opzione **Escludi da gestione sconti** su *Sì*. Questa opzione non si applica agli ordini fornitore. Inoltre, solo gli sconti cliente sono esclusi quando questa opzione è impostata su *Sì*. Si applicano ancora gli sconti royalty cliente e gli sconti fornitori.

1. Nel riquadro azioni, nella scheda **Preleva e imballa** nel gruppo **Genera** seleziona **Registra documento di trasporto**.
1. Nella Scheda dettaglio **Parametri**, nel campo **Quantità**, selezionare *Tutto*.
1. Selezionare **OK**.
1. Se viene richiesto di confermare l'operazione seleziona **OK**.
1. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
1. Nella Scheda dettaglio **Parametri**, nel campo **Quantità**, seleziona *Tutto* o *Documento di trasporto*.
1. Selezionare **OK**.
1. Se viene richiesto di confermare l'operazione seleziona **OK**.

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>Elaborare le transazioni della gestione degli sconti

Quando si elabora una transazione, il sistema calcola tutti gli sconti e le royalty rilevanti che sono impostati. Solo le transazioni selezionate con periodi di calcolo pronti per essere calcolati e con stato *Attivo* saranno considerate. Al termine dell'elaborazione, il sistema genera una serie di transazioni che è possibile esaminare e quindi registrare.

> [!NOTE]
> In tutti i casi, gli sconti vengono elaborati al livello specificato dall'impostazione **Riconcilia per** di ogni transazione (*Transazione* o *Riga*). Puoi eseguire calcoli su una sola riga solo per le transazioni in cui il campo **Riconcilia per** è impostato su *Riga*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Elaborare tutte le righe per una o più transazioni

1. Apri l'appropriata [pagina elenco delle transazioni di sconto](rebate-management-deals.md) per il tipo di transazione con cui desideri lavorare.
1. Seleziona la riga per ogni transazione che desideri elaborare (o apri la transazione che desideri elaborare).
1. Nel riquadro azioni, nella scheda **Transazioni di gestione degli sconti** nel gruppo **Genera** seleziona uno dei seguenti comandi:

    - **Elabora \> Accantonamento** - Accantonamento di una serie di ratei per ogni transazione di sconto pertinente che non vengono registrati. Questa voce di menu non è disponibile per le transazioni in cui il campo **Output sconto** è impostato su *Articolo*.
    - **Elabora \> Gestione degli sconti** - Elabora una serie di transazioni che forniscono il valore dello sconto per ogni transazione.
    - **Elabora \> Annulla** – Per ogni transazione di origine per la transazione di sconto e il periodo specificato, elabora lo scostamento tra gli importi registrati per un accantonamento e per la gestione degli sconti. Questa voce di menu non è disponibile per le transazioni in cui il campo **Output sconto** è impostato su *Articolo*.

1. Nella finestra di dialogo che appare, imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per il calcolo.
1. Seleziona **OK** per eseguire il calcolo.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Elaborare una o più righe di contratto specifiche per una transazione selezionata

1. Apri l'appropriata [pagina elenco delle transazioni di sconto](rebate-management-deals.md) per il tipo di transazione con cui desideri lavorare.
1. Apri la transazione da cui desideri elaborare una riga.
1. Seleziona la scheda **Righe** nell'angolo in alto a destra.
1. Nella scheda dettaglio **Gestione degli sconti** seleziona la riga per ciascuna riga della transazione che desideri elaborare.
1. Sulla barra degli strumenti della scheda dettaglio **Gestione degli sconti** seleziona uno dei seguenti comandi. (Questi comandi sono disponibili solo per le transazioni in cui il campo **Riconcilia per** è impostato su *Riga* .)

    - **Elabora \> Accantonamento** - Accantonamento di una serie di ratei per ogni riga di transazione pertinente che non vengono registrati. Questa voce di menu non è disponibile per le transazioni in cui il campo **Output sconto** è impostato su *Articolo*.
    - **Elabora \> Gestione degli sconti** - Elabora una serie di transazioni che forniscono il valore dello sconto per ogni riga di transazione.
    - **Elabora \> Annulla** – Per ogni transazione di origine per la transazione di sconto e il periodo specificato, elabora lo scostamento tra gli importi registrati per un accantonamento e per la gestione degli sconti. Questa voce di menu non è disponibile per le transazioni in cui il campo **Output sconto** è impostato su *Articolo*. 

1. Nella finestra di dialogo che appare, imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per il calcolo.
1. Seleziona **OK** per eseguire il calcolo.

### <a name="process-deals-using-a-batch-job"></a>Elaborare le transazioni utilizzando un processo batch

Invece di elaborare transazioni o righe di transazioni specifiche, è possibile eseguire un processo batch per elaborare più transazioni contemporaneamente. Facoltativamente, puoi applicare filtri ai record e/o impostare una pianificazione ricorrente. Per elaborare le transazioni utilizzando un processo batch, segui questi passaggi.

1. Eseguire uno dei passaggi riportati di seguito.

    - Vai a **Gestione degli sconti \> Attività periodiche \> Elabora \> Accantonamento** per eseguire l'accantonamento di una serie di ratei per ogni transazione rilevante, ma senza pubblicarli.
    - Vai a **Gestione degli sconti \> Attività periodiche \> Elabora \> Gestione degli sconti** per elaborare una serie di transazioni che forniscono il valore dello sconto per ogni transazione.
    - Vai a **Gestione degli sconti \> Attività periodiche \> Elabora \> Fuori catalogo** per stornare le transazioni registrate in precedenza e annullarle in modo da poter calcolare nuove transazioni di sconto.

1. Nella finestra di dialogo che appare, nella scheda dettagli **Parametri** nella sezione **Periodo**, imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per le transazioni per il calcolo.
1. Nella sezione **Periodo di garanzia** imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per le garanzie del calcolo.
1. Nella scheda dettaglio **Record da includere** puoi impostare i filtri per limitare il set di offerte che il processo batch elaborerà. Queste impostazioni funzionano come per altri tipi di processi batch.
1. Nella Scheda dettaglio **Esecuzione in background** puoi impostare l'elaborazione batch e le opzioni di programmazione come richiesto. Queste impostazioni funzionano come per altri tipi di processi batch.
1. Seleziona **OK** per eseguire e/o pianificare il calcolo.

### <a name="process-deals-by-using-the-rebate-workbench"></a>Elaborare le transazioni utilizzando il workbench sconti

Invece di elaborare transazioni o righe di transazioni specifiche, puoi usare il *workbench sconti* per elaborare più transazioni contemporaneamente. Facoltativamente, puoi applicare filtri ai record e/o impostare una pianificazione ricorrente. Non è necessario selezionare alcuna riga. Il sistema elaborerà tutte le righe che soddisfano i requisiti di data e filtro impostati.

Per elaborare le transazioni usando il workbench sconti, segui questi passaggi.

1. Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Workbench sconti**.
1. Nel riquadro azioni, nella scheda **Workbench sconti** nel gruppo **Elaborazione** seleziona uno dei seguenti comandi:

    - **Elabora \> Accantonamento** - Accantonamento di una serie di ratei per ogni riga di transazione pertinente che non vengono registrati.
    - **Elabora \> Gestione degli sconti** - Elabora una serie di transazioni che forniscono il valore dello sconto per ogni riga di transazione.
    - **Elabora \> Annulla** – Elabora lo scostamento tra la gestione accantonamenti e sconti registrata per ogni transazione di origine, per la transazione di sconto e il periodo specificato.

1. Nella finestra di dialogo **Gestione sconti**, nella sezione **Periodo**, imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per il calcolo.
1. Nella sezione **Periodo di garanzia** imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per le garanzie del calcolo.
1. Nella scheda dettaglio **Record da includere** puoi impostare i filtri per limitare il set di offerte che il processo batch elaborerà. Queste impostazioni funzionano come per altri tipi di processi batch.
1. Nella Scheda dettaglio **Esecuzione in background** puoi impostare l'elaborazione batch e le opzioni di programmazione come richiesto. Queste impostazioni funzionano come per altri tipi di processi batch.
1. Seleziona **OK** per eseguire e/o pianificare il calcolo.

## <a name="view-and-edit-rebate-management-transactions"></a>Visualizzare e modificare le transazioni di gestione degli sconti

Quando elabori una o più transazioni, il sistema crea le transazioni che puoi visualizzare e, forse, modificare prima di registrarle.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>Visualizzare e modificare le transazioni di gestione sconti utilizzando la pagina dell'elenco delle transazioni di sconto

Per visualizzare e modificare le transazioni di gestione sconti utilizzando la pagina dell'elenco delle transazioni di sconto, segui questi passaggi.

1. Eseguire uno dei passaggi riportati di seguito.

    - Seleziona la transazione di cui visualizzare le transazioni (ad esempio, nella pagina [**Tutte le transazioni di gestione degli sconti**](rebate-management-deals.md)). Nel riquadro azioni, nella scheda **Transazioni di gestione degli sconti** nel gruppo **Transazioni**, seleziona **Transazioni** o **Transazioni di garanzia**, a seconda del tipo di transazione che desideri visualizzare.
    - Apri una transazione (ad esempio, nella pagina [**Tutte le transazioni di gestione degli sconti**](rebate-management-deals.md)) per visualizzarne i dettagli. Nella Scheda dettaglio **Gestione degli sconti** seleziona la riga della transazione per cui vuoi visualizzare le transazioni. Quindi, sulla barra degli strumenti, seleziona **Transazioni** o **Transazioni di garanzia**, a seconda del tipo di transazione che desideri visualizzare. (Questi pulsanti sono disponibili solo per le transazioni in cui il campo **Riconcilia per** è impostato su *Riga* .)

1. Viene visualizzata la pagina **Transazioni data di gestione degli sconti** o **Transazioni di garanzia di gestione degli sconti**. Contiene una griglia, in cui ogni riga rappresenta una raccolta di transazioni da un singolo periodo di sconto o garanzia. Seleziona una riga nella griglia e quindi, nel riquadro azioni, seleziona **Transazioni di origine** per visualizzare le transazioni che appartengono a quella riga.
1. La pagina che appare mostra l'elenco delle transazioni del tipo selezionato che appartengono alla riga selezionata. Ogni transazione fornisce dettagli rilevanti, a seconda del tipo di transazione. Per le transazioni di garanzia è possibile visualizzare solo l'elenco. Per altri tipi di transazioni, puoi eseguire le seguenti azioni in questa pagina:

    - Per verificare il valore totale di tutte le transazioni richieste nella pagina, vedi il campo **Importo richiesto**.
    - Per visualizzare ulteriori informazioni su qualsiasi transazione, selezionala e quindi seleziona la scheda **Generale**, **Dimensione finanziaria** o **Dimensione**.
    - Per visualizzare eventuali riduzioni applicabili, seleziona **Transazioni di riduzione** nel riquadro azioni. Per ulteriori informazioni, vedi [Principi di riduzione degli sconti](rebate-reduction-principle.md).
    - Per contrassegnare le transazioni come richieste o non richieste se utilizzi un processo di richiesta, seleziona le righe pertinenti e quindi, nel riquadro azioni, seleziona uno dei seguenti comandi. (Abilita i processi di richiesta nella pagina [**Parametri di gestione degli sconti**](rebate-management-parameters.md) .)

        - **Imposta richiesto \> Tutti** - Contrassegna tutte le transazioni come richieste.
        - **Imposta richiesto \> Selezionato** - Contrassegna le transazioni selezionate come richieste.
        - **Imposta non richiesto \> Tutti** - Contrassegna tutte le transazioni come non richieste.
        - **Imposta non richiesto \> Selezionato** - Contrassegna le transazioni selezionate come non richieste.

    - Seleziona **Registra** nel riquadro azioni per registrare la richiesta per tutte le righe pertinenti. Se stai utilizzando una procedura di richiesta (quando l'opzione **Usa procedura di richiesta** è abilitata nella pagina **Parametri gestione sconti**), solo le righe contrassegnate come **Richieste** vengono registrate. In caso contrario, vengono registrate tutte le transazioni di origine per la transazione di sconto selezionata. Il pulsante **Registra** è disponibile solo per le transazioni di sconto. Non è disponibile per le transazioni di accantonamento e annullamento. Nella finestra di dialogo **Registra** i campi **Dal** e **Al** vengono impostati automaticamente. Imposta il campo **Data registrazione** quindi seleziona **OK**.
    - Per modificare l'importo visualizzato per qualsiasi transazione aperta o non registrata, seleziona la transazione, quindi segui uno di questi passaggi:

        - Modifica il valore nel campo **Importo corretto**.
        - Nel riquadro azioni, seleziona **Imposta correzione**. Quindi, nella finestra di dialogo a discesa visualizzata, nel campo **Importo corretto**, immetti un valore.

> [!NOTE]
> Se stai usando un processo di richiesta, quando elabori il periodo successivo, l'elenco delle transazioni includerà tutte le transazioni non richieste dalla registrazione precedente, più eventuali nuove transazioni per il periodo selezionato.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>Visualizzare e modificare le transazioni di gestione sconti utilizzando il workbench sconti

Per visualizzare e modificare le transazioni di gestione sconti utilizzando il workbench sconti, segui questi passaggi.

1. Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Workbench sconti**.
1. Imposta il campo **Mostra** su *Non registrato*.
1. La pagina **Workbench sconti** mostra un elenco di transazioni. Ogni transazione fornisce dettagli rilevanti. Questi dettagli variano a seconda del tipo di transazione. In questa pagina puoi eseguire le azioni riportate di seguito:

    - Per visualizzare ulteriori informazioni su qualsiasi transazione, selezionala e quindi seleziona la scheda **Generale**, **Dimensione finanziaria** o **Dimensione**.
    - Se stai utilizzando una processo di attestazione, puoi contrassegnare le transazioni come richieste o non richieste. Seleziona le righe pertinenti e nel riquadro azioni, nella scheda **Workbench sconti** seleziona uno dei seguenti comandi. (Abilita i processi di attestazione nella pagina [**Parametri di gestione degli sconti**](rebate-management-parameters.md).)

        - **Imposta richiesto** – Contrassegna le transazioni selezionate come richieste.
        - **Imposta non richiesto** – Contrassegna le transazioni selezionate come non richieste.

    - Per registrare l'attestazione per una o più righe, seleziona le righe pertinenti. Nel riquadro azioni, nella scheda **Workbench sconti**, seleziona **Registra**. Il pulsante **Registra** è disponibile per le transazioni di accantonamento, sconto e annullamento. Nella finestra di dialogo **Registra** i campi **Dal** e **Al** vengono impostati automaticamente. Imposta il campo **Data registrazione** quindi seleziona **OK**.
    - Per modificare l'importo visualizzato per qualsiasi transazione aperta o non registrata, seleziona la transazione, quindi segui uno di questi passaggi:

        - Modifica il valore nel campo **Importo corretto**.
        - Nel riquadro azioni, nella scheda **Workbench sconti**, seleziona **Imposta correzione**. Quindi, nella finestra di dialogo a discesa visualizzata, nel campo **Importo corretto**, immetti un valore.

> [!NOTE]
> Se stai usando un processo di richiesta, quando elabori il periodo successivo, l'elenco delle transazioni includerà tutte le transazioni non richieste dalla registrazione precedente, più eventuali nuove transazioni per il periodo selezionato.

## <a name="post-rebates-transactions"></a>Registrare le transazioni di sconto

Per registrare il valore di un accantonamento elaborato, l'importo della gestione degli sconti e l'annullamento, è necessario eseguire il processo di registrazione. Il processo di registrazione contrassegna le transazioni di accantonamento, gestione degli sconti o di annullamento come registrate e crea la transazione di destinazione. Se non è necessario rivedere la transazione di destinazione, queste transazioni possono essere impostate in modo che vengano registrate automaticamente.

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>Configurare il sistema per registrare automaticamente tutte le transazioni di destinazione

Per configurare il tuo sistema in modo che registri tutte le transazioni di destinazione non appena vengono generate da una registrazione di accantonamento, importo di gestione sconti e annullamento, attiva l'opzione **Registra automaticamente giornali di registrazione** e/o **Registra automaticamente fatture a testo libero** nella pagina **Parametri di gestione degli sconti**. Per ulteriori informazioni, vedi [Parametri di gestione degli sconti](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Registrare le transazioni per tutte le righe per una o più transazioni

Dopo aver elaborato le transazioni pertinenti, segui questi passaggi per esaminare e registrare le transazioni generate per tutte le righe di una o più transazioni.

1. Apri l'appropriata [pagina elenco delle transazioni di sconto](rebate-management-deals.md) per il tipo di transazione con cui desideri lavorare.
1. Seleziona la riga per ogni transazione che desideri registrare (o apri la transazione che desideri registrare).
1. Nel riquadro azioni, nella scheda **Transazioni di gestione degli sconti** nel gruppo **Genera** seleziona uno dei seguenti comandi:

    - **Registra \> Accantonamento** - Registra le transazioni di attribuzione per competenza disponibili che hai creato.
    - **Registra \> Gestione degli sconti** - Registra le transazioni di sconti disponibili che hai creato.
    - **Registra \> Annullamento** - Registra le transazioni di annullamento disponibili che hai creato.

1. Nella finestra di dialogo visualizzata, imposta il campo **Data di registrazione**. Quindi imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per la transazione che deve essere registrata.
1. Seleziona **OK** per registrare le transazioni.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Registrare le transazioni per una o più righe di contratto specifiche per una transazione selezionata

Dopo aver elaborato le transazioni pertinenti, segui questi passaggi per esaminare e registrare le transazioni generate per una o più righe di transazioni specifiche per una transazione selezionata. Questa procedura è applicabile solo per le transazioni in cui il campo **Riconcilia per** è impostato su *Riga*.

1. Apri l'appropriata [pagina elenco delle transazioni di sconto](rebate-management-deals.md) per il tipo di transazione con cui desideri lavorare.
1. Apri la transazione con una riga per la quale desideri registrare le transazioni.
1. Seleziona la scheda **Righe** nell'angolo in alto a destra.
1. Nella scheda dettaglio **Gestione degli sconti** seleziona la riga per ciascuna riga della transazione che desideri registrare.
1. Sulla barra degli strumenti della scheda dettaglio **Gestione degli sconti** seleziona uno dei seguenti comandi. (Questi comandi sono disponibili solo per le transazioni con il campo **Riconcilia per** impostato su *Riga* .)

    - **Registra \> Accantonamento** - Registra le transazioni di attribuzione per competenza disponibili che hai creato.
    - **Registra \> Gestione degli sconti** - Registra le transazioni di sconti disponibili che hai creato.
    - **Registra \> Annullamento** - Registra le transazioni di annullamento disponibili che hai creato.

1. Nella finestra di dialogo visualizzata, imposta il campo **Data di registrazione**. Quindi imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per la transazione che deve essere registrata.
1. Seleziona **OK** per registrare le transazioni.

### <a name="post-transactions-using-a-batch-job"></a>Registrare le transazioni utilizzando un processo batch

Invece di registrare le transazioni per transazioni o righe di transazioni specifiche, è possibile eseguire un processo batch per registrare le transazioni per più transazioni contemporaneamente. Facoltativamente, puoi applicare filtri ai record e/o impostare una pianificazione ricorrente. Per registrare le transazioni utilizzando un processo batch, segui questi passaggi.

1. Eseguire uno dei passaggi riportati di seguito.

    - Vai a **Gestione degli sconti \> Attività periodiche \> Registra \> Accantonamento** per registrare le transazioni di attribuzione per competenza disponibili che hai creato.
    - Vai a **Gestione degli sconti \> Attività periodiche \> Registra \> Gestione degli sconti** per registrare le transazioni di sconto disponibili che hai creato.
    - Vai a **Gestione degli sconti \> Attività periodiche \> Registra \> Annullamento** per registrare le transazioni di annullamento disponibili che hai creato.

1. Nella finestra di dialogo che appare, nella scheda dettaglio **Parametri** nella sezione **Periodo** imposta il campo **Data di pubblicazione**. Quindi imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per la transazione che deve essere registrata.
1. Nella sezione **Periodo di garanzia** imposta i campi **Data iniziale** e **Data finale** per definire l'intervallo di date per le garanzie che devono essere registrate.
1. Nella scheda dettaglio **Record da includere** puoi impostare i filtri per limitare il set di offerte che il processo batch elaborerà. Queste impostazioni funzionano come per altri tipi di processi batch.
1. Nella Scheda dettaglio **Esecuzione in background** puoi impostare l'elaborazione batch e le opzioni di programmazione come richiesto. Queste impostazioni funzionano come per altri tipi di processi batch.
1. Seleziona **OK** per eseguire e/o pianificare il calcolo.

### <a name="post-transactions-by-using-the-rebate-workbench"></a>Registrare le transazioni utilizzando il workbench sconti

Dopo aver elaborato le transazioni di accantonamento, sconto o annullamento, segui questi passaggi per utilizzare il workbench sconti per rivedere e registrare le transazioni generate per una o più righe di transazione specifiche per tutte le transazioni.

1. Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Workbench sconti**.
1. Nella griglia, seleziona la riga per ogni riga di transazione che vuoi registrare. È possibile selezionare transazioni di accantonamento, sconto e/o annullamento non registrate. Vengono applicate le seguenti regole:

    - Il sistema registra anche tutte le righe che hanno lo stesso valore **Numero transazione sconto** delle righe selezionate.
    - Il sistema non registra le righe con il tipo di transazione *Sconto* non contrassegnato come richiesto.
    - Se si selezionano righe che sono già state registrate, il sistema ignorerà le righe registrate.
    - Il pulsante **Registra** è disponibile solo se si seleziona almeno una riga non registrata.

1. Nel riquadro azioni, nella scheda **Workbench sconti**, nel gruppo **Elaborazione**, seleziona **Registra**.
1. Nella finestra di dialogo **Registra**, imposta il campo **Data di registrazione**. I campi **Data di inizio** e **Data di fine** vengono impostati automaticamente, in base al primo valore **Data di inizio** e l'ultimo valore **Data di fine** delle righe selezionate.
1. Seleziona **OK** per registrare le transazioni.

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>Esaminare i giornali di registrazione di Gestione degli sconti

Dopo che le transazioni sono state registrate, è possibile rivedere i giornali di registrazione, i documenti o gli articoli risultanti. Le transazioni di destinazione per sconti e royalty si basano sul tipo di pagamento impostato nel profilo di registrazione e sul tipo di output dello sconto. Ad esempio, se l'output dello sconto è impostato su *Articolo*, verrà creato un ordine cliente per uno sconto cliente e un ordine fornitore per uno sconto fornitore. Questi ordini possono essere visualizzati tramite le transazioni di destinazione. In alternativa, se il pagamento è impostato per utilizzare Contabilità fornitori, verrà creata una fattura fornitore per il fornitore che viene impostata sul cliente per gli sconti cliente.

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>Rivedere i giornali di registrazione utilizzando la pagina dell'elenco delle transazioni di sconto

Per esaminare le voci del giornale di registrazione associate a una transazione di gestione degli sconti, attieniti alla seguente procedura.

1. Apri l'appropriata [pagina elenco delle transazioni di sconto](rebate-management-deals.md) per il tipo di transazione con cui desideri lavorare.
1. Seleziona la transazione per cui vuoi ispezionare le voci del giornale di registrazione.
1. Nel riquadro azioni, nella scheda **Transazioni di gestione degli sconti** nel gruppo **Transazioni**, seleziona **Transazioni** o **Transazioni di garanzia**, a seconda del tipo di transazione che desideri esaminare.
1. Imposta il campo **Mostra** su *Tutto* o *Registrato*.
1. Trova e seleziona la raccolta di transazioni che vuoi ispezionare, quindi, nel riquadro azioni, seleziona uno dei seguenti pulsanti. (Questi pulsanti sono disponibili solo quando esistono registrazioni pertinenti per la raccolta di transazioni selezionata.)

    - **Transazioni di destinazione** - Rivedi i giornali di registrazione pertinenti e altri tipi di documenti generati dalla transazione selezionata.
    - **Articoli** – Rivedere gli ordini fornitore o gli ordini cliente pertinenti che sono stati generati dalla transazione selezionata.

1. Viene visualizzato un elenco di giornali di registrazione, documenti o articoli pertinenti. Per visualizzare ulteriori informazioni su qualsiasi giornale di registrazione, documento o articolo, seleziona la riga e quindi, nel riquadro azioni, seleziona **Visualizza dettagli**.

### <a name="review-journals-by-using-the-rebate-workbench"></a>Esaminare i giornali di registrazione utilizzando il workbench sconti

Per esaminare i giornali di registrazione usando il workbench sconti, segui questi passaggi.

1. Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Workbench sconti**.
1. Imposta il campo **Mostra** su _Tutto_ o _Registrato_.
1. Trova e seleziona la riga che vuoi controllare. Quindi, nel riquadro azioni, nella scheda **Workbench sconti**, nel gruppo **Visualizza**, seleziona **Transazioni di destinazione**. Questo pulsante è disponibile solo se esistono registrazioni rilevanti per la riga selezionata.
1. Viene visualizzato un elenco di giornali di registrazione, documenti o articoli pertinenti. Per visualizzare ulteriori informazioni su qualsiasi giornale di registrazione, documento o articolo, seleziona la riga e quindi, nel riquadro azioni, seleziona **Visualizza dettagli**.

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>Transazioni di gestione sconti nel workbench detrazioni

Quando registri una transazione di gestione sconti che presenta uno dei seguenti valori di **Tipo di pagamento**, il sistema crea un giornale di registrazione detrazioni cliente o una fattura a testo libero per il conto cliente pertinente:

- Detrazioni cliente
- Detrazioni cliente fattura fiscale
- Fondi per promozioni
- Creazione di report

Dopo che una transazione di destinazione è stata creata e registrata, sarà disponibile come transazione aperta nella pagina **Workbench detrazioni** (**Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**). Le transazioni aperte hanno un valore di **Tipo di attestazione** di *Gestione sconti*, e un valore **Numero transazione sconto** è disponibile per consentire la tracciabilità. La data è impostata sulla data di registrazione della transazione di destinazione di gestione sconti. Per utilizzare il workbench detrazioni per liquidare le transazioni aperte alle detrazioni esistenti per lo stesso conto cliente, seleziona **Gestisci \> Corrispondenza** nel riquadro azioni.

Per ulteriori informazioni, vedi [Gestire le detrazioni utilizzando il workbench detrazioni](deduction-workbench.md).

## <a name="purge-unposted-transactions"></a>Eliminare le transazioni non registrate

Dopo aver elaborato le transazioni di accantonamento, sconto o annullamento, segui questi passaggi per eliminare le transazioni non registrate selezionate.

1. Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Workbench sconti**.
2. Imposta il campo **Mostra** su *Non registrato*.
3. Trova e seleziona le transazioni da eliminare. Nel riquadro azioni, nella scheda **Workbench sconti**, nel gruppo **Elaborazione**, seleziona **Elimina**.
4. Seleziona **OK** per eliminare le transazioni non registrate.

## <a name="cancel-a-posted-provision"></a>Annullare un accantonamento registrato

Dopo aver elaborato e registrato un accantonamento, segui questi passaggi per annullare le transazioni di accantonamento registrate.

1. Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Workbench sconti**.
2. Imposta il campo **Mostra** su *Registrato*.
3. Trova e seleziona le transazioni di accantonamento da annullare. Nel riquadro azioni, nella scheda **Workbench sconti**, nel gruppo **Elaborazione**, seleziona **Annulla accantonamento**.
4. Seleziona **OK** per stornare le transazioni.

Tali storni di accantonamenti saranno visibili anche nei relativi [giornali di registrazione di gestione sconti](#review-journals).
