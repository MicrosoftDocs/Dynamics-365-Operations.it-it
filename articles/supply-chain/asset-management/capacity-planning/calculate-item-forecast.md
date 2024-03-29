---
title: Calcolare le previsioni articolo
description: In questo articolo viene descritto come calcolare le previsioni articolo in Gestione cespiti.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 25e9b00533fb183b27c1bbe616cf6f414b44b5e7
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016103"
---
# <a name="calculate-item-forecast"></a>Calcolare le previsioni articolo

[!include [banner](../../includes/banner.md)]

 

Esattamente come è possibile eseguire i calcoli del carico di capacità, descritti nella sezione precedente, è possibile eseguire i calcoli della previsioni articolo in:

- righe di programma di manutenzione  
- ordini di lavoro non ancora programmati  
- ordini di lavoro programmati

Questa funzionalità è utile se si desidera ottenere una panoramica del consumo previsto degli articoli (pezzi di ricambio nonché altri articoli necessari per il completamento degli ordini di lavoro) per un periodo specifico. Il calcolo delle previsioni articolo può essere eseguito in tutti i cespiti o nei cespiti selezionati. È inoltre possibile eseguire un calcolo in un'attività dei tempi di fermo per la manutenzione (**Tutte le attività tempi di fermo per manutenzione** o **Attività tempi di fermo per manutenzione attive**) oppure in un pool di ordini di lavoro (**Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**).

1. Fai clic su **Gestione cespiti** > **Richieste di informazion** > **Previsione articolo**, o **Gestione cespiti** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** / **Pool di ordini di lavoro attivi** > seleziona il pool degli ordini di lavoro nell'elenco > pulsante **Previsione articolo** o **Gestione cespiti** > **Attività tempi di fermo per manutenzione** > **Tutte le attività tempi di fermo per manutenzione** / **Attività tempi di fermo per manutenzione attive** >seleziona l'attività dei tempi di fermo per la manutenzione nell'elenco > pulsante **Previsione articolo**.

2. Nella finestra di dialogo **Calcolare previsioni articolo** selezionare un periodo per il calcolo nei campi **Data/ora di inizio** e **Data/ora di fine**.

3. Impostare l'interruttore **Includi programma di manutenzione** su "Sì" se si desidera includere le righe di programma di manutenzione nel calcolo delle previsioni.

4. Impostare l'interruttore **Includi ordine di lavoro** su "Sì" se si desidera includere processi di ordine di lavoro nel calcolo delle previsioni.

5. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe di previsione articolo in relazione alle unità funzionali. 

      Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di programma di manutenzione e gli ordini di lavoro per un'unità funzionale verranno visualizzati nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali che si trovano in un livello inferiore. 
  
      Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di programma di manutenzione e tutti gli ordini di lavoro in tutti i livelli di unità funzionali a cui sono correlati.

6. Fare clic su **OK** per avviare il calcolo.

7. Nei gruppi **Raggruppa per**, fare clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo. Nel schermata di seguito, i pulsanti selezionati **Raggruppa per** sono evidenziati nel colore blu. Fare clic su un pulsante per attivarlo o disattivarlo.

8. Fare clic sul pulsante **Visualizza dimensioni** se si desidera visualizzare il prodotto, l'immagazzinamento o le dimensioni di tracciabilità correlati agli articoli. Selezionare le casella di controllo pertinenti, quindi fare clic su **OK**.

![Figura 1.](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]