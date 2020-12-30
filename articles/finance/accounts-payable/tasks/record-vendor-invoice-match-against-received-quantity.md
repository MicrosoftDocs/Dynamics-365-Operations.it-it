---
title: Registrare la fattura fornitore e associarla alla quantità ricevuta
description: Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa79ab46e9fdc6f8a2b4524d372949314ac2d200
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444728"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>Registrare la fattura fornitore e associarla alla quantità ricevuta

[!include [banner](../../includes/banner.md)]

Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento. Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture. 

Nella pagina Parametri di contabilità fornitori, assicurarsi che l'opzione Abilita convalida abbinamento fatture sia selezionata,che il campo Registra fatture con discrepanze sia impostato su Richiedi approvazione e che il campo Criteri di abbinamento riga sia impostato su Criteri di abbinamento a tre elementi di verifica.

Questa procedura utilizza la società dimostrativa USMF. Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni.


## <a name="create-a-purchase-order"></a>Creare un ordine fornitore
1. Fare clic su Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.
4. Digitare un valore nel campo Conto fornitore.
5. Fare clic su OK.
6. Fare clic su Aggiungi riga.
7. Nel campo Numero articolo, digitare un valore.
8. Nel riquadro azioni fare clic su Acquisti.
9. Fare clic su Conferma.

## <a name="post-a-product-receipt"></a>Registra un'entrata prodotti
1. Nel riquadro azioni fare clic su Ricevimento.
2. Fare clic su Entrata prodotti.
3. Nell'elenco contrassegnare la riga selezionata.
4. Digitare un valore nel campo Entrata prodotti.
5. Fare clic su OK.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registrare e abbinare una fattura fornitore a un'entrata prodotti
1. Nel riquadro azioni fare clic su Fattura.
2. Fare clic su Fattura.
3. Digitare un valore nel campo Numero.
4. Fare clic su Predefinito da: Quantità ordinata per aprire la finestra di dialogo a discesa.
5. Nel campo Quantità predefinita per le righe selezionare un'opzione.
6. Fare clic su OK.
7. Fare clic su Sì.
8. Fare clic su Abbina entrate prodotti.
9. Fare clic su OK.
10. Nel riquadro azioni fare clic su Revisione.
11. Fare clic su Dettagli abbinamento.

