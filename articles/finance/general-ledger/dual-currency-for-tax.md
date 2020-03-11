---
title: Supporto a doppia valuta per le imposte
description: Questo argomento spiega come estendere la funzionalità di contabilità a doppia valuta nel dominio fiscale e l'impatto sul calcolo e sulla registrazione delle imposte
author: EricWang
manager: Ann Beebe
ms.date: 12/16/2019
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
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c9318f518135bf7aa545cdb5ddd2e68c54a6d211
ms.sourcegitcommit: bcc8cba8905ed51797d36e1712d7360452cfc5c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "3090566"
---
# <a name="dual-currency-support-for-sales-tax"></a><span data-ttu-id="0e019-103">Supporto a doppia valuta per l'IVA</span><span class="sxs-lookup"><span data-stu-id="0e019-103">Dual currency support for sales tax</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="0e019-104">Questo argomento spiega come estendere la contabilità a doppia valuta per l'IVA e l'impatto sul calcolo, sulla registrazione e sulla liquidazione dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="0e019-104">This topic explains how to extend dual currency accounting for sales taxes and the impact for sales tax calculations, posting and settlements.</span></span>

<span data-ttu-id="0e019-105">La funzione di doppia valuta per Dynamics 365 Finance è stata introdotta nella versione 8.1 (ottobre 2018).</span><span class="sxs-lookup"><span data-stu-id="0e019-105">The Dual currency feature for Dynamics 365 Finance was introduced in version 8.1 (October 2018).</span></span> <span data-ttu-id="0e019-106">Cambia il modo in cui vengono calcolate le voci contabili nella valuta di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0e019-106">It changes the way that accounting entries in the reporting currency are calculated.</span></span>

<span data-ttu-id="0e019-107">Nelle versioni precedenti, le transazioni venivano convertite nella valuta di dichiarazione nella seguente sequenza:</span><span class="sxs-lookup"><span data-stu-id="0e019-107">In earlier versions, transactions were converted to the reporting currency in the following sequence:</span></span> 

<span data-ttu-id="0e019-108">Il totale della transazione è stato calcolato nella valuta della transazione > L'importo della transazione è stato convertito nella valuta contabile > L'importo della valuta contabile è stato convertito nella valuta di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-108">Transaction total was calculated in the transaction currency > Transaction amount was converted to the accounting currency > Accounting currency amount was converted to the Reporting currency</span></span>

<span data-ttu-id="0e019-109">Dopo aver abilitato la funzione di doppia valuta, le transazioni sono state convertite nella valuta di dichiarazione nella seguente sequenza:</span><span class="sxs-lookup"><span data-stu-id="0e019-109">After enabling the dual currency feature, transactions were converted to the reporting currency in the following sequence:</span></span>

- <span data-ttu-id="0e019-110">Importo valuta transazione > Importo valuta dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-110">Transaction currency amount > Reporting currency amount</span></span>

<span data-ttu-id="0e019-111">Per ulteriori informazioni sulla doppia valuta, fare riferimento a [Doppia valuta](dual-currency.md).</span><span class="sxs-lookup"><span data-stu-id="0e019-111">For more information about dual currency, please refer to [Dual currency](dual-currency.md).</span></span>

<span data-ttu-id="0e019-112">Come conseguenza del supporto per la doppia valuta, sono disponibili due nuove funzionalità nella gestione delle funzionalità:</span><span class="sxs-lookup"><span data-stu-id="0e019-112">As a consequence of support for dual currencies, two new features are available in feature management:</span></span> 

- <span data-ttu-id="0e019-113">Conversione IVA (rilascio nella versione 10.0.9)</span><span class="sxs-lookup"><span data-stu-id="0e019-113">Sales tax conversion (Release in version 10.0.9)</span></span>
- <span data-ttu-id="0e019-114">Saldo automatico della liquidazione imposte nella valuta di dichiarazione (rilascio nella versione 10.0.11)</span><span class="sxs-lookup"><span data-stu-id="0e019-114">Tax settlement auto balance in reporting currency (Release in version 10.0.11)</span></span>

<span data-ttu-id="0e019-115">Il supporto per doppia valuta per l'IVA garantisce che le imposte vengano calcolate accuratamente nella valuta fiscale e che il saldo della liquidazione IVA sia calcolato con precisione sia nella valuta contabile che nella valuta di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0e019-115">Dual currency support for sales taxes ensures that taxes are calculated accurately in the tax currency, and that the sales tax settlement balance is calculated accurately in both the accounting currency and reporting currency.</span></span> 

<span data-ttu-id="0e019-116">Le nuove funzionalità sono attualmente abilitate per i clienti dell'anteprima privata.</span><span class="sxs-lookup"><span data-stu-id="0e019-116">The new features are currently enabled for private preview customers.</span></span> <span data-ttu-id="0e019-117">Per abilitare le funzionalità, inoltrare a Microsoft una richiesta di assistenza tramite i canali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="0e019-117">To enable the features, raise a service request through corresponding channels to Microsoft.</span></span>

## <a name="sales-tax-conversion"></a><span data-ttu-id="0e019-118">Conversione IVA</span><span class="sxs-lookup"><span data-stu-id="0e019-118">Sales tax conversion</span></span>

<span data-ttu-id="0e019-119">Il parametro **Conversione IVA** fornisce due opzioni per convertire l'importo fiscale dalla valuta di transazione alla valuta imposte.</span><span class="sxs-lookup"><span data-stu-id="0e019-119">The **Sales tax conversion** parameter provides two options to convert tax amount from transaction currency to tax currency.</span></span> 

- <span data-ttu-id="0e019-120">Valuta di contabilizzazione: il percorso sarà "Importo in valuta di transazione > Importo in valuta di contabilizzazione > Importo in valuta imposte".</span><span class="sxs-lookup"><span data-stu-id="0e019-120">Accounting currency: The path will be "Amount in transaction currency > Amount in accounting currency > Amount in tax currency".</span></span> <span data-ttu-id="0e019-121">Per la conversione della valuta verrà utilizzato il tipo di tasso di cambio della valuta contabile (configurato in Impostazione contabilità generale).</span><span class="sxs-lookup"><span data-stu-id="0e019-121">The accounting currency exhange rate type (configured in Ledger setup) will be used for the currency conversion.</span></span>
- <span data-ttu-id="0e019-122">Valuta dichiarazione: il percorso sarà "Importo in valuta di transazione > Importo in valuta di dichiarazione > Importo in valuta imposte".</span><span class="sxs-lookup"><span data-stu-id="0e019-122">Reporting currency: The path will be "Amount in transaction currency > Amount in reporting currency > Amount in tax currency".</span></span> <span data-ttu-id="0e019-123">Per la conversione della valuta verrà utilizzato il tipo di tasso di cambio della valuta dichiarazione (configurato in Impostazione contabilità generale).</span><span class="sxs-lookup"><span data-stu-id="0e019-123">The reporting currency exhange rate type (configured in Ledger setup) will be used for the currency conversion.</span></span>

### <a name="example"></a><span data-ttu-id="0e019-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e019-124">Example</span></span>

<span data-ttu-id="0e019-125">Un semplice esempio per dimostrare questa funzionalità è:</span><span class="sxs-lookup"><span data-stu-id="0e019-125">A simple example to demonstrate this functionality is:</span></span>

<span data-ttu-id="0e019-126">Impostazione valuta per contabilità generale e imposte</span><span class="sxs-lookup"><span data-stu-id="0e019-126">Currency setup for ledger and tax</span></span>

| <span data-ttu-id="0e019-127">Valuta transazione</span><span class="sxs-lookup"><span data-stu-id="0e019-127">Transaction currency</span></span> | <span data-ttu-id="0e019-128">Valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="0e019-128">Accounting currency</span></span> | <span data-ttu-id="0e019-129">Valuta dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-129">Reporting currency</span></span> | <span data-ttu-id="0e019-130">Valuta imposte</span><span class="sxs-lookup"><span data-stu-id="0e019-130">Tax currency</span></span> |
| -------------------- | ------------------- | ------------------ | ------------ |
| <span data-ttu-id="0e019-131">EUR</span><span class="sxs-lookup"><span data-stu-id="0e019-131">EUR</span></span>                  | <span data-ttu-id="0e019-132">GBP</span><span class="sxs-lookup"><span data-stu-id="0e019-132">USD</span></span>                 | <span data-ttu-id="0e019-133">GBP</span><span class="sxs-lookup"><span data-stu-id="0e019-133">GBP</span></span>                | <span data-ttu-id="0e019-134">GBP</span><span class="sxs-lookup"><span data-stu-id="0e019-134">GBP</span></span>          |

<span data-ttu-id="0e019-135">Tasso di cambio</span><span class="sxs-lookup"><span data-stu-id="0e019-135">Exchange rate</span></span>

| <span data-ttu-id="0e019-136">Dalla valuta</span><span class="sxs-lookup"><span data-stu-id="0e019-136">From currency</span></span> | <span data-ttu-id="0e019-137">Alla valuta</span><span class="sxs-lookup"><span data-stu-id="0e019-137">To currency</span></span> | <span data-ttu-id="0e019-138">Fattore</span><span class="sxs-lookup"><span data-stu-id="0e019-138">Factor</span></span> | <span data-ttu-id="0e019-139">Tasso di cambio</span><span class="sxs-lookup"><span data-stu-id="0e019-139">Exchange rate</span></span> |
| ------------- | ----------- | ------ | ------------- |
| <span data-ttu-id="0e019-140">EUR</span><span class="sxs-lookup"><span data-stu-id="0e019-140">EUR</span></span>           | <span data-ttu-id="0e019-141">GBP</span><span class="sxs-lookup"><span data-stu-id="0e019-141">USD</span></span>         | <span data-ttu-id="0e019-142">1</span><span class="sxs-lookup"><span data-stu-id="0e019-142">1</span></span>      | <span data-ttu-id="0e019-143">1.11</span><span class="sxs-lookup"><span data-stu-id="0e019-143">1.11</span></span>          |
| <span data-ttu-id="0e019-144">EUR</span><span class="sxs-lookup"><span data-stu-id="0e019-144">EUR</span></span>           | <span data-ttu-id="0e019-145">GBP</span><span class="sxs-lookup"><span data-stu-id="0e019-145">GBP</span></span>         | <span data-ttu-id="0e019-146">1</span><span class="sxs-lookup"><span data-stu-id="0e019-146">1</span></span>      | <span data-ttu-id="0e019-147">0.83</span><span class="sxs-lookup"><span data-stu-id="0e019-147">0.83</span></span>          |
| <span data-ttu-id="0e019-148">GBP</span><span class="sxs-lookup"><span data-stu-id="0e019-148">USD</span></span>           | <span data-ttu-id="0e019-149">GBP</span><span class="sxs-lookup"><span data-stu-id="0e019-149">GBP</span></span>         | <span data-ttu-id="0e019-150">1</span><span class="sxs-lookup"><span data-stu-id="0e019-150">1</span></span>      | <span data-ttu-id="0e019-151">0.75</span><span class="sxs-lookup"><span data-stu-id="0e019-151">0.75</span></span>          |

<span data-ttu-id="0e019-152">Calcolo dell'importo imposte in diverse opzioni di parametro</span><span class="sxs-lookup"><span data-stu-id="0e019-152">Tax amount calculation in different parameter options</span></span>

<span data-ttu-id="0e019-153">Importo imposte = 100 EUR</span><span class="sxs-lookup"><span data-stu-id="0e019-153">Tax amount = 100 EUR</span></span>

| <span data-ttu-id="0e019-154">Parametri di conversione IVA</span><span class="sxs-lookup"><span data-stu-id="0e019-154">Sales tax conversion parameters</span></span> | <span data-ttu-id="0e019-155">Valuta transazione (EUR)</span><span class="sxs-lookup"><span data-stu-id="0e019-155">Transaction currency (EUR)</span></span> | <span data-ttu-id="0e019-156">Valuta contabile (USD)</span><span class="sxs-lookup"><span data-stu-id="0e019-156">Accounting currency (USD)</span></span> | <span data-ttu-id="0e019-157">Valuta di dichiarazione (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-157">Reporting currency (GBP)</span></span> | <span data-ttu-id="0e019-158">Valuta imposte (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-158">Tax currency (GBP)</span></span> |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| <span data-ttu-id="0e019-159">Valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="0e019-159">Accounting currency</span></span>             | <span data-ttu-id="0e019-160">100</span><span class="sxs-lookup"><span data-stu-id="0e019-160">100</span></span>                        | <span data-ttu-id="0e019-161">111</span><span class="sxs-lookup"><span data-stu-id="0e019-161">111</span></span>                       | <span data-ttu-id="0e019-162">83</span><span class="sxs-lookup"><span data-stu-id="0e019-162">83</span></span>                       | <span data-ttu-id="0e019-163">**83.25**</span><span class="sxs-lookup"><span data-stu-id="0e019-163">**83.25**</span></span>          |
| <span data-ttu-id="0e019-164">Valuta dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-164">Reporting currency</span></span>              | <span data-ttu-id="0e019-165">100</span><span class="sxs-lookup"><span data-stu-id="0e019-165">100</span></span>                        | <span data-ttu-id="0e019-166">111</span><span class="sxs-lookup"><span data-stu-id="0e019-166">111</span></span>                       | <span data-ttu-id="0e019-167">83</span><span class="sxs-lookup"><span data-stu-id="0e019-167">83</span></span>                       | <span data-ttu-id="0e019-168">**83**</span><span class="sxs-lookup"><span data-stu-id="0e019-168">**83**</span></span>             |

<span data-ttu-id="0e019-169">Questo parametro può essere configurato in base alle esigenze di conformità dell'autorità fiscale.</span><span class="sxs-lookup"><span data-stu-id="0e019-169">This parameter can be configured based on the compliance need from tax authority.</span></span>


### <a name="upgrade-consideration"></a><span data-ttu-id="0e019-170">Considerazione sull'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0e019-170">Upgrade Consideration</span></span>

<span data-ttu-id="0e019-171">Questa funzione si applica solo alle nuove transazioni.</span><span class="sxs-lookup"><span data-stu-id="0e019-171">This feature will only apply for new transactions.</span></span> <span data-ttu-id="0e019-172">Per le transazioni imposte già salvate nella tabella TAXTRANS ma non ancora regolate, il sistema non ricalcolerà l'importo delle imposte in valuta fiscale perché il tasso di cambio al momento della registrazione delle imposte è già mancante.</span><span class="sxs-lookup"><span data-stu-id="0e019-172">For tax transaction already saved in TAXTRANS table but not settled yet, system will not recalculate tax amount in tax currency because the exchange rate at time point of posting tax is already missing.</span></span>

<span data-ttu-id="0e019-173">Per evitare lo scenario precedente, si consiglia di modificare questo valore di parametro in un nuovo periodo di liquidazione delle imposte (pulito) che non contenga alcuna transazione fiscale non liquidata.</span><span class="sxs-lookup"><span data-stu-id="0e019-173">To prevent preceding scenario, we recommend changing this parameter value in a new (clean) tax settlement period that doesn't contain any unsettled tax transactions.</span></span> <span data-ttu-id="0e019-174">Per modificare questo valore nel mezzo di un periodo di dichiarazione fiscale, eseguire il programma "Liquida e registra IVA" per il periodo di liquidazione imposte corrente prima di modificare questo valore di parametro.</span><span class="sxs-lookup"><span data-stu-id="0e019-174">To change this value in the middle of a tax settlement period, please run "Settle and post sales tax" program for current tax settlement period before changing this parameter value.</span></span>


## <a name="track-reporting-currency-tax-amount"></a><span data-ttu-id="0e019-175">Tracciare l'importo delle imposte in valuta di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-175">Track reporting currency tax amount</span></span>

<span data-ttu-id="0e019-176">Tre nuovi campi sono stati aggiunti alle tabelle relative alle imposte per tenere traccia degli importi nella valuta di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0e019-176">Three new fields were added to tax-related tables to track amounts in the reporting currency.</span></span> <span data-ttu-id="0e019-177">Questi campi si trovano nelle tabelle TAXUNCOMMITTED e TAXTRANS:</span><span class="sxs-lookup"><span data-stu-id="0e019-177">These fields are within the TAXUNCOMMITTED and TAXTRANS tables:</span></span>

- <span data-ttu-id="0e019-178">TaxAmountRep: importo imposte in valuta di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-178">TaxAmountRep: tax amount in reporting currency</span></span>
- <span data-ttu-id="0e019-179">TaxBaseAmountRep: importo base in valuta di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-179">TaxBaseAmountRep: base amount in reporting currency</span></span>
- <span data-ttu-id="0e019-180">TaxInCostPriceRep: importo non deducibile in valuta di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-180">TaxInCostPriceRep: non-deductible amount in reporting currency</span></span>

<span data-ttu-id="0e019-181">Per le imposte salvate solo nella tabella TAXUNCOMMITTED ma non ancora registrate, il sistema ricalcolerà l'importo delle imposte nella valuta di dichiarazione al momento della registrazione e salverà nella tabella TAXTRANS.</span><span class="sxs-lookup"><span data-stu-id="0e019-181">For tax only saved in TAXUNCOMMITTED table but not posted yet, system will recalculate tax amount in reporting currency at the time of posting and save in TAXTRANS table.</span></span>

<span data-ttu-id="0e019-182">Questa versione non includerà le modifiche ai report e ai moduli che mostrano l'importo delle imposte nella valuta di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0e019-182">This release will not include changes to reports and forms that show the tax amount in the reporting currency.</span></span> <span data-ttu-id="0e019-183">Le modifiche a report e moduli verranno offerte nella versione futura.</span><span class="sxs-lookup"><span data-stu-id="0e019-183">Changes to reports and forms will be delivered in the future release.</span></span>



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a><span data-ttu-id="0e019-184">Saldo automatico della liquidazione imposte nella valuta di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-184">Tax settlement auto-balance in reporting currency</span></span>

<span data-ttu-id="0e019-185">Se la liquidazione imposte non è inclusa nel saldo nella valuta di dichiarazione per determinati motivi, ad esempio il percorso di conversione dell'IVA è "Valuta contabile" o la variazione del tasso di cambio in un singolo periodo di liquidazione imposte, il sistema genererà automaticamente voci contabili per adeguare lo scostamento dell'importo dell'imposta e compensarlo con il conto profitti/perdite di cambio realizzato, che è impostato nella configurazione della contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="0e019-185">If the tax settlement is not balanced in the reporting currency for certain reason such as the sales tax conversion path is "Accounting currency", or the exchange rate change in a single tax settlement period, thebn the system will automatically generate accounting entries to adjust the tax amount variance and offset it against realized exchange gain/loss account, which is configured in Ledger setup.</span></span>

<span data-ttu-id="0e019-186">Utilizzando l'esempio precedente per dimostrare questa funzionalità, si supponga che i dati nella tabella TAXTRANS al momento della registrazione siano i seguenti.</span><span class="sxs-lookup"><span data-stu-id="0e019-186">Using the the previous example to demonstrate this feature, suppose that the data in TAXTRANS table at the time of posting is as follows.</span></span>

| <span data-ttu-id="0e019-187">Parametri di conversione IVA</span><span class="sxs-lookup"><span data-stu-id="0e019-187">Sales tax conversion parameters</span></span> | <span data-ttu-id="0e019-188">Valuta transazione (EUR)</span><span class="sxs-lookup"><span data-stu-id="0e019-188">Transaction currency (EUR)</span></span> | <span data-ttu-id="0e019-189">Valuta contabile (USD)</span><span class="sxs-lookup"><span data-stu-id="0e019-189">Accounting currency (USD)</span></span> | <span data-ttu-id="0e019-190">Valuta di dichiarazione (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-190">Reporting currency (GBP)</span></span> | <span data-ttu-id="0e019-191">Valuta imposte (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-191">Tax currency (GBP)</span></span> |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| <span data-ttu-id="0e019-192">Valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="0e019-192">Accounting currency</span></span>             | <span data-ttu-id="0e019-193">100</span><span class="sxs-lookup"><span data-stu-id="0e019-193">100</span></span>                        | <span data-ttu-id="0e019-194">111</span><span class="sxs-lookup"><span data-stu-id="0e019-194">111</span></span>                       | <span data-ttu-id="0e019-195">83</span><span class="sxs-lookup"><span data-stu-id="0e019-195">83</span></span>                       | <span data-ttu-id="0e019-196">**83.25**</span><span class="sxs-lookup"><span data-stu-id="0e019-196">**83.25**</span></span>          |
| <span data-ttu-id="0e019-197">Valuta dichiarazione</span><span class="sxs-lookup"><span data-stu-id="0e019-197">Reporting currency</span></span>              | <span data-ttu-id="0e019-198">100</span><span class="sxs-lookup"><span data-stu-id="0e019-198">100</span></span>                        | <span data-ttu-id="0e019-199">111</span><span class="sxs-lookup"><span data-stu-id="0e019-199">111</span></span>                       | <span data-ttu-id="0e019-200">83</span><span class="sxs-lookup"><span data-stu-id="0e019-200">83</span></span>                       | <span data-ttu-id="0e019-201">**83**</span><span class="sxs-lookup"><span data-stu-id="0e019-201">**83**</span></span>             |

<span data-ttu-id="0e019-202">Quando si esegue il programma di liquidazione dell'IVA alla fine del mese, la voce contabile sarà la seguente:</span><span class="sxs-lookup"><span data-stu-id="0e019-202">When you run the sales tax settlement program at month-end, the accounting entry will be as follows:.</span></span>
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a><span data-ttu-id="0e019-203">Scenario: conversione IVA = "valuta di contabilizzazione"</span><span class="sxs-lookup"><span data-stu-id="0e019-203">Scenario: sales tax conversion = "Accounting currency"</span></span>

| <span data-ttu-id="0e019-204">Conto principale</span><span class="sxs-lookup"><span data-stu-id="0e019-204">Main account</span></span>           | <span data-ttu-id="0e019-205">Valuta transazione (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-205">Transaction currency (GBP)</span></span> | <span data-ttu-id="0e019-206">Valuta contabile (USD)</span><span class="sxs-lookup"><span data-stu-id="0e019-206">Accounting currency (USD)</span></span> | <span data-ttu-id="0e019-207">Valuta di dichiarazione (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-207">Reporting currency (GBP)</span></span> |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| <span data-ttu-id="0e019-208">Imposta a debito/credito</span><span class="sxs-lookup"><span data-stu-id="0e019-208">Tax Payable/Receivable</span></span> | <span data-ttu-id="0e019-209">-83,25</span><span class="sxs-lookup"><span data-stu-id="0e019-209">-83.25</span></span>                     | <span data-ttu-id="0e019-210">-111</span><span class="sxs-lookup"><span data-stu-id="0e019-210">-111</span></span>                      | <span data-ttu-id="0e019-211">-83,25</span><span class="sxs-lookup"><span data-stu-id="0e019-211">-83.25</span></span>                   |
| <span data-ttu-id="0e019-212">Liquidazione imposte</span><span class="sxs-lookup"><span data-stu-id="0e019-212">Tax Settlement</span></span>         | <span data-ttu-id="0e019-213">83.25</span><span class="sxs-lookup"><span data-stu-id="0e019-213">83.25</span></span>                      | <span data-ttu-id="0e019-214">111</span><span class="sxs-lookup"><span data-stu-id="0e019-214">111</span></span>                       | <span data-ttu-id="0e019-215">83.25</span><span class="sxs-lookup"><span data-stu-id="0e019-215">83.25</span></span>                    |
| <span data-ttu-id="0e019-216">Perdita/profitto realizzato</span><span class="sxs-lookup"><span data-stu-id="0e019-216">Realized Gain/Loss</span></span>     | <span data-ttu-id="0e019-217">0</span><span class="sxs-lookup"><span data-stu-id="0e019-217">0</span></span>                          | <span data-ttu-id="0e019-218">0</span><span class="sxs-lookup"><span data-stu-id="0e019-218">0</span></span>                         | <span data-ttu-id="0e019-219">-0,25</span><span class="sxs-lookup"><span data-stu-id="0e019-219">-0.25</span></span>                    |
| <span data-ttu-id="0e019-220">Imposta a debito/credito</span><span class="sxs-lookup"><span data-stu-id="0e019-220">Tax Payable/Receivable</span></span> | <span data-ttu-id="0e019-221">0</span><span class="sxs-lookup"><span data-stu-id="0e019-221">0</span></span>                          | <span data-ttu-id="0e019-222">0</span><span class="sxs-lookup"><span data-stu-id="0e019-222">0</span></span>                         | <span data-ttu-id="0e019-223">0.25</span><span class="sxs-lookup"><span data-stu-id="0e019-223">0.25</span></span>                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a><span data-ttu-id="0e019-224">Scenario: conversione IVA = "valuta di dichiarazione"</span><span class="sxs-lookup"><span data-stu-id="0e019-224">Scenario: sales tax conversion = "Reporting currency"</span></span>


| <span data-ttu-id="0e019-225">Conto principale</span><span class="sxs-lookup"><span data-stu-id="0e019-225">Main account</span></span>           | <span data-ttu-id="0e019-226">Valuta transazione (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-226">Transaction currency (GBP)</span></span> | <span data-ttu-id="0e019-227">Valuta contabile (USD)</span><span class="sxs-lookup"><span data-stu-id="0e019-227">Accounting currency (USD)</span></span> | <span data-ttu-id="0e019-228">Valuta di dichiarazione (GBP)</span><span class="sxs-lookup"><span data-stu-id="0e019-228">Reporting currency (GBP)</span></span> |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| <span data-ttu-id="0e019-229">Imposta a debito/credito</span><span class="sxs-lookup"><span data-stu-id="0e019-229">Tax Payable/Receivable</span></span> | <span data-ttu-id="0e019-230">-83</span><span class="sxs-lookup"><span data-stu-id="0e019-230">-83</span></span>                        | <span data-ttu-id="0e019-231">-110,67</span><span class="sxs-lookup"><span data-stu-id="0e019-231">-110.67</span></span>                   | <span data-ttu-id="0e019-232">-83</span><span class="sxs-lookup"><span data-stu-id="0e019-232">-83</span></span>                      |
| <span data-ttu-id="0e019-233">Liquidazione imposte</span><span class="sxs-lookup"><span data-stu-id="0e019-233">Tax Settlement</span></span>         | <span data-ttu-id="0e019-234">83</span><span class="sxs-lookup"><span data-stu-id="0e019-234">83</span></span>                         | <span data-ttu-id="0e019-235">110.67</span><span class="sxs-lookup"><span data-stu-id="0e019-235">110.67</span></span>                    | <span data-ttu-id="0e019-236">83</span><span class="sxs-lookup"><span data-stu-id="0e019-236">83</span></span>                       |
| <span data-ttu-id="0e019-237">Perdita/profitto realizzato</span><span class="sxs-lookup"><span data-stu-id="0e019-237">Realized Gain/Loss</span></span>     | <span data-ttu-id="0e019-238">0</span><span class="sxs-lookup"><span data-stu-id="0e019-238">0</span></span>                          | <span data-ttu-id="0e019-239">0.33</span><span class="sxs-lookup"><span data-stu-id="0e019-239">0.33</span></span>                      | <span data-ttu-id="0e019-240">0</span><span class="sxs-lookup"><span data-stu-id="0e019-240">0</span></span>                        |
| <span data-ttu-id="0e019-241">Imposta a debito/credito</span><span class="sxs-lookup"><span data-stu-id="0e019-241">Tax Payable/Receivable</span></span> | <span data-ttu-id="0e019-242">0</span><span class="sxs-lookup"><span data-stu-id="0e019-242">0</span></span>                          | <span data-ttu-id="0e019-243">-0,33</span><span class="sxs-lookup"><span data-stu-id="0e019-243">-0.33</span></span>                     | <span data-ttu-id="0e019-244">0</span><span class="sxs-lookup"><span data-stu-id="0e019-244">0</span></span>                        |



<span data-ttu-id="0e019-245">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e019-245">For more information, see the following topics:</span></span>

- [<span data-ttu-id="0e019-246">Doppia valuta</span><span class="sxs-lookup"><span data-stu-id="0e019-246">Dual currency</span></span>](dual-currency.md)
- [<span data-ttu-id="0e019-247">Panoramica dell'IVA</span><span class="sxs-lookup"><span data-stu-id="0e019-247">Sales tax overview</span></span>](indirect-taxes-overview.md)
