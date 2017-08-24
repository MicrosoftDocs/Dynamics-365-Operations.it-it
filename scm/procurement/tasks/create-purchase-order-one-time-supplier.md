--- 
title: Creare un ordine fornitore per un fornitore occasionale
description: Questa procedura indica come creare un ordine fornitore per un fornitore occasionale.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 580dfe3680c36a32a24999bc8c266a38a07177fd
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Creare un ordine fornitore per un fornitore occasionale

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura indica come creare un ordine fornitore per un fornitore occasionale. Il fornitore è creato automaticamente con l'ordine fornitore, piuttosto che dover creare manualmente il conto fornitore. Gli ordini acquisti sono in genere creati da un addetto agli acquisti. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. È un prerequisito che un conto fornitore occasionale sia stato impostato nella pagina Parametri contabilità fornitori.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Creare un ordine fornitore per un fornitore occasionale
1. Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Selezionare Sì nel campo Fornitore occasionale.
    * Un conto fornitore viene automaticamente creato ed assegnato all'ordine fornitore. Il conto fornitore è creato in base al modello che è specificato nella scheda generale nella pagina Parametri contabilità fornitori.  
4. Nel campo Nome digitare un nome univoco per il fornitore.
5. Fare clic su OK.
    * L'ordine fornitore può ora essere completato ed elaborato come qualunque altro ordine. Non ci sono caratteristiche speciali relative a come questo è fatto. La fattura contabilizzerà una transazione dovuta sul conto fornitore che è stato creato con l'ordine ed il pagamento poi sarà elaborato. Quando questo è completato, il conto fornitore può essere eliminato. Ciò viene in genere eseguito dal reparto contabilità fornitori.  


