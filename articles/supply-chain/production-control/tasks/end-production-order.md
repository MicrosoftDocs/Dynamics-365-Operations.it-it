---
title: Chiudere un ordine di produzione
description: Questa procedura indica come terminare un ordine di produzione.
author: johanhoffmann
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
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 1cc586f804a072ca5499c73ecdf7d37778cbf067
ms.contentlocale: it-it
ms.lasthandoff: 02/06/2018

---
# <a name="end-a-production-order"></a>Chiudere un ordine di produzione

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura indica come terminare un ordine di produzione. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Si tratta dell'ultima procedura su sette che spiega il ciclo di vita dell'ordine di produzione.


## <a name="end-a-production-order"></a>Chiudere un ordine di produzione
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
    * Selezionare un ordine di produzione con stato Dichiarato finito.  
2. Nel riquadro azioni fare clic su Ordine di produzione.
3. Fare clic su Fine.
    * In questa pagina, è possibile confermare che si desidera terminare l'ordine di produzione.  
4. Fare clic sulla scheda Generale.
5. Nel campo Data immettere una data.
6. Nel campo Metodo scarti selezionare 'Allocazione'.
    * Quando si seleziona il metodo di allocazione, i costi dei materiali scartati vengono aggiunti ai prodotti finiti.  
7. Fare clic su OK.

## <a name="validate-calculation-results"></a>Convalidare i risultati del calcolo
1. Nel riquadro azioni, fare clic su Gestisci costi.
2. Fare clic su Visualizza confronto costi.
    * Dopo aver terminato l'ordine di produzione, è possibile comparare il prezzo di costo stimato al prezzo di costo realizzato per ottenere una panoramica degli scostamenti di produzione.  

