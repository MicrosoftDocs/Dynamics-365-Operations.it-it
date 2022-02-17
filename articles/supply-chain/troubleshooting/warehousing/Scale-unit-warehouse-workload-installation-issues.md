---
title: I problemi di elaborazione si verificano dopo l'installazione di un carico di lavoro di magazzino con unità di scala
description: Questo argomento descrive i problemi che possono verificarsi subito dopo l'installazione di un carico di lavoro di magazzino con unità di scala e fornisce consigli per risolverli.
author: perlynne
ms.date: 1/13/2022
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningWorkbench, WHSOutboundLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-01-13
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f589ffed61b695f471989ab1dd693f30cd5d5262
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071631"
---
# <a name="processing-issues-occur-after-a-scale-unit-warehouse-workload-is-installed"></a>I problemi di elaborazione si verificano dopo l'installazione di un carico di lavoro di magazzino con unità di scala

Questo argomento descrive i problemi che possono verificarsi subito dopo l'installazione di un carico di lavoro di magazzino con unità di scala e fornisce consigli per risolverli.

## <a name="issue-1-error-after-a-load-is-released-from-a-load-planning-workbench"></a>Problema 1: errore dopo il rilascio di un carico da una workbench di pianificazione del carico

### <a name="symptoms-of-issue-1"></a>Sintomo del problema 1

Quando si rilascia un carico dalla pagina **Workbench pianificazione carico** o **Workbench di pianificazione del carico in uscita**, viene visualizzato un messaggio di errore con la forma seguente:

> È stata rilevata un'eccezione durante la registrazione del carico %1. Impossibile rilasciare il carico.
> 
> UPDATE WHSSHIPMENTTABLE SET ...
> 
> Impossibile modificare un record in Spedizioni (WHSShipmentTable). ID spedizione: ...

Ecco un esempio reale che include dati di esempio:

> È stata rilevata un'eccezione durante la registrazione del carico USMF-000033. Impossibile rilasciare il carico.
sessione 5133 (amministratore)
>
> UPDATE WHSSHIPMENTTABLE SET ORDERNUM=?,RECVERSION=?,MODIFIEDDATETIME=?,MODIFIEDBY=? WHERE ((RECID=?) AND (RECVERSION=?))  
> [Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Scale Unit @@ attempted to update records owned by Scale Unit @A.  
> Server oggetti Azure:
>
> Impossibile modificare un record in Spedizioni (WHSShipmentTable). ID spedizione: USMF-000031, USMF-000033. Errore del database SQL.

### <a name="cause-of-issue-1"></a>Causa del problema 1

Questo problema può verificarsi se si verifica la seguente combinazione di condizioni quando si installa il carico di lavoro di magazzino con unità di scala:

- Il sistema include un carico non rilasciato in cui più righe sono associate a ordini diversi e alcune righe di carico non sono associate a una spedizione.
- Il sistema è configurato per utilizzare il consolidamento della spedizione.

In una distribuzione di topologia ibrida distribuita, ogni record di carico e spedizione è contrassegnato come di proprietà di un'unità di scala o hub specifico. Quando si rilascia un carico dalla pagina **Workbench pianificazione carico**, il sistema cambia la proprietà assegnata. Tuttavia, a causa delle condizioni elencate in precedenza, il sistema potrebbe non essere in grado di risolvere la proprietà dei dati. Pertanto, non riesce a rilasciare il carico al magazzino.

### <a name="resolution-of-issue-1"></a>Risoluzione del problema 1

Dividi il carico in due carichi più piccoli prima di rilasciarlo al magazzino.

## <a name="issue-2-error-while-a-wave-is-processed-on-a-scale-unit"></a>Problema 2: errore durante l'elaborazione di un ciclo su un'unità di scala

### <a name="symptoms-of-issue-2"></a>Sintomo del problema 2

Durante l'elaborazione di un ciclo su un'unità di scala, viene visualizzato un messaggio di errore con la forma seguente:

> Non è possibile modificare la riga di carico con RecId =%1, ID carico=%2 in quanto è ancora di proprietà dell'hub aziendale. Assicurarsi che il carico in uscita corrispondente sia stato rilasciato a un'unità di scala e quindi che le righe ordine di magazzino siano state create.

Ecco un esempio reale che include dati di esempio:

> Infolog per il processo Esegui ciclo USMF-000000012 (9223377668365210)  
> Infolog per l'attività Esegui ciclo USMF-000000012 (9223377668370462)  
> Non è possibile modificare la riga di carico con RecId = 68719478242, ID carico= USMF-000034 in quanto è ancora di proprietà dell'hub aziendale. Assicurarsi che il carico in uscita corrispondente sia stato rilasciato a un'unità di scala e quindi che le righe ordine di magazzino siano state create.

### <a name="cause-of-issue-2"></a>Causa del problema 2

In una distribuzione di topologia ibrida distribuita, la proprietà dei dati di carico e spedizione è assegnata a un'unità di scala o hub specifico. Nell'ambito dell'elaborazione dei cicli, la proprietà dei dati dovrebbe essere assegnata a un'unità di scala.

Quando si installa un carico di lavoro di magazzino con unità di scala, se una spedizione aperta è associata a un carico e a un ciclo, il sistema non può controllare la proprietà dei dati. Pertanto, l'elaborazione del ciclo non riesce sull'unità di scala.

### <a name="resolution-of-issue-2"></a>Risoluzione del problema 2

Rilascia il carico al magazzino dall'hub.

## <a name="troubleshoot-issues-by-viewing-a-records-ownership-and-destination"></a>Risolvere i problemi visualizzando la proprietà e la destinazione di un record

In una distribuzione di topologia ibrida distribuita, molti tipi di record sono contrassegnati come di proprietà di un'unità di scala o hub specifico. Dopo il passaggio a una topologia ibrida distribuita e/o l'impostazione di un nuovo carico di lavoro di magazzino con unità di scala, il sistema assegna la proprietà a ciascun record pertinente. Questo processo a volte può causare errori o produrre risultati imprevisti. Pertanto, le informazioni sulla proprietà di un record e sulla destinazione del trasferimento possono aiutare a risolvere i problemi che si verificano dopo aver apportato questi tipi di modifiche.

Segui questi passaggi per visualizzare la proprietà e la destinazione del trasferimento di un record.

1. Apri il record pertinente.
1. Nel riquadro azioni della scheda **Opzioni** del gruppo **Info record**, seleziona **Mostra tutti campi**.
1. La pagina che appare mostra tutti i valori per tutti i campi che sono disponibili per il record selezionato. Rivedi i seguenti campi:

    - **SYSSCALEUNITID** – Questo campo mostra l'attuale proprietario del record.
    - **SYSTARGETSCALEUNITID** – Questo campo mostra l'ID dell'unità di scala dell'hub o dell'unità di scala a cui verrà trasferito il record quando l'attuale proprietario avrà finito di utilizzarlo. Il valore di questo campo viene utilizzato dai processi batch che gestiscono questo tipo di processo. Sebbene questo campo non sia direttamente correlato alla proprietà, la proprietà potrebbe cambiare quando il record viene trasferito. In alcuni casi, questo campo sarà vuoto.
