---
title: Controllo delle ore lavorative
description: In questo articolo viene descritto il controllo delle ore lavorative in Gestione cespiti.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetHourControl
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f5f5dbb23c4d6c86bee7612c4ade65ef4b1cee8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869751"
---
# <a name="work-hour-control"></a>Controllo delle ore lavorative

[!include [banner](../../includes/banner.md)]

 

In Gestione cespiti, è possibile calcolare le ore per ottenere una panoramica delle ore effettive comparate alle ore di budget in cespiti, unità funzionali o ordini di lavoro. Le ore effettive sono basate sulle transazioni registrate.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Controllo delle ore lavorative per cespiti, unità funzionali e ordini di lavoro

I calcoli effettuati per cespiti, aree funzionali e ordini di lavoro sono quasi identici. La sola differenza è che per i cespiti e le unità funzionali, è possibile includere cespiti secondari e ubicazioni secondarie nel calcolo. La data è quella di transazione alla quale la registrazione è stata registrata.

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Controllo ore cespiti** o **Controllo ore unità funzionali** o **Gestione cespiti** > **Richieste di informazioni** > **Ordini di lavoro** > **Controllo ore ordini di lavoro**.

2. Nella finestra di dialogo **Controllo ore cespiti**.

3. Nella finestra di dialogo **Controllo ore cespiti** / **Controllo ore unità funzionali** / **Controllo ore ordini di lavoro**, selezionare un periodo da calcolare nei campi **Dal** e **Al**.

4. Se necessario, selezionare un **Set di dimensioni finanziarie** da includere nel calcolo.

5. Impostare l'interruttore **Ignora lo zero** su "Sì" se non si desidera visualizzare i risultati contenenti zero ore.

6. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe del controllo delle ore in relazione alle unità funzionali. 

    Ad esempio, se si inserisce "1" nel campo e si ha una gerarchia di unità funzionali multilivello, tutte le righe di controllo delle ore di un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore. 
    
    Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del controllo delle ore in tutti i livelli di unità funzionali a cui sono correlate.

7. Impostare l'interruttore **Includere cespiti secondari** su "Sì" per visualizzare i costi correlati ai cespiti secondari come righe separate.

8. Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti/unità funzionali/ordini di lavoro nella Scheda dettaglio **Record da includere**.

9. Fare clic su **OK** per avviare il calcolo.

10. Nella pagina **Controllo ore cespiti**, fare clic sul pulsante **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo. I pulsanti **Raggruppa per** selezionati sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

## <a name="example"></a>Esempio

Nella schermata seguente viene illustrato un esempio di calcolo **Controllo ore cespiti**.

- Nel campo **Budget originale** sono visualizzate le ore di budget della previsione dell'ordine di lavoro. 
- Nel campo **Ore effettive** sono visualizzate le ore registrate negli ordini di lavoro. 
- Nel campo **Ore impegnate** sono visualizzate le ore totali della società in relazione agli ordini di lavoro.

![Esempio di calcolo di controllo ore cespiti.](media/04-controlling-and-reporting.png)

Un altro metodo di eseguire un calcolo delle ore è la selezione di molteplici cespiti in **Tutti i cespiti** o **Cespiti attivi**. Quindi fare clic sul pulsante **Controllo ore** nella Scheda dettaglio **Generale**. I cespiti selezionati vengono inseriti automaticamente nel campo **Cespite** della Scheda dettaglio **Record da includere**. Fare clic su **OK** nella finestra di dialogo **Controllo ore cespiti** e viene visualizzato il calcolo dei cespiti selezionati. La stessa procedura può essere eseguita per le unità funzionali in **Tutte le unità funzionali** o **Unità funzionali attive** e per gli ordini di lavoro in **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]