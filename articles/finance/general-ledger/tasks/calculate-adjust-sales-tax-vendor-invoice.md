---
title: Calcolare e rettificare l'IVA in una fattura fornitore
description: In questo argomento viene descritto come rettificare l'IVA in una fattura fornitore in Dynamics 365 Finance.
author: twheeloc
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 648d94e895a4941f5f3148134130b3ffa693a9d57e0bb4e236f5d5fb33aca48f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779814"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]