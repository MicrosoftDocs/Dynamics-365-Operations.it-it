---
title: Utilizzo dell'articolo
description: In questo argomento viene descritto come ottenere una panoramica sull'utilizzo di un articolo in Gestione cespiti.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 262a5a9d83767599f6e15183d6afcacf4b5901fe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808642"
---
# <a name="item-where-used"></a>Utilizzo dell'articolo

[!include [banner](../../includes/banner.md)]

 

È possibile eseguire un calcolo relativo a un articolo specifico per ottenere una panoramica dell'utilizzo dell'articolo in Gestione cespiti. I risultati visualizzano il contesto in cui l'articolo è stato utilizzato durante il relativo ciclo di vita. La pagina **Utilizzo dell'articolo** può essere aperta dal menu Gestione cespiti principale nonché dalle pagine seguenti:

- [DBA cespiti](../objects/object-BOM.md)

- [Pezzi di ricambio in valori predefiniti di tipo di cespite](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [Categorie di tipi di processi di manutenzione e tipi di processi di manutenzione, varianti di tipo di processi di manutenzione, commerci di processi di manutenzione e ed elenchi di controllo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Previsione di manutenzione](../work-orders/maintenance-forecasts.md)

- [Approvvigionamento](../work-orders/procurement.md)

- [Acquisto ordine di lavoro](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Eseguire un calcolo Utilizzo dell'articolo

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Utilizzo dell'articolo** o selezionare il pulsante **Utilizzo dell'articolo** in una delle pagine menzionate sopra.

2. Nella finestra di dialogo **Utilizza dell'articolo**, selezionare l'articolo per il quale si desidera eseguire il calcolo nel campo **Numero articolo**.

3. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe articolo in relazione alle unità funzionali. 

    Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe articolo di un'unità funzionale saranno visualizzate nel livello principale. Di conseguenza, la relazione/quantità di una riga può essere aggiunta dalle unità funzionali in un livello inferiore. 
    
    Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe articolo in tutti i livelli di unità funzionali a cui sono correlate.

4. Nella sezione **Includi** selezionare gli interruttori su "Sì" che si desidera includere nel calcolo.

5. Fare clic su **OK** per avviare il calcolo.

6. Nella scheda **Utilizzo dell'articolo** selezionare i pulsanti **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo. I pulsanti **Raggruppa per** selezionati sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

7. Se si desidera visualizzare le dimensioni relative all'articolo, fare clic su **Visualizza dimensioni** e selezionare le dimensioni da visualizzare.

## <a name="example"></a>Esempio

Nella schermata seguente, viene visualizzato un esempio di un calcolo Utilizzo dell'articolo per l'articolo numero "1000".

![Esempio di calcolo Utilizzo dell'articolo](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]