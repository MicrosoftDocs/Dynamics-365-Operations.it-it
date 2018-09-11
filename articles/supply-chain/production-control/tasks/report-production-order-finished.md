--- 
title: Dichiarazione di un ordine di produzione come finito
description: Questa procedura indica come dichiarare un ordine di produzione come finito.
author: johanhoffmann
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: e6f5e7316f89ba7c2b7091eb9df02aa07ea44dbd
ms.contentlocale: it-it
ms.lasthandoff: 02/06/2018

---
# <a name="report-a-production-order-as-finished"></a>Dichiarazione di un ordine di produzione come finito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura indica come dichiarare un ordine di produzione come finito. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Si tratta della sesta procedura su sette che spiega il ciclo di vita dell'ordine di produzione.


## <a name="report-a-production-order-as-finished"></a>Dichiarazione di un ordine di produzione come finito
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
    * Selezionare un ordine di produzione con stato Avviato.  
2. Nel riquadro azioni fare clic su Ordine di produzione.
3. Fare clic su Dichiarazione di finito.
    * In questa pagina, è possibile confermare la quantità di prodotto finito da dichiarare come finita.  
4. Fare clic sulla scheda Generale.
5. Impostare Quantità idonea su '18'.
6. Impostare Quantità difettosa su '2'.
7. Nel campo Causa dell'errore, selezionare 'Materiale'.
8. Selezionare o deselezionare la casella di controllo Processo finale.
9. Selezionare o deselezionare la casella di controllo Accetta errore.
10. Fare clic su OK.

## <a name="verify-the-report-as-finished-journal"></a>Verificare il giornale di registrazione dichiarazioni di finito
1. Nel riquadro azioni fare clic su Visualizza.
2. Fare clic su Dichiarato finito.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Il giornale di registrazione dichiarazioni di finito è stato registrato. Se si desidera apportare rettifiche al giornale di registrazione, è possibile creare manualmente un nuovo giornale di registrazione in cui è possibile apportare modifiche.  


