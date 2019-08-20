---
title: Area di lavoro gestione banche
description: Vengono fornite le informazioni sull'area di lavoro gestione banche. In quest'area di lavoro vengono visualizzate le informazioni relative ai conti bancari della società e comprende una visualizzazione di riepilogo e una pagina di analisi. Nella visualizzazione di riepilogo vengono visualizzati i riquadri di riepilogo, le informazioni sul conto bancario, un grafico del saldo e informazioni correlate. La pagina dell'analisi dei dati utilizza le funzionalità di Microsoft Power BI per visualizzare le rappresentazioni correlate ai saldi del conto bancario.
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 20847ea4651b816fc95135ca03667ae297cde5be
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842739"
---
# <a name="bank-management-workspace"></a><span data-ttu-id="59b7d-106">Area di lavoro gestione banche</span><span class="sxs-lookup"><span data-stu-id="59b7d-106">Bank management workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59b7d-107">Nell'area di lavoro **Gestione banche** vengono visualizzate le informazioni relative ai conti bancari della società.</span><span class="sxs-lookup"><span data-stu-id="59b7d-107">The **Bank management** workspace shows information that is related to company bank accounts.</span></span> <span data-ttu-id="59b7d-108">Questa area di lavoro include una visualizzazione **Riepilogo** e una pagina **Analisi**.</span><span class="sxs-lookup"><span data-stu-id="59b7d-108">This workspace includes a **Summary** view and an **Analytics** page.</span></span> <span data-ttu-id="59b7d-109">Nella visualizzazione **Riepilogo** vengono visualizzati i riquadri di riepilogo, le informazioni sul conto bancario, un grafico del saldo e informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="59b7d-109">The **Summary** view shows summary tiles, bank account information, a balance chart, and related information.</span></span> <span data-ttu-id="59b7d-110">La pagina dell'**analisi** dei dati utilizza le funzionalità di Microsoft Power BI per visualizzare le rappresentazioni correlate ai saldi del conto bancario.</span><span class="sxs-lookup"><span data-stu-id="59b7d-110">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to bank account balances.</span></span>

## <a name="summary-view"></a><span data-ttu-id="59b7d-111">Visualizzazione di riepilogo</span><span class="sxs-lookup"><span data-stu-id="59b7d-111">Summary view</span></span>

### <a name="summary"></a><span data-ttu-id="59b7d-112">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="59b7d-112">Summary</span></span>

<span data-ttu-id="59b7d-113">Nei riquadri della sezione **Riepilogo** viene fornita una panoramica dei conti bancari e l'accesso rapido alle pagine usate più di frequente.</span><span class="sxs-lookup"><span data-stu-id="59b7d-113">The tiles in the **Summary** section give an overview of your bank accounts and provide quick access to the pages that you most often have to use.</span></span> <span data-ttu-id="59b7d-114">Le informazioni di riconciliazione estratti conto sono specifiche della funzionalità avanzata di riconciliazione estratti conto.</span><span class="sxs-lookup"><span data-stu-id="59b7d-114">The bank reconciliation information is specific to the Advanced bank reconciliation functionality.</span></span> <span data-ttu-id="59b7d-115">Vengono incluse solo le informazioni per i conti bancari con l'opzione **Riconciliazione estratti conto avanzata** impostata su **Sì** nella pagina **Conto bancario**.</span><span class="sxs-lookup"><span data-stu-id="59b7d-115">Information is included only for those bank accounts that have the **Advanced bank reconciliation** option set to **Yes** on the **Bank account** page.</span></span> <span data-ttu-id="59b7d-116">Nella sezione **Riepilogo** è possibile importare i file bancari elettronici per i conti bancari di tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="59b7d-116">From the **Summary** section, you can import electronic bank files for bank accounts across all legal entities.</span></span>

### <a name="bank-accounts"></a><span data-ttu-id="59b7d-117">Conti bancari</span><span class="sxs-lookup"><span data-stu-id="59b7d-117">Bank accounts</span></span>

<span data-ttu-id="59b7d-118">Ciascun conto bancario della persona giuridica è rappresentato da una scheda nella sezione **Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="59b7d-118">Each bank account in the legal entity is represented by a card in the **Bank accounts** section.</span></span> <span data-ttu-id="59b7d-119">Viene visualizzato il saldo corrente ed è possibile eseguire il drill-down delle transazioni che costituiscono l'importo del saldo riepilogativo.</span><span class="sxs-lookup"><span data-stu-id="59b7d-119">The current balance is shown, and you can drill down to the transactions that make up that summary balance amount.</span></span> <span data-ttu-id="59b7d-120">Anche l'importo **Transazioni provvisorie** consente di eseguire il drill-down delle transazioni che costituiscono l'importo riepilogativo.</span><span class="sxs-lookup"><span data-stu-id="59b7d-120">The **Bridged transactions** amount also lets you drill down to the transactions that make up that summary amount.</span></span> <span data-ttu-id="59b7d-121">Le transazioni provvisorie sono tutte le transazioni in sospeso che sono state registrate utilizzando la funzionalità di registrazione provvisoria ma che non sono state cancellate.</span><span class="sxs-lookup"><span data-stu-id="59b7d-121">Bridged transactions are any pending transactions that have been posted by using bridging functionality, but that haven't yet been cleared.</span></span> <span data-ttu-id="59b7d-122">L'importo **Saldo in sospeso** è il saldo corrente meno le transazioni provvisorie o in sospeso.</span><span class="sxs-lookup"><span data-stu-id="59b7d-122">The **Pending balance** amount is the current balance minus the bridged, or pending, transactions.</span></span>

<span data-ttu-id="59b7d-123">Nella scheda viene visualizzato anche la data dell'ultima riconciliazione del conto bancario.</span><span class="sxs-lookup"><span data-stu-id="59b7d-123">The card also shows when the bank account was last reconciled.</span></span> <span data-ttu-id="59b7d-124">Queste informazioni vengono visualizzate solo se la riconciliazione degli estratti conto avanzata è attivata per il conto bancario.</span><span class="sxs-lookup"><span data-stu-id="59b7d-124">This information is shown only if Advanced bank reconciliation is enabled for the bank account.</span></span>

### <a name="balance"></a><span data-ttu-id="59b7d-125">Stato patrimoniale</span><span class="sxs-lookup"><span data-stu-id="59b7d-125">Balance</span></span>

<span data-ttu-id="59b7d-126">Nel grafico **Saldo** vengono visualizzati i dati storici del saldo del conto bancario selezionato nella sezione **Conti bancari** o un riepilogo dei dati storici del saldo per tutti i conti bancari della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="59b7d-126">The **Balance** chart shows either historic balance information for the bank account that is selected in the **Bank accounts** section or a summary of historic balance information for all bank accounts in the legal entity.</span></span> <span data-ttu-id="59b7d-127">Questi dati sono disponibili per diversi periodi: la settimana corrente, il mese corrente, l'anno corrente, gli ultimi cinque anni e tutti i periodi (lo storico completo del conto bancario).</span><span class="sxs-lookup"><span data-stu-id="59b7d-127">This information is available for various periods: the current week, the current month, the current year, the last five years, and all periods (the full history of the bank account).</span></span> 

<span data-ttu-id="59b7d-128">Se si visualizza il grafico **Saldo** per un singolo conto bancario, i dati storici dei saldi verranno visualizzati nella valuta del conto bancario.</span><span class="sxs-lookup"><span data-stu-id="59b7d-128">If you're viewing the **Balance** chart for a single bank account, the historic balances are shown in the bank account currency.</span></span> <span data-ttu-id="59b7d-129">Se si visualizza il grafico per tutti i conti bancari della persona giuridica, i dati storici dei saldi verranno visualizzati nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="59b7d-129">If you're viewing the chart for all bank accounts in the legal entity, the historic balances are shown in the accounting currency.</span></span>

<span data-ttu-id="59b7d-130">Le informazioni relative alla data dell'ultimo aggiornamento dei dati sono visualizzate nella parte superiore del grafico.</span><span class="sxs-lookup"><span data-stu-id="59b7d-130">Information about when the data was last updated appears at the top of the chart.</span></span> <span data-ttu-id="59b7d-131">È possibile aggiornare i dati secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="59b7d-131">You can update the data as you require.</span></span>

### <a name="related-information"></a><span data-ttu-id="59b7d-132">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="59b7d-132">Related information</span></span>

<span data-ttu-id="59b7d-133">Nella sezione **Informazioni correlate**, è possibile aprire la pagina **Giornale di registrazione generale** per completare i trasferimenti bancari.</span><span class="sxs-lookup"><span data-stu-id="59b7d-133">From the **Related information** section, you can open the **General journal** page to complete bank transfers.</span></span> <span data-ttu-id="59b7d-134">È inoltre possibile aprire rapidamente le pagine **Transazioni provvisorie** e **Transazioni bancarie**.</span><span class="sxs-lookup"><span data-stu-id="59b7d-134">You can also quickly open the **Bank transactions** and **Bridged transactions** pages.</span></span>

## <a name="analytics-view"></a><span data-ttu-id="59b7d-135">Visualizzazione Analisi</span><span class="sxs-lookup"><span data-stu-id="59b7d-135">Analytics view</span></span>

<span data-ttu-id="59b7d-136">La pagina **Analisi** mostra le metriche importanti dei conti bancari della società corrente.</span><span class="sxs-lookup"><span data-stu-id="59b7d-136">The **Analytics** page provides important metrics about the bank accounts in the current company.</span></span> <span data-ttu-id="59b7d-137">Le visualizzazioni riportate di seguito sono disponibili nella pagina:</span><span class="sxs-lookup"><span data-stu-id="59b7d-137">The following visualizations are available on the page:</span></span>

-   <span data-ttu-id="59b7d-138">Saldo bancario totale nella valuta di sistema</span><span class="sxs-lookup"><span data-stu-id="59b7d-138">Total bank balance in system currency</span></span>
-   <span data-ttu-id="59b7d-139">Saldo per persona giuridica</span><span class="sxs-lookup"><span data-stu-id="59b7d-139">Balance by legal entity</span></span>
-   <span data-ttu-id="59b7d-140">Saldo effettivo odierno rispetto al saldo previsto nella valuta del conto bancario</span><span class="sxs-lookup"><span data-stu-id="59b7d-140">Today’s actual vs forecasted balance in bank account currency</span></span>
-   <span data-ttu-id="59b7d-141">Saldo per conto bancario</span><span class="sxs-lookup"><span data-stu-id="59b7d-141">Balance by bank account</span></span>
-   <span data-ttu-id="59b7d-142">Saldo per valuta</span><span class="sxs-lookup"><span data-stu-id="59b7d-142">Balance by currency</span></span>

<span data-ttu-id="59b7d-143">È possibile visualizzare l'analisi dei dati bancari per tutte le società dall'area di lavoro **Panoramica situazione di cassa - tutte le società**.</span><span class="sxs-lookup"><span data-stu-id="59b7d-143">You can view bank analytics across all companies from the **Cash overview – all companies** workspace.</span></span>
