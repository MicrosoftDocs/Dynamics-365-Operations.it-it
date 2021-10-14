---
title: Risolvere l'errore del motore di pianificazione "Impossibile trovare capacità sufficiente"
description: Questo argomento fornisce informazioni sui motivi e sulle soluzioni per l'errore del motore di pianificazione "Impossibile programmare l'ordine di produzione %1. Impossibile trovare capacità sufficiente".
author: ChristianRytt
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 16626a7ee74e89bd129d8435a17d16b41a5e0387
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565761"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Risolvere l'errore del motore di pianificazione "Impossibile trovare capacità sufficiente"

[!include [banner](../includes/banner.md)]

Quando si esegue la programmazione, è possibile che venga visualizzato il seguente messaggio di errore:

> Impossibile programmare l'ordine di produzione %1. Impossibile trovare capacità sufficiente.

Esistono diversi motivi per cui il motore di pianificazione potrebbe non essere eseguito e per cui viene visualizzato di conseguenza un messaggio di errore. Questo argomento fornisce linee guida che consentiranno di trovare la causa principale dell'errore e di risolverla.

## <a name="review-the-applicable-resources"></a>Esaminare le risorse applicabili

L'errore può verificarsi se nessuna risorsa applicabile soddisfa i requisiti dell'operazione nel sito dell'ordine di produzione.

Per esaminare le risorse applicabili, seguire questi passaggi.

1. Andare a **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** e aprire o selezionare l'ordine di produzione che non può essere pianificato.
1. Nel riquadro Azioni, nella scheda **Ordine di produzione**, nel gruppo **Dettagli produzione** selezionare **Ciclo di lavorazione**.
1. Nella pagina **Ciclo di lavorazione produzione** selezionare l'operazione e quindi, nel riquadro Azioni, selezionare **Risorse applicabili**.
1. Nella finestra di dialogo **Risorse applicabili** impostare il campo **Usa requisiti per** su *Programmazione operazioni* o *Programmazione processo*, in base al tipo di programmazione in uso.
1. Assicurarsi che siano presenti risorse applicabili nel sito dell'ordine di produzione.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>Esaminare i calendari associati alle risorse

L'errore può verificarsi se nessun calendario è associato alla risorsa o al gruppo di risorse o se il calendario associato non è impostato correttamente (ad esempio se non ha orari di lavoro o se la sua efficienza in percentuale è 0 \[zero\]).

Per verificare che un calendario sia associato alla risorsa o al gruppo di risorse, seguire questi passaggi.

1. Andare a **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** e aprire o selezionare l'ordine di produzione che non può essere pianificato.
1. Nel riquadro Azioni, nella scheda **Ordine di produzione**, nel gruppo **Dettagli produzione** selezionare **Ciclo di lavorazione**.
1. Nella pagina **Ciclo di lavorazione produzione** selezionare l'operazione e quindi, nel riquadro Azioni, selezionare **Risorse applicabili**.
1. Nella finestra di dialogo **Risorse applicabili** selezionare la risorsa e quindi selezionare **Visualizza risorsa**. In alternativa, selezionare e tenere premuto (o fare clic con il pulsante destro del mouse) il campo **Gruppo di risorse** e quindi selezionare **Visualizza dettagli**.
1. Nella pagina **Risorse** o **Gruppi di risorse**, nella Scheda dettaglio **Calendari** verificare che un calendario sia associato alla risorsa o al gruppo di risorse.

> [!NOTE]
> Se l'errore si verifica durante la programmazione delle operazioni, è necessario assicurarsi che un calendario sia associato a tutti i gruppi di risorse applicabili.

Per esaminare l'impostazione del calendario, seguire questi passaggi.

1. Andare a **Amministrazione organizzazione \> Impostazione \> Calendari \> Calendari** e selezionare il calendario associato alla risorsa o al gruppo di risorse.
1. Nel riquadro Azioni selezionare **Orari di lavoro**.
1. Verificare che la pagina **Orari di lavoro** non sia vuota. Inoltre, per i giorni pertinenti, verificare che il campo **Controllo** non sia impostato su *Chiuso*, che gli orari di lavoro esistano e che il campo **Efficienza in percentuale** non sia impostato su *0* (zero).

Se il calendario è associato al calendario di base, è necessario rivedere anche l'impostazione di quest'ultimo.

> [!NOTE]
> Nella pianificazione delle operazioni, il calendario del gruppo di risorse viene utilizzato per determinare le ore e le date di inizio e di fine di ciascuna operazione. Limita inoltre la quantità di tempo che il sistema può pianificare per un'operazione specifica per un determinato giorno in un gruppo di risorse specifico. Ad esempio, se gli orari di lavoro per un gruppo di risorse in un giorno specifico sono compresi tra le 8:00 e le 16:00, il carico che un'operazione pone sul gruppo di risorse non può superare il carico che può essere contenuto in otto ore, indipendentemente dalla quantità di capacità disponibile di cui dispone il gruppo di risorse in quel giorno. La capacità disponibile può tuttavia limitare ulteriormente il carico.

## <a name="review-the-scheduling-parameters"></a>Esaminare i parametri di programmazione

Per garantire buone prestazioni, il motore di pianificazione cercherà una risorsa solo per un determinato periodo di tempo e per un numero specifico di conflitti di pianificazione.

Per esaminare i parametri della programmazione, seguire questi passaggi.

1. Andare a **Amministrazione organizzazione \> Impostazione \> Parametri di programmazione**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Se l'opzione **Timeout pianificazione abilitato** è impostata su *No*, andare al passaggio 3.
    - Se l'opzione **Timeout pianificazione abilitato** è impostata su *Sì*, aumentare il valore del campo **Tempo di pianificazione per sequenza** per incrementare il tempo di elaborazione.

1. Eseguire uno dei passaggi riportati di seguito.

    - Se l'opzione **Timeout ottimizzazione pianificazione abilitato** è impostata su *No*, andare al passaggio 4.
    - Se l'opzione **Timeout ottimizzazione pianificazione abilitato** è impostata su *Sì*, aumentare il valore del campo **Timeout tentativi ottimizzazione** per incrementare il tempo di elaborazione.

1. Se una delle impostazioni della pagina è stata modificata, riprogrammare l'ordine per riprovare.

## <a name="review-capacity"></a>Esaminare la capacità

L'errore può verificarsi quando si esegue la programmazione finita, ma non c'è capacità disponibile.

Per eseguire la programmazione della capacità infinita, seguire questi passaggi.

1. Andare a **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** e selezionare o aprire l'ordine di produzione che non può essere pianificato.
1. Nel riquadro Azioni, nella scheda **Programmazione**, nel gruppo **Ordine di produzione** selezionare **Programma operazioni** o **Programma processi**.
1. Nella finestra di dialogo **Programmazione operazioni** o **Programmazione processi** impostare l'opzione **Capacità limitata** su *No*.
1. Selezionare **OK** per programmare l'ordine.

Per esaminare la capacità disponibile sulla risorsa, seguire questi passaggi.

1. Andare a **Amministrazione organizzazione \> Risorse \> Risorse** e selezionare una risorsa applicabile all'ordine che non può essere programmato.
1. Nel riquadro Azioni, nella scheda **Risorsa**, nel gruppo **Visualizza** selezionare **Carico di capacità** o **Carico di capacità, grafico** e verificare che ci sia capacità disponibile.

Per esaminare la capacità disponibile sul gruppo di risorse, seguire questi passaggi.

1. Andare a **Amministrazione organizzazione \> Risorse \> Gruppi di risorse** e selezionare un gruppo di risorse applicabile all'ordine che non può essere programmato.
1. Nel riquadro Azioni, nella scheda **Gruppo di risorse**, nel gruppo **Visualizza** selezionare **Carico di capacità** o **Carico di capacità, grafico** e verificare che ci sia capacità disponibile.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
