--- 
title: Crea una fattura a testo libero
description: "Questa guida attività dimostra la generazione di una fattura a testo libero."
author: mikefalkner
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33324a9b95026600bcc6facb9c22a04fd2e323c8
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="8b118-103">Crea una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="8b118-103">Create a free text invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b118-104">Questa guida attività dimostra la generazione di una fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="8b118-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="8b118-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="8b118-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="8b118-106">Andare a Contabilità clienti > Fatture > Tutte le fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="8b118-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="8b118-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8b118-107">Click New.</span></span>
3. <span data-ttu-id="8b118-108">Nel campo Conto cliente selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b118-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="8b118-109">Il conto fatture verrà impostato sul conto utilizzato per il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="8b118-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="8b118-110">Lo stato iniziale della contabilità è In corso se la fattura non è registrata.</span><span class="sxs-lookup"><span data-stu-id="8b118-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="8b118-111">Il numero fattura viene assegnato al momento della registrazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="8b118-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="8b118-112">Se si utilizzano i mandati SEPA, il mandato di addebito diretto verrà automaticamente popolato con un mandato, quando si seleziona il conto cliente.</span><span class="sxs-lookup"><span data-stu-id="8b118-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="8b118-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b118-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8b118-114">Nel campo Conto principale, specificare un numero di conto senza dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8b118-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="8b118-115">È anche possibile immettere uno o più caratteri per il conto principale e utilizzare la ricerca per trovare il conto.</span><span class="sxs-lookup"><span data-stu-id="8b118-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="8b118-116">Le dimensioni verranno immesse successivamente nella guida.</span><span class="sxs-lookup"><span data-stu-id="8b118-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="8b118-117">Espandere la scheda dettaglio Dettagli riga in modo da poter aggiungere dimensioni al conto principale.</span><span class="sxs-lookup"><span data-stu-id="8b118-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="8b118-118">Fare clic sulla scheda Riga dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="8b118-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="8b118-119">Le dimensioni sono relative solo alla riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b118-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="8b118-120">La fascia IVA viene popolata dal cliente.</span><span class="sxs-lookup"><span data-stu-id="8b118-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="8b118-121">Se il cliente non dispone di una fascia IVA, viene utilizzata la fascia IVA del conto principale.</span><span class="sxs-lookup"><span data-stu-id="8b118-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="8b118-122">La fascia IVA articoli viene popolata dal conto principale.</span><span class="sxs-lookup"><span data-stu-id="8b118-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="8b118-123">Se il conto principale non dispone di una fascia IVA articoli, viene utilizzata quella dei parametri IVA di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="8b118-123">If the main account does not have a item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="8b118-124">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8b118-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8b118-125">La quantità è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8b118-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="8b118-126">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8b118-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="8b118-127">Il prezzo unitario è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8b118-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="8b118-128">L'importo è calcolato come quantità per prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="8b118-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="8b118-129">Tuttavia è possibile ignorare questo calcolo e immettere un importo.</span><span class="sxs-lookup"><span data-stu-id="8b118-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="8b118-130">Fare clic su IVA per visualizzare l'IVA calcolata per la fattura.</span><span class="sxs-lookup"><span data-stu-id="8b118-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="8b118-131">Visualizzare gli importi IVA nella pagina o ignorare gli importi nella scheda Rettifica.</span><span class="sxs-lookup"><span data-stu-id="8b118-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="8b118-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b118-132">Click OK.</span></span>
12. <span data-ttu-id="8b118-133">Fare clic su Spese per aggiungere una spesa alla fattura.</span><span class="sxs-lookup"><span data-stu-id="8b118-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="8b118-134">Digitare un valore nel campo Codice spese.</span><span class="sxs-lookup"><span data-stu-id="8b118-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="8b118-135">Nel campo Valore spese immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8b118-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="8b118-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b118-136">Close the page.</span></span>
16. <span data-ttu-id="8b118-137">Fare clic su Totali per visualizzare il riepilogo dei totali e dei dettagli della fattura.</span><span class="sxs-lookup"><span data-stu-id="8b118-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="8b118-138">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="8b118-138">Click Close.</span></span>
18. <span data-ttu-id="8b118-139">Scegliere Registra per registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="8b118-139">Click Post to post the invoice.</span></span> <span data-ttu-id="8b118-140">Sarà possibile annullare prima di registrare.</span><span class="sxs-lookup"><span data-stu-id="8b118-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="8b118-141">Per modificare il tempo di stampa delle fatture: selezionare Corrente per stampare ciascuna fattura non appena viene aggiornata oppure selezionare Dopo per stampare dopo che tutte le fatture sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="8b118-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="8b118-142">Se si desidera modificare la modalità in cui il limite di credito del cliente viene verificato prima della registrazione, modificare il tipo di limite di credito.</span><span class="sxs-lookup"><span data-stu-id="8b118-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="8b118-143">Se si desidera stampare la fattura, selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="8b118-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="8b118-144">Se si desidera registrare la fattura selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="8b118-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="8b118-145">È possibile stampare la fattura senza registrare.</span><span class="sxs-lookup"><span data-stu-id="8b118-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="8b118-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b118-146">Click OK.</span></span>


