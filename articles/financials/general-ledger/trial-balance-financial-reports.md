---
title: Report finanziari del bilancio di verifica
description: "In questo articolo viene descritto i report predefiniti per i bilanci di verifica. Sono descritti inoltre i blocchi predefiniti associati a questi report e come è possibile modificare i report in modo da soddisfare i requisiti aziendali."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6d5674bed7167e002e7467e1e77d333fdf1b4f8d
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="trial-balance-financial-reports"></a><span data-ttu-id="705b1-104">Report finanziari del bilancio di verifica</span><span class="sxs-lookup"><span data-stu-id="705b1-104">Trial balance financial reports</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="705b1-105">In questo articolo viene descritto i report predefiniti per i bilanci di verifica.</span><span class="sxs-lookup"><span data-stu-id="705b1-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="705b1-106">Sono descritti inoltre i blocchi predefiniti associati a questi report e come è possibile modificare i report in modo da soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="705b1-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="705b1-107">Report predefiniti del bilancio di verifica</span><span class="sxs-lookup"><span data-stu-id="705b1-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="705b1-108">Tre report di bilancio di verifica sono disponibili in Creazione di report finanziari in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="705b1-108">Three trial balance reports are available in Financial reporting in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

| <span data-ttu-id="705b1-109">Report predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-109">Default report</span></span>                                 | <span data-ttu-id="705b1-110">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="705b1-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="705b1-111">Bilancio di verifica dettagliato - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="705b1-112">Fornisce informazioni sul saldo per tutti i conti e include i saldi in Avere e in Dare e l'importo netto di questi, insieme alla data della transazione, al giustificativo e alla descrizione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="705b1-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="705b1-113">Bilancio di verifica riepilogativo - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="705b1-114">Fornisce informazioni sul saldo per tutti i conti e include i saldi di chiusura e di apertura e i saldi in Avere e in Dare, insieme alle differenze nette.</span><span class="sxs-lookup"><span data-stu-id="705b1-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="705b1-115">Bilancio di verifica riepilogativo annuale - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="705b1-116">Fornisce informazioni sul saldo per tutti i conti e include i saldi di chiusura e di apertura e i saldi in Avere e in Dare, insieme alle differenze nette per l'anno corrente e l'anno precedente.</span><span class="sxs-lookup"><span data-stu-id="705b1-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="705b1-117">Blocchi predefiniti</span><span class="sxs-lookup"><span data-stu-id="705b1-117">Building blocks</span></span>
<span data-ttu-id="705b1-118">I report finanziari del bilancio di verifica utilizzano i seguenti blocchi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="705b1-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="705b1-119">Report predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-119">Default report</span></span>                                 | <span data-ttu-id="705b1-120">Definizione riga</span><span class="sxs-lookup"><span data-stu-id="705b1-120">Row definition</span></span>          | <span data-ttu-id="705b1-121">Definizione colonna</span><span class="sxs-lookup"><span data-stu-id="705b1-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="705b1-122">Bilancio di verifica dettagliato - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="705b1-123">Bilancio di verifica - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-123">Trial Balance - Default</span></span> | <span data-ttu-id="705b1-124">Bilancio di verifica dettagliato - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="705b1-125">Bilancio di verifica riepilogativo - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="705b1-126">Bilancio di verifica - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-126">Trial Balance - Default</span></span> | <span data-ttu-id="705b1-127">Bilancio di verifica riepilogativo - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="705b1-128">Bilancio di verifica riepilogativo annuale - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="705b1-129">Bilancio di verifica - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-129">Trial Balance - Default</span></span> | <span data-ttu-id="705b1-130">Bilancio di verifica riepilogativo annuale - Predefinito</span><span class="sxs-lookup"><span data-stu-id="705b1-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="705b1-131">Definizione riga</span><span class="sxs-lookup"><span data-stu-id="705b1-131">Row definition</span></span>

<span data-ttu-id="705b1-132">La definizione di riga, Bilancio di verifica - Predefinito, contiene una singola riga che esegue il pull in tutti i conti principali.</span><span class="sxs-lookup"><span data-stu-id="705b1-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="705b1-133">Di conseguenza, chiunque può generare il report senza dover apportare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="705b1-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="705b1-134">Quando si visualizza il report, si analizza la singola riga per visualizzare i dettagli relativi a ciascun conto.</span><span class="sxs-lookup"><span data-stu-id="705b1-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="705b1-135">È possibile modificare la definizione di riga in modo da includere più dettagli.</span><span class="sxs-lookup"><span data-stu-id="705b1-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="705b1-136">Per modificare la definizione di riga Bilancio di verifica - Predefinito in modo che includa le righe per tutti i conti, attenersi ai passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="705b1-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="705b1-137">Fare clic su **Modifica** e quindi su **Inserisci righe da dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="705b1-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="705b1-138">Il comando **Inserisci righe da dimensioni** consente di scegliere le dimensioni che si desidera inserire nella definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="705b1-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="705b1-139">Per questa definizione di riga, si utilizza **Conto principale**.</span><span class="sxs-lookup"><span data-stu-id="705b1-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="705b1-140">Assicurarsi che **Conto principale** contenga tutte le e commerciali (&) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="705b1-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="705b1-141">La definizione di riga ora contiene tutti i conti principale per la persona giuridica predefinita.</span><span class="sxs-lookup"><span data-stu-id="705b1-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="705b1-142">Definizione colonna</span><span class="sxs-lookup"><span data-stu-id="705b1-142">Column definition</span></span>

<span data-ttu-id="705b1-143">Ogni report di bilancio di verifica utilizza una definizione di colonna diversa.</span><span class="sxs-lookup"><span data-stu-id="705b1-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="705b1-144">Le definizioni di colonna contengono i diversi tipi di colonna per fornire diversi livelli di dettagli e dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="705b1-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="705b1-145">**Bilancio di verifica dettagliato - Tipi predefiniti di colonna:**</span><span class="sxs-lookup"><span data-stu-id="705b1-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="705b1-146">**DESC** - Descrizione della definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="705b1-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="705b1-147">**ACCT** - Codici conto</span><span class="sxs-lookup"><span data-stu-id="705b1-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="705b1-148">**ATTR (3)** - Attributi:</span><span class="sxs-lookup"><span data-stu-id="705b1-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="705b1-149">Data della transazione</span><span class="sxs-lookup"><span data-stu-id="705b1-149">Transaction Date</span></span>
        -   <span data-ttu-id="705b1-150">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="705b1-150">Voucher</span></span>
        -   <span data-ttu-id="705b1-151">Descrizione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="705b1-151">Journal Description</span></span>
    -   <span data-ttu-id="705b1-152">**FD** I dati finanziari contenenti solo i debiti</span><span class="sxs-lookup"><span data-stu-id="705b1-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="705b1-153">**FD** I dati finanziari contenenti solo i crediti</span><span class="sxs-lookup"><span data-stu-id="705b1-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="705b1-154">**CALC** La differenza netta</span><span class="sxs-lookup"><span data-stu-id="705b1-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="705b1-155">**Bilancio di verifica riepilogativo - Tipi predefiniti di colonna:**</span><span class="sxs-lookup"><span data-stu-id="705b1-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="705b1-156">**ACCT** - Codici conto</span><span class="sxs-lookup"><span data-stu-id="705b1-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="705b1-157">**DESC** - Descrizione della definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="705b1-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="705b1-158">**ATTR** Un attributo:</span><span class="sxs-lookup"><span data-stu-id="705b1-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="705b1-159">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="705b1-159">Voucher</span></span>
    -   <span data-ttu-id="705b1-160">**FD** I dati finanziari del saldo iniziale</span><span class="sxs-lookup"><span data-stu-id="705b1-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="705b1-161">**FD** I dati finanziari contenenti solo i debiti</span><span class="sxs-lookup"><span data-stu-id="705b1-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="705b1-162">**FD** I dati finanziari contenenti solo i crediti</span><span class="sxs-lookup"><span data-stu-id="705b1-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="705b1-163">**CALC** La differenza netta</span><span class="sxs-lookup"><span data-stu-id="705b1-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="705b1-164">**CALC** Il saldo di chiusura</span><span class="sxs-lookup"><span data-stu-id="705b1-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="705b1-165">**Bilancio di verifica riepilogativo annuale - Predefinito:**</span><span class="sxs-lookup"><span data-stu-id="705b1-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="705b1-166">**ACCT** - Codici conto</span><span class="sxs-lookup"><span data-stu-id="705b1-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="705b1-167">**DESC** - Descrizione della definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="705b1-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="705b1-168">**ATTR** Un attributo</span><span class="sxs-lookup"><span data-stu-id="705b1-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="705b1-169">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="705b1-169">Voucher</span></span>
    -   <span data-ttu-id="705b1-170">**FD** I dati finanziari del saldo iniziale per l'anno in corso</span><span class="sxs-lookup"><span data-stu-id="705b1-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="705b1-171">**FD** I dati finanziari contenenti solo i debiti per l'anno in corso</span><span class="sxs-lookup"><span data-stu-id="705b1-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="705b1-172">**FD** I dati finanziari contenenti solo i crediti per l'anno in corso</span><span class="sxs-lookup"><span data-stu-id="705b1-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="705b1-173">**CALC** La differenza netta</span><span class="sxs-lookup"><span data-stu-id="705b1-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="705b1-174">**CALC** Il saldo di chiusura</span><span class="sxs-lookup"><span data-stu-id="705b1-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="705b1-175">**FD** I dati finanziari contenenti solo i debiti per l'anno precedente</span><span class="sxs-lookup"><span data-stu-id="705b1-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="705b1-176">**FD** I dati finanziari contenenti solo i crediti per l'anno precedente</span><span class="sxs-lookup"><span data-stu-id="705b1-176">**FD** – Financial data that contains only credits for the last year</span></span>

 

<a name="see-also"></a><span data-ttu-id="705b1-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="705b1-177">See also</span></span>
--------

[<span data-ttu-id="705b1-178">Creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="705b1-178">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="705b1-179">Visualizza report finanziari</span><span class="sxs-lookup"><span data-stu-id="705b1-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="705b1-180">Blog sui report finanziari di Dynamics</span><span class="sxs-lookup"><span data-stu-id="705b1-180">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




