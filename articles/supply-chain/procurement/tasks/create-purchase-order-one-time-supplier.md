---
title: Creare un ordine fornitore per un fornitore occasionale
description: Questa procedura indica come creare un ordine fornitore per un fornitore occasionale.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c4885547cdf2f8496446761e27ce39e67e670f15
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016404"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Creare un ordine fornitore per un fornitore occasionale

[!include [banner](../../includes/banner.md)]

Questa procedura indica come creare un ordine fornitore per un fornitore occasionale. Il fornitore è creato automaticamente con l'ordine fornitore, piuttosto che dover creare manualmente il conto fornitore. Gli ordini acquisti sono in genere creati da un addetto agli acquisti. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. È un prerequisito che un conto fornitore occasionale sia stato impostato nella pagina Parametri contabilità fornitori.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Creare un ordine fornitore per un fornitore occasionale
1. Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Selezionare Sì nel campo Fornitore occasionale.
    * Un conto fornitore viene automaticamente creato ed assegnato all'ordine fornitore. Il conto fornitore è creato in base al modello che è specificato nella scheda generale nella pagina Parametri contabilità fornitori.  
4. Nel campo Nome digitare un nome univoco per il fornitore.
5. Fare clic su OK.
    * L'ordine fornitore può ora essere completato ed elaborato come qualunque altro ordine. Non ci sono caratteristiche speciali relative a come questo è fatto. La fattura contabilizzerà una transazione dovuta sul conto fornitore che è stato creato con l'ordine ed il pagamento poi sarà elaborato.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]