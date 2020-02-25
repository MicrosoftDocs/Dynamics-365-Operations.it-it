---
title: Configurare le detrazioni
description: ''
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
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009564"
---
# <a name="configure-deductions"></a><span data-ttu-id="2c012-102">Configurare le detrazioni</span><span class="sxs-lookup"><span data-stu-id="2c012-102">Configure deductions</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="2c012-103">L'utilizzo delle detrazioni in Microsoft Dynamics 365 Human Resources consente di determinare quanto eventualmente detrarre dalla busta paga di un dipendente per ogni benefit.</span><span class="sxs-lookup"><span data-stu-id="2c012-103">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="2c012-104">Le detrazioni hanno una data di validità, pertanto è possibile tenere un record cronologico delle informazioni sulla detrazione.</span><span class="sxs-lookup"><span data-stu-id="2c012-104">Deductions are date effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="2c012-105">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Detrazioni**.</span><span class="sxs-lookup"><span data-stu-id="2c012-105">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="2c012-106">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2c012-106">Select **New**.</span></span>

3. <span data-ttu-id="2c012-107">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="2c012-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="2c012-108">Campo</span><span class="sxs-lookup"><span data-stu-id="2c012-108">Field</span></span> | <span data-ttu-id="2c012-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c012-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2c012-110">Detrazione</span><span class="sxs-lookup"><span data-stu-id="2c012-110">Deduction</span></span> | <span data-ttu-id="2c012-111">Un ID univoco utilizzato per identificare la detrazione per benefit.</span><span class="sxs-lookup"><span data-stu-id="2c012-111">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="2c012-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c012-112">Description</span></span> | <span data-ttu-id="2c012-113">Una descrizione della detrazione.</span><span class="sxs-lookup"><span data-stu-id="2c012-113">A description for the deduction.</span></span> |
   | <span data-ttu-id="2c012-114">Valido</span><span class="sxs-lookup"><span data-stu-id="2c012-114">Effective</span></span> | <span data-ttu-id="2c012-115">La data di inizio.</span><span class="sxs-lookup"><span data-stu-id="2c012-115">The start date.</span></span> <span data-ttu-id="2c012-116">Il valore predefinito è la data di sistema corrente.</span><span class="sxs-lookup"><span data-stu-id="2c012-116">The default value is the current system date.</span></span> |
   | <span data-ttu-id="2c012-117">Scadenza</span><span class="sxs-lookup"><span data-stu-id="2c012-117">Expiration</span></span> | <span data-ttu-id="2c012-118">La data di fine.</span><span class="sxs-lookup"><span data-stu-id="2c012-118">The end date.</span></span> <span data-ttu-id="2c012-119">31/12/2154 (che significa mai) è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2c012-119">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="2c012-120">Intestazione</span><span class="sxs-lookup"><span data-stu-id="2c012-120">Heading</span></span> | <span data-ttu-id="2c012-121">Il codice di intestazione del sistema di gestione delle retribuzioni che la detrazione utilizzerà per la parte della detrazione del dipendente durante l'elaborazione dei benefit per la retribuzione.</span><span class="sxs-lookup"><span data-stu-id="2c012-121">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="2c012-122">Questo codice viene utilizzato quando si utilizza un fornitore di retribuzioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2c012-122">This is used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="2c012-123">Riferimento detrazioni sulle retribuzioni del dipendente</span><span class="sxs-lookup"><span data-stu-id="2c012-123">Employee payroll deduction reference</span></span> | <span data-ttu-id="2c012-124">Codice di detrazione del sistema di gestione delle retribuzioni utilizzato dalla detrazione per la parte relativa al dipendente della detrazione durante l'elaborazione dei benefit per le retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="2c012-124">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="2c012-125">Intestazione importo</span><span class="sxs-lookup"><span data-stu-id="2c012-125">Amount heading</span></span> | <span data-ttu-id="2c012-126">Il codice di intestazione del sistema di gestione delle retribuzioni che questo importo di detrazioni utilizzerà per la parte della detrazione del dipendente durante l'elaborazione dei benefit per la retribuzione.</span><span class="sxs-lookup"><span data-stu-id="2c012-126">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="2c012-127">Questo codice viene normalmente utilizzato quando si utilizza un fornitore di retribuzioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2c012-127">This is normally used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="2c012-128">Eliminazione possibile</span><span class="sxs-lookup"><span data-stu-id="2c012-128">Can delete</span></span> | <span data-ttu-id="2c012-129">Specifica se un valore esportato da Dynamics 365 for Finance and Operations può causare l'eliminazione del valore nel sistema di gestione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="2c012-129">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="2c012-130">Colonne associate</span><span class="sxs-lookup"><span data-stu-id="2c012-130">Paired columns</span></span> | <span data-ttu-id="2c012-131">Specifica se esportare l'intestazione e l'importo delle detrazioni in colonne adiacenti accoppiate nel sistema di gestione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="2c012-131">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="2c012-132">Data di validità modifica</span><span class="sxs-lookup"><span data-stu-id="2c012-132">Change effective date</span></span> | <span data-ttu-id="2c012-133">La data in cui la modifica alle detrazioni per benefit diventa effettiva.</span><span class="sxs-lookup"><span data-stu-id="2c012-133">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="2c012-134">In questa data il sistema modificherà automaticamente la detrazione per benefit e aggiornerà tutti i piani di benefit associati a tale detrazione, purché si esegua l'elaborazione dell'aggiornamento delle modifiche alle detrazioni.</span><span class="sxs-lookup"><span data-stu-id="2c012-134">On this date the system will automatically change the benefit deduction and update all benefit plans associated with this deduction, as long as you run Deduction change update processing.</span></span> |
   | <span data-ttu-id="2c012-135">Modifica detrazione completata</span><span class="sxs-lookup"><span data-stu-id="2c012-135">Deduction change completed</span></span> | <span data-ttu-id="2c012-136">La casella di controllo Modifica detrazione completata verrà selezionata automaticamente una volta completate le modifiche alla detrazioni per benefit mediante l'elaborazione dell'aggiornamento delle modifiche alle detrazioni.</span><span class="sxs-lookup"><span data-stu-id="2c012-136">The Deduction change completed check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="2c012-137">Per tenere traccia e gestire le modifiche all'impostazione del tasso di benefit, selezionare **Azioni**, quindi selezionare **Gestisci versioni**.</span><span class="sxs-lookup"><span data-stu-id="2c012-137">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="2c012-138">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2c012-138">Select **Save**.</span></span> 
