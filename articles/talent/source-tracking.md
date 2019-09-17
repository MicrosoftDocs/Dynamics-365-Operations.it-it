---
title: Tenere traccia delle origini delle domande di lavoro e dei profili dei candidati
description: In questo argomento vengono fornite informazioni sulla tracciabilità delle origini delle domande di lavoro e dei profili dei candidati.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 2cfa180f992a4f7a9b2e21e0fb3e0845c7546c94
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742720"
---
# <a name="track-candidate-sources"></a><span data-ttu-id="0021c-103">Tenere traccia delle origini dei candidati</span><span class="sxs-lookup"><span data-stu-id="0021c-103">Track candidate sources</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE] 
> <span data-ttu-id="0021c-104">La funzionalità indicata in questo argomento è disponibile come parte di un rilascio di verifica di anteprima.</span><span class="sxs-lookup"><span data-stu-id="0021c-104">Functionality noted in this topic is available as part of a preview review release.</span></span> <span data-ttu-id="0021c-105">Il contenuto e la funzionalità sono soggetti a modifiche.</span><span class="sxs-lookup"><span data-stu-id="0021c-105">The content and the functionality are subject to change.</span></span> <span data-ttu-id="0021c-106">Per utilizzare questa funzionalità, chiedere a un amministratore di abilitarla utilizzando **Impostazioni di amministrazione** in Attract.</span><span class="sxs-lookup"><span data-stu-id="0021c-106">To use this feature, ask an administrator to enable it using the **Admin settings** in Attract.</span></span> <span data-ttu-id="0021c-107">Una versione futura fornirà report di tracciabilità delle origini.</span><span class="sxs-lookup"><span data-stu-id="0021c-107">A future release will provide source tracking reports.</span></span> <span data-ttu-id="0021c-108">Per ulteriori informazioni, vedere [Accesso alle funzionalità di anteprima in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="0021c-108">For more information, see [Access preview features in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

<span data-ttu-id="0021c-109">Quando i candidati si candidano per una mansione, Attract tiene automaticamente traccia dell'origine delle loro domande di lavoro, fornendo informazioni preziose per migliorare le operazioni di selezione.</span><span class="sxs-lookup"><span data-stu-id="0021c-109">When candidates apply for a job, Attract automatically tracks the source of their applications, providing you with valuable information to help you target your recruiting efforts.</span></span> <span data-ttu-id="0021c-110">I selezionatori e i responsabili delle assunzioni possono inoltre selezionare l'origine di una domanda di lavoro quando aggiungono manualmente un candidato a una mansione o a un pool di talenti.</span><span class="sxs-lookup"><span data-stu-id="0021c-110">Recruiters and hiring managers can also select an application source while manually adding a candidate to a job or talent pool.</span></span>

<span data-ttu-id="0021c-111">È possibile visualizzare l'origine della domanda di lavoro nei dettagli dell'attività della domanda di lavoro nella scheda **Attività** nonché nello storico delle domande di lavoro disponibile in **Profilo** nei pool di talenti.</span><span class="sxs-lookup"><span data-stu-id="0021c-111">You can view the application source in the application activity details under the **Activity** tab, as well as in the application history available under **Profile** in talent pools.</span></span> <span data-ttu-id="0021c-112">È possibile trovare l'origine del profilo di un candidato nei dettagli del candidato nella scheda **Profilo** di Domande di lavoro e Pool di talenti.</span><span class="sxs-lookup"><span data-stu-id="0021c-112">You can find a candidate's profile source in the candidate details under the **Profile** tab in both applications and talent pools.</span></span>

> [!NOTE] 
> <span data-ttu-id="0021c-113">I modelli di processo sono disponibili nel [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="0021c-113">You can find process templates in the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>

## <a name="pre-configured-sources"></a><span data-ttu-id="0021c-114">Origini preconfigurate</span><span class="sxs-lookup"><span data-stu-id="0021c-114">Pre-configured sources</span></span>

<span data-ttu-id="0021c-115">L'elenco di origini predefinite contiene origini di domande di lavoro comuni.</span><span class="sxs-lookup"><span data-stu-id="0021c-115">The default source list contains common application sources.</span></span> <span data-ttu-id="0021c-116">Alcuni tipi di origini, ad esempio **Bacheca mansioni** e **Social Network**, includono ulteriori informazioni sulle origini.</span><span class="sxs-lookup"><span data-stu-id="0021c-116">Some source types, like **Job board** and **Social Network**, have additional source details.</span></span> <span data-ttu-id="0021c-117">Ad esempio, **Social Network** include Facebook e Twitter.</span><span class="sxs-lookup"><span data-stu-id="0021c-117">For example, **Social Network** includes Facebook and Twitter.</span></span> <span data-ttu-id="0021c-118">Il tipo di origine **Segnalazione** consente di specificare un dipendente interno come garante.</span><span class="sxs-lookup"><span data-stu-id="0021c-118">The **Referral** source type allows you to specify an internal employee as the referrer.</span></span> <span data-ttu-id="0021c-119">L'elenco di origini predefinite include le seguenti origini preconfigurate:</span><span class="sxs-lookup"><span data-stu-id="0021c-119">The default source list includes the following pre-configured sources:</span></span>

-   <span data-ttu-id="0021c-120">Sito di avanzamento professionale di Attract</span><span class="sxs-lookup"><span data-stu-id="0021c-120">Attract career site</span></span>

-   <span data-ttu-id="0021c-121">Agenzia</span><span class="sxs-lookup"><span data-stu-id="0021c-121">Agency</span></span>

-   <span data-ttu-id="0021c-122">Borsa del lavoro</span><span class="sxs-lookup"><span data-stu-id="0021c-122">Career Fair</span></span>

-   <span data-ttu-id="0021c-123">Marketing aziendale</span><span class="sxs-lookup"><span data-stu-id="0021c-123">Company Marketing</span></span>

-   <span data-ttu-id="0021c-124">Conferenze e fiere campionarie</span><span class="sxs-lookup"><span data-stu-id="0021c-124">Conferences & Trade shows</span></span>

-   <span data-ttu-id="0021c-125">Associazione di professionisti</span><span class="sxs-lookup"><span data-stu-id="0021c-125">Professional Association</span></span>

-   <span data-ttu-id="0021c-126">Bacheca delle offerte di lavoro</span><span class="sxs-lookup"><span data-stu-id="0021c-126">Job board</span></span>

    -   <span data-ttu-id="0021c-127">Indeed</span><span class="sxs-lookup"><span data-stu-id="0021c-127">Indeed</span></span>

    -   <span data-ttu-id="0021c-128">Seek</span><span class="sxs-lookup"><span data-stu-id="0021c-128">Seek</span></span>

    -   <span data-ttu-id="0021c-129">CareerBuilder</span><span class="sxs-lookup"><span data-stu-id="0021c-129">CareerBuilder</span></span>

    -   <span data-ttu-id="0021c-130">Google Jobs</span><span class="sxs-lookup"><span data-stu-id="0021c-130">Google Jobs</span></span>

    -   <span data-ttu-id="0021c-131">Xing</span><span class="sxs-lookup"><span data-stu-id="0021c-131">Xing</span></span>

    -   <span data-ttu-id="0021c-132">Glassdoor</span><span class="sxs-lookup"><span data-stu-id="0021c-132">Glassdoor</span></span>

    -   <span data-ttu-id="0021c-133">Monster Jobs</span><span class="sxs-lookup"><span data-stu-id="0021c-133">Monster Jobs</span></span>

-   <span data-ttu-id="0021c-134">Riviste e pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="0021c-134">Magazines & Publications</span></span>

-   <span data-ttu-id="0021c-135">Social Network</span><span class="sxs-lookup"><span data-stu-id="0021c-135">Social Network</span></span>

    -   <span data-ttu-id="0021c-136">Facebook</span><span class="sxs-lookup"><span data-stu-id="0021c-136">Facebook</span></span>

    -   <span data-ttu-id="0021c-137">Twitter</span><span class="sxs-lookup"><span data-stu-id="0021c-137">Twitter</span></span>

-   <span data-ttu-id="0021c-138">Selezione presso università</span><span class="sxs-lookup"><span data-stu-id="0021c-138">University Recruiting</span></span>

-   <span data-ttu-id="0021c-139">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="0021c-139">LinkedIn</span></span>

-   <span data-ttu-id="0021c-140">Annunci</span><span class="sxs-lookup"><span data-stu-id="0021c-140">Classifieds</span></span>

-   <span data-ttu-id="0021c-141">Segnalazione</span><span class="sxs-lookup"><span data-stu-id="0021c-141">Referral</span></span>

-   <span data-ttu-id="0021c-142">Aggiunta dal selezionatore</span><span class="sxs-lookup"><span data-stu-id="0021c-142">Added by Recruiter</span></span>

-   <span data-ttu-id="0021c-143">Altro</span><span class="sxs-lookup"><span data-stu-id="0021c-143">Other</span></span>

## <a name="customize-the-source-list"></a><span data-ttu-id="0021c-144">Personalizzare l'elenco di origini</span><span class="sxs-lookup"><span data-stu-id="0021c-144">Customize the source list</span></span> 

<span data-ttu-id="0021c-145">È possibile estendere l'elenco di origini per includere ulteriori origini di domande di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0021c-145">You can extend the source list to include additional application sources.</span></span> <span data-ttu-id="0021c-146">Per personalizzare questo elenco, seguire le istruzioni in [Estensione di set di opzioni in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span><span class="sxs-lookup"><span data-stu-id="0021c-146">To customize this list, follow the instructions in [Extending Option Sets in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span></span> <span data-ttu-id="0021c-147">Modificare l'entità **TalentSource** per includere ulteriori origini.</span><span class="sxs-lookup"><span data-stu-id="0021c-147">Edit the **TalentSource** entity to include additional sources.</span></span> 

<span data-ttu-id="0021c-148">Per evitare un impatto negativo sull'interfaccia utente, non modificare o eliminare i valori di enumerazione **TalentCategory** (non i nomi) per quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0021c-148">To avoid negatively impacting the user interface (UI), don't edit or delete the **TalentCategory** enum values (not names) for the following:</span></span>

- <span data-ttu-id="0021c-149">**Segnalazione**</span><span class="sxs-lookup"><span data-stu-id="0021c-149">**Referral**</span></span>
- <span data-ttu-id="0021c-150">**LinkedIn**</span><span class="sxs-lookup"><span data-stu-id="0021c-150">**LinkedIn**</span></span>
- <span data-ttu-id="0021c-151">**Altro**</span><span class="sxs-lookup"><span data-stu-id="0021c-151">**Other**</span></span>

<span data-ttu-id="0021c-152">È invece possibile estendere l'enumerazione **TalentSource** per aggiungere altri tipi di origini.</span><span class="sxs-lookup"><span data-stu-id="0021c-152">Instead, you can extend the **TalentSource** enum to add other types of sources.</span></span>
