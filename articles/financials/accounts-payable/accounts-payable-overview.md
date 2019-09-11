---
title: Configurare la panoramica contabilità fornitori
description: Questo articolo descrive le pagine utilizzate per impostare le funzionalità di base e facoltative per la contabilità fornitori in Microsoft Dynamics 365 for Finance and Operations. Vengono descritti i passaggi di configurazione da completare prima di iniziare a impostare la contabilità fornitori.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce2caf8df871ee8f577b3a1af9d71244a1dc4694
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864992"
---
# <a name="configure-accounts-payable-overview"></a><span data-ttu-id="03240-104">Configurare la panoramica contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="03240-104">Configure Accounts payable overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03240-105">Questo articolo descrive le pagine utilizzate per impostare le funzionalità di base e facoltative per la contabilità fornitori in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="03240-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="03240-106">Vengono descritti i passaggi di configurazione da completare prima di iniziare a impostare la contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="03240-107">Prerequisiti per l'impostazione della contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="03240-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="03240-108">Prima di poter impostare la contabilità fornitori, occorre completare la seguente configurazione:</span><span class="sxs-lookup"><span data-stu-id="03240-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="03240-109">In contabilità generale:</span><span class="sxs-lookup"><span data-stu-id="03240-109">In General ledger:</span></span>
    -   <span data-ttu-id="03240-110">Se si prevede di utilizzare i giornali di registrazione pagamenti, è necessario prima configurarli.</span><span class="sxs-lookup"><span data-stu-id="03240-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="03240-111">Se si prevede di eseguire le rettifiche tasso di cambio, impostare i codici valuta nella pagina Valute, i tipi di tasso di cambio nella pagina Tipi di tasso di cambio e i tassi di cambio valutario di impostazione nella pagina Tassi di cambio valutario.</span><span class="sxs-lookup"><span data-stu-id="03240-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="03240-112">In Gestione cassa e banche impostare i conti bancari da utilizzare con i metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="03240-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="03240-113">Pagine di impostazione per la contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="03240-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="03240-114">Utilizzare le pagina descritte di seguito per impostare le funzionalità di base della contabilità fornitori per ogni persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="03240-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="03240-115">Le pagine sono elencate nell'ordine di impostazione consigliato.</span><span class="sxs-lookup"><span data-stu-id="03240-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="03240-116">Per semplificare il processo di impostazione, è possibile creare modelli in base ai primi record creati.</span><span class="sxs-lookup"><span data-stu-id="03240-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="03240-117">In un modello i valori sono in genere immessi in base alle funzionalità che l'organizzazione desidera implementare per un particolare tipo di fornitore.</span><span class="sxs-lookup"><span data-stu-id="03240-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="03240-118">Nella pagina Termini di pagamento definire i termini di pagamento che si assegnano a ordini cliente, ordini fornitore, clienti e fornitori e che determinano le date di scadenza delle fatture.</span><span class="sxs-lookup"><span data-stu-id="03240-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="03240-119">Per ulteriori informazioni, vedere [Definire le commissioni di pagamento fornitore](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="03240-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="03240-120">Nella pagina Metodi di pagamento - Fornitori creare e gestire le informazioni sui metodi utilizzati dall'organizzazione per il pagamento dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="03240-121">Nella pagina Gruppi di fornitori creare e gestire i gruppi di fornitori che condividono parametri importanti per la registrazione, la liquidazione, il pagamento, il reporting e le previsioni.</span><span class="sxs-lookup"><span data-stu-id="03240-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="03240-122">Nella pagina Profili registrazione fornitori definire come registrare le transazioni fornitore nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="03240-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="03240-123">Nella pagina Parametri contabilità fornitori configurare le impostazioni predefinite che verranno applicate se non è definita un'impostazione più specifica, i parametri per vari tipi di funzionalità e varie sequenze numeriche per la contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="03240-124">Nella pagina Impostazione moduli definire il formato di vari documenti correlati ai fornitori e utilizzati all'interno dell'organizzazione per tenere traccia dei ricevimenti dai fornitori e per specificare i motivi del flusso di pagamenti a favore dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="03240-125">Nella pagina Fornitori creare e gestire i conti fornitore e gli uffici tributari a cui devono essere inviati i report IVA dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03240-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="03240-126">Pagine di impostazione facoltative per la contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="03240-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="03240-127">Oltre alla funzionalità di base, la contabilità fornitori ha altre funzionalità da impostare.</span><span class="sxs-lookup"><span data-stu-id="03240-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="03240-128">Le pagine di impostazione aggiuntive sono organizzate per funzionalità.</span><span class="sxs-lookup"><span data-stu-id="03240-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="03240-129">**Criteri**</span><span class="sxs-lookup"><span data-stu-id="03240-129">**Policies**</span></span>
-   <span data-ttu-id="03240-130">Nella pagina Criteri fattura fornitore, impostare i criteri fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="03240-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="03240-131">**Abbinamento fatture**</span><span class="sxs-lookup"><span data-stu-id="03240-131">**Invoice matching**</span></span>

-   <span data-ttu-id="03240-132">Nella pagina Tolleranze totali fatture, impostare le tolleranze per i totali fattura.</span><span class="sxs-lookup"><span data-stu-id="03240-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="03240-133">Nella pagina Criteri di abbinamento, impostare i criteri di abbinamento a due elementi di verifica e a tre elementi di verifica.</span><span class="sxs-lookup"><span data-stu-id="03240-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="03240-134">Nella pagina Tolleranze prezzi, impostare le tolleranze per i prezzi unitari.</span><span class="sxs-lookup"><span data-stu-id="03240-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="03240-135">Nella pagina Gruppi di controllo tolleranza prezzi articolo impostare i gruppi di controllo tolleranza per prezzi articolo.</span><span class="sxs-lookup"><span data-stu-id="03240-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="03240-136">Nella pagina Gruppi di controllo tolleranza prezzi fornitore impostare i gruppi di controllo tolleranza per prezzi fornitore.</span><span class="sxs-lookup"><span data-stu-id="03240-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="03240-137">Nella pagina Tolleranze spese, impostare le tolleranze per le spese.</span><span class="sxs-lookup"><span data-stu-id="03240-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="03240-138">**Flusso di lavoro**</span><span class="sxs-lookup"><span data-stu-id="03240-138">**Workflow**</span></span>

-   <span data-ttu-id="03240-139">Nella pagina Flussi di lavoro contabilità fornitori impostare configurazioni di flusso di lavoro per l'approvazione dei giornali di registrazione e per le richieste di acquisto.</span><span class="sxs-lookup"><span data-stu-id="03240-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="03240-140">**Motivi**</span><span class="sxs-lookup"><span data-stu-id="03240-140">**Reasons**</span></span>

-   <span data-ttu-id="03240-141">Nella pagina Motivi fornitore, impostare i codici motivo.</span><span class="sxs-lookup"><span data-stu-id="03240-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="03240-142">**Spese**</span><span class="sxs-lookup"><span data-stu-id="03240-142">**Charges**</span></span>

-   <span data-ttu-id="03240-143">Nella pagina Codice spese, impostare i codici per le spese utilizzate negli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="03240-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="03240-144">Nella pagina Gruppo di addebiti fornitore creare e gestire gruppi di spese per i fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="03240-145">Nella pagina Gruppi di addebito articoli  creare e gestire i gruppi di spese per gli articoli.</span><span class="sxs-lookup"><span data-stu-id="03240-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="03240-146">Nella pagina Spese automatiche , definire le spese assegnate automaticamente agli ordini.</span><span class="sxs-lookup"><span data-stu-id="03240-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="03240-147">**Articoli supplementari**</span><span class="sxs-lookup"><span data-stu-id="03240-147">**Supplementary items**</span></span>

-   <span data-ttu-id="03240-148">Nella pagina Gruppi di articoli supplementari - Fornitore , creare e gestire gruppi di articoli supplementari per i fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="03240-149">Nella pagina Gruppi di articoli supplementari - Magazzino creare e gestire gruppi di articoli supplementari per gli articoli.</span><span class="sxs-lookup"><span data-stu-id="03240-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="03240-150">**Distribuzione**</span><span class="sxs-lookup"><span data-stu-id="03240-150">**Distribution**</span></span>

-   <span data-ttu-id="03240-151">Nella pagina Termini di consegna, creare e gestire le condizioni per il trasferimento di un articolo dal venditore all'acquirente.</span><span class="sxs-lookup"><span data-stu-id="03240-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="03240-152">Nella pagina Modi di consegna, creare e gestire il mezzo di trasporto utilizzato per la consegna di un ordine dal venditore all'acquirente.</span><span class="sxs-lookup"><span data-stu-id="03240-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="03240-153">Nella pagina Codici di destinazione, creare e gestire gli ID e le descrizioni per le destinazioni di consegna.</span><span class="sxs-lookup"><span data-stu-id="03240-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="03240-154">**Moduli**</span><span class="sxs-lookup"><span data-stu-id="03240-154">**Forms**</span></span>

-   <span data-ttu-id="03240-155">Nella pagine Note moduli, creare il testo standard visualizzato su diverse pagine.</span><span class="sxs-lookup"><span data-stu-id="03240-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="03240-156">Nella pagina Parametri di ordinamento moduli, impostare i criteri di ordinamento per le richieste di approvvigionamento, gli elenchi entrate, i documenti di trasporto e le fatture.</span><span class="sxs-lookup"><span data-stu-id="03240-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="03240-157">Nella pagina Impostazione Gestione stampa impostare informazioni di gestione stampa per gli originali e le copie delle pagine.</span><span class="sxs-lookup"><span data-stu-id="03240-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="03240-158">**Pagamenti**</span><span class="sxs-lookup"><span data-stu-id="03240-158">**Payments**</span></span>

-   <span data-ttu-id="03240-159">Nella pagina Sconti di cassa, impostare e gestire le condizioni per ottenere sconti di cassa.</span><span class="sxs-lookup"><span data-stu-id="03240-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="03240-160">I codici sconto di cassa vengono collegati ai fornitori e applicati ai rispettivi ordini.</span><span class="sxs-lookup"><span data-stu-id="03240-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="03240-161">Nella pagina Scadenzari pagamenti, impostare gli scadenzari pagamenti utilizzati per gestire i pagamenti rateali ai fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="03240-162">Nella pagina Giorni di pagamento, definire i giorni di pagamento utilizzati per il calcolo delle date di scadenza e impostare un giorno specifico della settimana e del mese.</span><span class="sxs-lookup"><span data-stu-id="03240-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="03240-163">Nella pagina Commissione pagamento creare e gestire le commissioni di pagamento associate ai fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="03240-164">Nella pagina Istruzione di pagamento, creare e gestire le istruzioni di pagamento.</span><span class="sxs-lookup"><span data-stu-id="03240-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="03240-165">**Statistiche**</span><span class="sxs-lookup"><span data-stu-id="03240-165">**Statistics**</span></span>

-   <span data-ttu-id="03240-166">Nella pagina Definizioni periodo di aging, impostare intervalli definiti dall'utente utilizzati per analizzare la distribuzione delle scadenze dei conti fornitore.</span><span class="sxs-lookup"><span data-stu-id="03240-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="03240-167">Nella pagina Linea di business creare i codici della linea di business (LOB) assegnati ai fornitori.</span><span class="sxs-lookup"><span data-stu-id="03240-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="03240-168">**Imposta 1099**</span><span class="sxs-lookup"><span data-stu-id="03240-168">**Tax 1099**</span></span>

-   <span data-ttu-id="03240-169">Nella pagina **Campi 1099**, verificare e aggiornare gli importi minimi che devono essere dichiarati in IRS (Internal Revenue Service), in base ai più recenti requisiti IRS.</span><span class="sxs-lookup"><span data-stu-id="03240-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="03240-170">**Impostazione facoltativa per altri moduli**</span><span class="sxs-lookup"><span data-stu-id="03240-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="03240-171">**Amministrazione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="03240-171">**Organization administration**</span></span>

-   <span data-ttu-id="03240-172">Nella pagina Sequenze numeriche, impostare i gruppi di sequenze numeriche per i numeri di fattura.</span><span class="sxs-lookup"><span data-stu-id="03240-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="03240-173">Nelle seguenti pagine impostare le informazioni relative all'indirizzo:</span><span class="sxs-lookup"><span data-stu-id="03240-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="03240-174">Impostazione indirizzo</span><span class="sxs-lookup"><span data-stu-id="03240-174">Address setup</span></span>
    -   <span data-ttu-id="03240-175">Codici NAF</span><span class="sxs-lookup"><span data-stu-id="03240-175">NAF codes</span></span>
    -   <span data-ttu-id="03240-176">Importa codici postali (CAP)</span><span class="sxs-lookup"><span data-stu-id="03240-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="03240-177">**Contabilità generale**</span><span class="sxs-lookup"><span data-stu-id="03240-177">**General ledger**</span></span>

-   <span data-ttu-id="03240-178">Nella pagina Dimensioni finanziarie impostare le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="03240-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="03240-179">Nelle seguenti pagine impostare le informazioni sulle imposte:</span><span class="sxs-lookup"><span data-stu-id="03240-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="03240-180">Codici IVA</span><span class="sxs-lookup"><span data-stu-id="03240-180">Sales tax codes</span></span>
    -   <span data-ttu-id="03240-181">Fasce IVA</span><span class="sxs-lookup"><span data-stu-id="03240-181">Sales tax groups</span></span>
    -   <span data-ttu-id="03240-182">Fasce IVA articoli</span><span class="sxs-lookup"><span data-stu-id="03240-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="03240-183">Gruppo di conti</span><span class="sxs-lookup"><span data-stu-id="03240-183">Account group</span></span>
    -   <span data-ttu-id="03240-184">Codici di esenzione IVA</span><span class="sxs-lookup"><span data-stu-id="03240-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="03240-185">Uffici IVA competenti</span><span class="sxs-lookup"><span data-stu-id="03240-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="03240-186">Uffici IVA</span><span class="sxs-lookup"><span data-stu-id="03240-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="03240-187">Periodi liquidazione IVA</span><span class="sxs-lookup"><span data-stu-id="03240-187">Sales tax settlement periods</span></span>

<span data-ttu-id="03240-188">**Gestione cassa e banche**</span><span class="sxs-lookup"><span data-stu-id="03240-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="03240-189">Nella pagina Codici scopo pagamento impostare il codice di scopo pagamento della banca centrale.</span><span class="sxs-lookup"><span data-stu-id="03240-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>





