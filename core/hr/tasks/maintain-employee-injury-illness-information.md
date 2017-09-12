--- 
title: Gestire le informazioni sull'infortunio e la malattia del dipendente
description: "Si consiglia di completare prima la guida di attività 'Impostazione infortunio e malattia' perché alcune informazioni di impostazione vengono utilizzate qui."
author: ShielaSogge
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7b0df977d46ac87744d1ddc36d0c7b3f1d292f6a
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="maintain-employee-injury-and-illness-information"></a><span data-ttu-id="4c924-103">Gestire le informazioni sull'infortunio e la malattia del dipendente</span><span class="sxs-lookup"><span data-stu-id="4c924-103">Maintain employee injury and illness information</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4c924-104">Si consiglia di completare prima la guida di attività 'Impostazione infortunio e malattia' perché alcune informazioni di impostazione vengono utilizzate qui.</span><span class="sxs-lookup"><span data-stu-id="4c924-104">It is recommended to complete the 'Setup injury and illness' task guide first, as some of the setup information is used here.</span></span> 



<span data-ttu-id="4c924-105">Questa registrazione attività copre i passaggi fondamentali per la creazione di un caso di infortunio o malattia.</span><span class="sxs-lookup"><span data-stu-id="4c924-105">This task recording covers the basic steps to creating an injury or illness case.</span></span> <span data-ttu-id="4c924-106">Oltre a tracciare i dettagli dell'infortunio o della malattia, viene tracciato anche lo stato del caso.</span><span class="sxs-lookup"><span data-stu-id="4c924-106">Besides tracking the details of the injury or illness, there is a case status that is tracked as well.</span></span>  <span data-ttu-id="4c924-107">Per il caso viene utilizzato il valore predefinito 'aperto' per lo stato.</span><span class="sxs-lookup"><span data-stu-id="4c924-107">The case defaults with an 'open' status.</span></span>  <span data-ttu-id="4c924-108">Gli stati possono essere gestiti dalla voce di menu 'Stato caso' nella barra dell'applicazione nella parte superiore del modulo.</span><span class="sxs-lookup"><span data-stu-id="4c924-108">The statuses can be managed from the 'Case status' menu item in the application bar at the top of the form.</span></span>

1. <span data-ttu-id="4c924-109">Andare a Risorse umane > Lavoratori > Infortunio e malattia > Eventi imprevisti di infortunio o malattia.</span><span class="sxs-lookup"><span data-stu-id="4c924-109">Go to Human resources > Workers > Injury and illness > Injury or illness incidents.</span></span>
2. <span data-ttu-id="4c924-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4c924-110">Click New.</span></span>
3. <span data-ttu-id="4c924-111">Digitare un valore nel campo Descrizione caso.</span><span class="sxs-lookup"><span data-stu-id="4c924-111">In the Case description field, type a value.</span></span>
    * <span data-ttu-id="4c924-112">Esempio: infortunio al polso</span><span class="sxs-lookup"><span data-stu-id="4c924-112">Example:  Wrist injury</span></span>  
4. <span data-ttu-id="4c924-113">Nel campo Lavoratore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-113">In the Worker field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-114">Esempio: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="4c924-114">Example: Ahmed Barnett</span></span>  
5. <span data-ttu-id="4c924-115">Nel campo Data e ora evento imprevisto immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4c924-115">In the Date and time of incident field, enter a date and time.</span></span>
    * <span data-ttu-id="4c924-116">Esempio: 20/01/2016 10.00</span><span class="sxs-lookup"><span data-stu-id="4c924-116">Example:  1/20/2016 10:00 AM</span></span>  
6. <span data-ttu-id="4c924-117">Nel campo Tipo di infortunio o malattia, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-117">In the Injury or illness type field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-118">Esempio: frattura</span><span class="sxs-lookup"><span data-stu-id="4c924-118">Example:  Fracture</span></span>  
7. <span data-ttu-id="4c924-119">Nel campo Parte del corpo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-119">In the Body part field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-120">Esempio: polso</span><span class="sxs-lookup"><span data-stu-id="4c924-120">Example:  Wrist</span></span>  
8. <span data-ttu-id="4c924-121">Nel campo Tipo di esito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-121">In the Outcome type field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-122">Esempio: terapia</span><span class="sxs-lookup"><span data-stu-id="4c924-122">Example:  Therapy</span></span>  
9. <span data-ttu-id="4c924-123">Nel campo Data e ora restituite immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4c924-123">In the Date and time reported field, enter a date and time.</span></span>
    * <span data-ttu-id="4c924-124">La data e l'ora restituite devono essere successive alla data e all'ora dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="4c924-124">The date and time reported must be later than the date and time of incident.</span></span>  
10. <span data-ttu-id="4c924-125">Nel campo Persona che ha segnalato il caso, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-125">In the Person who reported case field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-126">Potrebbe essere il dipendente o un altro testimone dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="4c924-126">This could be the employee or another witness to the incident.</span></span>  <span data-ttu-id="4c924-127">Esempio: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="4c924-127">Example: Ahmed Barnett</span></span>  
11. <span data-ttu-id="4c924-128">Espandere la sezione Evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4c924-128">Expand the Incident section.</span></span>
12. <span data-ttu-id="4c924-129">Nel campo Luogo dell'evento imprevisto, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-129">In the Where incident occurred field, type a value.</span></span>
    * <span data-ttu-id="4c924-130">Esempio: Magazzino</span><span class="sxs-lookup"><span data-stu-id="4c924-130">Example:  Warehouse</span></span>  
13. <span data-ttu-id="4c924-131">Selezionare Sì nel campo Sul posto di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4c924-131">Select Yes in the On work premises field.</span></span>
    * <span data-ttu-id="4c924-132">Se l'evento imprevisto si è verificato sul posto di lavoro, selezionare sì.</span><span class="sxs-lookup"><span data-stu-id="4c924-132">If the incident occurred on work premises, select yes.</span></span>  
14. <span data-ttu-id="4c924-133">Nel campo Data e ora di inizio lavoro immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4c924-133">In the Date and time began work field, enter a date and time.</span></span>
    * <span data-ttu-id="4c924-134">Immettere la data e l'ora in cui l'utente interessato ha iniziato a lavorare, prima che si verificasse l'incidente.</span><span class="sxs-lookup"><span data-stu-id="4c924-134">Enter the date and time that affected individual started working, prior to the incident occurring.</span></span>  
15. <span data-ttu-id="4c924-135">Nel campo Posizione lavorativa o attività del dipendente, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-135">In the Employee job or task field, type a value.</span></span>
    * <span data-ttu-id="4c924-136">Immettere la mansione o l'attività che il lavoratore stava svolgendo quando si è verificato l'incidente.</span><span class="sxs-lookup"><span data-stu-id="4c924-136">Enter the job or task the worker was performing when the incident occurred.</span></span>  <span data-ttu-id="4c924-137">Esempio: caricamento scatole</span><span class="sxs-lookup"><span data-stu-id="4c924-137">Example:  Loading boxes</span></span>  
16. <span data-ttu-id="4c924-138">Digitare un valore nel campo Causa dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4c924-138">In the Cause of incident field, type a value.</span></span>
    * <span data-ttu-id="4c924-139">Immettere la causa dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="4c924-139">Enter the cause of the incident.</span></span>  <span data-ttu-id="4c924-140">Esempio: scivolato sul pavimento bagnato</span><span class="sxs-lookup"><span data-stu-id="4c924-140">Example:  Slipped on wet floor</span></span>  
17. <span data-ttu-id="4c924-141">Nel campo Livello di gravità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-141">In the Severity level field, enter or select a value.</span></span>
18. <span data-ttu-id="4c924-142">Nel campo Azione da eseguire, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-142">In the Action to be taken field, type a value.</span></span>
    * <span data-ttu-id="4c924-143">Esempio: pulire subito le perdite</span><span class="sxs-lookup"><span data-stu-id="4c924-143">Example:  Clean up spills promptly</span></span>  
19. <span data-ttu-id="4c924-144">Nel campo Giorni di assenza dal lavoro previsti, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4c924-144">In the Expected days away from work field, enter a number.</span></span>
    * <span data-ttu-id="4c924-145">Consente di immettere il numero di giorni di assenza che si prevede siano necessari per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4c924-145">Enter the number of days that the individual is expected to be away from work.</span></span>  <span data-ttu-id="4c924-146">Quando l'utente torna al lavoro, aggiornare il campo 'Giorni di assenza dal lavoro' con il numero effettivo di giorni di assenza.</span><span class="sxs-lookup"><span data-stu-id="4c924-146">Once the individual returns to work, update the 'Days away from work' field with the actual number of days away.</span></span>  
20. <span data-ttu-id="4c924-147">Espandere la sezione Costi infortunio o malattia.</span><span class="sxs-lookup"><span data-stu-id="4c924-147">Expand the Injury or illness costs section.</span></span>
21. <span data-ttu-id="4c924-148">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4c924-148">Click Add.</span></span>
22. <span data-ttu-id="4c924-149">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="4c924-149">In the Date field, enter a date.</span></span>
23. <span data-ttu-id="4c924-150">Nel campo Tipo di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-150">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-151">Esempio: terapia. È inoltre possibile immettere un importo e allegare al costo qualsiasi documentazione di supporto, ad esempio fatture o certificati medici.</span><span class="sxs-lookup"><span data-stu-id="4c924-151">Example:  Therapy    You can also enter in an amount, and attach any supporting documentation such as invoices or doctor's notes to the cost.</span></span>  
24. <span data-ttu-id="4c924-152">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4c924-152">Click Add.</span></span>
25. <span data-ttu-id="4c924-153">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="4c924-153">In the Date field, enter a date.</span></span>
26. <span data-ttu-id="4c924-154">Nel campo Tipo di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-154">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-155">Esempio: Medico</span><span class="sxs-lookup"><span data-stu-id="4c924-155">Example: Doctor</span></span>  
27. <span data-ttu-id="4c924-156">Espandere la sezione Trattamenti per infortunio o malattia.</span><span class="sxs-lookup"><span data-stu-id="4c924-156">Expand the Injury or illness treatments section.</span></span>
28. <span data-ttu-id="4c924-157">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4c924-157">Click Add.</span></span>
29. <span data-ttu-id="4c924-158">Nel campo Data trattamento immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4c924-158">In the Treatment date field, enter a date and time.</span></span>
30. <span data-ttu-id="4c924-159">Nel campo Tipo di trattamento, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-159">In the Treatment type field, enter or select a value.</span></span>
    * <span data-ttu-id="4c924-160">Esempio: Stampella</span><span class="sxs-lookup"><span data-stu-id="4c924-160">Example:  Splint</span></span>  
31. <span data-ttu-id="4c924-161">Facoltativamente, impostare la sezione Visita al Pronto soccorso su Sì.</span><span class="sxs-lookup"><span data-stu-id="4c924-161">Optionally, set the emergency room hospital visit section to Yes.</span></span>
32. <span data-ttu-id="4c924-162">Nel campo Commenti trattamento, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-162">In the Treatment comments field, type a value.</span></span>
    * <span data-ttu-id="4c924-163">Esempio: Stampella per 2 settimane</span><span class="sxs-lookup"><span data-stu-id="4c924-163">Example:  Splint for 2 weeks</span></span>  
33. <span data-ttu-id="4c924-164">Digitare un valore nel campo Nome medico.</span><span class="sxs-lookup"><span data-stu-id="4c924-164">In the Physician name field, type a value.</span></span>
    * <span data-ttu-id="4c924-165">Esempio: Dott. Anderson</span><span class="sxs-lookup"><span data-stu-id="4c924-165">Example:  Dr. Anderson</span></span>  
34. <span data-ttu-id="4c924-166">Nel campo Struttura e luogo del trattamento, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-166">In the Treatment facility and location field, type a value.</span></span>
    * <span data-ttu-id="4c924-167">Esempio: Pronto soccorso di via Olmo</span><span class="sxs-lookup"><span data-stu-id="4c924-167">Example:  Elm St. Emergency</span></span>  
35. <span data-ttu-id="4c924-168">Nel campo Dettagli trattamento, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4c924-168">In the Treatment details field, type a value.</span></span>
    * <span data-ttu-id="4c924-169">Esempio: i raggi x confermano la frattura, indossare stampella</span><span class="sxs-lookup"><span data-stu-id="4c924-169">Example:  Xray confirms fracture, wear splint</span></span>  
36. <span data-ttu-id="4c924-170">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4c924-170">Click Save.</span></span>
    * <span data-ttu-id="4c924-171">Lo stato del caso può essere aggiornato in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="4c924-171">The case status can be updated at any time.</span></span>  <span data-ttu-id="4c924-172">Impostare il caso su In corso se l'elaborazione dell'infortunio o della malattia è ancora in corso.</span><span class="sxs-lookup"><span data-stu-id="4c924-172">Set the case to in process, if the processing of the injury or illness is in process.</span></span>  <span data-ttu-id="4c924-173">Una volta chiuso l'incidente, è possibile solo aggiungere o rimuovere solo i costi, i trattamenti o le archiviazioni relative all'incidente.</span><span class="sxs-lookup"><span data-stu-id="4c924-173">Once you close the incident you can only add or remove costs, treatments or filings related to the incident.</span></span>  <span data-ttu-id="4c924-174">Per modificare altre informazioni, riaprire il caso.</span><span class="sxs-lookup"><span data-stu-id="4c924-174">To modify other information, reopen the case.</span></span>  

