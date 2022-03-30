---
title: Differenza imprevista tra i dati della richiesta e quelli di sessione durante il test
description: Una differenza imprevista tra i dati della richiesta e quelli di sessione nei risultati di convalida dell'attività di magazzino.
author: mamuszal
ms.date: 03/11/2022
ms.topic: troubleshooting
ms.search.form: WHSValidatorRunInstance_executeRun
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mamuszal
ms.search.validFrom: 2022-03-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da8f0506a76b0d0cc02bfc2e1bff01b4ddccb578
ms.sourcegitcommit: 941119133be1765f653d5d5270dfdf58466e1d07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2022
ms.locfileid: "8456939"
---
# <a name="unexpected-difference-between-request-and-session-data-during-testing"></a>Differenza imprevista tra i dati della richiesta e quelli di sessione durante il test

Codice errore: WarehouseMobileDeviceRequestInputValidationError

## <a name="symptoms"></a>Sintomi

Quando l'operatore usa il [Framework di convalida delle attività dell'app Warehouse](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/warehouse-app-task-validation-rsat), la convalida restituisce il seguente messaggio di errore:

> Differenza imprevista tra i dati della richiesta e quelli di sessione. Protocollo XML dei dispositivi mobili del magazzino violato. REQUEST_XML_TAMPERING

## <a name="cause"></a>Causa

L'errore si verifica quando l'output dell'ultimo passaggio che è stato eseguito correttamente nell'esecuzione del test non corrisponde all'input registrata per il passaggio successivo. Questa situazione può essere dovuta al fatto che la convalida dell'attività non usa l'output di un passaggio precedente come input per un passaggio successivo. Utilizza l'XML registrato come input per ciascun passaggio.

Nella maggior parte dei casi l'errore si verifica quando un'attività viene eseguita nuovamente ma il test richiede alcuni record modificati o rimossi da una precedente esecuzione della stessa attività.

## <a name="resolution"></a>Risoluzione

L'esecuzione del test di convalida dell'attività dell'app di magazzino non è un'operazione idempotenti ma modifica i dati sottostanti. Pertanto, prima di eseguire nuovamente un'attività potresti dover ripristinare i relativi dati.

1. Rivedi l'output XML dell'ultimo passaggio di test eseguito correttamente per determinare se l'esecuzione del tuo test è andata a buon fine.
1. Controlla li tuo test e accertati che tutti gli ordini di vendita richiesti, gli ordini di trasferimento, le intestazioni dei lavori e gli altri record siano ancora presenti e nello stato previsto.
1. Creare nuovamente o modificare i record modificati o mancanti. In alternativa, creare una nuova configurazione di test e progettare il test affinché usi i record esistenti validi.
