---
title: Orario e presenze nella vendita al dettaglio
description: In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Microsoft Dynamics 365 for Retail.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ebbf3c72b4c34cba95ecd2fb3ce506af393acc34
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="retail-time-and-attendance"></a><span data-ttu-id="96d8f-103">Orario e presenze vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="96d8f-103">Retail time and attendance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="96d8f-104">In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="96d8f-104">This topic describes the scenarios that are supported for time and attendance management in Microsoft Dynamics 365 for Retail.</span></span> 

<a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="96d8f-105">Gestire l'impostazione e la programmazione dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="96d8f-105">Manage worker setup and scheduling</span></span>
----------------------------------

### <a name="initial-configuration"></a><span data-ttu-id="96d8f-106">Configurazione iniziale</span><span class="sxs-lookup"><span data-stu-id="96d8f-106">Initial configuration</span></span>

-   <span data-ttu-id="96d8f-107">Eseguire la Configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="96d8f-107">Run the configuration wizard.</span></span>
-   <span data-ttu-id="96d8f-108">Registrare i lavoratori come lavoratori per registrazione ore</span><span class="sxs-lookup"><span data-stu-id="96d8f-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="96d8f-109">Pianificare le programmazioni del lavoratore</span><span class="sxs-lookup"><span data-stu-id="96d8f-109">Plan worker schedules</span></span>

-   <span data-ttu-id="96d8f-110">Applicare profili utilizzando Pianificazione lavori.</span><span class="sxs-lookup"><span data-stu-id="96d8f-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="96d8f-111">Per ulteriori informazioni, vedere <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span><span class="sxs-lookup"><span data-stu-id="96d8f-111">For more information, see <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span></span>

<span data-ttu-id="96d8f-112">Per informazioni sui passaggi di configurazione, vedere <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span><span class="sxs-lookup"><span data-stu-id="96d8f-112">For information about the configuration steps, see <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="96d8f-113">Configurazione specifica per la vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="96d8f-113">Retail-specific configuration</span></span>

-   <span data-ttu-id="96d8f-114">Attivare un profilo funzionalità per l'orologio per i lavoratori per cui si desidera consentire le registrazioni ore.</span><span class="sxs-lookup"><span data-stu-id="96d8f-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="96d8f-115">Fare clic su **Profili funzionalità POS** &gt; **Funzioni** &gt; **Registrazioni ore POS** &gt; **Abilita registrazioni ore**.</span><span class="sxs-lookup"><span data-stu-id="96d8f-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
-   <span data-ttu-id="96d8f-116">Configurare i gruppi di autorizzazioni POS per abilitare l'autorizzazione Visualizza voci orologio.</span><span class="sxs-lookup"><span data-stu-id="96d8f-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="96d8f-117">Tale autorizzazione consente la visualizzazione delle registrazioni delle voci di entrata/uscita di altri lavoratori del punto vendita (e di qualsiasi altro punto vendita a cui l'utente è associato, tramite la Rubrica).</span><span class="sxs-lookup"><span data-stu-id="96d8f-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="96d8f-118">È consigliabile consentire l'autorizzazione per un ruolo di amministratore, ma non per un ruolo di cassiere.</span><span class="sxs-lookup"><span data-stu-id="96d8f-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="96d8f-119">Fare clic su **Gruppi di autorizzazioni POS** &gt; **Visualizza voci orologio**.</span><span class="sxs-lookup"><span data-stu-id="96d8f-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="96d8f-120">Ora registrazione</span><span class="sxs-lookup"><span data-stu-id="96d8f-120">Register time</span></span>
### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="96d8f-121">Registrazioni ore cassieri e ruoli diversi dal cassiere</span><span class="sxs-lookup"><span data-stu-id="96d8f-121">Cashier and non-cashier time registrations</span></span>

-   <span data-ttu-id="96d8f-122">Nel POS:</span><span class="sxs-lookup"><span data-stu-id="96d8f-122">On POS:</span></span>
    -   <span data-ttu-id="96d8f-123">Operazioni di entrata:</span><span class="sxs-lookup"><span data-stu-id="96d8f-123">Clock-in operations:</span></span>
        -   <span data-ttu-id="96d8f-124">Accedere a un'operazione non relativa al cassetto o di nuovo turno.</span><span class="sxs-lookup"><span data-stu-id="96d8f-124">Log on with a non-drawer operation or New shift.</span></span>
        -   <span data-ttu-id="96d8f-125">Selezionare un'operazione di orologio.</span><span class="sxs-lookup"><span data-stu-id="96d8f-125">Select a Time Clock operation.</span></span>
        -   <span data-ttu-id="96d8f-126">Selezionare un'operazione desiderata:</span><span class="sxs-lookup"><span data-stu-id="96d8f-126">Select a desired operation:</span></span>
            -   <span data-ttu-id="96d8f-127">Entrata</span><span class="sxs-lookup"><span data-stu-id="96d8f-127">Clock-in</span></span>
            -   <span data-ttu-id="96d8f-128">Pausa dal lavoro</span><span class="sxs-lookup"><span data-stu-id="96d8f-128">Break for Work</span></span>
            -   <span data-ttu-id="96d8f-129">Pausa pranzo</span><span class="sxs-lookup"><span data-stu-id="96d8f-129">Break for Lunch</span></span>
            -   <span data-ttu-id="96d8f-130">Uscita</span><span class="sxs-lookup"><span data-stu-id="96d8f-130">Clock-out</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="96d8f-131">Stato corrente</span><span class="sxs-lookup"><span data-stu-id="96d8f-131">Current state</span></span></th>
    <th><span data-ttu-id="96d8f-132">Operazioni disponibili</span><span class="sxs-lookup"><span data-stu-id="96d8f-132">Available operations</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="96d8f-133">Entrata</span><span class="sxs-lookup"><span data-stu-id="96d8f-133">Clock-in</span></span></td>
    <td><ul>
    <li><span data-ttu-id="96d8f-134">Pausa dal lavoro</span><span class="sxs-lookup"><span data-stu-id="96d8f-134">Break for Work</span></span></li>
    <li><span data-ttu-id="96d8f-135">Pausa pranzo</span><span class="sxs-lookup"><span data-stu-id="96d8f-135">Break for Lunch</span></span></li>
    <li><span data-ttu-id="96d8f-136">Uscita</span><span class="sxs-lookup"><span data-stu-id="96d8f-136">Clock-out</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="96d8f-137">Pausa dal lavoro</span><span class="sxs-lookup"><span data-stu-id="96d8f-137">Break for Work</span></span></td>
    <td><span data-ttu-id="96d8f-138">Entrata</span><span class="sxs-lookup"><span data-stu-id="96d8f-138">Clock-in</span></span></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="96d8f-139">Pausa pranzo</span><span class="sxs-lookup"><span data-stu-id="96d8f-139">Break for Lunch</span></span></td>
    <td><span data-ttu-id="96d8f-140">Entrata</span><span class="sxs-lookup"><span data-stu-id="96d8f-140">Clock-in</span></span></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="96d8f-141">Uscita</span><span class="sxs-lookup"><span data-stu-id="96d8f-141">Clock-out</span></span></td>
    <td><span data-ttu-id="96d8f-142">Entrata</span><span class="sxs-lookup"><span data-stu-id="96d8f-142">Clock-in</span></span></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="96d8f-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="96d8f-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>
-   <span data-ttu-id="96d8f-144">Consente di visualizzare il messaggio di conferma e di convalidare come corretto l'orario dell'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="96d8f-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
-   <span data-ttu-id="96d8f-145">Registro:</span><span class="sxs-lookup"><span data-stu-id="96d8f-145">Logbook:</span></span>
    -   <span data-ttu-id="96d8f-146">Fare clic su **Registro** per visualizzare l'attività di orologio.</span><span class="sxs-lookup"><span data-stu-id="96d8f-146">Click **Logbook** to view time clock activity.</span></span>
    -   <span data-ttu-id="96d8f-147">Utilizzare i filtri orari per per selezionare intervalli di tempo diversi.</span><span class="sxs-lookup"><span data-stu-id="96d8f-147">Use time filters to select different time windows.</span></span>
    -   <span data-ttu-id="96d8f-148">Se si lavora in più ubicazioni del punto di vendita, è possibile visualizzare le registrazioni ore da tutti i punti vendita in cui le ore sono state registrate.</span><span class="sxs-lookup"><span data-stu-id="96d8f-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="96d8f-149">È possibile utilizzare il filtro di punti vendita per visualizzare le registrazioni ore da un punto vendita selezionato.</span><span class="sxs-lookup"><span data-stu-id="96d8f-149">You can use the store filter to view time registrations from a selected store.</span></span>

<!-- -->

-   <span data-ttu-id="96d8f-150">Fusi orari diversi:</span><span class="sxs-lookup"><span data-stu-id="96d8f-150">Different time zones:</span></span>
    -   <span data-ttu-id="96d8f-151">Se si visualizza l'ora da un'ubicazione diversa (per il registro del cassiere o tramite l'opzione **Visualizza voci orologio** per uno scenario di amministratore) e tale ubicazione si trova in fuso orario diverso, i record orari vengono convertiti nel fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="96d8f-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="96d8f-152">Ad esempio, si è un responsabile per due punti vendita, uno in Arizona e l'altro in Nevada.</span><span class="sxs-lookup"><span data-stu-id="96d8f-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="96d8f-153">Un cassiere registra l'entrata alle 9.00 del mattino</span><span class="sxs-lookup"><span data-stu-id="96d8f-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="96d8f-154">in Arizona.</span><span class="sxs-lookup"><span data-stu-id="96d8f-154">in Arizona.</span></span> <span data-ttu-id="96d8f-155">In quel momento in Nevada sono le 8.00.</span><span class="sxs-lookup"><span data-stu-id="96d8f-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="96d8f-156">Di conseguenza, per il responsabile del punto vendita in Nevada i record orari riportano 8.00 come ora di registrazione.</span><span class="sxs-lookup"><span data-stu-id="96d8f-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="96d8f-157">Visualizzare le registrazioni ore dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="96d8f-157">View worker time registrations</span></span>
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="96d8f-158">Visualizzare le registrazioni ore del lavoratore e filtrare per punto vendita o tipo di attività</span><span class="sxs-lookup"><span data-stu-id="96d8f-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="96d8f-159">Nel POS:</span><span class="sxs-lookup"><span data-stu-id="96d8f-159">On POS:</span></span>

-   <span data-ttu-id="96d8f-160">Selezionare **Visualizza voci orologio**.</span><span class="sxs-lookup"><span data-stu-id="96d8f-160">Select **View timeclock entries**.</span></span>
-   <span data-ttu-id="96d8f-161">Vengono visualizzate tutte le attività di registrazione orologio di tutti i lavoratori assegnati agli stessi punti vendita a cui è assegnato l'utente.</span><span class="sxs-lookup"><span data-stu-id="96d8f-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
-   <span data-ttu-id="96d8f-162">È possibile utilizzare i filtri per tipo di attività e punto vendita per filtrare le registrazioni ore.</span><span class="sxs-lookup"><span data-stu-id="96d8f-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="96d8f-163">Elaborare e gestire le registrazioni ore</span><span class="sxs-lookup"><span data-stu-id="96d8f-163">Process and manage time registrations</span></span>
<span data-ttu-id="96d8f-164">Un utente di Dynamics 365 for Retail segue il flusso di lavoro per calcolare, approvare e trasferire le registrazioni ore alle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="96d8f-164">A Dynamics 365 for Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="96d8f-165">Operazioni primarie</span><span class="sxs-lookup"><span data-stu-id="96d8f-165">Primary operations</span></span>

-   <span data-ttu-id="96d8f-166">Calcola</span><span class="sxs-lookup"><span data-stu-id="96d8f-166">Calculate</span></span>
-   <span data-ttu-id="96d8f-167">Approva</span><span class="sxs-lookup"><span data-stu-id="96d8f-167">Approve</span></span>
-   <span data-ttu-id="96d8f-168">Inviare a retribuzioni</span><span class="sxs-lookup"><span data-stu-id="96d8f-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="96d8f-169">Altre operazioni comuni</span><span class="sxs-lookup"><span data-stu-id="96d8f-169">Other common operations</span></span>

-   <span data-ttu-id="96d8f-170">Uscita in blocco</span><span class="sxs-lookup"><span data-stu-id="96d8f-170">Bulk Clock-out</span></span>
-   <span data-ttu-id="96d8f-171">Registrare le assenze</span><span class="sxs-lookup"><span data-stu-id="96d8f-171">Register Absence</span></span>

<span data-ttu-id="96d8f-172">Per ulteriori informazioni su come elaborare le registrazioni di orari e presenze, vedere <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span><span class="sxs-lookup"><span data-stu-id="96d8f-172">For more information about how to process time and attendance registrations, see <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span></span>




