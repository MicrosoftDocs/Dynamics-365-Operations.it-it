--- 
title: Creare un modello di fattura a testo libero
description: "Questa registrazione utilizza la società dimostrativa USMF."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9c9811b348d81cd735c5b75ca48e0a56a8d52be
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="23bed-103">Creare un modello di fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="23bed-103">Create a free text invoice template</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23bed-104">Questa registrazione utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="23bed-104">This recording uses the USMF demo company.</span></span> <span data-ttu-id="23bed-105">La registrazione è destinata all'utente responsabile della gestione e dell'elaborazione delle fatture di CoCli.</span><span class="sxs-lookup"><span data-stu-id="23bed-105">The recording is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="23bed-106">Andare a Contabilità clienti > Fatture > Fatture ricorrenti > Modelli di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="23bed-106">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="23bed-107">Utilizzare questo modulo per creare modelli di fattura a testo libero in cui possono essere incluse righe di fattura, spese, modelli di distribuzione contabile e informazioni sul conto CoGe.</span><span class="sxs-lookup"><span data-stu-id="23bed-107">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="23bed-108">Fare clic su "Nuovo" per creare un nuovo modello di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="23bed-108">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="23bed-109">Digitare un valore nel campo Nome modello.</span><span class="sxs-lookup"><span data-stu-id="23bed-109">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="23bed-110">"Nome modello" identifica in modo univoco un modello di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="23bed-110">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="23bed-111">Non due modelli possono avere lo stesso "nome modello".</span><span class="sxs-lookup"><span data-stu-id="23bed-111">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="23bed-112">Nel campo Descrizione immettere una descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="23bed-112">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="23bed-113">Espandere la scheda Righe fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-113">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="23bed-114">Nel campo Descrizione immettere una descrizione della riga fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-114">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="23bed-115">Nel campo Conto principale selezionare un conto ricavi.</span><span class="sxs-lookup"><span data-stu-id="23bed-115">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="23bed-116">È possibile selezionare il conto transazioni di contropartita di un credito del cliente per l'importo totale della fattura nella pagina Profili di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="23bed-116">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="23bed-117">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="23bed-117">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="23bed-118">La fascia IVA per la riga di fattura corrente corrisponde alla fascia IVA predefinita per il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="23bed-118">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="23bed-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23bed-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="23bed-120">Nel campo Fascia IVA articoli selezionare la fascia IVA articoli per la riga fattura corrente.</span><span class="sxs-lookup"><span data-stu-id="23bed-120">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="23bed-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23bed-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="23bed-122">Nel campo Prezzo unitario immettere o visualizzare il prezzo unitario per la riga fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-122">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="23bed-123">Questo importo viene moltiplicato per campo Quantità per determinare l'importo della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-123">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="23bed-124">Aggiungere una nuova riga al modello di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="23bed-124">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="23bed-125">Nel campo Descrizione immettere una descrizione della riga fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-125">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="23bed-126">Nel campo Conto principale selezionare un conto ricavi.</span><span class="sxs-lookup"><span data-stu-id="23bed-126">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="23bed-127">È possibile selezionare il conto transazioni di contropartita di un credito del cliente per l'importo totale della fattura nella pagina Profili di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="23bed-127">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="23bed-128">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="23bed-128">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="23bed-129">La fascia IVA per la riga di fattura corrente corrisponde alla fascia IVA predefinita per il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="23bed-129">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="23bed-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23bed-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="23bed-131">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="23bed-131">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="23bed-132">Fascia IVA articoli per la riga di fattura corrente.</span><span class="sxs-lookup"><span data-stu-id="23bed-132">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="23bed-133">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23bed-133">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="23bed-134">Immettere o visualizzare il numero di unità per la riga di fattura</span><span class="sxs-lookup"><span data-stu-id="23bed-134">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="23bed-135">Questo numero viene moltiplicato per il valore del campo Prezzo unitario per determinare l'importo della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-135">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="23bed-136">Immettere o visualizzare il prezzo unitario della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-136">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="23bed-137">Questo importo viene moltiplicato per il valore del campo Quantità per determinare l'importo della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="23bed-137">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="23bed-138">Consente di visualizzare e modificare le distribuzioni contabili per una singola riga e tutte le righe figlio.</span><span class="sxs-lookup"><span data-stu-id="23bed-138">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="23bed-139">Le distribuzioni contabili definiscono il modo in cui un importo verrà conteggiato, ad esempio i ricavi, le tasse o le spese vengono conteggiate in una fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="23bed-139">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="23bed-140">Aggiorna le distribuzioni contabili per la riga fattura selezionata.</span><span class="sxs-lookup"><span data-stu-id="23bed-140">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="23bed-141">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="23bed-141">Click Close.</span></span>


