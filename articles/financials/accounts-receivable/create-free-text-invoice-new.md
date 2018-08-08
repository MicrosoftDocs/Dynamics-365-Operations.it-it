--- 
title: Crea una fattura a testo libero
description: Questo articolo illustra come creare una fattura a testo libero.
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e6f89a6d77ff8e1cd88632df0d9a72915086ee1e
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="create-a-free-text-invoice"></a><span data-ttu-id="90366-103">Crea una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="90366-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90366-104">Questo articolo illustra come creare una fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="90366-104">This article demonstrates how to create a free text invoice.</span></span> <span data-ttu-id="90366-105">Per questa procedura utilizzare la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="90366-105">For this procedure, use the USMF demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="90366-106">Crea una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="90366-106">Create a free text invoice</span></span>

1. <span data-ttu-id="90366-107">Andare a Contabilità clienti > Fatture > Tutte le fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="90366-107">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="90366-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="90366-108">Click New.</span></span>
3. <span data-ttu-id="90366-109">Nel campo Conto cliente selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="90366-109">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="90366-110">Il conto fatture verrà impostato sul conto utilizzato per il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="90366-110">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="90366-111">Lo stato iniziale della contabilità è In corso se la fattura non è registrata.</span><span class="sxs-lookup"><span data-stu-id="90366-111">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="90366-112">Il numero fattura viene assegnato al momento della registrazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="90366-112">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="90366-113">Se si utilizzano i mandati SEPA, il mandato di addebito diretto verrà automaticamente popolato con un mandato, quando si seleziona il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="90366-113">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="90366-114">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="90366-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="90366-115">Nel campo Conto principale, specificare un numero di conto senza dimensioni.</span><span class="sxs-lookup"><span data-stu-id="90366-115">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="90366-116">È anche possibile immettere uno o più caratteri per il conto principale e utilizzare la ricerca per trovare il conto.</span><span class="sxs-lookup"><span data-stu-id="90366-116">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="90366-117">Le dimensioni verranno immesse successivamente nella guida.</span><span class="sxs-lookup"><span data-stu-id="90366-117">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="90366-118">Espandere la scheda dettaglio Dettagli riga in modo da poter aggiungere dimensioni al conto principale.</span><span class="sxs-lookup"><span data-stu-id="90366-118">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="90366-119">Fare clic sulla scheda Riga dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="90366-119">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="90366-120">Le dimensioni sono relative solo alla riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="90366-120">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="90366-121">La fascia IVA viene popolata dal cliente.</span><span class="sxs-lookup"><span data-stu-id="90366-121">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="90366-122">Se il cliente non dispone di una fascia IVA, viene utilizzata la fascia IVA del conto principale.</span><span class="sxs-lookup"><span data-stu-id="90366-122">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="90366-123">La fascia IVA articoli viene popolata dal conto principale.</span><span class="sxs-lookup"><span data-stu-id="90366-123">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="90366-124">Se il conto principale non dispone di una fascia IVA articoli, viene utilizzata quella dei parametri IVA di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="90366-124">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="90366-125">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="90366-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="90366-126">La quantità è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="90366-126">The quantity is optional.</span></span>  
9. <span data-ttu-id="90366-127">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="90366-127">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="90366-128">Il prezzo unitario è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="90366-128">The unit price is optional.</span></span>  
    * <span data-ttu-id="90366-129">L'importo è calcolato come quantità per prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="90366-129">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="90366-130">Tuttavia è possibile ignorare questo calcolo e immettere un importo.</span><span class="sxs-lookup"><span data-stu-id="90366-130">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="90366-131">Fare clic su IVA per visualizzare l'IVA calcolata per la fattura.</span><span class="sxs-lookup"><span data-stu-id="90366-131">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="90366-132">Visualizzare gli importi IVA nella pagina o ignorare gli importi nella scheda Rettifica.</span><span class="sxs-lookup"><span data-stu-id="90366-132">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="90366-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="90366-133">Click OK.</span></span>
12. <span data-ttu-id="90366-134">Fare clic su Spese per aggiungere una spesa alla fattura.</span><span class="sxs-lookup"><span data-stu-id="90366-134">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="90366-135">Digitare un valore nel campo Codice spese.</span><span class="sxs-lookup"><span data-stu-id="90366-135">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="90366-136">Nel campo Valore spese immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="90366-136">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="90366-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="90366-137">Close the page.</span></span>
16. <span data-ttu-id="90366-138">Fare clic su Totali per visualizzare il riepilogo dei totali e dei dettagli della fattura.</span><span class="sxs-lookup"><span data-stu-id="90366-138">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="90366-139">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="90366-139">Click Close.</span></span>
18. <span data-ttu-id="90366-140">Scegliere Registra per registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="90366-140">Click Post to post the invoice.</span></span> <span data-ttu-id="90366-141">Sarà possibile annullare prima di registrare.</span><span class="sxs-lookup"><span data-stu-id="90366-141">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="90366-142">Per modificare il tempo di stampa delle fatture: selezionare Corrente per stampare ciascuna fattura non appena viene aggiornata oppure selezionare Dopo per stampare dopo che tutte le fatture sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="90366-142">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="90366-143">Se si desidera modificare la modalità in cui il limite di credito del cliente viene verificato prima della registrazione, modificare il tipo di limite di credito.</span><span class="sxs-lookup"><span data-stu-id="90366-143">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="90366-144">Se si desidera stampare la fattura, selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="90366-144">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="90366-145">Se si desidera registrare la fattura selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="90366-145">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="90366-146">È possibile stampare la fattura senza registrare.</span><span class="sxs-lookup"><span data-stu-id="90366-146">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="90366-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="90366-147">Click OK.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="90366-148">Copia righe</span><span class="sxs-lookup"><span data-stu-id="90366-148">Copy lines</span></span>
<span data-ttu-id="90366-149">Per copiare le righe della fattura a testo libero, selezionare una o più righe e quindi fare clic su Copia righe selezionate.</span><span class="sxs-lookup"><span data-stu-id="90366-149">To copy lines on the free text invoice, select one or more lines and then click Copy selected lines.</span></span> <span data-ttu-id="90366-150">È possibile specificare il numero di copie che si desidera nonché copiare note e gli allegati.</span><span class="sxs-lookup"><span data-stu-id="90366-150">You can specify the number of copies that you want to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="90366-151">È possibile copiare le distribuzioni o permettere che siano ricreate quando si effettua la registrazione.</span><span class="sxs-lookup"><span data-stu-id="90366-151">You can copy the distributions or allow them to be recreated when you post.</span></span> <span data-ttu-id="90366-152">Dopo aver copiato le linee le informazioni potranno quindi essere modificate secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="90366-152">Once you copy the lines, you can edit the information as needed.</span></span> 

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="90366-153">Creare una fattura a testo libero da un modello</span><span class="sxs-lookup"><span data-stu-id="90366-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="90366-154">L'utente può creare una fattura a testo libero da un modello.</span><span class="sxs-lookup"><span data-stu-id="90366-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="90366-155">Quando si seleziona Nuovo dal modello dalla scheda Fattura, è possibile selezionare un nome modello e l'account cliente per la nuova fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="90366-155">When you select New from template from the Invoice tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="90366-156">È inoltre possibile scegliere i valori predefiniti ad esempio i termini di pagamento e il metodo di pagamento dal cliente oppure utilizzare i valori che sono stati salvati con il modello.</span><span class="sxs-lookup"><span data-stu-id="90366-156">You can also choose to default values such as the terms of payment and method of payment from the customer or use the values that were saved with the template.</span></span> <span data-ttu-id="90366-157">Una nuova fattura a testo libero verrà creata ed è possibile modificare i valori nella fattura.</span><span class="sxs-lookup"><span data-stu-id="90366-157">A new free text invoice will be created and you can edit the values in that invoice.</span></span> 


