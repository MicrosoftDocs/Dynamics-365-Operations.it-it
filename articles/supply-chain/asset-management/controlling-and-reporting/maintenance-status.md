---
title: Stato della manutenzione
description: In questo argomento viene illustrato come calcolare lo stato della manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918351"
---
# <a name="maintenance-status"></a>Stato della manutenzione

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

In Gestione cespiti, è possibile eseguire un calcolo per visualizzare una panoramica delle richieste di intervento di manutenzione nuove, attive e completate, degli ordini di lavoro e delle attività dei tempi di fermo per la manutenzione per un periodo specifico. È inoltre possibile visualizzare il numero di valutazioni delle condizioni completate per lo stesso periodo. Utilizzare questo calcolo per ottenere una panoramica del carico di lavoro relativo alle richieste di intervento di manutenzione ricevute e completate e agli ordini di lavoro.

## <a name="make-a-maintenance-status-calculation"></a>Eseguire il calcolo di uno stato di manutenzione

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Stato della manutenzione**.

2. Nella finestra di dialogo **Calcola stato**, selezionare il periodo per il quale si desidera eseguire il calcolo nei campi **Dal** e **Al**.

3. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe di manutenzione in relazione alle unità funzionali. Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di manutenzione per un'unità funzionale verranno visualizzate nel livello principale, quindi lo stato in una riga può essere aggiunto dalle unità funzionali situate a un livello inferiore. Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di manutenzione in tutti i livelli di unità funzionali a cui sono correlate.

4. Fare clic su **OK** per avviare il calcolo.

5. Nei gruppi di riquadri azioni **Raggruppa per**, fare clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo. I pulsanti selezionati nei riquadri azioni sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

6. Ricordarsi di fare clic sul pulsante **Aggiorna** per aggiornare il calcolo ogni volta che si apportano modifiche attivando o disattivando i pulsanti **Raggruppa per**, oppure eseguendo un calcolo per un nuovo periodo.

7. Fare clic su **Stato** se si desidera creare un nuovo calcolo dello stato della manutenzione.

>[!NOTE]
>I risultati visualizzati in **Stato della manutenzione** includono solo le richieste di intervento di manutenzione e gli ordini di lavoro che hanno una data di inizio e di fine effettive. La data e l'ora di fine possono essere vuote.

*Esempio 1:*

Nella figura seguente, i pulsanti **Mese** e **Anno** sono stati attivati. In questo caso, si ha una panoramica generale su base mensile del carico di lavoro e della produttività relativi alle richieste di intervento di manutenzione e agli ordini di lavoro. 

![Figura 1](media/13-controlling-and-reporting.png)

*Esempio 2:*

Nella figura seguente, sono state aggiunte le informazioni sulle unità funzionali. A questo punto, è possibile confrontare il carico di lavoro e la produttività nelle unità funzionali, che possono rappresentare le ubicazioni geografiche, gli stabilimenti o le aree di lavoro. 

![Figura 2](media/14-controlling-and-reporting.png)

