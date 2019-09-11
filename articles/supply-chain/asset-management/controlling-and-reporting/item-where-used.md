---
title: Utilizzo dell'articolo
description: In questo argomento viene descritto come ottenere una panoramica sull'utilizzo di un articolo in Gestione cespiti.
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
ms.openlocfilehash: 84ab803aedf5b803b6c5f39ff1907726335cb45d
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918328"
---
# <a name="item-where-used"></a>Utilizzo dell'articolo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

È possibile eseguire un calcolo relativo a un articolo specifico per ottenere una panoramica dell'utilizzo dell'articolo in Gestione cespiti. I risultati visualizzano il contesto in cui l'articolo è stato utilizzato durante il relativo ciclo di vita. La pagina **Utilizzo dell'articolo** può essere aperta dal menu Gestione cespiti principale nonché dalle pagine seguenti:

[DBA cespiti](../objects/object-BOM.md)

[Pezzi di ricambio in valori predefiniti di tipo di cespite](../setup-for-objects/object-types.md)

[Previsione articolo nella previsione di valori predefiniti di tipo di processo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

[Previsioni di manutenzione dell'ordine di lavoro](../work-orders/maintenance-forecasts.md)

[Richiesta di acquisto ordine di lavoro](../work-orders/procurement.md)

[Acquisto ordine di lavoro](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Eseguire un calcolo Utilizzo dell'articolo

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Utilizzo dell'articolo** o selezionare il pulsante **Utilizzo dell'articolo** in una delle pagine menzionate sopra.

2. Nella finestra di dialogo **Utilizza dell'articolo**, selezionare l'articolo per il quale si desidera eseguire il calcolo nel campo **Numero articolo**.

3. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe articolo in relazione alle unità funzionali. Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe articolo di un'unità funzionale saranno visualizzate nel livello principale. Di conseguenza, la relazione/quantità di una riga può essere aggiunta dalle unità funzionali in un livello inferiore. Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe articolo in tutti i livelli di unità funzionali a cui sono correlate.

4. Nella sezione **Includi** selezionare gli interruttori su "Sì" che si desidera includere nel calcolo.

5. Fare clic su **OK** per avviare il calcolo.

6. Nella scheda **Utilizzo dell'articolo** > gruppi di riquadri azioni **Raggruppa per**, selezionare i pulsanti pertinenti per visualizzare il livello di dettagli necessario per il calcolo. I pulsanti selezionati nei riquadri azioni sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

7. Se si desidera visualizzare le dimensioni relative all'articolo, fare clic su **Visualizza dimensioni** e selezionare le dimensioni da visualizzare.

Nella figura seguente, viene visualizzato un esempio di un calcolo Utilizzo dell'articolo per l'articolo numero "1000".

![Figura 1](media/12-controlling-and-reporting.png)

