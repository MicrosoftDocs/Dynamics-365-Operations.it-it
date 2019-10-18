---
title: Report finanziari del bilancio di verifica
description: In questo articolo viene descritto i report predefiniti per i bilanci di verifica. Sono descritti inoltre i blocchi predefiniti associati a questi report e come è possibile modificare i report in modo da soddisfare i requisiti aziendali.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fd4512b02070415b6228c91b66635815dbacaa2
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175485"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="09b4d-104">Report finanziari del bilancio di verifica</span><span class="sxs-lookup"><span data-stu-id="09b4d-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09b4d-105">In questo articolo viene descritto i report predefiniti per i bilanci di verifica.</span><span class="sxs-lookup"><span data-stu-id="09b4d-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="09b4d-106">Sono descritti inoltre i blocchi predefiniti associati a questi report e come è possibile modificare i report in modo da soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="09b4d-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="09b4d-107">Report predefiniti del bilancio di verifica</span><span class="sxs-lookup"><span data-stu-id="09b4d-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="09b4d-108">Tre report del bilancio di verifica sono disponibili nei report finanziari.</span><span class="sxs-lookup"><span data-stu-id="09b4d-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="09b4d-109">Report predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-109">Default report</span></span>                                 | <span data-ttu-id="09b4d-110">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="09b4d-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="09b4d-111">Bilancio di verifica dettagliato - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="09b4d-112">Fornisce informazioni sul saldo per tutti i conti e include i saldi in Avere e in Dare e l'importo netto di questi, insieme alla data della transazione, al giustificativo e alla descrizione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="09b4d-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="09b4d-113">Bilancio di verifica riepilogativo - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="09b4d-114">Fornisce informazioni sul saldo per tutti i conti e include i saldi di chiusura e di apertura e i saldi in Avere e in Dare, insieme alle differenze nette.</span><span class="sxs-lookup"><span data-stu-id="09b4d-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="09b4d-115">Bilancio di verifica riepilogativo annuale - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="09b4d-116">Fornisce informazioni sul saldo per tutti i conti e include i saldi di chiusura e di apertura e i saldi in Avere e in Dare, insieme alle differenze nette per l'anno corrente e l'anno precedente.</span><span class="sxs-lookup"><span data-stu-id="09b4d-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="09b4d-117">Blocchi predefiniti</span><span class="sxs-lookup"><span data-stu-id="09b4d-117">Building blocks</span></span>
<span data-ttu-id="09b4d-118">I report finanziari del bilancio di verifica utilizzano i seguenti blocchi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="09b4d-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="09b4d-119">Report predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-119">Default report</span></span>                                 | <span data-ttu-id="09b4d-120">Definizione riga</span><span class="sxs-lookup"><span data-stu-id="09b4d-120">Row definition</span></span>          | <span data-ttu-id="09b4d-121">Definizione colonna</span><span class="sxs-lookup"><span data-stu-id="09b4d-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="09b4d-122">Bilancio di verifica dettagliato - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="09b4d-123">Bilancio di verifica - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-123">Trial Balance - Default</span></span> | <span data-ttu-id="09b4d-124">Bilancio di verifica dettagliato - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="09b4d-125">Bilancio di verifica riepilogativo - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="09b4d-126">Bilancio di verifica - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-126">Trial Balance - Default</span></span> | <span data-ttu-id="09b4d-127">Bilancio di verifica riepilogativo - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="09b4d-128">Bilancio di verifica riepilogativo annuale - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="09b4d-129">Bilancio di verifica - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-129">Trial Balance - Default</span></span> | <span data-ttu-id="09b4d-130">Bilancio di verifica riepilogativo annuale - Predefinito</span><span class="sxs-lookup"><span data-stu-id="09b4d-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="09b4d-131">Definizione riga</span><span class="sxs-lookup"><span data-stu-id="09b4d-131">Row definition</span></span>

<span data-ttu-id="09b4d-132">La definizione di riga, Bilancio di verifica - Predefinito, contiene una singola riga che esegue il pull in tutti i conti principali.</span><span class="sxs-lookup"><span data-stu-id="09b4d-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="09b4d-133">Di conseguenza, chiunque può generare il report senza dover apportare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="09b4d-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="09b4d-134">Quando si visualizza il report, si analizza la singola riga per visualizzare i dettagli relativi a ciascun conto.</span><span class="sxs-lookup"><span data-stu-id="09b4d-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="09b4d-135">È possibile modificare la definizione di riga in modo da includere più dettagli.</span><span class="sxs-lookup"><span data-stu-id="09b4d-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="09b4d-136">Per modificare la definizione di riga Bilancio di verifica - Predefinito in modo che includa le righe per tutti i conti, attenersi ai passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="09b4d-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="09b4d-137">Fare clic su **Modifica** e quindi su **Inserisci righe da dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="09b4d-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="09b4d-138">Il comando **Inserisci righe da dimensioni** consente di scegliere le dimensioni che si desidera inserire nella definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="09b4d-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="09b4d-139">Per questa definizione di riga, si utilizza **Conto principale**.</span><span class="sxs-lookup"><span data-stu-id="09b4d-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="09b4d-140">Assicurarsi che **Conto principale** contenga tutte le e commerciali (&) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="09b4d-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="09b4d-141">La definizione di riga ora contiene tutti i conti principale per la persona giuridica predefinita.</span><span class="sxs-lookup"><span data-stu-id="09b4d-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="09b4d-142">Definizione colonna</span><span class="sxs-lookup"><span data-stu-id="09b4d-142">Column definition</span></span>

<span data-ttu-id="09b4d-143">Ogni report di bilancio di verifica utilizza una definizione di colonna diversa.</span><span class="sxs-lookup"><span data-stu-id="09b4d-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="09b4d-144">Le definizioni di colonna contengono i diversi tipi di colonna per fornire diversi livelli di dettagli e dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="09b4d-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="09b4d-145">**Bilancio di verifica dettagliato - Tipi predefiniti di colonna:**</span><span class="sxs-lookup"><span data-stu-id="09b4d-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="09b4d-146">**DESC** - Descrizione della definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="09b4d-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="09b4d-147">**ACCT** - Codici conto</span><span class="sxs-lookup"><span data-stu-id="09b4d-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="09b4d-148">**ATTR (3)** - Attributi:</span><span class="sxs-lookup"><span data-stu-id="09b4d-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="09b4d-149">Data della transazione</span><span class="sxs-lookup"><span data-stu-id="09b4d-149">Transaction Date</span></span>
        -   <span data-ttu-id="09b4d-150">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="09b4d-150">Voucher</span></span>
        -   <span data-ttu-id="09b4d-151">Descrizione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="09b4d-151">Journal Description</span></span>
    -   <span data-ttu-id="09b4d-152">**FD** I dati finanziari contenenti solo i debiti</span><span class="sxs-lookup"><span data-stu-id="09b4d-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="09b4d-153">**FD** I dati finanziari contenenti solo i crediti</span><span class="sxs-lookup"><span data-stu-id="09b4d-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="09b4d-154">**CALC** La differenza netta</span><span class="sxs-lookup"><span data-stu-id="09b4d-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="09b4d-155">**Bilancio di verifica riepilogativo - Tipi predefiniti di colonna:**</span><span class="sxs-lookup"><span data-stu-id="09b4d-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="09b4d-156">**ACCT** - Codici conto</span><span class="sxs-lookup"><span data-stu-id="09b4d-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="09b4d-157">**DESC** - Descrizione della definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="09b4d-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="09b4d-158">**ATTR** Un attributo:</span><span class="sxs-lookup"><span data-stu-id="09b4d-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="09b4d-159">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="09b4d-159">Voucher</span></span>
    -   <span data-ttu-id="09b4d-160">**FD** I dati finanziari del saldo iniziale</span><span class="sxs-lookup"><span data-stu-id="09b4d-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="09b4d-161">**FD** I dati finanziari contenenti solo i debiti</span><span class="sxs-lookup"><span data-stu-id="09b4d-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="09b4d-162">**FD** I dati finanziari contenenti solo i crediti</span><span class="sxs-lookup"><span data-stu-id="09b4d-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="09b4d-163">**CALC** La differenza netta</span><span class="sxs-lookup"><span data-stu-id="09b4d-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="09b4d-164">**CALC** Il saldo di chiusura</span><span class="sxs-lookup"><span data-stu-id="09b4d-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="09b4d-165">**Bilancio di verifica riepilogativo annuale - Predefinito:**</span><span class="sxs-lookup"><span data-stu-id="09b4d-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="09b4d-166">**ACCT** - Codici conto</span><span class="sxs-lookup"><span data-stu-id="09b4d-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="09b4d-167">**DESC** - Descrizione della definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="09b4d-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="09b4d-168">**ATTR** Un attributo</span><span class="sxs-lookup"><span data-stu-id="09b4d-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="09b4d-169">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="09b4d-169">Voucher</span></span>
    -   <span data-ttu-id="09b4d-170">**FD** I dati finanziari del saldo iniziale per l'anno in corso</span><span class="sxs-lookup"><span data-stu-id="09b4d-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="09b4d-171">**FD** I dati finanziari contenenti solo i debiti per l'anno in corso</span><span class="sxs-lookup"><span data-stu-id="09b4d-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="09b4d-172">**FD** I dati finanziari contenenti solo i crediti per l'anno in corso</span><span class="sxs-lookup"><span data-stu-id="09b4d-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="09b4d-173">**CALC** La differenza netta</span><span class="sxs-lookup"><span data-stu-id="09b4d-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="09b4d-174">**CALC** Il saldo di chiusura</span><span class="sxs-lookup"><span data-stu-id="09b4d-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="09b4d-175">**FD** I dati finanziari contenenti solo i debiti per l'anno precedente</span><span class="sxs-lookup"><span data-stu-id="09b4d-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="09b4d-176">**FD** I dati finanziari contenenti solo i crediti per l'anno precedente</span><span class="sxs-lookup"><span data-stu-id="09b4d-176">**FD** – Financial data that contains only credits for the last year</span></span>



<a name="additional-resources"></a><span data-ttu-id="09b4d-177">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="09b4d-177">Additional resources</span></span>
--------

[<span data-ttu-id="09b4d-178">Creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="09b4d-178">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="09b4d-179">Visualizzare i report finanziari</span><span class="sxs-lookup"><span data-stu-id="09b4d-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="09b4d-180">Blog sui report finanziari di Dynamics</span><span class="sxs-lookup"><span data-stu-id="09b4d-180">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)



