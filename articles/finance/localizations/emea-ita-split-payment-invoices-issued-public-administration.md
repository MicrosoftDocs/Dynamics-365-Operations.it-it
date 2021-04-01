---
title: Scissione dei pagamenti per fatture emesse alla Pubblica Amministrazione
description: In questo argomento vengono fornite informazioni sullo schema di contabilità di scissione dei pagamenti.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxBookSection, TaxGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 261314
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 234a3845547a661375b62590e19a78d0e8932570
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247972"
---
# <a name="split-payment-for-invoices-issued-to-the-public-administration"></a><span data-ttu-id="e9321-103">Scissione dei pagamenti per fatture emesse alla Pubblica Amministrazione</span><span class="sxs-lookup"><span data-stu-id="e9321-103">Split payment for invoices issued to the Public Administration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e9321-104">In questo argomento vengono fornite informazioni sullo schema di contabilità di scissione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="e9321-104">This topic provides information about the split payment accounting schema.</span></span>

<span data-ttu-id="e9321-105">Lo schema di contabilità di scissione dei pagamenti è valido per la vendita di merci e servizi resi alla Pubblica amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e9321-105">The split payment accounting schema is valid for the sale of goods and services rendered to the Public Administration.</span></span> <span data-ttu-id="e9321-106">Il meccanismo di scissione dei pagamenti trasferisce l'obbligo di pagamento delle imposte alla Pubblica amministrazione che sarà obbligata a pagare solo la base imponibile al fornitore.</span><span class="sxs-lookup"><span data-stu-id="e9321-106">The split payment mechanism transfers the tax payment obligation to the Public Administration who are obligated to pay only the taxable base to the supplier.</span></span> <span data-ttu-id="e9321-107">L'IVA viene accreditata in un conto riservato specifico.</span><span class="sxs-lookup"><span data-stu-id="e9321-107">The VAT is credited to a specific reserved account.</span></span> <span data-ttu-id="e9321-108">Le società con relazioni con la Pubblica amministrazione devono assicurarsi che l'IVA relativa venga registrata nelle vendite del registro, senza contribuire al pagamento IVA periodico.</span><span class="sxs-lookup"><span data-stu-id="e9321-108">Companies that have relationships with the Public Administration should ensure that the relevant VAT is recorded in the register sales, without contributing to the periodic VAT payment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9321-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e9321-109">Prerequisites</span></span>
<span data-ttu-id="e9321-110">Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="e9321-110">The following table shows the prerequisites that must be in place before you start.</span></span>

<span data-ttu-id="e9321-111">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e9321-111">**Category**</span></span>

<span data-ttu-id="e9321-112">**Prerequisito**</span><span class="sxs-lookup"><span data-stu-id="e9321-112">**Prerequisite**</span></span>

<span data-ttu-id="e9321-113">**Impostazioni**: registrazione IVA</span><span class="sxs-lookup"><span data-stu-id="e9321-113">**Setup:** Sales tax posting</span></span>

<span data-ttu-id="e9321-114">Creare un nuovo conto principale per la scissione dei pagamenti IVA, quindi selezionare **IVA** nel campo **Tipo di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="e9321-114">Create a new main account for VAT split payment, and then select **Sales tax** in the **Posting type** field.</span></span> <span data-ttu-id="e9321-115">Creare un gruppo di registrazione per la scissione dei pagamenti IVA, quindi selezionare il conto CoGe creato nei campi **IVA a debito**, **IVA a credito** e **Conto di liquidazione**.</span><span class="sxs-lookup"><span data-stu-id="e9321-115">Create a posting group for VAT split payment, and then select the created ledger account in the **Sales tax payable**, **Sales tax receivable**, and **Settlement account** fields.</span></span>

<span data-ttu-id="e9321-116">**Impostazione:** IVA</span><span class="sxs-lookup"><span data-stu-id="e9321-116">**Setup:** Sales tax</span></span>

<span data-ttu-id="e9321-117">Creare una **Fascia IVA** per la Pubblica amministrazione, quindi selezionare l'opzione **Scissione dei pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="e9321-117">Create a **Sales tax group** for the Public Administration, and then select the **Split payment** option.</span></span> <span data-ttu-id="e9321-118">Creare un codice IVA per la scissione dei pagamenti IVA.</span><span class="sxs-lookup"><span data-stu-id="e9321-118">Create a sales tax code for VAT split payment.</span></span> <span data-ttu-id="e9321-119">Impostare il valore utilizzabile per il paese, quindi aggiungere il codice IVA in **Fascia IVA** e **Fascia IVA articoli**.</span><span class="sxs-lookup"><span data-stu-id="e9321-119">Set the value applicable for the country/region, and then add the sales tax code in the **Sales tax group** and **Item Sales tax group**.</span></span>

<span data-ttu-id="e9321-120">**Impostazioni:** contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="e9321-120">**Setup:** Accounts receivable</span></span>

<span data-ttu-id="e9321-121">Impostare la **Sequenza numerica** per il riferimento **Giustificativo scissione dei pagamenti** nei parametri di contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="e9321-121">Set up the **Number sequence** for the **Split payment voucher** reference in Accounts payable parameters.</span></span> <span data-ttu-id="e9321-122">Selezionare il codice di sequenza numerica per registrare l'IVA stornata per le fatture nel meccanismo di scissione dei pagamenti per il riferimento **Giustificativo scissione dei pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="e9321-122">Select the number sequence code to post the reversed VAT for invoices under the split payment mechanism for the **Split payment voucher** reference.</span></span> <span data-ttu-id="e9321-123">Creare un gruppo di sequenze numeriche per il cliente - Pubblica amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e9321-123">Create a number sequence group for the Customer – Public Administration.</span></span> <span data-ttu-id="e9321-124">Nella scheda **Sequenze numeriche**, selezionare la riga con il riferimento **Giustificativo fattura a testo libero**, quindi fare clic sul pulsante **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="e9321-124">On the **Number sequences** tab, select the line with the **Free text invoice voucher** reference, and then click the **Group** button.</span></span> <span data-ttu-id="e9321-125">Nella pagina **Gruppi di sequenze numeriche**, creare un nuovo gruppo, quindi selezionare una sequenza numerica per i riferimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9321-125">In the **Number sequence groups** page, create a new group, and then select a number sequence for the following references:</span></span>

-   <span data-ttu-id="e9321-126">Giustificativo fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="e9321-126">Free text invoice voucher</span></span>
-   <span data-ttu-id="e9321-127">Giustificativo nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="e9321-127">Free text credit note voucher</span></span>
-   <span data-ttu-id="e9321-128">Giustificativo fattura cliente</span><span class="sxs-lookup"><span data-stu-id="e9321-128">Customer invoice voucher</span></span>
-   <span data-ttu-id="e9321-129">Giustificativo nota di accredito vendita</span><span class="sxs-lookup"><span data-stu-id="e9321-129">Sales credit note voucher</span></span>

<span data-ttu-id="e9321-130">Impostare **Fascia IVA** e **Gruppo di sequenze numeriche** per i Clienti- Pubblica amministrazione nella pagina **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="e9321-130">Set up a **Sales tax group** and **Number sequence group** for the Customers-Public Administration on the **All Customers** page.</span></span>

<span data-ttu-id="e9321-131">**Impostazioni:** libro IVA e sezione Libro IVA</span><span class="sxs-lookup"><span data-stu-id="e9321-131">**Setup:** VAT book and VAT book section</span></span>

<span data-ttu-id="e9321-132">Creare un nuovo libro IVA per registrare fatture alla Pubblica amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e9321-132">Create a new VAT book to register invoices to Public administration.</span></span> <span data-ttu-id="e9321-133">Creare una nuova sezione per il libro IVA.</span><span class="sxs-lookup"><span data-stu-id="e9321-133">Create a new section for the VAT book.</span></span>

<span data-ttu-id="e9321-134">**Transazioni correlate**</span><span class="sxs-lookup"><span data-stu-id="e9321-134">**Related transactions**</span></span>

-   <span data-ttu-id="e9321-135">Registrare una vendita a un cliente con le impostazioni di scissione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="e9321-135">Register a sale to a customer with split payment settings.</span></span>
-   <span data-ttu-id="e9321-136">Registrare una fattura a testo libero per un cliente con impostazioni di scissione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="e9321-136">Register a free text invoice for a customer with split payment settings.</span></span>

## <a name="working-with-the-split-payment-invoices"></a><span data-ttu-id="e9321-137">Utilizzo delle fatture di scissione dei pagamenti</span><span class="sxs-lookup"><span data-stu-id="e9321-137">Working with the split payment invoices</span></span>
<span data-ttu-id="e9321-138">Quando si registra la fattura, ad esempio un ordine cliente, una fattura a testo libero o una fattura di progetto.</span><span class="sxs-lookup"><span data-stu-id="e9321-138">When posting the invoice, such as sales order, free text invoice, or project invoice.</span></span> <span data-ttu-id="e9321-139">Con la fascia IVA di scissione dei pagamenti, le transazioni IVA di storno con i relativi codici di imposta vengono registrate per eliminare l'imposta accumulata.</span><span class="sxs-lookup"><span data-stu-id="e9321-139">with the Split payment sales tax group, the reversing sales tax transactions with relevant tax codes are posted to eliminate the tax being accrued.</span></span> <span data-ttu-id="e9321-140">Per ridurre il saldo cliente, una transazione cliente per l'importo IVA viene creata e automaticamente compensata con la fattura durante la registrazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="e9321-140">To reduce the customer balance, a customer transaction for the sales tax amount is created and automatically settled with the invoice while invoice posting.</span></span> <span data-ttu-id="e9321-141">In tal modo, il saldo cliente viene ridotto dell'importo IVA.</span><span class="sxs-lookup"><span data-stu-id="e9321-141">This reduces the customer balance by the VAT amount.</span></span> <span data-ttu-id="e9321-142">**Nota:** le transazioni IVA registrate con l'opzione **Scissione dei pagamenti** selezionata sono escluse dal processo di pagamento IVA.</span><span class="sxs-lookup"><span data-stu-id="e9321-142">**Note:** The tax transactions posted with the \*\*Split payment \*\*option selected are excluded from the sales tax payment process.</span></span> <span data-ttu-id="e9321-143">Le fatture create utilizzando il processo di scissione dei pagamenti hanno una "S" nel tag &lt;EsigibilitaIVA&gt;.</span><span class="sxs-lookup"><span data-stu-id="e9321-143">eInvoices created using the Split payment process have an "S" in the tag &lt;EsigibilitaIVA&gt;.</span></span>

### <a name="booking-example-for-sales-invoice"></a><span data-ttu-id="e9321-144">Esempio di prenotazione per la fattura di vendita</span><span class="sxs-lookup"><span data-stu-id="e9321-144">Booking example for sales invoice</span></span>

<span data-ttu-id="e9321-145">Nella seguente tabella è riportato un esempio di transazioni di contabilità generale per due transazioni cliente create per una fattura di scissione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="e9321-145">The following table shows an example of general ledger transactions for two customer transactions сreated for a split payment invoice.</span></span>

** **

<span data-ttu-id="e9321-146">**Conto**</span><span class="sxs-lookup"><span data-stu-id="e9321-146">**Account**</span></span>

<span data-ttu-id="e9321-147">**Dare**</span><span class="sxs-lookup"><span data-stu-id="e9321-147">**Debit**</span></span>

<span data-ttu-id="e9321-148">**Avere**</span><span class="sxs-lookup"><span data-stu-id="e9321-148">**Credit**</span></span>

<span data-ttu-id="e9321-149">**Contabilizzazione fattura**</span><span class="sxs-lookup"><span data-stu-id="e9321-149">**Invoice accounting**</span></span>

<span data-ttu-id="e9321-150">Cliente\_Società pubblica</span><span class="sxs-lookup"><span data-stu-id="e9321-150">Customer\_Public Company</span></span>

<span data-ttu-id="e9321-151">1220</span><span class="sxs-lookup"><span data-stu-id="e9321-151">1220</span></span>

<span data-ttu-id="e9321-152">Ricavi vendite</span><span class="sxs-lookup"><span data-stu-id="e9321-152">Sales revenue</span></span>

<span data-ttu-id="e9321-153">1000</span><span class="sxs-lookup"><span data-stu-id="e9321-153">1000</span></span>

<span data-ttu-id="e9321-154">Scissione dei pagamenti IVA</span><span class="sxs-lookup"><span data-stu-id="e9321-154">VAT split payment</span></span>

<span data-ttu-id="e9321-155">220</span><span class="sxs-lookup"><span data-stu-id="e9321-155">220</span></span>

<span data-ttu-id="e9321-156">**Eliminazione debito IVA**</span><span class="sxs-lookup"><span data-stu-id="e9321-156">**VAT debt elimination**</span></span>

<span data-ttu-id="e9321-157">Cliente\_Società pubblica</span><span class="sxs-lookup"><span data-stu-id="e9321-157">Customer\_Public Company</span></span>

<span data-ttu-id="e9321-158">220</span><span class="sxs-lookup"><span data-stu-id="e9321-158">220</span></span>

<span data-ttu-id="e9321-159">Scissione dei pagamenti IVA</span><span class="sxs-lookup"><span data-stu-id="e9321-159">VAT split payment</span></span>

<span data-ttu-id="e9321-160">220</span><span class="sxs-lookup"><span data-stu-id="e9321-160">220</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]