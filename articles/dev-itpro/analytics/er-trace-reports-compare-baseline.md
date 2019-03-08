---
title: Tenere traccia dei risultati dei report generati e confrontarli con i valori di base
description: In questo argomento vengono fornite informazioni su come confrontare i risultati dei report di ER generati con i valori di report di base.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 7f7877ccaa0c45ab5f0032d6808280e3c47a43ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "317938"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Tenere traccia dei risultati dei report generati e confrontarli con i valori di base

[!include[banner](../includes/banner.md)]

È possibile tenere traccia dei risultati dei formati di ER che generano i documenti elettronici in uscita. Quando si attiva la generazione della traccia (parametro dell'utente ER **Esegui in modalità di debug**), viene generato un nuovo record di traccia nel registro di esecuzione del formato di ER ogni volta che viene eseguito un report di ER. I dettagli seguenti vengono archiviati in ogni traccia generata:

- Tutti gli avvisi generati dalle regole di convalida
- Tutti gli errori generati dalle regole di convalida
- Tutti i file generati archiviati come allegati del record di traccia

È possibile archiviare i singoli file di applicazione di base per qualsiasi formato di ER. I file vengono considerati file di base quando descrivono i risultati previsti di report che vengono eseguiti. Se un file di base è disponibile per un formato di ER eseguito mentre la generazione di traccia era attivata, la traccia archivia, oltre ai dettagli menzionati in precedenza, il risultato del confronto tra il documento elettronico generato e il file di base. Con un semplice clic è inoltre possibile ottenere il documento elettronico generato e il relativo file di base in un unico file con estensione zip. È quindi possibile effettuare il confronto dettagliato utilizzando uno strumento esterno come Windiff.

È possibile valutare la traccia per analizzare se i documenti elettronici generati includono il contenuto previsto. È possibile effettuare questa valutazione in un ambiente di test di accettazione utenti (UAT) quando viene modificata la base di codice, ad esempio quando è stata effettuata la migrazione a una nuova istanza dell'applicazione, sono stati installati gli hotfix o sono state distribuite modifiche al codice. In questo modo, è possibile assicurarsi che la valutazione non influisca sull'esecuzione dei report di ER utilizzati. Per molti report di ER, la valutazione può essere effettuata in modalità automatica.

Per ulteriori informazioni su questa funzionalità,, riprodurre le guide attività **ER Generare report e confrontare i risultati (Parte 1)** e **ER Generare report e confrontare i risultati (Parte 2)**, che fanno parte del processo aziendale **7.5.4.3 Eseguire test di soluzioni/servizi IT (10679)** e che possono essere scaricate dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Queste guide attività illustrano in dettaglio il processo di configurazione del framework di ER per utilizzare file di base per valutare documenti elettronici generati.
