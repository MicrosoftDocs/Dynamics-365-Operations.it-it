---
title: Dichiarazione di un ordine di produzione come finito
description: Questa procedura indica come dichiarare un ordine di produzione come finito.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa27691942b27886e85c52b7b3a736a62db7b7bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580602"
---
# <a name="report-a-production-order-as-finished"></a>Dichiarazione di un ordine di produzione come finito

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]