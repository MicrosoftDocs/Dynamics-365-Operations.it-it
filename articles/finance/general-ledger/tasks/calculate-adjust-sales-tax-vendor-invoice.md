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
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="ee72a-103">Calcolare e rettificare l'IVA in una fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="ee72a-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee72a-104">In questo argomento viene descritto come rettificare l'IVA in una fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="ee72a-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="ee72a-105">Se nel documento di origine originale vengono visualizzati importi di imposta diversi come calcolati, è possibile rettificare gli importi prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="ee72a-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="ee72a-106">In questa attività viene utilizzata la società dimostrativa DEMF.</span><span class="sxs-lookup"><span data-stu-id="ee72a-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="ee72a-107">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="ee72a-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-108">Select **New**.</span></span>
3. <span data-ttu-id="ee72a-109">Nel campo **Nome** della nuova riga, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="ee72a-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="ee72a-110">Nel riquadro azioni selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="ee72a-111">Nel campo **Conto**, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="ee72a-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="ee72a-112">Digitare un valore nel campo **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="ee72a-113">Nel campo **Credito** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee72a-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="ee72a-114">Nel campo **Conto di contropartita**, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="ee72a-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="ee72a-115">Selezionare **IVA**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="ee72a-116">Nel campo **Importo IVA effettiva totale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee72a-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="ee72a-117">Nella scheda **Rettifica**, è possibile rettificare gli importi IVA per ogni codice IVA.</span><span class="sxs-lookup"><span data-stu-id="ee72a-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="ee72a-118">Selezionare **Reimposta importi effettivi da calcolati**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="ee72a-119">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-119">Select **OK**.</span></span>
14. <span data-ttu-id="ee72a-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ee72a-120">Select **Save**.</span></span>

