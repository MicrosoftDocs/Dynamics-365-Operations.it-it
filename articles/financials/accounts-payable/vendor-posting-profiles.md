---
title: Profili registrazione fornitori
description: "I profili di registrazione fornitore controllano la registrazione delle transazioni fornitore nella contabilità generale."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPosting
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: ae019ebec2788fc499b0f2ef27a7eb2832ceaa9d
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="vendor-posting-profiles"></a><span data-ttu-id="4a177-103">Profili registrazione fornitori</span><span class="sxs-lookup"><span data-stu-id="4a177-103">Vendor posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4a177-104">I profili di registrazione fornitore controllano la registrazione delle transazioni fornitore nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="4a177-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="4a177-105">Profili registrazione fornitori</span><span class="sxs-lookup"><span data-stu-id="4a177-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="4a177-106">I profili registrazione del fornitore consentono di assegnare i conti CoGe e le impostazioni del documento a tutti i fornitori, a un gruppo di fornitori o a un singolo fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a177-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors or a single vendor.</span></span> <span data-ttu-id="4a177-107">Queste impostazioni verranno utilizzate quando si creano ordini fornitore, fatture fornitore e pagamenti in contanti.</span><span class="sxs-lookup"><span data-stu-id="4a177-107">These settings will be used when you create purchase orders, vendor invoices and cash payments.</span></span> <span data-ttu-id="4a177-108">Per alcune transazioni, è possibile selezionare un profilo registrazione diverso a cui verrà accordata precedenza sui profili registrazione impostati per le transazioni in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="4a177-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> <span data-ttu-id="4a177-109">Il profilo di registrazione predefinito viene definito nella scheda dettaglio Contabilità generale e IVA nella pagina dei parametri Contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="4a177-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts payable parameters page.</span></span> <span data-ttu-id="4a177-110">Il profilo di registrazione predefinito verrà incluso automaticamente nell'intestazione di nuovi documenti in cui è possibile modificarlo in un profilo registrazione diverso se necessario.</span><span class="sxs-lookup"><span data-stu-id="4a177-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="4a177-111">È inoltre possibile associare le definizioni di registrazione ai tipi di registrazione transazioni nella pagina Definizioni di registrazione transazioni.</span><span class="sxs-lookup"><span data-stu-id="4a177-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="4a177-112">Le definizioni di registrazione controllano la registrazione delle transazioni fornitore nella contabilità generale invece dei profili registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a177-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="4a177-113">Creazione di un profilo registrazione</span><span class="sxs-lookup"><span data-stu-id="4a177-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="4a177-114">**Impostazioni**</span><span class="sxs-lookup"><span data-stu-id="4a177-114">**Setup**</span></span>

<span data-ttu-id="4a177-115">Specificare i conti CoGe utilizzati nella registrazione delle transazioni che utilizzano il profilo registrazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="4a177-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="4a177-116">Selezionare un codice conto e, quando possibile, un numero di conto o di gruppo per il profilo registrazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="4a177-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="4a177-117">Durante il processo di registrazione, il profilo registrazione più appropriato per ciascuna transazione si trova cercando il codice conto, il numero di conto o la combinazione gruppo e numero più specifica in base alla seguente priorità:</span><span class="sxs-lookup"><span data-stu-id="4a177-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="4a177-118">**Codice conto** - valore del campo</span><span class="sxs-lookup"><span data-stu-id="4a177-118">**Account code** field value</span></span> | <span data-ttu-id="4a177-119">**Numero conto/gruppo** - valore del campo</span><span class="sxs-lookup"><span data-stu-id="4a177-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="4a177-120">Priorità ricerca</span><span class="sxs-lookup"><span data-stu-id="4a177-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="4a177-121">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="4a177-121">**Table**</span></span>                    | <span data-ttu-id="4a177-122">Conto specifico del fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a177-122">Specific vendor account</span></span>                     | <span data-ttu-id="4a177-123">1</span><span class="sxs-lookup"><span data-stu-id="4a177-123">1</span></span>               |
| <span data-ttu-id="4a177-124">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="4a177-124">**Group**</span></span>                    | <span data-ttu-id="4a177-125">Gruppo di fornitori assegnato al fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a177-125">vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="4a177-126">2</span><span class="sxs-lookup"><span data-stu-id="4a177-126">2</span></span>               |
| <span data-ttu-id="4a177-127">**Tutti**</span><span class="sxs-lookup"><span data-stu-id="4a177-127">**All**</span></span>                      | <span data-ttu-id="4a177-128">Vuoto</span><span class="sxs-lookup"><span data-stu-id="4a177-128">Blank</span></span>                                       | <span data-ttu-id="4a177-129">3</span><span class="sxs-lookup"><span data-stu-id="4a177-129">3</span></span>               |

<span data-ttu-id="4a177-130">Se si desidera assegnare lo stesso profilo registrazione a tutte le transazioni fornitore, impostare un solo profilo registrazione con il valore Tutti nel campo Codice conto.</span><span class="sxs-lookup"><span data-stu-id="4a177-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="4a177-131">Specificare i valori seguenti per impostare il profilo registrazione:</span><span class="sxs-lookup"><span data-stu-id="4a177-131">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4a177-132">Campo</span><span class="sxs-lookup"><span data-stu-id="4a177-132">Field</span></span></th>
<th><span data-ttu-id="4a177-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a177-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4a177-134"><strong>Profilo registrazione</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="4a177-135">Immettere un codice per il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a177-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="4a177-136">Ad esempio, è possibile creare due profili registrazione per ottenere un conto per i saldi fornitore in valuta nazionale e un altro conto per i saldi fornitore in valuta estera.</span><span class="sxs-lookup"><span data-stu-id="4a177-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="4a177-137">È possibile chiamare un conto Nazionale e l'altro Estero.</span><span class="sxs-lookup"><span data-stu-id="4a177-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4a177-138"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="4a177-139">Immettere una descrizione del profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a177-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4a177-140"><strong>Codice conto</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="4a177-141">Specificare se il profilo registrazione è valido per uno specifico fornitore, un gruppo di fornitori o tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="4a177-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="4a177-142"><strong>Tabella</strong>: il profilo registrazione viene utilizzato per un singolo fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a177-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="4a177-143">Selezionare il conto fornitore nel campo Numero conto/gruppo.</span><span class="sxs-lookup"><span data-stu-id="4a177-143">Select the vendor account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="4a177-144"><strong>Gruppo</strong>: il profilo registrazione viene utilizzato per un gruppo di fornitori.</span><span class="sxs-lookup"><span data-stu-id="4a177-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="4a177-145">Selezionare il gruppo fornitori nel campo Numero conto/gruppo.</span><span class="sxs-lookup"><span data-stu-id="4a177-145">Select the vendor group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="4a177-146"><strong>Tutti</strong>: il profilo registrazione viene utilizzato per tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="4a177-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="4a177-147">Lasciare vuoto il campo Numero conto/gruppo.</span><span class="sxs-lookup"><span data-stu-id="4a177-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4a177-148"><strong>Numero conto/gruppo</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="4a177-149">Se si seleziona Tabella nel campo Codice conto, selezionare il numero di conto del fornitore associato al profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a177-149">If Table is selected in the Account code field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="4a177-150">Se è selezionata l'opzione Gruppo, indicare un gruppo di fornitori.</span><span class="sxs-lookup"><span data-stu-id="4a177-150">If Group is selected, select a vendor group.</span></span> <span data-ttu-id="4a177-151">Se si seleziona Tutti, lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="4a177-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4a177-152"><strong>Conto riepilogativo</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="4a177-153">Selezionare il conto CoGe da utilizzare come conto riepilogativo per i fornitori a cui fa riferimento il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a177-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Nota" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="4a177-155"><strong>Nota</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-155"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4a177-156">Se è selezionata l'opzione Usa definizioni di registrazione della pagina Parametri di contabilità generale, viene utilizzata la definizione di registrazione transazioni per le fatture fornitore anziché il conto riepilogativo.</span><span class="sxs-lookup"><span data-stu-id="4a177-156">If the Use posting definitions toggle is selected in the General ledger parameters page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4a177-157"><strong>Conto di liquidazione</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="4a177-158">Selezionare il conto CoGe liquidità utilizzato per le previsioni di cassa.</span><span class="sxs-lookup"><span data-stu-id="4a177-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="4a177-159">Questo campo è disponibile solo quando le previsioni di cassa sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="4a177-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4a177-160"><strong>Pagamenti anticipati IVA</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="4a177-161">Selezionare il conto per i pagamenti IVA incassati in anticipo.</span><span class="sxs-lookup"><span data-stu-id="4a177-161">Select the account for sales tax payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Nota" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="4a177-163"><strong>Nota</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4a177-164">Il profilo registrazione utilizzato quando il pagamento viene contrassegnato come pagamento anticipato è selezionato nel campo Profilo registrazione con giustificativo giornale di registrazione per pagamento anticipato nell'area Contabilità generale e IVA della pagina Parametri contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="4a177-164">The posting profile that is used when the payment is marked as a prepayment is selected in the Posting profile with prepayment journal voucher field in the Ledger and sales tax area of the Accounts payable parameters page.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4a177-165"><strong>Arrivo</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-165"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="4a177-166">Selezionare il conto CoGe in cui devono essere registrate le informazioni sulle fatture fornitore non approvate.</span><span class="sxs-lookup"><span data-stu-id="4a177-166">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="4a177-167">Le informazioni vengono immesse nel giornale di registrazione del registro fatture.</span><span class="sxs-lookup"><span data-stu-id="4a177-167">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="4a177-168">Si supponga ad esempio che un utente immetta informazioni molto generali sulle fatture fornitore non appena queste vengono inserite nel registro fatture.</span><span class="sxs-lookup"><span data-stu-id="4a177-168">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="4a177-169">Alla registrazione del registro fatture, le transazioni verranno registrate nel conto immesso in questo campo e nel campo Conto di contropartita.</span><span class="sxs-lookup"><span data-stu-id="4a177-169">When the invoice register is posted, the transactions are posted to the account that is entered here and in the Offset account field.</span></span> <span data-ttu-id="4a177-170">Una volta approvate le fatture, il debito verrà trasferito dal conto Arrivi al conto riepilogativo del fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a177-170">When the invoices are approved, the debt is transferred from the Arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4a177-171"><strong>Conto di contropartita</strong></span><span class="sxs-lookup"><span data-stu-id="4a177-171"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="4a177-172">Selezionare il conto CoGe da utilizzare per la registrazione in contropartita delle fatture fornitore aggiornate mediante il registro fatture.</span><span class="sxs-lookup"><span data-stu-id="4a177-172">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="4a177-173">Il conto di contropartita funge da contropartita per le transazioni registrate nei conti arrivi.</span><span class="sxs-lookup"><span data-stu-id="4a177-173">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="4a177-174">Di conseguenza, il conto contiene gli acquisti fornitore non ancora approvati.</span><span class="sxs-lookup"><span data-stu-id="4a177-174">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a><span data-ttu-id="4a177-175">**Restrizioni tabella**</span><span class="sxs-lookup"><span data-stu-id="4a177-175">**Table restrictions**</span></span>

<span data-ttu-id="4a177-176">Per le transazioni con il profilo registrazione selezionato, specificare se le transazioni verranno liquidate automaticamente, gli interessi verranno calcolati e le lettere di sollecito verranno emesse.</span><span class="sxs-lookup"><span data-stu-id="4a177-176">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="4a177-177">È inoltre possibile selezionare il conto utilizzato quando le transazioni con il profilo registrazione selezionato vengono chiuse.</span><span class="sxs-lookup"><span data-stu-id="4a177-177">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="4a177-178">Specificare i valori seguenti per impostare il profilo registrazione:</span><span class="sxs-lookup"><span data-stu-id="4a177-178">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="4a177-179">Campo</span><span class="sxs-lookup"><span data-stu-id="4a177-179">Field</span></span>          | <span data-ttu-id="4a177-180">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a177-180">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4a177-181">**Liquidazione**</span><span class="sxs-lookup"><span data-stu-id="4a177-181">**Settlement**</span></span> | <span data-ttu-id="4a177-182">Selezionare questa opzione per attivare la liquidazione automatica delle transazioni con questo profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a177-182">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="4a177-183">Se questa opzione è deselezionata, è necessario liquidare manualmente le transazioni utilizzando la pagina Liquida transazioni aperte.</span><span class="sxs-lookup"><span data-stu-id="4a177-183">If this option is cleared, you must manually settle transactions by using the Settle open transactions page.</span></span> |
| <span data-ttu-id="4a177-184">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="4a177-184">**Cancel**</span></span>     | <span data-ttu-id="4a177-185">Selezionare questa opzione per poter annullare le transazioni con questo profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a177-185">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="4a177-186">**Chiudi**</span><span class="sxs-lookup"><span data-stu-id="4a177-186">**Close**</span></span>      | <span data-ttu-id="4a177-187">Selezionare un profilo registrazione da applicare quando le transazioni con il profilo registrazione specificato vengono chiuse.</span><span class="sxs-lookup"><span data-stu-id="4a177-187">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="4a177-188">È considerata chiusa una transazione liquidata completamente.</span><span class="sxs-lookup"><span data-stu-id="4a177-188">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |






