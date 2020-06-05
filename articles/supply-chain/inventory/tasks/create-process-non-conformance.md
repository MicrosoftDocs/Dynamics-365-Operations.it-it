---
title: Creare ed elaborare una conformità
description: In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bf20ed737707b7cf99023e3c78489caf4a68eab
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383621"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="723bd-103">Creare ed elaborare una conformità</span><span class="sxs-lookup"><span data-stu-id="723bd-103">Create and process a conformance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="723bd-104">In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.</span><span class="sxs-lookup"><span data-stu-id="723bd-104">This topic explains how to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="723bd-105">È possibile eseguire questa registrazione nella società dimostrativa USMF e utilizzare i valori suggeriti.</span><span class="sxs-lookup"><span data-stu-id="723bd-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="723bd-106">In genere, questa procedura viene eseguita da un addetto al controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="723bd-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="723bd-107">Come prerequisito, completare le istruzioni in [Verificare la qualità delle merci](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="723bd-107">As a prerequisite, complete the instructions in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span> <span data-ttu-id="723bd-108">Per elaborare l'approvazione di una non conformità, l'utente che esegue la registrazione attività deve avere un valore "Nome" assegnato nella pagina Utenti.</span><span class="sxs-lookup"><span data-stu-id="723bd-108">To process the approval of a nonconformance, the user who runs the task recording must have a "Name" value assigned on the Users page.</span></span> <span data-ttu-id="723bd-109">Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="723bd-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="723bd-110">Selezionare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="723bd-110">Select a quality order</span></span>
1. <span data-ttu-id="723bd-111">Nel pannello di navigazione andare a **Moduli > Gestione articoli > Attività periodiche > Gestione qualità > Ordini di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="723bd-111">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="723bd-112">Nell'elenco, selezionare l'ordine di controllo qualità creato in [Verificare la qualità delle merci](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="723bd-112">In the list, select the quality order that was created in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="723bd-113">Creare una non conformità</span><span class="sxs-lookup"><span data-stu-id="723bd-113">Create a nonconformance</span></span>
1. <span data-ttu-id="723bd-114">Nel riquadro azioni, seleziona **Informazioni**.</span><span class="sxs-lookup"><span data-stu-id="723bd-114">On the Action Pane, select **Inquiries**.</span></span>
2. <span data-ttu-id="723bd-115">Selezionare **Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="723bd-115">Select **Non conformances**.</span></span>
3. <span data-ttu-id="723bd-116">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="723bd-116">Select **New**.</span></span>
4. <span data-ttu-id="723bd-117">Nel menu a discesa del campo **Tipi di problema**, selezionare il problema individuato durante il processo di ispezione.</span><span class="sxs-lookup"><span data-stu-id="723bd-117">In the drop-down menu of the **Problem type** field, select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="723bd-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="723bd-118">Select **OK**.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="723bd-119">Approvare/respingere una non conformità</span><span class="sxs-lookup"><span data-stu-id="723bd-119">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="723bd-120">Selezionare **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="723bd-120">Select **Functions**.</span></span>
2. <span data-ttu-id="723bd-121">Selezionare **Approva non conformità**.</span><span class="sxs-lookup"><span data-stu-id="723bd-121">Select **Approve non conformance**.</span></span> <span data-ttu-id="723bd-122">Per questo esempio, approvare la non conformità.</span><span class="sxs-lookup"><span data-stu-id="723bd-122">For this example, approve the nonconformance.</span></span> <span data-ttu-id="723bd-123">Le non conformità approvate possono essere associate alle operazioni correlate per la registrazione del lavoro che viene eseguito nell'ambito della gestione di non conformità e, come in questo argomento, l'elaborazione della gestione della correzione.</span><span class="sxs-lookup"><span data-stu-id="723bd-123">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this topic, the processing of correction handling.</span></span>  
3. <span data-ttu-id="723bd-124">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="723bd-124">Select **Yes**.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="723bd-125">Creare un'azione correttiva</span><span class="sxs-lookup"><span data-stu-id="723bd-125">Create a correction action</span></span>
1. <span data-ttu-id="723bd-126">Selezionare **Correzioni**.</span><span class="sxs-lookup"><span data-stu-id="723bd-126">Select **Corrections**.</span></span>
2. <span data-ttu-id="723bd-127">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="723bd-127">Select **New**.</span></span>
3. <span data-ttu-id="723bd-128">Nel campo **Numero dipendente** della nuova riga, selezionare il record desiderato dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="723bd-128">In the **Personnel number** field of the new row, select the desired record from the drop down menu.</span></span>
4. <span data-ttu-id="723bd-129">Fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="723bd-129">Click **Select**.</span></span>
5. <span data-ttu-id="723bd-130">Selezionare **Allega**.</span><span class="sxs-lookup"><span data-stu-id="723bd-130">Select **Attach**.</span></span> <span data-ttu-id="723bd-131">Creare una nota sulla correzione.</span><span class="sxs-lookup"><span data-stu-id="723bd-131">Create a note about the correction.</span></span> <span data-ttu-id="723bd-132">Per questo esempio l'azione è di contattare il fornitore per discutere il caso di non conformità.</span><span class="sxs-lookup"><span data-stu-id="723bd-132">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
6. <span data-ttu-id="723bd-133">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="723bd-133">Select **New**.</span></span>
7. <span data-ttu-id="723bd-134">Selezionare **Nota**.</span><span class="sxs-lookup"><span data-stu-id="723bd-134">Select **Note**.</span></span> <span data-ttu-id="723bd-135">A seconda dell'impostazione del report, i tipi di documento possono essere stampati nei report correlati alla gestione di non conformità.</span><span class="sxs-lookup"><span data-stu-id="723bd-135">Depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
8. <span data-ttu-id="723bd-136">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="723bd-136">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="723bd-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="723bd-137">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="723bd-138">Gestire una correzione</span><span class="sxs-lookup"><span data-stu-id="723bd-138">Maintain a correction</span></span>
1. <span data-ttu-id="723bd-139">Selezionare **Contrassegna come completata**.</span><span class="sxs-lookup"><span data-stu-id="723bd-139">Select **Mark complete**.</span></span>
2. <span data-ttu-id="723bd-140">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="723bd-140">Select **OK**.</span></span>
3. <span data-ttu-id="723bd-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="723bd-141">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="723bd-142">Chiudere una non conformità</span><span class="sxs-lookup"><span data-stu-id="723bd-142">Close a nonconformance</span></span>
1. <span data-ttu-id="723bd-143">Selezionare **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="723bd-143">Select **Functions**.</span></span>
2. <span data-ttu-id="723bd-144">Selezionare **Chiudi non conformità**.</span><span class="sxs-lookup"><span data-stu-id="723bd-144">Select **Close non conformance**.</span></span>
3. <span data-ttu-id="723bd-145">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="723bd-145">Select **Yes**.</span></span>
4. <span data-ttu-id="723bd-146">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="723bd-146">Close the pages.</span></span>
