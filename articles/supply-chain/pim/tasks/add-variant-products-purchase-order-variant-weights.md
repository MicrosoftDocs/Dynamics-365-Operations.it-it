---
title: Aggiungere prodotti varianti agli ordini fornitore tramite pesi varianti
description: In questa procedura vengono descritti i passaggi per utilizzare i pesi varianti per popolare automaticamente le righe ordine fornitore per ogni variante di un prodotto.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0199f4b05c23eec5c03c770c37111a6ee6d13efe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208388"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>Aggiungere prodotti varianti agli ordini fornitore tramite pesi varianti

[!include [banner](../../includes/banner.md)]

In questa procedura vengono descritti i passaggi per utilizzare i pesi varianti per popolare automaticamente le righe ordine fornitore per ogni variante di un prodotto. Quando si seleziona la quantità del prodotto che si desidera acquistare, le righe ordine fornitore vengono create per tutte le varianti del prodotto con le quantità suggerite in base ai pesi configurati nelle varianti prodotto. Questa procedura non include i passaggi per configurare i valori di peso nelle dimensioni prodotto e nelle varianti prodotto. Questa procedura utilizza i dati dimostrativi della società USRT.

1. Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Attivare/disattivare l'espansione della sezione Generale.
6. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco trovare e selezionare il record desiderato.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Fare clic su OK.
12. Attivare/disattivare l'espansione della sezione Dettagli riga.
13. Fare clic sulla scheda Varianti.
14. Fare clic su Aggiungi riga.
15. Nell'elenco contrassegnare la riga selezionata.
16. Nel campo Numero articolo digitare '0140'.
17. Impostare la quantità su "1000".
18. Fare clic su Salva.

