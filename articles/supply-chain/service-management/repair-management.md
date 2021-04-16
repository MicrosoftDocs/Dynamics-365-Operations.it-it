---
title: Gestione delle riparazioni
description: Raggruppare i problemi sistematicamente per semplificare l'individuazione delle soluzioni di problemi analoghi avvenuti in passato.
author: ShylaThompson
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d0c6ee65713af86378ada79075f969a41f1c0ad
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836016"
---
# <a name="repair-management"></a><span data-ttu-id="cf671-103">Gestione delle riparazioni</span><span class="sxs-lookup"><span data-stu-id="cf671-103">Repair management</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="cf671-104">Per la gestione delle riparazioni è possibile raggruppare i problemi in modo sistematico.</span><span class="sxs-lookup"><span data-stu-id="cf671-104">For repair management you can group problems systematically.</span></span> <span data-ttu-id="cf671-105">Ciò agevola l'individuazione di soluzioni rivelatesi utili in passato.</span><span class="sxs-lookup"><span data-stu-id="cf671-105">This is to help with the suggestion of solutions that have been successful in the past.</span></span>

<span data-ttu-id="cf671-106">È necessario definire le impostazioni di sintomi, diagnosi e soluzioni.</span><span class="sxs-lookup"><span data-stu-id="cf671-106">You set up symptoms, diagnosis, and resolution settings.</span></span> <span data-ttu-id="cf671-107">Queste potranno essere applicate in un secondo momento quando si riceve un articolo simile per la riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-107">All these can later be applied when you receive a similar item for repair.</span></span> <span data-ttu-id="cf671-108">È inoltre possibile impostare fasi di riparazione, allo scopo di seguire l'avanzamento della riparazione stessa.</span><span class="sxs-lookup"><span data-stu-id="cf671-108">You can also set up repair stages that can follow the progress of a repair issue.</span></span>

## <a name="setting-up-repair-management"></a><span data-ttu-id="cf671-109">Impostazione della gestione riparazione</span><span class="sxs-lookup"><span data-stu-id="cf671-109">Setting up repair management</span></span>

<span data-ttu-id="cf671-110">Utilizzare i seguenti moduli di impostazione per immettere informazioni che verranno utilizzate per specificare i sintomi, la diagnosi e la soluzione per la riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-110">Use the following setup forms to enter information that will be used to specify the symptoms, the diagnosis, and the resolution, of the repair.</span></span>

- <span data-ttu-id="cf671-111">**Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Condizioni**.</span><span class="sxs-lookup"><span data-stu-id="cf671-111">**Service management** \> **Setup** \> **Repair** \> **Conditions**.</span></span>
- <span data-ttu-id="cf671-112">**Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Aree sintomo**.</span><span class="sxs-lookup"><span data-stu-id="cf671-112">**Service management** \> **Setup** \> **Repair** \> **Symptom areas**.</span></span>
-  <span data-ttu-id="cf671-113">**Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Aree diagnosi**.</span><span class="sxs-lookup"><span data-stu-id="cf671-113">**Service management** \> **Setup** \> **Repair** \> **Diagnosis areas**.</span></span>
- <span data-ttu-id="cf671-114">**Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="cf671-114">**Service management** \> **Setup** \> **Repair** \> **Resolutions**.</span></span>
- <span data-ttu-id="cf671-115">**Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Fasi riparazione**.</span><span class="sxs-lookup"><span data-stu-id="cf671-115">**Service management** \> **Setup** \> **Repair** \> **Repair stages**.</span></span>

## <a name="symptoms-and-conditions"></a><span data-ttu-id="cf671-116">Sintomi e condizioni</span><span class="sxs-lookup"><span data-stu-id="cf671-116">Symptoms and conditions</span></span>

<span data-ttu-id="cf671-117">Per sintomi si intendono le caratteristiche del problema così come vengono indicate dal cliente.</span><span class="sxs-lookup"><span data-stu-id="cf671-117">Symptoms are how the customer characterizes the problem.</span></span> <span data-ttu-id="cf671-118">I sintomi comprendono anche le osservazioni del cliente che indicano la necessità della riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-118">Symptoms include the customer observations that indicate the need for repair.</span></span>

<span data-ttu-id="cf671-119">È possibile impostare aree sintomo, codici sintomo e condizioni.</span><span class="sxs-lookup"><span data-stu-id="cf671-119">You can set up symptom areas, symptom codes, and conditions.</span></span> <span data-ttu-id="cf671-120">L'area sintomo riguarda l'area del malfunzionamento e il codice sintomo riguarda il sintomo del malfunzionamento.</span><span class="sxs-lookup"><span data-stu-id="cf671-120">The symptom area covers the area of malfunction, and the symptom code covers the malfunction symptom.</span></span> <span data-ttu-id="cf671-121">Le condizioni descrivono la situazione o ambiente in cui si è verificato il problema.</span><span class="sxs-lookup"><span data-stu-id="cf671-121">The condition describes the situation or environment that is present when the problem occurs.</span></span>

<span data-ttu-id="cf671-122">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cf671-122">**Example**</span></span>

<span data-ttu-id="cf671-123">Un computer viene inviato in riparazione a causa di un malfunzionamento del disco rigido che si verifica in seguito a lunghi periodi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="cf671-123">A computer is brought in for repair because the hard drive fails after an extended period of use.</span></span> <span data-ttu-id="cf671-124">L'errore del disco rigido causa la visualizzazione di una schermata blu.</span><span class="sxs-lookup"><span data-stu-id="cf671-124">The hard drive failure causes a blue screen error.</span></span> <span data-ttu-id="cf671-125">Il tecnico che riceve il computer immette i seguenti sintomi e condizioni:</span><span class="sxs-lookup"><span data-stu-id="cf671-125">The technician who receives the computer enters the following symptoms and conditions:</span></span>

1.  <span data-ttu-id="cf671-126">L'area sintomo è il disco rigido</span><span class="sxs-lookup"><span data-stu-id="cf671-126">The symptom area is the hard drive</span></span>

2.  <span data-ttu-id="cf671-127">Il codice sintomo è la visualizzazione della schermata blu</span><span class="sxs-lookup"><span data-stu-id="cf671-127">The symptom code is the blue screen error</span></span>

3.  <span data-ttu-id="cf671-128">Le condizioni sono l'utilizzo prolungato che dà origine all'errore del disco rigido</span><span class="sxs-lookup"><span data-stu-id="cf671-128">The condition is that the hard drive fails after extended use</span></span>

## <a name="diagnosis-and-resolutions"></a><span data-ttu-id="cf671-129">Diagnosi e soluzioni</span><span class="sxs-lookup"><span data-stu-id="cf671-129">Diagnosis and resolutions</span></span>

<span data-ttu-id="cf671-130">I campi relativi alla diagnosi e alle soluzioni contengono descrizioni di carattere tecnico,</span><span class="sxs-lookup"><span data-stu-id="cf671-130">The diagnosis and resolution fields are statements from the repair perspective.</span></span> <span data-ttu-id="cf671-131">ovvero i diversi passaggi attraverso i quali il tecnico ha individuato il problema.</span><span class="sxs-lookup"><span data-stu-id="cf671-131">These are the steps that a technician went through to investigate the problem.</span></span>

<span data-ttu-id="cf671-132">L'area diagnostica riguarda l'operazione che deve essere effettuata per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="cf671-132">The diagnosis area covers the operation that must occur to solve the issue.</span></span> <span data-ttu-id="cf671-133">Il codice diagnostico indica come è stato gestito il problema, mentre la soluzione può indicare che l'articolo è stato riparato, sostituito o che l'ordine è stato annullato dal cliente.</span><span class="sxs-lookup"><span data-stu-id="cf671-133">The diagnosis code is how the problem was handled, and the resolution could be that the item was repaired, replaced, or the order was canceled by the customer.</span></span> <span data-ttu-id="cf671-134">Se ad esempio il computer viene riparato, l'area diagnostica, il codice diagnostico e la soluzione potrebbero corrispondere rispettivamente a "componente difettoso", "nuova scheda video installata" e "sostituito".</span><span class="sxs-lookup"><span data-stu-id="cf671-134">For example, if the computer is repaired, the diagnosis area could be "defective part," the diagnosis code could be "new video card installed," and the resolution could be "replaced."</span></span>

## <a name="repair-stages"></a><span data-ttu-id="cf671-135">Fasi di riparazione</span><span class="sxs-lookup"><span data-stu-id="cf671-135">Repair stages</span></span>

<span data-ttu-id="cf671-136">Le fasi di riparazione indicano l'avanzamento del processo di riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-136">Repair stages state the progress of the repair process.</span></span> <span data-ttu-id="cf671-137">Ogni fase di riparazione dispone del parametro di approvazione **Completato**, che indica il completamento della riga di riparazione e nel quale vengono registrate la data e l'ora di completamento.</span><span class="sxs-lookup"><span data-stu-id="cf671-137">The repair stage has a **Finished** sign-off parameter that indicates that the repair line has been completed, and the finishing date and time has been recorded.</span></span>

## <a name="applying-repair-management"></a><span data-ttu-id="cf671-138">Applicazione della gestione delle riparazioni</span><span class="sxs-lookup"><span data-stu-id="cf671-138">Applying repair management</span></span>

<span data-ttu-id="cf671-139">Per applicare la gestione delle riparazioni a un articolo, quest'ultimo deve essere impostato con una relazione oggetto assistenza in un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="cf671-139">To apply repair management to an item, the item must be set up with a service object relation on a service order.</span></span> <span data-ttu-id="cf671-140">Dall'ordine di assistenza è quindi possibile creare una riga di riparazione con le informazioni relative al problema.</span><span class="sxs-lookup"><span data-stu-id="cf671-140">From the service order you can then create a repair line with information about the current issue.</span></span> <span data-ttu-id="cf671-141">Nella riga di riparazione è necessario definire l'oggetto assistenza in riparazione e inserire le informazioni relative ai sintomi, alla diagnosi e all'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cf671-141">On the repair line you define the service object that is in repair and information about symptoms, diagnosis, and execution.</span></span> <span data-ttu-id="cf671-142">È inoltre possibile creare una nota per la riga di riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-142">You can also create a note for the repair line.</span></span>

<span data-ttu-id="cf671-143">È possibile creare righe di riparazione per ogni fase del processo di riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-143">You can create repair lines for each step in the repair process.</span></span>

## <a name="create-a-repair-line-on-a-service-order"></a><span data-ttu-id="cf671-144">Creazione di una riga di riparazione in un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="cf671-144">Create a repair line on a service order</span></span>

1.  <span data-ttu-id="cf671-145">Selezionare **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="cf671-145">Go to **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="cf671-146">Selezionare l'ordine di assistenza con l'oggetto assistenza per il quale è necessaria una riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-146">Select the service order with the service object that needs repair.</span></span>

3.  <span data-ttu-id="cf671-147">Selezionare **Riparazione** \> **Righe riparazione** per aprire il modulo **Righe riparazione**.</span><span class="sxs-lookup"><span data-stu-id="cf671-147">Select **Repair** \> **Repair lines** to open the **Repair lines** form.</span></span>

4.  <span data-ttu-id="cf671-148">Selezionare **Nuovo** per creare una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="cf671-148">Select **New** to create a new line.</span></span>

5.  <span data-ttu-id="cf671-149">Selezionare un oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="cf671-149">Select a service object.</span></span> <span data-ttu-id="cf671-150">È possibile selezionare qualsiasi oggetto assistenza impostato con una relazione oggetto nell'ordine di servizio.</span><span class="sxs-lookup"><span data-stu-id="cf671-150">You can select any service object that has been set up with an object relation on the service order.</span></span>

6.  <span data-ttu-id="cf671-151">Selezionare i valori appropriati tra quelli predefiniti relativi a sintomi, diagnosi ed esecuzione per la riga di riparazione e, se necessario, selezionare la scheda **Nota** per creare una nota nella riga di riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-151">Select any of the preset symptoms, diagnosis, and execution values that are relevant in the repair line and then select the **Note** tab to create a note on the repair line, if needed.</span></span>

7.  <span data-ttu-id="cf671-152">Selezionare **Salva** per salvare la nuova riga di riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-152">Select **Save** to save the new repair line.</span></span> <span data-ttu-id="cf671-153">Il campo **Data e ora creazione** nella scheda **Generale** del modulo **Righe riparazione** viene aggiornato con la data e l'ora del salvataggio.</span><span class="sxs-lookup"><span data-stu-id="cf671-153">The **Created date and time** field in the **General** tab of the **Repair lines** form is updated with the time of saving.</span></span>

## <a name="tracking-progress-and-resolving-a-repair-issue"></a><span data-ttu-id="cf671-154">Stato di avanzamento e risoluzione di una riparazione</span><span class="sxs-lookup"><span data-stu-id="cf671-154">Tracking progress and resolving a repair issue</span></span>

<span data-ttu-id="cf671-155">Per seguire l'avanzamento di una riparazione, è possibile impostare le relative fasi in modo da seguire l'avanzamento della riparazione stessa.</span><span class="sxs-lookup"><span data-stu-id="cf671-155">You can set the repair stages of a repair line to track the progress of the repair.</span></span>

<span data-ttu-id="cf671-156">Quando una riparazione è risolta, è possibile chiudere la relativa riga di riparazione.</span><span class="sxs-lookup"><span data-stu-id="cf671-156">When a repair issue is resolved, you can close the repair line.</span></span> <span data-ttu-id="cf671-157">Impostare la fase di riparazione su una fase con la proprietà **Completato** abilitata.</span><span class="sxs-lookup"><span data-stu-id="cf671-157">Set the repair stage to a stage with a **Finished** property enabled.</span></span> <span data-ttu-id="cf671-158">La data e l'ora correnti vengono registrate nella riga come data e ora di conclusione.</span><span class="sxs-lookup"><span data-stu-id="cf671-158">The current date and time is registered as the finish time on the line.</span></span>

## <a name="close-a-repair-line-for-a-resolved-issue"></a><span data-ttu-id="cf671-159">Chiusura di una riga di riparazione per un problema risolto</span><span class="sxs-lookup"><span data-stu-id="cf671-159">Close a repair line for a resolved issue</span></span>

1.  <span data-ttu-id="cf671-160">Apri il modulo **Righe riparazione**.</span><span class="sxs-lookup"><span data-stu-id="cf671-160">Open the **Repair lines** form.</span></span> <span data-ttu-id="cf671-161">Seguire la procedura di creazione di una riga di riparazione, descritta in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="cf671-161">Follow the procedure earlier in this topic to create a repair line.</span></span>

2.  <span data-ttu-id="cf671-162">Selezionare la riga di riparazione contenente il problema che si desidera chiudere.</span><span class="sxs-lookup"><span data-stu-id="cf671-162">Select the repair line with the repair issue that you want to close.</span></span>

3.  <span data-ttu-id="cf671-163">Nel campo **Fase riparazione** selezionare una fase con la proprietà **Completato** attivata.</span><span class="sxs-lookup"><span data-stu-id="cf671-163">In the **Repair stage** field, select a stage with the **Finished** property enabled.</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]