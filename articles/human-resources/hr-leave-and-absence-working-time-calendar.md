---
title: Creare un calendario orario di lavoro
description: Definire un calendario orario di lavoro, festività e orari non lavorativi in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: 2bedbe65f146c4159c2a809de8f683815fd4a01f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419178"
---
# <a name="create-a-working-time-calendar"></a><span data-ttu-id="debf1-103">Creare un calendario orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="debf1-103">Create a working time calendar</span></span>

<span data-ttu-id="debf1-104">Un calendario orario di lavoro in Dynamics 365 Human Resources mostra i giorni e le ore in cui i dipendenti lavorano nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="debf1-104">A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization.</span></span> <span data-ttu-id="debf1-105">Quando un dipendente invia una richiesta di permesso, non deve preoccuparsi di festività e chiusure.</span><span class="sxs-lookup"><span data-stu-id="debf1-105">When an employee submits a time-off request, they don't have to worry about holidays and closures.</span></span>

<span data-ttu-id="debf1-106">Per semplificare le richieste di permesso, configurare questi elementi per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="debf1-106">To streamline time-off requests, configure these items for your organization:</span></span>

- <span data-ttu-id="debf1-107">Calendario orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="debf1-107">Working time calendar</span></span>
- <span data-ttu-id="debf1-108">Festività e chiusure</span><span class="sxs-lookup"><span data-stu-id="debf1-108">Holidays and closures</span></span>
- <span data-ttu-id="debf1-109">Orario non lavorativo</span><span class="sxs-lookup"><span data-stu-id="debf1-109">Non-work time</span></span>

<span data-ttu-id="debf1-110">È possibile aggiungere gli ultimi due elementi mentre si imposta un calendario orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="debf1-110">You can add the last two items while you're setting up a working time calendar.</span></span> <span data-ttu-id="debf1-111">È anche possibile configurarli o aggiornarli separatamente.</span><span class="sxs-lookup"><span data-stu-id="debf1-111">You can also configure or update them separately.</span></span>

## <a name="set-up-a-working-time-calendar"></a><span data-ttu-id="debf1-112">Impostare un calendario orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="debf1-112">Set up a working time calendar</span></span>

<span data-ttu-id="debf1-113">Impostare almeno un calendario orario di lavoro che mostri i giorni e le ore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="debf1-113">Set up at least one working time calendar that shows your days and hours of operation.</span></span> <span data-ttu-id="debf1-114">Se si hanno ubicazioni in più paesi e aree geografiche, è possibile che si intenda impostare un calendario orario di lavoro per ogni area.</span><span class="sxs-lookup"><span data-stu-id="debf1-114">If you have locations in multiple countries and regions, you might want to set up a working time calendar for each area.</span></span>

1. <span data-ttu-id="debf1-115">Nella pagina **Amministrazione organizzazione** selezionare **Calendari**.</span><span class="sxs-lookup"><span data-stu-id="debf1-115">On the **Organization administration** page, select **Calendars**.</span></span>

2. <span data-ttu-id="debf1-116">Selezionare **Nuovo** e immettere un nome e una descrizione per il calendario.</span><span class="sxs-lookup"><span data-stu-id="debf1-116">Select **New** and enter a name and description for your calendar.</span></span>

3. <span data-ttu-id="debf1-117">Sotto **Opzioni di generazione**, selezionare i giorni lavorativi dell'organizzazione e immettere gli orari di lavoro.</span><span class="sxs-lookup"><span data-stu-id="debf1-117">Under **Generation options**, select the work days for your organization and enter work times.</span></span> 
   - <span data-ttu-id="debf1-118">Per aggiungere una festività o una chiusura, selezionare il pulsante **Aggiungi** accanto a **Festività e chiusure**.</span><span class="sxs-lookup"><span data-stu-id="debf1-118">To add a holiday or closure, select the **Add** button next to **Holidays and closures**.</span></span>
   - <span data-ttu-id="debf1-119">Per aggiungere un orario non lavorativo, come i pranzi o le pause, selezionare **Aggiungi** sotto **ORARIO NON LAVORATIVO** e immettere il nome e l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="debf1-119">To add non-work time, like lunches or breaks, select **Add** under **NON-WORK TIME** and enter the name and time range.</span></span>

4. <span data-ttu-id="debf1-120">Sotto **Giorni** selezionare **Genera** per generare i giorni nel calendario.</span><span class="sxs-lookup"><span data-stu-id="debf1-120">Under **Days**, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="debf1-121">Immettere l'intervallo di date per il calendario e quindi selezionare **Genera giorni**.</span><span class="sxs-lookup"><span data-stu-id="debf1-121">Enter the date range for your calendar and then select **Generate days**.</span></span>

5. <span data-ttu-id="debf1-122">Per aggiungere programmi di lavoro, in **Programma lavori**, selezionare **Aggiungi** e quindi immettere gli orari per ogni programma.</span><span class="sxs-lookup"><span data-stu-id="debf1-122">To add work schedules, under **Work schedule**, select **Add** and then enter the times for each work schedule.</span></span>

## <a name="configure-holidays-and-closures"></a><span data-ttu-id="debf1-123">Configurare festività e chiusure</span><span class="sxs-lookup"><span data-stu-id="debf1-123">Configure holidays and closures</span></span>

<span data-ttu-id="debf1-124">È possibile aggiungere o modificare festività e chiusure separatamente da un calendario orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="debf1-124">You can add or change holidays and closures separately from a working time calendar.</span></span>

1. <span data-ttu-id="debf1-125">Nella pagina **Amministrazione organizzazione** selezionare **Festività e chiusure**.</span><span class="sxs-lookup"><span data-stu-id="debf1-125">On the **Organization administration** page, select **Holidays and closures**.</span></span>

2. <span data-ttu-id="debf1-126">Selezionare **Nuovo** e immettere una data per la festività o la chiusura.</span><span class="sxs-lookup"><span data-stu-id="debf1-126">Select **New** and enter a name and date for the holiday or closure.</span></span>

## <a name="configure-non-work-time"></a><span data-ttu-id="debf1-127">Configurare orari non lavorativi</span><span class="sxs-lookup"><span data-stu-id="debf1-127">Configure non-work time</span></span>

<span data-ttu-id="debf1-128">È possibile aggiungere o modificare orari non lavorativi separatamente da un calendario orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="debf1-128">You can add or change non-work times separately from a working time calendar.</span></span>

1. <span data-ttu-id="debf1-129">Nella pagina **Amministrazione organizzazione** selezionare **Orario non lavorativo**.</span><span class="sxs-lookup"><span data-stu-id="debf1-129">On the **Organization administration** page, select **Non-work time**.</span></span>

2. <span data-ttu-id="debf1-130">Selezionare **Nuovo** e immettere un nome e la fascia oraria per l'orario non lavorativo.</span><span class="sxs-lookup"><span data-stu-id="debf1-130">Select **New** and enter a name and time range for the non-work time.</span></span>

<span data-ttu-id="debf1-131">Se la funzionalità di anteprima per la correzione di giorni festivi di Congedo e assenza è stata abilitata, Human Resources utilizza le date di festività e chiusura per determinare il numero di giorni da rettificare per i dipendenti iscritti al calendario.</span><span class="sxs-lookup"><span data-stu-id="debf1-131">If you've enabled the Leave and absence bank holiday corrections preview feature, Human Resources uses holidays and closure dates to determine the number of days to adjust for employees enrolled in the calendar.</span></span>

## <a name="see-also"></a><span data-ttu-id="debf1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="debf1-132">See also</span></span>

- [<span data-ttu-id="debf1-133">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="debf1-133">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="debf1-134">Configurare tipi di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="debf1-134">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)
