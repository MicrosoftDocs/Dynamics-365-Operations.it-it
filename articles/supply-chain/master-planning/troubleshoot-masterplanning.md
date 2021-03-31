---
title: Risolvere i problemi della pianificazione principale
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si lavora con la pianificazione principale.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: db336946873fa1b5cc3f669823541af8cab4115b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216107"
---
# <a name="troubleshoot-master-planning"></a>Risolvere i problemi della pianificazione principale

Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si lavora con la pianificazione principale.

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a>L'esplosione della distinta base si comporta in modo diverso per gli ordini di produzione fissi e per gli ordini di produzione stimati per il lavoro creato manualmente.

### <a name="issue-description"></a>Descrizione del problema

Quando un ordine di produzione viene stabilizzato, gli articoli non vengono esplosi quando si esplode la distinta base (DBA). Tuttavia, quando si crea manualmente un ordine di lavoro e quindi si stima l'ordine di produzione, gli articoli vengono esplosi.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Il sistema funziona come previsto. L'esplosione che si verifica quando l'ordine di produzione viene stabilizzato punterà all'ordine pianificato, ma in questo caso non sembra che l'ordine pianificato sia attualmente confermato. Tuttavia, se l'ordine di produzione è stato stimato, l'esplosione viene attivata dall'ordine di produzione rilasciato in cui non esiste alcun ordine pianificato.

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a>Il valore Ritardo non viene aggiornato quando riprogramma un ordine pianificato.

Per aggiornare il ritardo per gli ordini pianificati, aprire la finestra di dialoto **Riprogrammazione** per l'ordine pianificato. Nella Scheda dettaglio **Esplosione**, assicurarsi che l'opzione **Esegui esplosione dopo la riprogrammazione** sia impostata su *Sì*.

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a>La programmazione della produzione non considera i margini di sicurezza impostati sulla copertura dell'articolo per la fornitura con pegging.

### <a name="issue-description"></a>Descrizione del problema

La pianificazione generale considera i margini di sicurezza. Tuttavia, i margini di sicurezza vengono ignorati quando vengono pianificati gli ordini di produzione pianificati.

### <a name="issue-resolution"></a>Risoluzione dei problemi

I margini vengono considerati solo durante la pianificazione generale, non durante la pianificazione manuale. I margini sono progettati per fungere da cuscinetto durante la fase di pianificazione, per dare un certo "margine" al processo vero e proprio.

Per ottenere il risultato desiderato, è possibile rimuovere il margine. Il ciclo di lavorazione deve quindi essere aggiornato in modo che includa il tempo desiderato (ad esempio, come tempo di coda). Sia la pianificazione generale che la pianificazione manuale devono quindi produrre lo stesso risultato.

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a>Gli ordini pianificati vengono generati anche se sono presenti articoli in magazzino e per essi esistono già ordini di produzione.

È possibile risolvere questo problema aumentando il valore **Giorni positivi** per i gruppi rilevanti nella pagina **Gruppo di copertura**. Questa modifica farà sì che il sistema determini se le scorte disponibili possono essere utilizzate per la domanda. Quindi non verrà generato un nuovo ordine pianificato per gli articoli disponibili.

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a>La pianificazione generale non sembra rispettare i limiti di capacità e sta pianificando più della capacità disponibile.

### <a name="issue-description"></a>Descrizione del problema

Quando si utilizza la pianificazione delle operazioni in cui è presente una capacità finita e dove il ciclo di lavorazione specifica una combinazione di requisiti sia per un gruppo di risorse che per le singole risorse, esiste una piccola possibilità di prenotazioni in eccesso a causa del modo in cui l'algoritmo convalida i conflitti di capacità. Questo prenotazione in eccesso può verificarsi quando si utilizzano helper per eseguire la pianificazione generale. È molto probabile che si verifichi se sono presenti molti processi che hanno un tempo di esecuzione relativamente breve.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Se è essenziale che non si verifichi la prenotazione in eccesso per la pianificazione delle operazioni, è possibile rendere la pianificazione parte della pianificazione generale a thread singolo attivando l'opzione **Capacità finita accurata per la pianificazione delle operazioni** nella pagina **Parametri di pianificazione generale**. Questa opzione non è disponibile per impostazione predefinita. È necessario aggiungerla manualmente alla pagina utilizzando le funzionalità di personalizzazione. Quando si utilizza questa opzione, la pianificazione verrà eseguita più lentamente a causa della mancanza di elaborazione parallela.

## <a name="planned-orders-take-a-long-time-to-update"></a>Gli ordini pianificati richiedono molto tempo per l'aggiornamento.

### <a name="issue-description"></a>Descrizione del problema

Quando si aggiorna la quantità richiesta e/o la data di consegna di un ordine pianificato, in genere sono necessari almeno 30 secondi per ordine per salvare l'aggiornamento.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Si tratta di un problema noto con il motore di pianificazione generale integrato. È causato dall'auto esplosione sottostante attraverso la struttura della distinta base durante le modifiche. Questo problema viene risolto in Ottimizzazione pianificazione, in cui un pianificatore può aggiornare e approvare gli ordini pertinenti e, se desiderato, attivare un'esecuzione della pianificazione per aggiornare gli ordini pianificati per la struttura della distinta base sottostante.

Un modo per migliorare le prestazioni con il motore di pianificazione generale integrato consiste nell'effettuare quanto segue:

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare un piano.
1. Espandere la scheda dettaglio **Intervalli temporali in giorni**.
1. Impostare **Esplosione** su *Sì* e impostare il campo sotto questa impostazione su 0 (zero).

> [!NOTE]
> Ciò limiterà il periodo per le esplosioni eseguite per questo piano generale a un solo giorno.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]