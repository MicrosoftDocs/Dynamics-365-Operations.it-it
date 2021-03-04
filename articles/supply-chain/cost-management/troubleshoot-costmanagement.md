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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e84bb167395c06295b0e8ef8b9fd98aa4bc0cc14
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4431593"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]