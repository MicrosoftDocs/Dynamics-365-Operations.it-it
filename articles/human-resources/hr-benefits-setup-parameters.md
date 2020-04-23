---
title: Impostare i parametri di Gestione benefit
description: Configurare i parametri di Gestione benefit in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229765"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="2a26d-103">Impostare i parametri di gestione dei benefit</span><span class="sxs-lookup"><span data-stu-id="2a26d-103">Set Benefits management parameters</span></span>

<span data-ttu-id="2a26d-104">Prima di poter impostare piani di congedo in Microsoft Dynamics 365 Human Resources, è necessario configurare i parametri di Gestione benefit.</span><span class="sxs-lookup"><span data-stu-id="2a26d-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="2a26d-105">Questi parametri impostano valori predefiniti, codici motivo e altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="2a26d-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="2a26d-106">Configurare i parametri generali</span><span class="sxs-lookup"><span data-stu-id="2a26d-106">Configure general parameters</span></span>

1. <span data-ttu-id="2a26d-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="2a26d-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="2a26d-108">Nella scheda **Generale** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="2a26d-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="2a26d-109">Campo</span><span class="sxs-lookup"><span data-stu-id="2a26d-109">Field</span></span> | <span data-ttu-id="2a26d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a26d-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2a26d-111">**Paese**</span><span class="sxs-lookup"><span data-stu-id="2a26d-111">**Country/region**</span></span> | <span data-ttu-id="2a26d-112">Il campo **Paese** determina l'ordine di visualizzazione di paesi/CAP.</span><span class="sxs-lookup"><span data-stu-id="2a26d-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="2a26d-113">Il paese selezionato viene visualizzato per primo nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="2a26d-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="2a26d-114">**Codice motivo iscrizione**</span><span class="sxs-lookup"><span data-stu-id="2a26d-114">**Enrollment reason code**</span></span> | <span data-ttu-id="2a26d-115">Selezionare un codice motivo predefinito da utilizzare quando vengono creati piani per i dipendenti durante l'elaborazione dell'iscrizione aperta.</span><span class="sxs-lookup"><span data-stu-id="2a26d-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="2a26d-116">**Codice motivo annullamento**</span><span class="sxs-lookup"><span data-stu-id="2a26d-116">**Cancellation reason code**</span></span> | <span data-ttu-id="2a26d-117">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene annullato.</span><span class="sxs-lookup"><span data-stu-id="2a26d-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="2a26d-118">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="2a26d-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="2a26d-119">Gli utenti possono modificarlo in **Codice motivo annullamento** se necessario.</span><span class="sxs-lookup"><span data-stu-id="2a26d-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="2a26d-120">**Codice motivo riapertura**</span><span class="sxs-lookup"><span data-stu-id="2a26d-120">**Reopen reason code**</span></span> | <span data-ttu-id="2a26d-121">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene riaperto.</span><span class="sxs-lookup"><span data-stu-id="2a26d-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="2a26d-122">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="2a26d-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="2a26d-123">Gli utenti possono modificare il **Codice motivo riapertura** se necessario.</span><span class="sxs-lookup"><span data-stu-id="2a26d-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="2a26d-124">**Codice motivo evento reale**</span><span class="sxs-lookup"><span data-stu-id="2a26d-124">**Life event reason code**</span></span> | <span data-ttu-id="2a26d-125">Il codice motivo da utilizzare quando si verifica un evento reale.</span><span class="sxs-lookup"><span data-stu-id="2a26d-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="2a26d-126">**Codice motivo modifica tassi**</span><span class="sxs-lookup"><span data-stu-id="2a26d-126">**Rate change reason code**</span></span> | <span data-ttu-id="2a26d-127">Il codice motivo da utilizzare si annulla e si riapre un piano di benefit per i dipendenti durante il processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="2a26d-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="2a26d-128">Indica quali record sono stati modificati dal processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="2a26d-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="2a26d-129">**Nuova assunzione idonea**</span><span class="sxs-lookup"><span data-stu-id="2a26d-129">**New hire eligible**</span></span> | <span data-ttu-id="2a26d-130">Specifica se le nuove assunzioni sono idonee.</span><span class="sxs-lookup"><span data-stu-id="2a26d-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="2a26d-131">**Periodo di iscrizione nuova assunzione**</span><span class="sxs-lookup"><span data-stu-id="2a26d-131">**New hire enrollment period**</span></span> | <span data-ttu-id="2a26d-132">Il periodo di tempo in cui è consentita l'iscrizione di un nuova assunzione.</span><span class="sxs-lookup"><span data-stu-id="2a26d-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="2a26d-133">**Nota**: questa impostazione sostituisce qualsiasi periodo di iscrizione di nuove assunzioni impostato nella regola di idoneità del piano.</span><span class="sxs-lookup"><span data-stu-id="2a26d-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="2a26d-134">**Eventi reali abilitati**</span><span class="sxs-lookup"><span data-stu-id="2a26d-134">**Life events enabled**</span></span> | <span data-ttu-id="2a26d-135">Abilita gli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="2a26d-135">Enables life events.</span></span> |
   | <span data-ttu-id="2a26d-136">**Nascondi moduli di benefit legacy**</span><span class="sxs-lookup"><span data-stu-id="2a26d-136">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="2a26d-137">Consente di nascondere i moduli di benefit legacy.</span><span class="sxs-lookup"><span data-stu-id="2a26d-137">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="2a26d-138">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2a26d-138">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="2a26d-139">Configurare i parametri di Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="2a26d-139">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="2a26d-140">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="2a26d-140">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="2a26d-141">Nella scheda **Dipendente self-service** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="2a26d-141">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="2a26d-142">Campo</span><span class="sxs-lookup"><span data-stu-id="2a26d-142">Field</span></span> | <span data-ttu-id="2a26d-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a26d-143">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2a26d-144">**Verifica benefit**</span><span class="sxs-lookup"><span data-stu-id="2a26d-144">**Benefit verification**</span></span> | <span data-ttu-id="2a26d-145">Il testo di verifica da utilizzare durante il checkout dei benefit self-service.</span><span class="sxs-lookup"><span data-stu-id="2a26d-145">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="2a26d-146">**Seleziona automaticamente i beneficiari designati**</span><span class="sxs-lookup"><span data-stu-id="2a26d-146">**Auto select designees**</span></span> | <span data-ttu-id="2a26d-147">Specifica se selezionare automaticamente le persone a carico e i beneficiari in base alla loro idoneità per le opzioni del piano.</span><span class="sxs-lookup"><span data-stu-id="2a26d-147">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="2a26d-148">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2a26d-148">Select **Save**.</span></span>
