---
title: Impostare le spese accessorie per l'hub e le spese accessorie principali
description: Questa procedura mostra come creare spese accessorie principali per un hub e come utilizzare tali dati per creare spese accessorie per l'hub.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ea59326a85d97d53795104f80486f2fac24148a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148526"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Impostare le spese accessorie per l'hub e le spese accessorie principali

[!include [banner](../../includes/banner.md)]

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

