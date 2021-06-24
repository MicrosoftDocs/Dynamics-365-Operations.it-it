---
title: Profili di registrazione cliente
description: I profili di registrazione cliente controllano la registrazione delle transazioni cliente nella contabilità generale.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 07acb7ef5565fa4a63607f6828e46c1fcf8110cc
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193620"
---
# <a name="customer-posting-profiles"></a><span data-ttu-id="9f177-103">Profili di registrazione cliente</span><span class="sxs-lookup"><span data-stu-id="9f177-103">Customer posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f177-104">I profili di registrazione cliente controllano la registrazione delle transazioni cliente nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="9f177-104">Customer posting profiles control the posting of customer transactions to the general ledger.</span></span>

## <a name="customer-posting-profiles"></a><span data-ttu-id="9f177-105">Profili di registrazione cliente</span><span class="sxs-lookup"><span data-stu-id="9f177-105">Customer posting profiles</span></span>

<span data-ttu-id="9f177-106">I profili registrazione del cliente consentono di assegnare i conti CoGe e le impostazioni del documento a tutti i clienti, a un gruppo di clienti o a un singolo cliente.</span><span class="sxs-lookup"><span data-stu-id="9f177-106">Customer posting profiles enable you to assign general ledger accounts and document settings to all customers, a group of customers or a single customer.</span></span> <span data-ttu-id="9f177-107">Queste impostazioni verranno utilizzate quando si creano ordini cliente, fatture a testo libero, pagamenti in contanti, lettere di sollecito e note d'interesse.</span><span class="sxs-lookup"><span data-stu-id="9f177-107">These settings will be used when you create sales orders, free text invoices, cash payments, collection letters, and interest notes.</span></span> <span data-ttu-id="9f177-108">Per alcune transazioni, è possibile selezionare un profilo registrazione diverso a cui verrà accordata precedenza sui profili registrazione impostati per le transazioni in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="9f177-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> 

<span data-ttu-id="9f177-109">Il profilo di registrazione predefinito viene definito nella scheda dettaglio Contabilità generale e IVA nella pagina dei parametri Contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="9f177-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts receivable parameters page.</span></span> <span data-ttu-id="9f177-110">Il profilo di registrazione predefinito verrà incluso automaticamente nell'intestazione di nuovi documenti in cui è possibile modificarlo in un profilo registrazione diverso se necessario.</span><span class="sxs-lookup"><span data-stu-id="9f177-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="9f177-111">È inoltre possibile associare le definizioni di registrazione ai tipi di registrazione transazioni nella pagina Definizioni di registrazione transazioni.</span><span class="sxs-lookup"><span data-stu-id="9f177-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="9f177-112">Le definizioni di registrazione controllano la registrazione delle transazioni cliente nella contabilità generale invece dei profili registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-112">Posting definitions control the posting of customer transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="9f177-113">Creazione di un profilo registrazione</span><span class="sxs-lookup"><span data-stu-id="9f177-113">Creating a posting profile</span></span>
<span data-ttu-id="9f177-114">Specificare i conti CoGe utilizzati nella registrazione delle transazioni che utilizzano il profilo registrazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="9f177-114">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="9f177-115">Selezionare un codice conto e, quando possibile, un numero di conto o di gruppo per il profilo registrazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="9f177-115">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="9f177-116">Durante il processo di registrazione, il profilo registrazione più appropriato per ciascuna transazione si trova cercando il codice conto, il numero di conto o la combinazione gruppo e numero più specifica in base alla seguente priorità:</span><span class="sxs-lookup"><span data-stu-id="9f177-116">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="9f177-117">**Codice conto** - valore del campo</span><span class="sxs-lookup"><span data-stu-id="9f177-117">**Account code** field value</span></span> | <span data-ttu-id="9f177-118">**Numero conto/gruppo** - valore del campo</span><span class="sxs-lookup"><span data-stu-id="9f177-118">**Account/Group number** field value</span></span>            | <span data-ttu-id="9f177-119">Priorità ricerca</span><span class="sxs-lookup"><span data-stu-id="9f177-119">Search priority</span></span> |
|------------------------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="9f177-120">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="9f177-120">**Table**</span></span>                    | <span data-ttu-id="9f177-121">Conto cliente specifico</span><span class="sxs-lookup"><span data-stu-id="9f177-121">Specific customer account</span></span>                       | <span data-ttu-id="9f177-122">1</span><span class="sxs-lookup"><span data-stu-id="9f177-122">1</span></span>               |
| <span data-ttu-id="9f177-123">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="9f177-123">**Group**</span></span>                    | <span data-ttu-id="9f177-124">Gruppo di clienti assegnato al cliente</span><span class="sxs-lookup"><span data-stu-id="9f177-124">Customer group that is assigned to the customer</span></span> | <span data-ttu-id="9f177-125">2</span><span class="sxs-lookup"><span data-stu-id="9f177-125">2</span></span>               |
| <span data-ttu-id="9f177-126">**Tutti**</span><span class="sxs-lookup"><span data-stu-id="9f177-126">**All**</span></span>                      | <span data-ttu-id="9f177-127">Vuoto</span><span class="sxs-lookup"><span data-stu-id="9f177-127">Blank</span></span>                                           | <span data-ttu-id="9f177-128">3</span><span class="sxs-lookup"><span data-stu-id="9f177-128">3</span></span>               |

<span data-ttu-id="9f177-129">Se si desidera assegnare lo stesso profilo registrazione a tutte le transazioni cliente, impostare un solo profilo registrazione con il valore Tutti nel campo Codice conto.</span><span class="sxs-lookup"><span data-stu-id="9f177-129">If you want all customer transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="9f177-130">Specificare i valori seguenti per impostare il profilo registrazione:</span><span class="sxs-lookup"><span data-stu-id="9f177-130">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9f177-131">Campo</span><span class="sxs-lookup"><span data-stu-id="9f177-131">Field</span></span></th>
<th><span data-ttu-id="9f177-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f177-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9f177-133"><strong>Profilo registrazione</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-133"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="9f177-134">Immettere un codice per il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-134">Enter a code for the posting profile.</span></span> <span data-ttu-id="9f177-135">Ad esempio, è possibile creare due profili registrazione per ottenere un conto per i saldi cliente in valuta nazionale e un altro conto per i saldi cliente in valuta estera.</span><span class="sxs-lookup"><span data-stu-id="9f177-135">For example, you could create two posting profiles to obtain one account for customer balances in the national currency and another for customer balances in a foreign currency.</span></span> <span data-ttu-id="9f177-136">È possibile chiamare un conto Nazionale e l'altro Estero.</span><span class="sxs-lookup"><span data-stu-id="9f177-136">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f177-137"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-137"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="9f177-138">Immettere una descrizione del profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-138">Enter a description of the posting profile.</span></span> <span data-ttu-id="9f177-139">Viene utilizzato solo per identificare meglio il profilo registrazione quando viene visualizzato in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="9f177-139">This is only used to better identify the posting profile when you view it in this page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f177-140"><strong>Codice conto</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="9f177-141">Specificare se il profilo registrazione è applicabile a un singolo cliente, a un gruppo di clienti o a tutti i clienti:</span><span class="sxs-lookup"><span data-stu-id="9f177-141">Specify whether the posting profile applies to a single customer, a group of customers, or all customers:</span></span>
<ul>
<li><span data-ttu-id="9f177-142"><strong>Tabella</strong>: il profilo registrazione viene utilizzato per un singolo cliente.</span><span class="sxs-lookup"><span data-stu-id="9f177-142"><strong>Table</strong> – The posting profile applies to a single customer.</span></span> <span data-ttu-id="9f177-143">Selezionare il conto cliente nel campo Numero conto/gruppo.</span><span class="sxs-lookup"><span data-stu-id="9f177-143">Select the customer account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="9f177-144"><strong>Gruppo</strong>: il profilo registrazione viene utilizzato per un gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="9f177-144"><strong>Group</strong> – The posting profile applies to a customer group.</span></span> <span data-ttu-id="9f177-145">Selezionare il gruppo di clienti nel campo Numero conto/gruppo.</span><span class="sxs-lookup"><span data-stu-id="9f177-145">Select the customer group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="9f177-146"><strong>Tuti</strong>: il profilo registrazione viene utilizzato per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="9f177-146"><strong>All</strong> – The posting profile applies to all customers.</span></span> <span data-ttu-id="9f177-147">Lasciare vuoto il campo Numero conto/gruppo.</span><span class="sxs-lookup"><span data-stu-id="9f177-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f177-148"><strong>Numero conto/gruppo</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="9f177-149">Se si seleziona Tabella nel campo Codice conto, selezionare il numero di conto del cliente associato al profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-149">If Table is selected in the Account code field, select the account number of the customer who is associated with the posting profile.</span></span> <span data-ttu-id="9f177-150">Se è stato selezionato Gruppo, selezionare il gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="9f177-150">If Group is selected, select the customer group.</span></span> <span data-ttu-id="9f177-151">Se si seleziona Tutti, lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="9f177-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f177-152"><strong>Conto riepilogativo</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="9f177-153">Selezionare il conto CoGe che sarà utilizzato come conto riepilogativo per i clienti associati al profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-153">Select the ledger account that will be used as the customer summary account for the customers who are associated with the posting profile.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f177-154"><strong>Conto di liquidazione</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-154"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="9f177-155">Selezionare il conto CoGe liquidità utilizzato per le previsioni di cassa.</span><span class="sxs-lookup"><span data-stu-id="9f177-155">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="9f177-156">Questo campo verrà visualizzato solo se le previsioni di cassa sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="9f177-156">This field will only appear if cash flow forecasts are enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f177-157"><strong>Pagamenti anticipati IVA</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-157"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="9f177-158">Selezionare il conto dell'IVA per i pagamenti incassati in anticipo.</span><span class="sxs-lookup"><span data-stu-id="9f177-158">Select the account for sales tax for payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Nota" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="9f177-160"><strong>Nota</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-160"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9f177-161">Utilizzare la pagina Parametri contabilità clienti per specificare il profilo registrazione da utilizzare quando un pagamento viene contrassegnato come pagamento anticipato.</span><span class="sxs-lookup"><span data-stu-id="9f177-161">Use the Accounts receivable parameters page to specify the posting profile to use when a payment is marked as a prepayment.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f177-162"><strong>Conto per passività di sconto</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-162"><strong>Liabilities for discount account</strong></span></span></td>
<td><span data-ttu-id="9f177-163">Selezionare il conto CoGe per le passività di sconto.</span><span class="sxs-lookup"><span data-stu-id="9f177-163">Select the ledger account for liabilities of discount.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f177-164"><strong>Sequenza lettere di sollecito</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-164"><strong>Collection letter sequence</strong></span></span></td>
<td><span data-ttu-id="9f177-165">Selezionare l'identificatore della sequenza lettere di sollecito da utilizzare per i clienti a cui viene assegnato il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-165">Select the identifier of the collection letter sequence to use for customers to whom the posting profile is assigned.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f177-166"><strong>Codice interessi</strong></span><span class="sxs-lookup"><span data-stu-id="9f177-166"><strong>Interest code</strong></span></span></td>
<td><span data-ttu-id="9f177-167">Selezionare il codice interessi da utilizzare per il calcolo degli interessi per i clienti a cui viene assegnato il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-167">Select the interest code to use for the calculation of interest for customers to whom the posting profile is assigned.</span></span></td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a><span data-ttu-id="9f177-168">**Restrizioni tabella**</span><span class="sxs-lookup"><span data-stu-id="9f177-168">**Table restrictions**</span></span>

<span data-ttu-id="9f177-169">Per le transazioni con il profilo registrazione selezionato, specificare se le transazioni verranno liquidate automaticamente, gli interessi verranno calcolati e le lettere di sollecito verranno emesse.</span><span class="sxs-lookup"><span data-stu-id="9f177-169">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="9f177-170">È inoltre possibile selezionare il conto utilizzato quando le transazioni con il profilo registrazione selezionato vengono chiuse.</span><span class="sxs-lookup"><span data-stu-id="9f177-170">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="9f177-171">Specificare i valori seguenti per impostare il profilo registrazione:</span><span class="sxs-lookup"><span data-stu-id="9f177-171">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="9f177-172">Campo</span><span class="sxs-lookup"><span data-stu-id="9f177-172">Field</span></span>                 | <span data-ttu-id="9f177-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f177-173">Description</span></span>                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9f177-174">**Liquidazione**</span><span class="sxs-lookup"><span data-stu-id="9f177-174">**Settlement**</span></span>        | <span data-ttu-id="9f177-175">Selezionare questa opzione di controllo per abilitare la liquidazione automatica delle transazioni con questo profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f177-175">Select this toggle to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="9f177-176">Se l'opzione è deselezionata, è necessario liquidare manualmente le transazioni utilizzando la pagina Liquida transazioni aperte o la pagina Pagamenti cliente.</span><span class="sxs-lookup"><span data-stu-id="9f177-176">If this toggle is cleared, you must manually settle transactions by using the Settle open transactions page or the Enter customer payments page.</span></span> |
| <span data-ttu-id="9f177-177">**Interessi**</span><span class="sxs-lookup"><span data-stu-id="9f177-177">**Interest**</span></span>          | <span data-ttu-id="9f177-178">Selezionare questa opzione se gli interessi devono essere calcolati sui saldi residui per i conti cliente che utilizzano questo profilo.</span><span class="sxs-lookup"><span data-stu-id="9f177-178">Select this toggle if interest should be calculated on outstanding balances for customer accounts that use this profile.</span></span> <span data-ttu-id="9f177-179">Se questa opzione è deselezionata, gli interessi non verranno calcolati per tali clienti.</span><span class="sxs-lookup"><span data-stu-id="9f177-179">If this toggle is cleared, interest will not be calculated for these customers.</span></span>                                           |
| <span data-ttu-id="9f177-180">**Lettera di sollecito**</span><span class="sxs-lookup"><span data-stu-id="9f177-180">**Collection letter**</span></span> | <span data-ttu-id="9f177-181">Selezionare questa opzione se le lettere di sollecito devono essere generate per i conti cliente che utilizzano questo profilo.</span><span class="sxs-lookup"><span data-stu-id="9f177-181">Select this toggle if collection letters should be generated for customer accounts that use this profile.</span></span> <span data-ttu-id="9f177-182">Se questa opzione è deselezionata, le lettere di sollecito non verranno generate per tali clienti.</span><span class="sxs-lookup"><span data-stu-id="9f177-182">If this toggle is cleared, collection letters will not be generated for these customers.</span></span>                                                 |
| <span data-ttu-id="9f177-183">**Chiudi**</span><span class="sxs-lookup"><span data-stu-id="9f177-183">**Close**</span></span>             | <span data-ttu-id="9f177-184">Selezionare un profilo registrazione da applicare quando le transazioni con il profilo registrazione specificato vengono chiuse.</span><span class="sxs-lookup"><span data-stu-id="9f177-184">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="9f177-185">È considerata chiusa una transazione liquidata completamente.</span><span class="sxs-lookup"><span data-stu-id="9f177-185">A transaction is regarded as closed when it has been settled in full.</span></span>                                                                           |



<span data-ttu-id="9f177-186">Per ulteriori informazioni, vedere [Panoramica pagamenti cliente](../cash-bank-management/tasks/customer-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f177-186">For more information, see [Customer payment overview](../cash-bank-management/tasks/customer-payment-overview.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]