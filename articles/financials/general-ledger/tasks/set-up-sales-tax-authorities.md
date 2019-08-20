---
title: Impostazione degli uffici IVA
description: Gli uffici IVA sono entità in cui l'IVA deve essere dichiarata e pagata.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb0b30be91e33cb50af0ae5c2e4dcd75bd12599b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846321"
---
# <a name="set-up-sales-tax-authorities"></a>Impostazione degli uffici IVA

[!include [task guide banner](../../includes/task-guide-banner.md)]

Gli uffici IVA sono entità in cui l'IVA deve essere dichiarata e pagata. È possibile pagare l'IVA all'ufficio direttamente o tramite un conto fornitore creato per l'ufficio IVA. In questo caso la società potrà utilizzare la routine di pagamento abituale per effettuare il pagamento all'ufficio IVA entro i termini previsti. Se non si imposta l'ufficio IVA come fornitore, sarà necessario preparare un pagamento manuale per l'ufficio IVA nella data di scadenza appropriata. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a Imposta > Imposte indirette > IVA > Uffici IVA.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Ufficio.
4. Digitare un valore nel campo Nome.
5. Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Selezionare il layout del report per il paese, se disponibile. Se i layout del report non corrispondono ai requisiti dell'ufficio IVA, utilizzare il layout predefinito.
9. Immettere i valori nei campi Tipo di arrotondamento e Arrotondamento per specificare come l'importo totale IVA da pagare deve essere arrotondato. Tutte le differenze di arrotondamento verranno registrate nei conti per l'impostazione di transazioni automatiche nella contabilità generale.
10. Immettere un numero nel campo Arrotondamento.
11. Fare clic su Salva.

