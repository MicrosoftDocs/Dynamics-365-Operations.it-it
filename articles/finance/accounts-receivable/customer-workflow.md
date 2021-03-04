---
title: Flusso di lavoro cliente
description: In questo argomento vengono fornite informazioni sul flusso di lavoro del cliente. È possibile modificare campi specifici per un cliente e inviare tali modifiche per l'approvazione utilizzando il flusso di lavoro prima che vengano aggiunte al cliente.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: a74b8ed226c4e13c8684fe86d4dca7236a84040e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012190"
---
# <a name="customer-workflow"></a><span data-ttu-id="3a0e3-104">Flusso di lavoro cliente</span><span class="sxs-lookup"><span data-stu-id="3a0e3-104">Customer workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a0e3-105">Il flusso di lavoro cliente è stato aggiunto alla versione 8.0.4.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-105">The customer workflow has been added to version 8.0.4.</span></span> <span data-ttu-id="3a0e3-106">È possibile modificare campi specifici per un cliente e inviare tali modifiche per l'approvazione utilizzando il flusso di lavoro prima che vengano aggiunte al cliente.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-106">You can change specific fields for a customer and then send those changes for approval by using the workflow before they are added to the customer.</span></span>

## <a name="set-up-the-customer-workflow"></a><span data-ttu-id="3a0e3-107">Impostare il flusso di lavoro cliente</span><span class="sxs-lookup"><span data-stu-id="3a0e3-107">Set up the customer workflow</span></span>

<span data-ttu-id="3a0e3-108">Prima di utilizzare la funzionalità del flusso di lavoro del cliente, è necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-108">Before you can use the customer workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="3a0e3-109">Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-109">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="3a0e3-110">Nella scheda **Generale**, nella Scheda dettaglio **Approvazione cliente**, impostare l'opzione **Abilita approvazioni cliente** su **Sì** per abilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-110">On the **General** tab, on the **Customer approval** FastTab, set the **Enable customer approvals** option to **Yes** to enable the feature.</span></span>
3. <span data-ttu-id="3a0e3-111">Nel campo **Comportamento entità di dati** selezionare il comportamento che le entità di dati devono utilizzare quando i dati vengono importati:</span><span class="sxs-lookup"><span data-stu-id="3a0e3-111">In the **Data entity behavior** field, select the behavior that the data entities should use when data is imported:</span></span>

    - <span data-ttu-id="3a0e3-112">**Consentire modifiche senza approvazione** - Un'entità può aggiornare il record cliente senza elaborarlo durante il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-112">**Allow changes without approval** – An entity can update the customer record without processing it through the workflow.</span></span>
    - <span data-ttu-id="3a0e3-113">**Rifiuta modifiche** - Le modifiche non possono essere applicate al record cliente.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-113">**Reject changes** – Changes can't be made to the customer record.</span></span> <span data-ttu-id="3a0e3-114">L'importazione avrà esito negativo per i campi abilitati per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-114">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="3a0e3-115">**Crea proposte di modifica** - Tutti i campi verranno modificati ad eccezione dei campi abilitati per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-115">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="3a0e3-116">I nuovi valori per questi campi verranno aggiunti al cliente come modifiche proposte e il flusso di lavoro verrà avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-116">The new values for those fields will be added to the customer as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="3a0e3-117">Nell'elenco dei campi del cliente, selezionare quindi la casella di controllo **Abilita** per ogni campo che deve essere approvato prima che le modifiche possano essere effettuate.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-117">In the list of customer fields, select then **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="3a0e3-118">Andare a **Contabilità clienti \> Impostazioni \> Flussi di lavoro contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-118">Go to **Accounts receivable \> Setup \> Accounts receivable workflows**.</span></span>
6. <span data-ttu-id="3a0e3-119">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-119">Select **New**.</span></span>
7. <span data-ttu-id="3a0e3-120">Selezionare **Flusso di lavoro della modifica del cliente proposta**.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-120">Select **Proposed customer change workflow**.</span></span> 
8. <span data-ttu-id="3a0e3-121">Impostare il flusso di lavoro in modo che corrisponda al processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-121">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="3a0e3-122">L'elemento di approvazione del flusso di lavoro **Approvazione del flusso di lavoro per la modifica cliente proposta** applicherà le modifiche al cliente.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-122">The **Workflow approval for proposed customer change** workflow approval element will apply the changes to the customer.</span></span>

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="3a0e3-123">Modificare le informazioni sul cliente e inviare le modifiche al flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3a0e3-123">Change customer information and submit the changes to the workflow</span></span>

<span data-ttu-id="3a0e3-124">Quando si modifica un campo che viene abilitato per il flusso di lavoro, viene visualizzata la pagina **Modifiche proposte**.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-124">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="3a0e3-125">In questa pagina vengono visualizzati il valore originale del campo e il nuovo valore immesso.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-125">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="3a0e3-126">Il campo modificato viene reimpostato sul valore originale.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-126">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="3a0e3-127">Un messaggio di stato nella pagina comunica all'utente che le modifiche non sono state inviate.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-127">A status message on the page informs you that your changes haven't been submitted.</span></span>

<span data-ttu-id="3a0e3-128">Ogni volta che si modifica un campo abilitato per il flusso di lavoro, tale campo viene aggiunto all'elenco delle modifiche proposte.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-128">Every time that you change a field that is enabled for the workflow, that field is added to the list of proposed changes.</span></span> <span data-ttu-id="3a0e3-129">Per eliminare il valore proposto per un campo, utilizzare il pulsante **Elimina** accanto al campo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-129">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="3a0e3-130">Per eliminare tutte le modifiche, utilizzare il pulsante **Ignora tutte le modifiche** in fondo alla pagina.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-130">To discard all changes, use the **Discard all change** button at the bottom of the page.</span></span> <span data-ttu-id="3a0e3-131">Selezionare **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-131">Select **OK** to close the page.</span></span>

<span data-ttu-id="3a0e3-132">Dopo avere almeno una modifica proposta, vengono visualizzati due menu aggiuntivi nel riquadro Azioni: **Modifiche proposte** e **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-132">After you have at least one proposed change, two additional menus appear on the Action Pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="3a0e3-133">Selezionare **Modifiche proposte** per aprire la pagina **Modifiche proposte** ed esaminare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-133">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="3a0e3-134">Selezionare **Flusso di lavoro \> Invia** per inviare le modifiche al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-134">Select **Workflow \> Submit** to submit the changes to the workflow.</span></span>

    <span data-ttu-id="3a0e3-135">Lo stato sulla pagina è passato a **Modifiche in attesa di approvazione**.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-135">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="3a0e3-136">Il flusso di lavoro segue il processo standard del flusso di lavoro nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-136">The workflow follows the standard workflow process in the application.</span></span> <span data-ttu-id="3a0e3-137">L'approvatore viene reindirizzato alla pagina **Cliente**, in cui le modifiche possono essere riviste nella pagina **Modifiche proposte** e selezionare **Flusso di lavoro \> Approva** per approvare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-137">The approver is directed to the **Customer** page where the changes can be reviewed on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="3a0e3-138">Una volta completate tutte le approvazioni, i campi vengono aggiornati con i valori proposti.</span><span class="sxs-lookup"><span data-stu-id="3a0e3-138">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>
