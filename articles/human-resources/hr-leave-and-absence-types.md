---
title: Configurare tipi di congedo e assenza
description: Impostare i tipi di congedo che i dipendenti possono prendere in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1802938f54a1d78e6ea60572a76177a037192ae0
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428595"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="e9912-103">Configurare tipi di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="e9912-103">Configure leave and absence types</span></span>

<span data-ttu-id="e9912-104">I tipi di congedo in Dynamics 365 Human Resources definiscono i tipi di assenze che i dipendenti possono segnalare.</span><span class="sxs-lookup"><span data-stu-id="e9912-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="e9912-105">È possibile adattare i tipi di congedo in base alle esigenze della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9912-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="e9912-106">Di seguito sono riportati alcuni esempi di tipi di congedo:</span><span class="sxs-lookup"><span data-stu-id="e9912-106">Examples of leave types include:</span></span>

- <span data-ttu-id="e9912-107">Permessi retribuiti</span><span class="sxs-lookup"><span data-stu-id="e9912-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="e9912-108">Congedo non retribuito</span><span class="sxs-lookup"><span data-stu-id="e9912-108">Unpaid leave</span></span>
- <span data-ttu-id="e9912-109">Ferie pagate</span><span class="sxs-lookup"><span data-stu-id="e9912-109">Paid vacation</span></span>
- <span data-ttu-id="e9912-110">Congedo per malattia</span><span class="sxs-lookup"><span data-stu-id="e9912-110">Sick leave</span></span>
- <span data-ttu-id="e9912-111">Congedo per motivi medici</span><span class="sxs-lookup"><span data-stu-id="e9912-111">Medical leave</span></span>
- <span data-ttu-id="e9912-112">Congedo per motivi familiari</span><span class="sxs-lookup"><span data-stu-id="e9912-112">Family leave</span></span>
- <span data-ttu-id="e9912-113">Disabilità a breve termine</span><span class="sxs-lookup"><span data-stu-id="e9912-113">Short-term disability</span></span>
- <span data-ttu-id="e9912-114">Congedo per lutto</span><span class="sxs-lookup"><span data-stu-id="e9912-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="e9912-115">Aggiungere un tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="e9912-115">Add a leave type</span></span>

1. <span data-ttu-id="e9912-116">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="e9912-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="e9912-117">Sotto **Impostazione**, selezionare **Tipi di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="e9912-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="e9912-118">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e9912-118">Select **New**.</span></span>

4. <span data-ttu-id="e9912-119">Immettere un nome per il tipo di congedo sotto **Tipo**, selezionare un flusso di lavoro in **ID flusso di lavoro** e immettere una descrizione sotto **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="e9912-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="e9912-120">In **Generale**, selezionare **Nessuno**, **Programmato** o **Non programmato** nell'elenco a discesa **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="e9912-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="e9912-121">Seleziona un codice di reddito nell'elenco a discesa**Codice di reddito**.</span><span class="sxs-lookup"><span data-stu-id="e9912-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="e9912-122">Sotto **Codice motivo obbligatorio**, scegliere se richiedere un codice motivo o meno.</span><span class="sxs-lookup"><span data-stu-id="e9912-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="e9912-123">Se si desidera richiedere dei codici motivo, potrebbe essere necessario aggiungerli.</span><span class="sxs-lookup"><span data-stu-id="e9912-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="e9912-124">Sotto **Codici motivo**, selezionare **Aggiungi**, selezionare un codice motivo, quindi selezionare la casella di controllo **Abilitato** accanto allo stesso.</span><span class="sxs-lookup"><span data-stu-id="e9912-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="e9912-125">Sotto **Limitare l'accesso a ruoli selezionati**, scegliere se limitare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e9912-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="e9912-126">Quindi selezionare i ruoli di sicurezza sotto **Ruoli di sicurezza per questo tipo di congedo**.</span><span class="sxs-lookup"><span data-stu-id="e9912-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="e9912-127">I ruoli di sicurezza sono definiti nel flusso di lavoro selezionato sotto **ID flusso di lavoro** precedentemente in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="e9912-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="e9912-128">Sotto **Relazioni di sospensione**, scegli se questo tipo di congedo deve sospendere questo tipo di congedo o deve essere sospeso da un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="e9912-128">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="e9912-129">Quando una richiesta di congedo viene inviata per il tipo di congedo che provoca la sospensione, verrà automaticamente creata una sospensione del congedo per il tipo di congedo sospeso.</span><span class="sxs-lookup"><span data-stu-id="e9912-129">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="e9912-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e9912-130">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="e9912-131">Configurare le regole del tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="e9912-131">Configure leave type rules</span></span>

1. <span data-ttu-id="e9912-132">Impostare opzioni di arrotondamento per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="e9912-132">Set rounding options for the leave type.</span></span> <span data-ttu-id="e9912-133">Le opzioni includono **Nessuno**, **Su**, **Giù** e **Al più vicino**.</span><span class="sxs-lookup"><span data-stu-id="e9912-133">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="e9912-134">È inoltre possibile impostare la precisione di arrotondamento per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="e9912-134">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="e9912-135">Impostare **Correzione giorni festivi** per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="e9912-135">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="e9912-136">Quando si seleziona questa opzione, Human Resources utilizza il numero di giorni festivi che cadono in un giorno lavorativo per determinare come accumulare permessi per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="e9912-136">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="e9912-137">Ad esempio, se il giorno di Natale cade di lunedì, Human Resources sottrarrà un giorno dal tipo di congedo durante l'elaborazione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="e9912-137">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="e9912-138">i giorni festivi sono impostati nel calendario orario lavorativo.</span><span class="sxs-lookup"><span data-stu-id="e9912-138">You set holidays in the working time calendar.</span></span> <span data-ttu-id="e9912-139">Per ulteriori informazioni, vedere [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md).</span><span class="sxs-lookup"><span data-stu-id="e9912-139">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="e9912-140">Impostare **Tipo di congedo riportabile** per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="e9912-140">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="e9912-141">Quando si seleziona questa opzione, tutti i saldi riportabili verranno trasferiti al tipo di congedo specificato.</span><span class="sxs-lookup"><span data-stu-id="e9912-141">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="e9912-142">Anche il tipo di congedo riportabile deve essere incluso nel piano di congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="e9912-142">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="e9912-143">Definire **Regole di scadenza** per il tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="e9912-143">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="e9912-144">Quando si configura questa opzione, è possibile scegliere l'unità di giorni o mesi e impostare la durata per la scadenza.</span><span class="sxs-lookup"><span data-stu-id="e9912-144">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="e9912-145">È inoltre possibile impostare la data di validità della regola di scadenza.</span><span class="sxs-lookup"><span data-stu-id="e9912-145">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="e9912-146">Eventuali saldi di congedi esistenti al momento della scadenza verranno sottratti dal tipo di congedo e si rifletteranno nel saldo di congedi.</span><span class="sxs-lookup"><span data-stu-id="e9912-146">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
 
## <a name="see-also"></a><span data-ttu-id="e9912-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9912-147">See also</span></span>

- [<span data-ttu-id="e9912-148">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="e9912-148">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="e9912-149">Creare un piano di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="e9912-149">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="e9912-150">Creare un calendario orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="e9912-150">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="e9912-151">Congedo sospeso</span><span class="sxs-lookup"><span data-stu-id="e9912-151">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)

