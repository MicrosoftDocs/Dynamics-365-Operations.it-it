---
title: Abilitare la stampa di etichette targa
description: In questo argomento viene descritto come abilitare la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e548e5e5528733412d47478dd740b87217cdac2
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016104"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="dd260-103">Abilitare la stampa di etichette targa</span><span class="sxs-lookup"><span data-stu-id="dd260-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd260-104">In questo argomento viene descritto come abilitare la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.</span><span class="sxs-lookup"><span data-stu-id="dd260-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="dd260-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="dd260-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="dd260-106">Se tale procedura è stata eseguita utilizzando i propri dati, è necessario disporre di una sequenza numerica impostata per le targhe.</span><span class="sxs-lookup"><span data-stu-id="dd260-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="dd260-107">È necessario impostare una stampante di etichette prima di iniziare questa attività.</span><span class="sxs-lookup"><span data-stu-id="dd260-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="dd260-108">Fare clic su Amministrazione organizzazione > Impostazioni > Stampanti di rete.</span><span class="sxs-lookup"><span data-stu-id="dd260-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="dd260-109">Nel riquadro azioni, fai clic su Opzioni, quindi sul pulsante del programma di installazione dell'agente di distribuzione Scarica documento.</span><span class="sxs-lookup"><span data-stu-id="dd260-109">On the Action Pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="dd260-110">Eseguire il programma di installazione e assicurarsi di disporre di una stampante di rete operativa impostata su Attiva prima di continuare con la procedura.</span><span class="sxs-lookup"><span data-stu-id="dd260-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="dd260-111">Imposta il prefisso della società GS1</span><span class="sxs-lookup"><span data-stu-id="dd260-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="dd260-112">Andare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="dd260-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="dd260-113">Nel campo **Prefisso società GS1** immettere i 7 numeri per il numero di società GS1.</span><span class="sxs-lookup"><span data-stu-id="dd260-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="dd260-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd260-114">Select **Save**.</span></span>
4. <span data-ttu-id="dd260-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd260-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="dd260-116">Imposta la sequenza del numero di identificazione SSCC</span><span class="sxs-lookup"><span data-stu-id="dd260-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="dd260-117">Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche**.</span><span class="sxs-lookup"><span data-stu-id="dd260-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="dd260-118">Selezionare un'opzione nel campo **Area**.</span><span class="sxs-lookup"><span data-stu-id="dd260-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="dd260-119">Selezionare un'opzione nel campo **Riferimento**.</span><span class="sxs-lookup"><span data-stu-id="dd260-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="dd260-120">Digitare un valore nel campo **Società**.</span><span class="sxs-lookup"><span data-stu-id="dd260-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="dd260-121">Espandere la sezione **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="dd260-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="dd260-122">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="dd260-122">Select **Edit**.</span></span>
7. <span data-ttu-id="dd260-123">Nella tabella **Segmenti** , selezionare la prima riga.</span><span class="sxs-lookup"><span data-stu-id="dd260-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="dd260-124">Selezione **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="dd260-124">Select **Remove**.</span></span>
9. <span data-ttu-id="dd260-125">Selezione **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="dd260-125">Select **Remove**.</span></span>
10. <span data-ttu-id="dd260-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd260-126">Select **Save**.</span></span>
11. <span data-ttu-id="dd260-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd260-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="dd260-128">Crea il layout di distribuzione dei documenti</span><span class="sxs-lookup"><span data-stu-id="dd260-128">Create the document route layout</span></span>
1. <span data-ttu-id="dd260-129">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Distribuzione documenti > Layout distribuzione documenti**.</span><span class="sxs-lookup"><span data-stu-id="dd260-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="dd260-130">Attiva il layout di SSCC.</span><span class="sxs-lookup"><span data-stu-id="dd260-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="dd260-131">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-131">Select **New**.</span></span>
3. <span data-ttu-id="dd260-132">Digitare un valore nel campo **ID layout**.</span><span class="sxs-lookup"><span data-stu-id="dd260-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="dd260-133">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dd260-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="dd260-134">Selezionare **Inserisci al termine del testo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="dd260-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd260-135">Select **Save**.</span></span>
7. <span data-ttu-id="dd260-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd260-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="dd260-137">Imposta la distribuzione dei documenti</span><span class="sxs-lookup"><span data-stu-id="dd260-137">Set up the document routing</span></span>
1. <span data-ttu-id="dd260-138">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Distribuzione documenti > Distribuzione documenti**.</span><span class="sxs-lookup"><span data-stu-id="dd260-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="dd260-139">Nel campo **Tipo ordine di lavoro** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="dd260-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="dd260-140">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-140">Select **New**.</span></span>
4. <span data-ttu-id="dd260-141">Digitare un valore nel campo **Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="dd260-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="dd260-142">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="dd260-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="dd260-143">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-143">Select **New**.</span></span>
7. <span data-ttu-id="dd260-144">Nel campo **ID layout** , immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd260-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="dd260-145">Nel campo **Nome** selezionare il nome della stampante che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="dd260-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="dd260-146">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd260-146">Select **Save**.</span></span>
10. <span data-ttu-id="dd260-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd260-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="dd260-148">Crea il menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="dd260-148">Create mobile device menu</span></span>
1. <span data-ttu-id="dd260-149">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="dd260-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="dd260-150">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-150">Select **New**.</span></span>
3. <span data-ttu-id="dd260-151">Digitare un valore nel campo **Nome voce di menu**.</span><span class="sxs-lookup"><span data-stu-id="dd260-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="dd260-152">Digitare un valore nel campo **Titolo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="dd260-153">Selezionare un'opzione nel campo **Modalità**.</span><span class="sxs-lookup"><span data-stu-id="dd260-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="dd260-154">Selezionare **Sì** nel campo **Utilizza lavoro esistente**.</span><span class="sxs-lookup"><span data-stu-id="dd260-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="dd260-155">Selezionare **Sì** nel campo **Genera targa**.</span><span class="sxs-lookup"><span data-stu-id="dd260-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="dd260-156">Espandere la sezione **Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="dd260-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="dd260-157">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-157">Select **New**.</span></span>
10. <span data-ttu-id="dd260-158">Nel campo **ID classe lavoro** , digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd260-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="dd260-159">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd260-159">Select **Save**.</span></span>
12. <span data-ttu-id="dd260-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd260-160">Close the page.</span></span>
13. <span data-ttu-id="dd260-161">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="dd260-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="dd260-162">Nella struttura selezionare la voce di menu creata prima.</span><span class="sxs-lookup"><span data-stu-id="dd260-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="dd260-163">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="dd260-163">Select **Edit**.</span></span>
16. <span data-ttu-id="dd260-164">Selezionare la freccia per aggiungere la voce di menu al menu.</span><span class="sxs-lookup"><span data-stu-id="dd260-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="dd260-165">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd260-165">Select **Save**.</span></span>
18. <span data-ttu-id="dd260-166">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd260-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="dd260-167">Aggiorna un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="dd260-167">Update a work template</span></span>
1. <span data-ttu-id="dd260-168">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="dd260-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="dd260-169">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="dd260-169">Select **Edit**.</span></span>
3. <span data-ttu-id="dd260-170">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd260-170">Select **New**.</span></span>
4. <span data-ttu-id="dd260-171">Nel campo **Tipo di lavoro** , selezionare **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="dd260-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="dd260-172">Nel campo **ID classe lavoro** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dd260-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="dd260-173">Selezionare **Sposta su**.</span><span class="sxs-lookup"><span data-stu-id="dd260-173">Select **Move up**.</span></span>
7. <span data-ttu-id="dd260-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dd260-174">Select **Save**.</span></span>
8. <span data-ttu-id="dd260-175">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dd260-175">Close the page.</span></span>

