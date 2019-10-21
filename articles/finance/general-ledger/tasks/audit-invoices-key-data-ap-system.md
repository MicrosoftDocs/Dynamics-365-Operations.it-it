---
title: Verificare le fatture e i dati principali nel sistema di contabilità fornitori
description: Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178416"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a>Verificare le fatture e i dati principali nel sistema di contabilità fornitori

[!include [task guide banner](../../includes/task-guide-banner.md)]

Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento. Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture. 

Nella pagina Parametri di contabilità fornitori, assicurarsi che l'opzione Abilita convalida abbinamento fatture sia selezionata,che il campo Registra fatture con discrepanze sia impostato su Richiedi approvazione e che il campo Criteri di abbinamento riga sia impostato su Criteri di abbinamento a tre elementi di verifica.

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

