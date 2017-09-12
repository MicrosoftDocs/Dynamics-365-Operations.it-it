--- 
title: Definire termini di pagamento fornitore
description: Impostare i termini di pagamento per le fatture fornitore.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a00ca73b1bc301960132a86846749d12c39ed3f7
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="a0282-103">Definire termini di pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="a0282-103">Define vendor payment terms</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0282-104">Impostare i termini di pagamento per le fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="a0282-104">Set up payment terms for vendor invoices.</span></span> <span data-ttu-id="a0282-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="a0282-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a0282-106">Andare a Contabilità fornitori > Impostazione pagamenti > Termini di pagamento.</span><span class="sxs-lookup"><span data-stu-id="a0282-106">Go to Accounts payable > Payment setup > Terms of payment.</span></span>
2. <span data-ttu-id="a0282-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a0282-107">Click New.</span></span>
    * <span data-ttu-id="a0282-108">La pagina Termini di pagamento viene utilizzata per definire la modalità di calcolo della data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="a0282-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="a0282-109">Tale pagina viene utilizzata per definire come la data dello sconto di cassa verrà calcolata.</span><span class="sxs-lookup"><span data-stu-id="a0282-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="a0282-110">Digitare un valore nel campo Termini di pagamento.</span><span class="sxs-lookup"><span data-stu-id="a0282-110">In the Terms of payment field, type a value.</span></span>
4. <span data-ttu-id="a0282-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="a0282-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a0282-112">Nel campo Giorni immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="a0282-112">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="a0282-113">Il numero immesso in questo campo verrà utilizzato per essere aggiunto alla data di scadenza o alla fine del periodo identificato nel Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="a0282-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="a0282-114">Ad esempio, se si seleziona Netto, il numero verrà aggiunto alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="a0282-114">For example, if you select Net, the number will be added to the due date.</span></span> <span data-ttu-id="a0282-115">Se si seleziona Mese corrente, verrà aggiunto il numero all'ultimo giorno del mese corrente per calcolare la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="a0282-115">If you select Current month, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="a0282-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a0282-116">Click Save.</span></span>
7. <span data-ttu-id="a0282-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a0282-117">Close the page.</span></span>
8. <span data-ttu-id="a0282-118">Andare a Contabilità fornitori > Impostazione pagamenti > Sconti di cassa.</span><span class="sxs-lookup"><span data-stu-id="a0282-118">Go to Accounts payable > Payment setup > Cash discounts.</span></span>
9. <span data-ttu-id="a0282-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a0282-119">Click New.</span></span>
10. <span data-ttu-id="a0282-120">Nel campo Sconto di cassa immettere un ID.</span><span class="sxs-lookup"><span data-stu-id="a0282-120">In the Cash discount field, enter an ID.</span></span>
11. <span data-ttu-id="a0282-121">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="a0282-121">In the Description field, type a value.</span></span>
12. <span data-ttu-id="a0282-122">Se il fornitore offre più livelli di sconto, selezionare lo sconto di cassa successivo dopo che quello corrente è scaduto.</span><span class="sxs-lookup"><span data-stu-id="a0282-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="a0282-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a0282-123">Close the page.</span></span>
14. <span data-ttu-id="a0282-124">Nel campo Giorni immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="a0282-124">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="a0282-125">La quantità immessa nel campo Giorni verrà utilizzata per calcolare la data dello sconto di cassa in base all'opzione selezionata nel campo Netto/Corrente.</span><span class="sxs-lookup"><span data-stu-id="a0282-125">The quantity entered in the Days field will be used to calculate the Cash discount date, based on what option was selected in the Net/Current field.</span></span> <span data-ttu-id="a0282-126">Se è stato selezionato Netto, la quantità verrà aggiunta alla data della fattura per determinare la data dello sconto di cassa.</span><span class="sxs-lookup"><span data-stu-id="a0282-126">If Net was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="a0282-127">Se è stato selezionato Mese corrente, la quantità verrà aggiunta alla fine del mese della valuta per determinare la data dello sconto di cassa.</span><span class="sxs-lookup"><span data-stu-id="a0282-127">If Current month was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="a0282-128">Immettere la percentuale dello sconto di cassa nel campo Sconto.</span><span class="sxs-lookup"><span data-stu-id="a0282-128">Enter the percentage of the cash discount in the Discount field.</span></span> 
16. <span data-ttu-id="a0282-129">Immettere il conto principale in cui verrà registrato lo sconto di cassa per le fatture cliente.</span><span class="sxs-lookup"><span data-stu-id="a0282-129">Enter the main account to which the cash discount will be posted for customer invoices.</span></span>
17. <span data-ttu-id="a0282-130">Immettere il conto principale in cui verrà registrato lo sconto di cassa per le fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="a0282-130">Enter the main account to which the cash discount will be posted for vendor invoices.</span></span>
    * <span data-ttu-id="a0282-131">Se "conti di contropartita di sconto" viene impostato per l'utilizzo del conto principale per lo sconto fornitore, verrà utilizzato il conto principale.</span><span class="sxs-lookup"><span data-stu-id="a0282-131">If 'Discount offset accounts' is set to Use main account for vendor discount, then the Main account will be used.</span></span>  <span data-ttu-id="a0282-132">Se l'opzione è impostata su Conti nelle righe fattura, lo sconto di cassa verrà registrato nei conti spese/cespite nelle righe della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="a0282-132">If the option is set to Accounts on the invoice lines, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
18. <span data-ttu-id="a0282-133">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a0282-133">Click Save.</span></span>

