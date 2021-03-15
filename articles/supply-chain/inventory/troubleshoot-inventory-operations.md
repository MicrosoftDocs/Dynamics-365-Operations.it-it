---
title: Risolvere i problemi relativi alle operazioni di inventario
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizzano le operazioni di inventario.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3a22229106753d265a90f0ef05f5ac82dc745bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967157"
---
# <a name="troubleshoot-inventory-operations"></a>Risolvere i problemi relativi alle operazioni di inventario

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizzano le operazioni di inventario.

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Non riesco a trovare la finestra di dialogo a discesa "Flusso di lavoro" per i giornali di registrazione magazzino.

### <a name="issue-description"></a>Descrizione del problema

Non riesci a trovare la finestra di dialogo a discesa **Flusso di lavoro** nella pagina del giornale di registrazione o le operazioni del flusso di lavoro correlate non sono disponibili.

Questo problema può verificarsi per tre motivi, come descritto nelle sottosezioni seguenti.

### <a name="issue-resolution-1"></a>Risoluzione del problema 1

Se il problema si applica a tutti gli utenti, potrebbe verificarsi perché il flusso di lavoro di approvazione non è stato assegnato al nome del giornale di registrazione. Per risolvere il problema, procedere come segue.

1. Andare a **Gestione inventario &gt; Imposta &gt; Nomi giornale di registrazione &gt; Inventario**.
1. Nel riquadro dell'elenco, selezionare il nome di un giornale di registrazione per aprirne le impostazioni.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Flusso di lavoro di approvazione** su *Sì*. Se viene richiesto di confermare la modifica, fare clic su **Sì**.
1. Nel campo **Flusso di lavoro** selezionare il flusso di lavoro che si desidera utilizzare per il nome del giornale di registrazione selezionato.

### <a name="issue-resolution-2"></a>Risoluzione del problema 2

Se il flusso di lavoro utilizza codice personalizzato, potrebbero verificarsi problemi dopo l'aggiornamento del sistema. Ad esempio, nel flusso di lavoro del giornale di registrazione, il pulsante **Invia** potrebbe essere disattivato, quindi non puoi selezionarlo per approvare un invio.

Se il pulsante **Invia** è disattivato, il flusso di lavoro potrebbe essere stato personalizzato, il che significa che il metodo del flusso di lavoro, `canSubmitToWorkflow()` in `FormDataUtil`, è stato esteso. Per risolvere questo problema, modifica il modo in cui estendi il metodo `canSubmitToWorkflow()` per utilizzare la struttura nel seguente esempio.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a>Risoluzione del problema 3

Se il problema si applica solo a pochi utenti specifici, tali utenti potrebbero non disporre dei privilegi di sicurezza obbligatori per eseguire le operazioni del flusso di lavoro sui giornali di registrazione magazzino. Verifica che ogni utente interessato disponga del privilegio di sicurezza *Mantieni il flusso di lavoro del giornale di registrazione magazzino*. Per impostazione predefinita, questo privilegio viene assegnato a un compito con lo stesso nome e tale compito viene applicato ai ruoli *Addetto magazzino* e *Responsabile magazzino*.

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a>Il mio giornale di registrazione magazzino rimane nello stato di bloccato dal sistema e il processo batch del flusso di lavoro non funziona.

### <a name="issue-description"></a>Descrizione del problema

Uno dei tuoi giornali di registrazione magazzino è bloccato da un'operazione e non viene rilasciato. Ad esempio, se si verifica un errore sconosciuto durante la registrazione (che è un'operazione di blocco del sistema), il giornale di registrazione potrebbe rimanere nello stato di blocco del sistema. In questo caso, il gestore dell'elemento di lavoro del flusso di lavoro genererà un errore mentre blocca la convalida.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Accedi all'istanza di SQL Server per Supply Chain Management e verifica se **InventJournalTable.SystemBlocked** è impostato su *1*. In tal caso, accertati che il giornale di registrazione non sia in stato bloccato e quindi reimposta **InventJournalTable.SystemBlocked** su *0*.

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a>Il mio flusso di lavoro del giornale di registrazione magazzino non viene mai completato e il giornale di registrazione non può essere modificato o registrato.

### <a name="issue-description"></a>Descrizione del problema

Dopo aver inviato un flusso di lavoro di approvazione del giornale di registrazione, l'elaborazione del flusso di lavoro smette di rispondere e non è possibile modificare o elaborare i giornali di registrazione.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Esistono diversi motivi per cui l'elaborazione del flusso di lavoro potrebbe non essere completata. Verifica i seguenti problemi:

- Vai a **Gestione inventario &gt; Imposta &gt; Flussi di lavoro gestione articoli** e rivedi la configurazione del flusso di lavoro interessato. Per ulteriori informazioni, vedere [Flussi di lavoro di approvazione del giornale di registrazione magazzino](inventory-journal-workflow.md).
- Il flusso di lavoro potrebbe riscontrare un'eccezione o un errore. Rivedi la cronologia degli elementi di lavoro del flusso di lavoro interessato per vedere se include un errore dell'applicazione che termina il flusso di lavoro.
- Il giornale di registrazione inventario può essere aggiornato o modificato solo se approvato. Se il richiamo è attivo, puoi provare a richiamare il giornale di registrazione. L'esecuzione del processo batch del flusso di lavoro potrebbe essere sospesa per diversi motivi. Alcuni di questi motivi potrebbero essere causati dal problema del framework del flusso di lavoro.

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a>Le condizioni del flusso di lavoro del giornale di registrazione magazzino si applicano solo a livello di giornale di registrazione, non a livello di riga

### <a name="issue-description"></a>Descrizione del problema

È possibile che si verifichi questo problema se, ad esempio, si tenta di configurare una condizione del flusso di lavoro del giornale di registrazione magazzini sull'importo del costo. Si configura la condizione in modo che il passaggio 1 venga eseguito solo quando l'importo del costo è inferiore a 100. Quindi si configura un'altra condizione in modo che il passaggio 2 venga eseguito solo quando l'importo del costo è maggiore o uguale a 100. Quindi, quando viene eseguito il flusso di lavoro, la cronologia del flusso di lavoro mostra solo una riga e la prima condizione viene sempre valutata come *vero*, indipendentemente dal valore inviato.

### <a name="issue-workaround"></a>Soluzione del problema

Nella versione attuale, le condizioni del flusso di lavoro del giornale di registrazione magazzino si applicano solo a livello di giornale di registrazione, non a livello di riga. Questo comportamento è predefinito. È consigliabile impostare i criteri della condizione solo sugli attributi a livello di giornale di registrazione.

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a>Il riquadro dei filtri nella pagina elenco Elenco scorte disponibili non filtra i risultati come previsto.

### <a name="issue-description"></a>Descrizione del problema

I filtri nel riquadro dei filtri nella pagina **Elenco scorte disponibili**  non filtra i risultati come previsto.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito.

La pagina  **Elenco scorte disponibili**  è assemblata da una tabella dettagliata di scorte disponibili che include tutte le dimensioni disponibili. Tuttavia, l'elenco in questa pagina è un riepilogo. Pertanto, potrebbe combinare le righe dalla tabella di origine aggregando i valori in base alle dimensioni visualizzate.

I filtri configurati nel riquadro dei filtri si applicano alla tabella di origine, non all'elenco aggregato. Questo comportamento a volte può produrre risultati imprevisti, come mostrato in [questi esempi](inventory-on-hand-list.md#examples).

Tuttavia, i  [filtri forniti nella griglia](inventory-on-hand-list.md#grid-filters)  *si applicano*  all'elenco aggregato. Questi filtri includono sia un filtro rapido nella parte superiore della griglia sia il filtro per ciascuna intestazione di colonna.

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>L'unità e la quantità unitaria non funzionano correttamente nel giornale di registrazione magazzino.

### <a name="issue-description"></a>Descrizione del problema

Potresti riscontrare uno o entrambi i seguenti problemi quando lavori con unità e quantità in un giornale di registrazione magazzino:

- Non vengono visualizzate le unità o le quantità unitarie nel giornale di registrazione magazzino mentre è impostata un'unità di conversione per il prodotto rilasciato e non è possibile modificare l'unità nel giornale di registrazione magazzino.
- Vedi i campi **Quantità** e **Unità** nel giornale di registrazione magazzino, ma non vedi il campo **Quantità unitaria**. Se modifichi l'unità, immetti una quantità e registri il giornale di registrazione, il giornale di registrazione mostra ancora l'unità di misura originale per quella quantità.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per risolvere questo problema, procedere come segue.

1. Nell'area di lavoro **Gestione funzionalità**, assicurati che la funzionalità *Utilizzo di unità di misura e quantità unitaria nei giornali di registrazione magazzino* sia attivata. Questa funzionalità aggiunge i campi **Unità** e **Quantità unitaria** al giornale di registrazione.
1. Dopo che la funzionalità è stata attivata, utilizza i campi **Quantità**, **Quantità unitaria** e **Unità** nel modo seguente:

    - **Quantità**: specifica la quantità utilizzando l'unità predefinita definita per il prodotto rilasciato. Tuttavia, l'unità predefinita stessa non viene mostrata qui. Se viene configurata una conversione tra l'unità predefinita e l'unità selezionata nel campo **Unità**, il campo **Quantità** viene aggiornato automaticamente, in base alle selezioni nei campi **Quantità unitaria** e **Unità**.
    - **Quantità unitaria**: specificare la quantità utilizzando l'unità selezionata nel campo **Unità**.
    - **Unità**: selezionare l'unità da applicare al valore nel campo **Quantità unitaria**.

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Ricevo il seguente messaggio di errore: "Il numero massimo di decimali per l'unità di stockkeeping è 0."

### <a name="issue-description"></a>Descrizione del problema

Quando si tenta di registrare una transazione di magazzino o una prenotazione di magazzino, viene visualizzato il seguente messaggio di errore: "Il numero massimo di decimali per l'unità di stockkeeping è 0."

Questo problema si verifica quando la quantità della transazione di magazzino viene specificata come valore decimale inferiore al livello di precisione supportato dal campo. Ad esempio, una quantità di *0,5* è stata specificato per una transazione di magazzino, ma sono supportate solo quantità intere. Pertanto, il valore dovrebbe essere *1* invece di *0,5*.

### <a name="issue-resolution"></a>Risoluzione dei problemi

1. Esegui il seguente script sull'istanza di SQL Server per arrotondare le quantità nelle transazioni di magazzino. Questo script correggerà i valori nella tabella **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Esegui un controllo di coerenza delle scorte disponibili dove l'opzione **correggi l'errore** è attivata. Questo controllo correggerà i valori nella tabella **inventSum**.

> [!IMPORTANT]
> Si consiglia vivamente di modificare con attenzione lo script come richiesto per il proprio ambiente, di testarlo in un ambiente di test e quindi di controllare i dati ottenuti prima di eseguire lo script in un ambiente di produzione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]