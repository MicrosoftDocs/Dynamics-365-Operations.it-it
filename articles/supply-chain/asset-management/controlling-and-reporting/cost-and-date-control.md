---
title: Controllo dei costi e delle date
description: In questo argomento viene descritto il controllo dei costi e delle date in Gestione cespiti.
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
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918397"
---
# <a name="cost-and-date-control"></a>Controllo dei costi e delle date

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

In Gestione cespiti, è possibile calcolare i costi per ottenere una panoramica dei costi effettivi comparati ai costi in budget in cespiti, unità funzionali e ordini di lavoro. I costi effettivi sono basati sulle transazioni registrate. È inoltre possibile eseguire un calcolo delle date se si desidera confrontare le date di inizio e fine programmate alle date di inizio e di fine effettive negli ordini di lavoro.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Controllo dei costi per cespiti, unità funzionali e ordini di lavoro

I calcoli effettuati per cespiti, aree funzionali e ordini di lavoro sono quasi identici. La sola differenza è che per i cespiti e le unità funzionali, è possibile includere cespiti secondari e ubicazioni secondarie nel calcolo. La data è quella di transazione alla quale la registrazione è stata registrata.

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Controllo costi cespiti** o **Controllo costi unità funzionali** o **Gestione cespiti** > **Richieste di informazioni** > **Ordini di lavoro** > **Controllo costi ordini di lavoro**.

2. Nella finestra di dialogo **Controllo costi cespiti** / **Controllo costi unità funzionali** / **Controllo costi ordini di lavoro**, selezionare un periodo da calcolare.

3. Se necessario, selezionare un set di dimensioni finanziarie da includere nel calcolo.

4. Impostare l'interruttore **Ignora lo zero** su "Sì" se non si desidera visualizzare i risultati con un costo zero.

5. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe del controllo dei costi in relazione alle unità funzionali. Ad esempio, se si inserisce "1" nel campo e si ha una gerarchia di unità funzionali multilivello, tutte le righe di controllo dei costi di un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore. Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del controllo dei costi in tutti i livelli di unità funzionali a cui sono correlate.

6. Impostare l'interruttore **Mostra costo impegnato aperto** su "Sì" se si desidera includere quella colonna nel calcolo.

7. Impostare l'interruttore **Includere cespiti secondari** su "Sì" per visualizzare i costi correlati ai cespiti secondari come righe separate.

8. Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti/unità funzionali/ordini di lavoro nella Scheda dettaglio **Record da includere**.

9. Fare clic su **OK** per avviare il calcolo.

Nella figura seguente viene illustrato un esempio della finestra di dialogo **Controllo costi cespiti**.

![Figura 1](media/01-controlling-and-reporting.png)

10. Nei gruppi di riquadri azioni **Raggruppa per** nella pagina **Controllo costi cespiti**, fare clic sui pulsanti pertinenti per visualizzare il livello di dettagli necessario del calcolo. I pulsanti selezionati nei riquadri azioni sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

Nella figura seguente viene illustrato un esempio di risultati di calcolo in **Controllo costi cespiti**.

![Figura 2](media/02-controlling-and-reporting.png)

Un altro metodo di eseguire un calcolo dei costi è la selezione di molteplici cespiti in **Tutti i cespiti** o **Cespiti attivi**. Quindi, fare clic sul pulsante **Controllo costi** nella scheda **Generale**. Nella finestra di dialogo **Controllo costi cespiti**, i cespiti selezionati vengono inseriti automaticamente nel campo **Cespite** della Scheda dettaglio **Record da includere**. Fare clic **OK**. Viene visualizzato un calcolo dei costi per i cespiti selezionati. La stessa procedura può essere eseguita per le unità funzionali in **Tutte le unità funzionali** o **Unità funzionali attive** e per gli ordini di lavoro in **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

>[!NOTE]
>Nel campo **Budget originale** sono visualizzati i costi in budget della previsione dell'ordine di lavoro. Il campo **Costo impegnato** mostra l'importo totale delle spese che una persona giuridica si è impegnata a pagare. Nel campo **Costo impegnato aperto** sono visualizzati gli impegni per il pagamento di articoli, ore e servizi ordinati o ricevuti ma non ancora pagati. Quando tutte le registrazioni del consumo sono state registrate i costi correlati sono inclusi nel campo **Costo effettivo**.

## <a name="work-order-date-control"></a>Controllo data dell'ordine di lavoro

Utilizzare questa pagina per ottenere una panoramica delle date di inizio e di fine previste comparate alle date di inizio e di fine negli ordini di lavoro.

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Ordini di lavoro** > **Controllo date ordini di lavoro**.

2. Fare clic su **Calcola**.

3. Selezionare un'unità funzionale nel campo **Unità funzionale**.

4. Inserire il periodo per il quale si desidera eseguire il calcolo nei campi **Dal** e **Al**. Verranno inclusi tutti gli ordini di lavoro con la data di inizio prevista entro quel periodo.

5. Fare clic su **OK**.

6. Nei gruppi di riquadri azioni **Raggruppa per**, fare clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo. I pulsanti selezionati nei riquadri azioni sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

Nella figura seguente viene illustrato un esempio di risultati di calcolo in **Controllo date ordini di lavoro**.

![Figura 3](media/03-controlling-and-reporting.png)

- Il campo **Ritardo inizio medio** visualizza la differenza in giorni tra la data di inizio programmata per un ordine di lavoro rispetto alla data di inizio effettiva. Se, ad esempio, la data di inizio effettiva è due giorni prima la data di inizio programmata, in questo campo viene visualizzato "- 2".  
- Il campo **Ritardo fine medio** visualizza la differenza in giorni tra la data di fine programmata per un ordine di lavoro rispetto alla data di fine effettiva. Se, ad esempio, la data di fine effettiva è tre giorni dopo la data di fine programmata, in questo campo viene visualizzato "3".  
- I campi **Occorrenze** mostrano il numero di scostamenti in relazione alla data di inizio programmata ed effettiva e alla data di fine programmata ed effettiva nell'ordine di lavoro.

