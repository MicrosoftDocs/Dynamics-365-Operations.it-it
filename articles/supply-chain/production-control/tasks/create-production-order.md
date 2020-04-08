---
title: Creare un ordine di produzione
description: Questa procedura indica come creare un ordine di produzione.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aaef3ed01573c10bc15c6768f13c1bf0151d212d
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149276"
---
# <a name="create-a-production-order"></a>Creare un ordine di produzione

[!include [banner](../../includes/banner.md)]

Questa procedura indica come creare un ordine di produzione. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Si tratta della prima procedura su sette che spiega il ciclo di vita dell'ordine di produzione.


## <a name="create-a-production-order"></a>Creare un ordine di produzione
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
2. Fare clic su Nuovo ordine di produzione.
3. Nel campo Numero articolo digitare "D0001".
4. Immettere una data nel campo Consegna.
    * La data di consegna indica se l'ordine di produzione deve terminare per consegnare in tempo. Questa data può essere utilizzata nel processo di programmazione. Ad esempio, è possibile programmare l'ordine a ritroso dalla data di consegna.  
5. Impostare la quantità su "20".
    * Nota: nel campo Numero DBA verrà visualizzato automaticamente il numero di qualsiasi DBA attiva per l'articolo corrente, ma è possibile modificare la DBA per l'ordine di produzione selezionando una DBA attiva dall'elenco delle versioni DBA approvate.    Nel campo Numero ciclo di lavorazione verrà visualizzato automaticamente il numero di qualsiasi ciclo di lavorazione attivo per l'articolo corrente, ma è possibile modificare il ciclo di lavorazione per l'ordine di produzione selezionando un ciclo di lavorazione attivo dall'elenco delle versioni cicli di lavorazione approvati.  
6. Fare clic su Crea.

## <a name="validate-the-production-order"></a>Convalida l'ordine di produzione
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Fare clic sul collegamento relativo al numero dell'ordine di produzione appena creato. Verrà aperta la pagina dei dettagli dell'ordine.  
2. Fare clic su Modifica.
3. Immettere una data nel campo Consegna.
    * Ad esempio, è possibile modificare la data di consegna per l'ordine di produzione.  
4. Fare clic su Salva.
5. Chiudere la pagina.

## <a name="update-the-bom"></a>Aggiorna la DBA
1. Nel riquadro azioni fare clic su Ordine di produzione.
2. Fare clic su DBA.
    * Aprire la pagina DBA per convalidare i dati DBA che sono stati copiati dai dati predefiniti quando l'ordine di produzione è stato creato. In questa procedura, è necessario aggiornare la quantità per una DBA.  
3. Fare clic su Modifica.
4. Nel campo Quantità immettere un numero.
    * La modifica della quantità nella riga DBA influisce sulla stima dei costi del consumo di materiali per l'ordine di produzione.  
5. Fare clic su Salva.
6. Chiudere la pagina.

## <a name="update-the-production-route"></a>Aggiorna il ciclo di lavorazione produzione
1. Nel riquadro azioni fare clic su Ordine di produzione.
2. Fare clic su Ciclo di lavorazione.
    * Aprire la pagina Ciclo di lavorazione per convalidare i dati del ciclo di lavorazione produzione copiati dai dati predefiniti quando l'ordine è stato creato. In questa procedura, è necessario aggiornare la quantità per una delle operazioni nel ciclo di lavorazione produzione.  
3. Nell'elenco trovare e selezionare il record desiderato.
4. Fare clic su Modifica.
5. Nel campo Qtà lavorazione immettere un numero.
    * La modifica del tempo di elaborazione influisce sul consumo del ciclo di lavorazione stimato e sul costo dell'ordine di produzione.  
6. Fare clic su Salva.
7. Chiudere la pagina.

