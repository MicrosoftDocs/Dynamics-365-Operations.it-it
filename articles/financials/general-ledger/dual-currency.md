---
title: Doppia valuta
description: In questo argomento vengono fornite informazioni sulla doppia valuta, dove la valuta di dichiarazione viene utilizzata come seconda valuta di contabilizzazione per Microsoft Dynamics 365 for Finance and Operations.
author: kweekley
manager: AnnBe
ms.date: 05/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: dfd4c116552510ee42cd2f3e8a0f31100826b9d2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839403"
---
# <a name="dual-currency"></a>Doppia valuta

[!include [banner](../includes/banner.md)]

La funzionalità che è stata introdotta in Microsoft Dynamics 365 for Finance and Operations versione 8.1 (ottobre 2018) consente di ridestinare e utilizzare la valuta di dichiarazione come seconda valuta di contabilizzazione. Questa funzionalità viene talvolta definita *valuta doppia*. Le modifiche per valuta doppia non possono essere disabilitate tramite una chiave di configurazione o un parametro. Poiché la valuta di dichiarazione viene utilizzata come seconda valuta di contabilizzazione, la modalità in cui la valuta di dichiarazione viene calcolata nella logica di registrazione è cambiata.

Inoltre, alcuni moduli sono stati aggiornati a scopo di traccia, report e utilizzo della valuta di dichiarazione nei diversi processi. I moduli interessati sono **Contabilità generale**, **Creazione di report finanziari**, **Contabilità fornitori**, **Contabilità clienti**, **Gestione cassa e banche** e **Cespiti**. Dopo un aggiornamento, è necessario completare passaggi specifici per Gestione cassa e banche e Cespiti. Di conseguenza, assicurarsi di leggere attentamente le aree pertinenti di questo argomento.

## <a name="posting-process"></a>Processo di registrazione

La logica di registrazione è stata modificata per tutte le transazioni che generano una voce contabile nella contabilità generale. Ecco come la valuta di dichiarazione è stata precedentemente calcolata:

Importo valuta transazione \> Importo valuta contabilizzazione \> Importo valuta dichiarazione

Ad esempio, una transazione viene immessa nella valuta dollaro canadese (CAD). L'importo in CAD viene convertito nella valuta di contabilizzazione, ovvero dollaro statunitense (USD). L'importo in USD viene convertito nella valuta di dichiarazione, ovvero euro (EUR). Di conseguenza, i tassi di cambio devono essere presenti tra CAD e USD e tra USD e EUR.

Ecco il nuovo calcolo:

Importo valuta transazione \> Importo valuta contabilizzazione

Importo valuta transazione \> Importo valuta dichiarazione

A causa di questa modifica, i tassi di cambio devono ora essere presenti tra CAD e USD e tra CAD e EUR.

## <a name="reports-and-inquiries"></a>Report e richieste di informazioni

I vari report e richieste di informazioni ora mostrano sia gli importi in valuta di dichiarazione che gli importi in valuta di contabilizzazione. Non ogni report e richiesta di informazioni è stato aggiornato. Ad esempio, i report che mostrano importi solo nella valuta di transazione non sono cambiati.

Le modifiche seguono uno di due criteri:

- Se il report o la richiesta di informazioni aveva disponibile spazio per visualizzare gli importi sia nella valuta di contabilizzazione sia nella valuta di dichiarazione, gli importi della valuta di dichiarazione sono stati aggiunti.
- Se il report o la richiesta di informazioni non aveva disponibile spazio per visualizzare gli importi in entrambe le valute, un'opzione è stata aggiunta in modo che gli utenti possono selezionare quale valuta viene visualizzata.

Per alcuni report e richieste di informazioni, è stata anche aggiunta logica per omettere gli importi nella valuta di dichiarazione se la valuta di dichiarazione corrisponde alla valuta di contabilizzazione, o se la valuta di dichiarazione non è stata definita nella contabilità generale della persona giuridica.

## <a name="financial-journals"></a>Giornali di registrazione finanziari

I giornali di registrazione finanziari, ad esempio il giornale di registrazione generale e il giornale di registrazione fatture fornitore, sono stati aggiornati in modo da comprendessero informazioni aggiuntive sulla valuta di dichiarazione. I totali relativi al giustificativo e il giornale di registrazione sono ora visualizzati nella valuta di dichiarazione. Inoltre, le informazioni sul tasso di cambio della valuta di dichiarazione sono ora visualizzate nella scheda **Generale** delle righe del giornale di registrazione. Di conseguenza, è possibile ignorare il tasso di cambio della valuta di dichiarazione quando si immettono transazioni.

## <a name="vendor-invoices-sales-orders-and-sales-agreements"></a>Fatture fornitore, ordini cliente e contratti di vendita
Le fatture fornitore, ordini cliente e i contratti di vendita sono stati aggiornati per includere un tasso di cambio fisso per la valuta di dichiarazione. È possibile definire un tasso di cambio fisso sia per la valuta di contabilizzazione che per la valuta di dichiarazione quando la valuta della transazione è diversa. Quando la valuta di contabilizzazione e la valuta di dichiarazione sono uguali, il tasso di cambio fisso verrà mantenuto sincronizzato utilizzando il tasso fisso della valuta di contabilizzazione come tasso fisso della valuta di dichiarazione. Il tasso di cambio fisso della valuta di dichiarazione non può essere modificato per questa configurazione. Quando la valuta di contabilizzazione e la valuta di dichiarazione sono diverse, è possibile definire un tasso di cambio fisso sia per la valuta di contabilizzazione che per la valuta di dichiarazione durante l'immissione della transazione. Se la valuta di dichiarazione non è stata definita nella contabilità generale, il campo **Tasso di cambio fisso della valuta di dichiarazione** non è disponibile e nessun importo nella valuta di dichiarazione viene calcolato.

## <a name="module-changes"></a>Modifiche nei moduli

Di seguito sono elencati i moduli che utilizzano la valuta di dichiarazione come seconda valuta di contabilizzazione:

- [Contabilità generale](#general-ledger)
- [Creazione di report finanziari](#financial-reporting)
- [Contabilità fornitori](#accounts-payable-and-accounts-receivable)
- [Contabilità clienti](#accounts-payable-and-accounts-receivable)
- [Gestione cassa e banche](#cash-and-bank-management)
- [Cespiti](#fixed-assets)

### <a name="general-ledger"></a>Contabilità generale

Se una valuta di dichiarazione era definita nella contabilità generale, la contabilità generale già teneva traccia degli importi in valuta di dichiarazione per ciascuna voce contabile. Tuttavia, questi importi verranno ora convertiti in base agli importi in valuta della transazione.

Le seguenti modifiche aggiuntive sono state effettuate nel modulo **Contabilità generale**:

- Un tipo di tasso di cambio separato per la valuta di dichiarazione può essere definito nella contabilità generale. Se un'organizzazione non desidera utilizzare un altro tipo di tasso di cambio, è possibile lasciare vuoto il campo per il tipo di tasso di cambio della valuta di dichiarazione. In alternativa, è possibile selezionare lo stesso tipo di tasso di cambio utilizzato per la valuta di contabilizzazione. Se si lascia il campo vuoto, verrà utilizzato il tipo di tasso di cambio per la valuta di contabilizzazione.
- Un nuovo giornale di registrazione, il giornale di registrazione rettifiche valuta di dichiarazione, consente di registrare rettifiche nei conti CoGe solo nella valuta di dichiarazione. Questo giornale di registrazione consente la registrazione solo nei conti CoGe. Non supporta la registrazione interaziendalw e la valuta deve essere la valuta di dichiarazione della persona giuridica in cui viene registrato il giornale. Quando il giornale viene registrato, gli importi in valuta della transazione e valuta di contabilizzazione sono 0 (zero) e l'importo della valuta di dichiarazione viene registrato con l'importo immesso nella transazione. Poiché il modo in cui la valuta di dichiarazione viene utilizzata nei moduli **Contabilità fornitori**, **Contabilità clienti** e **Cespiti** è cambiato, questo giornale di registrazione può essere utilizzato per le rettifiche dopo un aggiornamento. Per alcuni esempi relativi a come il giornale di registrazione può essere utilizzato, vedere le sezioni di questi moduli.
- Il processo per l'allocazione per periodo è stato aggiornato in modo da allocare gli importi nelle valute di transazione, contabilizzazione e dichiarazione. In precedenza, gli importi erano allocati nelle valute di transazione e contabilizzazione e quindi l'importo nella valuta di contabilizzazione veniva convertito nella valuta di dichiarazione. Questo comportamento poteva determinare che un saldo rimanesse nel conto CoGe nella valuta di dichiarazione. Ora, quando gli importi vengono calcolati e utilizzati nella voce contabile, non viene eseguita alcuna conversione.
- Il processo per la rivalutazione valuta estera già ha rivalutato gli importi nella valuta di dichiarazione. Tuttavia, l'importo della valuta di dichiarazione viene ora calcolato tramite l'importo in valuta della transazione, come descritto nella sezione [Processo di registrazione](#posting-process) in precedenza in questo argomento.
- Molti report e richieste di informazioni nella contabilità generale già avevano la valuta di dichiarazione, ma alcuni no. Un esempio è la pagina elenco **Bilancio di verifica**. Questa pagina elenco ora include le colonne sia per la valuta di contabilizzazione sia per la valuta di dichiarazione. Tenere presente che le colonne per la valuta di dichiarazione vengono nascoste se la valuta di contabilizzazione e la valuta di dichiarazione sono uguali, o se la valuta di dichiarazione non è stata definita nella contabilità generale.

### <a name="financial-reporting"></a>Creazione di report finanziari

Un aggiornamento nel modulo **Creazione di report finanziari** consente di includere gli importi della valuta di dichiarazione in un rendiconto finanziario in due modi. Nella definizione di colonna, è possibile dichiarare direttamente gli importi nella valuta di dichiarazione registrati nella contabilità generale (nuova funzionalità). In alternativa, è possibile continuare a convertire gli importi della valuta di contabilizzazione alla valuta di dichiarazione (funzionalità esistente).

Questa modifica è disponibile tramite l'impostazione **Valuta visualizzata** nella definizione di colonna. Se si seleziona **Valuta per i report da Contabilità generale**, gli importi della colonna non vengono convertiti. Invece, vengono dichiarati direttamente dalla contabilità generale. Se si desidera che la colonna visualizzare gli importi convertiti, selezionare **Converti in XXXX**, dove *XXXX* è la valuta di dichiarazione che la colonna deve visualizzare. In questo caso, gli importi in valuta di contabilizzazione verranno convertiti nella valuta selezionata utilizzando le funzionalità esistenti di conversione.

### <a name="accounts-payable-and-accounts-receivable"></a>Contabilità fornitori e Contabilità clienti

I moduli **Contabilità fornitori** e **Contabilità clienti** già tenevano traccia degli importi nella valuta di dichiarazione. Tuttavia, gli importi non venivano visualizzati o utilizzati per diversi processi. Sono state apportate le seguenti modifiche:

- Gli importi in valuta di dichiarazione vengono ora visualizzati nelle transazioni per clienti e fornitori. Gli importi della valuta di dichiarazione vengono anche visualizzati per il saldo di apertura di ciascuna transazione.
- Il processo di aging è stato aggiornato in modo che un'organizzazione può visualizzare gli intervalli di aging nella valuta di contabilizzazione o nella valuta di dichiarazione.
- Varie richieste di informazioni e report sono stati aggiornati in modo da mostrare gli importi nella valuta di dichiarazione. Gli esempi includono i report **Riconciliazione cliente/saldi contabili** e **Riconciliazione saldi contabili/fornitore**.
- Il processo per la rivalutazione valuta estera già ha rivalutato gli importi nella valuta di dichiarazione. Tuttavia, l'importo in valuta di dichiarazione viene ora calcolato tramite l'importo in valuta della transazione, come descritto nella sezione [Processo di registrazione](#posting-process).
- **Considerazioni sull'aggiornamento:** Prima di un aggiornamento, gli importi nella valuta di dichiarazione dei documenti (fatture, pagamenti, e così via) sono calcolati tramite la valuta di contabilizzazione. Ad esempio, una fattura viene registrata prima degll'aggiornamento di un'organizzazione e non viene pagata. Durante l'aggiornamento, la voce contabile della fattura rimarrà invariata. Tuttavia, dopo l'aggiornamento, le modifiche per la doppia valuta doppia saranno attive. Pertanto, quando viene effettuato un pagamento per la fattura, l'importo nella valuta di dichiarazione del pagamento verrà calcolato in base all'importo in valuta della transazione. Quando il pagamento e la fattura vengono liquidati, una leggera differenza può essere calcolata nell'importo di profitto o perdita realizzata, poiché gli importi nella valuta di dichiarazione vengono ora calcolati in modo diverso. Se la differenza calcolata viene considerata significativa, il nuovo giornale di registrazione rettifiche di valuta di dichiarazione può essere utilizzato per rettificare il saldo del profitto/perdita realizzata e dei conti CoGe di Contabilità clienti e Contabilità fornitori solo nella valuta di dichiarazione.

### <a name="cash-and-bank-management"></a>Gestione cassa e banche

In precedenza, il modulo **Gestione cassa e banche** non teneva traccia degli importi nella valuta di dichiarazione per le transazioni registrate per ciascun conto bancario. Dopo un aggiornamento, importi nella valuta di dichiarazione sono automaticamente registrati per le nuove transazioni registrate. Tuttavia, gli importi nella valuta di dichiarazione devono essere aggiunti alle transazioni precedentemente registrate nella contabilità secondaria.

- **Considerazioni sull'aggiornamento:** Poiché le transazioni del conto bancario in precedenza non tenevano traccia degli importi nella valuta di dichiarazione nella contabilità secondaria, una procedura guidata è stata aggiunta che consente di aggiungere gli importi nella valuta di dichiarazione alle transazioni del conto bancario. Questa procedura guidata **non** registra nuovamente nella contabilità generale. Invece, prende gli importi nella valuta di dichiarazione dalla contabilità generale e li aggiorna nelle tabelle della contabilità secondaria.

    - Per avviare la procedura guidata, selezionare **Gestione cassa e banche** \> **Impostazione** \> **Aggiungi importi in valuta di dichiarazione a transazioni conto bancario**.
    - La procedura guidata visualizza le transazioni per tutti i conti bancari della società corrente con un importo in valuta di dichiarazione di 0 (zero). Solo le transazioni registrate prima del'aggiornamento sono incluse.
    - Per ciascuna transazione di conto bancario, la procedura guidata consente di individuare le voci contabili corrispondenti nella contabilità generale e immettere un importo nella valuta di dichiarazione predefinita. Sebbene gli importi possano essere modificato, si consiglia di **non** modificarli. In caso contrario, potrebbe non essere possibile riconciliare i saldi del conto bancario nella contabilità generale. L'unica volta che è necessario modificare un importo è se l'importo nella valuta di dichiarazione non viene trovato nella contabilità generale. In questo caso, la procedura guidata visualizzerà un importo pari a 0 (zero) per la valuta di dichiarazione.
    - Se si seleziona **Annulla** nella procedura guidata, le transazioni del conto bancario e le eventuali modifiche agli importi in valuta di dichiarazione verranno salvate fino al successiva esecuzione della procedura guidata. Tuttavia, gli importi in valuta di dichiarazione non vengono aggiornati per le transazioni di conto bancario. Quell'aggiornamento viene eseguito soltanto quando si seleziona **Fine** nella procedura guidata. È possibile eseguire più volte la procedura guidata. Di conseguenza, è possibile correggere eventuali importi in valuta di dichiarazione incorretti se si esegue un errore.

- Nessun processo in Gestione cassa e banche è stato modificato, ma alcuni report e richieste di informazioni sono stati aggiornati in modo che mostrassero gli importi nella valuta di dichiarazione. I report delle previsioni di cassa sono un'eccezione. Non sono stati aggiornati per includere gli importi in valuta di dichiarazione.

### <a name="fixed-assets"></a>Cespiti

In precedenza, il modulo **Cespiti** non teneva traccia degli importi nella valuta di dichiarazione per le transazioni registrate per ciascun libro cespiti. Dopo un aggiornamento, importi nella valuta di dichiarazione sono automaticamente registrati per le nuove transazioni registrate. Tuttavia, gli importi nella valuta di dichiarazione devono essere aggiunti alle transazioni precedentemente registrate nella contabilità secondaria.

Inoltre, le modifiche principali sono stati effettuate al processo di ammortamento. Le modifiche richiedono l'azione dell'utente dopo un aggiornamento. È importante aver letto e compreso le seguenti modifiche, anche se non si utilizza ancora il modulo Cespiti.

- Il modo in cui il processo di ammortamento determina l'importo in valuta di dichiarazione è cambiato. Il seguente scenario confronta come l'ammortamento in precedenza ha determinato l'importo in valuta di dichiarazione e come ora determina l'importo in valuta di dichiarazione.

    **Scenario di ammortamento**

    Un cespite viene acquisito e registrato con gli importi seguenti. Tenere presente che l'importo in valuta di dichiarazione viene registrato nella contabilità generale, ma non viene archiviato nelle tabelle del giornale di registrazione secondario del cespite.

    | Tipo di transazione | Importo transazione | Tasso di cambio | Importo in valuta di contabilizzazione | Tasso di cambio | Importo in valuta di dichiarazione |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Acquisizione      | 1.000.000 DKK      | 2.0           | 500.000 USD                | 2,5           | 200.000 EUR               |

    **Ammortamento precedente per la valuta di dichiarazione**

    A fine anno, la proposta di ammortamento verrà eseguita e vengono calcolati i seguenti importi.

    | Tipo di transazione | Importo transazione | Tasso di cambio | Importo in valuta di contabilizzazione | Tasso di cambio | Importo in valuta di dichiarazione |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Ammortamento     | 50.000 USD         | 1.0           | 50.000 USD                 | 2.6           | 19.230,77 EUR             |

    Quando la proposta di ammortamento verrà eseguita, calcola l'importo nella valuta di contabilizzazione utilizzando il metodo di ammortamento. Quindi converte l'importo nella valuta di dichiarazione utilizzando il tasso di cambio corrente tra USD e EUR. La conversione determina problemi, poiché il cespite non può essere ammortizzato completamente nella valuta di dichiarazione quando si usa la tariffa corrente.

    **Nuovo ammortamento per la valuta di dichiarazione**

    Il processo di ammortamento è stato modificato in modo che l'importo in valuta di dichiarazione viene anche calcolato utilizzando il metodo di ammortamento. Di seguito vengono riportati i risultati dell'ammortamento eseguito sul cespite.

    | Tipo di transazione | Importo transazione | Tasso di cambio | Importo in valuta di contabilizzazione | Tasso di cambio                                                       | Importo in valuta di dichiarazione |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | Ammortamento     | 50.000 USD         | 1.0           | 50.000 USD                 | 2,5<blockquote>[!NOTE] Sebbene questo tasso di cambio viene visualizzato, non viene utilizzato per convertire la valuta di dichiarazione.</blockquote> | 20.000 EUR                |

    Quando la proposta di ammortamento verrà eseguita, calcola l'importo nella valuta di contabilizzazione e l'importo nella valuta di dichiarazione utilizzando il metodo di ammortamento. Gli importi vengono quindi utilizzati per la voce contabile nella contabilità generale. Nessuna conversione verrà effettuata per determinare l'importo in valuta di dichiarazione.

- **Considerazioni sull'aggiornamento:** Poiché le transazioni del libro cespiti in precedenza non tenevano della valuta di dichiarazione, una procedura guidata è stata aggiunta che consente di aggiungere gli importi nella valuta di dichiarazione alle transazioni del libro cespiti. Questa procedura guidata **non** registra nuovamente nella contabilità generale. Poiché la modalità in cui la proposta di ammortamento calcola gli importi nella valuta di dichiarazione è cambiata, la procedura guidata **deve** essere eseguita e completato per ogni società prima che un'organizzazione può immettere qualsiasi transazione di ammortamento.

    - Per avviare la procedura guidata, selezionare **Cespiti** \> **Impostazione** \> **Aggiungi importi in valuta di dichiarazione a libri cespiti**.
    - La procedura guidata visualizza le transazioni per tutti i libri cespiti della società corrente con un importo in valuta di dichiarazione di 0 (zero). Solo le transazioni registrate prima del'aggiornamento sono incluse.
    - La procedura guidata **non** estrae gli importi in valuta di dichiarazione dalla contabilità generale. Come descritto è stato nello scenario precedente, gli importi in valuta di dichiarazione originariamente registrati nella contabilità generale hanno utilizzo in modo errato la tariffa corrente. Quegli importi non da visualizzare nel giornale di registrazione secondario del cespite, in quanto il calcolo successivo di ammortamento utilizzerà gli importi non corretti. Invece, la procedura guidata trova il tasso di cambio alla data della prima acquisizione. Quindi utilizza quel tasso di cambio per consigliare l'importo in valuta di dichiarazione che deve essere registrato nella contabilità secondaria. Ad esempio, ecco cosa la procedura guidata può visualizzare per lo scenario precedente.

        | Cespite | Prenota      | Tipo di transazione | Data della transazione | Valuta | Importo in valuta di transazione | Periodo  | Tasso di cambio | Importo in valuta di dichiarazione |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_SLLT | Acquisizione      | 6/3/2016         | DKK      | 1.000.000                      | 500,000 | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Ammortamento     | 6/3/2016         | DKK      | 50.000                         | 50.000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Ammortamento     | 6/3/2016         | DKK      | 50.000                         | 50.000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Ammortamento     | 6/3/2016         | DKK      | 50.000                         | 50.000  | 2,5       | 250,000                   |

    - Molti clienti hanno tenuto traccia dei dettagli delle transazioni cespiti in cartelle di lavoro. Queste informazioni includono i tassi di cambio e importi. Se si dispone di questi dati in una cartella di lavoro, è possibile creare un tipo di tasso di cambio personalizzato e aggiornarlo con i tassi di cambio della cartella di lavoro. Questo tipo di tasso di cambio verrà utilizzato per registrare un tasso di cambio predefinito alla data di acquisizione e per calcolare l'importo in valuta di dichiarazione. Se non si seleziona un tipo di tasso di cambio, la procedura guidata utilizza il tipo di tasso di cambio definito nella contabilità generale.
    - Non è possibile modificare il tasso di cambio e gli importi in valuta di dichiarazione. Se il tasso di cambio viene modificato, l'importo in valuta di dichiarazione viene ricalcolato utilizzando il nuovo tasso.
    - Se si seleziona **Annulla** nella procedura guidata, le transazioni del libro cespiti e le eventuali modifiche al tasso di cambio o agli importi in valuta di dichiarazione verranno salvate fino al successiva esecuzione della procedura guidata. Tuttavia, gli importi in valuta di dichiarazione non vengono aggiornati per le transazioni del libro cespiti. Quell'aggiornamento viene eseguito soltanto quando si seleziona **Fine** nella procedura guidata. È possibile eseguire più volte la procedura guidata. Di conseguenza, è possibile correggere eventuali importi in valuta di dichiarazione incorretti se si esegue un errore.
    - Quando gli importi in valuta di dichiarazione sono completamente aggiornati nella contabilità secondaria, **è necessario** impostare l'opzione **Sono stati aggiornati tutti gli importi in valuta di dichiarazione nelle transazioni dei libri cespiti?** su **Sì** e quindi selezionare **Fine**. I calcoli di ammortamento non possono essere completati finché non impostare l'opzione **Sono stati aggiornati tutti gli importi in valuta di dichiarazione nelle transazioni dei libri cespiti?** su **Sì**. Dopo aver impostato l'opzione su **Sì**, la procedura guidata non è più disponibile.
    - Dopo che le transazioni dei cespiti nella contabilità secondaria vengono aggiornate con importi in valuta di dichiarazione, gli importi non corrisponderanno agli importi originariamente registrati nella contabilità generale. Tuttavia, il giornale di registrazione rettifiche valuta di dichiarazione può essere utilizzato per aggiornare i saldi dei conti CoGe di ammortamento in contabilità generale, in modo che corrispondano agli importi originariamente registrati.
    - Una nuova entità **Importi in valuta di dichiarazione transazioni cespiti** che è stata aggiunta all'area di lavoro **Gestione dati** consente di esportare i dati dalla procedura guidata. È quindi possibile utilizzare i dati per determinare il saldo nel giornale di registrazione secondario del cespite per le transazioni di ammortamento. Il saldo può quindi essere utilizzato per determinare l'importo della rettifica in valuta di dichiarazione nella contabilità generale.

- **Considerazione sull'aggiornamento:** Nuovi campi di impostazione sono stati aggiunti ai cespiti e vengono utilizzati per il calcolo di ammortamento. Potrebbe essere necessario aggiornare questi campi prima del calcolo successivo di ammortamento.

    - Nel libro cespiti (**Cespiti** \> **Libri**), la scheda dettaglio **Generale** ha un nuovo campo **Prezzo di acquisizione in valuta di dichiarazione**.
    - Nel libro cespiti (**Cespiti** \> **Libri**), la scheda dettaglio **Ammortamento** ha un nuovo campo **Valore di recupero atteso in valuta di dichiarazione**.
    - Nei parametri Cespiti (**Cespiti** \> **Impostazione** \> **Parametri Cespiti**), la scheda dettaglio **Generale** ha un nuovo campo **Importo minimo di ammortamento in valuta di dichiarazione**.
    - Nei libri (**Cespiti** \> **Impostazione** \> **Libri**), la scheda dettaglio **Generale** ha due nuovi campi: **Arrotonda ammortamento in valuta di dichiarazione** e **Lascia valore contabile netto sulla valuta di dichiarazione**.

- Poiché la proposta di ammortamento ora calcola gli importi sia nella valuta di contabilizzazione che nella valuta di dichiarazione, il giornale di registrazione cespiti è stato aggiornato in modo che mostrasse gli importi di ammortamento nella valuta di dichiarazione. Per le transazioni di ammortamento, la valuta della transazione è sempre la valuta di contabilizzazione. Di conseguenza, questi importi continueranno a apparire nelle colonne **Dare** e **Avere**. Due nuove colonne, **Dare in valuta di dichiarazione** e **Avere in valuta di dichiarazione**, sono state aggiunte alla griglia.

    - I nuovi campi sono disponibili solo quando il tipo di transazione è uno dei quattro tipi di ammortamento: **Ammortamento**, **Rettifica ammortamento**, **Ammortamento straordinario** o **Fondo di ammortamento speciale**.
    - Se il tipo di transazione di ammortamento viene immesso nel giornale di registrazione cespiti, gli importi in valuta di dichiarazione appaiono nelle nuove colonne. Quegli importi possono essere modificati.
    - Se la valuta di contabilizzazione e le valute di dichiarazione per la contabilità generale sono uguali, gli importi verranno mantenuti in sincronizzazione. Se si modifica l'importo **Avere**, l'importo **Avere in valuta di dichiarazione** verrà modificato automaticamente in modo da corrispondere.
    - Se qualsiasi altro tipo di transazione viene immesso nel giornale di registrazione cespiti, gli importi **Dare in valuta di dichiarazione** e **Avere in valuta di dichiarazione** non vengono mai visualizzati, prima o dopo la registrazione. Gli importi in valuta di contabilizzazione e in valuta di dichiarazione sono comunque disponibili sul giustificativo registrato nella contabilità generale.
