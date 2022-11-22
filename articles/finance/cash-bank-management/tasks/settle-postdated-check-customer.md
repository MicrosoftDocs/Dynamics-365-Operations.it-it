---
title: Liquidare un assegno postdatato di un cliente
description: Un assegno postdatato può essere liquidato solo dopo essere stato liquidato dalla banca.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e61ac6d6785dd0383d5e5dcaca4cc55bf6deb52
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780017"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>Liquidare un assegno postdatato di un cliente

[!include [banner](../../includes/banner.md)]

Un assegno postdatato può essere liquidato solo dopo essere stato liquidato dalla banca. Questa transazione finanziaria liquida inoltre la transazione del conto provvisorio per l'assegno postdatato. 

Completare le seguenti attività prima di iniziare la presente.

1) Impostare gli assegni postdatati

2) Registrare un assegno postdatato per un cliente 



Il ruolo dell'attività è Tesoriere.



Questa procedura utilizza la società dimostrativa USMF.

1. Andare a **Crediti e riscossioni > Richieste di informazioni e report > Pagamenti > Assegni postdatati cliente**.
2. Fare clic su **Liquida**.
3. Fare clic su **Liquida voci di compensazione**.
    * Liquidare il conto cliente per la transazione assegno.  
4. Chiudere la pagina.
5. Fare clic su **Contabilità generale > Scritture contabili > Giornali di registrazione generali**.
6. Selezionare un'opzione nel campo **Mostra**.
7. Selezionare o deselezionare la casella di controllo **Mostra solo giornali creati dall'utente**.
8. Nell'elenco trovare e selezionare il record desiderato.
9. Fare clic su **Righe**.
10. Fai clic su **Giustificativo**.
11. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
