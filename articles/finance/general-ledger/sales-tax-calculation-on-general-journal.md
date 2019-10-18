---
title: Calcolo dell'IVA nelle righe giornale di registrazione generale
description: Questo argomento spiega come viene calcolata l'IVA per diversi tipi di conti (fornitore, cliente, contabilità generale e progetto) sulle righe del giornale di registrazione generale.
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 354076dbc14f34b83d1cd24f591874b9af856af1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186304"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="a9422-103">Calcolo dell'IVA nelle righe giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="a9422-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="a9422-104">Questo argomento spiega come viene calcolata l'IVA per diversi tipi di conti (fornitore, cliente, contabilità generale e progetto) sulle righe del giornale di registrazione generale.</span><span class="sxs-lookup"><span data-stu-id="a9422-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="a9422-105">Il processo può essere suddiviso in tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="a9422-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="a9422-106">Determinare la direzione dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="a9422-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="a9422-107">Determinare l'importo dell'IVA da archiviare una tabella IVA temporanea.</span><span class="sxs-lookup"><span data-stu-id="a9422-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="a9422-108">Determinare l'importo dell'IVA e il conto sul giustificativo.</span><span class="sxs-lookup"><span data-stu-id="a9422-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="a9422-109">Determinare la direzione dell'IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-109">Determine the sales tax direction</span></span>

<span data-ttu-id="a9422-110">Il modo in cui viene determinata la direzione dell'IVA dipende dal tipo di conto nel giustificativo.</span><span class="sxs-lookup"><span data-stu-id="a9422-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="a9422-111">La direzione dell'IVA è determinata dalla combinazione di tipo di conto e codice IVA.</span><span class="sxs-lookup"><span data-stu-id="a9422-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="a9422-112">Nelle seguenti sezioni vengono spiegate le opzioni in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="a9422-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="a9422-113">Il tipo di conto è Progetto</span><span class="sxs-lookup"><span data-stu-id="a9422-113">Account type is Project</span></span>

<span data-ttu-id="a9422-114">Se un giustificativo ha riga giornale di registrazione in cui il tipo di conto è **Progetto**, tutte le righe giornale di registrazione del giustificativo applicano la stessa direzione dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="a9422-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="a9422-115">Nella figura seguente è illustrata la regola.</span><span class="sxs-lookup"><span data-stu-id="a9422-115">The following illustration shows the rule.</span></span> <span data-ttu-id="a9422-116">I punti seguenti indicano le possibili direzioni dell'IVA per i conti di progetto.</span><span class="sxs-lookup"><span data-stu-id="a9422-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="a9422-117">•   Se il codice IVA è l'imposta di utilizzo, la direzione dell'IVA è Imposta di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a9422-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="a9422-118">•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.</span><span class="sxs-lookup"><span data-stu-id="a9422-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9422-119">•   Se il codice IVA è l'IVA intracomunitaria, la direzione dell'IVA è IVA a debito.</span><span class="sxs-lookup"><span data-stu-id="a9422-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9422-120">•   Se il codice IVA è il reverse charge, la direzione dell'IVA è IVA a debito.</span><span class="sxs-lookup"><span data-stu-id="a9422-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9422-121">Negli altri casi la direzione dell'IVA è IVA a credito.</span><span class="sxs-lookup"><span data-stu-id="a9422-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="a9422-122">Nel diagramma riportato di seguito viene illustrata graficamente la regola.</span><span class="sxs-lookup"><span data-stu-id="a9422-122">The following diagram illustrates the rule graphically.</span></span>

![Possibilità di direzione dell'IVA per i conti di progetto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="a9422-124">Il tipo di conto è Fornitore</span><span class="sxs-lookup"><span data-stu-id="a9422-124">Account type is Vendor</span></span>

<span data-ttu-id="a9422-125">Se un giustificativo ha riga giornale di registrazione in cui il tipo di conto è **Fornitore**, tutte le righe giornale di registrazione del giustificativo applicano la stessa direzione dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="a9422-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="a9422-126">I punti seguenti indicano le possibili direzioni dell'IVA per i conti di fornitore.</span><span class="sxs-lookup"><span data-stu-id="a9422-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="a9422-127">•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.</span><span class="sxs-lookup"><span data-stu-id="a9422-127">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9422-128">•   Se il codice IVA è l'IVA intracomunitaria, la direzione dell'IVA è IVA a credito.</span><span class="sxs-lookup"><span data-stu-id="a9422-128">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="a9422-129">•   Se il codice IVA è il reverse charge, la direzione dell'IVA è IVA a credito.</span><span class="sxs-lookup"><span data-stu-id="a9422-129">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>


<span data-ttu-id="a9422-130">Negli altri casi la direzione dell'IVA è IVA a debito.</span><span class="sxs-lookup"><span data-stu-id="a9422-130">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9422-131">Nel diagramma riportato di seguito viene illustrata graficamente la regola.</span><span class="sxs-lookup"><span data-stu-id="a9422-131">The following diagram illustrates the rule graphically.</span></span>

![Possibilità di direzione dell'IVA per i conti di fornitore](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="a9422-133">Il tipo di conto è Cliente</span><span class="sxs-lookup"><span data-stu-id="a9422-133">Account type is Customer</span></span>

<span data-ttu-id="a9422-134">Se un giustificativo ha riga giornale di registrazione in cui il tipo di conto è **Cliente**, tutte le righe giornale di registrazione del giustificativo applicano la stessa direzione dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="a9422-134">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="a9422-135">I punti seguenti indicano le possibili direzioni dell'IVA per i conti di cliente.</span><span class="sxs-lookup"><span data-stu-id="a9422-135">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="a9422-136">•   Se il codice IVA è l'imposta di utilizzo, la direzione dell'IVA è Imposta di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a9422-136">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="a9422-137">•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.</span><span class="sxs-lookup"><span data-stu-id="a9422-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9422-138">•   Se il codice IVA è l'IVA intracomunitaria, la direzione dell'IVA è IVA a debito.</span><span class="sxs-lookup"><span data-stu-id="a9422-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9422-139">•   Se il codice IVA è il reverse charge, la direzione dell'IVA è IVA a debito.</span><span class="sxs-lookup"><span data-stu-id="a9422-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9422-140">Negli altri casi la direzione dell'IVA è IVA a credito.</span><span class="sxs-lookup"><span data-stu-id="a9422-140">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="a9422-141">Nel diagramma riportato di seguito viene illustrata graficamente la regola.</span><span class="sxs-lookup"><span data-stu-id="a9422-141">The following diagram illustrates the rule graphically.</span></span>

![Possibilità di direzione dell'IVA per i conti di cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="a9422-143">Il tipo di conto è Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="a9422-143">Account type is Ledger</span></span>

<span data-ttu-id="a9422-144">Nella seguente figura è illustrata la regola che si applica quando in un giustificativo sono presenti solo righe giornale di registrazione in cui il tipo conto è **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="a9422-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="a9422-145">I punti seguenti indicano le possibili direzioni dell'IVA per i conti di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="a9422-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="a9422-146">•   Se il codice IVA è l'imposta di utilizzo, la direzione dell'IVA è Imposta di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a9422-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="a9422-147">•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.</span><span class="sxs-lookup"><span data-stu-id="a9422-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9422-148">Altrimenti, se l'importo giornale di registrazione è un addebito (positivo), la direzione è IVA a credito, se l'importo giornale di registrazione è un credito (negativo), la direzione è IVA a debito.</span><span class="sxs-lookup"><span data-stu-id="a9422-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9422-149">Nel diagramma riportato di seguito viene illustrata graficamente la regola.</span><span class="sxs-lookup"><span data-stu-id="a9422-149">The following diagram illustrates the rule graphically.</span></span>

![Possibilità di direzione dell'IVA per i conti di contabilità generale](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="a9422-151">Sostituire la direzione dell'IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-151">Override the sales tax direction</span></span>

<span data-ttu-id="a9422-152">È possibile sostituire la direzione dell'IVA quando il giustificativo contiene solo le righe in cui il tipo di conto è **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="a9422-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="a9422-153">Passare a **Contabilità generale \> Piano dei conti \> Conti \> Conti principali** e selezionare la scheda dettaglio **Sostituzioni persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="a9422-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="a9422-154">Determinare l'importo dell'IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-154">Determine the sales tax amount</span></span>

<span data-ttu-id="a9422-155">In questa sezione viene descritto come viene calcolato il segno dell'importo dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="a9422-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Pagina delle transazioni IVA](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="a9422-157">Nella tabella seguente viene illustrata la regola generica per determinare il segno degli importi IVA nella tabella IVA temporanea.</span><span class="sxs-lookup"><span data-stu-id="a9422-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="a9422-158">Importo riga giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a9422-158">Journal line amount</span></span> | <span data-ttu-id="a9422-159">Tipo di IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-159">Sales tax direction</span></span>  | <span data-ttu-id="a9422-160">Segno dell'importo IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="a9422-161">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-161">Positive</span></span>            | <span data-ttu-id="a9422-162">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-162">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-163">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-163">Positive</span></span>              |
| <span data-ttu-id="a9422-164">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-164">Positive</span></span>            | <span data-ttu-id="a9422-165">IVA a debito</span><span class="sxs-lookup"><span data-stu-id="a9422-165">Sales Tax Payable</span></span>    | <span data-ttu-id="a9422-166">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-166">Negative</span></span>              |
| <span data-ttu-id="a9422-167">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-167">Negative</span></span>            | <span data-ttu-id="a9422-168">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-168">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-169">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-169">Negative</span></span>              |
| <span data-ttu-id="a9422-170">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-170">Negative</span></span>            | <span data-ttu-id="a9422-171">IVA a debito</span><span class="sxs-lookup"><span data-stu-id="a9422-171">Sales Tax Payable</span></span>    | <span data-ttu-id="a9422-172">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-172">Positive</span></span>              |

<span data-ttu-id="a9422-173">Esiste una regola speciale per i giustificativi con righe solo righe **Contabilità generale** o **Progetto**, quando una fascia IVA o fascia VAT articoli è selezionata nella riga **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="a9422-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="a9422-174">Questa regola è controllata dalla funzionalità di abilitazione del calcolo dell'IVA indipendente per i giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="a9422-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="a9422-175">Quando questa funzionalità è disattivata, l'importo IVA della riga **Contabilità generale** utilizza la direzione Dare/Avere della riga **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a9422-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="a9422-176">Quando la funzionalità è attivata, l'importo IVA della riga **Contabilità generale** utilizza la propria direzione Dare/Avere.</span><span class="sxs-lookup"><span data-stu-id="a9422-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="a9422-177">Nelle tabelle seguente è illustrata la regola per ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="a9422-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="a9422-178">**Regola quando la funzionalità è attivata**</span><span class="sxs-lookup"><span data-stu-id="a9422-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="a9422-179">Importo riga giornale di registrazione del progetto</span><span class="sxs-lookup"><span data-stu-id="a9422-179">Journal line amount of project</span></span> | <span data-ttu-id="a9422-180">Tipo di IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-180">Sales tax direction</span></span>  | <span data-ttu-id="a9422-181">Segno dell'importo IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="a9422-182">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-182">Positive</span></span>                       | <span data-ttu-id="a9422-183">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-183">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-184">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-184">Positive</span></span>              |
| <span data-ttu-id="a9422-185">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-185">Negative</span></span>                       | <span data-ttu-id="a9422-186">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-186">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-187">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-187">Negative</span></span>              |

<span data-ttu-id="a9422-188">**Regola quando la funzionalità è disattivata**</span><span class="sxs-lookup"><span data-stu-id="a9422-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="a9422-189">Importo riga giornale di registrazione della contabilità generale</span><span class="sxs-lookup"><span data-stu-id="a9422-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="a9422-190">Tipo di IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-190">Sales tax direction</span></span>  | <span data-ttu-id="a9422-191">Segno dell'importo IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="a9422-192">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-192">Positive</span></span>                       | <span data-ttu-id="a9422-193">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-193">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-194">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-194">Positive</span></span>              |
| <span data-ttu-id="a9422-195">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-195">Negative</span></span>                       | <span data-ttu-id="a9422-196">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-196">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-197">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="a9422-198">Determinare l'importo dell'IVA e il conto sul giustificativo</span><span class="sxs-lookup"><span data-stu-id="a9422-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="a9422-199">Quando si registra l'IVA, il conto principale viene recuperato dal profilo del gruppo di registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="a9422-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="a9422-200">Quando l'IVA è a credito, il sistema utilizza il conto IVA a credito specificato nel profilo.</span><span class="sxs-lookup"><span data-stu-id="a9422-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="a9422-201">Per l'IVA a debito, il sistema utilizza il conto IVA a debito specificato nel profilo.</span><span class="sxs-lookup"><span data-stu-id="a9422-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="a9422-202">Nella seguente tabella viene illustrata la regola generale.</span><span class="sxs-lookup"><span data-stu-id="a9422-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="a9422-203">Tipo di IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-203">Sales tax direction</span></span>  | <span data-ttu-id="a9422-204">Segno dell'importo IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-204">Sales tax amount sign</span></span> | <span data-ttu-id="a9422-205">Conto IVA</span><span class="sxs-lookup"><span data-stu-id="a9422-205">Sales tax account</span></span>      | <span data-ttu-id="a9422-206">Importo su giustificativo</span><span class="sxs-lookup"><span data-stu-id="a9422-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="a9422-207">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-207">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-208">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-208">Positive</span></span>              | <span data-ttu-id="a9422-209">Conto IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-209">Tax Receivable Account</span></span> | <span data-ttu-id="a9422-210">Positivo (Dare)</span><span class="sxs-lookup"><span data-stu-id="a9422-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="a9422-211">IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-211">Sales Tax Receivable</span></span> | <span data-ttu-id="a9422-212">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-212">Negative</span></span>              | <span data-ttu-id="a9422-213">Conto IVA a credito</span><span class="sxs-lookup"><span data-stu-id="a9422-213">Tax Receivable Account</span></span> | <span data-ttu-id="a9422-214">Negativo (Avere)</span><span class="sxs-lookup"><span data-stu-id="a9422-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="a9422-215">IVA a debito</span><span class="sxs-lookup"><span data-stu-id="a9422-215">Sales Tax Payable</span></span>    | <span data-ttu-id="a9422-216">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9422-216">Positive</span></span>              | <span data-ttu-id="a9422-217">Conto IVA a debito</span><span class="sxs-lookup"><span data-stu-id="a9422-217">Tax Payable Account</span></span>    | <span data-ttu-id="a9422-218">Negativo (Avere)</span><span class="sxs-lookup"><span data-stu-id="a9422-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="a9422-219">IVA a debito</span><span class="sxs-lookup"><span data-stu-id="a9422-219">Sales Tax Payable</span></span>    | <span data-ttu-id="a9422-220">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9422-220">Negative</span></span>              | <span data-ttu-id="a9422-221">Conto IVA a debito</span><span class="sxs-lookup"><span data-stu-id="a9422-221">Tax Payable Account</span></span>    | <span data-ttu-id="a9422-222">Positivo (Dare)</span><span class="sxs-lookup"><span data-stu-id="a9422-222">Positive (Debit)</span></span>  |
