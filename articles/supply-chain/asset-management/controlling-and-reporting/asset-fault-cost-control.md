---
title: Controllo costo degli errori dei cespiti
description: In questo argomento viene descritto il controllo dei costi relativi agli errori di cespite in Gestione cespiti.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 44b101c3b386c3edd8aec4c44e8ee834519718ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811184"
---
# <a name="asset-fault-cost-control"></a>Controllo costo degli errori dei cespiti

[!include [banner](../../includes/banner.md)]

 

In Gestione cespiti, è possibile calcolare i costi nelle registrazioni di errore di cespite per ottenere una panoramica dei costi effettivi rispetto ai costi in budget. I costi effettivi sono basati sulle transazioni registrate. La data è quella in cui il sintomo dell'errore è stato registrato.

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Controllo costo degli errori dei cespiti**.

2. Nella finestra di dialogo **Controllo costo degli errori dei cespiti**, selezionare un set di dimensioni finanziarie da includere nel calcolo, se necessario.

4. Impostare l'interruttore **Ignora lo zero** su "Sì" se non si desidera visualizzare i risultati con un costo zero.

5. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe del controllo dei costi in relazione alle unità funzionali. 

    Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe del controllo dei costi relativi agli errori di cespite per un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali in un livello inferiore. 
    
    Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del controllo dei costi degli errori di cespite in tutti i livelli di unità funzionali a cui sono correlate.

6. Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti, date di errore e cause di errore nella Scheda dettaglio **Record da includere**.

7. Fare clic su **OK** per avviare il calcolo.

8. Fare clic sui pulsanti **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo. I pulsanti **Raggruppa per** selezionati sono evidenziati. Fare clic su un pulsante per attivarlo o disattivarlo.

## <a name="example"></a>Esempio

In questo esempio viene illustrato un calcolo del controllo costi dell'errore cespiti.

- Nel campo **Budget originale** sono visualizzati i costi in budget della previsione dell'ordine di lavoro. 
- Nel campo **Costo effettivo** sono visualizzati i costi registrati negli ordini di lavoro. 
- Nel campo **Costo impegnato** sono visualizzati i costi totali della società in relazione agli ordini di lavoro.

    ![Figura 1](media/05-controlling-and-reporting.png)

Per informazioni su come impostare gli errori, fare riferimento alla sezione [Gestione errori](../setup-for-work-orders/fault-management.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]