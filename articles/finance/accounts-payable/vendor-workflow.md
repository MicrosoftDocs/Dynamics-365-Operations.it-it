---
title: Flusso di lavoro fornitori
description: Modificare le informazioni sul fornitore e utilizzare il flusso di lavoro per approvarle.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: afda0ead11ec1adac2d436511eef8165a7f0aed2
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189271"
---
# <a name="vendor-workflow"></a><span data-ttu-id="60801-103">Flusso di lavoro fornitori</span><span class="sxs-lookup"><span data-stu-id="60801-103">Vendor workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60801-104">Quando viene utilizzato il flusso di lavoro fornitori, le modifiche apportate a campi specifici vengono inviate al flusso di lavoro per l'approvazione prima che vengano aggiunte al fornitore.</span><span class="sxs-lookup"><span data-stu-id="60801-104">When the vendor workflow is used, changes that are made to specific fields are sent to the workflow for approval before they are added to the vendor.</span></span>

## <a name="set-up-the-vendor-workflow"></a><span data-ttu-id="60801-105">Impostare il flusso di lavoro fornitori</span><span class="sxs-lookup"><span data-stu-id="60801-105">Set up the vendor workflow</span></span>

<span data-ttu-id="60801-106">Prima di poter utilizzare la funzionalità del flusso di lavoro, è necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="60801-106">Before you can use the workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="60801-107">Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="60801-107">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="60801-108">Nella scheda **Generale**, nella Scheda dettaglio **Approvazione fornitore**, impostare l'opzione **Abilita approvazioni fornitore** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="60801-108">On the **General** tab, on the **Vendor approval** FastTab, set the **Enable vendor approvals** option to **Yes**.</span></span>
3. <span data-ttu-id="60801-109">Nel campo **Comportamento entità di dati** selezionare il comportamento da utilizzare quando vengono importati i dati:</span><span class="sxs-lookup"><span data-stu-id="60801-109">In the **Data entity behavior** field, select the behavior that should be used when data is imported:</span></span>

    - <span data-ttu-id="60801-110">**Consenti modifiche senza approvazione** - L'entità di dati può aggiornare il record fornitore senza elaborarlo attraverso il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="60801-110">**Allow changes without approval** – The data entity can update the vendor record without processing it through the workflow.</span></span>
    - <span data-ttu-id="60801-111">**Rifiuta modifiche** - Non è possibile apportare modifiche al record fornitore.</span><span class="sxs-lookup"><span data-stu-id="60801-111">**Reject changes** – Changes can't be made to the vendor record.</span></span> <span data-ttu-id="60801-112">L'importazione non avrà esito positivo per i campi che sono abilitati per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="60801-112">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="60801-113">**Crea proposte di modifica** - Tutti i campi verranno modificati eccetto i campi che sono abilitati per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="60801-113">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="60801-114">I nuovi valori per questi campi verranno aggiunti al fornitore come modifiche proposte e il flusso di lavoro verrà avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="60801-114">The new values for those fields will be added to the vendor as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="60801-115">Nell'elenco di campi del fornitore, selezionare la casella di controllo **Abilita** per ogni campo che deve essere approvato prima che si possano apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="60801-115">In the list of vendor fields, select the **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="60801-116">Passare a **Contabilità fornitori \> Impostazioni \> Flussi di lavoro contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="60801-116">Go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
6. <span data-ttu-id="60801-117">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="60801-117">Select **New**.</span></span>
7. <span data-ttu-id="60801-118">Selezionare **Flusso di lavoro modifiche fornitore proposte**.</span><span class="sxs-lookup"><span data-stu-id="60801-118">Select **Proposed vendor changes workflow**.</span></span> 
8. <span data-ttu-id="60801-119">Impostare il flusso di lavoro in modo che corrisponda al processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="60801-119">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="60801-120">L'elemento di approvazione del flusso di lavoro **Approvazione del flusso di lavoro per la modifica fornitore proposta** applicherà le modifiche al fornitore.</span><span class="sxs-lookup"><span data-stu-id="60801-120">The **Workflow approval for proposed vendor change** workflow approval element will apply the changes to the vendor.</span></span>

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="60801-121">Modificare le informazioni sul fornitore e inviare le modifiche al flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="60801-121">Change vendor information and submit the changes to the workflow</span></span>

<span data-ttu-id="60801-122">Quando si modifica un campo abilitato per il flusso di lavoro, viene visualizzata la pagina **Modifiche proposte**.</span><span class="sxs-lookup"><span data-stu-id="60801-122">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="60801-123">In questa pagina vengono visualizzati il valore originale del campo e il nuovo valore immesso.</span><span class="sxs-lookup"><span data-stu-id="60801-123">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="60801-124">Il campo che è stato modificato viene ripristinato al valore originale.</span><span class="sxs-lookup"><span data-stu-id="60801-124">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="60801-125">Un messaggio di stato informa anche che le modifiche non sono state inviate.</span><span class="sxs-lookup"><span data-stu-id="60801-125">A status message also informs you that your changes haven't been submitted.</span></span> 

<span data-ttu-id="60801-126">Ogni volta che si modifica un campo che è abilitato per il flusso di lavoro, questo campo viene aggiunto all'elenco nella pagina **Modifiche proposte**.</span><span class="sxs-lookup"><span data-stu-id="60801-126">Every time that you change a field that is enabled for the workflow, that field is added to the list on the **Proposed changes** page.</span></span> <span data-ttu-id="60801-127">Per eliminare il valore proposto per un campo, utilizzare il pulsante **Elimina** accanto al campo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="60801-127">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="60801-128">Per eliminare tutte le modifiche, utilizzare il pulsante **Ignora tutte le modifiche** nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="60801-128">To discard all changes, use the **Discard all changes** button at the bottom of the page.</span></span> <span data-ttu-id="60801-129">Selezionare **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="60801-129">Select **OK** to close the page.</span></span>

<span data-ttu-id="60801-130">Quando si ha almeno una modifica proposta, vengono visualizzate due schede aggiuntive nel riquadro azioni: **Modifiche proposte** e **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="60801-130">After you have at least one proposed change, two additional tabs appear on the action pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="60801-131">Selezionare **Modifiche proposte** per aprire la pagina **Modifiche proposte** ed esaminare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="60801-131">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="60801-132">Selezionare **Flusso di lavoro \> Invia per inviare le modifiche al flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="60801-132">Select **Workflow \> Submit to submit the changes to workflow**.</span></span>

    <span data-ttu-id="60801-133">Lo stato sulla pagina è cambiato in **Modifiche in attesa di approvazione**.</span><span class="sxs-lookup"><span data-stu-id="60801-133">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="60801-134">Il flusso di lavoro segue il processo standard del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="60801-134">The workflow follows the standard workflow process.</span></span> <span data-ttu-id="60801-135">L'approvatore viene indirizzato alla pagina **Fornitore** dove può esaminare le modifiche nella pagina **Modifiche proposte** e quindi selezionare **Flusso di lavoro \> Approva** per approvare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="60801-135">The approver is directed to the **Vendor** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="60801-136">Una volta completate tutte le approvazioni, i campi vengono aggiornati con i valori proposti.</span><span class="sxs-lookup"><span data-stu-id="60801-136">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>
