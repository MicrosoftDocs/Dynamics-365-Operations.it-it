---
title: Perché non posso stornare questa transazione?
description: Questo articolo descrive i vari motivi per cui le transazioni non possono essere stornate. Elenca anche le soluzioni per questo problema.
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9a8b26584b1a9b82440583db693cd14daa580e22
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876184"
---
# <a name="why-cant-i-reverse-this-transaction"></a>Perché non posso stornare questa transazione?

[!include [banner](../includes/banner.md)]

Questo articolo descrive i vari motivi per cui le transazioni non possono essere stornate. Elenca anche le soluzioni per questo problema.

## <a name="symptom"></a>Sintomo

Le organizzazioni potrebbero incontrare situazioni in cui devono stornare una transazione che hanno registrato. Occasionalmente, il sistema impedirà di stornare queste transazioni. Questo comportamento può originare due domande:

- Perché non posso stornare la transazione?
- In che modo la funzionalità di storno di massa influisce su questo comportamento?

## <a name="resolution"></a>Risoluzione

Le transazioni devono soddisfare criteri specifici prima di poter essere stornate. Le altre sezioni di questo articolo forniscono la convalida di ogni modulo. Sebbene questo articolo descriva le transazioni in Microsoft Dynamics 365 Finance, alcuni dei concetti e la convalida possono essere applicati ad altre app, come Dynamics 365 Supply Chain Management.

Inoltre, la posizione in cui una transazione viene stornata potrebbe influire sulla possibilità di effettuare lo storno. Ad esempio, un pagamento fornitore registrato come assegno può essere stornato solo nella sezione **Assegni** della pagina delle transazioni per i conti bancari. Non può essere stornata nella pagina **Transazioni giustificativo** in Contabilità generale.

Se la funzionalità **Storno di massa per più documenti** (nota anche come funzionalità Storno di massa) è attivata nell'area di lavoro **Gestione funzionalità** influisce sul numero di transazioni che possono essere stornate e sulla posizione in cui possono essere stornate. Questa funzionalità presenta due vantaggi quando è attivata:

- Per alcuni tipi di transazioni, è possibile selezionare e stornare più di una transazione alla volta nel giornale di registrazione in cui sono state registrate o nella pagina **Transazioni giustificativo**. Tuttavia, le singole transazioni devono risultare stornabili prima dell'attivazione della funzionalità. Prima dell'introduzione di questa funzionalità, le transazioni dovevano essere stornate una alla volta.
- *Alcune* transazioni del giornale di registrazione secondario possono essere stornate nel giornale di registrazione (giornale di registrazione generale) o nella pagina **Transazioni giustificativo**. Non devono essere stornate nella pagina del giornale di registrazione secondario. Ad esempio, un giornale di registrazione fatture fornitore in precedenza poteva essere stornato solo nella pagina **Transazioni giustificativo**. Ora può tuttavia essere stornato anche nella contabilità generale, nel giornale di registrazione o nella pagina **Transazioni giustificativo**. Ogni sezione di questo articolo illustra i tipi di transazioni a cui non si applica questo vantaggio.

La funzionalità Storno di massa **non** abilita più tipi di transazioni da stornare. Se un tipo di transazione non poteva essere stornato in precedenza, non può ancora essere stornato dopo l'attivazione della funzionalità. Ad esempio, le fatture fornitore di ordini fornitore non possono essere stornate, indipendentemente dall'attivazione o meno della funzionalità Storno di massa.

Per ulteriori informazioni sulla funzionalità Storno di massa, vedi [Stornare la registrazione del giornale di registrazione](reverse-journal-posting.md).

## <a name="general-ledger"></a>Contabilità generale

Le rettifiche della contabilità generale vengono immesse solo utilizzando i conti CoGe. Pertanto, aggiornano solo la contabilità generale.

Se la funzionalità Storno di massa è disattivata, la maggior parte delle rettifiche della contabilità generale può essere stornata individualmente nella pagina **Transazioni per \<main account\>** per la contabilità generale (**LedgerTransAccount**) (il titolo esatto della pagina varia a seconda del conto principale selezionato.) La pagina mostra ogni transazione che è stata registrata nel conto principale. Viene in genere aperta dalla pagina elenco **Bilancio di verifica** o selezionando **Transazioni** nella pagina **Transazioni giustificativo**.

Se la funzionalità Storno di massa è attivata, ora è possibile stornare uno o più giustificativi di contabilità generale nella pagina **Transazioni giustificativo** e nel giornale di registrazione da cui è stata registrata la transazione. Le eccezioni sono le transazioni di rivalutazione valuta estera della contabilità generale, di consolidamento e di chiusura di fine anno. Tali transazioni vengono stornate dalle pagine da cui è stata eseguita la chiusura di fine anno.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivi per cui le transazioni non possono essere stornate

Le transazioni non possono essere stornate per i seguenti motivi:

- Giornale di registrazione generale:

    - Il periodo fiscale è sospeso o definitivamente chiuso:

        - Se la data di storno è in un periodo fiscale non aperto, la transazione non può essere stornata.
        - Se la transazione supporta l'inserimento di una data di storno, la transazione può ancora essere stornata modificando la data di storno in un periodo aperto.

    - Il processo di chiusura di fine anno è stato eseguito:

        - La data di registrazione della transazione è in un anno fiscale che è stato chiuso a fine anno. Sebbene un periodo dell'anno fiscale possa essere ancora aperto, la transazione non può essere stornata se il processo di chiusura di fine anno è stato eseguito per l'anno fiscale. L'anno fiscale ha uno stato diverso rispetto ai relativi periodi.
        - La chiusura di fine anno può essere stornata e quindi la transazione può essere stornata. Questo approccio potrebbe non essere un'opzione. Potrebbe essere più semplice inserire manualmente una transazione di storno in un periodo aperto dell'anno fiscale chiuso o dell'anno fiscale successivo, a seconda dello stato del processo di chiusura fiscale. Se una nuova transazione viene registrata in un periodo aperto dell'anno fiscale per il quale è stato eseguito il processo di chiusura di fine anno, la chiusura di fine anno deve essere eseguita di nuovo.

    - Lo storno della transazione è già in corso:

        - Se la transazione è in fase di storno, tale processo deve essere completato. Non è possibile eseguire un processo di storno separato. 
        - Una volta completato lo storno, una transazione stornata può essere stornata di nuovo (ovvero, lo storno può essere stornato).

    - Compensazione dei saldi contabili:

        - Se è stata eseguita la compensazione dei saldi contabili della transazione utilizzando l'attività periodica **Compensazioni dei saldi contabili** (**Contabilità \> Attività periodiche \> Compensazioni dei saldi contabili**), in modo che il record esista nella tabella LedgerTransSettlement, la transazione non può essere stornata.
        - La compensazione dei saldi contabili può essere stornata e quindi il giustificativo può essere stornato.

    - Interaziendale:

        - Se la transazione è una transazione interaziendale, non può essere stornata.
        - La transazione **non** è una transazione interaziendale, ma è registrata in un conto principale a favore o a carico definito nella pagina **Impostazioni gestione interaziendale**.

    - Ratei:

        - Se il giustificativo di contabilità generale maturato viene stornato, la registrazione maturata e tutte le transazioni secondarie di attribuzione per competenza corrispondenti verranno stornate.
        - Le singole transazioni secondarie di attribuzione per competenza non possono essere stornate.

- Giornali di registrazione del riconoscimento ricavi:

    - Le transazioni di riconoscimento ricavi non possono essere stornate.
    - Quando i ricavi vengono riconosciuti tramite il giornale di registrazione per il riconoscimento ricavi, il giustificativo viene registrato solo nei conti CoGe. Pertanto, in pagine come **Transazioni giustificativo**, le transazioni sono visualizzate come se fossero solo voci di contabilità generale.

- Rivalutazione valuta estera:

    - Le transazioni di rivalutazione valuta estera possono essere stornate, ma solo nella pagina **Rivalutazione valuta estera** della contabilità generale da cui è stata eseguita la rivalutazione.
    - Lo storno può essere completato solo se è stato registrato in un periodo fiscale aperto.

- Consolidamento:

    - Le transazioni di consolidamento possono essere stornate, ma solo nella pagina **Transazioni di consolidamento**.
    - Lo storno può essere completato solo se è stato registrato in un periodo fiscale aperto.

- Chiusura di fine anno:

    - Le transazioni di chiusura di fine anno (sia di chiusura che di apertura) possono essere stornate nei seguenti modi:

        - Se la funzionalità Miglioramenti di fine anno della contabilità generale è disattivata, seleziona l'opzione **Annulla chiusura precedente** nella finestra di dialogo **Chiusura di fine anno**.
        - Se la funzionalità Miglioramenti di fine anno della contabilità generale è attivata, seleziona i record società e anno fiscale che sono stati creati per la chiusura di fine anno nella pagina **Chiusura di fine anno**, quindi seleziona **Storna chiusura di fine anno**.

    - Si noti che lo storno della chiusura di fine anno elimina effettivamente le transazioni di chiusura e apertura. Un giustificativo di storno non viene mai registrato.

## <a name="accounts-payable"></a>Contabilità fornitori

Più tipi di transazione aggiornano il registro secondario della contabilità fornitori. Gli esempi includono fatture fornitore, giornali di registrazione fatture fornitore e note spese.

Se la funzionalità Storno di massa è disattivata, le transazioni possono essere stornate individualmente nella pagina **Transazioni giustificativo** per le fatture o nella pagina **Conto bancario** per i pagamenti con assegno.

Se la funzionalità Storno di massa è attivata, anche una o più transazioni di contabilità generale possono essere stornate nella pagina **Transazioni giustificativo** e nel giornale di registrazione da cui sono state registrate le transazioni. Tuttavia, i pagamenti fornitore possono ancora essere stornati solo dal conto bancario. Inoltre, le transazioni fornitore non possono essere stornate nella pagina **Transazioni per \<main account\>** per la contabilità generale. Possono essere stornate solo nella pagina **Transazioni giustificativo**.

Tieni presente che alcune transazioni non possono essere affatto stornate. Gli esempi includono le fatture fornitore di ordini fornitore e i pagamenti elettronici di fornitori.

### <a name="reasons-why-vouchers-cant-be-reversed"></a>Motivi per cui i giustificativi non possono essere stornati

I giustificativi non possono essere stornati per i seguenti motivi:

- Il periodo fiscale è sospeso o chiuso:

    - Se la data di storno è in un periodo fiscale non aperto, la transazione non può essere stornata.
    - Se la transazione supporta l'inserimento di una data di storno, la transazione può ancora essere stornata modificando la data di storno in un periodo aperto.

- Il processo di chiusura di fine anno della contabilità generale è stato eseguito:

    - La data di registrazione della transazione è in un anno fiscale che è stato chiuso nella contabilità generale. Sebbene un periodo dell'anno fiscale possa essere ancora aperto, la transazione non può essere stornata se il processo di chiusura di fine anno è stato eseguito per l'anno fiscale. L'anno fiscale ha uno stato diverso rispetto ai relativi periodi.
    - La chiusura di fine anno può essere stornata e quindi la transazione può essere stornata. Questo approccio potrebbe non essere un'opzione. Potrebbe essere più semplice inserire manualmente una transazione di storno in un periodo aperto dell'anno fiscale chiuso o dell'anno fiscale successivo, a seconda dello stato del processo di chiusura fiscale. Se una nuova transazione viene registrata in un periodo aperto dell'anno fiscale per il quale è stato eseguito il processo di chiusura di fine anno, la chiusura di fine anno deve essere eseguita di nuovo.

- L'inserimento nel giornale di registrazione secondario non è stata trasferito alla contabilità generale:

    - Questo motivo si applica solo alle fatture fornitore non relative a ordini fornitore.
    - Usa la pagina **Inserimenti nel giornale di registrazione secondario non ancora trasferiti** per trasferire la voce nella contabilità generale. La fattura fornitore non relativa a ordine fornitore può quindi essere stornata nella pagina **Transazioni fornitore**.

- Liquidazione:

    - La transazione (come una fattura o un pagamento) viene liquidata o contrassegnata per la liquidazione.

        - Puoi verificare se una transazione è stata liquidata o contrassegnata per la liquidazione selezionando **Visualizza liquidazioni** o **Liquidazione \> Cronologia liquidazioni** nella pagina **Transazioni fornitore**.
        - Puoi anche stornare una liquidazione nella pagina **Transazioni fornitore** (**Liquidazione \> Annulla liquidazione**) se una delle transazioni deve essere annullata.

- Il giustificativo contiene più di una transazione del giornale di registrazione secondario che è stata inserita utilizzando lo stesso numero di giustificativo (emissione di un voucher).
- La fattura non è stata approvata:

    - Se la casella di controllo **Approvazione** non è selezionata nella fattura, la fattura non può essere stornata.

        - In questo caso, l'approvazione non si riferisce alle approvazioni nel processo del flusso di lavoro ma all'opzione **Approvazione** nella fattura. Questa opzione è utilizzata per impedire il pagamento di una fattura. Viene in genere utilizzata per le fatture del registro delle fatture fornitore.

- La transazione è nel pool di fatture:

    - Una fattura nel pool non può essere stornata direttamente nella pagina **Transazioni fornitore**. Deve invece essere stornata attraverso il processo di cancellazione nella pagina **Giornale di approvazione fatture**.

- La transazione include una fattura padre che è stata corretta (localizzazione indiana).
- Lo stato dell'effetto passivo della transazione è **Fattura rimessa**.
- La transazione viene utilizzata per una liquidazione fiscale parziale.
- La transazione contiene un conto fornitore ma viene stornata da una pagina errata, come ad esempio la pagina **Transazioni per \<main account\>**:

    - Come suggerisce questo motivo, anche quando la funzionalità Storno di massa è attivata, alcune transazioni del giornale di registrazione secondario possono essere stornate solo in pagine specifiche.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipi di transazioni che non possono essere stornate

Le transazioni dei seguenti tipi non possono essere stornate:

- Rivalutazione valuta estera:

    - A differenza della rivalutazione valuta estera della contabilità generale, la rivalutazione valuta estera della contabilità clienti e della contabilità fornitori non può essere stornata. La rivalutazione deve invece essere rieseguita utilizzando la data della fattura. In questo caso, la rivalutazione utilizza il tasso di cambio della data della fattura e porta sostanzialmente a 0 (zero) il profitto o la perdita non realizzato. Pertanto, il risultato è simile al risultato dello storno della rivalutazione precedente. Tuttavia, tieni presente che lo stesso importo non verrà stornato se il tasso di cambio predefinito è stato modificato nella fattura.

- Fattura, fornitore di ordine fornitore:

    - È necessario creare una nota di accredito per stornare la fattura fornitore. Per ulteriori informazioni su come creare una transazione di storno, vedi [Creare un ordine di reso acquisti](../../supply-chain/procurement/tasks/create-purchase-return-order.md).

- Effetto passivo
- Spedizione di esportazione con lettera di credito bancaria

## <a name="accounts-receivable"></a>Contabilità clienti

Vari tipi di transazione aggiornano i giornali di registrazione secondari della contabilità clienti. Gli esempi includono fatture cliente di ordini cliente, fatture cliente immesse tramite il giornale di registrazione generale, fatture a testo libero, pagamenti cliente e annullamenti.

Se la funzionalità Storno di massa è disattivata, le transazioni possono essere stornate individualmente nella pagina **Transazioni cliente** per le fatture o nella pagina **Conti bancari** per i depositi. Per informazioni su come stornare un pagamento, vedi la sezione [Gestione cassa e banche](cant-reverse-transctns.md#cash-and-bank-management) più avanti in questo articolo.

Se la funzionalità Storno di massa è attivata, anche una o più transazioni di contabilità clienti possono essere stornate nella pagina **Transazioni giustificativo** e nel giornale di registrazione da cui sono state registrate. Tuttavia, i depositi possono ancora essere stornati solo dal conto bancario e le fatture a testo libero possono essere stornate solo nella pagina di origine (se la funzionalità che consente le correzioni è attivata). Inoltre, le transazioni cliente non possono ancora essere stornate nella pagina **Transazioni per \<main account\>** per la contabilità generale. Tuttavia, possono essere stornate nella pagina **Transazioni giustificativo**.

Tieni presente che alcune transazioni non possono essere stornate. Gli esempi includono fatture cliente di ordini di vendita e annullamenti.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivi per cui le transazioni non possono essere stornate

Le transazioni non possono essere stornate per i seguenti motivi:

- Il periodo fiscale è sospeso o definitivamente chiuso:

    - Se la data di storno è in un periodo fiscale non aperto, la transazione non può essere stornata.
    - Se la transazione supporta l'inserimento di una data di storno, la transazione può ancora essere stornata modificando la data di storno in un periodo aperto.

- Il processo di chiusura di fine anno della contabilità generale è stato eseguito:

    - La data di registrazione della transazione è in un anno fiscale per il quale è stata eseguita la chiusura di fine anno della contabilità generale. Sebbene un periodo dell'anno fiscale possa essere ancora aperto, la transazione non può essere stornata se il processo di chiusura di fine anno è stato eseguito per l'anno fiscale. L'anno fiscale ha uno stato diverso rispetto ai relativi periodi.
    - La chiusura di fine anno può essere stornata e quindi la transazione può essere stornata. Questo approccio potrebbe non essere un'opzione. Potrebbe essere più semplice inserire manualmente una transazione di storno in un periodo aperto dell'anno fiscale chiuso o dell'anno fiscale successivo, a seconda dello stato del processo di chiusura fiscale. Se una nuova transazione viene registrata in un periodo aperto dell'anno fiscale per il quale è stato eseguito il processo di chiusura di fine anno, la chiusura di fine anno deve essere eseguita di nuovo.

- L'inserimento nel giornale di registrazione secondario non è stata trasferito alla contabilità generale:

    - Questo motivo vale solo per le fatture a testo libero.
    - Usa la pagina **Inserimenti nel giornale di registrazione secondario non ancora trasferiti** per trasferire la voce nella contabilità generale. La fattura a testo libero può quindi essere stornata o corretta se la funzionalità di correzione è abilitata.

- Liquidazione:

    - La transazione (come una fattura o un pagamento) viene liquidata o contrassegnata per la liquidazione.

        - Puoi verificare se una transazione è stata liquidata o contrassegnata per la liquidazione selezionando **Visualizza liquidazioni** o **Liquidazione \> Cronologia liquidazioni** nella pagina **Transazioni cliente**.
        - Puoi anche stornare una liquidazione nella pagina **Transazioni cliente** (**Liquidazione \> Annulla liquidazione**) se una delle transazioni deve essere annullata.

- La transazione contiene più di una transazione del giornale di registrazione secondario che è stata inserita utilizzando lo stesso numero di giustificativo (emissione di un voucher).
- La fattura non è stata approvata:

    - Se la casella di controllo **Approvazione** non è selezionata nella fattura, la fattura non può essere stornata.

        - In questo caso, l'approvazione non si riferisce alle approvazioni nel processo del flusso di lavoro ma all'opzione **Approvazione** nelle righe del giustificativo. Questa opzione è utilizzata per impedire il pagamento di una fattura. Sebbene questa opzione sia in genere utilizzata nella contabilità fornitori, è disponibile anche per le fatture della contabilità clienti immesse tramite i giornali di registrazione.

- La transazione include una fattura padre che è stata corretta (localizzazione indiana).
- La transazione contiene un conto cliente ma viene stornata da una pagina errata, come ad esempio la pagina **Transazioni per \<main account\>**:

    - Come suggerisce questo motivo, anche quando la funzionalità Storno di massa è attivata, alcune transazioni del giornale di registrazione secondario possono essere stornate solo in pagine specifiche.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipi di transazioni che non possono essere stornate

Le transazioni dei seguenti tipi non possono essere stornate:

- Rivalutazione valuta estera:

    - A differenza della rivalutazione valuta estera della contabilità generale, la rivalutazione valuta estera della contabilità clienti e della contabilità fornitori non può essere stornata. La rivalutazione deve invece essere rieseguita utilizzando la data della fattura. In questo caso, la rivalutazione utilizza il tasso di cambio della data della fattura e porta sostanzialmente a 0 (zero) il profitto o la perdita non realizzato. Pertanto, il risultato è simile al risultato dello storno della rivalutazione precedente. Tuttavia, tieni presente che lo stesso importo non verrà stornato se il tasso di cambio predefinito è stato modificato nella fattura.

- Una transazione che ha rettificato la ritenuta d'acconto
- Fattura cliente di ordine cliente:

    - È necessario creare una nota di accredito o un reso per stornare la transazione. Per informazioni su come creare la transazione di storno, vedi [Resi su vendite](../../supply-chain/warehousing/sales-returns.md).

- Effetti attivi
- Transazione registratore di cassa
- Rettifica avanzata
- Nota d'interesse
- Lettere di sollecito
- Lettera di credito bancaria
- Spedizione di esportazione
- Giornali di registrazione del riconoscimento ricavi:

    - Quando i ricavi vengono riconosciuti tramite il giornale di registrazione per il riconoscimento ricavi, i giustificativi sono registrati solo nei conti CoGe. Pertanto, vengono visualizzati come se fossero solo voci di contabilità generale. Queste voci non possono essere stornate, perché la programmazione dei ricavi non verrà riaperta per riconoscere nuovamente i ricavi.

## <a name="cash-and-bank-management"></a>Gestione cassa e banche

Diversi tipi di transazioni aggiornano la contabilità secondaria della banca tramite il giornale di registrazione generale. Gli esempi includono pagamenti fornitore, pagamenti cliente e bonifici bancari.

Se la funzionalità Storno di massa è disattivata, le transazioni possono essere stornate individualmente nella pagina **Conti bancari** per assegni e depositi o nella pagina **Transazioni cliente** per i pagamenti cliente.

Se la funzionalità Storno di massa è attivata, anche una o più transazioni di pagamento possono essere stornate nella pagina **Transazioni giustificativo** e nel giornale di registrazione da cui sono state registrate le transazioni. Tuttavia, i depositi possono ancora essere stornati solo dal conto bancario. Inoltre, le transazioni bancarie non possono ancora essere stornate nella pagina **Transazioni per \<main account\>** della contabilità generale. Tuttavia, possono essere stornate nella pagina **Transazioni giustificativo**.

Tieni presente che alcune transazioni non possono essere stornate. Gli esempi includono pagamenti fornitore elettronici.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivi per cui le transazioni non possono essere stornate

Le transazioni non possono essere stornate per i seguenti motivi:

- Il periodo fiscale è sospeso o definitivamente chiuso:

    - Se la data di storno è in un periodo fiscale non aperto, la transazione non può essere stornata.
    - Se la transazione supporta l'inserimento di una data di storno, la transazione può ancora essere stornata modificando la data di storno in un periodo aperto.

- Il processo di chiusura di fine anno della contabilità generale è stato eseguito:

    - La data di registrazione della transazione è in un anno fiscale per il quale è stata eseguita la chiusura di fine anno della contabilità generale. Sebbene un periodo dell'anno fiscale possa essere ancora aperto, la transazione non può essere stornata se il processo di chiusura di fine anno è stato eseguito per l'anno fiscale. L'anno fiscale ha uno stato diverso rispetto ai relativi periodi.
    - La chiusura di fine anno può essere stornata e quindi la transazione può essere stornata. Questo approccio potrebbe non essere un'opzione. Potrebbe essere più semplice inserire manualmente una transazione di storno in un periodo aperto dell'anno fiscale chiuso o dell'anno fiscale successivo, a seconda dello stato del processo di chiusura fiscale. Se una nuova transazione viene registrata in un periodo aperto dell'anno fiscale per il quale è stato eseguito il processo di chiusura di fine anno, la chiusura di fine anno deve essere eseguita di nuovo.

- Liquidazione:

    - La transazione (pagamento) viene liquidata o contrassegnata per la liquidazione.

        - Puoi verificare se una transazione è stata liquidata o contrassegnata per la liquidazione selezionando **Visualizza liquidazioni** o **Liquidazione \> Cronologia liquidazioni** nella pagina **Transazioni fornitore** o **Transazioni cliente**.
        - Puoi anche stornare una liquidazione nella pagina **Transazioni fornitore** o **Transazioni cliente** (**Liquidazione \> Annulla liquidazione**) se una delle transazioni deve essere stornata.

- La transazione contiene più di una transazione del giornale di registrazione secondario che è stata inserita utilizzando lo stesso numero di giustificativo (emissione di un voucher).
- Transazioni provvisorie:

    - Se la transazione è correlata a un pagamento provvisorio, non può essere annullata.
    - Se il pagamento provvisorio deve essere stornato, il pagamento deve essere eliminato dal conto provvisorio alla banca. Il pagamento può quindi essere stornato, a condizione che soddisfi gli altri criteri di convalida.

- La transazione contiene un conto bancario, ma viene stornata nella pagina **Transazioni per \<main account\>** o in un giornale di registrazione secondario errato, come Contabilità clienti o Contabilità fornitori:

    - Come suggerisce questo motivo, anche quando la funzionalità Storno di massa è attivata, alcune transazioni del giornale di registrazione secondario possono essere stornate solo in pagine specifiche.

- Rivalutazione valuta estera bancaria:

    - La rivalutazione della valuta estera bancaria può essere stornata. Tuttavia, lo storno potrebbe essere impedito se i passaggi di storno non vengono eseguiti in ordine cronologico. Ad esempio, se esegui la rivalutazione in marzo e aprile, la rivalutazione di marzo non può essere stornata finché non viene stornata la rivalutazione di aprile.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipi di transazioni che non possono essere stornate

Le transazioni dei seguenti tipi non possono essere stornate:

- I pagamenti fornitore effettuati come bonifici
- Effetti passivi
- Effetti attivi

## <a name="fixed-assets"></a>Cespiti

Diversi tipi di transazioni aggiornano il giornale di registrazione cespiti secondario. Gli esempi includono acquisizioni e ammortamenti.

Se la funzionalità Storno di massa è disattivata, le transazioni possono essere stornate individualmente nella pagina **Transazioni fornitore**, nella pagina **Transazioni cespiti** o in Leasing cespiti, a seconda del tipo di transazione.

Se la funzionalità Storno di massa è attivata, anche una o più transazioni cespiti possono essere stornate nella pagina **Transazioni giustificativo** nel giornale di registrazione da cui sono state registrate le transazioni.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Motivi per cui le transazioni non possono essere stornate

Le transazioni non possono essere stornate per i seguenti motivi:

- Il periodo fiscale è sospeso o definitivamente chiuso:

    - Se la data di storno è in un periodo fiscale non aperto, la transazione non può essere stornata.
    - Se la transazione supporta l'inserimento di una data di storno, la transazione può ancora essere stornata modificando la data di storno in un periodo aperto.

- Il processo di chiusura di fine anno della contabilità generale è stato eseguito:

    - La data di registrazione della transazione è in un anno fiscale che è stato chiuso nella contabilità generale. Sebbene un periodo dell'anno fiscale possa essere ancora aperto, la transazione non può essere stornata se il processo di chiusura di fine anno è stato eseguito per l'anno fiscale. L'anno fiscale ha uno stato diverso rispetto ai relativi periodi.
    - La chiusura di fine anno può essere stornata e quindi la transazione può essere stornata. Questo approccio potrebbe non essere un'opzione. Potrebbe essere più semplice inserire manualmente una transazione di storno in un periodo aperto dell'anno fiscale chiuso o dell'anno fiscale successivo, a seconda dello stato del processo di chiusura fiscale. Se una nuova transazione viene registrata in un periodo aperto dell'anno fiscale per il quale è stato eseguito il processo di chiusura di fine anno, la chiusura di fine anno deve essere eseguita di nuovo.

- Acquisizioni:

    - Se l'acquisizione è avvenuta in una fattura fornitore di ordine fornitore, lo storno deve essere effettuato inserendo una nota di accredito fornitore. Per ulteriori informazioni su come immettere la transazione di storno, vedi [Creare un ordine di reso acquisti](../../supply-chain/procurement/tasks/create-purchase-return-order.md).
    - L'acquisizione è avvenuta in una transazione di progetto.
    - L'acquisizione non può essere stornata dopo la registrazione dell'ammortamento per il cespite. L'ammortamento deve essere stornato prima che l'acquisizione possa essere stornata.
    - Se lo stato del modello di valore o del registro beni ammortizzabili per un cespite non è aperto, la transazione non può essere stornata.

- Dismissioni:

    - La dismissione avviene tramite una fattura a testo libero:

        - La correzione di una fattura a testo libero è bloccata se contiene un cespite. Tuttavia, se il cespite viene dismesso tramite un giornale di registrazione, la fattura a testo libero può essere stornata dal record del cespite.

    - Se lo stato del modello di valore o del registro beni ammortizzabili per un cespite non è aperto, la transazione non può essere stornata.

- Ammortamento:

    - L'ammortamento **può** essere stornato se viene registrato anche l'ammortamento successivo. Tuttavia, riceverai un avviso, poiché questo approccio non è una procedura consigliata.
    - Se lo stato del modello di valore o del registro beni ammortizzabili per un cespite non è aperto, la transazione non può essere stornata.

- Le transazioni (o le transazioni di storno) per un cespite e un libro cespiti specifico esistono per la data della transazione del giustificativo o una data successiva.
- La transazione contiene un conto cespiti ma viene stornata nella pagina **Transazioni per \<main account\>** o in un giornale di registrazione secondario errato, come Contabilità clienti o Contabilità fornitori:

    - Come suggerisce questo motivo, anche quando la funzionalità Storno di massa è attivata, alcune transazioni del giornale di registrazione secondario possono essere stornate solo in pagine specifiche.
    - Se si verifica un'acquisizione in una fattura fornitore di ordine non fornitore o in un giornale di registrazione fatture fornitore, può essere stornata solo nella pagina **Transazioni fornitore** nella contabilità fornitori.
    - Se un cespite viene acquisito da Leasing cespite, può essere stornato nella pagina **Transazioni di passività** in Leasing cespite.
