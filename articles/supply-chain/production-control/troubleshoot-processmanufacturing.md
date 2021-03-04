---
title: Risolvere i problemi di produzione processo
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza la produzione processo.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 63993fca2164301d31dbfa1474a4cf5eb16273e6
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516811"
---
# <a name="troubleshoot-process-manufacturing"></a>Risolvere i problemi di produzione processo

Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza la produzione processo.

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a>Quando si utilizza il dispositivo scheda processo per dichiarare una quantità parziale sull'ultimo processo in un ordine di produzione, tutti i processi precedenti su quell'ordine che hanno lo stato In corso vengono automaticamente terminati.

Questo comportamento è predefinito. Nella pagina **Impostazioni predefinite ordine di produzione**, nella scheda **Dichiarazione di finito**, c'è un'opzione denominata **Ciclo di lavorazione con contrassegno di fine**. Se questo argomento è impostato su *Sì*, viene registrato un giornale di registrazione delle schede cicli di lavorazione quando un lavoratore utilizza il dispositivo scheda processo o il terminale scheda processo per dichiarare l'ultima operazione. Questo giornale contrassegna tutte le operazioni come completate e termina tutti i processi di produzione. Quando l'opzione **Ciclo di lavorazione con contrassegno di fine** è impostata su *Sì*, il sistema non considera lo stato del processo che il lavoratore ha selezionato quando ha dichiarato l'ultima operazione. Il sistema inoltre non considera se il lavoratore sta dichiarando una quantità totale o parziale.

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a>Quando si tenta di chiudere uno stock viene visualizzato il seguente messaggio di avviso: "Nessuna esecuzione del calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo è stata registrata."

Nelle versioni precedenti alla versione 10.0.13, se non si utilizza il flusso di determinazione dei costi di produzione snella, viene visualizzato il seguente messaggio di avviso errato durante la chiusura dell'inventario:

> Si sta per eseguire una chiusura dell'inventario con data %1. Nessuna esecuzione del calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo è stata registrata. Eseguire il calcolo dei costi di backflush con data %1 corrispondente alla fine del periodo. La valutazione delle scorte, del costo delle merci vendute e degli scostamenti potrebbe non essere corretta nella contabilità secondaria o nella contabilità generale fino a quando non viene eseguito.

Questo problema è stato risolto nella versione 10.0.13 e successive. Per ulteriori informazioni, vedere [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]