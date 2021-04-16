---
title: Creare transazioni IVA su documenti
description: L'IVA sui documenti viene calcolata immettendo una fascia IVA e una fascia IVA articoli nelle righe del documento.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 061949dedde763c188e13c07cec750895cbef175
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836987"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="fbfd7-103">Creare transazioni IVA su documenti</span><span class="sxs-lookup"><span data-stu-id="fbfd7-103">Create sales tax transactions on documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fbfd7-104">L'IVA sui documenti viene calcolata immettendo una fascia IVA e una fascia IVA articoli nelle righe del documento.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="fbfd7-105">Come fascia IVA e fascia IVA articoli predefinite vengono impostate quelle dei dati master ma possono essere modificate manualmente se necessario.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="fbfd7-106">L'IVA calcolata può essere verificata a livello di documento e riga.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="fbfd7-107">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="fbfd7-108">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="fbfd7-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-109">Click New.</span></span>
3. <span data-ttu-id="fbfd7-110">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fbfd7-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fbfd7-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fbfd7-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-113">Click OK.</span></span>
7. <span data-ttu-id="fbfd7-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="fbfd7-115">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="fbfd7-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="fbfd7-117">Immettere un numero nel campo Prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="fbfd7-118">Espandere o comprimere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="fbfd7-119">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="fbfd7-120">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="fbfd7-121">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="fbfd7-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="fbfd7-123">Fare clic su Dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-123">Click Financials.</span></span>
17. <span data-ttu-id="fbfd7-124">Fare clic su Fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-124">Click Sales tax.</span></span>
18. <span data-ttu-id="fbfd7-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-125">Click OK.</span></span>
19. <span data-ttu-id="fbfd7-126">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-126">Click Add line.</span></span>
20. <span data-ttu-id="fbfd7-127">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="fbfd7-128">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="fbfd7-129">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="fbfd7-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="fbfd7-131">Immettere un numero nel campo Prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="fbfd7-132">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="fbfd7-133">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="fbfd7-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="fbfd7-135">Nel riquadro azioni fare clic su Vendi.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="fbfd7-136">Fare clic su Fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-136">Click Sales tax.</span></span>
30. <span data-ttu-id="fbfd7-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fbfd7-137">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]