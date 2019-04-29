---
title: Novità o modifiche in Dynamics 365 for Talent (5 marzo 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e4ad32ef71c87f52e59959d80c21ae7fcd6d6524
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "949807"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-5-2019"></a><span data-ttu-id="4f012-103">Novità o modifiche in Dynamics 365 for Talent (5 marzo 2019)</span><span class="sxs-lookup"><span data-stu-id="4f012-103">What's new or changed in Dynamics 365 for Talent (March 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4f012-104">Questo argomento descrive le funzionalità nuove o modificate di Talent</span><span class="sxs-lookup"><span data-stu-id="4f012-104">This topic describes features that are either new or changed in Talent</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="4f012-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="4f012-105">Changes in Attract</span></span>

### <a name="extending-option-sets-in-attract"></a><span data-ttu-id="4f012-106">Estensione di set di opzioni in Attract</span><span class="sxs-lookup"><span data-stu-id="4f012-106">Extending option sets in Attract</span></span>

<span data-ttu-id="4f012-107">In Attract, molteplici campi sono set di opzioni in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4f012-107">In Attract, there are multiple fields that are option sets within the Common Data Service.</span></span> <span data-ttu-id="4f012-108">Sono state introdotte nuove funzionalità per l'estensione di set di opzioni, a partire dai campi **Rifiuto**, **Tipo di impiego** e **Tipo di anzianità**.</span><span class="sxs-lookup"><span data-stu-id="4f012-108">New capabilities have been introduced to extend the option sets, beginning with the **Rejection** reason field, **Employment type** field, and **Seniority type** field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f012-109">La funzionalità di pubblicazione di annunci di lavoro in LinkedIn richiede l'utilizzo dei campi **Tipo di impiego** e **Tipo di anzianità** nella pagina **Dettagli mansione**.</span><span class="sxs-lookup"><span data-stu-id="4f012-109">The job posting to LinkedIn functionality requires the use of the **Employment type** and **Seniority type** fields on the **Job details** page.</span></span> <span data-ttu-id="4f012-110">I valori predefiniti in questi campi sono supportati da LinkedIn e visualizzati quando l'annuncio viene pubblicato.</span><span class="sxs-lookup"><span data-stu-id="4f012-110">The default values in these fields are supported by LinkedIn and are displayed when the job is posted.</span></span> <span data-ttu-id="4f012-111">Se si pubblicano annunci di lavoro in LinkedIn e si modificano i valori del set di opzioni esistente per questi campi, l'annuncio di lavoro verrà comunque pubblicato ma LinkedIn non visualizzerà i valori **Tipo di anzianità** e **Tipo di impiego**.</span><span class="sxs-lookup"><span data-stu-id="4f012-111">If you are posting jobs to LinkedIn and you modify the existing option set values for these fields, the job will still post, but LinkedIn will not display the custom **Employment type** and **Seniority type** values.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="4f012-112">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="4f012-112">Changes in Onboarding</span></span>

### <a name="private-preview-for-onboard-teams"></a><span data-ttu-id="4f012-113">Anteprima privata per i team Onboard</span><span class="sxs-lookup"><span data-stu-id="4f012-113">Private preview for Onboard teams</span></span>
<span data-ttu-id="4f012-114">Ora è possibile condividere e collaborare facilmente sui modelli nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f012-114">You can now easily share and collaborate on templates across your entire organization.</span></span> <span data-ttu-id="4f012-115">Per ulteriori informazioni, vedere [Procedura consigliate sulla condivisione nell'organizzazione mediante i team Onboard](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span><span class="sxs-lookup"><span data-stu-id="4f012-115">For more information, see [Share best practices across your organization using Onboard Teams](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span></span>

### <a name="private-preview-for-assignee-placeholders"></a><span data-ttu-id="4f012-116">Anteprima privata per segnaposto di assegnatari</span><span class="sxs-lookup"><span data-stu-id="4f012-116">Private preview for assignee placeholders</span></span>
<span data-ttu-id="4f012-117">È possibile arricchire i modelli assegnando attività a ruoli anziché a individui.</span><span class="sxs-lookup"><span data-stu-id="4f012-117">You can enrich your templates by assigning activities to roles instead of individuals.</span></span> <span data-ttu-id="4f012-118">I ruoli sono quindi assegnati a utenti al momento della creazione della guida.</span><span class="sxs-lookup"><span data-stu-id="4f012-118">Roles are then assigned to individuals at the time of guide creation.</span></span> <span data-ttu-id="4f012-119">Per ulteriori informazioni, vedere [Semplificare l'amministrazione della guida assegnando attività a ruoli](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span><span class="sxs-lookup"><span data-stu-id="4f012-119">For more information, see [Streamline guide administration by assigning activities to roles](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="4f012-120">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="4f012-120">Changes in Core HR</span></span>
<span data-ttu-id="4f012-121">**Build 8.1.2178**</span><span class="sxs-lookup"><span data-stu-id="4f012-121">**Build 8.1.2178**</span></span>

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a><span data-ttu-id="4f012-122">Configurare il flusso di lavoro per l'approvazione automatica o tenere traccia del flusso di lavoro quando un superiore o un responsabile risorse umane invia o aggiorna le richieste di permesso</span><span class="sxs-lookup"><span data-stu-id="4f012-122">Configure workflow to auto-approve or follow workflow when an HR or line manager submits or updates time off requests</span></span>
<span data-ttu-id="4f012-123">Nuove condizioni di flusso di lavoro sono state aggiunte per l'approvazione automatica delle richieste di congedo se inviate dal manager del dipendente o dalle Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="4f012-123">New workflow conditions have been added to allow for leave requests to be automatically approved if submitted by an employee’s manager or by HR.</span></span> <span data-ttu-id="4f012-124">Un modo di ottenere questa approvazione automatica in un flusso di lavoro è di abilitare un'azione automatica nell'approvazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4f012-124">One way to achieve this auto-approval on a workflow is to enable an automatic action on the workflow approval.</span></span>

<span data-ttu-id="4f012-125">Le condizioni aggiunte includono:</span><span class="sxs-lookup"><span data-stu-id="4f012-125">The conditions that have been added include:</span></span>

- <span data-ttu-id="4f012-126">Inviata da - Utilizzata per valutare l'ID utente di sistema dell'utente che ha inviato la richiesta al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4f012-126">Submitted by - Used to evaluate the system user ID of the user who submitted the request to workflow.</span></span>
- <span data-ttu-id="4f012-127">Inviata per conto di - Utilizzata per valutare se la richiesta di congedo è stata inviata per conto del lavoratore associato alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="4f012-127">Submitted on behalf of - Used to evaluate if the leave request was submitted on behalf of the worker associated to the request.</span></span>
- <span data-ttu-id="4f012-128">Inviata da Risorse umane - Utilizzata per valutare se l'utente di sistema che ha inviato la richiesta al flusso di lavoro ha un ruolo Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="4f012-128">Submitted by human resources - Used to evaluate if the system user who submitted the request to workflow is in a Human Resources role.</span></span>
- <span data-ttu-id="4f012-129">Inviata da Responsabile - Utilizzata per valutare se l'utente che ha inviato la richiesta di congedo al flusso di lavoro è un responsabile gerarchia del lavoratore associato alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="4f012-129">Submitted by manager - Used to evaluate if the user who submitted the leave request to workflow is a line hierarchy manager of the worker associated to the request.</span></span>

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a><span data-ttu-id="4f012-130">Attivare la retribuzione fissa dei dipendenti per assegnazioni di posizione future</span><span class="sxs-lookup"><span data-stu-id="4f012-130">Enable employee fixed compensation for future position assignments</span></span>
<span data-ttu-id="4f012-131">È tipico per i dipendenti entrare a far parte di un'organizzazione con una data di inizio futura.</span><span class="sxs-lookup"><span data-stu-id="4f012-131">It is typical for employees to join an organization with a future start date.</span></span> <span data-ttu-id="4f012-132">Questa modifica consente di definire la retribuzione fissa dei dipendenti con assegnazioni di posizione future.</span><span class="sxs-lookup"><span data-stu-id="4f012-132">This change enables defining fixed compensation for employees with future position assignments.</span></span>

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a><span data-ttu-id="4f012-133">I campi delle retribuzioni di posizione sono vuoti durante la modifica della posizione</span><span class="sxs-lookup"><span data-stu-id="4f012-133">Position Payroll fields are blank when editing the position</span></span>
<span data-ttu-id="4f012-134">Con questa modifica, quando si richiedono modifiche alle posizioni esistenti, per impostazione predefinita i valori dei campi delle retribuzioni saranno i valori correnti.</span><span class="sxs-lookup"><span data-stu-id="4f012-134">With this change, when requesting changes to existing positions, the payroll fields will now default to the current values.</span></span>

### <a name="other-miscellaneous-bug-fixes"></a><span data-ttu-id="4f012-135">Altre correzioni di bug varie</span><span class="sxs-lookup"><span data-stu-id="4f012-135">Other miscellaneous bug fixes</span></span>
<span data-ttu-id="4f012-136">Altre correzioni di bug minori incluse in questa versione.</span><span class="sxs-lookup"><span data-stu-id="4f012-136">Other minor bug fixes are included with this release.</span></span>

### <a name="upgrade-to-common-data-service"></a><span data-ttu-id="4f012-137">Eseguire l'aggiornamento a Common Data Service</span><span class="sxs-lookup"><span data-stu-id="4f012-137">Upgrade to Common Data Service</span></span>
<span data-ttu-id="4f012-138">Le scadenze per l'aggiornamento di Common Data Service sono imminenti.</span><span class="sxs-lookup"><span data-stu-id="4f012-138">Deadlines to upgrade to Common Data Service are quickly approaching.</span></span> <span data-ttu-id="4f012-139">Accedere all'interfaccia di amministrazione PowerApps per determinare se il database deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="4f012-139">Sign in to the PowerApps Admin center to determine if your database needs to be upgraded.</span></span> <span data-ttu-id="4f012-140">Per ulteriori informazioni sulle scadenze e sui passaggi necessari per eseguire l'aggiornamento, vedere [Aggiornamento di Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span><span class="sxs-lookup"><span data-stu-id="4f012-140">For more information about deadlines and necessary steps to upgrade, see [Upgrade to Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="4f012-141">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="4f012-141">Coming soon</span></span>

###  <a name="advanced-compensation-security-fixed-and-variable"></a><span data-ttu-id="4f012-142">Protezione retribuzione avanzata (fissa e variabile)</span><span class="sxs-lookup"><span data-stu-id="4f012-142">Advanced compensation security (fixed and variable)</span></span>
<span data-ttu-id="4f012-143">In molte organizzazioni, i responsabili retribuzione e benefit possono accedere solo a determinati record di retribuzione, ad esempio i record di dirigenti o di dipendenti in base all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="4f012-143">In many organizations, compensation and benefits managers can only access certain compensation records, such as records for executives or regional-based employees.</span></span> <span data-ttu-id="4f012-144">Con questa modifica, è possibile gestire i piani di retribuzione per differenti popolazioni di dipendenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f012-144">With this change, you can manage and maintain the compensation plans for different employee populations in the organization.</span></span> <span data-ttu-id="4f012-145">Ai piani fissi e variabili è possibile assegnare ruoli di sicurezza, che determineranno l'accesso ai piani e ai dati dei dipendenti correlati ai piani, ad esempio i record di stipendi o premi.</span><span class="sxs-lookup"><span data-stu-id="4f012-145">Fixed and variable plans can be assigned security roles, which will determine the access to the plans and the employee data related to the plans, such as salary or bonus records.</span></span> <span data-ttu-id="4f012-146">Solo i ruoli con l'accesso potranno elaborare la retribuzione per quei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4f012-146">Only the roles with the given access will be able to process compensation for those employees.</span></span>

###  <a name="platform-update-24"></a><span data-ttu-id="4f012-147">Update 24 della piattaforma</span><span class="sxs-lookup"><span data-stu-id="4f012-147">Platform update 24</span></span>
<span data-ttu-id="4f012-148">Per ulteriori informazioni sull'aggiornamento 24 della piattaforma, vedere [Novità o modifiche nell'aggiornamento 24 della piattaforma Finance and Operations (marzo 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="4f012-148">For additional details about Platform update 24, see [What's new or changed in Finance and Operations platform update 24 (March 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span></span>
