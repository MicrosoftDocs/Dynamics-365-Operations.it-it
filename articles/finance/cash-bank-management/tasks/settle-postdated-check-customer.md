---
title: Liquidare un assegno postdatato di un cliente
description: Un assegno postdatato può essere liquidato solo dopo essere stato liquidato dalla banca.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab591fc3ac529e65c15ee083377954a83363edd528861aff9bc449bfc10c7735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771730"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>Liquidare un assegno postdatato di un cliente

[!include [banner](../../includes/banner.md)]

Un assegno postdatato può essere liquidato solo dopo essere stato liquidato dalla banca. Questa transazione finanziaria liquida inoltre la transazione del conto provvisorio per l'assegno postdatato. 

Completare le seguenti attività prima di iniziare la presente.

1) Impostare gli assegni postdatati

2) Registrare un assegno postdatato per un cliente 



Il ruolo dell'attività è Tesoriere.



Questa procedura utilizza la società dimostrativa USMF.

1. Andare a Crediti e riscossioni > Richieste di informazioni e report > Pagamenti > Assegni postdatati cliente.
2. Fare clic su Liquida.
3. Fare clic su Liquida voci di compensazione.
    * Liquidare il conto cliente per la transazione assegno.  
4. Chiudere la pagina.
5. Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.
6. Selezionare un'opzione nel campo Mostra.
7. Selezionare o deselezionare la casella di controllo Mostra solo giornali creati dall'utente.
8. Nell'elenco trovare e selezionare il record desiderato.
9. Fare clic su Righe.
10. Fare clic su Giustificativo.
11. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]