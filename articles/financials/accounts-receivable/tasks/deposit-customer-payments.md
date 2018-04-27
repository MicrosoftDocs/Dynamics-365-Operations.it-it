--- 
title: Depositare pagamenti clienti
description: Depositare pagamenti cliente.
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dbf21bd5df70cd80e4fe3f2f5d699aa82b62423b
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="deposit-customer-payments"></a>Depositare pagamenti clienti

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Depositare pagamenti cliente. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
4. Selezionare il giornale di registrazione pagamento. 
5. Fare clic su Righe.
6. Nel campo Conto selezionare il cliente per il quale si sta registrando il pagamento.
7. Nel campo Avere, immettere l'importo del pagamento.
    * È possibile scegliere di lasciare l'importo vuoto e farlo calcolare dal sistema selezionando le fatture che sono state pagate.  
8. Digitare un valore nel campo Riferimento di pagamento.
    * Il riferimento di pagamento può essere il numero di assegno per il pagamento che si immette. Il riferimento di pagamento è necessario per includere il pagamento in una distinta di deposito.  
9. Contrassegnare la casella Utilizzo di una distinta di deposito.
    * Se il pagamento deve essere incluso nel deposito, modificare questa impostazione su Sì.  
10. Fare clic su Nuovo.
11. Nel campo Conto selezionare il cliente per il pagamento successivo.
12. Nel campo Avere, immettere l'importo del pagamento.
13. Digitare un valore nel campo Riferimento di pagamento.
14. Contrassegnare la casella Utilizzo di una distinta di deposito.
15. Fare clic su Registra.
    * I pagamenti devono essere registrati prima che la distinta di deposito possa essere generata. In questo modo è possibile garantire che i pagamenti non cambino dopo che la distinta di deposito viene generata.  
16. Fare clic su Funzioni.
17. Fare clic su Distinta di deposito.
18. Fare clic su OK.
    * La prima pagina viene utilizzata per creare la distinta di deposito.  
19. Fare clic su OK.
    * Il secondo passaggio è di stampare la distinta di deposito, ma questo passaggio non è obbligatorio.  


