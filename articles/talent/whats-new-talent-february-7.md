---
title: Novità o modifiche in Dynamics 365 for Talent (7 febbraio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 23386d04fac5a41682d3ced448ce07e6729def3c
ms.sourcegitcommit: b3b21795f36e5852ffe18200d6fe0b93363b1cbd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "377743"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-7-2019"></a><span data-ttu-id="238bf-103">Novità o modifiche in Dynamics 365 for Talent (7 febbraio 2019)</span><span class="sxs-lookup"><span data-stu-id="238bf-103">What's new or changed in Dynamics 365 for Talent (February 7, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="238bf-104">Questo argomento descrive le funzionalità nuove o modificate di Talent.</span><span class="sxs-lookup"><span data-stu-id="238bf-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="238bf-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="238bf-105">Changes in Attract</span></span>

### <a name="interview-scheduling-enhancements"></a><span data-ttu-id="238bf-106">Miglioramenti alla programmazione dei colloqui</span><span class="sxs-lookup"><span data-stu-id="238bf-106">Interview scheduling enhancements</span></span>
<span data-ttu-id="238bf-107">Dei miglioramenti sono stati apportati all'esperienza completa di programmazione dei colloqui.</span><span class="sxs-lookup"><span data-stu-id="238bf-107">Improvements have been made to the end-to-end interview scheduling experience.</span></span> <span data-ttu-id="238bf-108">Ora è possibile visualizzare la disponibilità nel calendario di un candidato interno e utilizzare il calendario del candidato interno per suggerimenti di programmazione.</span><span class="sxs-lookup"><span data-stu-id="238bf-108">You can now see the calendar availability of an internal candidate and use the internal candidate’s calendar for schedule recommendations.</span></span> <span data-ttu-id="238bf-109">Per ulteriori informazioni, vedere [Programmazione e riscontro del colloquio](interview-scheduling-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="238bf-109">For more information, see [Interview scheduling and feedback](interview-scheduling-feedback.md).</span></span>

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a><span data-ttu-id="238bf-110">Annunci di lavoro in LinkedIn - Problema di società non corrispondente risolto</span><span class="sxs-lookup"><span data-stu-id="238bf-110">Job posting to LinkedIn – company mismatch issue fixed</span></span>
<span data-ttu-id="238bf-111">Un'uscita è stata fissa dei processi registrati LinkedIn Attract stavano comparendo nel nome della società errato.</span><span class="sxs-lookup"><span data-stu-id="238bf-111">An issue has been fixed where jobs posted to LinkedIn from Attract were appearing under the wrong company name.</span></span> <span data-ttu-id="238bf-112">Per ulteriori informazioni, vedere [Creazione, approvazione e pubblicazione di annunci di mansioni in Attract](creating-jobs-attract.md).</span><span class="sxs-lookup"><span data-stu-id="238bf-112">For more information, see [Create, approve, and post jobs in Attract](creating-jobs-attract.md).</span></span>

### <a name="career-site-url-displayed-in-admin-settings"></a><span data-ttu-id="238bf-113">URL del sito di avanzamento professionale visualizzato nelle impostazioni di amministrazione</span><span class="sxs-lookup"><span data-stu-id="238bf-113">Career site URL displayed in Admin settings</span></span>
<span data-ttu-id="238bf-114">L'URL della home page del sito di avanzamento professionale è ora visualizzato in **Impostazioni di amministrazione** in **Gestione del sito per le possibilità di carriera**.</span><span class="sxs-lookup"><span data-stu-id="238bf-114">The career site home page URL is now displayed in **Admin Settings** under **Career Site management**.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="238bf-115">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="238bf-115">Changes in Core HR</span></span>

<span data-ttu-id="238bf-116">**Build 8.1.2134**</span><span class="sxs-lookup"><span data-stu-id="238bf-116">**Build 8.1.2134**</span></span>

### <a name="multiple-compensation-levels-supported-on-jobs"></a><span data-ttu-id="238bf-117">Molteplici livelli retributivi più supportati nelle mansioni</span><span class="sxs-lookup"><span data-stu-id="238bf-117">Multiple compensation levels supported on jobs</span></span>
<span data-ttu-id="238bf-118">Questa modifica consente la definizione di più livelli retributivi in una mansione, abilitando intervalli di retribuzione fissa dei dipendenti che possono differire tra i piani quando si utilizza la stessa mansione.</span><span class="sxs-lookup"><span data-stu-id="238bf-118">This change allows for more than one compensation level to be defined on a job, enabling employee fixed compensation ranges which may differ between plans when using the same job.</span></span> 

<span data-ttu-id="238bf-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="238bf-119">For example:</span></span>    
<span data-ttu-id="238bf-120">*Mansione* - *Livelli retributivi associati* account manager: B1 and B2 - Ogni livello ha un intervallo di valori definito.</span><span class="sxs-lookup"><span data-stu-id="238bf-120">*Job* - Account Manager *Associated compensation levels:* B1 and B2 - Each level has a defined range of values.</span></span> <span data-ttu-id="238bf-121">B1 = Min. 50.000, Interm. 60.000, Mass. 75.000 e B2= Min. 65.000, Interm. 74.000, Mass. 85.000.</span><span class="sxs-lookup"><span data-stu-id="238bf-121">B1 = Min 50,000, Mid 60,000, Max 75,000 and B2 = Min 65,000, Mid 74,000, Max 85,000.</span></span> <span data-ttu-id="238bf-122">Durante la creazione della retribuzione fissa per i dipendenti, in base alle regole di idoneità definite, ciascun piano fisso può ora puntare alla stessa mansione e a livelli diversi nella mansione.</span><span class="sxs-lookup"><span data-stu-id="238bf-122">When creating fixed compensation for employees, based on the eligibility rules defined, each fixed plan can now point to the same job and to different levels on the job.</span></span> <span data-ttu-id="238bf-123">Ciò consente la definizione di piani in aree geografiche/società definite, che puntano alla stessa mansione ma a intervalli diversi senza duplicare le mansioni nell'account per tali differenze.</span><span class="sxs-lookup"><span data-stu-id="238bf-123">This allows for plans to be defined in different regions/companies and point to the same job but different ranges without duplicating jobs to account for these differences.</span></span>

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a><span data-ttu-id="238bf-124">Il campo Livello retributivo è stato aggiunto all'entità Retribuzione fissa dipendente</span><span class="sxs-lookup"><span data-stu-id="238bf-124">Compensation level field has been added to the Employee fixed compensation entity</span></span> 
<span data-ttu-id="238bf-125">Con questo aggiornamento, l'entità Retribuzione fissa dipendente è stata aggiornata per includere il campo **Livello retributivo**.</span><span class="sxs-lookup"><span data-stu-id="238bf-125">With this update, the employee fixed compensation entity has been updated to include the **Compensation level** field.</span></span> <span data-ttu-id="238bf-126">Questa aggiunta facilita l'aggiornamento i piani di retribuzione fissa dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="238bf-126">This addition makes it easier to update employee fixed compensation plans.</span></span> 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a><span data-ttu-id="238bf-127">Aggiornamento della famiglia di mansioni durante l'aggiornamento e la creazione di nuove posizioni</span><span class="sxs-lookup"><span data-stu-id="238bf-127">Update Job family when updating and creating new positions</span></span>
<span data-ttu-id="238bf-128">Quando si modifica una mansione in una posizione, verrà utilizzato il valore predefinito di **Famiglia di processi** in base alla mansione selezionata.</span><span class="sxs-lookup"><span data-stu-id="238bf-128">When changing the job on a position, **Job family** will now default based on the job selected.</span></span>

### <a name="performance-improvements-when-rendering-workspaces"></a><span data-ttu-id="238bf-129">Miglioramento delle prestazioni durante il rendering delle aree di lavoro</span><span class="sxs-lookup"><span data-stu-id="238bf-129">Performance improvements when rendering workspaces</span></span>
<span data-ttu-id="238bf-130">La scheda Analisi nelle aree di lavoro verrà ora caricata quando si accede a tali pagine.</span><span class="sxs-lookup"><span data-stu-id="238bf-130">Analytics tabs on workspaces will now load only when accessing those pages.</span></span> <span data-ttu-id="238bf-131">Un indicatore verrà visualizzato durante il rendering iniziale della pagina nell'angolo in alto a sinistra della pagina.</span><span class="sxs-lookup"><span data-stu-id="238bf-131">An indicator will display during the initial rendering of the page in the upper-left corner of the page.</span></span>
