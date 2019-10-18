---
title: Creare un modello di fattura a testo libero
description: Questa procedura illustra come creare un modello di fattura a testo libero.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8281de3cb336d9392a6a97f98e51a2a139a384c5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189133"
---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="6e747-103">Creare un modello di fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="6e747-103">Create a free text invoice template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e747-104">Per questa procedura utilizzare la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="6e747-104">For this walkthrough, use the USMF demo company.</span></span> <span data-ttu-id="6e747-105">Questa procedura è destinata all'utente responsabile della gestione e dell'elaborazione delle fatture di CoCli.</span><span class="sxs-lookup"><span data-stu-id="6e747-105">This procedure is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="6e747-106">Crea un modello</span><span class="sxs-lookup"><span data-stu-id="6e747-106">Create a template</span></span>

1. <span data-ttu-id="6e747-107">Andare a Contabilità clienti > Fatture > Fatture ricorrenti > Modelli di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="6e747-107">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="6e747-108">Utilizzare questo modulo per creare modelli di fattura a testo libero in cui possono essere incluse righe di fattura, spese, modelli di distribuzione contabile e informazioni sul conto CoGe.</span><span class="sxs-lookup"><span data-stu-id="6e747-108">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="6e747-109">Fare clic su "Nuovo" per creare un nuovo modello di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="6e747-109">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="6e747-110">Digitare un valore nel campo Nome modello.</span><span class="sxs-lookup"><span data-stu-id="6e747-110">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="6e747-111">"Nome modello" identifica in modo univoco un modello di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="6e747-111">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="6e747-112">Non due modelli possono avere lo stesso "nome modello".</span><span class="sxs-lookup"><span data-stu-id="6e747-112">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="6e747-113">Nel campo Descrizione immettere una descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="6e747-113">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="6e747-114">Espandere la scheda Righe fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-114">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="6e747-115">Nel campo Descrizione immettere una descrizione della riga fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-115">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="6e747-116">Nel campo Conto principale selezionare un conto ricavi.</span><span class="sxs-lookup"><span data-stu-id="6e747-116">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="6e747-117">È possibile selezionare il conto transazioni di contropartita di un credito del cliente per l'importo totale della fattura nella pagina Profili di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="6e747-117">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="6e747-118">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6e747-118">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e747-119">La fascia IVA per la riga di fattura corrente corrisponde alla fascia IVA predefinita per il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="6e747-119">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="6e747-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6e747-120">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="6e747-121">Nel campo Fascia IVA articoli selezionare la fascia IVA articoli per la riga fattura corrente.</span><span class="sxs-lookup"><span data-stu-id="6e747-121">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="6e747-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6e747-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="6e747-123">Nel campo Prezzo unitario immettere o visualizzare il prezzo unitario per la riga fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-123">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="6e747-124">Questo importo viene moltiplicato per campo Quantità per determinare l'importo della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-124">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="6e747-125">Aggiungere una nuova riga al modello di fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="6e747-125">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="6e747-126">Nel campo Descrizione immettere una descrizione della riga fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-126">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="6e747-127">Nel campo Conto principale selezionare un conto ricavi.</span><span class="sxs-lookup"><span data-stu-id="6e747-127">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="6e747-128">È possibile selezionare il conto transazioni di contropartita di un credito del cliente per l'importo totale della fattura nella pagina Profili di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="6e747-128">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="6e747-129">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6e747-129">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e747-130">La fascia IVA per la riga di fattura corrente corrisponde alla fascia IVA predefinita per il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="6e747-130">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="6e747-131">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6e747-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="6e747-132">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6e747-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e747-133">Fascia IVA articoli per la riga di fattura corrente.</span><span class="sxs-lookup"><span data-stu-id="6e747-133">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="6e747-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6e747-134">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="6e747-135">Immettere o visualizzare il numero di unità per la riga di fattura</span><span class="sxs-lookup"><span data-stu-id="6e747-135">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="6e747-136">Questo numero viene moltiplicato per il valore del campo Prezzo unitario per determinare l'importo della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-136">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="6e747-137">Immettere o visualizzare il prezzo unitario della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-137">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="6e747-138">Questo importo viene moltiplicato per il valore del campo Quantità per determinare l'importo della riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="6e747-138">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="6e747-139">Consente di visualizzare e modificare le distribuzioni contabili per una singola riga e tutte le righe figlio.</span><span class="sxs-lookup"><span data-stu-id="6e747-139">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="6e747-140">Le distribuzioni contabili definiscono il modo in cui un importo verrà conteggiato, ad esempio i ricavi, le tasse o le spese vengono conteggiate in una fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="6e747-140">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="6e747-141">Aggiorna le distribuzioni contabili per la riga fattura selezionata.</span><span class="sxs-lookup"><span data-stu-id="6e747-141">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="6e747-142">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="6e747-142">Click Close.</span></span>

## <a name="save-a-free-text-invoice-as-a-template"></a><span data-ttu-id="6e747-143">Salvare un modello di fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="6e747-143">Save a free text invoice as a template</span></span>
<span data-ttu-id="6e747-144">È inoltre possibile salvare una fattura a testo libero esistente come modello.</span><span class="sxs-lookup"><span data-stu-id="6e747-144">You can also save an existing free text invoice as a template.</span></span> <span data-ttu-id="6e747-145">Quando si seleziona Salva come modello dalla scheda Fattura, immettere un nome e una descrizione per il modello.</span><span class="sxs-lookup"><span data-stu-id="6e747-145">When you select Save to template from the Invoice tab, provide a name and a description for the template.</span></span> <span data-ttu-id="6e747-146">Se un modello con il nome è già presente, vedrete una notifica in un modello con il nome esistente.</span><span class="sxs-lookup"><span data-stu-id="6e747-146">If a template with the name already exists, you will see a notification that a template with that name already exists.</span></span> <span data-ttu-id="6e747-147">È comunque possibile fare clic su OK per sostituirlo.</span><span class="sxs-lookup"><span data-stu-id="6e747-147">You can still click on Ok to replace it.</span></span> 
