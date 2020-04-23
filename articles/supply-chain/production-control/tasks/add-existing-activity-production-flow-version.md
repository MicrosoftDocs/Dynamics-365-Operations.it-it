---
title: Aggiungere un'attività esistente a una versione del flusso di produzione
description: Durante la creazione di nuove versioni dei flussi di produzione, è possibile scegliere di aggiungere attività create per le versioni precedenti, nella nuova versione.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8dc890462ac44f0471882e65b928563415aceaea
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212436"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a><span data-ttu-id="28991-103">Aggiungere un'attività esistente a una versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="28991-103">Add an existing activity to a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="28991-104">Durante la creazione di nuove versioni dei flussi di produzione, è possibile scegliere di aggiungere attività create per le versioni precedenti, nella nuova versione.</span><span class="sxs-lookup"><span data-stu-id="28991-104">When creating new versions of production flows, you can choose to add activities created for the older versions, to the new version.</span></span> <span data-ttu-id="28991-105">In questa procedura viene illustrato come viene creata una nuova versione di un flusso di produzione esistente, senza copiare le attività.</span><span class="sxs-lookup"><span data-stu-id="28991-105">This procedure shows how a new version is created for an existing production flow, without copying the activities.</span></span> <span data-ttu-id="28991-106">Nel passaggio successivo, un'attività esistente viene aggiunta alla nuova versione.</span><span class="sxs-lookup"><span data-stu-id="28991-106">In the next step, an existing activity is added to the new version.</span></span> 

<span data-ttu-id="28991-107">Per questa attività è necessario un flusso di produzione con versione e attività già create.</span><span class="sxs-lookup"><span data-stu-id="28991-107">This task requires production flow with version and activities already created.</span></span>


## <a name="create-a-new-production-flow-version"></a><span data-ttu-id="28991-108">Crea nuova versione flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="28991-108">Create a new production flow version</span></span>
1. <span data-ttu-id="28991-109">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="28991-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="28991-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="28991-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="28991-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="28991-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="28991-112">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="28991-112">Click Edit.</span></span>
5. <span data-ttu-id="28991-113">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="28991-113">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="28991-114">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="28991-114">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="28991-115">Tenere presente che prima di creare una nuova versione del flusso di produzione, accertarsi di controllare la data e l'ora di scadenza della versione attiva.</span><span class="sxs-lookup"><span data-stu-id="28991-115">Note that before you create a new production flow version, make sure to check the expiration date and time of the active version.</span></span> <span data-ttu-id="28991-116">La nuova versione verrà creata con una data di inizio validità, che si connetterà alla data di scadenza della versione selezionata.</span><span class="sxs-lookup"><span data-stu-id="28991-116">The new version will be created with an effective start date, which connects to the expiry date of the selected version.</span></span>  
7. <span data-ttu-id="28991-117">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="28991-117">Click Add.</span></span>
8. <span data-ttu-id="28991-118">Selezionare No nel campo Copia da versione.</span><span class="sxs-lookup"><span data-stu-id="28991-118">Select No in the Copy from version field.</span></span>
    * <span data-ttu-id="28991-119">Selezionare No per iniziare con una versione vuota se la maggior parte delle attività della versione copiata verranno sostituite da nuove attività.</span><span class="sxs-lookup"><span data-stu-id="28991-119">Select No to start with an empty version if most of the activities of the copied version will be replaced by new activities.</span></span> <span data-ttu-id="28991-120">Aggiungere manualmente le attività immutate alla funzione Aggiungi esistente nel modulo delle attività.</span><span class="sxs-lookup"><span data-stu-id="28991-120">Add the unchanged activities to the Add existing function in the activity form manually.</span></span>  
9. <span data-ttu-id="28991-121">Selezionare No nel campo Duplica regole kanban.</span><span class="sxs-lookup"><span data-stu-id="28991-121">Select No in the Duplicate kanban rules field.</span></span>
    * <span data-ttu-id="28991-122">Quando le attività non sono copiate nella nuova versione, non sarà possibile copiare le regole kanban al momento della creazione di una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="28991-122">When the activities are not copied to the new version, it is not possible to copy the kanban rules at the time of creation of the new version.</span></span>   <span data-ttu-id="28991-123">Invece si utilizzerà successivamente la funzione di creazione di una regola kanban sostitutiva nel modulo delle regole kanban, per sostituire le regole kanban della versione precedente del flusso di produzione con le regole kanban che utilizzano le attività della nuova versione.</span><span class="sxs-lookup"><span data-stu-id="28991-123">Instead you will use the create replacement kanban function later in the kanban rule form, to replace kanban rules of the old production flow version with kanban rules using the activities of the new version.</span></span>  
10. <span data-ttu-id="28991-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="28991-124">Click OK.</span></span>
11. <span data-ttu-id="28991-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="28991-125">In the list, find and select the desired record.</span></span>

## <a name="add-an-existing-activity"></a><span data-ttu-id="28991-126">Aggiungere un'attività esistente</span><span class="sxs-lookup"><span data-stu-id="28991-126">Add an existing activity</span></span>
1. <span data-ttu-id="28991-127">Fare clic su Attività.</span><span class="sxs-lookup"><span data-stu-id="28991-127">Click Activities.</span></span>
2. <span data-ttu-id="28991-128">Fare clic su Aggiungi esistente per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="28991-128">Click Add existing to open the drop dialog.</span></span>
    * <span data-ttu-id="28991-129">Trovare e selezionare un'attività esistente da aggiungere alla nuova versione del flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="28991-129">Find and select an existing activity to be added to the new production flow version.</span></span>  <span data-ttu-id="28991-130">Tenere presente che l'elenco visualizza tutte le attività create per questo flusso di produzione per tutte le versioni precedenti del flusso.</span><span class="sxs-lookup"><span data-stu-id="28991-130">Note that the list shows all activities that have been created for this production flow for all previous versions of the flow.</span></span>  
3. <span data-ttu-id="28991-131">Nel campo Attività immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="28991-131">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="28991-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="28991-132">Click OK.</span></span>

