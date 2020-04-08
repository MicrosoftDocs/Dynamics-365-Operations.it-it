---
title: Calcolare e rettificare l'IVA in una fattura fornitore
description: In questo argomento viene descritto come rettificare l'IVA in una fattura fornitore in Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2f3521f7bc56659fc6f7a6d47f581ddbfea16523
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139969"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Calcolare e rettificare l'IVA in una fattura fornitore

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come rettificare l'IVA in una fattura fornitore. Se nel documento di origine originale vengono visualizzati importi di imposta diversi come calcolati, è possibile rettificare gli importi prima della registrazione. In questa attività viene utilizzata la società dimostrativa DEMF.

1. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Giornale di registrazione fatture**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome** della nuova riga, selezionare un'opzione dal menu a discesa.
4. Nel riquadro azioni selezionare **Righe**.
5. Nel campo **Conto**, specificare i valori desiderati.
6. Digitare un valore nel campo **Fattura**.
7. Nel campo **Credito** immettere un numero.
8. Nel campo **Conto di contropartita**, specificare i valori desiderati.
9. Selezionare **IVA**.
10. Nel campo **Importo IVA effettiva totale** immettere un numero.
11. Nella scheda **Rettifica**, è possibile rettificare gli importi IVA per ogni codice IVA.
12. Selezionare **Reimposta importi effettivi da calcolati**.
13. Selezionare **OK**.
14. Selezionare **Salva**.

