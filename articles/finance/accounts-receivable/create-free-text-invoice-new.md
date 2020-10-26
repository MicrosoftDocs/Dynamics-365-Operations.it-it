---
title: Creare una fattura a testo libero
description: In questo argomento viene illustrato come creare le fatture a testo libero.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1ac06e7d702ffe3a8cdb6bd2823f2ffdc055c722
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976525"
---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="49a75-103">Creare una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="49a75-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49a75-104">In questo argomento viene illustrato come creare le fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="49a75-104">This topic explains how to create free text invoices.</span></span> <span data-ttu-id="49a75-105">Per questa procedura viene utilizzata la società dimostrativa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="49a75-105">For the procedure, use the **USMF** demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="49a75-106">Crea una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="49a75-106">Create a free text invoice</span></span>

1. <span data-ttu-id="49a75-107">Passare a **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="49a75-107">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2. <span data-ttu-id="49a75-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="49a75-108">Select **New**.</span></span>
3. <span data-ttu-id="49a75-109">Nel campo **Conto cliente** selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="49a75-109">In the **Customer account** field, select a value.</span></span>

    * <span data-ttu-id="49a75-110">Per impostazione predefinita, il conto che viene selezionato come conto cliente viene utilizzare come conto fatture.</span><span class="sxs-lookup"><span data-stu-id="49a75-110">By default, the account that is selected as the customer account is used as the invoice account.</span></span>
    * <span data-ttu-id="49a75-111">Se la fattura non viene registrata, lo stato di contabilità inizia con **In corso**.</span><span class="sxs-lookup"><span data-stu-id="49a75-111">If the invoice isn't posted, the accounting status starts with **In process**.</span></span>
    * <span data-ttu-id="49a75-112">Il numero fattura viene assegnato al momento della registrazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="49a75-112">The invoice number will be assigned when the invoice is posted.</span></span>
    * <span data-ttu-id="49a75-113">Se si utilizzano i mandati SEPA (Single Euro Payments Area), il mandato per addebito diretto verrà automaticamente immesso quando si seleziona il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="49a75-113">If you're using Single Euro Payments Area (SEPA) mandates, the direct debit mandate is automatically entered when you select the customer account.</span></span>

4. <span data-ttu-id="49a75-114">Nel campo **Descrizione** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="49a75-114">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="49a75-115">Nel campo **Conto principale** specificare il numero di conto che non ha dimensioni.</span><span class="sxs-lookup"><span data-stu-id="49a75-115">In the **Main account** field, specify an account number that doesn't have dimensions.</span></span> <span data-ttu-id="49a75-116">Le dimensioni verranno immesse più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="49a75-116">You will enter dimensions later in this topic.</span></span>

    <span data-ttu-id="49a75-117">È anche possibile immettere uno o più caratteri per il conto principale e utilizzare la ricerca per trovare il conto.</span><span class="sxs-lookup"><span data-stu-id="49a75-117">You can also enter one or more characters for the main account, and use the lookup to find the account.</span></span>

6. <span data-ttu-id="49a75-118">Selezionare la Scheda dettaglio **Dettagli riga** per aggiungere dimensioni al conto principale.</span><span class="sxs-lookup"><span data-stu-id="49a75-118">Select the **Line details** FastTab to add dimensions to the main account.</span></span>
7. <span data-ttu-id="49a75-119">Selezionare la scheda **Riga dimensioni finanziarie**.</span><span class="sxs-lookup"><span data-stu-id="49a75-119">Select the **Financial dimensions line** tab.</span></span>

    * <span data-ttu-id="49a75-120">Le dimensioni sono relative solo alla riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="49a75-120">The dimensions are for the selected line only.</span></span>
    * <span data-ttu-id="49a75-121">La fascia IVA viene compilata dal cliente.</span><span class="sxs-lookup"><span data-stu-id="49a75-121">The sales tax group is filled in from the customer.</span></span> <span data-ttu-id="49a75-122">Se il cliente non dispone di una fascia IVA, viene utilizzata quella del conto principale.</span><span class="sxs-lookup"><span data-stu-id="49a75-122">If the customer doesn't have a sales tax group, the sales tax group from the main account is used.</span></span>
    * <span data-ttu-id="49a75-123">La fascia IVA articoli viene compilata dal conto principale.</span><span class="sxs-lookup"><span data-stu-id="49a75-123">The items sales tax group is filled in from the main account.</span></span> <span data-ttu-id="49a75-124">Se il conto principale non dispone di una fascia IVA articoli, viene utilizzata quella specificata nei parametri IVA della contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="49a75-124">If the main account doesn't have an item sales tax group, the item sales tax group that is specified in the sales tax parameters in General ledger is used.</span></span>

8. <span data-ttu-id="49a75-125">Facoltativo: nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="49a75-125">Optional: In the **Quantity** field, enter a number.</span></span>
9. <span data-ttu-id="49a75-126">Facoltativo: nel campo **Prezzo unitario** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="49a75-126">Optional: In the **Unit price** field, enter a number.</span></span>

    <span data-ttu-id="49a75-127">L'importo è calcolato come quantità per prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="49a75-127">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="49a75-128">Tuttavia è possibile ignorare questo calcolo immettendo un importo.</span><span class="sxs-lookup"><span data-stu-id="49a75-128">However, you can override that calculation by entering an amount.</span></span>

10. <span data-ttu-id="49a75-129">Selezionare **IVA** per visualizzare l'IVA che viene calcolata per la fattura.</span><span class="sxs-lookup"><span data-stu-id="49a75-129">Select **Sales tax** to view the sales tax that is calculated for the invoice.</span></span>

    <span data-ttu-id="49a75-130">È possibile visualizzare gli importi IVA in questa pagina o è possibile ignorare gli importi nella scheda **Rettifica**.</span><span class="sxs-lookup"><span data-stu-id="49a75-130">You can view the sales tax amounts on this page, or you can override the amounts on the **Adjustment** tab.</span></span>

11. <span data-ttu-id="49a75-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49a75-131">Select **OK**.</span></span>
12. <span data-ttu-id="49a75-132">Selezionare **Spese** per aggiungere una spesa alla fattura.</span><span class="sxs-lookup"><span data-stu-id="49a75-132">Select **Charges** to add a charge to the invoice.</span></span>
13. <span data-ttu-id="49a75-133">Nel campo **Codice spese** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="49a75-133">In the **Charges code** field, enter a value.</span></span>
14. <span data-ttu-id="49a75-134">Nel campo **Valore spese** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="49a75-134">In the **Charges value** field, enter a number.</span></span>
15. <span data-ttu-id="49a75-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="49a75-135">Close the page.</span></span>
16. <span data-ttu-id="49a75-136">Selezionare **Totali** per visualizzare un riepilogo dei dettagli e dei totali della fattura.</span><span class="sxs-lookup"><span data-stu-id="49a75-136">Select **Totals** to view a summary of the invoice details and totals.</span></span>
17. <span data-ttu-id="49a75-137">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="49a75-137">Select **Close**.</span></span>
18. <span data-ttu-id="49a75-138">Selezionare **Registra** per registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="49a75-138">Select **Post** to post the invoice.</span></span> <span data-ttu-id="49a75-139">Sarà ancora possibile annullare la fattura prima di registrarla.</span><span class="sxs-lookup"><span data-stu-id="49a75-139">You will still have an opportunity to cancel before you actually post.</span></span>

    * <span data-ttu-id="49a75-140">È possibile modificare il tempo di stampa delle fatture.</span><span class="sxs-lookup"><span data-stu-id="49a75-140">You can change the timing of invoice printing.</span></span> <span data-ttu-id="49a75-141">Selezionare **Corrente** per stampare ogni fattura man mano che viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="49a75-141">Select **Current** to print each invoice as it's updated.</span></span> <span data-ttu-id="49a75-142">Selezionare **Dopo** per eseguire la stampa dopo che tutte le fatture sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="49a75-142">Select **After** to print after all invoices have been updated.</span></span>
    * <span data-ttu-id="49a75-143">Per modificare il modo in cui il limite di credito del cliente viene verificato prima che la fattura venga registrata, modificare il valore nel campo **Tipo di limite di credito**.</span><span class="sxs-lookup"><span data-stu-id="49a75-143">To change how the customer's credit limit is verified before the invoice is posted, change the value in the **Credit limit type** field.</span></span>
    * <span data-ttu-id="49a75-144">Per stampare la fattura, impostare l'opzione su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="49a75-144">To print the invoice, set the option to **Yes**.</span></span>
    * <span data-ttu-id="49a75-145">Per registrare la fattura, impostare l'opzione su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="49a75-145">To post the invoice, set the option to **Yes**.</span></span> <span data-ttu-id="49a75-146">È possibile stampare la fattura senza registrarla.</span><span class="sxs-lookup"><span data-stu-id="49a75-146">You can print the invoice without posting it.</span></span>

19. <span data-ttu-id="49a75-147">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49a75-147">Select **OK**.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="49a75-148">Copia righe</span><span class="sxs-lookup"><span data-stu-id="49a75-148">Copy lines</span></span>
<span data-ttu-id="49a75-149">Per copiare le righe in una fattura a testo libero, selezionare una o più righe e quindi selezionare **Copia righe selezionate**.</span><span class="sxs-lookup"><span data-stu-id="49a75-149">To copy lines on a free text invoice, select one or more lines, and then select **Copy selected lines**.</span></span> <span data-ttu-id="49a75-150">È possibile specificare il numero di copie da eseguire, nonché copiare le note e gli allegati.</span><span class="sxs-lookup"><span data-stu-id="49a75-150">You can specify the number of copies to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="49a75-151">È possibile copiare le distribuzioni o permettere che vengano ricreate quando si effettua la registrazione.</span><span class="sxs-lookup"><span data-stu-id="49a75-151">You can either copy the distributions or let them be re-created when you post.</span></span>

<span data-ttu-id="49a75-152">Dopo aver copiato le righe, è possibile modificare le informazioni secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="49a75-152">After you copy lines, you can edit the information as you require.</span></span>

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="49a75-153">Creare una fattura a testo libero da un modello</span><span class="sxs-lookup"><span data-stu-id="49a75-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="49a75-154">L'utente può creare una fattura a testo libero da un modello.</span><span class="sxs-lookup"><span data-stu-id="49a75-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="49a75-155">Quando si seleziona **Nuovo da modello** nella scheda **Fattura**, è possibile selezionare un nome di modello e il conto cliente per la nuova fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="49a75-155">When you select **New from template** on the **Invoice** tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="49a75-156">Il cliente può compilare automaticamente i valori predefiniti, ad esempio i termini di pagamento e il metodo di pagamento, oppure è possibile utilizzare i valori che erano stati salvati nel modello.</span><span class="sxs-lookup"><span data-stu-id="49a75-156">Default values, such as the terms of payment and method of payment, can be automatically filled in from the customer, or you can use the values that were saved in the template.</span></span>

<span data-ttu-id="49a75-157">Viene creata una nuova fattura a testo libero ed è possibile modificare i valori secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="49a75-157">A new free text invoice is created, and you can edit the values as you require.</span></span>
