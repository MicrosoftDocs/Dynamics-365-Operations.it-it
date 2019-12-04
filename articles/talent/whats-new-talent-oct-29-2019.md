---
title: Novità o modifiche in Dynamics 365 Talent (29 ottobre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 83b4734190163ebd2dc29096632642bd45c61e8f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773879"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a><span data-ttu-id="2e5ac-103">Novità o modifiche in Dynamics 365 Talent (29 ottobre 2019)</span><span class="sxs-lookup"><span data-stu-id="2e5ac-103">What's new or changed in Dynamics 365 Talent (October 29, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2e5ac-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="2e5ac-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="2e5ac-105">Changes in Attract</span></span>

<span data-ttu-id="2e5ac-106">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="2e5ac-107">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="2e5ac-107">Changes in Onboard</span></span>

<span data-ttu-id="2e5ac-108">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="2e5ac-109">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="2e5ac-109">Changes in Core HR</span></span>

<span data-ttu-id="2e5ac-110">Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2586.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-110">Changes described in this section apply to build number 8.1.2586.</span></span> <span data-ttu-id="2e5ac-111">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="2e5ac-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a><span data-ttu-id="2e5ac-112">Elimina parti senza ruoli deve essere attivo per impostazione predefinita (371233)</span><span class="sxs-lookup"><span data-stu-id="2e5ac-112">Delete parties with no roles should be on by default (371233)</span></span>

<span data-ttu-id="2e5ac-113">Quando si esegue il provisioning di un nuovo ambiente in Talent, **Elimina parti senza ruoli** è attivo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-113">When you provision a new environment in Talent, **Delete parties if no roles exist** is turned on by default.</span></span> <span data-ttu-id="2e5ac-114">Quando si elimina un lavoratore, la parte associata al lavoratore non viene rimossa a meno che questa impostazione non sia attiva.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-114">When you delete a worker, the party associated with the worker is not removed unless this setting is on.</span></span> <span data-ttu-id="2e5ac-115">Questa modifica limita i record duplicati nella rubrica globale quando è necessario importare, modificare o reimportare i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-115">This change limits duplicate records in the global address book when you need to import, change, or reimport workers.</span></span>

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a><span data-ttu-id="2e5ac-116">Le bozze e le richieste di congedo annullate devono poter essere eliminate in Common Data Service (376999)</span><span class="sxs-lookup"><span data-stu-id="2e5ac-116">Draft and cancelled leave requests should be allowed to be deleted in Common Data Service (376999)</span></span>

<span data-ttu-id="2e5ac-117">Con questa modifica, è ora possibile eliminare le richieste di congedo con stato **Bozza** o **Annullato** in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-117">With this change, you can now delete leave requests with a status of **Draft** or **Cancelled** in Common Data Service.</span></span>

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a><span data-ttu-id="2e5ac-118">I valori aggiuntivi dell'elenco nei campi personalizzati non vengono riflessi in Common Data Service quando si fa clic su Applica nel modulo Campi personalizzati (379599)</span><span class="sxs-lookup"><span data-stu-id="2e5ac-118">Additional list values in custom fields aren't reflected in Common Data Service after clicking Apply on the Custom fields form (379599)</span></span>

<span data-ttu-id="2e5ac-119">Quando si aggiungono nuovi valori di elenco a un campo personalizzato esistente che è già sincronizzato con Common Data Service, i valori ora sono disponibili in Common Data Service dopo aver applicato le modifiche nel modulo **Campi personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-119">When you add new list values to an existing custom field that has already synchronized with Common Data Service, they're now available in Common Data Serivce after you apply your changes in the **Custom fields** form.</span></span>

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a><span data-ttu-id="2e5ac-120">Applicare gli elenchi di controllo per l'inserimento tra le persone giuridiche quando esiste più di un impiego (371270)</span><span class="sxs-lookup"><span data-stu-id="2e5ac-120">Apply onboarding checklists across legal entities when more than one employment exists (371270)</span></span>

<span data-ttu-id="2e5ac-121">Nella versione della settimana, è possibile applicare gli elenchi di controllo ai dipendenti con più di di impiego in **Modulo lavoratore > Elenchi di controllo**.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-121">In this week's release, you can apply checklists to employees with more than one employment in **Worker form > Checklists**.</span></span>

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a><span data-ttu-id="2e5ac-122">La funzionalità di anteprima dell'iscrizione aperta ai vantaggi è stata rimossa</span><span class="sxs-lookup"><span data-stu-id="2e5ac-122">Benefits open enrollment preview feature has been removed</span></span>

<span data-ttu-id="2e5ac-123">In concomitanza con l'annuncio nel [post di blog sugli investimenti strategici in Core HR per promuovere l'eccellenza operativa](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft ha rimosso la funzionalità di iscrizione aperta ai vantaggi dall'anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-123">In conjunction with our announcement in the [Strategic investments in core HR drive operational excellence](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) blog post, Microsoft has removed the benefits open enrollment feature from public preview.</span></span> <span data-ttu-id="2e5ac-124">Nuove funzionalità verranno rilasciate in futuro.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-124">New functionality will be released in the future.</span></span> <span data-ttu-id="2e5ac-125">L'utilizzo di produzione della funzionalità dell'iscrizione aperta ai vantaggi non è supportato.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-125">Production use of the benefits open enrollment feature isn't be supported.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="2e5ac-126">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="2e5ac-126">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="2e5ac-127">Stampare le valutazioni delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="2e5ac-127">Print performance reviews</span></span>

<span data-ttu-id="2e5ac-128">Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-128">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="2e5ac-129">Area di lavoro Gestione funzionalità</span><span class="sxs-lookup"><span data-stu-id="2e5ac-129">Feature management workspace</span></span>

<span data-ttu-id="2e5ac-130">Le funzionalità vengono aggiunte e aggiornate in ogni versione.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-130">Features are added and updated in every release.</span></span> <span data-ttu-id="2e5ac-131">L'esperienza di gestione delle funzionalità offre un'area di lavoro in cui è possibile visualizzare un elenco delle funzionalità incluse in ciascuna versione.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-131">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="2e5ac-132">Per impostazione predefinita, le nuove funzionalità sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-132">By default, new features are turned off.</span></span> <span data-ttu-id="2e5ac-133">È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-133">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="2e5ac-134">Per ulteriori informazioni sulle modifiche fornite con la gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="2e5ac-134">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
