---
title: Simulazioni di contabilità generale (Italia)
description: Questo argomento fornisce informazioni sulla registrazione delle transazioni di contabilità generale come simulazioni del giornale di registrazione generale e quindi sulla verifica dei report che includono le transazioni simulate.
author: anasyash
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3063f2b4ab21efb887ee983bf902729092b0ea81
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894752"
---
# <a name="general-ledger-simulations"></a><span data-ttu-id="85d4b-103">Simulazioni di contabilità generale</span><span class="sxs-lookup"><span data-stu-id="85d4b-103">General ledger simulations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="85d4b-104">Le simulazioni di contabilità generale consentono di registrare transazioni di contabilità generale simulate del giornale di registrazione generale e quindi di esaminare i report che includono le transazioni simulate.</span><span class="sxs-lookup"><span data-stu-id="85d4b-104">General ledger simulations allow you to post simulated ledger transactions from the general journal and then review reports that include the simulated transactions.</span></span>

<span data-ttu-id="85d4b-105">Questa funzionalità è disponibile solo per le persone giuridiche con un indirizzo principale in Italia.</span><span class="sxs-lookup"><span data-stu-id="85d4b-105">This feature is available only for legal entities with a primary address in Italy.</span></span> 

<span data-ttu-id="85d4b-106">È possibile registrare transazioni di simulazione solo per le righe del giornale di registrazione dove **Tipo di account** e **Tipo di conto di contropartita** sono uguali a **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-106">You can post simulation transactions only for journal lines where **Account type** and **Offset account type** are equal to **Ledger**.</span></span>
<span data-ttu-id="85d4b-107">È possibile eliminare le transazioni di contabilità generale simulate, modificarle e spostarle nelle transazioni di contabilità generale registrate reali.</span><span class="sxs-lookup"><span data-stu-id="85d4b-107">You can delete the simulated ledger transactions, modify them, and move them to the real general ledger posted transactions.</span></span>
<span data-ttu-id="85d4b-108">È possibile esaminare le transazioni di contabilità generale di simulazione registrate nei report **Bilancio di verifica** e **Rendiconto dimensioni con simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-108">You can review the posted simulation ledger transactions in the reports, **Trial balance** and **Dimension statement with simulation**.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="85d4b-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="85d4b-109">Prerequisites</span></span>

<span data-ttu-id="85d4b-110">Per poter utilizzare le simulazioni di contabilità generale, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="85d4b-110">Before you can use the General ledger simulations, the following prerequisites must be met:</span></span>

- <span data-ttu-id="85d4b-111">L'indirizzo principale della persona giuridica è in italia.</span><span class="sxs-lookup"><span data-stu-id="85d4b-111">The primary address of the legal entity is in Italy.</span></span>
- <span data-ttu-id="85d4b-112">Abilitare la funzionalità **Simulazioni di contabilità generale** nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-112">Enable the **General ledger simulations** feature in the **Feature management** workspace.</span></span> <span data-ttu-id="85d4b-113">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85d4b-113">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="setup"></a><span data-ttu-id="85d4b-114">Impostazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-114">Setup</span></span> 

### <a name="create-a-number-sequence-for-the-simulated-general-journal-transfer"></a><span data-ttu-id="85d4b-115">Creare una sequenza numerica per il trasferimento del giornale di registrazione simulato</span><span class="sxs-lookup"><span data-stu-id="85d4b-115">Create a number sequence for the simulated general journal transfer</span></span>

1.  <span data-ttu-id="85d4b-116">Selezionare **Contabilità generale** > **Impostazione contabilità generale** > **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-116">Go to **General ledger** > **Ledger setup** > **General ledger parameters**.</span></span>
2.  <span data-ttu-id="85d4b-117">Nella scheda **Sequenze numeriche**, impostare la sequenza su **Trasferimento giornale di registrazione generale di simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-117">On the **Number sequences** tab, set the sequence to **Simulation general journal transfer**.</span></span>

### <a name="create-a-simulation-journal"></a><span data-ttu-id="85d4b-118">Creare un giornale di registrazione di simulazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-118">Create a Simulation journal</span></span>

1. <span data-ttu-id="85d4b-119">Selezionare **Contabilità generale** > **Impostazione giornale di registrazione** > **Nome giornale di registrazione** e creare un nuovo giornale di registrazione denominato "Simulazione".</span><span class="sxs-lookup"><span data-stu-id="85d4b-119">Go to **General ledger** > **Journal setup** > **Journal name** and create a new journal called 'Simulation'.</span></span>
2. <span data-ttu-id="85d4b-120">Impostare **Tipo di giornale di registrazione** su **Giornaliero**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-120">Set the **Journal type** to **Daily**.</span></span>
3. <span data-ttu-id="85d4b-121">Nel campo **Simulazione**, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-121">In the **Simulation** field, select **Yes**.</span></span>
4. <span data-ttu-id="85d4b-122">Nel campo **Giornale di registrazione di simulazione**, impostare **Richiede convalida** su **Sì** per indicare che il giornale di registrazione deve essere convalidato prima dell'esecuzione della registrazione simulata.</span><span class="sxs-lookup"><span data-stu-id="85d4b-122">In the **Simulation journal** field group, set **Requires validation** to **Yes** to indicate that the journal must be validated before the simulated posting is executed.</span></span>


## <a name="operations"></a><span data-ttu-id="85d4b-123">Operations</span><span class="sxs-lookup"><span data-stu-id="85d4b-123">Operations</span></span>

### <a name="create-and-post-simulation-transaction"></a><span data-ttu-id="85d4b-124">Creare e registrare transazioni di simulazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-124">Create and post simulation transaction</span></span>

1. <span data-ttu-id="85d4b-125">Selezionare **Contabilità generale** > **Inserimenti nel giornale di registrazione** > **Giornali di registrazione di simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-125">Go to **General Ledger** > **Journal Entries** > **Simulation journals**.</span></span>
2. <span data-ttu-id="85d4b-126">Creare righe del giornale di registrazione come **Contabilità generale - Contabilità generale** nel modo standard, quindi selezionare **Registra** > **Registra simulazione** per registrare le transazioni di simulazione.</span><span class="sxs-lookup"><span data-stu-id="85d4b-126">Create journal lines as **Ledger - Ledger** in the standard way, and then select **Post** > **Post simulation** to post the simulation transactions.</span></span> <span data-ttu-id="85d4b-127">Ciò rende la transazione effettiva per i calcoli di simulazione e il giornale di registrazione diventa *simulazione registrata*.</span><span class="sxs-lookup"><span data-stu-id="85d4b-127">This makes the transaction effective for simulation calculations, and the journal becomes *simulation posted*.</span></span>
3. <span data-ttu-id="85d4b-128">Selezionare **Registra** > **Riapri** per rendere modificabile la transazione di simulazione registrata.</span><span class="sxs-lookup"><span data-stu-id="85d4b-128">Select **Post** > **Reopen** to make the posted simulation transaction editable.</span></span>
4. <span data-ttu-id="85d4b-129">Selezionare **Registra** > **Registra** per spostare la transazione di simulazione registrata nella contabilità generale ordinaria.</span><span class="sxs-lookup"><span data-stu-id="85d4b-129">Select **Post** > **Post** to move the posted simulation transaction to an ordinary ledger.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85d4b-130">La funzione che chiude un periodo fiscale o un anno fiscale verifica che le transazioni di simulazione siano state registrate come transazioni tipiche o siano state eliminate.</span><span class="sxs-lookup"><span data-stu-id="85d4b-130">The function that closes a fiscal period or a fiscal year verifies that the simulation transactions have been posted as typical transactions or have been deleted.</span></span> <span data-ttu-id="85d4b-131">Se vi sono transazioni di contabilità generale simulate in sospeso per il periodo, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="85d4b-131">If there are pending simulated general ledger transactions for the period, an error message appears.</span></span>


## <a name="periodic-operations"></a><span data-ttu-id="85d4b-132">Operazioni periodiche</span><span class="sxs-lookup"><span data-stu-id="85d4b-132">Periodic operations</span></span>

### <a name="post-all-simulation-transactions"></a><span data-ttu-id="85d4b-133">Registrare tutte le transazioni di simulazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-133">Post all simulation transactions</span></span> 

- <span data-ttu-id="85d4b-134">Per registrare transazioni di simulazione per tutti i giornali di registrazione di simulazione, selezionare **Attività periodiche** > **Simulazioni** > **Registra giornali di registrazione di simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-134">To post simulation transactions for all simulation journals, go to **Periodic tasks** > **Simulations** > **Post simulation journals**.</span></span>

<span data-ttu-id="85d4b-135">Le transazioni non includeranno più le transazioni di simulazione dopo la registrazione di tutti i giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="85d4b-135">Transactions will be no longer include simulation transactions after all journals are posted.</span></span>

### <a name="reopen-all-simulation-journals"></a><span data-ttu-id="85d4b-136">Riaprire tutti i giornali di registrazione di simulazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-136">Reopen all simulation journals</span></span> 

- <span data-ttu-id="85d4b-137">Per riaprire tutti i giornali di registrazione di simulazione, selezionare **Attività periodiche** > **Simulazioni** > **Riapri giornali di registrazione di simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-137">To reopen all simulation journals, go to **Periodic tasks** > **Simulations** > **Reopen simulation journals**.</span></span>

<span data-ttu-id="85d4b-138">Tutti i giornali di registrazione di simulazione registrati vengono riaperti.</span><span class="sxs-lookup"><span data-stu-id="85d4b-138">All simulation posted simulation journals are reopened.</span></span> <span data-ttu-id="85d4b-139">È possibile modificare i giornali di registrazione di simulazione e registrare nuovamente la simulazione.</span><span class="sxs-lookup"><span data-stu-id="85d4b-139">You can edit the Simulation journals and post simulation again.</span></span>

### <a name="delete-all-simulation-journals"></a><span data-ttu-id="85d4b-140">Eliminare tutti i giornali di registrazione di simulazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-140">Delete all simulation journals</span></span> 

- <span data-ttu-id="85d4b-141">Per eliminare tutti i giornali di registrazione di simulazione aperti, selezionare **Attività periodiche** > **Simulazioni** > **Elimina giornali di registrazione di simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-141">To delete all open simulation journals, go to **Periodic tasks** > **Simulations** > **Delete simulation journals**.</span></span> 

## <a name="review-simulation-transactions-in-reports"></a><span data-ttu-id="85d4b-142">Esaminare le transazioni di simulazione nei report</span><span class="sxs-lookup"><span data-stu-id="85d4b-142">Review simulation transactions in reports</span></span>

<span data-ttu-id="85d4b-143">Le transazioni di simulazione possono essere esaminare in diversi report di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="85d4b-143">Simulation transactions can be reviewed in several ledger reports.</span></span>

> [!NOTE] 
> <span data-ttu-id="85d4b-144">Le transazioni di simulazione non compaiono nel giornale di registrazione fiscale italiano fino a quando non diventano transazioni reali.</span><span class="sxs-lookup"><span data-stu-id="85d4b-144">Simulation transactions do not appear on the Italian fiscal journal until they become real transactions.</span></span>

### <a name="create-a-simulation-journal-name-group"></a><span data-ttu-id="85d4b-145">Creare un gruppo di giornali di registrazione di simulazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-145">Create a Simulation Journal name group</span></span> 

1. <span data-ttu-id="85d4b-146">Selezionare **Contabilità generale** > **Impostazione giornale di registrazione** > **Simulazioni** > **Gruppo di giornali di registrazione di simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-146">Go to **General ledger** > **Journal setup** > **Simulations** > **Simulation journal group**.</span></span>
2. <span data-ttu-id="85d4b-147">Creare un gruppo di giornali di registrazione di simulazione.</span><span class="sxs-lookup"><span data-stu-id="85d4b-147">Create a simulation journal group.</span></span> 
3. <span data-ttu-id="85d4b-148">Nella scheda **Giornali di registrazione di simulazione**, selezionare i giornali da includere nel gruppo dall'elenco dei giornali di registrazione di simulazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="85d4b-148">On the **Simulation journals** tab, select to include simulation journals in this group from the list of available simulation journals.</span></span> 

### <a name="trial-balance"></a><span data-ttu-id="85d4b-149">Bilancio di verifica</span><span class="sxs-lookup"><span data-stu-id="85d4b-149">Trial balance</span></span>

1. <span data-ttu-id="85d4b-150">Selezionare **Contabilità generale** > **Richieste di informazioni e report** > **Bilancio di verifica**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-150">Go to **General Ledger** > **Inquiries and reports** > **Trial balance**.</span></span>
2. <span data-ttu-id="85d4b-151">Nella scheda dettaglio **Parametri** dell'intestazione del report **Bilancio di verifica**, selezionare un valore nel campo **Gruppo di giornali di registrazione di simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-151">On the **Parameters** FastTab of the **Trial balance** report header, select a value in the **Simulation journal group** field.</span></span>
3. <span data-ttu-id="85d4b-152">Immettere altri parametri e calcolare i bilanci.</span><span class="sxs-lookup"><span data-stu-id="85d4b-152">Enter other parameters and calculate the balances.</span></span>
4. <span data-ttu-id="85d4b-153">Verificare che il report contenga colonne che prendano in considerazione le transazioni di simulazione, tra cui:</span><span class="sxs-lookup"><span data-stu-id="85d4b-153">Verify that the report contains columns that consider simulation transactions, this includes:</span></span>

-   <span data-ttu-id="85d4b-154">**Dare (simulazione)**</span><span class="sxs-lookup"><span data-stu-id="85d4b-154">**Debit (simulation)**</span></span>
-   <span data-ttu-id="85d4b-155">**Avere (simulazione)**</span><span class="sxs-lookup"><span data-stu-id="85d4b-155">**Credit (simulation)**</span></span>
-   <span data-ttu-id="85d4b-156">**Saldo di chiusura (con simulazioni)** - Questo è il totale dei valori nelle colonne **Saldo di chiusura**, **Dare (simulazione)** e **Avere (simulazione)**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-156">**Closing balance (with simulations)** - This is the total of the values in the **Closing balance**, **Debit (simulation)** and **Credit (simulation)** columns.</span></span>

### <a name="dimension-statement-with-simulation"></a><span data-ttu-id="85d4b-157">Rendiconto dimensioni con simulazione</span><span class="sxs-lookup"><span data-stu-id="85d4b-157">Dimension statement with simulation</span></span>

1. <span data-ttu-id="85d4b-158">Selezionare **Contabilità generale** > **Richieste di informazioni e report** > **Report di contabilità generale** > **Rendiconto dimensioni con simulazione**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-158">Go to **General Ledger** > **Inquiries and reports** > **Ledger reports** > **Dimension statement with simulation**.</span></span>
2. <span data-ttu-id="85d4b-159">Impostare **Transazioni giornale di registrazione di simulazione** su **Sì** nella finestra di dialogo **Rendiconto per dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-159">Set **Simulation journal transactions** to **Yes** in the **Statement by dimension** dialog menu.</span></span>
3. <span data-ttu-id="85d4b-160">Selezionare un valore nel campo **Gruppo di giornali di registrazione di simulazione** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="85d4b-160">Select a value in the **Simulation journal group** field, and then select **OK**.</span></span>
4. <span data-ttu-id="85d4b-161">Verificare che il report contenga transazioni di simulazione registrate e transazioni di contabilità generale standard.</span><span class="sxs-lookup"><span data-stu-id="85d4b-161">Verify that the report contains posted simulation transactions and standard ledger transactions.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]