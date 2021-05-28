---
title: Saldo iniziale mancante nella chiusura di fine anno
description: In questo argomento viene illustrato perché il saldo iniziale potrebbe mancare quando si chiude un anno e come ricostruire il saldo se manca.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028571"
---
# <a name="year-end-close-missing-opening-balances"></a><span data-ttu-id="2b724-103">Saldo iniziale mancante nella chiusura di fine anno</span><span class="sxs-lookup"><span data-stu-id="2b724-103">Year-end close missing opening balances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b724-104">In questo argomento viene illustrato perché il saldo iniziale potrebbe mancare quando si chiude un anno e come ricostruire il saldo se manca.</span><span class="sxs-lookup"><span data-stu-id="2b724-104">This topic explains why opening balances might be missing when you close a year, and how to rebuild those balances if they are missing.</span></span>

### <a name="symptom"></a><span data-ttu-id="2b724-105">Sintomo</span><span class="sxs-lookup"><span data-stu-id="2b724-105">Symptom</span></span>

<span data-ttu-id="2b724-106">Perché non sono presenti i saldi iniziali dopo l'esecuzione della chiusura di fine anno della contabilità generale?</span><span class="sxs-lookup"><span data-stu-id="2b724-106">Why are there no beginning balances after running the General ledger year-end close?</span></span> 

### <a name="resolution"></a><span data-ttu-id="2b724-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="2b724-107">Resolution</span></span>

<span data-ttu-id="2b724-108">Di seguito sono riportate le cose da verificare se è stato chiuso un anno nella contabilità generale e quindi è stato generato un bilancio di verifica che non riporta i saldi iniziali per l'anno fiscale successivo.</span><span class="sxs-lookup"><span data-stu-id="2b724-108">Here are things to check if you've closed a year in General ledger, and then generated a trial balance that doesn't display opening balances for the next fiscal year.</span></span>

<span data-ttu-id="2b724-109">Se il campo **Annulla chiusura precedente** è impostato su **Sì**, la chiusura di fine anno precedente per lo stesso anno fiscale viene annullata.</span><span class="sxs-lookup"><span data-stu-id="2b724-109">If the **Undo previous close** field is set to **Yes**, the previous year-end close for the same fiscal year is being reversed.</span></span> <span data-ttu-id="2b724-110">Quando si esegue un processo di annullamento della chiusura di fine anno, tutte le voci per il saldo finale e il saldo iniziale vengono eliminate, come se la chiusura di fine anno non fosse mai stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="2b724-110">When running a process to reverse the year-end close, all entries for both closing and opening balances will be deleted, as if the year had never been closed.</span></span> <span data-ttu-id="2b724-111">Anche i giustificativi vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="2b724-111">The vouchers are also deleted.</span></span> <span data-ttu-id="2b724-112">Il processo di chiusura di fine anno non viene ripetuto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2b724-112">The year-end close process will not run again automatically.</span></span> <span data-ttu-id="2b724-113">È necessario rieseguire il processo, questa volta aggiornando l'opzione **Annulla chiusura precedente** su **No**.</span><span class="sxs-lookup"><span data-stu-id="2b724-113">You must start the process again, this time updating the **Undo previous close** option to **No**.</span></span>

<span data-ttu-id="2b724-114">Questo scenario è trattato nell'argomento Domande frequenti sulla chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="2b724-114">This scenario is covered in the year-end close FAQ topic.</span></span> <span data-ttu-id="2b724-115">Per ulteriori informazioni, vedere [Domande frequenti sulle attività di fine anno](faq-year-end-activities.md).</span><span class="sxs-lookup"><span data-stu-id="2b724-115">For more information, see [Year-end activities FAQ](faq-year-end-activities.md).</span></span>

### <a name="symptom"></a><span data-ttu-id="2b724-116">Sintomo</span><span class="sxs-lookup"><span data-stu-id="2b724-116">Symptom</span></span>

<span data-ttu-id="2b724-117">È stata eseguita la chiusura di fine anno con l'opzione **Annulla chiusura precedente** impostata su **No** e ancora non sono stati restituiti i saldi iniziali per l'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="2b724-117">I ran year-end close with the **Undo previous close** option set to **No**, and I still do not have opening balances for my fiscal year.</span></span>

### <a name="resolution"></a><span data-ttu-id="2b724-118">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="2b724-118">Resolution</span></span>

<span data-ttu-id="2b724-119">Per prima cosa controllare lo stato del processo batch.</span><span class="sxs-lookup"><span data-stu-id="2b724-119">First check the status of the batch job.</span></span> <span data-ttu-id="2b724-120">La chiusura di un anno include una serie di attività separate, ma il passaggio più critico è l'attività batch con la descrizione dell'attività **Passaggio 5.0.0**.</span><span class="sxs-lookup"><span data-stu-id="2b724-120">Closing a year includes a number of separate tasks, but the most critical step is the batch task with the task description **Step 5.0.0**.</span></span> <span data-ttu-id="2b724-121">Durante questo passaggio viene eseguita la registrazione delle transazioni di apertura e, facoltativamente, delle transazioni di chiusura nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="2b724-121">Posting the opening transactions, and optionally the closing transactions, to General ledger takes place during this step.</span></span> 

<span data-ttu-id="2b724-122">[![Elenco storico batch](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span><span class="sxs-lookup"><span data-stu-id="2b724-122">[![Batch history list](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span></span>

<span data-ttu-id="2b724-123">Se questo passaggio è terminato con esito positivo, ma i saldi iniziali non sono presenti nella pagina **Richiesta informazioni bilancio di verifica** (**Contabilità generale > Richieste informazioni e report > Bilancio di verifica**), rivedere i risultati del processo batch di chiusura di fine anno per verificare se il passaggio per la ricostruzione dei saldi è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="2b724-123">If this step ended successfully but you don’t see opening balances on the **Trial balance inquiry** page (**General ledger > Inquires and reports > Trial balance**), review the results of the year-end close batch job to see if the Rebuild balances step completed successfully.</span></span>

<span data-ttu-id="2b724-124">[![Risultati del processo batch di chiusura di fine anno](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span><span class="sxs-lookup"><span data-stu-id="2b724-124">[![Results of year-end close batch job](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span></span>

<span data-ttu-id="2b724-125">Se questo passaggio non è riuscito per qualsiasi motivo, è probabile che le transazioni di apertura (e facoltativamente di chiusura) siano state registrate correttamente.</span><span class="sxs-lookup"><span data-stu-id="2b724-125">If this step has failed for any reason, the opening (and optionally closing) transactions were likely posted successfully.</span></span> <span data-ttu-id="2b724-126">È possibile verificare che le transazioni di contabilità generale siano state registrate correttamente utilizzando la pagina **Richiesta informazioni transazioni giustificativo** specificando il numero del giustificativo e la data forniti nella finestra di dialogo di chiusura di fine anno per l'anno che è stato chiuso, (**Contabilità generale > Richieste informazioni e report > Transazioni giustificativo**).</span><span class="sxs-lookup"><span data-stu-id="2b724-126">You can verify that the General ledger transactions were posted successfully using the **Voucher transactions inquiry** page by specifying the voucher number and date provided on the year-end close dialog for the year that you closed, (**General Ledger > Inquiries and reports > Voucher transactions**).</span></span>

<span data-ttu-id="2b724-127">[![Richiesta informazioni transazioni giustificativo](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span><span class="sxs-lookup"><span data-stu-id="2b724-127">[![Voucher transactions inquiry](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span></span>

<span data-ttu-id="2b724-128">Se sono presenti i giustificativi di apertura (e facoltativamente di chiusura), non è necessario riavviare la chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="2b724-128">If the opening (and optionally closing) vouchers are present, you don’t need to run the year-end close again.</span></span> <span data-ttu-id="2b724-129">Fare riferimento alla sezione successiva per informazioni su come procedere.</span><span class="sxs-lookup"><span data-stu-id="2b724-129">Instead refer to the next section for information about how to move forward.</span></span>

### <a name="symptom"></a><span data-ttu-id="2b724-130">Sintomo</span><span class="sxs-lookup"><span data-stu-id="2b724-130">Symptom</span></span>

<span data-ttu-id="2b724-131">Il passaggio per la ricostruzione dei saldi nella chiusura di fine anno non è riuscito, occorre rieseguire l'intero processo di chiusura di fine anno?</span><span class="sxs-lookup"><span data-stu-id="2b724-131">The “Rebuild balances” step in the year-end close failed, do I need to re-run the entire year-end close process?</span></span>

### <a name="resolution"></a><span data-ttu-id="2b724-132">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="2b724-132">Resolution</span></span>

<span data-ttu-id="2b724-133">Il passaggio della ricostruzione dei saldi aggiorna i saldi di contabilità generale utilizzati quando viene generata la richiesta informazioni bilancio di verifica.</span><span class="sxs-lookup"><span data-stu-id="2b724-133">The Rebuild balances step updates the General ledger balances that are used when the Trial balance inquiry is generated.</span></span>  <span data-ttu-id="2b724-134">È il passaggio finale del processo di chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="2b724-134">It is the final step in the year-end close process.</span></span>  <span data-ttu-id="2b724-135">Se questo passaggio è l'unico passaggio non riuscito, le transazioni di contabilità generale sono state registrate correttamente.</span><span class="sxs-lookup"><span data-stu-id="2b724-135">If this step is the only step that failed, the General ledger transactions have posted successfully.</span></span>  <span data-ttu-id="2b724-136">Non è necessario ripetere la chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="2b724-136">You do not need to run the year-end close again.</span></span> <span data-ttu-id="2b724-137">È possibile eseguire il processo per ricostruire manualmente i saldi utilizzando la pagina **Set di dimensioni finanziarie** (**Contabilità generale > Piano dei conti > Dimensioni > Set di dimensioni finanziarie**).</span><span class="sxs-lookup"><span data-stu-id="2b724-137">You can run the process to rebuild the balances manually using the **Financial dimension sets** page (**General ledger > Chart of accounts > Dimensions > Financial dimension sets**).</span></span>

<span data-ttu-id="2b724-138">[![Pulsante Ricostruisci saldi nella pagina Set di dimensioni finanziarie](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span><span class="sxs-lookup"><span data-stu-id="2b724-138">[![Rebuild balances button on Financial dimension sets page](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span></span>

<span data-ttu-id="2b724-139">Se l'elaborazione di questo passaggio richiede molto tempo, si consiglia di rivedere le procedure consigliate per i set di dimensioni finanziarie come descritto in [Procedure consigliate per l'aggiornamento dei set di dimensioni finanziarie](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span><span class="sxs-lookup"><span data-stu-id="2b724-139">If this step takes a long time to process, we recommend reviewing the best practices for financial dimension sets as described in [Best practices for updating Financial dimension sets](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span></span> 

