--- 
title: Impostare le firme elettroniche
description: Utilizzare questa procedure per configurare le firme elettroniche.
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 11fee0b2358e6a2b84c221f8eb06e32c888e5f44
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-electronic-signatures"></a><span data-ttu-id="75154-103">Impostare le firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="75154-103">Set up electronic signatures</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="75154-104">Utilizzare questa procedure per configurare le firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="75154-104">Use this procedure to set up electronic signatures.</span></span> <span data-ttu-id="75154-105">Una firma elettronica consente di confermare l'identità di una persona che sta per avviare o approvare un processo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="75154-105">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="75154-106">La società di dati dimostrativi utilizzata per creare questa procedura è DAT.</span><span class="sxs-lookup"><span data-stu-id="75154-106">The demo data company used to create this procedure is DAT.</span></span>


## <a name="enable-the-electronic-signature-configuration-key"></a><span data-ttu-id="75154-107">Attivare la chiave di configurazione Firma elettronica (SysSign)</span><span class="sxs-lookup"><span data-stu-id="75154-107">Enable the Electronic signature configuration key</span></span>
1. <span data-ttu-id="75154-108">Andare ad Amministrazione sistema > Impostazioni > Configurazione licenza.</span><span class="sxs-lookup"><span data-stu-id="75154-108">Go to System administration > Setup > License configuration.</span></span>
2. <span data-ttu-id="75154-109">Nella struttura espandere "Amministrazione".</span><span class="sxs-lookup"><span data-stu-id="75154-109">In the tree, expand 'Administration'.</span></span>
    * <span data-ttu-id="75154-110">Verificare che la casella di controllo Firma elettronica sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="75154-110">Verify that the Electronic signature check box is selected.</span></span>  
    * <span data-ttu-id="75154-111">Se la casella di controllo della firma elettronica non è selezionata, è necessario attivare la modalità manutenzione.</span><span class="sxs-lookup"><span data-stu-id="75154-111">If the Electronic signature check box is not selected, you must enable maintenance mode.</span></span> <span data-ttu-id="75154-112">È possibile attivare la modalità manutenzione in questo ambiente eseguendo un processo di manutenzione da LCS oppure utilizzando lo strumento Deployment.Setup in locale.</span><span class="sxs-lookup"><span data-stu-id="75154-112">Maintenance mode can be enabled in this environment by running a maintenance job from Lifecycle Services, or by using the Deployment.Setup tool locally.</span></span>  
3. <span data-ttu-id="75154-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="75154-113">Close the page.</span></span>

## <a name="set-up-electronic-signature-parameters"></a><span data-ttu-id="75154-114">Impostare i parametri di firma elettronica</span><span class="sxs-lookup"><span data-stu-id="75154-114">Set up electronic signature parameters</span></span>
1. <span data-ttu-id="75154-115">Andare ad Amministrazione organizzazione > Impostazioni > Firma elettronica > Parametri firma elettronica.</span><span class="sxs-lookup"><span data-stu-id="75154-115">Go to Organization administration > Setup > Electronic signature > Electronic signature parameters.</span></span>
2. <span data-ttu-id="75154-116">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="75154-116">Click Edit.</span></span>
3. <span data-ttu-id="75154-117">Digitare un valore nel campo Preavviso.</span><span class="sxs-lookup"><span data-stu-id="75154-117">In the Notice field, type a value.</span></span>
    * <span data-ttu-id="75154-118">Immettere il testo dell'avviso che verrà inviato ai firmatari quando è richiesta una firma.</span><span class="sxs-lookup"><span data-stu-id="75154-118">Enter the notice that signers will receive when a signature is requested.</span></span> <span data-ttu-id="75154-119">È possibile immettere qualsiasi testo.</span><span class="sxs-lookup"><span data-stu-id="75154-119">You can enter any text.</span></span> <span data-ttu-id="75154-120">Nel testo sono di solito indicate le implicazioni correlate alla firma elettronica di un documento.</span><span class="sxs-lookup"><span data-stu-id="75154-120">Typically, this text tells the user what it means to sign a document electronically.</span></span>  
    * <span data-ttu-id="75154-121">Fare clic sul pulsante Traduzioni per immettere il testo dell'avviso in altre lingue.</span><span class="sxs-lookup"><span data-stu-id="75154-121">If you want to enter the Notice text in additional languages, click the Translations button.</span></span>  
4. <span data-ttu-id="75154-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="75154-122">Click Save.</span></span>
5. <span data-ttu-id="75154-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="75154-123">Close the page.</span></span>

## <a name="set-up-reason-codes-for-electronic-signatures"></a><span data-ttu-id="75154-124">Impostare i codici motivo per le firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="75154-124">Set up reason codes for electronic signatures</span></span>
1. <span data-ttu-id="75154-125">Andare ad Amministrazione organizzazione > Impostazioni > Firma elettronica > Codici motivo firma elettronica.</span><span class="sxs-lookup"><span data-stu-id="75154-125">Go to Organization administration > Setup > Electronic signature > Electronic signature reason codes.</span></span>
2. <span data-ttu-id="75154-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="75154-126">Click New.</span></span>
    * <span data-ttu-id="75154-127">È necessario impostare i codici motivo prima di utilizzare le firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="75154-127">You must set up reason codes before using electronic signatures.</span></span> <span data-ttu-id="75154-128">Per la firma di un documento è richiesto un codice motivo valido.</span><span class="sxs-lookup"><span data-stu-id="75154-128">A valid reason code is required when signing a document.</span></span>     <span data-ttu-id="75154-129">I codici motivo vengono selezionati dai firmatari per indicare lo scopo di una firma elettronica.</span><span class="sxs-lookup"><span data-stu-id="75154-129">A signer selects a reason code to indicate the purpose of an electronic signature.</span></span> <span data-ttu-id="75154-130">È ad esempio possibile utilizzare un codice motivo per indicare un'approvazione legale.</span><span class="sxs-lookup"><span data-stu-id="75154-130">For example, a reason code could be used to indicate legal approval.</span></span>  
3. <span data-ttu-id="75154-131">Digitare un valore nel campo Codice motivo.</span><span class="sxs-lookup"><span data-stu-id="75154-131">In the Reason code field, type a value.</span></span>
4. <span data-ttu-id="75154-132">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="75154-132">In the Description field, type a value.</span></span>
    * <span data-ttu-id="75154-133">Immettere i codici motivo aggiuntivi, se necessario.</span><span class="sxs-lookup"><span data-stu-id="75154-133">Enter additional reason codes, if needed.</span></span>  
5. <span data-ttu-id="75154-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="75154-134">Click Save.</span></span>
6. <span data-ttu-id="75154-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="75154-135">Close the page.</span></span>

## <a name="require-electronic-signatures-for-existing-processes"></a><span data-ttu-id="75154-136">Richiedere le firme elettroniche per un processo esistente</span><span class="sxs-lookup"><span data-stu-id="75154-136">Require electronic signatures for existing processes</span></span>
1. <span data-ttu-id="75154-137">Andare ad Amministrazione organizzazione > Impostazioni > Firma elettronica > Requisiti firma elettronica.</span><span class="sxs-lookup"><span data-stu-id="75154-137">Go to Organization administration > Setup > Electronic signature > Electronic signature requirements.</span></span>
2. <span data-ttu-id="75154-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="75154-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="75154-139">Scegliere un processo per il quale sono richieste le firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="75154-139">Select a process that requires electronic signatures.</span></span>  
3. <span data-ttu-id="75154-140">Selezionare o deselezionare la casella di controllo Firma richiesta.</span><span class="sxs-lookup"><span data-stu-id="75154-140">Select or clear the Signature required check box.</span></span>
    * <span data-ttu-id="75154-141">Ripetere questi passaggi per ogni processo che richiede le firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="75154-141">Repeat these steps for each process that requires electronic signatures.</span></span>  
4. <span data-ttu-id="75154-142">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="75154-142">Click Save.</span></span>

## <a name="create-a-custom-requirement-for-electronic-signatures"></a><span data-ttu-id="75154-143">Creare un requisito personalizzato per le firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="75154-143">Create a custom requirement for electronic signatures</span></span>
1. <span data-ttu-id="75154-144">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="75154-144">Click New.</span></span>
2. <span data-ttu-id="75154-145">Selezionare o deselezionare la casella di controllo Firma richiesta.</span><span class="sxs-lookup"><span data-stu-id="75154-145">Select or clear the Signature required check box.</span></span>
3. <span data-ttu-id="75154-146">Nel campo Nome immettere un nome per il processo che richiede le firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="75154-146">In the Name field, enter a name for the process that requires electronic signatures.</span></span>
4. <span data-ttu-id="75154-147">Nel campo Nome tabella fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="75154-147">In the Table name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="75154-148">Nell'elenco trovare e selezionare la tabella in cui devono essere archiviati i dati da firmare.</span><span class="sxs-lookup"><span data-stu-id="75154-148">In the list, find and select the table where the data that must be signed is stored.</span></span>
6. <span data-ttu-id="75154-149">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="75154-149">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="75154-150">Nel campo Nome campo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="75154-150">In the Field name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="75154-151">Nell'elenco trovare e selezionare il campo della tabella che si desidera monitorare.</span><span class="sxs-lookup"><span data-stu-id="75154-151">In the list, find and select the field in the table that you want to monitor.</span></span>
9. <span data-ttu-id="75154-152">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="75154-152">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="75154-153">Specificare le situazioni in cui è necessaria una firma.</span><span class="sxs-lookup"><span data-stu-id="75154-153">Specify when a signature is required.</span></span>     <span data-ttu-id="75154-154">Selezionare Sempre se è necessaria una firma ogni volta che i dati nel campo cambiano.</span><span class="sxs-lookup"><span data-stu-id="75154-154">Select Always if a signature is required when the data in the field changes.</span></span>     <span data-ttu-id="75154-155">Selezionare Solo se la firma è necessaria solo a certe condizioni.</span><span class="sxs-lookup"><span data-stu-id="75154-155">Select Only if a signature is required only under certain conditions.</span></span> <span data-ttu-id="75154-156">Se si seleziona Solo, è necessario selezionare anche una delle seguenti opzioni: Inserimento di un record, Aggiornamento di un record o Eliminazione di un record.</span><span class="sxs-lookup"><span data-stu-id="75154-156">If you select Only, you must also select one of the following options: When a record is inserted, When a record is updated, or When a record is deleted.</span></span>  
10. <span data-ttu-id="75154-157">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="75154-157">Click Save.</span></span>
11. <span data-ttu-id="75154-158">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="75154-158">Close the page.</span></span>

