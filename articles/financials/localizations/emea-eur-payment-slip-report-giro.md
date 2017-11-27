---
title: Report della distinta di pagamento per l'Europa
description: Di seguito vengono descritti i report della distinta di pagamento per l'Europa.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264604
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a64a2ae8c84802a06e4f0f54a99bed3966c337f4
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="payment-slip-report-for-europe"></a><span data-ttu-id="54dc9-103">Report della distinta di pagamento per l'Europa</span><span class="sxs-lookup"><span data-stu-id="54dc9-103">Payment slip report for Europe</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="54dc9-104">Di seguito vengono descritti i report della distinta di pagamento per l'Europa.</span><span class="sxs-lookup"><span data-stu-id="54dc9-104">This topic provides information about payment slip reports for Europe.</span></span>

<span data-ttu-id="54dc9-105">La funzionalità per i report della distinta di pagamento è disponibile per le persone giuridiche il cui indirizzo principale si trova in Danimarca, Belgio, Norvegia, Svizzera o Finlandia.</span><span class="sxs-lookup"><span data-stu-id="54dc9-105">The functionality for payment slip reports is available for legal entities that have their primary address in Denmark, Belgium, Norway, Switzerland, or Finland.</span></span> <span data-ttu-id="54dc9-106">Le aziende spesso allegano le distinte di pagamento stampate alle fatture per fornire un riferimento di pagamento per la registrazione e la liquidazione.</span><span class="sxs-lookup"><span data-stu-id="54dc9-106">Businesses often attach printed payment slips to invoices to provide a payment reference for posting and settlement.</span></span> <span data-ttu-id="54dc9-107">La distinta di pagamento può essere utilizzata per fatture di progetti o servizi, lettere di sollecito, note d'interesse ed estratti conto, oltre che per fatture di vendita e fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="54dc9-107">The payment slip can be used for project or service invoices, collection letters, interest notes, and account statements, in addition to sales invoices and free text invoices.</span></span>

## <a name="set-up-a-creditor-id-number-denmark-only"></a><span data-ttu-id="54dc9-108">Impostare un numero ID creditore (Solo Danimarca)</span><span class="sxs-lookup"><span data-stu-id="54dc9-108">Set up a creditor ID number (Denmark only)</span></span>
<span data-ttu-id="54dc9-109">Seguire questi passaggi per immettere il numero di identificazione (ID) del creditore della società.</span><span class="sxs-lookup"><span data-stu-id="54dc9-109">Follow these steps to enter your company's creditor identification (ID) number.</span></span> <span data-ttu-id="54dc9-110">Questo numero viene fornito dall'istituto finanziario.</span><span class="sxs-lookup"><span data-stu-id="54dc9-110">Your financial institution provides this number.</span></span> <span data-ttu-id="54dc9-111">Viene utilizzato come riferimento quando si ricevono i pagamenti dei clienti tramite istituti finanziari.</span><span class="sxs-lookup"><span data-stu-id="54dc9-111">It's used as a reference when customer payments are received through financial institutions.</span></span>

1.  <span data-ttu-id="54dc9-112">Fare clic su **Amministrazione organizzazione** &gt; **Impostazione** &gt; **Organizzazione** &gt; **Persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="54dc9-112">Click **Organization administration** &gt; **Setup** &gt; **Organization** &gt; **Legal entities**.</span></span>
2.  <span data-ttu-id="54dc9-113">Nella Scheda dettaglio **Informazioni conto bancario**, nel campo **ID creditore IF**, immettere l'ID creditore univoco di otto cifre.</span><span class="sxs-lookup"><span data-stu-id="54dc9-113">On the **Bank account information** FastTab, in the **FI-Creditor ID** field, enter your unique eight-digit creditor ID number.</span></span>
3.  <span data-ttu-id="54dc9-114">Chiudere il modulo per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="54dc9-114">Close the form to save your changes.</span></span>

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a><span data-ttu-id="54dc9-115">Impostare un formato per l'allegato distinta di pagamento per fatture, note d'interesse, lettere di sollecito e rendiconti bancari</span><span class="sxs-lookup"><span data-stu-id="54dc9-115">Set up a payment slip attachment format for invoices, interest notes, collection letters, and account statements</span></span>
<span data-ttu-id="54dc9-116">Seguire questi passaggi per impostare un formato per gli allegati distinta di pagamento che accompagnano fatture di vendita, fatture a testo libero, note d'interesse, lettere di sollecito ed estratti conto.</span><span class="sxs-lookup"><span data-stu-id="54dc9-116">Follow these steps to set up a format for payment slip attachments that accompany sales invoices, free text invoices, interest notes, collection letters, and account statements.</span></span>

1.  <span data-ttu-id="54dc9-117">Fare clic su **Contabilità clienti** &gt; **Impostazione** &gt; **Moduli** &gt; **Impostazione moduli**.</span><span class="sxs-lookup"><span data-stu-id="54dc9-117">Click **Accounts receivable** &gt; **Setup** &gt; **Forms** &gt; **Form setup**.</span></span>
2.  <span data-ttu-id="54dc9-118">Nella scheda **Fattura**, nel campo **Allegato pagamento associato su fattura cliente**, selezionare il formato per l'allegato distinta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="54dc9-118">On the **Invoice** tab, in the **Associated payment attachment on customer invoice** field, select the payment slip attachment format.</span></span>
3.  <span data-ttu-id="54dc9-119">Nelle schede **Fattura a testo libero**, **Nota d'interesse**, **Lettera di sollecito** ed **Estratto conto** selezionare un formato per la distinta di pagamento per ciascun tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="54dc9-119">On the **Free text invoice**, **Interest note**, **Collection letter**, and **Account statement** tabs, select a payment slip attachment format for each document type.</span></span>
4.  <span data-ttu-id="54dc9-120">Chiudere il modulo per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="54dc9-120">Close the form to save your changes.</span></span>

<span data-ttu-id="54dc9-121">Seguire questi passaggi per impostare un formato per gli allegati distinta di pagamento che accompagnano le fatture di progetto.</span><span class="sxs-lookup"><span data-stu-id="54dc9-121">Follow these steps to set up a format for payment slip attachments that accompany project invoices.</span></span>

1.  <span data-ttu-id="54dc9-122">Fare clic su **Gestione progetti e contabilità** &gt; **Impostazione** &gt; **Moduli** &gt; **Impostazione moduli**.</span><span class="sxs-lookup"><span data-stu-id="54dc9-122">Click **Project management and accounting** &gt; **Setup** &gt; **Forms** &gt; **Form setup**.</span></span>
2.  <span data-ttu-id="54dc9-123">Nel campo **Allegato pagamento associato** selezionare il formato per la distinta base.</span><span class="sxs-lookup"><span data-stu-id="54dc9-123">In the **Associated payment attachment** field, select the payment slip attachment format.</span></span>

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a><span data-ttu-id="54dc9-124">Assegnare un formato di allegato per la distinta di pagamento a un conto cliente</span><span class="sxs-lookup"><span data-stu-id="54dc9-124">Assign a payment slip attachment format to a customer account</span></span>
<span data-ttu-id="54dc9-125">Dopo aver impostato il formato per l'allegato della distinta di pagamento per fatture di vendita, fatture a testo libero, note d'interesse, lettere di sollecito estratti conto e fatture di progetto, è possibile assegnare formati specifici per un cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="54dc9-125">After you set up the payment slip attachment format for sales invoices, free text invoices, interest notes, collection letters, account statements, and project invoices, you can assign specific formats for a selected customer.</span></span>

1.  <span data-ttu-id="54dc9-126">Fare clic su **Contabilità clienti** &gt; **Comune** &gt; **Clienti** &gt; **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="54dc9-126">Click **Accounts receivable** &gt; **Common** &gt; **Customers** &gt; **All customers**.</span></span>
2.  <span data-ttu-id="54dc9-127">Creare un nuovo cliente o selezionarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="54dc9-127">Create a new customer, or select an existing customer.</span></span>
3.  <span data-ttu-id="54dc9-128">Nella Scheda dettaglio **Fattura e consegna**, nei campi **Su fattura cliente**, **Su fattura a testo libero**, **Su nota d'interesse**, **Su lettera di sollecito**, **Su fattura di progetto** e **Su un estratto conto**, selezionare il formato di allegato per le distinte di pagamento che accompagneranno i documenti di ciascun tipo inviati al cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="54dc9-128">On the **Invoice and delivery** FastTab, in the **On a customer invoice**, **On a free text invoice**, **On an interest note**, **On a collection letter**, **On a project invoice**, and **On an account statement** fields, select the format for payment slip attachments that will accompany documents of each type that are sent to the selected customer.</span></span>
4.  <span data-ttu-id="54dc9-129">Chiudere il modulo per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="54dc9-129">Close the form to save your changes.</span></span>





