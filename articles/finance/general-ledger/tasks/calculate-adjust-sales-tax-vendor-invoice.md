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
ms.openlocfilehash: fd98f42b501ddabdc0cc26d2a264c533410731f1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815214"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="04bb3-103">Calcolare e rettificare l'IVA in una fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="04bb3-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="04bb3-104">In questo argomento viene descritto come rettificare l'IVA in una fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="04bb3-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="04bb3-105">Se nel documento di origine originale vengono visualizzati importi di imposta diversi come calcolati, è possibile rettificare gli importi prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="04bb3-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="04bb3-106">In questa attività viene utilizzata la società dimostrativa DEMF.</span><span class="sxs-lookup"><span data-stu-id="04bb3-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="04bb3-107">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="04bb3-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-108">Select **New**.</span></span>
3. <span data-ttu-id="04bb3-109">Nel campo **Nome** della nuova riga, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="04bb3-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="04bb3-110">Nel riquadro azioni selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="04bb3-111">Nel campo **Conto**, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="04bb3-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="04bb3-112">Digitare un valore nel campo **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="04bb3-113">Nel campo **Credito** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="04bb3-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="04bb3-114">Nel campo **Conto di contropartita**, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="04bb3-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="04bb3-115">Selezionare **IVA**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="04bb3-116">Nel campo **Importo IVA effettiva totale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="04bb3-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="04bb3-117">Nella scheda **Rettifica**, è possibile rettificare gli importi IVA per ogni codice IVA.</span><span class="sxs-lookup"><span data-stu-id="04bb3-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="04bb3-118">Selezionare **Reimposta importi effettivi da calcolati**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="04bb3-119">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-119">Select **OK**.</span></span>
14. <span data-ttu-id="04bb3-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="04bb3-120">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]