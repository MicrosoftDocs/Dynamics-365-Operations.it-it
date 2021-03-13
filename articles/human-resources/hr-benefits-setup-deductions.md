---
title: Configurare le detrazioni
description: L'utilizzo delle detrazioni in Microsoft Dynamics 365 Human Resources consente di determinare quanto eventualmente detrarre dalla busta paga di un dipendente per ogni benefit.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
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
ms.openlocfilehash: c84e44e784e18c82098d63909f198049ae5f995c
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113111"
---
# <a name="configure-deductions"></a><span data-ttu-id="f2a55-103">Configurare le detrazioni</span><span class="sxs-lookup"><span data-stu-id="f2a55-103">Configure deductions</span></span>

<span data-ttu-id="f2a55-104">L'utilizzo delle detrazioni in Microsoft Dynamics 365 Human Resources consente di determinare quanto eventualmente detrarre dalla busta paga di un dipendente per ogni benefit.</span><span class="sxs-lookup"><span data-stu-id="f2a55-104">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="f2a55-105">Le detrazioni hanno una data di validità, pertanto è possibile tenere un record cronologico delle informazioni sulla detrazione.</span><span class="sxs-lookup"><span data-stu-id="f2a55-105">Deductions are date-effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="f2a55-106">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Detrazioni**.</span><span class="sxs-lookup"><span data-stu-id="f2a55-106">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="f2a55-107">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2a55-107">Select **New**.</span></span>

3. <span data-ttu-id="f2a55-108">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="f2a55-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="f2a55-109">Campo</span><span class="sxs-lookup"><span data-stu-id="f2a55-109">Field</span></span> | <span data-ttu-id="f2a55-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2a55-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f2a55-111">**Detrazione**</span><span class="sxs-lookup"><span data-stu-id="f2a55-111">**Deduction**</span></span> | <span data-ttu-id="f2a55-112">Un ID univoco utilizzato per identificare la detrazione per benefit.</span><span class="sxs-lookup"><span data-stu-id="f2a55-112">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="f2a55-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f2a55-113">**Description**</span></span> | <span data-ttu-id="f2a55-114">Una descrizione della detrazione.</span><span class="sxs-lookup"><span data-stu-id="f2a55-114">A description for the deduction.</span></span> |
   | <span data-ttu-id="f2a55-115">**Valido**</span><span class="sxs-lookup"><span data-stu-id="f2a55-115">**Effective**</span></span> | <span data-ttu-id="f2a55-116">La data di inizio.</span><span class="sxs-lookup"><span data-stu-id="f2a55-116">The start date.</span></span> <span data-ttu-id="f2a55-117">Il valore predefinito è la data di sistema corrente.</span><span class="sxs-lookup"><span data-stu-id="f2a55-117">The default value is the current system date.</span></span> |
   | <span data-ttu-id="f2a55-118">**Scadenza**</span><span class="sxs-lookup"><span data-stu-id="f2a55-118">**Expiration**</span></span> | <span data-ttu-id="f2a55-119">La data di fine.</span><span class="sxs-lookup"><span data-stu-id="f2a55-119">The end date.</span></span> <span data-ttu-id="f2a55-120">31/12/2154 (che significa mai) è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f2a55-120">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="f2a55-121">**Intestazione**</span><span class="sxs-lookup"><span data-stu-id="f2a55-121">**Heading**</span></span> | <span data-ttu-id="f2a55-122">Il codice di intestazione del sistema di gestione delle retribuzioni che la detrazione utilizzerà per la parte della detrazione del dipendente durante l'elaborazione dei benefit per la retribuzione.</span><span class="sxs-lookup"><span data-stu-id="f2a55-122">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="f2a55-123">Questo codice viene utilizzato quando si utilizza un fornitore di retribuzioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f2a55-123">This is used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="f2a55-124">**Riferimento detrazioni sulle retribuzioni del dipendente**</span><span class="sxs-lookup"><span data-stu-id="f2a55-124">**Employee payroll deduction reference**</span></span> | <span data-ttu-id="f2a55-125">Codice di detrazione del sistema di gestione delle retribuzioni utilizzato dalla detrazione per la parte relativa al dipendente della detrazione durante l'elaborazione dei benefit per le retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="f2a55-125">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="f2a55-126">**Intestazione importo**</span><span class="sxs-lookup"><span data-stu-id="f2a55-126">**Amount heading**</span></span> | <span data-ttu-id="f2a55-127">Il codice di intestazione del sistema di gestione delle retribuzioni che questo importo di detrazioni utilizzerà per la parte della detrazione del dipendente durante l'elaborazione dei benefit per la retribuzione.</span><span class="sxs-lookup"><span data-stu-id="f2a55-127">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="f2a55-128">Questo codice viene normalmente utilizzato quando si utilizza un fornitore di retribuzioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f2a55-128">This is normally used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="f2a55-129">**Eliminazione possibile**</span><span class="sxs-lookup"><span data-stu-id="f2a55-129">**Can delete**</span></span> | <span data-ttu-id="f2a55-130">Specifica se un valore esportato da Dynamics 365 for Finance and Operations può causare l'eliminazione del valore nel sistema di gestione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="f2a55-130">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="f2a55-131">**Colonne associate**</span><span class="sxs-lookup"><span data-stu-id="f2a55-131">**Paired columns**</span></span> | <span data-ttu-id="f2a55-132">Specifica se esportare l'intestazione e l'importo delle detrazioni in colonne adiacenti accoppiate nel sistema di gestione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="f2a55-132">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="f2a55-133">**Data di validità modifica**</span><span class="sxs-lookup"><span data-stu-id="f2a55-133">**Change effective date**</span></span> | <span data-ttu-id="f2a55-134">La data in cui la modifica alle detrazioni per benefit diventa effettiva.</span><span class="sxs-lookup"><span data-stu-id="f2a55-134">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="f2a55-135">In questa data il sistema modifica automaticamente la detrazione per benefit e aggiorna tutti i piani di benefit associati a tale detrazione, purché si esegua l'elaborazione dell'**aggiornamento delle modifiche alle detrazioni**.</span><span class="sxs-lookup"><span data-stu-id="f2a55-135">On this date, the system automatically changes the benefit deduction and updates all benefit plans associated with this deduction, as long as you run **Deduction change update** processing.</span></span> |
   | <span data-ttu-id="f2a55-136">**Modifica detrazione completata**</span><span class="sxs-lookup"><span data-stu-id="f2a55-136">**Deduction change completed**</span></span> | <span data-ttu-id="f2a55-137">La casella di controllo **Modifica detrazione completata** verrà selezionata automaticamente una volta completate le modifiche alla detrazioni per benefit mediante l'elaborazione dell'aggiornamento delle modifiche alle detrazioni.</span><span class="sxs-lookup"><span data-stu-id="f2a55-137">The **Deduction change completed** check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="f2a55-138">Per tenere traccia e gestire le modifiche all'impostazione del tasso di benefit, selezionare **Azioni**, quindi selezionare **Gestisci versioni**.</span><span class="sxs-lookup"><span data-stu-id="f2a55-138">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="f2a55-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2a55-139">Select **Save**.</span></span> 
