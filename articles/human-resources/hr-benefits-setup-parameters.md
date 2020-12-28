---
title: Impostare i parametri di gestione dei benefit e self-service dei dipendenti per tutte le aziende
description: Configurare i parametri di gestione dei benefit e self-service dei dipendenti in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b50c4f71789c34f08ce810312f3c3198303b031e
ms.sourcegitcommit: fd097f6f76f0d8428038fa3655b3188bf093b517
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692699"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a><span data-ttu-id="d2bd2-103">Impostare i parametri di gestione dei benefit e self-service dei dipendenti per tutte le aziende</span><span class="sxs-lookup"><span data-stu-id="d2bd2-103">Set Benefits management and Employee self-service parameters for all companies</span></span>

<span data-ttu-id="d2bd2-104">Prima di poter impostare piani di benefit in Microsoft Dynamics 365 Human Resources, è necessario configurare i parametri di Gestione benefit.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-104">Before you can set up benefit plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="d2bd2-105">Questi parametri impostano valori predefiniti, codici motivo e altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-105">These parameters set default values, reason codes, and other options.</span></span> 

## <a name="configure-general-parameters"></a><span data-ttu-id="d2bd2-106">Configurare i parametri generali</span><span class="sxs-lookup"><span data-stu-id="d2bd2-106">Configure general parameters</span></span>

1. <span data-ttu-id="d2bd2-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri condividi Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="d2bd2-108">Nella scheda **Gestione benefit** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="d2bd2-108">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="d2bd2-109">Campo</span><span class="sxs-lookup"><span data-stu-id="d2bd2-109">Field</span></span> | <span data-ttu-id="d2bd2-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="d2bd2-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d2bd2-111">**Paese**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-111">**Country/region**</span></span> | <span data-ttu-id="d2bd2-112">Il campo **Paese** determina l'ordine di visualizzazione di paesi/CAP.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="d2bd2-113">Il paese selezionato viene visualizzato per primo nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="d2bd2-114">**Codice motivo iscrizione**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-114">**Enrollment reason code**</span></span> | <span data-ttu-id="d2bd2-115">Selezionare un codice motivo predefinito da utilizzare quando vengono creati piani per i dipendenti durante l'elaborazione dell'iscrizione aperta.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="d2bd2-116">**Codice motivo annullamento**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-116">**Cancellation reason code**</span></span> | <span data-ttu-id="d2bd2-117">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene annullato.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="d2bd2-118">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="d2bd2-119">Gli utenti possono modificarlo in **Codice motivo annullamento** se necessario.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="d2bd2-120">**Codice motivo riapertura**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-120">**Reopen reason code**</span></span> | <span data-ttu-id="d2bd2-121">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene riaperto.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="d2bd2-122">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="d2bd2-123">Gli utenti possono modificare il **Codice motivo riapertura** se necessario.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="d2bd2-124">**Codice motivo evento reale**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-124">**Life event reason code**</span></span> | <span data-ttu-id="d2bd2-125">Il codice motivo da utilizzare quando si verifica un evento reale.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="d2bd2-126">**Codice motivo modifica tassi**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-126">**Rate change reason code**</span></span> | <span data-ttu-id="d2bd2-127">Il codice motivo da utilizzare si annulla e si riapre un piano di benefit per i dipendenti durante il processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="d2bd2-128">Indica quali record sono stati modificati dal processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="d2bd2-129">**Retribuzione annuale benefit**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-129">**Benefits annual salary**</span></span> | <span data-ttu-id="d2bd2-130">Consente di impostare un importo **Retribuzione annuale benefit** per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="d2bd2-131">Le risorse umane useranno l'importo **Retribuzione annuale benefit** nel determinare gli importi di copertura, anziché l'importo annuale di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="d2bd2-132">**Nuova assunzione idonea**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-132">**New hire eligible**</span></span> | <span data-ttu-id="d2bd2-133">Specifica se le nuove assunzioni sono idonee.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="d2bd2-134">**Periodo di iscrizione nuova assunzione**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-134">**New hire enrollment period**</span></span> | <span data-ttu-id="d2bd2-135">Il periodo di tempo in cui è consentita l'iscrizione di un nuova assunzione.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="d2bd2-136">**Nota**: questa impostazione sostituisce qualsiasi periodo di iscrizione di nuove assunzioni impostato nella regola di idoneità del piano.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="d2bd2-137">**Frequenza pagamenti predefinita**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-137">**Default pay frequency**</span></span> | <span data-ttu-id="d2bd2-138">La frequenza di retribuzione predefinita da utilizzare quando vengono aggiunti nuovi lavoratori.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="d2bd2-139">**Eventi reali abilitati**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-139">**Life events enabled**</span></span> | <span data-ttu-id="d2bd2-140">Abilita gli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-140">Enables life events.</span></span> |
   | <span data-ttu-id="d2bd2-141">**Nascondi moduli di benefit legacy**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="d2bd2-142">Consente di nascondere i moduli di benefit legacy.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-142">Allows you to hide legacy benefit forms.</span></span> |
   | <span data-ttu-id="d2bd2-143">**Verifica benefit**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-143">**Benefit verification**</span></span> | <span data-ttu-id="d2bd2-144">Il testo di verifica da utilizzare durante il checkout dei benefit self-service.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-144">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="d2bd2-145">**Seleziona automaticamente i beneficiari designati**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-145">**Auto select designees**</span></span> | <span data-ttu-id="d2bd2-146">Specifica se selezionare automaticamente le persone a carico e i beneficiari in base alla loro idoneità per le opzioni del piano.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-146">Specifies whether to automatically select dependents and beneficiaries, based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="d2bd2-147">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-147">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="d2bd2-148">Configurare i parametri di self-service dipendenti</span><span class="sxs-lookup"><span data-stu-id="d2bd2-148">Configure Employee self-service parameters</span></span>

1. <span data-ttu-id="d2bd2-149">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-149">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="d2bd2-150">Nella scheda **Gestione benefit** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="d2bd2-150">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="d2bd2-151">Campo</span><span class="sxs-lookup"><span data-stu-id="d2bd2-151">Field</span></span> | <span data-ttu-id="d2bd2-152">descrizione</span><span class="sxs-lookup"><span data-stu-id="d2bd2-152">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d2bd2-153">**Verifica benefit**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-153">**Benefit verification**</span></span> | <span data-ttu-id="d2bd2-154">Il testo di verifica da utilizzare durante il checkout dei benefit self-service.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-154">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="d2bd2-155">**Seleziona automaticamente i beneficiari designati**</span><span class="sxs-lookup"><span data-stu-id="d2bd2-155">**Auto select designees**</span></span> | <span data-ttu-id="d2bd2-156">Specifica se selezionare automaticamente le persone a carico e i beneficiari in base alla loro idoneità per le opzioni del piano.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-156">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="d2bd2-157">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d2bd2-157">Select **Save**.</span></span>


