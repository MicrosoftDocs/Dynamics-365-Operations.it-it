---
title: Dimensioni finanziarie predefinite su giornali di registrazione finanziari
description: In questo articolo vengono descritte le regole che definiscono il modo in cui i valori di dimensione finanziaria vengono impostati sulle transazioni immesse tramite i giornali di registrazione finanziari. Include anche dettagli per scenari in cui vengono utilizzate dimensioni fisse.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d0fcf836e22207baae562801fb082d735df0f96
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907924"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>Dimensioni finanziarie predefinite su giornali di registrazione finanziari

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritte le regole che definiscono il modo in cui i valori di dimensione finanziaria vengono impostati sulle transazioni immesse tramite i giornali di registrazione finanziari (ma non tramite giornali di registrazione magazzino o giornali di progetto). Include anche dettagli per scenari in cui vengono utilizzate dimensioni fisse.

## <a name="symptom"></a>Sintomo

I valori di dimensione finanziaria non sono impostati come previsto nel conto o nel conto di contropartita all'interno di un giornale di registrazione finanziario. Gli scenari seguenti costituiscono due esempi:

Un giustificativo viene inserito in un giornale di registrazione generale. Il conto è un conto fornitore e il conto di contropartita è un conto bancario. Le dimensioni finanziarie del fornitore vengono immesse per impostazione predefinita nel conto, ma le dimensioni finanziarie della banca non vengono immesse per impostazione predefinita nel conto di contropartita. Invece, i valori di dimensione dal conto vengono immessi per impostazione predefinita nel conto di contropartita.

A un cliente sono assegnati valori di dimensione finanziaria predefiniti e a un conto principale ricavi è assegnato un valore di dimensione fissa per la dimensione finanziaria Reparto. Un giustificativo viene inserito in un giornale di registrazione generale.  Il conto è il cliente e il conto di contropartita è un conto CoGe, in particolare il conto ricavi con il valore di dimensione fissa. La dimensione fissa non è impostata nel conto di contropartita per il conto principale ricavi. Viene invece impostata sul valore di dimensione Reparto dal conto, proveniente dal cliente.  Dopo aver registrato il giustificativo, il valore di dimensione fissa viene utilizzato nella voce contabile registrata, ma il giustificativo mostra ancora il valore del reparto del cliente nel conto ricavi. 

Quali regole vengono seguite per i valori di dimensione finanziaria impostati sui giustificativi all'interno di un giornale di registrazione?

## <a name="resolution"></a>Risoluzione

Le regole seguenti vengono seguite per immettere i valori di dimensione finanziaria per impostazione predefinita nelle righe di un giustificativo nei giornali di registrazione finanziari, ad esempio il giornale di registrazione generale o il giornale di registrazione fatture fornitore. 

1. **Intestazione giornale di registrazione**

   - Le dimensioni dell'intestazione del giornale di registrazione vengono immesse per impostazione predefinita dalle dimensioni del nome del giornale di registrazione.

2. **Conto della riga del giornale di registrazione**

   - Le dimensioni del conto della riga del giornale di registrazione vengono immesse per impostazione predefinita dalle dimensioni dell'intestazione del giornale di registrazione.
   - Se le dimensioni finanziarie sono vuote, i relativi valori vengono immessi per impostazione predefinita dalle dimensioni cliente, fornitore, banca, cespite, progetto o contabilità generale.

     - Se il tipo di conto è **Contabilità generale**, una dimensione fissa in un conto CoGe viene trattata come una dimensione predefinita durante l'immissione della transazione.
     - Se il tipo di conto è **Cliente**, **Fornitore**, **Banca**, **Cespiti** o **Progetto**, non è ancora possibile determinare il conto principale. Pertanto, per il conto non verrà mai immessa una dimensione fissa per impostazione predefinita.

3. **Conto di contropartita della riga del giornale di registrazione**

 - Innanzitutto, le dimensioni del conto di contropartita della riga del giornale di registrazione vengono immesse per impostazione predefinita dalle dimensioni del conto della riga del giornale di registrazione.

 - Se le dimensioni finanziarie sono vuote, i successivi valori immessi per impostazione predefinita provengono dalle dimensioni cliente, fornitore, banca, cespiti, progetto o contabilità generale predefinite.
   1. Se il tipo di conto di contropartita è **Contabilità generale**, una dimensione fissa in un conto CoGe viene trattata come una dimensione predefinita durante l'immissione della transazione. Se un valore di dimensione è già stato immesso per impostazione predefinita dal conto, il valore di dimensione predefinito o fisso del conto principale non sovrascriverà il valore esistente.
   2. Se il tipo di conto di contropartita è **Cliente**, **Fornitore**, **Banca**, **Cespiti** o **Progetto**, il conto principale non è ancora noto, quindi per il conto di contropartita non verrà mai immessa una dimensione fissa per impostazione predefinita.

4. **Registrazione**

    1. Durante la registrazione, viene valutato il conto principale per ogni riga della voce contabile (sia per il conto che per il conto di contropartita) per determinare se esiste un valore di dimensione fissa. Se viene definita una dimensione fissa, tutti i valori esistenti o vuoti vengono sostituiti con tale valore di dimensione fissa.

        Il valore di dimensione fissa **non** è mostrato nelle righe del giornale di registrazione dopo la registrazione. Viene invece mostrato nella voce contabile quando si visualizza il giustificativo dopo che è stato registrato.

    2. Nessun altro valore di dimensione viene immesso per impostazione predefinita durante la registrazione, inclusi conti CoGe ulteriori che potrebbero essere aggiunti durante la registrazione, ad esempio conti con arrotondamento al centesimo e interaziendali da versare e da ricevere dai conti. Le voci di dimensione predefinite per conti CoGe aggiuntivi vengono recuperate dal conto o dai conti di contropartita.

Ai fini dell'immissione di valori di dimensione per impostazione predefinita, il processo predefinito del giornale di registrazione non è in grado di determinare se un valore di dimensione vuoto è stato lasciato intenzionalmente vuoto o se la voce predefinita non è stata inserita. Se il valore di una dimensione viene lasciato intenzionalmente vuoto, è possibile che venga comunque immesso un valore per impostazione predefinita utilizzando l'ordine predefinito descritto in precedenza. Se si richiede che una dimensione abbia un valore vuoto, potrebbe essere necessario creare una dimensione che abbia un valore di **0** (zero) o **Vuoto**, in modo che possa essere utilizzato al posto di una dimensione vuota.

Esaminare i seguenti scenari in cui vengono mostrati esempi dell'ordine predefinito della dimensione finanziaria.

### <a name="scenario-1"></a>Scenario 1

Andare a **Contabilità generale \> Impostazione del giornale di registrazione \> Nomi giornale di registrazione** e selezionare il nome del giornale **GenJrn**. Quindi, nella Scheda dettaglio **Dimensioni finanziarie**, definire i seguenti valori per le dimensioni finanziarie predefinite:

- **BUSINESSUNIT:** 001
- **DEPARTMENT:** 024

[![Pagina Nomi giornale di registrazione](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

Andare a **Contabilità generale \> Scritture contabili \> Giornale di registrazione generale**, quindi creare un nuovo giornale di registrazione generale che utilizzi il nome del giornale **GenJrn**. Le dimensioni vengono immesse per impostazione predefinita dal nome del giornale di registrazione (tabella LedgerJournalName) all'intestazione del giornale di registrazione (tabella LedgerJournalTable), come mostrato nella scheda **Dimensioni finanziarie**.

[![Scheda Dimensioni finanziarie nella pagina Giornali di registrazione generali](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

Andare a **Righe**. Nel campo **Tipo di conto**, selezionare **Contabilità generale**, quindi, nel campo **Conto**, immettere **170150**. Quindi, selezionare il tasto **Tab** per uscire dal campo. Le dimensioni vengono immesse per impostazione predefinita dall'intestazione del giornale di registrazione. Quindi, il valore **Conto** è mostrato come **170150-001-024**.

[![Righe del giornale di registrazione per un giornale di registrazione generale nella pagina del giustificativo del giornale di registrazione](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

Modificare il valore **Conto** in **170150-001-023**. Immettere un importo a debito o a credito. Nel campo **Tipo di conto di contropartita**, selezionare **Contabilità generale**, quindi, nel campo **Conto di contropartita**, immettere **600150**. I valori di dimensione vengono immessi per impostazione predefinita dal conto. Quindi, il valore **Conto di contropartita** è mostrato come **600150-001-023**.

### <a name="scenario-2"></a>Scenario 2

Utilizzare le stesse dimensioni finanziarie definite per il nome del giornale di registrazione nello scenario 1. Quindi, andare a **Contabilità clienti \> Clienti \> Tutti i clienti** e definire i valori di dimensione finanziaria predefiniti per il cliente US-001. Selezionare il cliente per aprire i dettagli del cliente. Sulla scheda **Dimensioni finanziarie**, mantenere il valore predefinito per la dimensione **BUSINESSUNIT** (**001**). Aggiungere la dimensione **COSTCENTER**, quindi immettere come valore **007**.

Crea un nuovo giornale di registrazione generale che utilizzi il nome del giornale di registrazione **GenJrn**. Sulla scheda **Dimensioni finanziarie**, modificare il valore predefinito **BUSINESSUNIT** da **001** a **002**.

Andare a **Righe**. Nel campo **Tipo di conto**, selezionare **Cliente**, quindi, nel campo **Conto**, immettere **US-001**. Per visualizzare le dimensioni finanziarie per i tipi di conti non CoGe, selezionare **Dimensioni finanziarie \> Conto**. Vengono immesse le seguenti voci predefinite per i valori di dimensione finanziaria:

- **BUSINESSUNIT:** 002 - La voce predefinita è ricavata dall'intestazione del giornale di registrazione. Il valore **001** non è inserito per impostazione predefinita dal cliente US-001, perché è già stato inserito un valore predefinito.
- **COSTCENTER:** 007 - La voce predefinita è ricavata dall'impostazione del cliente US-001.
- **DEPARTMENT:** 024 - La voce predefinita è ricavata dall'intestazione del giornale di registrazione.

Di nuovo sulla riga, nel campo **Tipo di conto di contropartita**, selezionare **Contabilità generale**, quindi, nel campo **Conto di contropartita**, immettere **600150**. Sulla riga vengono immessi i seguenti valori di dimensione finanziaria predefiniti:

- **BUSINESSUNIT:** 002 - La voce predefinita è ricavata dalle dimensioni finanziarie del conto. (Inizialmente era stata immessa per impostazione predefinita dall'intestazione del giornale di registrazione).
- **DEPARTMENT:** 024 - La voce predefinita è ricavata dalle dimensioni finanziarie del conto. (Inizialmente era stata immessa per impostazione predefinita dall'intestazione del giornale di registrazione).
- **COSTCENTER:** 007 - La voce predefinita è ricavata dalle dimensioni finanziarie del conto. (Inizialmente era stata immessa per impostazione predefinita dal cliente).

### <a name="scenario-3"></a>Scenario 3

Nello stesso giornale di registrazione utilizzato per lo scenario 2, aggiungere una nuova riga. Nel campo **Tipo di conto**, selezionare **Contabilità generale**, quindi, nel campo **Conto**, immettere **170150**. Cancellare i valori di dimensione predefiniti in modo che rimanga solo il conto principale 170150. Nel campo **Tipo di conto di contropartita**, selezionare **Cliente**, quindi, nel campo **Conto di contropartita**, immettere **US-001**. Vengono immesse le seguenti voci predefinite per i valori di dimensione finanziaria:

- **BUSINESSUNIT:** 002 - La voce predefinita è ricavata dall'intestazione del giornale di registrazione, perché il valore di dimensione Conto è vuoto. Il valore **001** non è inserito per impostazione predefinita dal cliente US-001, perché un valore predefinito è stato già ricavato dall'intestazione del giornale di registrazione. Se il valore **BUSINESSUNIT** è stato lasciato intenzionalmente vuoto, è necessario rimuovere anche la dimensione finanziaria nel conto di contropartita.
- **COSTCENTER:** 007 - La voce predefinita è ricavata dal cliente US-001, perché il valore di dimensione Conto e il valore di dimensione dell'intestazione del giornale di registrazione sono vuoti. Se il valore **COSTCENTER** è stato lasciato intenzionalmente vuoto, è necessario rimuovere anche la dimensione finanziaria nel conto di contropartita.
- **DEPARTMENT:** 024 - La voce predefinita è ricavata dall'intestazione del giornale di registrazione, perché il valore di dimensione Conto è vuoto. Se il valore **DEPARTMENT** è stato lasciato intenzionalmente vuoto, è necessario rimuovere anche la dimensione finanziaria nel conto di contropartita.

### <a name="scenario-4"></a>Scenario 4

Utilizzare gli stessi valori di dimensione finanziaria predefiniti definiti per il nome del giornale di registrazione e il cliente negli scenari 1 e 2. Quindi, definire un valore di dimensione fissa per la dimensione **BUSINESSUNIT** sul conto principale 170150. Andare a **Contabilità generale \> Piano dei conti \> Conti \> Conti principali**. Nel campo **Conto principale**, selezionare **170150**, quindi, sulla scheda **Sostituzioni entità giuridica**, selezionare **Aggiungi**. Selezionare **USMF** come persona giuridica, quindi **Aggiungi**. Selezionare tale record, quindi **Dimensioni predefinite**. Modificare la dimensione **BUSINESSUNIT** in **Valore fisso**, quindi inserire come valore **003**.

Crea un nuovo giornale di registrazione generale che utilizzi il nome del giornale di registrazione **GenJrn**. Sulla scheda **Dimensioni finanziarie**, rimuovere tutti i valori di dimensione predefiniti.

Andare a **Righe**. Nel campo **Tipo di conto**, selezionare **Contabilità generale**, quindi, nel campo **Conto**, immettere **170150**. Quindi, selezionare il tasto **Tab** per uscire dal campo. I valori di dimensione vengono immessi per impostazione predefinita dall'impostazione del conto principale per il conto 170150. Quindi, il valore **Conto** è mostrato come **170150-003-**.

Modificare il valore **Conto** in **170150-004-**. **La funzionalità giornale di registrazione non impedisce la modifica di un valore di dimensione fissa.** Immettere un importo a debito o a credito. Nel campo **Tipo di conto di contropartita**, selezionare **Contabilità generale**, quindi, nel campo **Conto di contropartita**, immettere **170250**. Il valore di dimensione finanziaria 004 viene immesso come impostazione predefinita dal conto. Quindi, registrare il documento. Nel giornale di registrazione, selezionare **Giustificativo**. Notare che il valore **BUSINESSUNIT** è stato ripristinato al valore di dimensione fissa, **003**, durante la registrazione.

Quando si torna al giustificativo sul giornale di registrazione, la dimensione **BUSINESSUNIT** **non** riflette il valore di dimensione fissa. Ha sempre il valore che è stato mostrato sulla schermata prima della registrazione. Il processo di registrazione non modifica nulla di quanto inserito nel giustificativo. Durante la registrazione viene modificata solo la voce contabile.

## <a name="developer-notes"></a>Note per lo sviluppatore

Se si opera nel ruolo di sviluppatore e si desidera esaminare il codice per il processo predefinito, fare riferimento ai seguenti metodi:

- **LedgerJournalEngine.accountModified()** - Questo metodo è il punto di immissione principale per il processo predefinito della dimensione del conto principale che è standard per tutti i giornali di registrazione (e viene sostituito da alcuni tipi di giornale di registrazione).
- **LedgerJournalEngine.offsetAccountModified()** - Questo metodo è il punto di immissione principale per il processo predefinito della dimensione del conto di contropartita.
