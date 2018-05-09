--- 
title: Definire le commissioni di pagamento cliente
description: Creare le commissioni di pagamento per i pagamenti cliente.
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 02449aff2273d30e0d0d847e137e3283aef1839b
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="establish-customer-payment-fees"></a><span data-ttu-id="96819-103">Definire le commissioni di pagamento cliente</span><span class="sxs-lookup"><span data-stu-id="96819-103">Establish customer payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="96819-104">Creare le commissioni di pagamento per i pagamenti cliente.</span><span class="sxs-lookup"><span data-stu-id="96819-104">Create payment fees for customer payments.</span></span>

<span data-ttu-id="96819-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="96819-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="96819-106">Andare a Contabilità clienti > Impostazione pagamenti > Commissione di pagamento.</span><span class="sxs-lookup"><span data-stu-id="96819-106">Go to Accounts receivable > Payments setup > Payment fee.</span></span>
2. <span data-ttu-id="96819-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="96819-107">Click New.</span></span>
3. <span data-ttu-id="96819-108">Nel campo ID commissione, immettere un ID della commissione.</span><span class="sxs-lookup"><span data-stu-id="96819-108">In the Fee ID field, enter a Fee ID.</span></span>
    * <span data-ttu-id="96819-109">L'ID della commissione viene visualizzato nei giornali di registrazione pagamenti, quindi fare in modo che sia descrittivo per comprendere la commissione imposta.</span><span class="sxs-lookup"><span data-stu-id="96819-109">The Fee ID displays on payment journals, so make it descriptive to understand what fee is being assessed.</span></span>  
4. <span data-ttu-id="96819-110">Nel campo Nome immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="96819-110">In the Name field, enter a fee Name.</span></span>
5. <span data-ttu-id="96819-111">Nel campo Descrizione commissione immettere una descrizione per la commissione.</span><span class="sxs-lookup"><span data-stu-id="96819-111">In the Fee description field, enter a description for the fee.</span></span>
6. <span data-ttu-id="96819-112">Selezionare se la commissione verrà addebitata al cliente o a un conto CoGe.</span><span class="sxs-lookup"><span data-stu-id="96819-112">Select whether the fee will be charged to the Customer or a Ledger account.</span></span>
    * <span data-ttu-id="96819-113">Se la commissione viene imposta al cliente, selezionare Cliente.</span><span class="sxs-lookup"><span data-stu-id="96819-113">If the customer is assessed the fee, select Customer.</span></span> <span data-ttu-id="96819-114">Se la commissione verrà imposta all'organizzazione come spesa, selezionare Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="96819-114">If the fee will be assess to your organization as an expense, select Ledger.</span></span> <span data-ttu-id="96819-115">Per l'attività, selezionare Cliente.</span><span class="sxs-lookup"><span data-stu-id="96819-115">For this task, select Customer.</span></span>  
7. <span data-ttu-id="96819-116">Selezionare il tipo di giornale di registrazione che può utilizzare la commissione di pagamento.</span><span class="sxs-lookup"><span data-stu-id="96819-116">Select the type of  journal that can use this payment fee.</span></span>
    * <span data-ttu-id="96819-117">Se queste commissioni sono utilizzate per i pagamenti cliente, il tipo di giornale di registrazione sarà probabilmente Pagamento cliente.</span><span class="sxs-lookup"><span data-stu-id="96819-117">If these fees are used for customer payments, the journal type will likely be Customer payment.</span></span>  
8. <span data-ttu-id="96819-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="96819-118">Click Save.</span></span>
9. <span data-ttu-id="96819-119">Fare clic su Impostazione commissione pagamento.</span><span class="sxs-lookup"><span data-stu-id="96819-119">Click Payment fee setup.</span></span>
    * <span data-ttu-id="96819-120">Impostazione commissione pagamento viene utilizzata per definire i criteri per quando la commissione di pagamento verrà imposta.</span><span class="sxs-lookup"><span data-stu-id="96819-120">The Payment fee setup is used to define the criteria for when the payment fee will be assessed.</span></span>  <span data-ttu-id="96819-121">Ad esempio, è possibile definire che la commissione verrà calcolata se il conto bancario è USMF OPER e il metodo di pagamento è assegno.</span><span class="sxs-lookup"><span data-stu-id="96819-121">For example, you can define that the fee will be calculated if the bank account is USMF OPER, and the method of payment is check.</span></span>  
10. <span data-ttu-id="96819-122">Selezionare Tabella, Gruppo o Tutti per definire i conti bancari a cui verrà imposta la commissione.</span><span class="sxs-lookup"><span data-stu-id="96819-122">Select either Table, Group or All to define which bank accounts will be assessed this fee.</span></span>
    * <span data-ttu-id="96819-123">Se si seleziona Tutti, la commissione potrà essere imposta a tutti i conti bancari.</span><span class="sxs-lookup"><span data-stu-id="96819-123">If you select All, all bank accounts could be assessed this fee.</span></span>  <span data-ttu-id="96819-124">Se si seleziona Tabella, la commissione potrà essere imposta solo al conto bancario selezionato.</span><span class="sxs-lookup"><span data-stu-id="96819-124">If you select Table, only the bank account you select could be assessed this fee.</span></span> <span data-ttu-id="96819-125">Se si seleziona Gruppo, la commissione potrà essere imposta solo ai conti bancari nel gruppo bancario selezionato.</span><span class="sxs-lookup"><span data-stu-id="96819-125">If you select Group, only the bank accounts in the selected bank group could be assessed this fee.</span></span>  
11. <span data-ttu-id="96819-126">Selezionare un gruppo bancario o un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="96819-126">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="96819-127">Se è stato selezionato Tabella, la ricerca consentirà di visualizzare i conti bancari.</span><span class="sxs-lookup"><span data-stu-id="96819-127">If you selected Table, the lookup will display bank accounts.</span></span> <span data-ttu-id="96819-128">Se è stato selezionato Gruppo, la ricerca consentirà di visualizzare i gruppi bancari.</span><span class="sxs-lookup"><span data-stu-id="96819-128">If you selected Group, the lookup will display bank groups.</span></span>  
12. <span data-ttu-id="96819-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="96819-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="96819-130">Selezionare il metodo di pagamento per cui verrà imposta la commissione.</span><span class="sxs-lookup"><span data-stu-id="96819-130">Select the Method of payment for which this fee will be assessed.</span></span>
    * <span data-ttu-id="96819-131">Ad esempio, è possibile imporre una commissione ai clienti se inviano i pagamenti come assegno, anziché come pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="96819-131">For example, you may assess a fee to your customers if they send payments as a check, rather than as an electronic payment.</span></span>  
14. <span data-ttu-id="96819-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="96819-132">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="96819-133">Se pertinente, immettere una valuta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="96819-133">If relevant, enter a payment currency.</span></span>
    * <span data-ttu-id="96819-134">La valuta del pagamento viene utilizzata come criterio aggiuntivo per indicare se la commissione verrà imposta.</span><span class="sxs-lookup"><span data-stu-id="96819-134">The payment currency is used as an additional criteria for whether the fee will be assessed.</span></span>  <span data-ttu-id="96819-135">Ad esempio, la banca può addebitare una commissione aggiuntiva per i pagamenti ricevuti nella valuta EUR, poiché trattano in genere solo nella valuta EUR.</span><span class="sxs-lookup"><span data-stu-id="96819-135">For example, your bank may charge an extra fee for payments received in USD currency, since they normally only transact in EUR currency.</span></span>  
16. <span data-ttu-id="96819-136">Selezionare se la commissione sarà una percentuale, un importo o un intervallo.</span><span class="sxs-lookup"><span data-stu-id="96819-136">Select whether the fee will be a percent, amount or interval.</span></span>
17. <span data-ttu-id="96819-137">Immettere la percentuale o l'importo della commissione.</span><span class="sxs-lookup"><span data-stu-id="96819-137">Enter either percentage or amount of the fee.</span></span>
    * <span data-ttu-id="96819-138">Se il campo Percentuale/Importo è Percentuale, il valore immesso in questo campo sarà una percentuale.</span><span class="sxs-lookup"><span data-stu-id="96819-138">If the Percentage/Amount field is Percent, then the value enter here will be a percentage.</span></span> <span data-ttu-id="96819-139">Se il campo Percentuale/Importo è Importo, il valore immesso in questo campo sarà un importo.</span><span class="sxs-lookup"><span data-stu-id="96819-139">If the Percentage/Amount field is Amount, then the value you enter here will be an amount.</span></span> <span data-ttu-id="96819-140">Se il campo Percentuale/Importo è Intervallo, utilizzare la scheda Intervallo per definire i livelli.</span><span class="sxs-lookup"><span data-stu-id="96819-140">If the Percentage/Amount field is Interval, use the Interval tab to define the tiers.</span></span>  
18. <span data-ttu-id="96819-141">Nel campo Valuta commissioni, selezionare la valuta della commissione.</span><span class="sxs-lookup"><span data-stu-id="96819-141">In the Fee currency field, select the currency of the fee.</span></span>
    * <span data-ttu-id="96819-142">Si tratta della valuta in cui la commissione verrà creata.</span><span class="sxs-lookup"><span data-stu-id="96819-142">This is the currency in which the fee will be created.</span></span>  
19. <span data-ttu-id="96819-143">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="96819-143">Click Save.</span></span>


