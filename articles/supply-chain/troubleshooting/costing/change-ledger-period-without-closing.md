---
title: Avvisi o gli erroriquando si modifica lo stato di un periodo contabile senza chiudere l'inventario
description: Avvisi o gli erroriquando si modifica lo stato di un periodo contabile senza chiudere l'inventario
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 05851753e29da75f014d2cc77e2b8df259620eee
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476754"
---
# <a name="warnings-or-errors-on-changing-ledger-period-status-without-closing-inventory"></a>Avvisi o gli erroriquando si modifica lo stato di un periodo contabile senza chiudere l'inventario

Microsoft ha introdotto le seguenti convalide per evitare problemi causati da un processo di fine periodo errato relativo ai costi. Se viene visualizzato uno dei seguenti messaggi di errore, fare riferimento a [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) per ulteriori informazioni su come risolvere questi problemi.

- Si sta per eseguire un ricalcolo con data %1 (10-02-2019). L'ultimo ricalcolo registrato è stato eseguito in un periodo precedente con una data %2 (20-01-2019). Nessuna esecuzione di chiusura di inventario con data %3 (31-01-2019) corrispondente alla fine del periodo è stata registrata. Ricordarsi di eseguire una chiusura dell'inventario a partire dal %3 (31-01-2019) corrispondente alla fine del periodo. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito.

- Si sta per modificare lo stato del periodo contabile %1 su %2. Nessuna esecuzione di chiusura di inventario con data %3 corrispondente alla fine del periodo è stata registrata. Eseguire una chiusura dell'inventario a partire dal %3 corrispondente alla fine del periodo prima di modificare lo stato. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito. Dichiarato dalla persona giuridica %4. Per il momento si tratta solo di un messaggio informativo, ma in futuro questa azione sarà necessaria.

- La struttura dei conti %1 è stata cambiata. Uno o più conti principali %2 non esistono più. Questi conti principali sono richiesti da %3 con data %4. Aggiungere questi account principali alla struttura dei conti %1 prima di poter riprendere il processo %3. Per il momento si tratta solo di un messaggio informativo, ma in futuro questa azione sarà necessaria.

- Si sta per eseguire una chiusura dell'inventario con data %1 (31-01-2019). Nessuna esecuzione del calcolo dei costi di backflush con data %2 (31-01-2019) corrispondente alla fine del periodo è stata registrata. Eseguire il calcolo dei costi di backflush con data %3 (31-01-2019) corrispondente alla fine del periodo. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito.

- Si sta per eseguire un calcolo dei costi di backflush con data %1 (28-02-2019). L'ultimo calcolo dei costi di backflush registrato è stato eseguito in un periodo precedente con una data %2 (31-01-2019). Nessuna esecuzione di chiusura di inventario con data %3 (31-01-2019) corrispondente alla fine del periodo è stata registrata.

Ricordarsi di eseguire una chiusura dell'inventario a partire dal %3 (31-01-2019) corrispondente alla fine del periodo. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando la chiusura dell'inventario non viene eseguita.