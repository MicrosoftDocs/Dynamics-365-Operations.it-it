---
title: Novità o modifiche in Dynamics 365 Talent (31 gennaio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690054"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a><span data-ttu-id="01cd1-103">Novità o modifiche in Dynamics 365 Talent (31 gennaio 2019)</span><span class="sxs-lookup"><span data-stu-id="01cd1-103">What's new or changed in Dynamics 365 Talent (January 31, 2019)</span></span>

<span data-ttu-id="01cd1-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="01cd1-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

<span data-ttu-id="01cd1-105">**Build 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="01cd1-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="01cd1-106">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="01cd1-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="01cd1-107">Il permesso richiesto nella scheda delle persone in congedo non considera le date del piano di congedo</span><span class="sxs-lookup"><span data-stu-id="01cd1-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="01cd1-108">Per i piani di congedo non eseguiti in un anno di calendario, la scheda **Richiesto** ora visualizza il permesso richiesto nell'anno di congedo definito nel piano.</span><span class="sxs-lookup"><span data-stu-id="01cd1-108">For leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="01cd1-109">Ad esempio, se l'anno di congedo dell'organizzazione va dal 1° giugno al 30 maggio e un dipendente ha preso tre giorni di congedo a dicembre, il 15 gennaio la scheda **Richiesto** visualizzerà 3 giorni.</span><span class="sxs-lookup"><span data-stu-id="01cd1-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken three days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="01cd1-110">Importi accumulo non corrispondenti alla base della data livello</span><span class="sxs-lookup"><span data-stu-id="01cd1-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="01cd1-111">Alcune nuove opzioni sono state aggiunte a congedi e assenze (parametri **Risorse umane** ) per consentire ai clienti di determinare quando la data dei mesi di servizio dei dipendenti è valida.</span><span class="sxs-lookup"><span data-stu-id="01cd1-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="01cd1-112">Per alcune organizzazioni, la data è la fine del mese, ma per altre può essere l'inizio del mese successivo.</span><span class="sxs-lookup"><span data-stu-id="01cd1-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="01cd1-113">Ad esempio, un'organizzazione può concedere permessi il 31 dicembre, mentre un'altra il 1° gennaio.</span><span class="sxs-lookup"><span data-stu-id="01cd1-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="01cd1-114">Questa opzione consentirà di scegliere quando concedere i permessi.</span><span class="sxs-lookup"><span data-stu-id="01cd1-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="01cd1-115">Le azioni di assunzione dei lavoratori sono bloccate allo stato "Flusso di lavoro completato"</span><span class="sxs-lookup"><span data-stu-id="01cd1-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="01cd1-116">Alcune modifiche sono state apportate per correggere un problema in cui un piccolo numero di flussi di lavoro termina con lo stato "Flusso di lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="01cd1-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="01cd1-117">I nuovi flussi di lavoro dovrebbero ora passare allo stato "Completato" quando vengono terminati.</span><span class="sxs-lookup"><span data-stu-id="01cd1-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="01cd1-118">Qualsiasi flusso di lavoro in uno stato completato passerà a uno stato di errore per consentire l'aggiornamento o la rimozione se necessario.</span><span class="sxs-lookup"><span data-stu-id="01cd1-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 
