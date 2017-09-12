--- 
title: Riconciliare il trasporto manualmente
description: In questa procedura viene illustrato come riconciliare manualmente il trasporto.
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 15148725664d839694ede8419213d881c7be83dd
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="4efaa-103">Riconciliare il trasporto manualmente</span><span class="sxs-lookup"><span data-stu-id="4efaa-103">Reconcile freight manually</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4efaa-104">In questa procedura viene illustrato come riconciliare manualmente il trasporto.</span><span class="sxs-lookup"><span data-stu-id="4efaa-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="4efaa-105">La procedura viene in genere eseguita dal coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="4efaa-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="4efaa-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="4efaa-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="4efaa-107">Selezionare un carico da riconciliare.</span><span class="sxs-lookup"><span data-stu-id="4efaa-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="4efaa-108">Andare a Gestione trasporto > Pianificazione > Workbench pianificazione carico.</span><span class="sxs-lookup"><span data-stu-id="4efaa-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="4efaa-109">Deselezionare la casella di controllo Nascondi articoli spediti e ricevuti.</span><span class="sxs-lookup"><span data-stu-id="4efaa-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="4efaa-110">Nell'elenco, selezionare il carico con l'ID 00006.</span><span class="sxs-lookup"><span data-stu-id="4efaa-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="4efaa-111">Creare una fattura vettore</span><span class="sxs-lookup"><span data-stu-id="4efaa-111">Create a carrier invoice</span></span>
    * <span data-ttu-id="4efaa-112">Se si riconcilia manualmente il trasporto e non si ricevono le fatture vettore automaticamente, è possibile creare una fattura basata sulla fattura di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4efaa-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="4efaa-113">Fare clic su Informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="4efaa-113">Click Related information.</span></span>
2. <span data-ttu-id="4efaa-114">Fare clic su Dettagli fattura trasporto.</span><span class="sxs-lookup"><span data-stu-id="4efaa-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="4efaa-115">Fare clic su Genera fattura di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4efaa-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="4efaa-116">Digitare un valore nel campo Fattura.</span><span class="sxs-lookup"><span data-stu-id="4efaa-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="4efaa-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4efaa-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="4efaa-118">Riconciliare la fattura</span><span class="sxs-lookup"><span data-stu-id="4efaa-118">Reconcile the invoice</span></span>
    * <span data-ttu-id="4efaa-119">Quando si esegue la riconciliazione di una fattura vettore e una fattura di trasporto, avviene riga per riga.</span><span class="sxs-lookup"><span data-stu-id="4efaa-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="4efaa-120">Fare clic su Associa fatture di trasporto e fatture.</span><span class="sxs-lookup"><span data-stu-id="4efaa-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="4efaa-121">Espandere la sezione Dettagli fattura.</span><span class="sxs-lookup"><span data-stu-id="4efaa-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="4efaa-122">Espandere la sezione Dettagli fattura trasporto non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="4efaa-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="4efaa-123">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4efaa-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="4efaa-124">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="4efaa-124">Click Match.</span></span>
6. <span data-ttu-id="4efaa-125">Espandere la sezione Dettagli fattura trasporto corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="4efaa-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="4efaa-126">Invia fattura per approvazione</span><span class="sxs-lookup"><span data-stu-id="4efaa-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="4efaa-127">Fare clic su Invio per approvazione.</span><span class="sxs-lookup"><span data-stu-id="4efaa-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="4efaa-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4efaa-128">Close the page.</span></span>
3. <span data-ttu-id="4efaa-129">Deselezionare la casella di controllo Nascondi approvazione.</span><span class="sxs-lookup"><span data-stu-id="4efaa-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="4efaa-130">Fare clic su Giornali di registrazione fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="4efaa-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="4efaa-131">Fare clic per seguire il collegamento nel campo Numero giornale di registrazione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4efaa-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="4efaa-132">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="4efaa-132">Click Lines.</span></span>

