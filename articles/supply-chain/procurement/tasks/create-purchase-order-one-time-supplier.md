---
title: Creare un ordine fornitore per un fornitore occasionale
description: Questa procedura indica come creare un ordine fornitore per un fornitore occasionale.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ffb6515d8f24df68efbce265d98ed4e64e8d6b07
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677424"
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