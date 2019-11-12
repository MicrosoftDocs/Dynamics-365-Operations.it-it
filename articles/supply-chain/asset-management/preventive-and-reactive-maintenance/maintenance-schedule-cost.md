---
title: Costo del programma di manutenzione
description: In questo argomento viene descritto il costo del programma di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.openlocfilehash: b30fa3c142057b43202a8f5a323c0b425865e971
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571325"
---
# <a name="maintenance-schedule-cost"></a>Costo del programma di manutenzione

[!include [banner](../../includes/banner.md)]

 

In Gestione cespiti, è possibile calcolare i costi in budget nelle righe di programma di manutenzione. Questa funzionalità è utile se si desidera ottenere una panoramica dei costi previsti, ad esempio, i costi relativi ai processi di manutenzione preventiva pianificati per l'anno successivo. I calcoli si basano sulle righe di programma di manutenzione esistenti di tipo "Piani di manutenzione ", "Cicli di manutenzione" e "Richiesta di intervento di manutenzione".

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Costo del programma di manutenzione**.

2. Nella finestra di dialogo **Costo del programma di manutenzione**, è possibile selezionare **Set di dimensioni finanziarie** se si desidera visualizzare i costi raggruppati in dimensioni finanziarie.

>[!NOTE]
>I set di dimensioni finanziarie sono impostati in **Contabilità generale** > **Piano dei conti** > **Dimensioni** > **Set di dimensioni finanziarie**.

3. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe di programma di manutenzione in relazione alle unità funzionali. Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di programma di manutenzione per un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore. Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di programma di manutenzione in tutti i livelli di unità funzionali a cui sono correlate.

4. Se si desidera eseguire un calcolo per specifici cespiti, fare clic su **Filtro** nella Scheda dettaglio **Record da includere** e selezionare i cespiti pertinenti. Se necessario, è anche possibile specificare uno **Stato** diverso o una **Data di inizio prevista** per il calcolo dei costi.

5. Scegliere **OK** per avviare il ricalcolo del costi.

6. Nella scheda **Costo del programma di manutenzione** > nei gruppi di riquadri azioni **Raggruppa per**, fare clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo dei costi. I pulsanti del gruppo di riquadri azioni selezionati sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

7. Fare clic sul pulsante **Calcola costo** se si desidera eseguire un nuovo calcolo dei costi.

Nella figura seguente vengono illustrati i risultati di un calcolo del costo del programma di manutenzione.

![Figura 1](media/17-preventive-maintenance.png)
