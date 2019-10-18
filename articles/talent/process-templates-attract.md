---
title: Creare un modello di processo in Attract
description: In questo argomento vengono fornite informazioni sulla creazione di un modello di processo in Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: 694835d20e3401aaeb22aa19082a2cd0e3a0163a
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010708"
---
# <a name="create-a-process-template"></a><span data-ttu-id="1ea78-103">Creare un modello di processo</span><span class="sxs-lookup"><span data-stu-id="1ea78-103">Create a process template</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1ea78-104">Un *modello di processo di assunzione* contiene tutte le attività che devono essere incluse durante il processo di assunzione per una posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="1ea78-104">A *hiring process template* contains all the activities that should be included as part of the hiring process for a job.</span></span> <span data-ttu-id="1ea78-105">In questo argomento sono descritti gli elementi di un modello di processo in Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="1ea78-105">This topic describes the elements of a process template in Microsoft Dynamics 365 Talent: Attract.</span></span> <span data-ttu-id="1ea78-106">Viene illustrato anche come creare un modello.</span><span class="sxs-lookup"><span data-stu-id="1ea78-106">It also explains how to create a template.</span></span>

> [!NOTE]
> <span data-ttu-id="1ea78-107">La creazione del modello fa parte del componente aggiuntivo per l'assunzione a livello globale per Attract.</span><span class="sxs-lookup"><span data-stu-id="1ea78-107">Template creation is part of the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="template-management"></a><span data-ttu-id="1ea78-108">Gestione modello</span><span class="sxs-lookup"><span data-stu-id="1ea78-108">Template management</span></span>

<span data-ttu-id="1ea78-109">Le organizzazioni possono decidere se i membri del team o solo gli amministratori possono creare modelli di processi in Attract.</span><span class="sxs-lookup"><span data-stu-id="1ea78-109">Organizations can decide whether team members or only admins can create process templates in Attract.</span></span> <span data-ttu-id="1ea78-110">Per configurare la gestione dei modelli, passare a **Interfaccia di amministrazione** \> **Gestione modello**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-110">To configure template management, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="1ea78-111">Affinché i membri del team creino i propri modelli, attivare la gestione modello.</span><span class="sxs-lookup"><span data-stu-id="1ea78-111">To let team members create their own templates, turn on template management.</span></span> <span data-ttu-id="1ea78-112">Se non si attiva la gestione modello, solo gli amministratori possono creare modelli.</span><span class="sxs-lookup"><span data-stu-id="1ea78-112">If you don't turn on template management, only admins can create templates.</span></span>

## <a name="default-template"></a><span data-ttu-id="1ea78-113">Modello predefinito</span><span class="sxs-lookup"><span data-stu-id="1ea78-113">Default template</span></span>

<span data-ttu-id="1ea78-114">Solo gli amministratori possono impostare il modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="1ea78-114">Only admins can set the default template.</span></span> <span data-ttu-id="1ea78-115">Il modello predefinito viene utilizzato se non è selezionato un modello quando viene creato un processo.</span><span class="sxs-lookup"><span data-stu-id="1ea78-115">The default template is used if a template isn't selected when a job is created.</span></span> <span data-ttu-id="1ea78-116">Per impostare il modello predefinito, passare a **Interfaccia di amministrazione** \> **Gestione modello**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-116">To set the default template, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="1ea78-117">Nella scheda del modello che dovrebbe essere quello predefinito, selezionare il pulsante con i puntini di sospensione (**...**), quindi selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-117">On the card for the template that should be the default template, select the ellipsis button (**...**), and then select **Set as default**.</span></span>

## <a name="create-a-process-template"></a><span data-ttu-id="1ea78-118">Creare un modello di processo</span><span class="sxs-lookup"><span data-stu-id="1ea78-118">Create a process template</span></span>

<span data-ttu-id="1ea78-119">Gli amministratori, i reclutatori e i responsabili delle assunzioni possono creare modelli di processi.</span><span class="sxs-lookup"><span data-stu-id="1ea78-119">Admins, recruiters, and hiring managers can create process templates.</span></span> <span data-ttu-id="1ea78-120">Un modello di processo comprende *fasi* e *attività*.</span><span class="sxs-lookup"><span data-stu-id="1ea78-120">A process template consists of *stages* and *activities*.</span></span> <span data-ttu-id="1ea78-121">Le fasi raggruppano insieme una o più attività.</span><span class="sxs-lookup"><span data-stu-id="1ea78-121">Stages group together one or more activities.</span></span> <span data-ttu-id="1ea78-122">Per impostazione predefinita, ciascun modello di processo ha le attività Prospect, Domanda di lavoro e Offerta.</span><span class="sxs-lookup"><span data-stu-id="1ea78-122">By default, every process template has Prospect, Application, and Offer activities.</span></span> <span data-ttu-id="1ea78-123">Le fasi contenenti queste attività possono essere rinominate.</span><span class="sxs-lookup"><span data-stu-id="1ea78-123">The stages that contain these activities can be renamed.</span></span> <span data-ttu-id="1ea78-124">È possibile aggiungere più fasi selezionando **+ Nuova fase**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-124">You can add more stages by selecting **+ New Stage**.</span></span> <span data-ttu-id="1ea78-125">È possibile aggiungere attività a una fase uno trascinandole nella fase appropriata o facendo doppio clic su di esse nell'elenco attività.</span><span class="sxs-lookup"><span data-stu-id="1ea78-125">You can activities to a stage either by dragging them to the appropriate stage or by double-clicking them in the activity list.</span></span>

> [!NOTE]
> <span data-ttu-id="1ea78-126">I nomi delle fasi sono visibili ai candidati nella pagina **Stato domanda di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-126">Stage names are visible to candidates on the **Application status** page.</span></span> <span data-ttu-id="1ea78-127">È opportuno considerare questo fatto quando si scelgono i nomi per le fasi.</span><span class="sxs-lookup"><span data-stu-id="1ea78-127">You should consider this fact when you choose names for stages.</span></span>

<span data-ttu-id="1ea78-128">Per ulteriori informazioni sulle attività, vedere [Attività del processo di assunzione in Attract](./activities-attract.md).</span><span class="sxs-lookup"><span data-stu-id="1ea78-128">To learn more about activities, see [Hiring process activities in Attract](./activities-attract.md).</span></span>

<span data-ttu-id="1ea78-129">Per creare un modello di processo di assunzione, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="1ea78-129">Follow these steps to create a hiring process template.</span></span>

1. <span data-ttu-id="1ea78-130">Andare a **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-130">Go to **Templates**.</span></span>
2. <span data-ttu-id="1ea78-131">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-131">Select **New**.</span></span>
3. <span data-ttu-id="1ea78-132">Nel campo **Nome del modello** immettere un nome per il modello, quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-132">In the **Template name** field, enter a name for the template, and then select **Create**.</span></span>
4. <span data-ttu-id="1ea78-133">Nell'elenco **Scegli il processo di approvazione** selezionare **Standard** per richiedere l'approvazione di un processo.</span><span class="sxs-lookup"><span data-stu-id="1ea78-133">In the **Choose the approval process** list, select **Default** to require approval for a job.</span></span>
5. <span data-ttu-id="1ea78-134">Selezionare questa opzione per abilitare o disabilitare i prospect.</span><span class="sxs-lookup"><span data-stu-id="1ea78-134">Select to enable or disable prospects.</span></span>
6. <span data-ttu-id="1ea78-135">Facoltativo: Aggiungere o rimuovere fasi.</span><span class="sxs-lookup"><span data-stu-id="1ea78-135">Optional: Add or remove stages.</span></span>

    - <span data-ttu-id="1ea78-136">Per aggiungere una fase, selezionare **+ Nuova fase**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-136">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="1ea78-137">Per rimuovere una fase, passare il puntatore sulla fase, quindi fare clic sul pulsante di pattumiera visualizzato.</span><span class="sxs-lookup"><span data-stu-id="1ea78-137">To remove a stage, hover the pointer over the stage, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1ea78-138">Le fasi Prospect, Domanda di lavoro e Offerta non possono essere rimosse, ma possono essere rinominate.</span><span class="sxs-lookup"><span data-stu-id="1ea78-138">Prospect, Application, and Offer stages can't be removed, but they can be renamed.</span></span>

7. <span data-ttu-id="1ea78-139">Facoltativo: Aggiungere o rimuovere attività.</span><span class="sxs-lookup"><span data-stu-id="1ea78-139">Optional: Add or remove activities.</span></span>

    - <span data-ttu-id="1ea78-140">Per aggiungere un'attività, trascinarla dall'elenco attività a destra alla fase appropriata.</span><span class="sxs-lookup"><span data-stu-id="1ea78-140">To add an activity, drag it from the activity list on the right to the appropriate stage.</span></span> <span data-ttu-id="1ea78-141">In alternativa, fare doppio clic sull'attività quindi selezionare la fase a cui aggiungerla.</span><span class="sxs-lookup"><span data-stu-id="1ea78-141">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="1ea78-142">Per rimuovere un'attività, espanderla, quindi fare clic sul pulsante di pattumiera nell'intestazione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1ea78-142">To remove an activity, expand it, and then select the trash can button on the activity header.</span></span>

8. <span data-ttu-id="1ea78-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1ea78-143">Select **Save**.</span></span>
