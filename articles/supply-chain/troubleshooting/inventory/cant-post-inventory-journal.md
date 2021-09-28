---
title: Il flusso di lavoro del giornale di registrazione dell'inventario non viene mai completato e il giornale di registrazione non può essere elaborato
description: Dopo aver inviato un flusso di lavoro di approvazione del giornale di registrazione, l'elaborazione del flusso di lavoro smette di rispondere e non è possibile modificare o elaborare i giornali di registrazione.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9430068f9c2d92c894817db04143297de6c6aa6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476730"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>Il flusso di lavoro del giornale di registrazione dell'inventario non viene mai completato e il giornale di registrazione non può essere elaborato

## <a name="symptoms"></a>Sintomi

Dopo aver inviato un flusso di lavoro di approvazione del giornale di registrazione, l'elaborazione del flusso di lavoro smette di rispondere e non è possibile modificare o elaborare i giornali di registrazione.

## <a name="resolution"></a>Risoluzione

Esistono diversi motivi per cui l'elaborazione del flusso di lavoro potrebbe non essere completata. Verifica i seguenti problemi:

- Vai a **Gestione inventario &gt; Imposta &gt; Flussi di lavoro gestione articoli** e rivedi la configurazione del flusso di lavoro interessato. Per ulteriori informazioni, vedere [Flussi di lavoro di approvazione del giornale di registrazione magazzino](/dynamics365/supply-chain/inventory/inventory-journal-workflow.md).
- Il flusso di lavoro potrebbe riscontrare un'eccezione o un errore. Rivedi la cronologia degli elementi di lavoro del flusso di lavoro interessato per vedere se include un errore dell'applicazione che termina il flusso di lavoro.
- Il giornale di registrazione inventario può essere aggiornato o modificato solo se approvato. Se il richiamo è attivo, puoi provare a richiamare il giornale di registrazione. L'esecuzione del processo batch del flusso di lavoro potrebbe essere sospesa per diversi motivi. Alcuni di questi motivi potrebbero essere causati dal problema del framework del flusso di lavoro.