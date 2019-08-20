---
title: Chiudere l'anno fiscale
description: Questa procedura descrive il processo di chiusura di fine anno per il trasferimento dei saldi in un nuovo anno fiscale.
author: aprilolson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c12f0842f6e8edf3b51d12d0e008eb09acf8c374
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834928"
---
# <a name="close-the-fiscal-year"></a><span data-ttu-id="c8b9b-103">Chiudere l'anno fiscale</span><span class="sxs-lookup"><span data-stu-id="c8b9b-103">Close the fiscal year</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c8b9b-104">Questa procedura descrive il processo di chiusura di fine anno per il trasferimento dei saldi in un nuovo anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-104">This procedure steps through the year end close process that transfers balances to a new fiscal year.</span></span>


## <a name="validate-year-end-close-parameters"></a><span data-ttu-id="c8b9b-105">Convalidare i parametri di chiusura di fine anno</span><span class="sxs-lookup"><span data-stu-id="c8b9b-105">Validate year-end close parameters</span></span>
1. <span data-ttu-id="c8b9b-106">Passare a **Pannello di navigazione > Moduli > Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-106">Go to **Navigation pane > Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="c8b9b-107">Espandere la sezione **Chiusura anno fiscale**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-107">Expand the **Fiscal year close** section.</span></span>
3. <span data-ttu-id="c8b9b-108">Selezionare 'Sì' o 'No' per l'opzione **Elimina transazioni di fine anno durante il trasferimento**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-108">Select 'Yes' or 'No' for the **Delete close-of-year transactions during transfer** option.</span></span>
    
    <span data-ttu-id="c8b9b-109">Se l'anno fiscale è già stato chiuso e la chiusura di fine anno viene rieseguita, questa impostazione è importante.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-109">If the fiscal year has already been closed and the year-end close is being run again, this setting is important.</span></span> <span data-ttu-id="c8b9b-110">Se impostata su Sì, il giustificativo per la precedente chiusura di fine anno verrà eliminato e un nuovo giustificativo verrà creato per tutti i saldi iniziali di conti.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-110">If set to Yes, the voucher for the previous year-end close will be deleted, and a new voucher will be created for all accounts beginning balances.</span></span> <span data-ttu-id="c8b9b-111">Se l'opzione è impostata su No, il giustificativo precedente rimarrà e un nuovo giustificativo verrà creato solo per le voci di rettifica registrate dopo l'ultima chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-111">If set to No, the previous voucher will remain and a new voucher will only be created for adjusting entries that were posted after the last year-end close.</span></span>

4. <span data-ttu-id="c8b9b-112">Selezionare 'Sì' o 'No' per l'opzione **Crea transazioni di chiusura durante il trasferimento**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-112">Select 'Yes' or 'No' for the **Create closing transactions during transfer** option.</span></span>

    <span data-ttu-id="c8b9b-113">Se l'opzione è impostata su Sì, due transazioni vengono create.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-113">If set to Yes, two transactions are created.</span></span> <span data-ttu-id="c8b9b-114">Un giustificativo viene creato nell'anno fiscale che viene chiuso per azzerare i saldi dei conti CoGe Profitti e perdite e un secondo giustificativo viene creato nell'anno fiscale successivo per i saldi iniziali.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-114">One voucher is created in the fiscal year being closed to bring the balances of the P&L ledger accounts down to zero and a second voucher is created in the next fiscal year for the beginning balances.</span></span> <span data-ttu-id="c8b9b-115">Se impostata su No, a un singolo giustificativo viene creato nell'anno fiscale successivo per i saldi iniziali.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-115">If set to No, a single voucher is created in the next fiscal year for the beginning balances.</span></span>  

5. <span data-ttu-id="c8b9b-116">Selezionare 'Sì' o 'No' per l'opzione **Imposta stato anno fiscale su chiuso in modo permanente**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-116">Select 'Yes' or 'No' for the **Set fiscal year status to permanently closed** option.</span></span>

    <span data-ttu-id="c8b9b-117">Se impostata su Sì, lo stato dell'anno fiscale verrà impostato su Chiuso in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-117">If set to Yes, the fiscal year status will be set to Permanently closed.</span></span>  <span data-ttu-id="c8b9b-118">Poiché un anno chiuso in modo permanente non può essere riaperto, sarebbe una procedura consigliata impostare questa opzione su No.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-118">Because a permanently closed year cannot be reopened, it would be a best practice to set this option to No.</span></span>  

6. <span data-ttu-id="c8b9b-119">Selezionare 'Sì' o 'No' per decidere se **un numero di giustificativo deve essere completato durante la chiusura di fine anno**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-119">Select 'Yes' or 'No' for the **Voucher number must be filled in during the year end close** option.</span></span>

    <span data-ttu-id="c8b9b-120">Se impostata su Sì, è necessario immettere un numero di giustificativo manualmente durante il processo di chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-120">If set to Yes, a voucher number must be manually entered during the year end close process.</span></span> <span data-ttu-id="c8b9b-121">Una sequenza numerica non viene utilizzata per generare il numero di giustificativo.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-121">A number sequence is not used to generate this voucher number.</span></span> <span data-ttu-id="c8b9b-122">È consigliabile impostare questa impostazione su Sì.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-122">It's a best practice to set this to Yes.</span></span>  

7. <span data-ttu-id="c8b9b-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-123">Close the page.</span></span>
8. <span data-ttu-id="c8b9b-124">Andare a **Contabilità generale > Periodo chiuso > Chiusura di fine anno**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-124">Go to **General ledger > Period close > Year end close**.</span></span>
9. <span data-ttu-id="c8b9b-125">Fare clic su **Nuovo** per creare un modello di chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-125">Click **New** to create a year-end close template.</span></span>

    <span data-ttu-id="c8b9b-126">Un modello può essere creato per un gruppo di persone giuridiche per cui eseguire la chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-126">A template can be created for a group of legal entities for which to run the year-end close.</span></span> <span data-ttu-id="c8b9b-127">Questo modello può essere riutilizzato anno dopo anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-127">This template can be reused year after year.</span></span>  

10. <span data-ttu-id="c8b9b-128">Nel campo **Nome gruppo** immettere un nome di modello di chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-128">In the **Group name** field, enter a year-end close template name..</span></span>
11. <span data-ttu-id="c8b9b-129">Nel campo **Calendario fiscale**, selezionare l'anno fiscale per il quale il modello verrà creato.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-129">In the **Fiscal calendar** field, select the fiscal year for which the template will be created.</span></span>

    <span data-ttu-id="c8b9b-130">Solo le persone giuridiche che utilizzano lo stesso anno fiscale possono essere raggruppate nel modello di chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-130">Only legal entities which use the same fiscal year can be grouped together in the year-end close template.</span></span> <span data-ttu-id="c8b9b-131">Questo perché la chiusura di fine anno viene effettuata selezionando un anno fiscale, non una data.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-131">This is because the year end close is done by selecting a fiscal year, not a date.</span></span>  

12. <span data-ttu-id="c8b9b-132">Nel **riquadro azioni** fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-132">On the **Action pane**, click **Save**.</span></span>
13. <span data-ttu-id="c8b9b-133">Nella sezione **Persone giuridiche**, fare clic su **Aggiungi** per selezionare le persone giuridiche per il modello.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-133">In the **Legal entities** section, click **Add** to select the legal entities for this template.</span></span>
    
    <span data-ttu-id="c8b9b-134">Le persone giuridiche possono essere aggiunti selezionando le persone giuridiche o selezionando una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-134">Legal entities can be added by either selecting the legal entities or by selecting an organizational hierarchy.</span></span>  <span data-ttu-id="c8b9b-135">Solo le persone giuridiche con la gerarchia organizzativa con lo stesso calendario fiscale selezionato verranno aggiunte.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-135">Only legal entities with the organizational hierarchy with the same fiscal calendar selected will be added.</span></span>  

14. <span data-ttu-id="c8b9b-136">Selezionare le persone giuridiche o la gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-136">Select either the legal entities or the organizational hierarchy.</span></span>
15. <span data-ttu-id="c8b9b-137">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-137">Click **OK**.</span></span>
16. <span data-ttu-id="c8b9b-138">Selezionare 'Sì' o 'No' in **Trasferisci dimensioni di conto patrimoniale**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-138">Select 'Yes' or 'No' in the **Transfer balance sheet dimension**.</span></span>

    <span data-ttu-id="c8b9b-139">È consigliabile impostare questa opzione su Sì per i conti dello stato patrimoniale.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-139">It's best practice to set this option to Yes for Balance sheet accounts.</span></span> <span data-ttu-id="c8b9b-140">Questo per gestire le dimensioni finanziarie nelle transazioni registrate durante la creazione dei saldi iniziali per i conti dello stato patrimoniale.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-140">This will maintain the financial dimensions on posted transactions when creating the beginning balances for the balance sheet accounts.</span></span> <span data-ttu-id="c8b9b-141">Per i conti profitti e perdite, è possibile selezionare di gestire le dimensioni finanziarie (Chiudi tutte) quando i saldi vengono spostati negli utili non distribuiti oppure scegliere di avere le dimensioni finanziarie sostituite con un altro valore di dimensione da (Chiudi singolo).</span><span class="sxs-lookup"><span data-stu-id="c8b9b-141">For profit and loss accounts, you can select to maintain the financial dimensions (Close all) when the balances are moved to Retained earnings or you can select to have the financial dimensions replaced with a different dimension value (Close single).</span></span> <span data-ttu-id="c8b9b-142">Se si seleziona Chiudi singolo, è possibile definire un valore specifico per ogni dimensione o anche scegliere di lasciarla vuota.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-142">If you choose Close single, you can define a specific dimension value for each dimension or even choose to leave it blank.</span></span>  

17. <span data-ttu-id="c8b9b-143">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-143">Click **Save**.</span></span>
18. <span data-ttu-id="c8b9b-144">Avviare la chiusura di fine anno scegliendo **Esegui chiusura fiscale** nel **riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-144">Start the year-end close by choosing **Run fiscal close** on the **Action Pane**.</span></span> <span data-ttu-id="c8b9b-145">La chiusura di fine anno verrà eseguita per il modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-145">The year-end close will be run for the selected template.</span></span>  
19. <span data-ttu-id="c8b9b-146">Selezionare tutte o un sottoinsieme di persone giuridiche dal modello per cui eseguire la chiusura di fine anno.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-146">Select all or a subset of legal entities from the template for which to run the year-end close.</span></span>

    <span data-ttu-id="c8b9b-147">Alla prima esecuzione della chiusura di fine anno, per ottenere i saldi iniziali la maggior parte delle organizzazioni possono scegliere di eseguire la chiusura di fine anno per tutte le persone giuridiche nel modello.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-147">When first running the year-end close, to get beginning balance,s most organizations may choose to run the year-end close for all legal entities within the template.</span></span> <span data-ttu-id="c8b9b-148">Se le voci di rettifica vengono effettuate successivamente, è possibile scegliere di eseguire la chiusura di fine anno solo per le persone giuridiche con rettifiche.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-148">If adjusting entries are made after that, you may choose to run the year-end close for only the legal entities that have adjustments.</span></span>  

20. <span data-ttu-id="c8b9b-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-149">Click **OK**.</span></span>
21. <span data-ttu-id="c8b9b-150">Selezionare l'anno fiscale per cui eseguire la chiusura.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-150">Select the fiscal year for which to run the year-end close.</span></span>
22. <span data-ttu-id="c8b9b-151">Nel campo **Giustificativo** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-151">In the **Voucher field**, type a value.</span></span> <span data-ttu-id="c8b9b-152">È consigliabile includere l'anno fiscale nel numero di giustificativo, per semplificare la ricerca del giustificativo di chiusura di fine anno creato.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-152">It's best practice to include the fiscal year in the voucher number, to make it easier to find the year-end close voucher that is created.</span></span>  
23. <span data-ttu-id="c8b9b-153">La chiusura di fine anno viene eseguita in modalità batch per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-153">The year-end close defaults to run in batch.</span></span> <span data-ttu-id="c8b9b-154">È consigliabile eseguire in modalità batch i processi a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-154">It's best practice for long-running processes to run in batch mode.</span></span> <span data-ttu-id="c8b9b-155">Questo è in genere uno di tali processi, che è il motivo per cui l'impostazione predefinita è utilizzare la modalità batch.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-155">This is typically one of those processes, which is why the default is to use batch mode.</span></span>  
24. <span data-ttu-id="c8b9b-156">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8b9b-156">Click **OK**.</span></span>

