---
title: Gestione di congedo e assenza
description: In questo argomento viene fornita una panoramica del modulo di gestione di congedi e assenze.
author: andreabichsel
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ebfaeb0696d7200ddf3c715f96a259b91db08e7a
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518350"
---
# <a name="leave-and-absence-management"></a><span data-ttu-id="f5617-103">Gestione di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="f5617-103">Leave and absence management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f5617-104">Il modulo di **gestione di congedi e assenze** offre un framework flessibile per la definizione del processo di gestione delle assenze.</span><span class="sxs-lookup"><span data-stu-id="f5617-104">The **Leave and absence management** module offers a flexible framework for defining the absence management process.</span></span> <span data-ttu-id="f5617-105">È possibile creare piani di congedo e assenza per determinare come i dipendenti accumulano o usano i permessi.</span><span class="sxs-lookup"><span data-stu-id="f5617-105">Leave and absence plans can be created to determine how employees accrue or are granted time off.</span></span> <span data-ttu-id="f5617-106">Dopo l'iscrizione a un piano, i dipendenti possono presentare le richieste di permesso ai responsabili per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="f5617-106">After employees are enrolled in a plan, they can submit time-off requests for approval by managers.</span></span> <span data-ttu-id="f5617-107">Il rilevamento di congedi consente ai responsabili di primo livello e ai responsabili di Risorse umane di vedere il dipendente in permesso e le ore di assenza residue.</span><span class="sxs-lookup"><span data-stu-id="f5617-107">Leave tracking lets both first-level managers and Human Resources (HR) managers see who is taking time off and how much time off each employee still has.</span></span>  

<span data-ttu-id="f5617-108">Il modulo di gestione di congedi e assenze fornisce le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="f5617-108">Leave and absence management provides the following features:</span></span> 

- <span data-ttu-id="f5617-109">**Definizione dei tipi di congedo e assenza**</span><span class="sxs-lookup"><span data-stu-id="f5617-109">**Define leave and absence types.**</span></span>

    <span data-ttu-id="f5617-110">I tipi di congedo definiscono i diversi tipi di assenza che i dipendenti possono dichiarare.</span><span class="sxs-lookup"><span data-stu-id="f5617-110">Leave types define the various types of absences that employees can report.</span></span> <span data-ttu-id="f5617-111">Poiché questi tipi sono definiti dall'utente, possono essere personalizzati in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5617-111">Because these types are user-defined, they can be tailored to your organization.</span></span> <span data-ttu-id="f5617-112">Alcuni tipi di congedo tipici sono permesso retribuito, ferie, malattia, funzione pubblica e lutto.</span><span class="sxs-lookup"><span data-stu-id="f5617-112">Some typical leave types include paid time off (PTO), leave, short-term disability, jury duty (this leave type is specific to the United States), and bereavement.</span></span> 

- <span data-ttu-id="f5617-113">**Definizione di piani di congedo e assenza a livelli per soddisfare le esigenze aziendali**</span><span class="sxs-lookup"><span data-stu-id="f5617-113">**Define leave and absence plans that are tiered to fit your business.**</span></span>

    <span data-ttu-id="f5617-114">È possibile definire piani di congedo e assenza di modo che l'accumulo avvenga a specifiche frequenze, ad esempio annualmente, mensilmente o ogni quindici giorni.</span><span class="sxs-lookup"><span data-stu-id="f5617-114">Leave and absence plans can be defined so that accrual occurs at specific frequencies, such as annually, monthly, or semimonthly.</span></span> <span data-ttu-id="f5617-115">I piani possono inoltre essere definiti come una concessione, dove un singolo accumulo avviene a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="f5617-115">Plans can also be defined as a grant, where a single accrual occurs on a specific date.</span></span> 

    <span data-ttu-id="f5617-116">I piani di congedo spesso includono dei livelli, dove alcuni gruppi di dipendenti ricevono ulteriori benefit, in base agli anni di servizio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5617-116">Leave plans often contain tiers, where some groups of employees receive additional benefits, based on the amount of time that they have been with the organization.</span></span> <span data-ttu-id="f5617-117">Questi livelli definiti dall'utente consentono l'iscrizione automatica a ulteriori ore benefit, in base ai criteri di data definiti.</span><span class="sxs-lookup"><span data-stu-id="f5617-117">These user-defined tiers enable automatic enrollment in additional benefit hours, based on the date criteria that are defined.</span></span> <span data-ttu-id="f5617-118">I piani di congedo possono essere configurati per applicare un limite di riporto massimo o un saldo minimo, in modo da impedire ai dipendenti di utilizzare più ore benefit di quelle accumulate.</span><span class="sxs-lookup"><span data-stu-id="f5617-118">Leave plans can also be configured to enforce a maximum carry-over amount or a minimum balance, to prevent employees from using more benefit hours than they have accrued.</span></span> 

    <span data-ttu-id="f5617-119">Piani di congedo tipici includono piani a livelli che concedono un benefit di 80 ore in permessi retribuiti ai nuovi dipendenti e un benefit di 120 ore dopo 60 mesi di servizio.</span><span class="sxs-lookup"><span data-stu-id="f5617-119">Typical leave plans include tiered plans that grant a benefit of 80 hours of PTO to new employees but a benefit of 120 hours after 60 months of service.</span></span> <span data-ttu-id="f5617-120">Ulteriori piani potrebbero concedere festività mobili o benefit in base alla posizione, ad esempio ore benefit solo per i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="f5617-120">Additional plans might grant floating holidays or position-based benefits, such as executive-only benefit hours.</span></span>

- <span data-ttu-id="f5617-121">**Iscrizione dei dipendenti ai piani di congedo e assenza individualmente o mediante un'assegnazione di massa in base ai criteri delle mansioni**</span><span class="sxs-lookup"><span data-stu-id="f5617-121">**Enroll employees in leave and absence plans individually or through mass assignment that is based on job criteria.**</span></span>

    <span data-ttu-id="f5617-122">Diversi filtri relativi alle mansioni consentono di assegnare un gruppo di dipendenti a un piano di congedo.</span><span class="sxs-lookup"><span data-stu-id="f5617-122">Several job-related filters can be used to assign a group of employees to a leave plan.</span></span> <span data-ttu-id="f5617-123">I responsabili di Risorse umane possono visualizzare un dipendente per verificare a quali piani di congedo e assenza è iscritto.</span><span class="sxs-lookup"><span data-stu-id="f5617-123">HR managers can view an employee to see what leave and absence plans the employee is enrolled in.</span></span> <span data-ttu-id="f5617-124">In alternativa, i responsabili di Risorse umane possono visualizzare tutti i piani e le relative iscrizioni dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="f5617-124">Alternatively, HR managers can view all plans and the related employee enrollments.</span></span>

- <span data-ttu-id="f5617-125">**Sospensione di piani di congedo e assenza**</span><span class="sxs-lookup"><span data-stu-id="f5617-125">**Suspend leave and absence plans.**</span></span>

    <span data-ttu-id="f5617-126">È possibile sospendere i piani di congedo e assenza per renderli inattivi e impedire ulteriori accumuli.</span><span class="sxs-lookup"><span data-stu-id="f5617-126">Leave and absence plans can be suspended to make them inactive and prevent additional accruals.</span></span> <span data-ttu-id="f5617-127">Gli accumuli dei dipendenti vengono sospesi in caso di fine impiego.</span><span class="sxs-lookup"><span data-stu-id="f5617-127">Accruals are suspended for employees if their employment ends.</span></span>  

- <span data-ttu-id="f5617-128">**Rettifica di diritti e concessioni**</span><span class="sxs-lookup"><span data-stu-id="f5617-128">**Adjust entitlements and grants.**</span></span>

    <span data-ttu-id="f5617-129">Un dipendente può essere iscritto a un livello superiore di un piano utilizzando una data specifica per sostituire il piano predefinito del dipendente.</span><span class="sxs-lookup"><span data-stu-id="f5617-129">An employee can be enrolled in a higher plan tier by using a worker-specific date to override the employee's default plan offering.</span></span> <span data-ttu-id="f5617-130">Il saldo congedo e assenza dei dipendenti può essere rettificato manualmente al momento dell'iscrizione al piano oppure in qualsiasi momento da parte di Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="f5617-130">Employees can receive a manual adjustment to their leave and absence balance at the time of plan enrollment, or HR can make a manual adjustment at any time.</span></span> 

- <span data-ttu-id="f5617-131">**Applicazione di un flusso di lavoro alle richieste di permesso**</span><span class="sxs-lookup"><span data-stu-id="f5617-131">**Apply a workflow to time-off requests.**</span></span>

     <span data-ttu-id="f5617-132">Un flusso di lavoro può essere personalizzato e applicato alle richieste di permesso per soddisfare i requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5617-132">A workflow can be customized and applied to time-off requests to meet the organization’s requirements.</span></span>  

- <span data-ttu-id="f5617-133">**Visualizzazione dei saldi assenza dei dipendenti**</span><span class="sxs-lookup"><span data-stu-id="f5617-133">**Track employee absence balances.**</span></span>

    <span data-ttu-id="f5617-134">I dipendenti, il relativo responsabile e Risorse umane possono visualizzare i saldi congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="f5617-134">Employees, their manager, and HR can view leave and absence balances.</span></span> <span data-ttu-id="f5617-135">Risorse umane può utilizzare report interattivi per tenere traccia delle iscrizioni ai piani e dei saldi permesso per tipo.</span><span class="sxs-lookup"><span data-stu-id="f5617-135">HR can use interactive reports to track plan enrollments and time-off balances by type.</span></span> 

- <span data-ttu-id="f5617-136">**Inoltro delle richieste di permesso**</span><span class="sxs-lookup"><span data-stu-id="f5617-136">**Submit time-off requests.**</span></span>

    <span data-ttu-id="f5617-137">I dipendenti possono inoltrare le richieste di permesso a fronte delle ore disponibili.</span><span class="sxs-lookup"><span data-stu-id="f5617-137">Employees can submit time-off requests against their available hours.</span></span> <span data-ttu-id="f5617-138">Le richieste possono essere semplici richieste di un solo giorno oppure di più giorni che includono più tipi di congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="f5617-138">Requests can be simple single-day requests or multiple-day requests that include multiple leave and absence types.</span></span> <span data-ttu-id="f5617-139">Se un flusso di lavoro non è attivato, le richieste vengono approvate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f5617-139">If a workflow isn't enabled, the requests are automatically approved.</span></span> <span data-ttu-id="f5617-140">Se un flusso di lavoro è attivato, l'approvazione può essere automatica o richiedere una conferma, a seconda della configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f5617-140">If a workflow is enabled, the approval can be automatic, or it can require sign-off, depending on the workflow configuration.</span></span>
