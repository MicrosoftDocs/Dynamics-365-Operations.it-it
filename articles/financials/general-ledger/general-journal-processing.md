---
title: Elaborazione giornale di registrazione generale
description: "Questo articolo descrive le funzionalità di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition che possono contribuire a rendere l'elaborazione del giornale di registrazione generale più semplice e che possono inoltre garantire che i dati corretti siano acquisiti e il controllo interno non sia compromesso."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 76386f7ab8033075f9db4cadc697f3a2a997163e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="general-journal-processing"></a><span data-ttu-id="aba29-103">Elaborazione giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="aba29-103">General journal processing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="aba29-104">Questo articolo descrive le funzionalità di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition che possono contribuire a rendere l'elaborazione del giornale di registrazione generale più semplice e che possono inoltre garantire che i dati corretti siano acquisiti e il controllo interno non sia compromesso.</span><span class="sxs-lookup"><span data-stu-id="aba29-104">This articles describes capabilities in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition that can help make general journal processing easier, and that can also help guarantee that correct data is captured and internal control isn't compromised.</span></span>  

<span data-ttu-id="aba29-105">Nomi giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="aba29-105">Journal names</span></span>

<span data-ttu-id="aba29-106">Una delle aree più importanti da configurare è i nomi di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aba29-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="aba29-107">È consigliabile definire nomi di giornali di registrazione specifici per ogni scopo, ad esempio interaziendale, rettifica ratei e correttivo.</span><span class="sxs-lookup"><span data-stu-id="aba29-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="aba29-108">È possibile personalizzare ciascun nome di giornale di registrazione per rendere semplice e sicura l'immissione dei dati per ogni scopo.</span><span class="sxs-lookup"><span data-stu-id="aba29-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="aba29-109">Nella pagina **Nomi giornale di registrazione** è possibile impostare i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="aba29-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="aba29-110">**Approvazione flusso di lavoro** – Per aumentare il controllo interno, definire flussi di lavoro del giornale di registrazione che stabiliscono i limiti di materialità per i passaggi di revisione e approvazione, in base a criteri quali l'importo totale in Dare.</span><span class="sxs-lookup"><span data-stu-id="aba29-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="aba29-111">Vengono impostati flussi di lavoro per i giornali di registrazione generali nella pagina **Flussi di lavoro contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="aba29-111">You set up workflows for the general journals on the** General ledger workflows** page.</span></span>
-   <span data-ttu-id="aba29-112">**Valori predefiniti** - Selezionare valori predefiniti per i conti di contropartita, la valuta e le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="aba29-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="aba29-113">**Controllo giornale di registrazione** - È possibile impostare restrizioni sul tipo di società e di conto e anche sui valori segmento.</span><span class="sxs-lookup"><span data-stu-id="aba29-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="aba29-114">**Esempi**</span><span class="sxs-lookup"><span data-stu-id="aba29-114">**Examples**</span></span>

<span data-ttu-id="aba29-115">Un nome di giornale di registrazione può essere utilizzato solo per le rettifiche.</span><span class="sxs-lookup"><span data-stu-id="aba29-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="aba29-116">In questo caso, è possibile specificare che solo il tipo di conto **Contabilità generale** è valido per tutte le società.</span><span class="sxs-lookup"><span data-stu-id="aba29-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> <span data-ttu-id="aba29-117">[![Tipi di conto di controllo giornale di registrazione](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="aba29-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="aba29-118">Un nome di giornale di registrazione può essere utilizzato solo per un segmento specifico o per un intervallo di conti principali.</span><span class="sxs-lookup"><span data-stu-id="aba29-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> <span data-ttu-id="aba29-119">[![Segmento controllo giornale di registrazione](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="aba29-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="aba29-120">L'opzione **Storno automatico** è disponibile nei giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="aba29-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="aba29-121">Ad esempio, si dispone di una rettifica di attribuzione per competenza in cui il documento effettivo non è ancora stato elaborato, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="aba29-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="aba29-122">[![Storno giornale di registrazione generale](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="aba29-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="aba29-123">Il componente aggiuntivo di Microsoft Excel per le scritture contabili fornisce un ulteriore livello di automazione e rende l'immissione di dati più semplice.</span><span class="sxs-lookup"><span data-stu-id="aba29-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="aba29-124">L'azione **Apri righe in Excel** è disponibile nelle pagine **Giornale di registrazione generale** e **Giustificativo giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="aba29-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="aba29-125">Nella pagina **Giornali di registrazione periodici** è possibile impostare i giornali ricorrenti per automatizzare l'elaborazione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aba29-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="aba29-126">È possibile utilizzare in qualsiasi momento modelli di giustificativo.</span><span class="sxs-lookup"><span data-stu-id="aba29-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="aba29-127">Nella pagina **Giornali di registrazione generali** le azioni **Salva** e **Seleziona modello giustificativo** si trovano nella pagina **Giustificativo giornale di registrazione**, sotto **Funzioni** per le righe del giustificativo.</span><span class="sxs-lookup"><span data-stu-id="aba29-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="aba29-128">Impostazione correlata</span><span class="sxs-lookup"><span data-stu-id="aba29-128">Related setup</span></span>
<span data-ttu-id="aba29-129">La seguente impostazione non è specifica dei giornali di registrazione generali, ma contribuirà a garantire che l'immissione di dati sia semplice e corretta.</span><span class="sxs-lookup"><span data-stu-id="aba29-129">The following setup isn't specific to general journals, but will help guarantee that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="aba29-130">Conto principale</span><span class="sxs-lookup"><span data-stu-id="aba29-130">Main account</span></span>

<span data-ttu-id="aba29-131">L'impostazione del conto principale offre numerose opzioni per l'elaborazione dei giornali di registrazione generali:</span><span class="sxs-lookup"><span data-stu-id="aba29-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="aba29-132">**Fabbisogno di DB/CR** - Utilizzare questa opzione se un conto principale è limitato alle transazioni in dare o in avere.</span><span class="sxs-lookup"><span data-stu-id="aba29-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="aba29-133">L'impostazione è verificata quando un giornale di registrazione viene convalidato o registrato.</span><span class="sxs-lookup"><span data-stu-id="aba29-133">The setup is verified when a journal is validated or posted.</span></span>
-   <span data-ttu-id="aba29-134">**Conto di contropartita predefinito**</span><span class="sxs-lookup"><span data-stu-id="aba29-134">**Default offset account**</span></span>
-   <span data-ttu-id="aba29-135">**Sospeso** - Consente di sospendere un conto principale per l'immissione di dati per tutte le società o per una società/persona giuridica specifica.</span><span class="sxs-lookup"><span data-stu-id="aba29-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entities.</span></span>
-   <span data-ttu-id="aba29-136">**Non consentire immissione manuale** - Impedisce agli utenti di immettere manualmente un valore per il conto nei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aba29-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="aba29-137">**Valuta predefinita/Convalida valuta**</span><span class="sxs-lookup"><span data-stu-id="aba29-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="aba29-138">**Sostituzioni persona giuridica** - Questa impostazione è specifica per la società/persona giuridica definita:</span><span class="sxs-lookup"><span data-stu-id="aba29-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="aba29-139">**IVA predefinita/Convalida IVA**</span><span class="sxs-lookup"><span data-stu-id="aba29-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="aba29-140">**Dimensione predefinita** – **Non fissa** o **Valore fisso**.</span><span class="sxs-lookup"><span data-stu-id="aba29-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="aba29-141">**Valore fisso** contribuirà a garantire che tutte le registrazioni per il conto principale utilizzano sempre qualsiasi valore di dimensione impostato come **Fisso**.</span><span class="sxs-lookup"><span data-stu-id="aba29-141">**Fixed value** will help guarantee that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="aba29-142">**Convalida di registrazione**</span><span class="sxs-lookup"><span data-stu-id="aba29-142">**Posting validation**</span></span>
    -   <span data-ttu-id="aba29-143">**Convalida utente** - Questa opzione consente di controllare a quali utenti è consentito registrare in un conto principale.</span><span class="sxs-lookup"><span data-stu-id="aba29-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="aba29-144">**Convalida tipo di registrazione** - Questa opzione consente di controllare quali tipi di registrazione sono consentiti in un conto principale.</span><span class="sxs-lookup"><span data-stu-id="aba29-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="aba29-145">Strutture di contabilità e delle regole avanzate</span><span class="sxs-lookup"><span data-stu-id="aba29-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="aba29-146">Le strutture di contabilità e delle regole avanzate sono estremamente importanti per garantire che i dati necessari per i report finanziari e il monitoraggio delle prestazioni vengano acquisiti durante l'elaborazione del giornale di registrazione generale e in qualsiasi documentazione.</span><span class="sxs-lookup"><span data-stu-id="aba29-146">Accounting structures and advanced rules structures are extremely important for guaranteeing that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="aba29-147">Le strutture di contabilità e delle regole avanzate consentono di personalizzare l'esperienza dell'immissione dati.</span><span class="sxs-lookup"><span data-stu-id="aba29-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="aba29-148">È possibile consentire l'immissione di dati solo per le dimensioni finanziarie pertinenti in ogni situazione e è inoltre possibile applicare la condizione che vengano sempre acquisiti i dati obbligatori e corretti.</span><span class="sxs-lookup"><span data-stu-id="aba29-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that mandatory and correct data always be captured.</span></span>

<span data-ttu-id="aba29-149">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="aba29-149">For more information, see the following topics:</span></span>
- <span data-ttu-id="aba29-150">[Pianificazione: piano dei conti](plan-chart-of-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="aba29-150">[Planning: Chart of accounts](plan-chart-of-accounts.md).</span></span> 
- [<span data-ttu-id="aba29-151">Creare regole avanzate per giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="aba29-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="aba29-152">Creare una scrittura contabile utilizzando un modello</span><span class="sxs-lookup"><span data-stu-id="aba29-152">Create a journal entry using a template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="aba29-153">Creare e convalidare giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="aba29-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="aba29-154">Registrare giornali periodici</span><span class="sxs-lookup"><span data-stu-id="aba29-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="aba29-155">Elaborare giornale di registrazione allocazioni contabili</span><span class="sxs-lookup"><span data-stu-id="aba29-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)



