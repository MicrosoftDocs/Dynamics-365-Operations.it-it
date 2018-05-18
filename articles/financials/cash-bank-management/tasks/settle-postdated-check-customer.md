--- 
title: Liquidare un assegno postdatato di un cliente
description: "Un assegno postdatato può essere liquidato solo dopo essere stato liquidato dalla banca."
author: kweekley
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
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a905166dcfbf8cee5b0e5831b47c95d443a74f8d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="settle-a-postdated-check-from-a-customer"></a>Liquidare un assegno postdatato di un cliente

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


