---
title: Migrazione all'ottimizzazione di pianificazione per la pianificazione generale
description: Questo articolo fornisce informazioni sul nuovo motore di pianificazione generale, sull'ottimizzazione della pianificazione e sulla migrazione dal motore esistente.
author: t-benebo
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: dbbc58f0dcd833f63e84a73ac68ada60bd0c291d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739953"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Migrazione all'ottimizzazione di pianificazione per la pianificazione generale

[!include [banner](../includes/banner.md)]

Il motore di pianificazione generale integrato è pianificato per diventare obsoleto (deprecato). Viene sostituito dal componente aggiuntivo Ottimizzazione pianificazione per Microsoft Dynamics 365 Supply Chain Management. Questo articolo fornisce informazioni sull'impatto sulle distribuzioni nuove ed esistenti. Include informazioni sulle azioni richieste.

Il componente aggiuntivo Ottimizzazione pianificazione consente il calcolo della pianificazione principale al di fuori di Supply Chain Management e del relativo database Azure SQL. I vantaggi associati all'ottimizzazione della pianificazione includono prestazioni migliorate e un impatto minimo sul database SQL durante le esecuzioni della pianificazione generale. Dal momento che le esecuzioni di pianificazione rapide possono essere eseguite anche durante le ore d'ufficio, i pianificatori possono reagire immediatamente alla modifica della domanda o dei parametri.

Per ulteriori informazioni sull'ottimizzazione della pianificazione, vedi [Architettura di sistema della pianificazione generale](master-planning-architecture.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>Obsolescenza del motore di pianificazione principale esistente

Microsoft è in procinto di rendere obsoleto il motore di pianificazione generale deprecato a favore di Ottimizzazione pianificazione. Questa modifica interessa tutti gli ambienti cloud. Le installazioni locali non sono interessate. Nella versione 10.0.16 e successive, verrà visualizzato un messaggio di errore se si esegue il motore di pianificazione generale deprecato senza generare ordini di produzione pianificati. Tuttavia, l'esecuzione della pianificazione generale verrà completata nonostante il messaggio di errore.

Per ulteriori informazioni sul motore di pianificazione generale deprecato, vedi gli annunci in [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Migrazione, messaggi ed eccezioni

I proprietari di ambienti esistenti che eseguono il motore di pianificazione generale deprecato senza la generazione di ordini di produzione pianificati riceveranno un messaggio e-mail con i dettagli sul processo di eccezione. Ti consigliamo di collaborare con un partner per valutare e pianificare la migrazione all'ottimizzazione di pianificazione.

Come già indicato, nella versione 10.0.16 e successive verrà visualizzato un messaggio di errore se si esegue il motore di pianificazione generale deprecato senza generare ordini di produzione pianificati. Questo messaggio di errore include indicazioni sulla migrazione e istruzioni per richiedere un'eccezione.

### <a name="new-deployments"></a>Nuove distribuzioni

Ottimizzazione pianificazione deve essere considerato il motore di pianificazione principale predefinito per tutte le nuove distribuzioni nel cloud. In generale, Ottimizzazione pianificazione deve essere utilizzato per tutte le nuove distribuzioni che non generano ordini di produzione pianificati durante la pianificazione generale. Se una nuova distribuzione dipende da funzionalità che Ottimizzazione pianificazione non supporta attualmente, è possibile richiedere un'eccezione in modo da poter continuare a utilizzare il motore di pianificazione generale deprecato.

### <a name="existing-deployments"></a>Distribuzioni esistenti

I proprietari di distribuzioni basate su cloud esistenti che dipendono dalla pianificazione generale devono pianificare la migrazione a Ottimizzazione pianificazione. Se l'implementazione dipende da funzionalità che Ottimizzazione pianificazione non supporta attualmente, è possibile richiedere un'eccezione in modo da poter continuare a utilizzare il motore di pianificazione generale deprecato.

Per gli ambienti che attualmente utilizzano processi di pianificazione generale resi obsoleti, Microsoft invierà un messaggio di posta elettronica all'amministratore dell'ambiente. Questo messaggio e-mail fornirà informazioni sulle azioni necessarie per eseguire la migrazione o per richiedere un'eccezione.

## <a name="the-exception-process"></a>Il processo delle eccezioni

È possibile richiedere un'eccezione se è necessario continuare a utilizzare il motore di pianificazione generale deprecato perché i processi aziendali dipendono in gran parte da almeno una funzionalità che non è attualmente implementata in Ottimizzazione pianificazione. Per un elenco delle funzionalità disponibili, vedere [Analisi corrispondenza di Ottimizzazione pianificazione](planning-optimization/planning-optimization-fit-analysis.md).

Attualmente le eccezioni per la migrazione di Ottimizzazione pianificazione sono rilevanti solo se il processo di pianificazione generale non include la produzione (ordini di produzione pianificati generati tramite la pianificazione generale) ed è necessaria una versione del motore di pianificazione generale deprecato successiva alla versione 10.0.15.

Dopo che le funzionalità richieste diventano disponibili, Microsoft fornirà un periodo di tolleranza fino alla scadenza dell'eccezione. L'amministratore dell'ambiente verrà informato quando le funzionalità richieste saranno disponibili e il periodo di tolleranza è iniziato.

Il diagramma di flusso seguente riepiloga le informazioni fornite in questo articolo in modo da poter scoprire rapidamente se è necessario richiedere un'eccezione. Se devi richiedere un'eccezione, compila e invia il [questionario sulla migrazione e sulle eccezioni di Ottimizzazione pianificazione](https://go.microsoft.com/fwlink/?linkid=2144962). Il gruppo di prodotti è responsabile della valutazione e dell'approvazione di ogni richiesta di eccezione, quindi invia la tua richiesta direttamente al gruppo di prodotti utilizzando il collegamento fornito senza creare un ticket di supporto. Se la tua richiesta viene rifiutata, non creare un ticket di supporto perché il supporto Microsoft non è in grado di rivalutare o concedere eccezioni.

![Diagramma di flusso delle eccezioni.](media/exception-diagram.png "Diagramma di flusso delle eccezioni")

> [!NOTE]
> È possibile richiedere un'eccezione solo per i tenant che attualmente includono, o includeranno, un ambiente di produzione, non solo per tenant con ambienti sandbox. Se è necessario disabilitare l'errore di eccezione di Ottimizzazione pianificazione su un ambiente sandbox IaaS (Infrastructure as a Service), eseguire la query SQL fornita in [Ambienti sandbox](#faq-sandbox).

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Ambienti sandbox

È possibile utilizzare il motore di pianificazione generale deprecato nell'ambiente sandbox? È necessaria un'eccezione?

**Risposta:** Le eccezioni non sono normalmente rilevanti per gli ambienti sandbox perché l'errore di eccezione di Ottimizzazione pianificazione non impedisce il corretto funzionamento del motore di pianificazione principale deprecato. Tuttavia, se il messaggio di errore disturba, è possibile disabilitarlo in un ambiente sandbox IaaS (non Service Fabric) eseguendo la seguente query sul database:

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>Ambienti locali

L'ambiente in uso è locale. È necessaria un'eccezione?

**Risposta:** No. Non è richiesta un'eccezione per gli ambienti locali. È possibile continuare a utilizzare il motore di pianificazione generale deprecato. L'amministratore dell'ambiente verrà informato se è necessaria un'azione.

### <a name="production-scenarios"></a>Scenari di produzione

Si usano gli ordini di produzione pianificati e preoccupa l'aggiornamento alla versione 10.0.16. Si deve intraprendere un'azione?

**Risposta:** Non c'è ragione di essere preoccupati. È possibile continuare a utilizzare il motore di pianificazione generale deprecato nella versione 10.0.16. Tuttavia, si consiglia di valutare se la migrazione a Ottimizzazione pianificazione può iniziare con la funzionalità corrente. Consigliamo inoltre di rimanere informati sulle nuove funzionalità.

### <a name="email-from-microsoft"></a>Messaggio e-mail di Microsoft

L'amministratore dell'ambiente ha ricevuto un messaggio e-mail da Microsoft. Questo messaggio e-mail afferma che si deve eseguire la migrazione a Ottimizzazione pianificazione o richiedere un'eccezione. Si deve intraprendere qualche azione?

**Risposta:** Sì. L'ambiente sarà influenzato a meno che non si seguano le istruzioni nel messaggio e-mail. È possibile eseguire la migrazione a Ottimizzazione pianificazione entro la data specificata o richiedere un'eccezione utilizzando il collegamento nell'e-mail. Questo collegamento apre un questionario. Dopo aver completato e inviato questo questionario, si riceverà una risposta via e-mail. Sebbene questo processo sia manuale, Microsoft cerca di rispondere entro una settimana dall'invio del questionario.

### <a name="error-messages"></a>Messaggi di errore

È in uso la versione 10.0.16 o successiva e si riceve il seguente messaggio di errore quando si esegue la pianificazione generale. La pianificazione generale è bloccata?

> Viene visualizzato questo messaggio di errore perché il motore di pianificazione generale deprecato è stato utilizzato per gli scenari supportati da Ottimizzazione pianificazione. È consigliabile eseguire la migrazione a Ottimizzazione pianificazione ora, poiché il motore di pianificazione generale è stato deprecato. Notare che l'esecuzione della pianificazione generale viene completata correttamente.
>
> Nel caso in cui la migrazione abbia forti dipendenze da funzionalità in sospeso, è possibile richiedere un'eccezione per l'utilizzo continuato del motore di pianificazione generale deprecato.
>
> Completare il seguente questionario per iniziare e, se pertinente, richiedere l'eccezione dalla migrazione a Ottimizzazione pianificazione.

**Risposta:** No, la pianificazione generale non è bloccata. L'esecuzione della pianificazione generale è stata completata ed è possibile utilizzare il risultato nel modo consueto. Tuttavia, per evitare di ricevere questo messaggio di errore durante le future esecuzioni della pianificazione generale, è necessario migrare immediatamente a Ottimizzazione pianificazione o richiedere un'eccezione utilizzando il collegamento nel messaggio di errore.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
