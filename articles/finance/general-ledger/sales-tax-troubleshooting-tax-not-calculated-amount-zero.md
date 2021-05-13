---
title: L'imposta non viene calcolata o l'importo dell'imposta è zero
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando l'importo dell'imposta è 0 (zero) o l'imposta non viene calcolata.
author: shtao
ms.date: 04/01/2021
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
ms.openlocfilehash: ead979081692d4dcee9812c89f5f10c7879d3f7e
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947662"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a><span data-ttu-id="a2989-103">L'imposta non viene calcolata o l'importo dell'imposta è zero</span><span class="sxs-lookup"><span data-stu-id="a2989-103">Tax isn't calculated or the tax amount is zero</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2989-104">Una transazione potrebbe avere un importo di riga diverso da 0 (zero), ma l'imposta non viene calcolata o l'importo calcolato dell'imposta è 0.</span><span class="sxs-lookup"><span data-stu-id="a2989-104">A transaction might have a line amount that isn't 0 (zero), but either tax isn't calculated or the calculated tax amount is 0.</span></span> <span data-ttu-id="a2989-105">Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto.</span><span class="sxs-lookup"><span data-stu-id="a2989-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a><span data-ttu-id="a2989-106">Verificare che i codici imposta siano selezionati correttamente dalla transazione</span><span class="sxs-lookup"><span data-stu-id="a2989-106">Verify that tax codes are correctly selected by the transaction</span></span>

<span data-ttu-id="a2989-107">Se la transazione non seleziona i codici imposta corretti o se non seleziona alcun codice imposta, le tasse non verranno calcolate su di essa.</span><span class="sxs-lookup"><span data-stu-id="a2989-107">If the transaction doesn't select the correct tax codes, or if it doesn't select any tax codes, taxes won't be calculated on it.</span></span> <span data-ttu-id="a2989-108">Segui questi passaggi per verificare che i codici imposta siano selezionati correttamente dalla transazione</span><span class="sxs-lookup"><span data-stu-id="a2989-108">Follow these steps to verify that tax codes are correctly selected by the transaction.</span></span> 

1. <span data-ttu-id="a2989-109">Nella riga della transazione, nella scheda dettaglio **Dettagli riga**, nella scheda **Impostazioni**, nella sezione **IVA**, verifica che siano selezionate le fasce IVA corrette nei campi **Fascia IVA articoli** e **Fascia IVA**.</span><span class="sxs-lookup"><span data-stu-id="a2989-109">On the transaction line, on the **Line details** FastTab, on the **Setup** tab, in the **Sales tax** section, verify that the correct tax groups are selected in the **Item sales tax group** and **Sales tax group** fields.</span></span> <span data-ttu-id="a2989-110">Se non sono selezionate le fasce IVA corrette, selezionale.</span><span class="sxs-lookup"><span data-stu-id="a2989-110">If the correct tax groups aren't selected, select them.</span></span>

    <span data-ttu-id="a2989-111">[![Campi Fascia IVA articoli e Fascia IVA](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="a2989-111">[![Item sales tax group and Sales tax group fields](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span></span>

2. <span data-ttu-id="a2989-112">Passare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Fasce IVA**.</span><span class="sxs-lookup"><span data-stu-id="a2989-112">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
3. <span data-ttu-id="a2989-113">Seleziona la fascia IVA appropriata, quindi, nella Scheda dettaglio **Impostazioni**, prendere nota del codice imposta nel campo **Codice IVA**.</span><span class="sxs-lookup"><span data-stu-id="a2989-113">Select the appropriate sales tax group, and then, on the **Setup** FastTab, make a note of the tax code in the **Sales tax code** field.</span></span>

    <span data-ttu-id="a2989-114">[![Pagina Fasce IVA](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="a2989-114">[![Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span></span>

4. <span data-ttu-id="a2989-115">Passare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Fasce IVA articoli**.</span><span class="sxs-lookup"><span data-stu-id="a2989-115">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
5. <span data-ttu-id="a2989-116">Selezionare la fascia IVA articoli appropriata e quindi, nel Scheda dettaglio **Impostazioni**, verificare che il codice imposta nel campo **Codice IVA** corrisponde al codice imposta della fascia IVA.</span><span class="sxs-lookup"><span data-stu-id="a2989-116">Select the appropriate item sales tax group, and then, on the **Setup** FastTab, verify that the tax code in the **Sales tax code** field matches the tax code of the sales tax group.</span></span>

    <span data-ttu-id="a2989-117">[![Pagina Fasce IVA articoli](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="a2989-117">[![Item sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span></span>

6. <span data-ttu-id="a2989-118">Se i codici imposta non corrispondono, aggiorna il codice IVA per uno dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="a2989-118">If the tax codes don't match, update the sales tax code for one of the groups.</span></span>

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a><span data-ttu-id="a2989-119">Verificare che i codici imposta selezionati non siano esenti e che abbiano il valore dell'aliquota fiscale corretto</span><span class="sxs-lookup"><span data-stu-id="a2989-119">Verify that the selected tax codes aren't exempt and that they have the correct tax rate value</span></span>

<span data-ttu-id="a2989-120">Se i codici imposta sono esenti o se l'aliquota fiscale è 0 (zero), il risultato del calcolo dell'imposta sarà 0.</span><span class="sxs-lookup"><span data-stu-id="a2989-120">If the tax codes are exempt, or if the tax rate is 0 (zero), the tax calculation result will be 0.</span></span> <span data-ttu-id="a2989-121">Segui questi passaggi per determinare se i codici imposta selezionati sono esenti e per verificare che ad essi sia applicata l'aliquota fiscale corretta.</span><span class="sxs-lookup"><span data-stu-id="a2989-121">Follow these steps to determine whether the selected tax codes are exempt and to verify that the correct tax rate is applied to them.</span></span>

1. <span data-ttu-id="a2989-122">Passare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Fasce IVA**.</span><span class="sxs-lookup"><span data-stu-id="a2989-122">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="a2989-123">Seleziona la fascia IVA appropriata, quindi, nella scheda dettaglio **Impostazioni**, verificare che la casella di controllo **Esenzione** è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="a2989-123">Select the appropriate sales tax group, and then, on the **Setup** FastTab, verify that the **Exempt** check box is cleared.</span></span> <span data-ttu-id="a2989-124">Se è selezionata, deselezionala.</span><span class="sxs-lookup"><span data-stu-id="a2989-124">If it's selected, clear it.</span></span>

    <span data-ttu-id="a2989-125">[![Casella di controllo Esenzione nella pagina Fasce IVA](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="a2989-125">[![Exempt check box on the Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span></span>

3. <span data-ttu-id="a2989-126">Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="a2989-126">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="a2989-127">Seleziona il codice IVA appropriato, quindi verifica che il valore dell'aliquota fiscale nel campo **Valore** non è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a2989-127">Select the appropriate sales tax code, and then verify that the tax rate value in the **Value** field isn't 0 (zero).</span></span> <span data-ttu-id="a2989-128">Se è 0, aggiorna il campo in modo che sia impostato sull'aliquota fiscale corretta.</span><span class="sxs-lookup"><span data-stu-id="a2989-128">If it's 0, update the field so that it's set to the correct tax rate.</span></span>

    <span data-ttu-id="a2989-129">[![Campo Valorr nella pagina Valori codice IVA](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="a2989-129">[![Value field on the Sales tax code values page](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span></span>

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a><span data-ttu-id="a2989-130">Determina se zero è l'importo dell'imposta corretto</span><span class="sxs-lookup"><span data-stu-id="a2989-130">Determine whether zero is the correct tax amount</span></span>

<span data-ttu-id="a2989-131">In alcuni scenari, un importo di imposta pari a 0 (zero) è corretto.</span><span class="sxs-lookup"><span data-stu-id="a2989-131">In some scenarios, a tax amount of 0 (zero) is correct.</span></span> <span data-ttu-id="a2989-132">Segui questi passaggi per determinare se 0 è l'importo fiscale corretto per la tua transazione.</span><span class="sxs-lookup"><span data-stu-id="a2989-132">Follow these steps to determine whether 0 is the correct tax amount for your transaction.</span></span>

1. <span data-ttu-id="a2989-133">Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="a2989-133">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="a2989-134">Nella scheda **IVA**, nel campo **Metodo di calcolo**, verifica che **Totale** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="a2989-134">On the **Sales tax** tab, in the **Calculation method** field, verify that **Total** is selected.</span></span>

    <span data-ttu-id="a2989-135">[![Campo Metodo di calcolo nella pagina Parametri di contabilità generale](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="a2989-135">[![Calculation method field on the General ledger parameters page](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span></span>

3. <span data-ttu-id="a2989-136">Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="a2989-136">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="a2989-137">Seleziona il codice IVA appropriato, seleziona **Calcolo** \> **Base marginale** e verifica che la base marginale sia impostata su **Importo netto del saldo fattura** o **Totale fattura inclusi altri importi IVA**.</span><span class="sxs-lookup"><span data-stu-id="a2989-137">Select the appropriate sales tax code, select **Calculation** \> **Marginal base**, and verify that the marginal base is set to **Net amount of invoice balance** or **Invoice total incl. other sales tax amounts**.</span></span> <span data-ttu-id="a2989-138">Per ulteriori informazioni, vedere [Totale fattura inclusi altri importi IVA](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span><span class="sxs-lookup"><span data-stu-id="a2989-138">For more information, see the [Invoice total incl. other sales tax amounts](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span></span>
5. <span data-ttu-id="a2989-139">Se i valori corretti sono impostati nei passaggi 2 e 4, determinare se l'importo totale della transazione è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a2989-139">If the correct values are set in steps 2 and 4, determine whether the total amount of the transaction is 0 (zero).</span></span> <span data-ttu-id="a2989-140">Se l'importo totale è 0, un importo fiscale pari a 0 è il risultato atteso.</span><span class="sxs-lookup"><span data-stu-id="a2989-140">If the total amount is 0, a tax amount of 0 is the expected result.</span></span> <span data-ttu-id="a2989-141">Poiché il calcolo delle imposte si basa sull'importo totale del saldo della fattura e tale importo non è riga per riga, l'importo dell'imposta pari a 0 verrà assegnato a ciascuna riga dopo il calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="a2989-141">Because the tax calculation is based on the total amount of the invoice balance, and that amount isn't line by line, the tax amount of 0 will be allocated to each line after the tax calculation.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="a2989-142">Determinare se esiste la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="a2989-142">Determine whether customization exists</span></span>

<span data-ttu-id="a2989-143">Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2989-143">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="a2989-144">Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="a2989-144">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
