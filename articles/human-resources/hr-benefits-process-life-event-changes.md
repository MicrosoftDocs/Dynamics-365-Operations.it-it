---
title: Elaborare le modifiche a eventi reali
description: Elaborare modifiche a eventi reali in Microsoft Dynamics 365 Human Resources per le modifiche a eventi reali.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39d1e94347809a1756fc4f66e5edc345c70eaf39
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419148"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="e76a2-103">Elaborare le modifiche a eventi reali</span><span class="sxs-lookup"><span data-stu-id="e76a2-103">Process life event changes</span></span>

<span data-ttu-id="e76a2-104">Elaborare modifiche a eventi reali in Microsoft Dynamics 365 Human Resources per due modifiche a eventi reali:</span><span class="sxs-lookup"><span data-stu-id="e76a2-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="e76a2-105">Modifiche di compleanno</span><span class="sxs-lookup"><span data-stu-id="e76a2-105">Birthday changes</span></span>
- <span data-ttu-id="e76a2-106">Modifiche alle scadenza della sostituzione delle regola di idoneità</span><span class="sxs-lookup"><span data-stu-id="e76a2-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="e76a2-107">Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione modifica idoneità da eventi reali**.</span><span class="sxs-lookup"><span data-stu-id="e76a2-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="e76a2-108">Nella finestra di dialogo **Esegui elaborazione modifica eventi reali**, specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e76a2-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="e76a2-109">Campo</span><span class="sxs-lookup"><span data-stu-id="e76a2-109">Field</span></span> | <span data-ttu-id="e76a2-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e76a2-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e76a2-111">Periodo di iscrizione</span><span class="sxs-lookup"><span data-stu-id="e76a2-111">Enrollment period</span></span> | <span data-ttu-id="e76a2-112">Il periodo di iscrizione per il quale elaborare le modifiche a eventi reali.</span><span class="sxs-lookup"><span data-stu-id="e76a2-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="e76a2-113">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="e76a2-113">Legal entity</span></span> | <span data-ttu-id="e76a2-114">La persona giuridica per la quale elaborare le modifiche a eventi reali.</span><span class="sxs-lookup"><span data-stu-id="e76a2-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="e76a2-115">Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="e76a2-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="e76a2-116">Immettere le informazioni per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e76a2-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="e76a2-117">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e76a2-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="e76a2-118">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e76a2-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="e76a2-119">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e76a2-119">Select **OK**.</span></span> <span data-ttu-id="e76a2-120">l'elaborazione verrà eseguita con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="e76a2-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="e76a2-121">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e76a2-121">Select **OK**.</span></span>
