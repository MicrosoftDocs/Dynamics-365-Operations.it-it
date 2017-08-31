--- 
title: Imposta i periodi di liquidazione IVA
description: I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata.
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7aa40362278a0a032e909574a59f842840fb9860
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a>Imposta i periodi di liquidazione IVA

[!include[task guide banner](../../includes/task-guide-banner.md)]

I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata. Un processo di liquidazione può essere eseguito per un periodo di liquidazione per un intervallo di date specifico. Tutti i codici IVA associati al periodo di liquidazione verranno liquidati. A seconda dell'impostazione dell'ufficio IVA correlato, la soggettività tributaria viene registrata in un conto fornitore o CoGe.



In questa attività viene utilizzata la società dimostrativa USMF.



1. Andare a Imposta > Imposte indirette > IVA > Periodi liquidazione IVA.
2. Fare clic su Nuovo.
3. Nel campo Periodo di liquidazione digitare un calore.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Ufficio selezionare l'ufficio IVA che riceve i report e i pagamenti creati per il periodo di liquidazione.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo Termini di pagamento fare clic sul pulsante a discesa per aprire la ricerca.
    * L'ufficio IVA relativo può essere impostato come fornitore e la liquidazione VAT creerà una fattura fornitore aperta. Termini di pagamento definisce la data di scadenza della fattura fornitore aperta.  
9. Nell'elenco trovare e selezionare il record desiderato.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Selezionare un tipo per gli intervalli del periodo di liquidazione.
12. Immettere il numero di unità dell'intervallo periodico per periodo. Ad esempio, un trimestre ha 3 mesi.
13. Selezionare o deselezionare la casella di controllo Utilizza elaborazione batch per liquidazione IVA.
    * Il processo di liquidazione per il periodo di liquidazione può essere elaborato come processo batch in background. Si consigliano tantissime transazioni IVA all'interno di un intervallo periodico.  
14. Espandere la scheda Intervalli periodici.
15. Scegliere Aggiungi.
16. Nell'elenco contrassegnare la riga selezionata.
17. Immettere una data nel campo Dal.
18. Nel campo Data finale immettere una data.
19. Fare clic su Nuovo intervallo periodico.
    * Una volta che il primo intervallo periodico è stato immesso, i nuovi periodi possono essere creati automaticamente. È possibile tornare e aggiungere nuovi intervalli periodici in base alle esigenze.  
20. Chiudere la pagina.


