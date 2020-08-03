---
title: Impostare i parametri di Gestione benefit
description: Configurare i parametri di Gestione benefit in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
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
ms.openlocfilehash: 85bbe5d3b422f2f29f1d1fe8ee269b407da691c2
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599358"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="4a787-103">Impostare i parametri di gestione dei benefit</span><span class="sxs-lookup"><span data-stu-id="4a787-103">Set Benefits management parameters</span></span>

<span data-ttu-id="4a787-104">Prima di poter impostare piani di congedo in Microsoft Dynamics 365 Human Resources, è necessario configurare i parametri di Gestione benefit.</span><span class="sxs-lookup"><span data-stu-id="4a787-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="4a787-105">Questi parametri impostano valori predefiniti, codici motivo e altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="4a787-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="4a787-106">Configurare i parametri generali</span><span class="sxs-lookup"><span data-stu-id="4a787-106">Configure general parameters</span></span>

1. <span data-ttu-id="4a787-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri condividi Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="4a787-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="4a787-108">Nella scheda **Generale** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="4a787-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="4a787-109">Campo</span><span class="sxs-lookup"><span data-stu-id="4a787-109">Field</span></span> | <span data-ttu-id="4a787-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a787-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="4a787-111">**Paese**</span><span class="sxs-lookup"><span data-stu-id="4a787-111">**Country/region**</span></span> | <span data-ttu-id="4a787-112">Il campo **Paese** determina l'ordine di visualizzazione di paesi/CAP.</span><span class="sxs-lookup"><span data-stu-id="4a787-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="4a787-113">Il paese selezionato viene visualizzato per primo nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="4a787-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="4a787-114">**Codice motivo iscrizione**</span><span class="sxs-lookup"><span data-stu-id="4a787-114">**Enrollment reason code**</span></span> | <span data-ttu-id="4a787-115">Selezionare un codice motivo predefinito da utilizzare quando vengono creati piani per i dipendenti durante l'elaborazione dell'iscrizione aperta.</span><span class="sxs-lookup"><span data-stu-id="4a787-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="4a787-116">**Codice motivo annullamento**</span><span class="sxs-lookup"><span data-stu-id="4a787-116">**Cancellation reason code**</span></span> | <span data-ttu-id="4a787-117">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene annullato.</span><span class="sxs-lookup"><span data-stu-id="4a787-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="4a787-118">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="4a787-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="4a787-119">Gli utenti possono modificarlo in **Codice motivo annullamento** se necessario.</span><span class="sxs-lookup"><span data-stu-id="4a787-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="4a787-120">**Codice motivo riapertura**</span><span class="sxs-lookup"><span data-stu-id="4a787-120">**Reopen reason code**</span></span> | <span data-ttu-id="4a787-121">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene riaperto.</span><span class="sxs-lookup"><span data-stu-id="4a787-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="4a787-122">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="4a787-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="4a787-123">Gli utenti possono modificare il **Codice motivo riapertura** se necessario.</span><span class="sxs-lookup"><span data-stu-id="4a787-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="4a787-124">**Codice motivo evento reale**</span><span class="sxs-lookup"><span data-stu-id="4a787-124">**Life event reason code**</span></span> | <span data-ttu-id="4a787-125">Il codice motivo da utilizzare quando si verifica un evento reale.</span><span class="sxs-lookup"><span data-stu-id="4a787-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="4a787-126">**Codice motivo modifica tassi**</span><span class="sxs-lookup"><span data-stu-id="4a787-126">**Rate change reason code**</span></span> | <span data-ttu-id="4a787-127">Il codice motivo da utilizzare si annulla e si riapre un piano di benefit per i dipendenti durante il processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="4a787-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="4a787-128">Indica quali record sono stati modificati dal processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="4a787-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="4a787-129">**Retribuzione annuale benefit**</span><span class="sxs-lookup"><span data-stu-id="4a787-129">**Benefits annual salary**</span></span> | <span data-ttu-id="4a787-130">Consente di impostare un importo **Retribuzione annuale benefit** per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="4a787-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="4a787-131">Le risorse umane useranno l'importo **Retribuzione annuale benefit** nel determinare gli importi di copertura, anziché l'importo annuale di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="4a787-131">Human Resources will use the **Benefits annual salary** amount when determing coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="4a787-132">**Nuova assunzione idonea**</span><span class="sxs-lookup"><span data-stu-id="4a787-132">**New hire eligible**</span></span> | <span data-ttu-id="4a787-133">Specifica se le nuove assunzioni sono idonee.</span><span class="sxs-lookup"><span data-stu-id="4a787-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="4a787-134">**Periodo di iscrizione nuova assunzione**</span><span class="sxs-lookup"><span data-stu-id="4a787-134">**New hire enrollment period**</span></span> | <span data-ttu-id="4a787-135">Il periodo di tempo in cui è consentita l'iscrizione di un nuova assunzione.</span><span class="sxs-lookup"><span data-stu-id="4a787-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="4a787-136">**Nota**: questa impostazione sostituisce qualsiasi periodo di iscrizione di nuove assunzioni impostato nella regola di idoneità del piano.</span><span class="sxs-lookup"><span data-stu-id="4a787-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="4a787-137">**Frequenza pagamenti predefinita**</span><span class="sxs-lookup"><span data-stu-id="4a787-137">**Default pay frequency**</span></span> | <span data-ttu-id="4a787-138">La frequenza di retribuzione predefinita da utilizzare quando vengono aggiunti nuovi lavoratori.</span><span class="sxs-lookup"><span data-stu-id="4a787-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="4a787-139">**Eventi reali abilitati**</span><span class="sxs-lookup"><span data-stu-id="4a787-139">**Life events enabled**</span></span> | <span data-ttu-id="4a787-140">Abilita gli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="4a787-140">Enables life events.</span></span> |
   | <span data-ttu-id="4a787-141">**Nascondi moduli di benefit legacy**</span><span class="sxs-lookup"><span data-stu-id="4a787-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="4a787-142">Consente di nascondere i moduli di benefit legacy.</span><span class="sxs-lookup"><span data-stu-id="4a787-142">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="4a787-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4a787-143">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="4a787-144">Configurare i parametri di Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="4a787-144">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="4a787-145">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="4a787-145">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="4a787-146">Nella scheda **Dipendente self-service** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="4a787-146">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="4a787-147">Campo</span><span class="sxs-lookup"><span data-stu-id="4a787-147">Field</span></span> | <span data-ttu-id="4a787-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a787-148">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="4a787-149">**Verifica benefit**</span><span class="sxs-lookup"><span data-stu-id="4a787-149">**Benefit verification**</span></span> | <span data-ttu-id="4a787-150">Il testo di verifica da utilizzare durante il checkout dei benefit self-service.</span><span class="sxs-lookup"><span data-stu-id="4a787-150">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="4a787-151">**Seleziona automaticamente i beneficiari designati**</span><span class="sxs-lookup"><span data-stu-id="4a787-151">**Auto select designees**</span></span> | <span data-ttu-id="4a787-152">Specifica se selezionare automaticamente le persone a carico e i beneficiari in base alla loro idoneità per le opzioni del piano.</span><span class="sxs-lookup"><span data-stu-id="4a787-152">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="4a787-153">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4a787-153">Select **Save**.</span></span>
