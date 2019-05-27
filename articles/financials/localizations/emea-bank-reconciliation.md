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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 41857315817f9863f77cb1d5f58711eca258d602
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538023"
---
# <a name="bank-statement-and-payment-reconciliation-for-the-eu"></a><span data-ttu-id="807e2-103">Rendiconto bancario e riconciliazione dei pagamenti dell'UE</span><span class="sxs-lookup"><span data-stu-id="807e2-103">Bank statement and payment reconciliation for the EU</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="807e2-104">In questo argomento viene fornita una panoramica delle funzionalità che è possibile utilizzare per riconciliare le informazioni sul pagamento dalle banche dei formati utilizzati dai paesi europei.</span><span class="sxs-lookup"><span data-stu-id="807e2-104">This topic provides an overview of the functionality that you can use to reconcile payment information from banks in formats that are used by European countries.</span></span>

<span data-ttu-id="807e2-105">In Microsoft Dynamics 365 for Finance and Operations è possibile importare transazioni da banche e liquidare le transazioni a fronte di transazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="807e2-105">In Microsoft Dynamics 365 for Finance and Operations, you can import transactions from banks and settle these transactions against existing transactions.</span></span> <span data-ttu-id="807e2-106">In Europa, è possibile effettuare questa operazione per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="807e2-106">In Europe, you can do this for the following scenarios:</span></span>

-   <span data-ttu-id="807e2-107">Importazione rendiconti bancari</span><span class="sxs-lookup"><span data-stu-id="807e2-107">Importing bank statements</span></span>
-   <span data-ttu-id="807e2-108">Importazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="807e2-108">Importing payments</span></span>
-   <span data-ttu-id="807e2-109">Importazione di file di risposta</span><span class="sxs-lookup"><span data-stu-id="807e2-109">Importing return files</span></span>

## <a name="bank-statements"></a><span data-ttu-id="807e2-110">Rendiconti bancari</span><span class="sxs-lookup"><span data-stu-id="807e2-110">Bank statements</span></span>
<span data-ttu-id="807e2-111">Un *rendiconto bancario* o *estratto conto* è un riepilogo delle transazioni finanziarie effettuate in un dato periodo su un conto bancario gestito da una società presso un istituto finanziario.</span><span class="sxs-lookup"><span data-stu-id="807e2-111">A *bank statement* or *account statement* is a summary of financial transactions that have occurred over a given period on a bank account held by a company with a financial institution.</span></span> <span data-ttu-id="807e2-112">In Finance and Operations è possibile importare un rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="807e2-112">In Finance and Operations you can import a bank statement.</span></span> <span data-ttu-id="807e2-113">È importante liquidare le transazioni importate con le transazioni esistenti nonché verificare il saldo iniziale e finale dei conti bancari.</span><span class="sxs-lookup"><span data-stu-id="807e2-113">It is important to settle imported transactions with existing transactions as well as verify the opening and ending balance of the bank accounts.</span></span> <span data-ttu-id="807e2-114">Nel seguente elenco sono riportati i formati europei supportati.</span><span class="sxs-lookup"><span data-stu-id="807e2-114">The following list includes the supported European formats.</span></span>

-   <span data-ttu-id="807e2-115">Formati di file europei per la riconciliazione estratti conto avanzata.</span><span class="sxs-lookup"><span data-stu-id="807e2-115">Advanced bank reconciliation European file formats.</span></span> <span data-ttu-id="807e2-116">Per ulteriori informazioni, vedere [Panoramica sulla riconciliazione degli estratti conto avanzata](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="807e2-116">For more information, see [Advanced bank reconciliation overview](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span></span>
-   <span data-ttu-id="807e2-117">Formato di file del messaggio di rendiconto bancario ISO 20022 camt.053.</span><span class="sxs-lookup"><span data-stu-id="807e2-117">ISO 20022 camt.053 bank statement message file format.</span></span>
-   <span data-ttu-id="807e2-118">Formato di file di rendiconto bancario CODA.</span><span class="sxs-lookup"><span data-stu-id="807e2-118">CODA bank statement file format.</span></span> <span data-ttu-id="807e2-119">Per ulteriori informazioni, vedere [Rendiconto bancario CODA](emea-bel-coda-bank-statement-import.md).</span><span class="sxs-lookup"><span data-stu-id="807e2-119">For more information, see [CODA bank statement](emea-bel-coda-bank-statement-import.md).</span></span>

## <a name="customer-and-vendor-payments-import-and-return-messages"></a><span data-ttu-id="807e2-120">Messaggi di importazione e risposta di pagamenti clienti e fornitori</span><span class="sxs-lookup"><span data-stu-id="807e2-120">Customer and vendor payments import and return messages</span></span>
<span data-ttu-id="807e2-121">Oltre a un rendiconto bancario, le banche possono generare messaggi specifici, contenenti informazioni sui pagamenti clienti/fornitori, che possono essere importati in Finance and Operations ed essere riconciliati con le transazioni dei clienti e dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="807e2-121">In addition to a bank statement, banks can provide specific messages, containing information about customer and vendor payments, which can be imported into Finance and Operations and reconciled with customer and vendor transactions.</span></span> <span data-ttu-id="807e2-122">Quando una società necessita di ricevere dalla banca informazioni sulle transazioni dei pagamenti clienti in entrata, è possibile utilizzare i formati di importazione.</span><span class="sxs-lookup"><span data-stu-id="807e2-122">When a company needs to receive information about incoming customer payments transactions from the bank, the import formats can be used.</span></span> <span data-ttu-id="807e2-123">Le società che utilizzano l'addebito diretto e il bonifico possono ricevere messaggi di risposta per aggiornare lo stato dei pagamenti precedentemente esportati.</span><span class="sxs-lookup"><span data-stu-id="807e2-123">For companies that use direct debit and credit transfer, the return messages can be received to update the status of payments that were previously exported.</span></span> <span data-ttu-id="807e2-124">La differenza tra i formati di importazione e i formati di risposta consiste nel fatto che le risposte servono principalmente ad aggiornare le righe del giornale di registrazione pagamenti già create (possono essere create con l'addebito diretto o il bonifico) anziché crearne di nuove.</span><span class="sxs-lookup"><span data-stu-id="807e2-124">The difference between import formats and return formats is that returns are targeted mostly to update already created payment journal lines (they can be created when direct debit or credit transfer were initiated) instead of creating new lines.</span></span> <span data-ttu-id="807e2-125">Alcuni formati di importazione complessi possono includere gli scenari di risposta.</span><span class="sxs-lookup"><span data-stu-id="807e2-125">Some complex import formats can also include return scenarios.</span></span> <span data-ttu-id="807e2-126">Nel seguente esempio viene illustrato come implementare questa divisione.</span><span class="sxs-lookup"><span data-stu-id="807e2-126">The following example shows how this division should be implemented.</span></span>

### <a name="import-formats"></a><span data-ttu-id="807e2-127">Formato di importazione</span><span class="sxs-lookup"><span data-stu-id="807e2-127">Import formats</span></span>

-   <span data-ttu-id="807e2-128">Messaggio di notifica della banca ISO 20022 [camt.054](emea-ISO20022-file-formats.md)</span><span class="sxs-lookup"><span data-stu-id="807e2-128">ISO 20022 [camt.054](emea-ISO20022-file-formats.md) bank notification message</span></span>
-   <span data-ttu-id="807e2-129">[Formato di importazione Nets](emea-nor-nets-import-format.md) - Complessa funzionalità per i formati di pagamento norvegesi</span><span class="sxs-lookup"><span data-stu-id="807e2-129">[Nets import format](emea-nor-nets-import-format.md) - Complex feature for Norwegian payment formats</span></span>
-   <span data-ttu-id="807e2-130">[Importazione pagamenti clienti ESR](emea-che-esr-customer-payments-import.md)</span><span class="sxs-lookup"><span data-stu-id="807e2-130">[ESR](emea-che-esr-customer-payments-import.md) customer payments import</span></span>
-   <span data-ttu-id="807e2-131">formati di importazione pagamenti per la Svezia - formati BankGirot Max e BankGirot OCR</span><span class="sxs-lookup"><span data-stu-id="807e2-131">Import payment formats for Sweden - BankGirot Max and BankGirot OCR formats</span></span>

### <a name="return-formats"></a><span data-ttu-id="807e2-132">Formati di risposta</span><span class="sxs-lookup"><span data-stu-id="807e2-132">Return formats</span></span>

-   <span data-ttu-id="807e2-133">Report sullo stato dei pagamenti ISO 20022 [pain.002](emea-ISO20022-file-formats.md)</span><span class="sxs-lookup"><span data-stu-id="807e2-133">ISO 20022 [pain.002](emea-ISO20022-file-formats.md) payment status report</span></span>
-   <span data-ttu-id="807e2-134">(DNK) BetalingsserviceBasis-returformat - Formato di risposta per il formato di esportazione clienti Betalingsservice</span><span class="sxs-lookup"><span data-stu-id="807e2-134">(DNK) BetalingsserviceBasis-returformat – Return format for customer Betalingsservice export format</span></span>
-   <span data-ttu-id="807e2-135">[Formati di importazione pagamenti per la Svezia](emea-swe-payment-formats-import.md) - Risposte Bankgirot Autogiro</span><span class="sxs-lookup"><span data-stu-id="807e2-135">[Import payment formats for Sweden](emea-swe-payment-formats-import.md) - Bankgirot Autogiro returns</span></span>
-   <span data-ttu-id="807e2-136">Risposta (SWE) BankGirot - Formato di risposta pagamenti fornitori che corrisponde al formato di esportazione Bankgirot</span><span class="sxs-lookup"><span data-stu-id="807e2-136">(SWE) BankGirot return – Vendor payments return format, which corresponds to Bankgirot export format</span></span>


