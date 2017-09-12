---
title: Configurare un flusso di lavoro voci
description: In questo argomento viene descritto come configurare un elemento del flusso di lavoro voci.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: d888bf4285a27369b197ed66e5975cc806c640d3
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="configure-a-line-item-workflow"></a><span data-ttu-id="ad6e8-103">Configurare un flusso di lavoro voci</span><span class="sxs-lookup"><span data-stu-id="ad6e8-103">Configure a line-item workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ad6e8-104">In questo argomento viene descritto come configurare un elemento del flusso di lavoro voci.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="ad6e8-105">Per configurare un elemento del flusso di lavoro voci, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento e scegliere **Proprietà** per aprire la pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="ad6e8-106">Quindi, per configurare le proprietà dell'elemento del flusso di lavoro voci, attenersi alle procedure indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-lineitem-workflow-element"></a><span data-ttu-id="ad6e8-107">Assegnare un nome all'elemento del flusso di lavoro voci</span><span class="sxs-lookup"><span data-stu-id="ad6e8-107">Name the lineitem workflow element</span></span>
<span data-ttu-id="ad6e8-108">Per immettere un nome per l'elemento del flusso di lavoro voci, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1.  <span data-ttu-id="ad6e8-109">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="ad6e8-110">Nel campo **Nome** immettere un nome univoco per l'elemento del flusso di lavoro voci.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="ad6e8-111">Specificare se verrà utilizzato lo stesso flusso di lavoro per elaborare tutte le voci.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-111">Specify whether the same workflow is used to process all line items</span></span>
<span data-ttu-id="ad6e8-112">Per specificare di utilizzare lo stesso flusso di lavoro per elaborare tutte le voci in un documento, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1.  <span data-ttu-id="ad6e8-113">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-113">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="ad6e8-114">Se lo stesso flusso di lavoro deve elaborare tutte le voci in un documento, fare clic su **Richiamare un solo flusso di lavoro per tutte le righe**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="ad6e8-115">Selezionare quindi il flusso di lavoro da utilizzare per l'elaborazione delle voci.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-115">Then select the workflow to use to process the line items.</span></span>
3.  <span data-ttu-id="ad6e8-116">Se uno specifico flusso di lavoro deve elaborare voci che soddisfano un set specifico di condizioni, fare clic su **Richiama un flusso di lavoro per ogni voce**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="ad6e8-117">Quindi, per definire il set di condizioni, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad6e8-117">Then follow these steps to define the set of conditions:</span></span>
    1.  <span data-ttu-id="ad6e8-118">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-118">Click **Add**.</span></span>
    2.  <span data-ttu-id="ad6e8-119">Selezionare la condizione nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-119">Select the condition in the table.</span></span>
    3.  <span data-ttu-id="ad6e8-120">Nella scheda **Nome condizione** immettere un nome per il set di condizioni da definire.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4.  <span data-ttu-id="ad6e8-121">Fare clic su **Aggiungi condizione** per immettere una condizione.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-121">Click **Add condition** to enter a condition.</span></span>
    5.  <span data-ttu-id="ad6e8-122">Immettere altre condizioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-122">Enter any additional conditions that are required.</span></span>
    6.  <span data-ttu-id="ad6e8-123">Per verificare la correttezza della configurazione del set di condizioni immesse, fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="ad6e8-124">Nella pagina **Test condizione flusso di lavoro**, nell'area **Convalida condizione**, selezionare un record e fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="ad6e8-125">Il sistema valuta il record per determinare se soddisfa le condizioni definite.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="ad6e8-126">Fare clic su **OK** o su **Annulla** per tornare alla pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="ad6e8-127">Nella scheda **Flusso di lavoro** selezionare il flusso di lavoro da utilizzare per elaborare le voci che soddisfano il set di condizioni definite.</span><span class="sxs-lookup"><span data-stu-id="ad6e8-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>





