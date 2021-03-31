---
title: Rendiconto bancario e riconciliazione dei pagamenti dell'UE
description: In questo argomento viene fornita una panoramica delle funzionalità che è possibile utilizzare per riconciliare le informazioni sul pagamento dalle banche dei formati utilizzati dai paesi europei.
author: neserovleo
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5410cd29c59c6c655c22e82eca43b5132b98ff0f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209878"
---
# <a name="bank-statement-and-payment-reconciliation-for-the-eu"></a><span data-ttu-id="7a48a-103">Rendiconto bancario e riconciliazione dei pagamenti dell'UE</span><span class="sxs-lookup"><span data-stu-id="7a48a-103">Bank statement and payment reconciliation for the EU</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a48a-104">In questo argomento viene fornita una panoramica delle funzionalità che è possibile utilizzare per riconciliare le informazioni sul pagamento dalle banche dei formati utilizzati dai paesi europei.</span><span class="sxs-lookup"><span data-stu-id="7a48a-104">This topic provides an overview of the functionality that you can use to reconcile payment information from banks in formats that are used by European countries.</span></span> <span data-ttu-id="7a48a-105">È possibile importare transazioni da banche e liquidare le transazioni a fronte di transazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="7a48a-105">You can import transactions from banks and settle these transactions against existing transactions.</span></span> <span data-ttu-id="7a48a-106">In Europa, è possibile effettuare questa operazione per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a48a-106">In Europe, you can do this for the following scenarios:</span></span>

-   <span data-ttu-id="7a48a-107">Importazione rendiconti bancari</span><span class="sxs-lookup"><span data-stu-id="7a48a-107">Importing bank statements</span></span>
-   <span data-ttu-id="7a48a-108">Importazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="7a48a-108">Importing payments</span></span>
-   <span data-ttu-id="7a48a-109">Importazione di file di risposta</span><span class="sxs-lookup"><span data-stu-id="7a48a-109">Importing return files</span></span>

## <a name="bank-statements"></a><span data-ttu-id="7a48a-110">Rendiconti bancari</span><span class="sxs-lookup"><span data-stu-id="7a48a-110">Bank statements</span></span>
<span data-ttu-id="7a48a-111">Un *rendiconto bancario* o *estratto conto* è un riepilogo delle transazioni finanziarie effettuate in un dato periodo su un conto bancario gestito da una società presso un istituto finanziario.</span><span class="sxs-lookup"><span data-stu-id="7a48a-111">A *bank statement* or *account statement* is a summary of financial transactions that have occurred over a given period on a bank account held by a company with a financial institution.</span></span> <span data-ttu-id="7a48a-112">In Finance è possibile importare un rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="7a48a-112">In Finance, you can import a bank statement.</span></span> <span data-ttu-id="7a48a-113">È importante liquidare le transazioni importate con le transazioni esistenti nonché verificare il saldo iniziale e finale dei conti bancari.</span><span class="sxs-lookup"><span data-stu-id="7a48a-113">It is important to settle imported transactions with existing transactions as well as verify the opening and ending balance of the bank accounts.</span></span> <span data-ttu-id="7a48a-114">Nel seguente elenco sono riportati i formati europei supportati.</span><span class="sxs-lookup"><span data-stu-id="7a48a-114">The following list includes the supported European formats.</span></span>

-   <span data-ttu-id="7a48a-115">Formati di file europei per la riconciliazione estratti conto avanzata.</span><span class="sxs-lookup"><span data-stu-id="7a48a-115">Advanced bank reconciliation European file formats.</span></span> <span data-ttu-id="7a48a-116">Per ulteriori informazioni, vedere [Panoramica sulla riconciliazione degli estratti conto avanzata](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7a48a-116">For more information, see [Advanced bank reconciliation overview](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span></span>
-   <span data-ttu-id="7a48a-117">Formato di file del messaggio di rendiconto bancario ISO 20022 camt.053.</span><span class="sxs-lookup"><span data-stu-id="7a48a-117">ISO 20022 camt.053 bank statement message file format.</span></span>
-   <span data-ttu-id="7a48a-118">Formato di file di rendiconto bancario CODA.</span><span class="sxs-lookup"><span data-stu-id="7a48a-118">CODA bank statement file format.</span></span> <span data-ttu-id="7a48a-119">Per ulteriori informazioni, vedere [Rendiconto bancario CODA](emea-bel-coda-bank-statement-import.md).</span><span class="sxs-lookup"><span data-stu-id="7a48a-119">For more information, see [CODA bank statement](emea-bel-coda-bank-statement-import.md).</span></span>

## <a name="customer-and-vendor-payments-import-and-return-messages"></a><span data-ttu-id="7a48a-120">Messaggi di importazione e risposta di pagamenti clienti e fornitori</span><span class="sxs-lookup"><span data-stu-id="7a48a-120">Customer and vendor payments import and return messages</span></span>
<span data-ttu-id="7a48a-121">Oltre a un rendiconto bancario, le banche possono generare messaggi specifici, contenenti informazioni sui pagamenti clienti/fornitori, che possono essere importati in Finance ed essere riconciliati con le transazioni dei clienti e dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="7a48a-121">In addition to a bank statement, banks can provide specific messages, containing information about customer and vendor payments, which can be imported into Finance and reconciled with customer and vendor transactions.</span></span> <span data-ttu-id="7a48a-122">Quando una società necessita di ricevere dalla banca informazioni sulle transazioni dei pagamenti clienti in entrata, è possibile utilizzare i formati di importazione.</span><span class="sxs-lookup"><span data-stu-id="7a48a-122">When a company needs to receive information about incoming customer payments transactions from the bank, the import formats can be used.</span></span> <span data-ttu-id="7a48a-123">Le società che utilizzano l'addebito diretto e il bonifico possono ricevere messaggi di risposta per aggiornare lo stato dei pagamenti precedentemente esportati.</span><span class="sxs-lookup"><span data-stu-id="7a48a-123">For companies that use direct debit and credit transfer, the return messages can be received to update the status of payments that were previously exported.</span></span> <span data-ttu-id="7a48a-124">La differenza tra i formati di importazione e i formati di risposta consiste nel fatto che le risposte servono principalmente ad aggiornare le righe del giornale di registrazione pagamenti già create (possono essere create con l'addebito diretto o il bonifico) anziché crearne di nuove.</span><span class="sxs-lookup"><span data-stu-id="7a48a-124">The difference between import formats and return formats is that returns are targeted mostly to update already created payment journal lines (they can be created when direct debit or credit transfer were initiated) instead of creating new lines.</span></span> <span data-ttu-id="7a48a-125">Alcuni formati di importazione complessi possono includere gli scenari di risposta.</span><span class="sxs-lookup"><span data-stu-id="7a48a-125">Some complex import formats can also include return scenarios.</span></span> <span data-ttu-id="7a48a-126">Nel seguente esempio viene illustrato come implementare questa divisione.</span><span class="sxs-lookup"><span data-stu-id="7a48a-126">The following example shows how this division should be implemented.</span></span>

### <a name="import-formats"></a><span data-ttu-id="7a48a-127">Formato di importazione</span><span class="sxs-lookup"><span data-stu-id="7a48a-127">Import formats</span></span>

-   <span data-ttu-id="7a48a-128">Messaggio di notifica della banca [ISO 20022 camt.054](emea-ISO20022-file-formats.md)</span><span class="sxs-lookup"><span data-stu-id="7a48a-128">[ISO 20022 camt.054](emea-ISO20022-file-formats.md) bank notification message</span></span>
-   <span data-ttu-id="7a48a-129">[Formato di importazione Nets](emea-nor-nets-import-format.md) - Complessa funzionalità per i formati di pagamento norvegesi</span><span class="sxs-lookup"><span data-stu-id="7a48a-129">[Nets import format](emea-nor-nets-import-format.md) - Complex feature for Norwegian payment formats</span></span>
-   [<span data-ttu-id="7a48a-130">Importazione pagamenti cliente PVR</span><span class="sxs-lookup"><span data-stu-id="7a48a-130">ESR customer payments import</span></span>](emea-che-esr-customer-payments-import.md) 
-   <span data-ttu-id="7a48a-131">formati di importazione pagamenti per la Svezia - formati BankGirot Max e BankGirot OCR</span><span class="sxs-lookup"><span data-stu-id="7a48a-131">Import payment formats for Sweden - BankGirot Max and BankGirot OCR formats</span></span>

### <a name="return-formats"></a><span data-ttu-id="7a48a-132">Formati di risposta</span><span class="sxs-lookup"><span data-stu-id="7a48a-132">Return formats</span></span>

-   <span data-ttu-id="7a48a-133">Report sullo stato dei pagamenti [ISO 20022 pain.002](emea-ISO20022-file-formats.md)</span><span class="sxs-lookup"><span data-stu-id="7a48a-133">[ISO 20022 pain.002](emea-ISO20022-file-formats.md) payment status report</span></span>
-   <span data-ttu-id="7a48a-134">(DNK) BetalingsserviceBasis-returformat - Formato di risposta per il formato di esportazione clienti Betalingsservice</span><span class="sxs-lookup"><span data-stu-id="7a48a-134">(DNK) BetalingsserviceBasis-returformat – Return format for customer Betalingsservice export format</span></span>
-   <span data-ttu-id="7a48a-135">[Formati di importazione pagamenti per la Svezia](emea-swe-payment-formats-import.md) - Risposte Bankgirot Autogiro</span><span class="sxs-lookup"><span data-stu-id="7a48a-135">[Import payment formats for Sweden](emea-swe-payment-formats-import.md) - Bankgirot Autogiro returns</span></span>
-   <span data-ttu-id="7a48a-136">Risposta (SWE) BankGirot - Formato di risposta pagamenti fornitori che corrisponde al formato di esportazione Bankgirot</span><span class="sxs-lookup"><span data-stu-id="7a48a-136">(SWE) BankGirot return – Vendor payments return format, which corresponds to Bankgirot export format</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]