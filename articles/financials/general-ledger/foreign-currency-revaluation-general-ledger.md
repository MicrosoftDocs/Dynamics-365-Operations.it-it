---
title: Rivalutazione valuta estera per contabilità generale
description: 'In questo argomento viene fornita una panoramica delle seguenti operazioni relative al processo di rivalutazione valuta estera della contabilità generale: impostazione, esecuzione del processo, calcolo per il processo e lo storno di transazioni di rivalutazione, se necessario.'
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bf61aa839d4d59b2c93eee9931eef0e6c51d4ac
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839307"
---
# <a name="foreign-currency-revaluation-for-general-ledger"></a>Rivalutazione valuta estera per contabilità generale

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica delle seguenti operazioni relative al processo di rivalutazione valuta estera della contabilità generale: impostazione, esecuzione del processo, calcolo per il processo e lo storno di transazioni di rivalutazione, se necessario. 

Nell'ambito di una fine periodo le convenzioni di contabilità richiedono che i saldi dei conti di registrazione contabile in valuta estera vengano rivalutati utilizzando diversi tipi di tassi di cambio (corrente, storico, medio e così via). Ad esempio, una convenzione contabile richiede che le attività e le passività vengano rivalutate al tasso di cambio corrente, i cespiti al tasso di cambio storico e i conti profitti e perdite alla media mensile. La rivalutazione valuta estera della contabilità generale può essere utilizzata per rivalutare lo stato patrimoniale e i conti profitti e perdite. 

> [!NOTE]
> La rivalutazione valuta estera è disponibile anche in Contabilità clienti (CoCli) e Contabilità fornitori (CoFor). Se si utilizzano tali moduli, le transazioni arretrate devono essere rivalutate utilizzando la rivalutazione valuta estera nei relativi moduli. La rivalutazione valuta estera di contabilità clienti e contabilità fornitori creerà una voce contabile nella contabilità generale che rifletta la perdita o il profitto non realizzato per assicurare che i giornali di registrazione secondari e la contabilità generale possano essere riconciliati. Poiché la rivalutazione valuta estera di contabilità clienti e contabilità fornitori crea le voci contabili nella contabilità generale, i conti principali contabilità fornitori e contabilità clienti dovrebbero essere esclusi dalla rivalutazione valuta estera della contabilità generale. 

Quando si esegue il processo di rivalutazione, il saldo in ogni conto principale registrato in valuta estera verrà rivalutato. Le transazioni relative alla perdita o al profitto non realizzato create durante il processo di rivalutazione vengono generate dal sistema. È possibile che vengano create due transazioni, una per la valuta di contabilizzazione e una seconda per la valuta di dichiarazione, se pertinente. Ogni voce contabile verrà registrata nella perdita o nel profitto non realizzato e nel conto principale che viene rivalutato.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Preparare l'esecuzione della rivalutazione valuta estera
Prima di effettuare il processo di rivalutazione, è richiesta l'impostazione che segue.

-   Nella pagina **Conto principale**:
-   Se il conto principale deve essere rivalutato in Contabilità generale, selezionare **Rivalutazione valuta estera**. Se il conto principale non deve essere rivalutato (ad esempio per la contabilità clienti e la contabilità fornitori se rivalutato nei giornali di registrazione secondari), deselezionare questa opzione.
-   Se il conto principale è contrassegnato per la rivalutazione, immettere **Tipo di tasso di cambio**. Questo tipo di tasso di cambio verrà utilizzato per la rivalutazione del conto principale. Un campo separato, **Tipo di tasso di cambio report finanziari**, è disponibile per i report finanziari. I due campi non vengono mantenuti nella sincronizzazione, consentendo l'utilizzo di tipi di tasso di cambio diversi per la rivalutazione e i report finanziari.

-   Nella pagina **Contabilità generale**:
-   Specificare **Tipo di tasso di cambio**. Se il tipo di tasso di cambio non è definito nel conto principale, il tipo di tasso di cambio verrà utilizzato durante la rivalutazione valuta estera.
-   Specificare i conti del profitto realizzato, della perdita realizzata, del profitto non realizzato e della perdita non realizzata per la rivalutazione valuta. I conti della perdita e del profitto realizzati vengono utilizzati quando vengono compensate le transazioni di contabilità clienti e contabilità fornitori e i conti di perdita e di profitto non realizzati vengono utilizzati per la rivalutazione di transazioni aperte e di conti principali di contabilità generale.

-   Nella pagina **Conti rivalutazione valuta**:
-   Selezionare conti di rivalutazione valuta diversi per ciascuna valuta e società. Se non vengono definiti, vengono utilizzati i conti della pagina **Contabilità generale**.

## <a name="process-foreign-currency-revaluation"></a>Elaborare una rivalutazione valuta estera
Una volta completata l'impostazione, utilizzare la pagina **Rivalutazione valuta estera** per rivalutare i saldi dei conti principali. È possibile eseguire il processo in tempo reale o programmarne l'esecuzione utilizzando un batch. 

Nella pagina **Rivalutazione valuta estera** verrà visualizzata la cronologia di ogni processo di rivalutazione, tra cui la data di esecuzione del processo, i criteri definiti, un collegamento al giustificativo creato per la rivalutazione e un record qualora una rivalutazione precedente sia stata stornata. Per eseguire il processo di rivalutazione, selezionare il pulsante **Rivalutazione valuta estera**. 

I valori **Data iniziale** e **Data finale** definiscono l'intervallo di date per il calcolo del saldo in valuta estera che verrà rivalutato. Quando si rivalutano i conti profitti e perdite, la somma di tutte le transazioni che vengono eseguite nell'intervallo di date viene rivalutata. Quando si rivalutano i conti dello stato patrimoniale, l'opzione Data iniziale viene ignorata. In tal caso, il saldo da rivalutare previsto è determinato dall'inizio dell'anno fiscale fino alla data di fine. 

La **Data del tasso** può essere utilizzata per definire la data per cui il tasso di cambio debba essere utilizzato per impostazione predefinita. Ad esempio, è possibile rivalutare i saldi tra l'intervallo di date dal 1° gennaio al 31 gennaio, ma utilizzare il tasso di cambio definito per il 1° febbraio. 

Selezionare i conti principali da rivalutare: Tutti, Stato patrimoniale o Profitti e perdite. Solo i conti principali contrassegnati per la rivalutazione (nella pagina Conto principale) verranno rivalutati. Se si desidera limitare ulteriormente l'intervallo di conti principali, utilizzare la scheda **Record da includere** per definire un intervallo di conti principali o singoli conti principali. 

Il processo di rivalutazione può essere eseguito per una o più persone giuridiche. La ricerca mostrerà solo le persone giuridiche a cui si ha accesso. Selezionare le persone giuridiche per cui si desidera eseguire il processo di rivalutazione. 

La rivalutazione può essere eseguita per una o più valute estere. La ricerca includerà tutte le valute registrate nell'intervallo di date relativo al tipo di conto principale (Stato patrimoniale o Profitti e perdite), per le persone giuridiche selezionate da rivalutare. La valuta di contabilizzazione sarà inclusa nell'elenco, ma non verrà rivalutato alcun elemento se la valuta di contabilizzazione è selezionata. 

Impostare **Visualizza anteprima prima della registrazione** su **Sì** se si desidera esaminare il risultato della rivalutazione della contabilità generale. L'anteprima nella contabilità generale è diversa dalla simulazione nella rivalutazione valuta estera di Contabilità clienti e Contabilità fornitori. La simulazione in Contabilità clienti e Contabilità fornitori è un report, ma la contabilità generale dispone di un'anteprima che può essere registrata, senza dover eseguire nuovamente il processo di rivalutazione. I risultati dell'anteprima possono essere esportati in Microsoft Excel per mantenere lo storico di come sono stati calcolati gli importi. Non è possibile utilizzare l'elaborazione batch se si desidera visualizzare l'anteprima dei risultati della rivalutazione. Nell'anteprima l'utente ha la possibilità di registrare i risultati di tutte le persone giuridiche che utilizzano il pulsante **Registra**. Se è presente un problema con i risultati relativi a una persona giuridica, l'utente ha anche la possibilità di registrare un sottoinsieme delle persone giuridiche utilizzando il pulsante **Seleziona persone giuridiche da registrare**. 

Al completamento del processo di rivalutazione valuta estera, verrà creato un record per tenere traccia dello storico di ciascuna esecuzione.  Un record separato verrà creato per ogni persona giuridica e livello di registrazione.

## <a name="calculate-unrealized-gainloss"></a>Calcolare perdita o profitto non realizzato
Le transazioni perdita o profitto non realizzato vengono create in modo diverso tra la rivalutazione di contabilità generale e il processo di rivalutazione di contabilità clienti e contabilità fornitori. In contabilità clienti e contabilità fornitori la rivalutazione precedente è stata stornata (presupponendo che la transazione non sia stata ancora liquidata) e una nuova transazione di rivalutazione viene creata per la perdita/il profitto non realizzato in base al nuovo tasso di cambio. Ciò accade perché ogni singola transazione viene rivalutata in contabilità clienti e contabilità fornitori. Nella contabilità generale, la rivalutazione precedente non viene stornata. In alternativa, viene creata una transazione per il delta tra il saldo del conto principale, incluso qualsiasi importo di rivalutazione precedente, e il nuovo valore in base al tasso di cambio per la Data del tasso. 

**Esempio** I seguenti saldi sono disponibili per il conto principale 110110.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **Data**   | **Conto CoGe** | **Importo transazione** | **Importo contabile** |
| 20 gennaio | 110110 (Contante)      | 500 EURO (Carta di debito)        | 1000 USD (Carta di debito)      |

Il conto principale viene rivalutato il 31 gennaio.  La perdita/il profitto non realizzato viene calcolato come indicato di seguito.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Saldo corrente in valuta della transazione** | **Saldo corrente in valuta di contabilizzazione** | **Tasso di cambio alla rivalutazione** | **Nuovo importo nella valuta di contabilizzazione** | **Perdita/profitto non realizzato**    |
| 500 EURO                                     | 1000 USD                                   | 166,6667                         | 833,33 EURO (500 x 1,666667)        | Perdita 166,67 (833,33 - 1000) |

Verrà creata la voce contabile che segue.

|            |                          |           |            |
|------------|--------------------------|-----------|------------|
| **Data**   | **Conto CoGe**       | **Dare** | **Avere** |
| 31 gennaio | 110110 (Contante)            |           | 166,67     |
| 31 gennaio | 801400 (Perdita non realizzata) | 166,67    |            |

Nessuna nuova transazione viene registrata per il mese di febbraio.  Il conto principale viene rivalutato il 28 febbraio.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Saldo corrente in valuta della transazione** | **Saldo corrente in valuta di contabilizzazione** | **Tasso di cambio alla rivalutazione** | **Nuovo importo nella valuta di contabilizzazione** | **Perdita/profitto non realizzato**    |
| 500 EURO                                     | 833,33 USD (1000 - 166,67)                 | 250,0000                         | 1250 USD (500 x 2,5)               | Guadagno 416,67 (1250 – 833,33) |

Verrà creata la voce contabile che segue.

|             |                          |           |            |
|-------------|--------------------------|-----------|------------|
| **Data**    | **Conto CoGe**       | **Dare** | **Avere** |
| 28 febbraio | 110110 (Contante)            | 416,67    |            |
| 28 febbraio | 801600 (Profitto non realizzato) |           | 416,67     |

## <a name="reverse-foreign-currency-revaluation"></a>Storno della rivalutazione valuta estera
Per stornare la transazione di rivalutazione, selezionare il pulsante **Transazione di storno** nella pagina **Rivalutazione valuta estera**. Un nuovo record cronologico di rivalutazione valuta estera verrà creato per mantenere un audit trail storico di quando la rivalutazione si è verificata o è stata stornata. 

È possibile stornare i risultati dell'ordine superato di rivalutazione, ma potrebbe essere necessario stornare inoltre una rivalutazione più recente per garantire i saldi corretti per ogni conto principale rivalutato. Gli storni possono verificarsi quando un ordine è superato poiché non è possibile controllare quali conti principali siano rivalutati e con quale frequenza. Ad esempio, un'organizzazione può scegliere di rivalutare i relativi conti principali di cassa su base trimestrale, ma tutti gli altri conti principali su base mensile.



