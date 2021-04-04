---
title: Riconciliare il trasporto manualmente
description: In questa procedura viene illustrato come riconciliare manualmente il trasporto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: becda50b5d176ceb350c471b154aed1842c31a3b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247192"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="c716b-103">Riconciliare il trasporto manualmente</span><span class="sxs-lookup"><span data-stu-id="c716b-103">Reconcile freight manually</span></span>

<span data-ttu-id="c716b-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="c716b-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="c716b-105">In questa procedura viene illustrato come riconciliare manualmente il trasporto.</span><span class="sxs-lookup"><span data-stu-id="c716b-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="c716b-106">La procedura viene in genere eseguita dal coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="c716b-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="c716b-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="c716b-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="c716b-108">Selezionare un carico da riconciliare.</span><span class="sxs-lookup"><span data-stu-id="c716b-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="c716b-109">Andare a Gestione trasporto > Pianificazione > Workbench pianificazione carico.</span><span class="sxs-lookup"><span data-stu-id="c716b-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="c716b-110">Deselezionare la casella di controllo Nascondi articoli spediti e ricevuti.</span><span class="sxs-lookup"><span data-stu-id="c716b-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="c716b-111">Nell'elenco, selezionare il carico con l'ID 00006.</span><span class="sxs-lookup"><span data-stu-id="c716b-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="c716b-112">Creare una fattura vettore</span><span class="sxs-lookup"><span data-stu-id="c716b-112">Create a carrier invoice</span></span>
<span data-ttu-id="c716b-113">Se si riconcilia manualmente il trasporto e non si ricevono le fatture vettore automaticamente, è possibile creare una fattura basata sulla fattura di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c716b-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="c716b-114">Fare clic su Informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="c716b-114">Click Related information.</span></span>
2. <span data-ttu-id="c716b-115">Fare clic su Dettagli fattura trasporto.</span><span class="sxs-lookup"><span data-stu-id="c716b-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="c716b-116">Fare clic su Genera fattura di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c716b-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="c716b-117">Digitare un valore nel campo Fattura.</span><span class="sxs-lookup"><span data-stu-id="c716b-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="c716b-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c716b-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="c716b-119">Riconciliare la fattura</span><span class="sxs-lookup"><span data-stu-id="c716b-119">Reconcile the invoice</span></span>
<span data-ttu-id="c716b-120">Quando si esegue la riconciliazione di una fattura vettore e una fattura di trasporto, avviene riga per riga.</span><span class="sxs-lookup"><span data-stu-id="c716b-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="c716b-121">Fare clic su Associa fatture di trasporto e fatture.</span><span class="sxs-lookup"><span data-stu-id="c716b-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="c716b-122">Espandere la sezione Dettagli fattura.</span><span class="sxs-lookup"><span data-stu-id="c716b-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="c716b-123">Espandere la sezione Dettagli fattura trasporto non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c716b-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="c716b-124">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c716b-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="c716b-125">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c716b-125">Click Match.</span></span>
6. <span data-ttu-id="c716b-126">Espandere la sezione Dettagli fattura trasporto corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c716b-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="c716b-127">Invia fattura per approvazione</span><span class="sxs-lookup"><span data-stu-id="c716b-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="c716b-128">Fare clic su Invio per approvazione.</span><span class="sxs-lookup"><span data-stu-id="c716b-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="c716b-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c716b-129">Close the page.</span></span>
3. <span data-ttu-id="c716b-130">Deselezionare la casella di controllo Nascondi approvazione.</span><span class="sxs-lookup"><span data-stu-id="c716b-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="c716b-131">Fare clic su Giornali di registrazione fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="c716b-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="c716b-132">Fare clic per seguire il collegamento nel campo Numero giornale di registrazione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c716b-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="c716b-133">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="c716b-133">Click Lines.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]