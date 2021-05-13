---
title: L'imposta è registrata nel conto CoGe sbagliato nel giustificativo
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando l'imposta viene registrata nel conto CoGe errato nel giustificativo.
author: qire
manager: beya
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0404d71f0492e188ed5da62387bb90a336e69c5a
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947663"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a><span data-ttu-id="25001-103">L'imposta è registrata nel conto CoGe sbagliato nel giustificativo</span><span class="sxs-lookup"><span data-stu-id="25001-103">Tax is posted to the wrong ledger account in the voucher</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25001-104">Durante la registrazione, l'importa potrebbe essere registrata nel conto CoGe sbagliato nel giustificativo.</span><span class="sxs-lookup"><span data-stu-id="25001-104">During posting, tax might be posted to the wrong ledger account in the voucher.</span></span> <span data-ttu-id="25001-105">Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto.</span><span class="sxs-lookup"><span data-stu-id="25001-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span> <span data-ttu-id="25001-106">Gli esempi in questo argomento utilizzano un ordine cliente come documento aziendale.</span><span class="sxs-lookup"><span data-stu-id="25001-106">The examples in this topic use a sales order as the business document.</span></span>

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a><span data-ttu-id="25001-107">Trovare il codice imposta della transazione fiscale registrata in modo errato</span><span class="sxs-lookup"><span data-stu-id="25001-107">Find the tax code of the incorrectly posted tax transaction</span></span>

1. <span data-ttu-id="25001-108">Nella pagina **Transazioni giustificativo** selezionare la transazione con cui si desidera lavorare, quindi selezionare **IVA registrata**.</span><span class="sxs-lookup"><span data-stu-id="25001-108">On the **Voucher transactions** page, select the transaction that you want to work with, and then select **Posted sales tax**.</span></span>

    <span data-ttu-id="25001-109">[![Pulsante IVA registrata nella pagina Transazioni giustificativo](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="25001-109">[![Posted sales tax button on the Voucher transactions page](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span></span>

2. <span data-ttu-id="25001-110">Nel campo **Codice IVA** rivedere il valore.</span><span class="sxs-lookup"><span data-stu-id="25001-110">Review the value in the **Sales tax code** field.</span></span> <span data-ttu-id="25001-111">In questo esempio, è **IVA 19**.</span><span class="sxs-lookup"><span data-stu-id="25001-111">In this example, it's **VAT 19**.</span></span>

    <span data-ttu-id="25001-112">[![Campo Codice IVA nella pagina IVA registrata](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="25001-112">[![Sales tax code field on the Posted sales tax page](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span></span>

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a><span data-ttu-id="25001-113">Controllare il gruppo di registrazione contabile del codice imposta</span><span class="sxs-lookup"><span data-stu-id="25001-113">Check the ledger posting group of the tax code</span></span>

1. <span data-ttu-id="25001-114">Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="25001-114">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
2. <span data-ttu-id="25001-115">Trova e seleziona il codice imposta, quindi controlla il valore nel campo **Gruppo registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="25001-115">Find and select the tax code, and then review the value in the **Ledger posting group** field.</span></span> <span data-ttu-id="25001-116">In questo esempio, è **IVA**.</span><span class="sxs-lookup"><span data-stu-id="25001-116">In this example, it's **VAT**.</span></span>

    <span data-ttu-id="25001-117">[![Campo Gruppo registrazione contabile nella pagina dei codici IVA](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="25001-117">[![Ledger posting group field on the Sales tax codes page](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span></span>

3. <span data-ttu-id="25001-118">Il valore nel campo **Gruppo registrazione contabile** è un collegamento.</span><span class="sxs-lookup"><span data-stu-id="25001-118">The value in the **Ledger posting group** field is a link.</span></span> <span data-ttu-id="25001-119">Per visualizzare i dettagli della configurazione del gruppo, selezionare il collegamento.</span><span class="sxs-lookup"><span data-stu-id="25001-119">To view the details of the group's configuration, select the link.</span></span> <span data-ttu-id="25001-120">In alternativa, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il campo, quindi seleziona **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="25001-120">Alternatively, select and hold (or right-click) in the field, and then select **View details**.</span></span>

    <span data-ttu-id="25001-121">[![Comando Visualizza dettagli](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="25001-121">[![View details command](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span></span>

4. <span data-ttu-id="25001-122">Nel campo **IVA a debito** verificare che il numero di conto sia corretto, in base al tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="25001-122">In the **Sales tax payable** field, verify that the account number is correct, according to the transaction type.</span></span> <span data-ttu-id="25001-123">In caso contrario, seleziona il conto corretto in cui registrare.</span><span class="sxs-lookup"><span data-stu-id="25001-123">If it isn't, select the correct account to post to.</span></span> <span data-ttu-id="25001-124">In questo esempio, l'IVA dell'ordine fornitore deve essere registrata nel conto IVA a debito 222200.</span><span class="sxs-lookup"><span data-stu-id="25001-124">In this example, the sales tax of the sales order should be posted to sales tax payable account 222200.</span></span>

    <span data-ttu-id="25001-125">[![Il campo IVA a debito nella pagina dei gruppi di registrazione contabile](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="25001-125">[![Sales tax payable field on the Ledger posting groups page](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span></span>

    <span data-ttu-id="25001-126">La tabella seguente fornisce informazioni su ogni campo nella pagina **Gruppi registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="25001-126">The following table provides information about each field on the **Ledger posting groups** page.</span></span>

    | <span data-ttu-id="25001-127">Campo</span><span class="sxs-lookup"><span data-stu-id="25001-127">Field</span></span>                  | <span data-ttu-id="25001-128">descrizione</span><span class="sxs-lookup"><span data-stu-id="25001-128">Description</span></span> |
    |------------------------|-------------|
    | <span data-ttu-id="25001-129">IVA a debito</span><span class="sxs-lookup"><span data-stu-id="25001-129">Sales tax payable</span></span>      | <span data-ttu-id="25001-130">Immettere il conto principale per l'IVA in uscita (pagabile all'ufficio IVA).</span><span class="sxs-lookup"><span data-stu-id="25001-130">The main account for outgoing sales taxes that are payable to the tax authority.</span></span> |
    | <span data-ttu-id="25001-131">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="25001-131">Sales tax receivable</span></span>   | <span data-ttu-id="25001-132">Il conto principale per l'IVA in entrata proveniente dall'ufficio IVA.</span><span class="sxs-lookup"><span data-stu-id="25001-132">The main account for incoming taxes that are received from the tax authority.</span></span> |
    | <span data-ttu-id="25001-133">Importo IVA intracomunitaria</span><span class="sxs-lookup"><span data-stu-id="25001-133">Use tax expense</span></span>        | <span data-ttu-id="25001-134">Il conto principale utilizzato per registrare le imposte di utilizzo deducibili che i fornitori non richiedono o non dichiarano all'autorità fiscale come parte dell'Imposta sui Beni e Servizi (GST)/Harmonized Sales Tax (HST) reverse charge dell'Unione europea (UE).</span><span class="sxs-lookup"><span data-stu-id="25001-134">The main account that is used to post deductible use taxes that vendors don't claim or report to the tax authority as part of European Union (EU) reverse charge Goods and Services Tax (GST)/Harmonized Sales Tax (HST).</span></span> <span data-ttu-id="25001-135">L'opzione **IVA intracomunitaria** deve essere selezionata per il codice IVA nella fascia IVA utilizzata nella transazione.</span><span class="sxs-lookup"><span data-stu-id="25001-135">**Use tax** must be selected for the sales tax code in the sales tax group that is used in the transaction.</span></span> <span data-ttu-id="25001-136">Questo campo non è disponibile se è selezionata l'opzione **Applica regole di tassazione IVA** nella pagina **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="25001-136">This field isn't available if **Apply sales tax taxation rules** is selected on the **General ledger parameters** page.</span></span> |
    | <span data-ttu-id="25001-137">IVA intracomunitaria a debito</span><span class="sxs-lookup"><span data-stu-id="25001-137">Use tax payable</span></span>        | <span data-ttu-id="25001-138">Conto principale utilizzato per registrare le imposte di utilizzo in entrata pagabili alle autorità fiscali.</span><span class="sxs-lookup"><span data-stu-id="25001-138">The main account that is used to post incoming use taxes that are payable to tax authorities.</span></span> |
    | <span data-ttu-id="25001-139">Conto di liquidazione</span><span class="sxs-lookup"><span data-stu-id="25001-139">Settlement account</span></span>     | <span data-ttu-id="25001-140">Conto principale utilizzato per registrare il saldo netto dei conti CoGe specificati nei campi **VAT intracomunitaria a debito** e **IVA a credito**.</span><span class="sxs-lookup"><span data-stu-id="25001-140">The main account that is used to post the net balance of the ledger accounts that are specified in the **Use tax payable** and **Sales tax receivable** fields.</span></span> |
    | <span data-ttu-id="25001-141">Sconto di cassa fornitore</span><span class="sxs-lookup"><span data-stu-id="25001-141">Vendor cash discount</span></span>   | <span data-ttu-id="25001-142">Il conto principale utilizzato per la registrazione di uno sconto di cassa per i codici IVA associati al gruppo di registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="25001-142">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |
    | <span data-ttu-id="25001-143">Sconto di cassa cliente</span><span class="sxs-lookup"><span data-stu-id="25001-143">Customer case discount</span></span> | <span data-ttu-id="25001-144">Il conto principale utilizzato per la registrazione di uno sconto di cassa per i codici IVA associati al gruppo di registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="25001-144">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |

    <span data-ttu-id="25001-145">Per ulteriori informazioni, vedere [Impostare gruppi di registrazione contabile per l'IVA](tasks/set-up-ledger-posting-groups-sales-tax.md).</span><span class="sxs-lookup"><span data-stu-id="25001-145">For more information, see, [Set up Ledger posting groups for sales tax](tasks/set-up-ledger-posting-groups-sales-tax.md)</span></span>

## <a name="debug-in-code-to-check-ledger-dimensions"></a><span data-ttu-id="25001-146">Eseguire il debug nel codice per controllare le dimensioni contabili</span><span class="sxs-lookup"><span data-stu-id="25001-146">Debug in code to check ledger dimensions</span></span>

<span data-ttu-id="25001-147">Nel codice, il conto di registrazione è determinato dalla dimensione contabile.</span><span class="sxs-lookup"><span data-stu-id="25001-147">In the code, the posting account is determined by the ledger dimension.</span></span> <span data-ttu-id="25001-148">La dimensione contabile salva l'ID record di un conto nel database.</span><span class="sxs-lookup"><span data-stu-id="25001-148">The ledger dimension saves the record ID of an account in the database.</span></span>

1. <span data-ttu-id="25001-149">Per un ordine cliente, aggiungere un punto di interruzione nei metodi **Tax::saveAndPost()** e **Tax::post()**.</span><span class="sxs-lookup"><span data-stu-id="25001-149">For a sales order, add a breakpoint at the **Tax::saveAndPost()** and **Tax::post()** methods.</span></span> <span data-ttu-id="25001-150">Presta attenzione al valore di **\_ledgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="25001-150">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="25001-151">[![Esempio di codice di ordine cliente con un punto di interruzione](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="25001-151">[![Sales order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span></span>

    <span data-ttu-id="25001-152">Per un ordine fornitore, aggiungere un punto di interruzione ai metodi **TaxPost::saveAndPost()** e **TaxPost::postToTaxTrans()**.</span><span class="sxs-lookup"><span data-stu-id="25001-152">For a purchase order, add a breakpoint at the **TaxPost::saveAndPost()** and **TaxPost::postToTaxTrans()** methods.</span></span> <span data-ttu-id="25001-153">Presta attenzione al valore di **\_ledgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="25001-153">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="25001-154">[![Esempio di codice di ordine fornitore con un punto di interruzione](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span><span class="sxs-lookup"><span data-stu-id="25001-154">[![Purchase order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span></span>

2. <span data-ttu-id="25001-155">Eseguire la seguente query SQL per trovare il valore visualizzato del conto nel database, in base all'ID record salvato dalla dimensione contabile.</span><span class="sxs-lookup"><span data-stu-id="25001-155">Run the following SQL query to find the display value of the account in the database, based on the record ID that is saved by the ledger dimension.</span></span>

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    <span data-ttu-id="25001-156">[![Valore visualizzato dell'ID record](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span><span class="sxs-lookup"><span data-stu-id="25001-156">[![Display value of the record ID](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span></span>

3. <span data-ttu-id="25001-157">Esamina il callstack per trovare dove il valore **_ledgerDimension** viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="25001-157">Examine the callstack to find where the **_ledgerDimension** value is assigned.</span></span> <span data-ttu-id="25001-158">Di solito, il valore proviene da **TmpTaxWorkTrans**.</span><span class="sxs-lookup"><span data-stu-id="25001-158">Usually, the value is from **TmpTaxWorkTrans**.</span></span> <span data-ttu-id="25001-159">In questo caso, dovresti aggiungere un punto di interruzione in **TmpTaxWorkTrans::insert()** e **TmpTaxWorkTrans::update()** per trovare dove il valore assegnato.</span><span class="sxs-lookup"><span data-stu-id="25001-159">In this case, you should add a breakpoint at **TmpTaxWorkTrans::insert()** and **TmpTaxWorkTrans::update()** to find where the value assigned.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="25001-160">Determinare se esiste la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="25001-160">Determine whether customization exists</span></span>

<span data-ttu-id="25001-161">Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="25001-161">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="25001-162">Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="25001-162">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
