---
title: Liquidare un assegno postdatato per un fornitore
description: Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e3816a2f1c95d568a173cb07daad0473703da9c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779503"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidare un assegno postdatato per un fornitore

[!include [banner](../../includes/banner.md)]

Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca. 

Completare le seguenti procedure prima di iniziare la presente.

1) Impostare gli assegni postdatati

2) Registrare un assegno postdatato per un fornitore



Il ruolo di questa procedura è Tesoriere. Questa procedura utilizza la società dimostrativa USMF.

1. Andare a **Contabilità fornitori > Pagamenti > Assegni postdatati fornitore**.
2. Fare clic su **Liquida**.
3. Fare clic su **Liquida voci di compensazione**.
    * Liquidare il conto fornitore per la transazione assegno.  
4. Chiudere la pagina.
5. Fare clic su **Contabilità generale > Scritture contabili > Giornali di registrazione generali**.
6. Nel campo **Mostra**, selezionare **Tutto**.
7. Selezionare o deselezionare la casella di controllo **Mostra solo giornali creati dall'utente**.
8. Nell'elenco contrassegnare la riga selezionata.
9. Fare clic su **Righe**.
10. Fai clic su **Giustificativo**.
11. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
