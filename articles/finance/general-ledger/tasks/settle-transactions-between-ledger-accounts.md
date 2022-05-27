---
title: Liquidare le transazioni tra conti CoGe
description: Questa procedura mostra come compensare le transazioni tra diversi conti CoGe e come annullare una compensazione dei saldi contabili.
author: aprilolson
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a871e379826626edbad2434b11281fce5e29e14e
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717308"
---
# <a name="settle-transactions-between-ledger-accounts"></a>Liquidare le transazioni tra conti CoGe

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come compensare le transazioni tra diversi conti CoGe e come annullare una compensazione dei saldi contabili. Questa procedura utilizza la società di dati dimostrativi USMF.


## <a name="settle-transaction-between-ledger-accounts"></a>Compensare una transazione tra conti CoGe
1. Andare a **Contabilità generale > Attività periodiche > Compensazioni dei saldi contabili**.
2. Nell'elenco trovare la transazione da compensare.
   > [!NOTE]
   > Il saldo dell'importo deve essere pari a zero.  
3. Fare clic su **Includi**.
4. Fare clic su **Accetta**.

## <a name="cancel-a-ledger-settlement"></a>Annullare una compensazione dei saldi contabili

1. Andare a **Contabilità generale > Richieste di informazioni e report > Bilancio di verifica**.
2. Fare clic su **Parametri** per aprire la finestra di dialogo a discesa.
3. Fare clic su **Aggiorna**.
4. Nell'elenco trovare il conto che ha la transazione compensata.
5. Fare clic su **Tutte le transazioni**.
6. Utilizzare un filtro per trovare facilmente la transazione nell'elenco.
7. Fare clic su **Compensazioni dei saldi contabili**.
8. Nell'elenco contrassegnare la riga selezionata.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
