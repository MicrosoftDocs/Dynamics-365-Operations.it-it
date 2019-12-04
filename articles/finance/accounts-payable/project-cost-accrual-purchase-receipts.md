---
title: Attribuzione dei costi per progetto nelle entrate acquisti
description: In questo argomento viene descritto come i ratei e risconti passivi di progetto provenienti dalle entrate di acquisto possono essere tracciati in Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0a930b4921a29d5ce561ce0e958733f0c3261b81
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772193"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="3ba9d-103">Attribuzione dei costi per progetto nelle entrate acquisti</span><span class="sxs-lookup"><span data-stu-id="3ba9d-103">Project cost accrual on purchase receipts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3ba9d-104">In questo argomento viene descritto come i ratei e risconti passivi di progetto provenienti dalle entrate di acquisto possono essere tracciati in Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 Finance.</span></span> 

<span data-ttu-id="3ba9d-105">Le fatture per un progetto spesso arrivano dopo la consegna di merci e servizi, aspetto che potrebbe avere un impatto significativo sugli indicatori di prestazione chiave (KPI) del progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="3ba9d-106">È importante poter tenere traccia di queste transazioni sia nei report finanziari che in quelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="3ba9d-107">Nel seguente scenario di esempio viene illustrato questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="3ba9d-108">Contoso Consulting ha avviato un nuovo progetto di distribuzione cloud.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="3ba9d-109">Un ordine fornitore viene creato per acquistare un computer per il progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="3ba9d-110">Il computer costerà $ 1.500 e i servizi di installazione costeranno $ 150.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="3ba9d-111">Il fornitore ha consegnato e installato il computer ma Contoso Consulting non ha ancora ricevuto la fattura.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="3ba9d-112">Il manager di progetto desidera esaminare l'attribuzione dei costi per il progetto di $ 1.650 prima che la fattura venga consegnata.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="3ba9d-113">Questi costi devono essere riportati anche nei rendiconti finanziari di fine mese della società.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="3ba9d-114">I ratei e risconti passivi devono essere registrati sia a livello finanziario che a quello di progetto a scopo di reporting.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="3ba9d-115">L'aggiornamento finanziario dell'entrata prodotti può essere tracciato per l'articoloo e le categorie di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-115">The financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="3ba9d-116">Per gli articoli, nella pagina **Parametri contabilità fornitori**, selezionare l'opzione **Registra entrate prodotti nella contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="3ba9d-117">[![Pagina Parametri contabilità fornitori](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-117">[![Accounts payable parameters page](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="3ba9d-118">Per le categorie di approvvigionamento, nella pagina **Regola dei criteri categorie**, selezionare i criteri **Acquisto**, quindi selezionare **Accumula spese su acquisti in entrata** per ciascuna categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="3ba9d-119">[![Pagina Regola dei criteri categorie](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-119">[![Category policy rule page](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="3ba9d-120">I conti **Spese acquisto non fatturate** e **Competenza acquisti** in **Impostazione di registrazione** verranno utilizzati quando i giustificativi correlati all'entrata prodotti vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>

<span data-ttu-id="3ba9d-121">Utilizzando questo stesso scenario, esaminiamo come la registrazione di un'entrata prodotti influirà sulla contabilità generale e sulle informazioni relative al progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-121">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="3ba9d-122">**Passaggio 1:** creare e confermare un nuovo ordine fornitore per il progetto per registrare l'acquisto di un computer per $ 1.500 e i servizi di installazione pari a $ 150.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-122">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="3ba9d-123">[![Creare un nuovo ordine fornitore](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-123">[![Create new purchase order](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="3ba9d-124">Quando l'ordine fornitore viene confermato, le transazioni del costo impegnato vengono create per il progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-124">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="3ba9d-125">[![Transazioni create](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-125">[![Transactions created](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="3ba9d-126">Le transazioni per il costo impegnato avranno il campo **Origine transazione** impostato su **Ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-126">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="3ba9d-127">La creazione e la conferma di un ordine fornitore non creano transazioni per un progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-127">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="3ba9d-128">**Passaggio 2:** le merci e i servizi vengono consegnati e un'entrata prodotti è registrata.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-128">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="3ba9d-129">La registrazione di un'entrata prodotti genera e registra un giustificativo nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-129">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="3ba9d-130">Il giustificativo addebiterà le spese di acquisto non fatturate e accrediterà il conto ratei di acquisto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-130">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="3ba9d-131">[![Transazioni giustificativo](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-131">[![Voucher transactions](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="3ba9d-132">La registrazione di un'entrata prodotti utilizzerà l'impostazione di registrazione per i prodotti e le categorie di approvvigionamento e non l'impostazione di registrazione per le categorie di progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-132">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="3ba9d-133">Per riflettere correttamente l'impatto finanziario dei ratei di acquisto, questa impostazione deve essere allineata.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-133">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="3ba9d-134">È possibile mappare le categorie di approvvigionamento alle categorie di progetto nella pagina **Categoria di approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-134">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="3ba9d-135">[![Pagina Categoria di approvvigionamento](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-135">[![Procurement category page](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="3ba9d-136">**Passaggio 3:** creare una bozza della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-136">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="3ba9d-137">La registrazione di un'entrata prodotti non influisce sulle informazioni relative al progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-137">Posting a product receipt does not impact project information.</span></span> <span data-ttu-id="3ba9d-138">Come soluzione alternativa, è possibile generare una bozza della fattura fornitore subito aver registrato l'entrata acquisti.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-138">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="3ba9d-139">Passare alla pagina **Ordine fornitore** &gt; **scheda Fattura** &gt; **Genera** &gt; **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-139">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="3ba9d-140">Verrà creato un documento di fattura in sospeso che aggiorna le informazioni sul progetto.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-140">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="3ba9d-141">La creazione di una bozza di fattura fornitore genera transazioni di progetto in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-141">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="3ba9d-142">[![Transazioni progetto in sospeso](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-142">[![Pending project transactions](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="3ba9d-143">Nella pagina **Costo impegnato**, i record creati nel passaggio 1 verranno chiusi e nuovi record verranno creati per riflettere gli impegni di costo derivanti dalla fattura fornitore in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-143">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="3ba9d-144">Il campo **Origine transazione** per il costo impegnato verrà impostato su **Fattura fornitore**.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-144">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="3ba9d-145">[![Pagina Costi impegnati](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="3ba9d-145">[![Commited costs page](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="3ba9d-146">La fattura fornitore rimane con stato in sospeso finché non arriva la fattura fornitore effettiva.</span><span class="sxs-lookup"><span data-stu-id="3ba9d-146">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>



