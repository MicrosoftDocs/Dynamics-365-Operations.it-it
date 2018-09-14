--- 
title: Calcolare e rettificare l'IVA in una fattura fornitore
description: "Se nel documento di origine originale vengono visualizzati importi di imposta diversi come calcolati, è possibile rettificare gli importi prima della registrazione."
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 803c038d907b68a3c72a83a3e035c4e08b8a8661
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="23cde-103">Calcolare e rettificare l'IVA in una fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="23cde-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23cde-104">Se nel documento di origine originale vengono visualizzati importi di imposta diversi come calcolati, è possibile rettificare gli importi prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="23cde-104">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="23cde-105">In questa attività viene utilizzata la società dimostrativa DEMF.</span><span class="sxs-lookup"><span data-stu-id="23cde-105">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="23cde-106">Passare a Contabilità fornitori > Fatture > Giornale di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="23cde-106">Go to Accounts payable > Invoices > Invoice journal.</span></span>
2. <span data-ttu-id="23cde-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="23cde-107">Click New.</span></span>
3. <span data-ttu-id="23cde-108">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23cde-108">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="23cde-109">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="23cde-109">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="23cde-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23cde-110">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="23cde-111">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="23cde-111">Click Lines.</span></span>
7. <span data-ttu-id="23cde-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23cde-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="23cde-113">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="23cde-113">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="23cde-114">Digitare un valore nel campo Fattura.</span><span class="sxs-lookup"><span data-stu-id="23cde-114">In the Invoice field, type a value.</span></span>
10. <span data-ttu-id="23cde-115">Nel campo Credito immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="23cde-115">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="23cde-116">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="23cde-116">In the Offset account field, specify the desired values.</span></span>
12. <span data-ttu-id="23cde-117">Fare clic su Fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="23cde-117">Click Sales tax.</span></span>
13. <span data-ttu-id="23cde-118">Nel campo Importo IVA effettiva totale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="23cde-118">In the Total actual sales tax amount field, enter a number.</span></span>
14. <span data-ttu-id="23cde-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="23cde-119">Click OK.</span></span>
15. <span data-ttu-id="23cde-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="23cde-120">Click Save.</span></span>
16. <span data-ttu-id="23cde-121">Fare clic su Fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="23cde-121">Click Sales tax.</span></span>
17. <span data-ttu-id="23cde-122">Nella scheda Rettifica, è possibile rettificare gli importi IVA per ogni codice IVA.</span><span class="sxs-lookup"><span data-stu-id="23cde-122">On the Adjustment tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
18. <span data-ttu-id="23cde-123">Fare clic su Reimposta importi effettivi da calcolati.</span><span class="sxs-lookup"><span data-stu-id="23cde-123">Click Reset actual from calculated amounts.</span></span>
19. <span data-ttu-id="23cde-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="23cde-124">Click OK.</span></span>
20. <span data-ttu-id="23cde-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="23cde-125">Click Save.</span></span>


