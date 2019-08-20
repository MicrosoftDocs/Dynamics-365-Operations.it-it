---
title: Elaborare lettere di sollecito
description: Questa procedura indica come creare, stampare e registrare le lettere di sollecito.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 8db80b184d565f71f62f99051c7378c4e6e45fb9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834417"
---
# <a name="process-collection-letters"></a><span data-ttu-id="f0293-103">Elaborare lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="f0293-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f0293-104">Questa procedura indica come creare, stampare e registrare le lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="f0293-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="f0293-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="f0293-106">Impostare una sequenza di lettere di sollecito nel profilo registrazione</span><span class="sxs-lookup"><span data-stu-id="f0293-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="f0293-107">Andare a **Crediti e riscossioni > Impostazione > Profili di registrazione cliente**.</span><span class="sxs-lookup"><span data-stu-id="f0293-107">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="f0293-108">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f0293-108">Click **Edit**.</span></span>
3. <span data-ttu-id="f0293-109">Selezionare una sequenza di lettere di sollecito dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="f0293-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="f0293-110">Se non si desidera generare lettere di sollecito per le transazioni che utilizzano il profilo registrazione, lasciare vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="f0293-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="f0293-111">Espandere la scheda delle restrizioni della tabella per modificare la modalità per l'elaborazione delle lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-111">Expand the table restriction tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="f0293-112">Se questo campo è impostato su **Sì**, le lettere di sollecito verranno create per il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="f0293-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="f0293-113">Crea lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="f0293-113">Create collection letters</span></span>
1. <span data-ttu-id="f0293-114">Andare a **Crediti e riscossioni > Lettera di sollecito > Crea lettere di sollecito**.</span><span class="sxs-lookup"><span data-stu-id="f0293-114">Go to **Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="f0293-115">Selezionare i tipi di transazione per cui si raccoglieranno le lettere.</span><span class="sxs-lookup"><span data-stu-id="f0293-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="f0293-116">Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="f0293-116">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="f0293-117">Selezionare una opzione nel campo **Lettera di sollecito**.</span><span class="sxs-lookup"><span data-stu-id="f0293-117">In the **Collection letter** field, select an option.</span></span>
3. <span data-ttu-id="f0293-118">Immettere la data della lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-118">Enter the date of the collection letter.</span></span>
4. <span data-ttu-id="f0293-119">Selezionare un profilo registrazione se **Utilizza profilo registrazione da** è stato impostato su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="f0293-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="f0293-120">Sono disponibili due opzioni di profilo di registrazione:</span><span class="sxs-lookup"><span data-stu-id="f0293-120">There are two posting profile options:</span></span>   
   - <span data-ttu-id="f0293-121">**Conto**: consente di utilizzare il profilo di registrazione assegnato al conto cliente per ogni nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f0293-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="f0293-122">**Seleziona**: consente di utilizzare il profilo di registrazione selezionato nel campo **Profilo registrazione**.</span><span class="sxs-lookup"><span data-stu-id="f0293-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  
5. <span data-ttu-id="f0293-123">Espandere la sezione **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="f0293-123">Expand the **Records to include** section.</span></span>
6. <span data-ttu-id="f0293-124">Fare clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f0293-124">Click **Filter**.</span></span>
7. <span data-ttu-id="f0293-125">Nel campo **Criteri**, immettere un ID cliente.</span><span class="sxs-lookup"><span data-stu-id="f0293-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="f0293-126">Ad esempio, immettere "US-001".</span><span class="sxs-lookup"><span data-stu-id="f0293-126">For example, enter 'US-001'.</span></span>
8. <span data-ttu-id="f0293-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0293-127">Click **OK**.</span></span>
9. <span data-ttu-id="f0293-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0293-128">Click **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="f0293-129">Stampare le lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="f0293-129">Print collection letters</span></span>
1. <span data-ttu-id="f0293-130">Andare a **Crediti e riscossioni > Lettera di sollecito > Esamina ed elabora lettere di sollecito**.</span><span class="sxs-lookup"><span data-stu-id="f0293-130">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="f0293-131">Nel campo **Stato** selezionare **Creata**.</span><span class="sxs-lookup"><span data-stu-id="f0293-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="f0293-132">Nel campo **Stampata** selezionare **Non stampata**.</span><span class="sxs-lookup"><span data-stu-id="f0293-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="f0293-133">Fare clic su **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="f0293-133">Click **Print**.</span></span>
5. <span data-ttu-id="f0293-134">Fare clic su **Nota lettera di sollecito**.</span><span class="sxs-lookup"><span data-stu-id="f0293-134">Click **Collection letter note**.</span></span>
6. <span data-ttu-id="f0293-135">Espandere la sezione **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="f0293-135">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="f0293-136">Specificare la data limite per le registrazioni.</span><span class="sxs-lookup"><span data-stu-id="f0293-136">Enter the cutoff date for postings.</span></span>
8. <span data-ttu-id="f0293-137">Fare clic su **OK** per stampare la lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-137">Click **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="f0293-138">Registrare la lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-138">Post the collection letter.</span></span>
   1. <span data-ttu-id="f0293-139">Fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="f0293-139">Click **Post**.</span></span>
   2. <span data-ttu-id="f0293-140">Immettere la data di registrazione per la lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-140">Enter the posting date for the collection letter.</span></span>
   3. <span data-ttu-id="f0293-141">Espandere la sezione **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="f0293-141">Expand the **Records to include** section.</span></span>
   4. <span data-ttu-id="f0293-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0293-142">Click **OK**.</span></span>
   5. <span data-ttu-id="f0293-143">Nel campo **Stato** selezionare **Registrata**.</span><span class="sxs-lookup"><span data-stu-id="f0293-143">In the **Status** field, select **Posted**.</span></span>
   6. <span data-ttu-id="f0293-144">Selezionare un'opzione nel campo **Stampata**.</span><span class="sxs-lookup"><span data-stu-id="f0293-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="f0293-145">Controllare lettere di sollecito a livello del cliente</span><span class="sxs-lookup"><span data-stu-id="f0293-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="f0293-146">È anche possibile configurare lettere di sollecito a livello del cliente in modo da tenere traccia del codice di lettera di sollecito per ogni transazione, ma l'elaborazione delle lettere di sollecito sarà basata su una singola lettera di sollecito archiviata per il cliente.</span><span class="sxs-lookup"><span data-stu-id="f0293-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="f0293-147">La singola lettera di sollecito conterrà tutte le transazioni insolute per il cliente.</span><span class="sxs-lookup"><span data-stu-id="f0293-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="f0293-148">Poiché ora si tiene traccia dei giorni di tolleranza a livello del cliente, la lettera di sollecito successiva non verrà inviata fino a che il numero di giorni di tolleranza non è passato per la lettera di sollecito successiva nella sequenza, anche se le transazioni diventano insolute dopo l'invio dell'ultima lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="f0293-149">Questa opzione riduce il numero di lettere di sollecito inviate per cliente.</span><span class="sxs-lookup"><span data-stu-id="f0293-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="f0293-150">Configurare il cliente per controllare lettere di sollecito a livello del cliente</span><span class="sxs-lookup"><span data-stu-id="f0293-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="f0293-151">Andare a **Crediti e le riscossioni > Impostazioni > Parametri contabilità clienti** e fare clic sulla scheda **Riscossioni**.</span><span class="sxs-lookup"><span data-stu-id="f0293-151">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2.  <span data-ttu-id="f0293-152">Impostare **Crea una lettera di sollecito per** su **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="f0293-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="f0293-153">Andare a **Crediti e riscossioni > Lettera di sollecito > Esamina ed elabora lettere di sollecito**.</span><span class="sxs-lookup"><span data-stu-id="f0293-153">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="f0293-154">Per un cliente con tutte le transazioni insolute verrà generata una sola lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="f0293-155">Ignorare pagamenti e note di credito durante il calcolo del codice di lettera di sollecito</span><span class="sxs-lookup"><span data-stu-id="f0293-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="f0293-156">Se si includono pagamenti e note di credito nelle transazioni che saranno incluse nelle lettere di sollecito, è possibile avere pagamenti o note di credito che genereranno una lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="f0293-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="f0293-157">È possibile controllare il modo in cui pagamenti e note di credito controllano il codice di lettera di sollecito modificando il valore del parametro **Ignora pagamenti e note credito durante il calcolo del codice di lettera di sollecito**.</span><span class="sxs-lookup"><span data-stu-id="f0293-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="f0293-158">Per ignorare pagamenti e note credito durante il calcolo del codice di lettera di sollecito, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="f0293-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>
1. <span data-ttu-id="f0293-159">Andare a **Crediti e le riscossioni > Impostazioni > Parametri contabilità clienti** e fare clic sulla scheda **Riscossioni**.</span><span class="sxs-lookup"><span data-stu-id="f0293-159">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="f0293-160">Impostare **Ignora pagamenti e note credito durante il calcolo del codice di lettera di sollecito** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f0293-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>
