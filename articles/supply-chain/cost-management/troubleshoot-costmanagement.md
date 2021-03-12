---
title: Risolvere i problemi relativi alla gestione dei costi
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre si lavora con la gestione dei costi.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b8c527e578fee6abfeeade99fba8070365c020bd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983852"
---
# <a name="troubleshoot-cost-management"></a>Risolvere i problemi relativi alla gestione dei costi

Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre si lavora con la gestione dei costi.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>Lacune funzionali tra il valore dell'inventario/i report di aging e le relative versioni di archiviazione

Le funzionalità [archiviazione del report di aging dell'inventario](inventory-aging-report-storage.md) e il [report sull'archiviazione valori di magazzino](inventory-value-report-storage.md) consentono a Supply Chain Management di visualizzare grandi volumi di transazioni di magazzino. In ogni caso, i risultati del report vengono salvati per l'esplorazione e l'esportazione, a differenza delle versioni non di archiviazione di questi report. Tuttavia, alcune funzionalità presenti nelle versioni non di archiviazione di questi report non esistono nelle versioni di archiviazione. Le seguenti sottosezioni riepilogano le differenze e forniscono soluzioni alternative.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>I report di archiviazione non includono i totali parziali, anche se sono abilitati nel layout del report

I totali parziali possono causare problemi durante l'esportazione del risultato, soprattutto se gli utenti modificano la sequenza del record.

Per controllare i subtotali, è possibile esportare il risultato in Microsoft Excel. In alternativa, se si desidera controllare i totali parziali in Supply Chain Management, utilizzare [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitare le funzionalità *Nuovo controllo griglia* e *(Anteprima) Raggruppamento in griglie* che forniscono un modo molto più flessibile per vedere il totale parziale di qualsiasi gruppo per colonna. Per ulteriori informazioni, vedere [Funzionalità di griglia](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md).

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Il report di archiviazione valori di magazzino non supporta le informazioni sul conto di contabilità generale

È possibile eseguire il bilancio di prova per ottenere il saldo dei conti inventario e confrontarlo con il report **Archiviazione valori di magazzino**.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>Gli avvisi o gli errori vengono visualizzati quando si modifica lo stato di un periodo contabile senza chiudere l'inventario

Microsoft ha introdotto le seguenti convalide per evitare problemi causati da un processo di fine periodo errato relativo ai costi. Se viene visualizzato uno dei seguenti messaggi di errore, fare riferimento a [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) per ulteriori informazioni su come risolvere questi problemi.

- Si sta per eseguire un ricalcolo con data %1 (10-02-2019). L'ultimo ricalcolo registrato è stato eseguito in un periodo precedente con una data %2 (20-01-2019). Nessuna esecuzione di chiusura di inventario con data %3 (31-01-2019) corrispondente alla fine del periodo è stata registrata. Ricordarsi di eseguire una chiusura dell'inventario a partire dal %3 (31-01-2019) corrispondente alla fine del periodo. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito.

- Si sta per modificare lo stato del periodo contabile %1 su %2. Nessuna esecuzione di chiusura di inventario con data %3 corrispondente alla fine del periodo è stata registrata. Eseguire una chiusura dell'inventario a partire dal %3 corrispondente alla fine del periodo prima di modificare lo stato. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito. Dichiarato dalla persona giuridica %4. Per il momento si tratta solo di un messaggio informativo, ma in futuro questa azione sarà necessaria.

- La struttura dei conti %1 è stata cambiata. Uno o più conti principali %2 non esistono più. Questi conti principali sono richiesti da %3 con data %4. Aggiungere questi account principali alla struttura dei conti %1 prima di poter riprendere il processo %3. Per il momento si tratta solo di un messaggio informativo, ma in futuro questa azione sarà necessaria.

- Si sta per eseguire una chiusura dell'inventario con data %1 (31-01-2019). Nessuna esecuzione del calcolo dei costi di backflush con data %2 (31-01-2019) corrispondente alla fine del periodo è stata registrata. Eseguire il calcolo dei costi di backflush con data %3 (31-01-2019) corrispondente alla fine del periodo. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito.

- Si sta per eseguire un calcolo dei costi di backflush con data %1 (28-02-2019). L'ultimo calcolo dei costi di backflush registrato è stato eseguito in un periodo precedente con una data %2 (31-01-2019). Nessuna esecuzione di chiusura di inventario con data %3 (31-01-2019) corrispondente alla fine del periodo è stata registrata.
Ricordarsi di eseguire una chiusura dell'inventario a partire dal %3 (31-01-2019) corrispondente alla fine del periodo. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando la chiusura dell'inventario non viene eseguita.

## <a name="inventory-aging-report-discrepancies"></a>Discrepanze report di aging delle scorte

Il **Report di aging delle scorte** mostra valori diversi se visualizzati a dimensioni di stoccaggio diverse (come sito o magazzino). Per ulteriori informazioni sulla logica di reporting, vedere [Esempi e logica del report di aging delle scorte](inventory-aging-report.md).

## <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Si verifica un conflitto di aggiornamento quando il metodo di valutazione dell'inventario è Costo standard o Media mobile

Quando si registrano documenti come giornali di registrazione magazzino, fatture di ordini fornitore o fatture di ordini cliente in parallelo per scalabilità e prestazioni, è possibile che venga visualizzato un messaggio di errore relativo a un conflitto di aggiornamento e alcuni documenti potrebbero non essere registrati. Il problema può verificarsi quando il metodo di valutazione dell'inventario è *Costo standard* o *Media mobile*. Entrambi questi metodi sono metodi di determinazione dei costi perpetui. In altre parole, il costo finale viene determinato al momento della registrazione.

Se stai usando il metodo *Media mobile*, il messaggio di errore è simile a questo esempio:

> Il valore dell'inventario xx.xx non è previsto dopo il calcolo della spesa proporzionale

Se stai usando il metodo *Costo standard*, il messaggio di errore è simile a questo esempio:

> Il costo standard non corrisponde al valore dell'inventario finanziario dopo l'aggiornamento. Valore = xx.xx, Qtà = yy.yy, Costo standard = zz.zz

Fino a quando Microsoft non rilascerà una soluzione per risolvere il problema, prendere in considerazione l'utilizzo delle seguenti soluzioni alternative per evitare o ridurre questi errori:

- Registrare nuovamente i documenti con errore.
- Creare documenti con meno righe.
- Evitare i valori decimali nel costo standard. Provare a definire il costo standard in modo che il campo **Quantità di prezzo** sia impostato su *1*. Se devi specificare un valore **Quantità di prezzo** maggiore di *1*, prova a ridurre al minimo il numero di cifre decimali nel costo standard unitario. (Idealmente, dovrebbero esserci meno di due cifre decimali.) Ad esempio, evitare di definire impostazioni di costo standard come **Prezzo** = *10* e **Quantità di prezzo** = *3*, perché produrranno un costo standard unitario di 3,333333 (dove si ripete il valore decimale).
- Nella maggior parte dei documenti, evitare di avere più righe che contengono la stessa combinazione di dimensioni di inventario finanziario e prodotto.
- Riduci il grado di parallelizzazione. (In questo caso, il sistema potrebbe diventare più veloce, perché si verificano meno conflitti di aggiornamento e nuovi tentativi.)
