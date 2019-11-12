---
title: Elaborazione batch degli avvisi
description: Vengono fornite informazioni generali sull'elaborazione batch degli avvisi.
author: tjvass
manager: AnnBe
ms.date: 09/10/2010
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: a06ca45de3a7bb6d65a8ed5466cd6591d4e0820f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180808"
---
# <a name="batch-processing-of-alerts"></a>Elaborazione batch degli avvisi

[!include [banner](../includes/banner.md)]

Gli avvisi vengono gestiti tramite l'elaborazione batch. È necessario impostare l'elaborazione batch per consentire il recapito degli avvisi.

Sono supportati due tipi di eventi:

- Eventi generati da eventi basati sulla modifica. Questi eventi vengono anche definiti eventi di creazione/eliminazione e di aggiornamento.
- Eventi generati dalle date di scadenza.

È possibile impostare processi batch per ciascun tipo di evento.
        
## <a name="batch-processing-for-change-based-events"></a>Elaborazione batch per eventi basati su modifica

Il sistema legge tutti gli eventi basati sulla modifica che si sono verificati dopo l'ultima esecuzione dell'elaborazione batch. Gli eventi basati su modifica includono gli aggiornamenti ai campi, nonché l'eliminazione e la creazione dei record. Questi eventi vengono confrontati con le condizioni impostate nelle regole di avviso. Quando un evento soddisfa le condizioni di una regola, il processo batch genera un avviso.

### <a name="frequency-for-change-based-events"></a>Frequenza per gli eventi basati sulla modifica

Per gli eventi basati sulla modifica è possibile impostare un processo batch che avvia l'elaborazione dell'evento poco dopo che è stato registrato nel sistema. Se si imposta il processo batch per la ripetizione più frequente, gli utenti ricevono gli avvisi subito dopo le modifiche. Tuttavia, una frequenza elevata dell'elaborazione batch può influire negativamente sulle prestazioni del sistema.

Un processo batch che si ripete invece con minore frequenza ed è pianificato per orari in cui il carico del sistema è ridotto può contribuire a migliorare le prestazioni del sistema. Tuttavia, una frequenza bassa dell'elaborazione batch può non soddisfare le richieste degli utenti riguardanti la tempestività degli avvisi.

Pertanto, quando si imposta la frequenza dell'elaborazione batch per eventi basati sulla modifica, è necessario raggiungere un compromesso tra la tempestività degli avvisi e le prestazioni dell'intero sistema. Queste considerazioni diventano più rilevanti, man mano che aumenta il numero degli utenti che creano regole di avviso. La frequenza non influisce sul numero di eventi che devono essere elaborati. Tuttavia, se più utenti creano regole, occorre eseguire maggiori controlli. Questo tipo di scambio dei dati può influire sulle prestazioni del sistema.

#### <a name="the-risks-of-low-batch-frequency"></a>I rischi correlati a una bassa frequenza del processo batch

Se si imposta una frequenza bassa per l'elaborazione batch degli eventi basati sulla modifica, i dati rilevanti per le condizioni delle regole di avviso possono cambiare prima dell'elaborazione del batch. Di conseguenza, è possibile perdere degli avvisi.

Ad esempio una regola di avviso viene impostata per generare un avviso quando si verifica l'evento **modifica del contatto del cliente** e viene soddisfatta la condizione **cliente = BB**. In altre parole, quando il contatto del cliente BB cambia, l'evento viene registrato. Tuttavia, il sistema di elaborazione batch viene impostato in modo che l'elaborazione batch si verifichi con una frequenza minore rispetto all'immissione dei dati. Se il nome del cliente viene modificato da **BB** in **AA** prima che l'evento venga elaborato, i dati nel database non corrispondono più alla condizione della regola, **cliente = BB**. Di conseguenza, quando l'evento è infine elaborato, non viene generato alcun avviso.

### <a name="set-up-processing-for-change-based-alerts"></a>Impostare l'elaborazione per gli avvisi basati sulla modifica

1. Passare ad **Amministrazione sistema** &gt; **Attività periodiche** &gt; **Avvisi** &gt; **Avvisi basati su modifica**.
2. Nella finestra di dialogo **Avvisi basati su modifica**, immettere le informazioni appropriate.

## <a name="batch-processing-for-due-date-events"></a>Elaborazione batch per eventi di scadenza

Il sistema rileva tutti gli eventi generati dalle date di scadenza, che vengono quindi confrontati con le condizioni impostate nelle regole di avviso. Quando un evento soddisfa le condizioni di una regola, il processo batch genera un avviso.

### <a name="frequency-for-due-date-events"></a>Frequenza per gli eventi generati dalla data di scadenza

Per gli eventi generati dalla data di scadenza è consigliabile impostare processi batch che vengono eseguiti durante la notte oppure in orari specifici del giorno in modo da bilanciare il carico del sistema. Si consiglia di impostare il processo batch in modo che venga eseguito almeno una volta al giorno. Se si desidera che gli avvisi vengano inviati quanto prima, impostare l'elaborazione batch in modo che venga eseguita immediatamente dopo il cambiamento della data di sistema. Se si desidera visualizzare gli avvisi per gli eventi generati dalla data di scadenza che si verificano dopo che un processo batch ha già elaborato gli avvisi, è possibile eseguire nuovamente il processo batch nello stesso giorno.

Ad esempio, un processo batch è stato eseguito in un giorno specifico. Viene pertanto creato un ordine fornitore con una data di scadenza che deve generare un avviso nello stesso giorno. Affinché l'avviso venga ricevuto in tale giorno, è necessario eseguire nuovamente il processo batch dopo la creazione dell'ordine fornitore. Se, tuttavia, il processo batch non viene eseguito di nuovo nello stesso giorno, il processo batch del giorno successivo rileverà tutti gli eventi generati dalla data di scadenza non elaborati nei giorni precedenti.

> [!NOTE]
> Anche quando il processo batch viene eseguito più volte al giorno, gli avvisi non vengono duplicati per lo stesso evento generato dalla data di scadenza e le stesse condizioni. Gli avvisi vengono generati solo quando viene raggiunta una data di scadenza a causa di modifiche apportate nel sistema dopo l'esecuzione dell'ultimo processo batch.

### <a name="batch-processing-window"></a>Finestra di elaborazione batch

L'elaborazione delle regole di avviso in una società può essere interrotta per diversi motivi, ad esempio vacanze, errori di sistema o altre situazioni che impediscono l'esecuzione dei processi batch per un determinato periodo di tempo.

Per evitare che gli avvisi della data di scadenza diventino obsoleti poiché il processo batch non è stato eseguito per vari giorni, è possibile impostare una finestra di elaborazione batch. È possibile utilizzare una finestra di elaborazione batch per impedire l'esecuzione di un processo batch per un numero di giorni specificato.

Se si configura una finestra di elaborazione batch, viene inviato un avviso quando la regola di avviso viene elaborata, anche se l'avviso supera il limite di tempo definito nei criteri relativi alla data di scadenza. Un avviso continua a essere inviato fino a quando non viene superato il periodo definito da questo limite di tempo e dalla finestra di elaborazione batch. Tuttavia, quando il periodo definito dal limite di tempo e dalla finestra di elaborazione batch viene superato, non viene più inviato un avviso.

### <a name="set-up-processing-for-due-date-alerts"></a>Impostare l'elaborazione per gli avvisi relativi alla data di scadenza

1. Passare ad **Amministrazione sistema** &gt; **Attività periodiche** &gt; **Avvisi** &gt; **Avvisi data di scadenza**.
2. Nella finestra di dialogo **Avvisi data di scadenza**, immettere le informazioni appropriate.