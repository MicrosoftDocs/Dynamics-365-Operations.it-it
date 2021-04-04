---
title: Verificare le fatture e i dati principali nella contabilità fornitori
description: Questo argomento mostra come verificare le fatture e i dati principali nella contabilità fornitori.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6188b10327e4827cf5752fa56c3d491ef315b955
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204763"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Verificare le fatture e i dati principali nella contabilità fornitori

[!include [banner](../../includes/banner.md)]

Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento. Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture. 

Nella pagina **Parametri di contabilità fornitori**, assicurarsi che l'opzione Abilita convalida abbinamento fatture sia selezionata,che il campo **Registra fatture con discrepanze** sia impostato su **Richiedi approvazione** e che il campo **Criteri di abbinamento riga** sia impostato su **Criteri di abbinamento a tre elementi di verifica**.

Questa procedura utilizza la società dimostrativa USMF. Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni.


## <a name="create-a-purchase-order"></a>Creare un ordine fornitore
1. Accedere a **Tutti gli ordini fornitore**.
2. Fare clic su **Nuovo**.
3. Nel campo **Conto fornitore**, digitare un valore.
4. Fare clic su **OK**.
5. Fare clic su **Aggiungi riga**.
6. Nel campo **Numero articolo**, digitare un valore.
7. Nel riquadro azioni, fare clic su **Acquisti**.
8. Fare clic su **Conferma**.

## <a name="post-a-product-receipt"></a>Registra un'entrata prodotti
1. Nel riquadro azioni, fare clic su **Ricevimento**.
2. Fare clic su **Entrata prodotti**.
3. Nel campo **Entrata prodotti**, digitare un valore.
4. Fare clic su **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registrare e abbinare una fattura fornitore a un'entrata prodotti
1. Nel riquadro azioni, fare clic su **Fattura > Fattura**.
2. Nel campo **Numero**, digitare un valore.
3. Fare clic su **Predefinito da: Quantità ordinata** per aprire la finestra di dialogo a discesa.
4. Nel campo **Quantità predefinita per le righe**, selezionare un'opzione.
5. Fare clic su **OK**.
6. Fare clic su **Sì**.
7. Fare clic su **Abbina entrate prodotti**.
8. Fare clic su **OK**.
9. Nel riquadro azioni fare clic su **Revisione**.
10. Fare clic su **Dettagli abbinamento**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]