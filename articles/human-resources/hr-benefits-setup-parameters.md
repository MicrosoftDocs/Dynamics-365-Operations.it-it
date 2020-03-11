---
title: Impostare i parametri di Gestione benefit
description: Configurare i parametri di Gestione benefit in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009551"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="2ff03-103">Impostare i parametri di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="2ff03-103">Set Benefits management parameters</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="2ff03-104">Prima di poter impostare piani di congedo in Microsoft Dynamics 365 Human Resources, è necessario configurare i parametri di Gestione benefit.</span><span class="sxs-lookup"><span data-stu-id="2ff03-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you need to configure Benefits management parameters.</span></span> <span data-ttu-id="2ff03-105">Questi parametri impostano valori predefiniti, codici motivo e altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="2ff03-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="2ff03-106">Configurare i parametri generali</span><span class="sxs-lookup"><span data-stu-id="2ff03-106">Configure general parameters</span></span>

1. <span data-ttu-id="2ff03-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="2ff03-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="2ff03-108">Nella scheda **Generale** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="2ff03-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="2ff03-109">Campo</span><span class="sxs-lookup"><span data-stu-id="2ff03-109">Field</span></span> | <span data-ttu-id="2ff03-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ff03-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2ff03-111">**Paese**</span><span class="sxs-lookup"><span data-stu-id="2ff03-111">**Country/region**</span></span> | <span data-ttu-id="2ff03-112">Il campo **Paese** determina l'ordine di visualizzazione di paesi/CAP.</span><span class="sxs-lookup"><span data-stu-id="2ff03-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="2ff03-113">Il paese selezionato viene visualizzato per primo nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="2ff03-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="2ff03-114">**Codice motivo iscrizione**</span><span class="sxs-lookup"><span data-stu-id="2ff03-114">**Enrollment reason code**</span></span> | <span data-ttu-id="2ff03-115">Selezionare un codice motivo predefinito da utilizzare quando vengono creati piani per i dipendenti durante l'elaborazione dell'iscrizione aperta.</span><span class="sxs-lookup"><span data-stu-id="2ff03-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="2ff03-116">**Codice motivo annullamento**</span><span class="sxs-lookup"><span data-stu-id="2ff03-116">**Cancellation reason code**</span></span> | <span data-ttu-id="2ff03-117">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene annullato.</span><span class="sxs-lookup"><span data-stu-id="2ff03-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="2ff03-118">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="2ff03-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="2ff03-119">Gli utenti possono modificarlo in **Codice motivo annullamento** se necessario.</span><span class="sxs-lookup"><span data-stu-id="2ff03-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="2ff03-120">**Codice motivo riapertura**</span><span class="sxs-lookup"><span data-stu-id="2ff03-120">**Reopen reason code**</span></span> | <span data-ttu-id="2ff03-121">Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene riaperto.</span><span class="sxs-lookup"><span data-stu-id="2ff03-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="2ff03-122">Viene visualizzato in una finestra di dialogo durante il processo di annullamento.</span><span class="sxs-lookup"><span data-stu-id="2ff03-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="2ff03-123">Gli utenti possono modificare il **Codice motivo riapertura** se necessario.</span><span class="sxs-lookup"><span data-stu-id="2ff03-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="2ff03-124">**Codice motivo evento reale**</span><span class="sxs-lookup"><span data-stu-id="2ff03-124">**Life event reason code**</span></span> | <span data-ttu-id="2ff03-125">Il codice motivo da utilizzare quando si verifica un evento reale.</span><span class="sxs-lookup"><span data-stu-id="2ff03-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="2ff03-126">**Codice motivo modifica tassi**</span><span class="sxs-lookup"><span data-stu-id="2ff03-126">**Rate change reason code**</span></span> | <span data-ttu-id="2ff03-127">Il codice motivo da utilizzare si annulla e si riapre un piano di benefit per i dipendenti durante il processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="2ff03-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="2ff03-128">Indica quali record sono stati modificati dal processo di aggiornamento delle modifiche ai tassi.</span><span class="sxs-lookup"><span data-stu-id="2ff03-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="2ff03-129">**Nuova assunzione idonea**</span><span class="sxs-lookup"><span data-stu-id="2ff03-129">**New hire eligible**</span></span> | <span data-ttu-id="2ff03-130">Specifica se le nuove assunzioni sono idonee.</span><span class="sxs-lookup"><span data-stu-id="2ff03-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="2ff03-131">**Periodo di iscrizione nuova assunzione**</span><span class="sxs-lookup"><span data-stu-id="2ff03-131">**New hire enrollment period**</span></span> | <span data-ttu-id="2ff03-132">Il periodo di tempo in cui è consentita l'iscrizione di un nuova assunzione.</span><span class="sxs-lookup"><span data-stu-id="2ff03-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="2ff03-133">**Nota**: questa impostazione sostituisce qualsiasi periodo di iscrizione di nuove assunzioni impostato nella regola di idoneità del piano.</span><span class="sxs-lookup"><span data-stu-id="2ff03-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="2ff03-134">**Miglioramento retribuzione annuale**</span><span class="sxs-lookup"><span data-stu-id="2ff03-134">**Annual salary enhancement**</span></span> | <span data-ttu-id="2ff03-135">Specifica se calcolare automaticamente l'importo della **retribuzione benefit annua** in **Dettagli benefit impiego**.</span><span class="sxs-lookup"><span data-stu-id="2ff03-135">Specifies whether to automatically calculate the **Annual benefit salary** amount in **Employment Benefit Details**.</span></span> <span data-ttu-id="2ff03-136">Si basa sul **Tasso di retribuzione fissa**, le **Ore medie** e la **Frequenza di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2ff03-136">It's based on the employee’s **Fixed compensation pay rate**, **Average hours**, and **Payment frequency**.</span></span></br></br><span data-ttu-id="2ff03-137">**Ore medie** x **Retribuzione fissa** x **Frequenza di pagamento** (N. di periodi retributivi) = **Retribuzione benefit annua**</span><span class="sxs-lookup"><span data-stu-id="2ff03-137">**Average hours** x **Fixed pay rate** x **Payment frequency** (# of pay periods) = **Annual benefit salary**</span></span> </br></br><span data-ttu-id="2ff03-138">Se uno qualsiasi dei valori nei campi **Ore medie**, **Tasso di retribuzione fissa** o **Frequenza di pagamento** cambia, il sistema ricalcola automaticamente l'importo della **Retribuzione benefit annua** in base ai valori modificati.</span><span class="sxs-lookup"><span data-stu-id="2ff03-138">If any of the values in the **Average hours**, **Fixed compensation pay rate**, or **Payment frequency** fields change, the system automatically recalculates the employee’s **Annual benefit salary** amount based on the changed values.</span></span> <span data-ttu-id="2ff03-139">Il sistema crea un record **Data valida** per identificare la data e l'ora esatte in cui è avvenuta la modifica.</span><span class="sxs-lookup"><span data-stu-id="2ff03-139">The system creates a **Date effective** record to identify the exact date and time the change occurred.</span></span> <span data-ttu-id="2ff03-140">È possibile modificare manualmente l'importo della **Retribuzione benefit annua** se necessario.</span><span class="sxs-lookup"><span data-stu-id="2ff03-140">You can manually edit the **Annual benefit salary** amount if necessary.</span></span> |
   | <span data-ttu-id="2ff03-141">**Eventi reali abilitati**</span><span class="sxs-lookup"><span data-stu-id="2ff03-141">**Life events enabled**</span></span> | <span data-ttu-id="2ff03-142">Abilita gli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="2ff03-142">Enables life events.</span></span> |
   | <span data-ttu-id="2ff03-143">**Nascondi moduli di benefit legacy**</span><span class="sxs-lookup"><span data-stu-id="2ff03-143">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="2ff03-144">Consente di nascondere i moduli di benefit legacy.</span><span class="sxs-lookup"><span data-stu-id="2ff03-144">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="2ff03-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2ff03-145">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="2ff03-146">Configurare i parametri di Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="2ff03-146">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="2ff03-147">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="2ff03-147">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="2ff03-148">Nella scheda **Dipendente self-service** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="2ff03-148">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="2ff03-149">Campo</span><span class="sxs-lookup"><span data-stu-id="2ff03-149">Field</span></span> | <span data-ttu-id="2ff03-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ff03-150">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2ff03-151">**Verifica benefit**</span><span class="sxs-lookup"><span data-stu-id="2ff03-151">**Benefit verification**</span></span> | <span data-ttu-id="2ff03-152">Il testo di verifica da utilizzare durante il checkout dei benefit self-service.</span><span class="sxs-lookup"><span data-stu-id="2ff03-152">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="2ff03-153">**Seleziona automaticamente i beneficiari designati**</span><span class="sxs-lookup"><span data-stu-id="2ff03-153">**Auto select designees**</span></span> | <span data-ttu-id="2ff03-154">Specifica se selezionare automaticamente le persone a carico e i beneficiari in base alla loro idoneità per le opzioni del piano.</span><span class="sxs-lookup"><span data-stu-id="2ff03-154">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="2ff03-155">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2ff03-155">Select **Save**.</span></span>