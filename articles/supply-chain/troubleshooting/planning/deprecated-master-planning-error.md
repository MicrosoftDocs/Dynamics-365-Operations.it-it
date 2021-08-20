---
title: Viene visualizzato un errore durante l'esecuzione del motore di pianificazione generale integrato
description: Quando si esegue il motore di pianificazione generale integrato viene visualizzato un messaggio di errore.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7c0c674818a21d3ad422661fc427b0b9c4aad52b8d44d08791d2d703be528fe3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751723"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a>Viene visualizzato un errore durante l'esecuzione del motore di pianificazione generale integrato

Codice di errore: ReqCalcScheduleItemTablePlanningOptimizationFitError

## <a name="symptoms"></a>Sintomi

Quando si esegue la pianificazione generale viene visualizzato il seguente messaggio di errore:

> Viene visualizzato questo messaggio di errore perché il motore di pianificazione generale incorporato è stato utilizzato per gli scenari supportati da Ottimizzazione pianificazione. È necessario eseguire la migrazione a Ottimizzazione pianificazione ora, poiché l'attuale pianificazione generale incorporata sarà deprecata. Notare che l'esecuzione della pianificazione generale viene completata correttamente. Nel caso in cui la migrazione abbia forti dipendenze da funzionalità in sospeso, è possibile richiedere un'eccezione per l'utilizzo continuato del motore di pianificazione generale integrato. Completare il seguente questionario per iniziare e, se pertinente, richiedere l'eccezione dalla migrazione a Ottimizzazione pianificazione. [Questionario sulla migrazione e sulle eccezioni di Ottimizzazione pianificazione](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a>Causa

Se si esegue la pianificazione e non si utilizzano le funzionalità di controllo della produzione, è consigliabile eseguire la migrazione a Ottimizzazione pianificazione. Il motore di pianificazione generale integrato è stato deprecato. Pertanto, per continuare a utilizzarlo senza ricevere il messaggio di errore, è necessario richiedere un'eccezione a Microsoft.

## <a name="resolution"></a>Risoluzione

Per ulteriori informazioni su come eseguire la migrazione a Ottimizzazione pianificazione o su come richiedere un'eccezione in modo da poter continuare a utilizzare il motore di pianificazione integrato deprecato, vedi [Migrazione a Ottimizzazione pianificazione per la pianificazione generale](/dynamics365/supply-chain/master-planning/new-master-planning-engine).
