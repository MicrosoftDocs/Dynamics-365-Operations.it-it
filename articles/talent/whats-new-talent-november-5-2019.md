---
title: Novità o modifiche in Dynamics 365 Talent (5 novembre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 48de07178acfaccf11e0a02b2848bf24e6ccc117
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896775"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a><span data-ttu-id="1238f-103">Novità o modifiche in Dynamics 365 Talent (5 novembre 2019)</span><span class="sxs-lookup"><span data-stu-id="1238f-103">What's new or changed in Dynamics 365 Talent (November 5, 2019)</span></span>

<span data-ttu-id="1238f-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="1238f-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="1238f-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="1238f-105">Changes in Attract</span></span>

<span data-ttu-id="1238f-106">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="1238f-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="1238f-107">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="1238f-107">Changes in Onboard</span></span>

<span data-ttu-id="1238f-108">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="1238f-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="1238f-109">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="1238f-109">Changes in Core HR</span></span>

<span data-ttu-id="1238f-110">Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2598.</span><span class="sxs-lookup"><span data-stu-id="1238f-110">Changes described in this section apply to build number 8.1.2598.</span></span> <span data-ttu-id="1238f-111">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="1238f-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="copy-a-core-hr-instance"></a><span data-ttu-id="1238f-112">Copiare un'istanza Core HR</span><span class="sxs-lookup"><span data-stu-id="1238f-112">Copy a Core HR instance</span></span>

<span data-ttu-id="1238f-113">Nella versione di questa settimana, è possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Talent: Core HR in un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="1238f-113">In this week's release, you can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Talent: Core HR database to a sandbox environment.</span></span> <span data-ttu-id="1238f-114">Se è disponibile un altro ambiente sandbox, è anche possibile copiare il database da tale ambiente in un ambiente sandbox di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1238f-114">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span> <span data-ttu-id="1238f-115">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="1238f-115">For more information, see:</span></span>

- <span data-ttu-id="1238f-116">[Gestione dell'ambiente più ampia](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.</span><span class="sxs-lookup"><span data-stu-id="1238f-116">[Broader environment management](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) in the Dynamics 365: 2019 release wave 2 plan</span></span>

- <span data-ttu-id="1238f-117">Documentazione [Copiare un'istanza Core HR](hr-copy-instance.md) in Talent</span><span class="sxs-lookup"><span data-stu-id="1238f-117">[Copy a Core HR instance](hr-copy-instance.md) in Talent documentation</span></span>

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a><span data-ttu-id="1238f-118">I processi batch di integrazione di Common Data Service non vengono creati quando l'integrazione Common Data Service è attivata (388030)</span><span class="sxs-lookup"><span data-stu-id="1238f-118">Common Data Service integration batch jobs aren't created when Common Data Service integration is enabled (388030)</span></span>

<span data-ttu-id="1238f-119">Questa modifica crea i processi batch per l'integrazione di Common Data Service quando è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1238f-119">This change will create batch jobs for Common Data Service integration when it's enabled.</span></span>

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a><span data-ttu-id="1238f-120">HcmPersonImageEntity non ridimensiona l'immagine della persona quando viene caricata (369469)</span><span class="sxs-lookup"><span data-stu-id="1238f-120">The HcmPersonImageEntity doesn't resize the person image when uploaded (369469)</span></span>

<span data-ttu-id="1238f-121">La versione di questa settimana modifica il modo in cui le immagini vengono ridimensionate per migliorare le prestazioni quando importate tramite la gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1238f-121">This week's release changes how images are resized for better performance when imported through data management.</span></span>

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a><span data-ttu-id="1238f-122">Una posizione disponibile per la data di assegnazione può essere precedente alla data di attivazione (340103)</span><span class="sxs-lookup"><span data-stu-id="1238f-122">A position's Available for assignment date can be earlier than the Activation date (340103)</span></span>

<span data-ttu-id="1238f-123">Con questa modifica, verrà visualizzato un avviso se si seleziona una **data disponibile per l'assegnazione** precedente alla **data di attivazione**della posizione.</span><span class="sxs-lookup"><span data-stu-id="1238f-123">With this change, a warning will appear if you select an **Available for assignment date** that's earlier than the position's **Activation date**.</span></span>

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a><span data-ttu-id="1238f-124">Impossibile creare una richiesta di modifica di retribuzione nel self-service dei dipendenti per piani basati su passaggi (376872)</span><span class="sxs-lookup"><span data-stu-id="1238f-124">Can't create a compensation change request in employee self-service for step-based plans (376872)</span></span>

<span data-ttu-id="1238f-125">Questa versione corregge un problema quando si richiede la modifica della retribuzione tramite Self Service dipendenti per i piani basati su passaggi.</span><span class="sxs-lookup"><span data-stu-id="1238f-125">This release corrects an issue when requesting compensation changes through employee self-service for step-based plans.</span></span> 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a><span data-ttu-id="1238f-126">Il codice motivo non viene sincronizzato in Common Data Service se la descrizione è più lunga di 30 caratteri, Core HR consente 60 (352682)</span><span class="sxs-lookup"><span data-stu-id="1238f-126">Reason code doesn't sync to Common Data Service if the description is longer than 30 characters, Core HR allows 60 (352682)</span></span>

<span data-ttu-id="1238f-127">Con questa modifica, i codici motivo con più di 30 caratteri verranno aggiornati in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1238f-127">with this change, reason codes with more than 30 characters will be updated in Common Data Service.</span></span> <span data-ttu-id="1238f-128">Le modifiche apportate in Common Data Service vengono applicate anche in Talent.</span><span class="sxs-lookup"><span data-stu-id="1238f-128">Changes made in Common Data Service will also be reflected back in Talent.</span></span>

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a><span data-ttu-id="1238f-129">Gestire l'integrazione da Talent in Finance and Operations (351961)</span><span class="sxs-lookup"><span data-stu-id="1238f-129">Address integration from Talent to Finance and Operations (351961)</span></span>

<span data-ttu-id="1238f-130">Questa versione risolve un problema a causa del quale gli indirizzi aggiornati in Talent non venivano aggiornati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1238f-130">This release fixes an issue where addresses updated in Talent weren't updating in Finance and Operations.</span></span> <span data-ttu-id="1238f-131">Le modifiche apportate ai blocchi di indirizzi ora vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="1238f-131">Changes to address blocks will now update.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="1238f-132">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="1238f-132">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="1238f-133">Stampare le valutazioni delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="1238f-133">Print performance reviews</span></span>

<span data-ttu-id="1238f-134">Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.</span><span class="sxs-lookup"><span data-stu-id="1238f-134">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="1238f-135">Area di lavoro Gestione funzionalità</span><span class="sxs-lookup"><span data-stu-id="1238f-135">Feature management workspace</span></span>

<span data-ttu-id="1238f-136">Le funzionalità vengono aggiunte e aggiornate in ogni versione.</span><span class="sxs-lookup"><span data-stu-id="1238f-136">Features are added and updated in every release.</span></span> <span data-ttu-id="1238f-137">L'esperienza di gestione delle funzionalità offre un'area di lavoro in cui è possibile visualizzare un elenco delle funzionalità incluse in ciascuna versione.</span><span class="sxs-lookup"><span data-stu-id="1238f-137">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="1238f-138">Per impostazione predefinita, le nuove funzionalità sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="1238f-138">By default, new features are turned off.</span></span> <span data-ttu-id="1238f-139">È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata.</span><span class="sxs-lookup"><span data-stu-id="1238f-139">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="1238f-140">Per ulteriori informazioni sulle modifiche fornite con la gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="1238f-140">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
