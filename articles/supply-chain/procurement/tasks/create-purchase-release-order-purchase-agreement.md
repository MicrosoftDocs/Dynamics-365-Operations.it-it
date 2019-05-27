---
title: Creare un ordine fornitore di rilascio da un contratto di acquisto
description: Questa procedura mostra come utilizzare un contratto di acquisto quando si crea un ordine fornitore.
author: mkirknel
manager: AnnBe
ms.date: 12/04/2015
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c45db4ac01be831c0c75f888d313d61d934fc33f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547590"
---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a><span data-ttu-id="37826-103">Creare un ordine fornitore di rilascio da un contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="37826-103">Create a purchase release order from a purchase agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="37826-104">Questa procedura mostra come utilizzare un contratto di acquisto quando si crea un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="37826-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="37826-105">Il contratto di acquisto deve essere applicato quando si crea l'ordine fornitore perché sono termini generali che devono essere copiati nell'intestazione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="37826-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="37826-106">In genere questa attività sarà svolta da un addetto acquisti.</span><span class="sxs-lookup"><span data-stu-id="37826-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="37826-107">Come prerequisito per la guida, è necessario disporre di un contratto di acquisto valido con un impegno quantità di prodotto per un fornitore e gli articoli.</span><span class="sxs-lookup"><span data-stu-id="37826-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="37826-108">La stessa procedura può essere utilizzata se si dispone di un contratto di acquisto con altri tipi di impegni.</span><span class="sxs-lookup"><span data-stu-id="37826-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="37826-109">È possibile eseguire questa guida nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="37826-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="37826-110">Se si utilizza USMF, è possibile “Creare un contratto di acquisto” innanzitutto per impostare i presupposti necessari per la guida.</span><span class="sxs-lookup"><span data-stu-id="37826-110">If you’re using USMF, you can run the “Create a purchase agreement” guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="37826-111">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="37826-111">Create a purchase order</span></span>
1. <span data-ttu-id="37826-112">Aprire l'area di lavoro preparazione ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="37826-112">Open the purchase order preparation workspace.</span></span>
2. <span data-ttu-id="37826-113">Fare clic su Nuovo ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="37826-113">Click New purchase order.</span></span>
3. <span data-ttu-id="37826-114">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="37826-114">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="37826-115">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="37826-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="37826-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="37826-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="37826-117">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="37826-117">Toggle the expansion of the General section.</span></span>
7. <span data-ttu-id="37826-118">Nel campo Contratto di acquisto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="37826-118">In the Purchase agreement field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="37826-119">Tutti i contratti disponibili per il fornitore sono elencati in questo campo.</span><span class="sxs-lookup"><span data-stu-id="37826-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="37826-120">Individuare il contratto valido da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="37826-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="37826-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="37826-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="37826-122">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="37826-122">Click Yes.</span></span>
10. <span data-ttu-id="37826-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="37826-123">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="37826-124">Aggiungere una riga</span><span class="sxs-lookup"><span data-stu-id="37826-124">Add a line</span></span>
1. <span data-ttu-id="37826-125">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="37826-125">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="37826-126">Se sono presenti dimensioni inventariali o di ubicazione sull'impegno, è necessario immettere gli stessi valori nella riga ordine fornitore per utilizzare il contratto.</span><span class="sxs-lookup"><span data-stu-id="37826-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="37826-127">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="37826-127">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="37826-128">Il sito può già essere popolato con il valore predefinito dall'ordine o dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="37826-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="37826-129">In questo caso, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="37826-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="37826-130">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="37826-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="37826-131">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="37826-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="37826-132">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="37826-132">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="37826-133">Verificare che il prezzo sia copiato dall'impegno.</span><span class="sxs-lookup"><span data-stu-id="37826-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="37826-134">Cercare l'impegno</span><span class="sxs-lookup"><span data-stu-id="37826-134">Look up the commitment</span></span>
1. <span data-ttu-id="37826-135">Fare clic su Aggiorna riga.</span><span class="sxs-lookup"><span data-stu-id="37826-135">Click Update line.</span></span>
2. <span data-ttu-id="37826-136">Fare clic su Collegata.</span><span class="sxs-lookup"><span data-stu-id="37826-136">Click Attached.</span></span>
    * <span data-ttu-id="37826-137">In questo punto è possibile ottenere i dettagli del contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="37826-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="37826-138">Ad esempio, è possibile visualizzare il prezzo e se il prezzo e lo sconto sono fissi. Ciò significa che se si modifica il prezzo o lo sconto nell'ordine fornitore su un valore diverso di quello dell'impegno, il collegamento verrà rimosso in modo che la riga ordine fornitore non soddisfi l'impegno.</span><span class="sxs-lookup"><span data-stu-id="37826-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="37826-139">È inoltre possibile visualizzare se l'opzione Valore massimo applicato è selezionata. In tal caso, la quantità relativa all'impegno non può essere superata sommando tutti gli acquisti correlati all'impegno.</span><span class="sxs-lookup"><span data-stu-id="37826-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="37826-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="37826-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="37826-141">Cercare il contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="37826-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="37826-142">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="37826-142">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="37826-143">Fare clic su Contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="37826-143">Click Purchase agreement.</span></span>
3. <span data-ttu-id="37826-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="37826-144">Close the page.</span></span>
4. <span data-ttu-id="37826-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="37826-145">Close the page.</span></span>

