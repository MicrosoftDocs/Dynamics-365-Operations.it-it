---
title: Configurare tipi di congedo e assenza
description: Impostare i tipi di congedo che i dipendenti possono prendere in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198052"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="4797d-103">Configurare tipi di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="4797d-103">Configure leave and absence types</span></span>

<span data-ttu-id="4797d-104">I tipi di congedo in Dynamics 365 Human Resources definiscono i tipi di assenze che i dipendenti possono segnalare.</span><span class="sxs-lookup"><span data-stu-id="4797d-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="4797d-105">È possibile adattare i tipi di congedo in base alle esigenze della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4797d-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="4797d-106">Di seguito sono riportati alcuni esempi di tipi di congedo:</span><span class="sxs-lookup"><span data-stu-id="4797d-106">Examples of leave types include:</span></span>

- <span data-ttu-id="4797d-107">Permessi retribuiti</span><span class="sxs-lookup"><span data-stu-id="4797d-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="4797d-108">Congedo non retribuito</span><span class="sxs-lookup"><span data-stu-id="4797d-108">Unpaid leave</span></span>
- <span data-ttu-id="4797d-109">Ferie pagate</span><span class="sxs-lookup"><span data-stu-id="4797d-109">Paid vacation</span></span>
- <span data-ttu-id="4797d-110">Congedo per malattia</span><span class="sxs-lookup"><span data-stu-id="4797d-110">Sick leave</span></span>
- <span data-ttu-id="4797d-111">Congedo per motivi medici</span><span class="sxs-lookup"><span data-stu-id="4797d-111">Medical leave</span></span>
- <span data-ttu-id="4797d-112">Congedo per motivi familiari</span><span class="sxs-lookup"><span data-stu-id="4797d-112">Family leave</span></span>
- <span data-ttu-id="4797d-113">Disabilità a breve termine</span><span class="sxs-lookup"><span data-stu-id="4797d-113">Short-term disability</span></span>
- <span data-ttu-id="4797d-114">Congedo per lutto</span><span class="sxs-lookup"><span data-stu-id="4797d-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="4797d-115">Aggiungere un tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="4797d-115">Add a leave type</span></span>

1. <span data-ttu-id="4797d-116">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="4797d-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="4797d-117">Sotto **Impostazione**, selezionare **Tipi di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="4797d-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="4797d-118">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4797d-118">Select **New**.</span></span>

4. <span data-ttu-id="4797d-119">Immettere un nome per il tipo di congedo sotto **Tipo**, selezionare un flusso di lavoro in **ID flusso di lavoro** e immettere una descrizione sotto **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="4797d-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="4797d-120">In **Generale**, selezionare **Nessuno**, **Programmato** o **Non programmato** nell'elenco a discesa **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="4797d-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="4797d-121">Seleziona un codice di reddito nell'elenco a discesa**Codice di reddito**.</span><span class="sxs-lookup"><span data-stu-id="4797d-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="4797d-122">Sotto **Codice motivo obbligatorio**, scegliere se richiedere un codice motivo o meno.</span><span class="sxs-lookup"><span data-stu-id="4797d-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="4797d-123">Se si desidera richiedere dei codici motivo, potrebbe essere necessario aggiungerli.</span><span class="sxs-lookup"><span data-stu-id="4797d-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="4797d-124">Sotto **Codici motivo**, selezionare **Aggiungi**, selezionare un codice motivo, quindi selezionare la casella di controllo **Abilitato** accanto allo stesso.</span><span class="sxs-lookup"><span data-stu-id="4797d-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="4797d-125">Sotto **Limitare l'accesso a ruoli selezionati**, scegliere se limitare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4797d-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="4797d-126">Quindi selezionare i ruoli di sicurezza sotto **Ruoli di sicurezza per questo tipo di congedo**.</span><span class="sxs-lookup"><span data-stu-id="4797d-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="4797d-127">I ruoli di sicurezza sono definiti nel flusso di lavoro selezionato sotto **ID flusso di lavoro** precedentemente in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4797d-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="4797d-128">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4797d-128">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="4797d-129">Configurare le regole del tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="4797d-129">Configure leave type rules</span></span>

1. <span data-ttu-id="4797d-130">Impostare opzioni di arrotondamento per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="4797d-130">Set rounding options for the leave type.</span></span> <span data-ttu-id="4797d-131">Le opzioni includono **Nessuno**, **Su**, **Giù** e **Al più vicino**.</span><span class="sxs-lookup"><span data-stu-id="4797d-131">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="4797d-132">È inoltre possibile impostare la precisione di arrotondamento per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="4797d-132">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="4797d-133">Impostare **Correzione giorni festivi** per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="4797d-133">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="4797d-134">Quando si seleziona questa opzione, Human Resources utilizza il numero di giorni festivi che cadono in un giorno lavorativo per determinare come accumulare permessi per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="4797d-134">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="4797d-135">Ad esempio, se il giorno di Natale cade di lunedì, Human Resources sottrarrà un giorno dal tipo di congedo durante l'elaborazione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="4797d-135">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="4797d-136">i giorni festivi sono impostati nel calendario orario lavorativo.</span><span class="sxs-lookup"><span data-stu-id="4797d-136">You set holidays in the working time calendar.</span></span> <span data-ttu-id="4797d-137">Per ulteriori informazioni, vedere [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md).</span><span class="sxs-lookup"><span data-stu-id="4797d-137">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
## <a name="configure-preview-features"></a><span data-ttu-id="4797d-138">Configurare funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="4797d-138">Configure preview features</span></span>

<span data-ttu-id="4797d-139">Se le funzionalità di anteprima per Congedo e assenza sono state abilitate, è necessario configurare le impostazioni anche per tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4797d-139">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="4797d-140">Scegliere il tipo di congedo per i saldi del riporto in cui vengono trasferiti.</span><span class="sxs-lookup"><span data-stu-id="4797d-140">Choose the leave type for carry forward balances to be transferred to.</span></span> <span data-ttu-id="4797d-141">È anche possibile creare un nuovo tipo di congedo per il riporto.</span><span class="sxs-lookup"><span data-stu-id="4797d-141">You can also create a new leave type for carry forward.</span></span> 

## <a name="see-also"></a><span data-ttu-id="4797d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4797d-142">See also</span></span>

- [<span data-ttu-id="4797d-143">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="4797d-143">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="4797d-144">Creare un piano di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="4797d-144">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="4797d-145">Creare un calendario orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="4797d-145">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
