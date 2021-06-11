---
title: Imposta i codici causale
description: Dynamics 365 Human Resources utilizza codici motivo per spiegare perché i benefit di un dipendente stanno cambiando.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6fc641233a1bd217de5b9eb6e06560b989f91c7b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056350"
---
# <a name="set-up-reason-codes"></a><span data-ttu-id="45a5e-103">Imposta i codici causale</span><span class="sxs-lookup"><span data-stu-id="45a5e-103">Set up reason codes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="45a5e-104">Dynamics 365 Human Resources utilizza codici motivo per spiegare perché i benefit di un dipendente stanno cambiando.</span><span class="sxs-lookup"><span data-stu-id="45a5e-104">Dynamics 365 Human Resources uses reason codes to explain why an employee’s benefits are changing.</span></span>

> [!NOTE]
> <span data-ttu-id="45a5e-105">A partire da gennaio 2021, i codici motivo verranno migrati nell'area di lavoro **Gestione personale** invece dell'area di lavoro **Gestione benefit**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-105">As of January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="45a5e-106">Per ulteriori informazioni, vedi [Migrare manualmente i codici motivo alla gestione del personale](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span><span class="sxs-lookup"><span data-stu-id="45a5e-106">For more information, see [Manually migrate reason codes to Personnel management](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span></span>

## <a name="create-reason-codes"></a><span data-ttu-id="45a5e-107">Creare codici motivo</span><span class="sxs-lookup"><span data-stu-id="45a5e-107">Create reason codes</span></span>

1. <span data-ttu-id="45a5e-108">Nell'area di lavoro **Gestione personale** (o nell'area di lavoro **Gestione benefit** se i codici motivo non sono ancora stati migrati), seleziona **Collegamenti** e quindi seleziona **Codici motivo**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-108">In the **Personnel management** workspace (or **Benefits management** workspace if your reason codes haven't yet migrated), select **Links**, and then select **Reason codes**.</span></span>

2. <span data-ttu-id="45a5e-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-109">Select **New**.</span></span>

3. <span data-ttu-id="45a5e-110">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="45a5e-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="45a5e-111">Campo</span><span class="sxs-lookup"><span data-stu-id="45a5e-111">Field</span></span> | <span data-ttu-id="45a5e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45a5e-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="45a5e-113">**Codice motivo**</span><span class="sxs-lookup"><span data-stu-id="45a5e-113">**Reason code**</span></span> | <span data-ttu-id="45a5e-114">Un nome univoco per identificare il motivo per cui un dipendente cambierebbe l'iscrizione a un piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="45a5e-114">A unique name to identify the reason an employee would change a benefit plan enrollment.</span></span> |
   | <span data-ttu-id="45a5e-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="45a5e-115">**Description**</span></span> | <span data-ttu-id="45a5e-116">Descrizione del codice motivo.</span><span class="sxs-lookup"><span data-stu-id="45a5e-116">A description of the reason code.</span></span> |

4. <span data-ttu-id="45a5e-117">In **Scenario applicabile**, imposta **Gestione benefit** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-117">Under **Applicable scenarios**, set **Benefits management** to **Yes**.</span></span> <span data-ttu-id="45a5e-118">Non applicabile se i tuoi codici motivo non sono ancora migrati all'area di lavoro **Gestione personale**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-118">(Not applicable if your reason codes haven't yet migrated to the **Personnel management** workspace.)</span></span>

5. <span data-ttu-id="45a5e-119">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-119">Select **Save**.</span></span>

## <a name="manually-migrate-reason-codes-to-personnel-management"></a><span data-ttu-id="45a5e-120">Migrare manualmente i codici motivo alla gestione del personale</span><span class="sxs-lookup"><span data-stu-id="45a5e-120">Manually migrate reason codes to Personnel management</span></span>

<span data-ttu-id="45a5e-121">A partire da gennaio 2021, i codici motivo verranno migrati nell'area di lavoro **Gestione personale** invece che nell'area di lavoro **Gestione benefit**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-121">In January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="45a5e-122">La maggior parte dei dati del codice motivo verrà migrata automaticamente nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="45a5e-122">Most reason code data will automatically migrate in your environment.</span></span> <span data-ttu-id="45a5e-123">Alcuni dati del codice motivo potrebbero non essere migrati.</span><span class="sxs-lookup"><span data-stu-id="45a5e-123">Some reason code data might not migrate.</span></span> <span data-ttu-id="45a5e-124">Ad esempio, i codici motivo ora hanno un massimo di 15 caratteri, quindi qualsiasi codice motivo più lungo di 15 caratteri non verrà migrato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="45a5e-124">For example, reason codes now have a 15-character maximum, so any reason codes longer than 15 characters won't migrate automatically.</span></span>

<span data-ttu-id="45a5e-125">Vedrai un banner nella pagina **Collegamenti** dell'area di lavoro **Gestione benefit** che ti informa sulla migrazione e se i codici motivo non sono stati migrati.</span><span class="sxs-lookup"><span data-stu-id="45a5e-125">You'll see a banner on the **Links** page of the **Benefits management** workspace informing you about the migration and whether any reason codes didn't migrate.</span></span>

1. <span data-ttu-id="45a5e-126">Seleziona **Codici motivo** per i dettagli sullo stato della migrazione.</span><span class="sxs-lookup"><span data-stu-id="45a5e-126">Select **Reason codes** for details about migration status.</span></span>

   <span data-ttu-id="45a5e-127">[![Codici causale](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span><span class="sxs-lookup"><span data-stu-id="45a5e-127">[![Reason codes](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span></span>

2. <span data-ttu-id="45a5e-128">Seleziona un codice motivo di cui la migrazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="45a5e-128">Select a reason code that failed to migrate.</span></span>

   <span data-ttu-id="45a5e-129">[![Stato della migrazione del codice motivo](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span><span class="sxs-lookup"><span data-stu-id="45a5e-129">[![Reason code migration status](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span></span>

3. <span data-ttu-id="45a5e-130">Seleziona **Migra codice motivo**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-130">Select **Migrate reason code**.</span></span>

   <span data-ttu-id="45a5e-131">[![Esegui migrazione del codice motivo](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span><span class="sxs-lookup"><span data-stu-id="45a5e-131">[![Migrate reason code](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span></span>

4. <span data-ttu-id="45a5e-132">Nel riquadro **Migrazione del codice motivo benefit**, sono disponibili due opzioni per la mappatura a un codice motivo della gestione del personale:</span><span class="sxs-lookup"><span data-stu-id="45a5e-132">In the **Benefit reason code migration** pane, you have two options for mapping to a Personnel management reason code:</span></span>

   - <span data-ttu-id="45a5e-133">Per utilizzare un codice motivo esistente in Gestione personale, scegline uno dal menu a discesa **Utilizza codice motivo esistente**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-133">To use an existing reason code in Personnel management, choose one from the **Use existing reason code** dropdown.</span></span>
     > [!NOTE]
     > <span data-ttu-id="45a5e-134">Puoi utilizzare un codice motivo esistente in Gestione personale solo se un altro codice motivo della gestione dei vantaggi non è già stato migrato su di esso.</span><span class="sxs-lookup"><span data-stu-id="45a5e-134">You can only use an existing reason code in Personnel management if another Benefits management reason code hasn't already migrated to it.</span></span>
   - <span data-ttu-id="45a5e-135">Per creare un nuovo codice motivo in Gestione personale, immettine uno nuovo in **Nuovo codice motivo**, quindi inserisci una descrizione in **Nuova descrizione**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-135">To create a new reason code in Personnel management, enter a new one in **New reason code**, and then enter a description in **New description**.</span></span>

   <span data-ttu-id="45a5e-136">[![Associare a un codice motivo di Gestione personale](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span><span class="sxs-lookup"><span data-stu-id="45a5e-136">[![Map to a Personnel management reason code](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span></span>

<span data-ttu-id="45a5e-137">Dopo la migrazione dei codici motivo a Gestione personale, l'opzione per utilizzarli in Gestione benefit viene automaticamente impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="45a5e-137">After reason codes migrate to Personnel management, the option for using them in Benefits management is automatically set to **Yes**.</span></span>

<span data-ttu-id="45a5e-138">[![Usa codice motivo in Gestione benefit](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span><span class="sxs-lookup"><span data-stu-id="45a5e-138">[![Use reason code in Benefits management](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]