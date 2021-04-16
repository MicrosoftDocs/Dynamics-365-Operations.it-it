---
title: Riconciliare il trasporto manualmente
description: In questa procedura viene illustrato come riconciliare manualmente il trasporto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a0a5450697a09e5e54e74b35b2576eb6bbd4cdf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838516"
---
# <a name="reconcile-freight-manually"></a>Riconciliare il trasporto manualmente

[!include [banner](../../includes/banner.md)]]

In questa procedura viene illustrato come riconciliare manualmente il trasporto. La procedura viene in genere eseguita dal coordinatore dei trasporti. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.


## <a name="select-a-load-to-reconcile"></a>Selezionare un carico da riconciliare.
1. Andare a Gestione trasporto > Pianificazione > Workbench pianificazione carico.
2. Deselezionare la casella di controllo Nascondi articoli spediti e ricevuti. 
3. Nell'elenco, selezionare il carico con l'ID 00006.

## <a name="create-a-carrier-invoice"></a>Creare una fattura vettore
Se si riconcilia manualmente il trasporto e non si ricevono le fatture vettore automaticamente, è possibile creare una fattura basata sulla fattura di trasporto.  
1. Fare clic su Informazioni correlate.
2. Fare clic su Dettagli fattura trasporto.
3. Fare clic su Genera fattura di trasporto.
4. Digitare un valore nel campo Fattura.
5. Fare clic su OK.

## <a name="reconcile-the-invoice"></a>Riconciliare la fattura
Quando si esegue la riconciliazione di una fattura vettore e una fattura di trasporto, avviene riga per riga.  
1. Fare clic su Associa fatture di trasporto e fatture.
2. Espandere la sezione Dettagli fattura.
3. Espandere la sezione Dettagli fattura trasporto non corrispondenti.
4. Nell'elenco contrassegnare la riga selezionata.
5. Fare clic su Associa.
6. Espandere la sezione Dettagli fattura trasporto corrispondenti.

## <a name="submit-the-invoice-for-approval"></a>Invia fattura per approvazione
1. Fare clic su Invio per approvazione.
2. Chiudere la pagina.
3. Deselezionare la casella di controllo Nascondi approvazione. 
4. Fare clic su Giornali di registrazione fatture fornitore.
5. Fare clic per seguire il collegamento nel campo Numero giornale di registrazione di riferimento.
6. Fare clic su Righe.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]