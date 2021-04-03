---
title: Liquidare un assegno postdatato per un fornitore
description: Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d66caa83df693445c1b1d40ffdc11e8d10cf7426
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239629"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidare un assegno postdatato per un fornitore

[!include [banner](../../includes/banner.md)]

Liquidare un assegno postdatato emesso a favore di un fornitore quando la banca ha liquidato la relativa transazione dopo che l'assegno è scaduto ed è stato liquidato dalla banca. 

Completare le seguenti procedure prima di iniziare la presente.

1) Impostare gli assegni postdatati

2) Registrare un assegno postdatato per un fornitore



Il ruolo di questa procedura è Tesoriere. Questa procedura utilizza la società dimostrativa USMF.

1. Andare a Contabilità fornitori > Pagamenti > Assegni postdatati fornitore.
2. Fare clic su Liquida.
3. Fare clic su Liquida voci di compensazione.
    * Liquidare il conto fornitore per la transazione assegno.  
4. Chiudere la pagina.
5. Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.
6. Nel campo Mostra, selezionare "Tutto".
7. Selezionare o deselezionare la casella di controllo Mostra solo giornali creati dall'utente.
8. Nell'elenco contrassegnare la riga selezionata.
9. Fare clic su Righe.
10. Fare clic su Giustificativo.
11. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]