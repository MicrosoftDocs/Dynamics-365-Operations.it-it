--- 
title: Impostare le spese accessorie per l'hub e le spese accessorie principali
description: Questa procedura mostra come creare spese accessorie principali per un hub e come utilizzare tali dati per creare spese accessorie per l'hub.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6381416640ffacf0a9d96d7da96bc33612ca7137
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Impostare le spese accessorie per l'hub e le spese accessorie principali

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come creare spese accessorie principali per un hub e come utilizzare tali dati per creare spese accessorie per l'hub. La procedura utilizza il set di dati di USMF. Questa impostazione viene in genere eseguita dal coordinatore dei trasporti.


## <a name="set-up-a-hub-master"></a>Impostare un hub principale
1. Andare a Gestione trasporto > Impostazioni > Valutazione > Rappresentazioni generali accessorie.
2. Fare clic su Nuovo.
3. Nel campo Spese accessorie principali digitare un valore.
4. Digitare un valore nel campo Nome.
5. Nel campo Tipo di spese accessorie selezionare "Hub".
6. Fare clic su Salva.
7. Chiudere la pagina.

## <a name="set-up-a-hub-accessorial-charge"></a>Impostare una spesa accessoria per l'hub
1. Andare a Gestione trasporto > Impostazioni > Valutazione > Spese accessorie hub.
2. Fare clic su Nuovo.
3. Nel campo ID spese accessorie hub digitare un valore.
4. Nel campo Hub fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato.
6. Selezionare un'opzione nel campo Posizione hub.
    * È possibile creare la spesa come spesa di prelievo o di consegna. A seconda della selezione, la spesa verrà applicata al segmento di trasporto corrispondente nel percorso.  
7. Nel campo Spese accessorie principali fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare i dati master creati.  
9. Fare clic su Salva.
10. Chiudere la pagina.


