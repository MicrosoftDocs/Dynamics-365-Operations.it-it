---
title: Gestione di Orario e presenze in Retail
description: In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Dynamics 365 Retail.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 887b0ff8bf78cd99b3a2ec34416f0265297f556a
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570101"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="02dba-103">Gestione di Orario e presenze in Retail</span><span class="sxs-lookup"><span data-stu-id="02dba-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02dba-104">In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="02dba-104">This topic describes the scenarios that are supported for time and attendance management in Dynamics 365 Retail.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="02dba-105">Gestire l'impostazione e la programmazione dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="02dba-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="02dba-106">Configurazione iniziale</span><span class="sxs-lookup"><span data-stu-id="02dba-106">Initial configuration</span></span>

- <span data-ttu-id="02dba-107">Eseguire la Configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="02dba-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="02dba-108">Registrare i lavoratori come lavoratori per registrazione ore</span><span class="sxs-lookup"><span data-stu-id="02dba-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="02dba-109">Pianificare le programmazioni del lavoratore</span><span class="sxs-lookup"><span data-stu-id="02dba-109">Plan worker schedules</span></span>

- <span data-ttu-id="02dba-110">Applicare profili utilizzando Pianificazione lavori.</span><span class="sxs-lookup"><span data-stu-id="02dba-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="02dba-111">Per ulteriori informazioni, vedere [Applicare profili utilizzando Pianificazione lavori](https://technet.microsoft.com/library/aa551234.aspx).</span><span class="sxs-lookup"><span data-stu-id="02dba-111">For more information, see [Apply profiles using work planner](https://technet.microsoft.com/library/aa551234.aspx).</span></span>

<span data-ttu-id="02dba-112">Per informazioni sui passaggi di configurazione, vedere [Impostazione di orari e presenze](https://technet.microsoft.com/library/aa496971.aspx).</span><span class="sxs-lookup"><span data-stu-id="02dba-112">For information about the configuration steps, see [Setting up time and attendance](https://technet.microsoft.com/library/aa496971.aspx).</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="02dba-113">Configurazione specifica per la vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="02dba-113">Retail-specific configuration</span></span>

- <span data-ttu-id="02dba-114">Attivare un profilo funzionalità per l'orologio per i lavoratori per cui si desidera consentire le registrazioni ore.</span><span class="sxs-lookup"><span data-stu-id="02dba-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="02dba-115">Fare clic su **Profili funzionalità POS** &gt; **Funzioni** &gt; **Registrazioni ore POS** &gt; **Abilita registrazioni ore**.</span><span class="sxs-lookup"><span data-stu-id="02dba-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="02dba-116">Configurare i gruppi di autorizzazioni POS per abilitare l'autorizzazione Visualizza voci orologio.</span><span class="sxs-lookup"><span data-stu-id="02dba-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="02dba-117">Tale autorizzazione consente la visualizzazione delle registrazioni delle voci di entrata/uscita di altri lavoratori del punto vendita (e di qualsiasi altro punto vendita a cui l'utente è associato, tramite la Rubrica).</span><span class="sxs-lookup"><span data-stu-id="02dba-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="02dba-118">È consigliabile consentire l'autorizzazione per un ruolo di amministratore, ma non per un ruolo di cassiere.</span><span class="sxs-lookup"><span data-stu-id="02dba-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="02dba-119">Fare clic su **Gruppi di autorizzazioni POS** &gt; **Visualizza voci orologio**.</span><span class="sxs-lookup"><span data-stu-id="02dba-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="02dba-120">Ora registrazione</span><span class="sxs-lookup"><span data-stu-id="02dba-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="02dba-121">Registrazioni ore cassieri e ruoli diversi dal cassiere</span><span class="sxs-lookup"><span data-stu-id="02dba-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="02dba-122">Nel POS:</span><span class="sxs-lookup"><span data-stu-id="02dba-122">On POS:</span></span>

    - <span data-ttu-id="02dba-123">Operazioni di entrata:</span><span class="sxs-lookup"><span data-stu-id="02dba-123">Clock-in operations:</span></span>

        - <span data-ttu-id="02dba-124">Accedere a un'operazione non relativa al cassetto o di nuovo turno.</span><span class="sxs-lookup"><span data-stu-id="02dba-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="02dba-125">Selezionare un'operazione di orologio.</span><span class="sxs-lookup"><span data-stu-id="02dba-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="02dba-126">Selezionare un'operazione desiderata:</span><span class="sxs-lookup"><span data-stu-id="02dba-126">Select a desired operation:</span></span>

            - <span data-ttu-id="02dba-127">Entrata</span><span class="sxs-lookup"><span data-stu-id="02dba-127">Clock-in</span></span>
            - <span data-ttu-id="02dba-128">Pausa dal lavoro</span><span class="sxs-lookup"><span data-stu-id="02dba-128">Break for Work</span></span>
            - <span data-ttu-id="02dba-129">Pausa pranzo</span><span class="sxs-lookup"><span data-stu-id="02dba-129">Break for Lunch</span></span>
            - <span data-ttu-id="02dba-130">Uscita</span><span class="sxs-lookup"><span data-stu-id="02dba-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="02dba-131">Stato corrente</span><span class="sxs-lookup"><span data-stu-id="02dba-131">Current state</span></span></th>
        <th><span data-ttu-id="02dba-132">Operazioni disponibili</span><span class="sxs-lookup"><span data-stu-id="02dba-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="02dba-133">Entrata</span><span class="sxs-lookup"><span data-stu-id="02dba-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="02dba-134">Pausa dal lavoro</span><span class="sxs-lookup"><span data-stu-id="02dba-134">Break for Work</span></span></li>
        <li><span data-ttu-id="02dba-135">Pausa pranzo</span><span class="sxs-lookup"><span data-stu-id="02dba-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="02dba-136">Uscita</span><span class="sxs-lookup"><span data-stu-id="02dba-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="02dba-137">Pausa dal lavoro</span><span class="sxs-lookup"><span data-stu-id="02dba-137">Break for Work</span></span></td>
        <td><span data-ttu-id="02dba-138">Entrata</span><span class="sxs-lookup"><span data-stu-id="02dba-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="02dba-139">Pausa pranzo</span><span class="sxs-lookup"><span data-stu-id="02dba-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="02dba-140">Entrata</span><span class="sxs-lookup"><span data-stu-id="02dba-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="02dba-141">Uscita</span><span class="sxs-lookup"><span data-stu-id="02dba-141">Clock-out</span></span></td>
        <td><span data-ttu-id="02dba-142">Entrata</span><span class="sxs-lookup"><span data-stu-id="02dba-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="02dba-143">[![Stati dell'orologio](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="02dba-143">[![Time Clock States](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="02dba-144">Consente di visualizzare il messaggio di conferma e di convalidare come corretto l'orario dell'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="02dba-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="02dba-145">Registro:</span><span class="sxs-lookup"><span data-stu-id="02dba-145">Logbook:</span></span>

    - <span data-ttu-id="02dba-146">Fare clic su **Registro** per visualizzare l'attività di orologio.</span><span class="sxs-lookup"><span data-stu-id="02dba-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="02dba-147">Utilizzare i filtri orari per per selezionare intervalli di tempo diversi.</span><span class="sxs-lookup"><span data-stu-id="02dba-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="02dba-148">Se si lavora in più ubicazioni del punto di vendita, è possibile visualizzare le registrazioni ore da tutti i punti vendita in cui le ore sono state registrate.</span><span class="sxs-lookup"><span data-stu-id="02dba-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="02dba-149">È possibile utilizzare il filtro di punti vendita per visualizzare le registrazioni ore da un punto vendita selezionato.</span><span class="sxs-lookup"><span data-stu-id="02dba-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="02dba-150">Fusi orari diversi:</span><span class="sxs-lookup"><span data-stu-id="02dba-150">Different time zones:</span></span>

    - <span data-ttu-id="02dba-151">Se si visualizza l'ora da un'ubicazione diversa (per il registro del cassiere o tramite l'opzione **Visualizza voci orologio** per uno scenario di amministratore) e tale ubicazione si trova in fuso orario diverso, i record orari vengono convertiti nel fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="02dba-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="02dba-152">Ad esempio, si è un responsabile per due punti vendita, uno in Arizona e l'altro in Nevada.</span><span class="sxs-lookup"><span data-stu-id="02dba-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="02dba-153">Un cassiere registra l'entrata alle 9.00 del mattino</span><span class="sxs-lookup"><span data-stu-id="02dba-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="02dba-154">in Arizona.</span><span class="sxs-lookup"><span data-stu-id="02dba-154">in Arizona.</span></span> <span data-ttu-id="02dba-155">In quel momento in Nevada sono le 8.00.</span><span class="sxs-lookup"><span data-stu-id="02dba-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="02dba-156">Di conseguenza, per il responsabile del punto vendita in Nevada i record orari riportano 8.00 come ora di registrazione.</span><span class="sxs-lookup"><span data-stu-id="02dba-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="02dba-157">Visualizzare le registrazioni ore dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="02dba-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="02dba-158">Visualizzare le registrazioni ore del lavoratore e filtrare per punto vendita o tipo di attività</span><span class="sxs-lookup"><span data-stu-id="02dba-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="02dba-159">Nel POS:</span><span class="sxs-lookup"><span data-stu-id="02dba-159">On POS:</span></span>

- <span data-ttu-id="02dba-160">Selezionare **Visualizza voci orologio**.</span><span class="sxs-lookup"><span data-stu-id="02dba-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="02dba-161">Vengono visualizzate tutte le attività di registrazione orologio di tutti i lavoratori assegnati agli stessi punti vendita a cui è assegnato l'utente.</span><span class="sxs-lookup"><span data-stu-id="02dba-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="02dba-162">È possibile utilizzare i filtri per tipo di attività e punto vendita per filtrare le registrazioni ore.</span><span class="sxs-lookup"><span data-stu-id="02dba-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="02dba-163">Elaborare e gestire le registrazioni ore</span><span class="sxs-lookup"><span data-stu-id="02dba-163">Process and manage time registrations</span></span>

<span data-ttu-id="02dba-164">Un utente di Retail segue il flusso di lavoro per calcolare, approvare e trasferire le registrazioni ore alle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="02dba-164">A Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="02dba-165">Operazioni primarie</span><span class="sxs-lookup"><span data-stu-id="02dba-165">Primary operations</span></span>

- <span data-ttu-id="02dba-166">Calcola</span><span class="sxs-lookup"><span data-stu-id="02dba-166">Calculate</span></span>
- <span data-ttu-id="02dba-167">Approva</span><span class="sxs-lookup"><span data-stu-id="02dba-167">Approve</span></span>
- <span data-ttu-id="02dba-168">Inviare a retribuzioni</span><span class="sxs-lookup"><span data-stu-id="02dba-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="02dba-169">Altre operazioni comuni</span><span class="sxs-lookup"><span data-stu-id="02dba-169">Other common operations</span></span>

- <span data-ttu-id="02dba-170">Uscita in blocco</span><span class="sxs-lookup"><span data-stu-id="02dba-170">Bulk Clock-out</span></span>
- <span data-ttu-id="02dba-171">Registrare le assenze</span><span class="sxs-lookup"><span data-stu-id="02dba-171">Register Absence</span></span>

<span data-ttu-id="02dba-172">Per ulteriori informazioni su come elaborare le registrazioni di orari e presenze, vedere [Elaborare le registrazioni in Orario e presenze](https://technet.microsoft.com/library/aa573180.aspx).</span><span class="sxs-lookup"><span data-stu-id="02dba-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](https://technet.microsoft.com/library/aa573180.aspx).</span></span>
