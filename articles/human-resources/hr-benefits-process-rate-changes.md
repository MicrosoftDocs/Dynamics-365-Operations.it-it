---
title: Elaborare modifiche ai tassi
description: Elaborare modifiche ai tassi di benefit in Microsoft Dynamics 365 Human Resources quando un piano di benefit nuovo o esistente presenta una modifica nelle impostazioni della regola di idoneità.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5cfecc4da90b4fb39bdece38095f3b25023e4cae
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055702"
---
# <a name="process-rate-changes"></a><span data-ttu-id="039ea-103">Elaborare modifiche ai tassi</span><span class="sxs-lookup"><span data-stu-id="039ea-103">Process rate changes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="039ea-104">Elaborare modifiche ai tassi di benefit in Microsoft Dynamics 365 Human Resources quando un piano di benefit nuovo o esistente presenta una modifica nelle impostazioni della regola di idoneità.</span><span class="sxs-lookup"><span data-stu-id="039ea-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="039ea-105">Se una nuova regola di idoneità viene creata e assegnata al piano, al sistema viene richiesto di eseguire di nuovo l'idoneità dei lavoratori per verificare se questi ora hanno diritto al piano in base alle nuove opzioni di idoneità.</span><span class="sxs-lookup"><span data-stu-id="039ea-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to rerun worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="039ea-106">Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione aggiornamento modifica tasso**.</span><span class="sxs-lookup"><span data-stu-id="039ea-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="039ea-107">Nella finestra di dialogo **Esegui elaborazione aggiornamento tasso benefit**, specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="039ea-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="039ea-108">Campo</span><span class="sxs-lookup"><span data-stu-id="039ea-108">Field</span></span> | <span data-ttu-id="039ea-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="039ea-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="039ea-110">**Periodo di iscrizione**</span><span class="sxs-lookup"><span data-stu-id="039ea-110">**Enrollment period**</span></span> | <span data-ttu-id="039ea-111">Il periodo di iscrizione per il quale elaborare le modifiche al tasso.</span><span class="sxs-lookup"><span data-stu-id="039ea-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="039ea-112">Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="039ea-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="039ea-113">Immettere le informazioni per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="039ea-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="039ea-114">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="039ea-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="039ea-115">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="039ea-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="039ea-116">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="039ea-116">Select **OK**.</span></span> <span data-ttu-id="039ea-117">l'elaborazione verrà eseguita con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="039ea-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="039ea-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="039ea-118">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]