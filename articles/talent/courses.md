---
title: Impostare i corsi di formazione
description: Gli amministratori e gli amministratori delle Risorse umane possono utilizzare le funzionalità dei corsi per gestire le informazioni sulla formazione offerta ai lavoratori.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: c68601b150e5c0963bfba0fa1c6c866abdd092cb
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898875"
---
# <a name="set-up-training-courses"></a><span data-ttu-id="8e342-103">Impostare i corsi di formazione</span><span class="sxs-lookup"><span data-stu-id="8e342-103">Set up training courses</span></span>

<span data-ttu-id="8e342-104">Gli amministratori e gli amministratori delle Risorse umane possono utilizzare le funzionalità dei corsi per gestire le informazioni sulla formazione offerta ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="8e342-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="8e342-105"> Prerequisiti per l'impostazione</span><span class="sxs-lookup"><span data-stu-id="8e342-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="8e342-106">Le seguenti informazioni sono obbligatorie e devono essere impostate prima di creare i corsi.</span><span class="sxs-lookup"><span data-stu-id="8e342-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="8e342-107">**Tipi di corso**</span><span class="sxs-lookup"><span data-stu-id="8e342-107">**Course types**</span></span>

<span data-ttu-id="8e342-108">Le seguenti informazioni necessarie da specificare per i corsi sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="8e342-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="8e342-109">Se queste informazioni verranno fornite per i corsi, è necessario impostarle prima di creare i record del corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="8e342-110">**Gruppi di classi**</span><span class="sxs-lookup"><span data-stu-id="8e342-110">**Classroom groups**</span></span>
-   <span data-ttu-id="8e342-111">**Gruppi del corso**</span><span class="sxs-lookup"><span data-stu-id="8e342-111">**Course groups**</span></span>
-   <span data-ttu-id="8e342-112">**Sedi del corso**</span><span class="sxs-lookup"><span data-stu-id="8e342-112">**Course locations**</span></span>
-   <span data-ttu-id="8e342-113">**Classi**</span><span class="sxs-lookup"><span data-stu-id="8e342-113">**Classrooms**</span></span>
-   <span data-ttu-id="8e342-114">**Istruttori**</span><span class="sxs-lookup"><span data-stu-id="8e342-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="8e342-115">Tipi di corso</span><span class="sxs-lookup"><span data-stu-id="8e342-115">Course types</span></span>
<span data-ttu-id="8e342-116">È possibile utilizzare i tipi di corso per classificare i corsi in base alla struttura o al contenuto del corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="8e342-117">È possibile creare i tipi di corso nella pagina **Tipi di corso**.</span><span class="sxs-lookup"><span data-stu-id="8e342-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="8e342-118">È necessario selezionare un tipo di corso quando si crea un record del corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="8e342-119">Tipo di impostazione del corso</span><span class="sxs-lookup"><span data-stu-id="8e342-119">Course setup type</span></span>
<span data-ttu-id="8e342-120">Vengono di seguito elencati i tre tipi di impostazione per i corsi.</span><span class="sxs-lookup"><span data-stu-id="8e342-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="8e342-121">I tipi di installazione determinano la struttura del corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8e342-122">Tipo di impostazione</span><span class="sxs-lookup"><span data-stu-id="8e342-122">Setup type</span></span></th>
<th><span data-ttu-id="8e342-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e342-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8e342-124"><strong>Standard</strong></span><span class="sxs-lookup"><span data-stu-id="8e342-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="8e342-125">Selezionare questo tipo per i corsi che non avranno un ordine del giorno giornaliero.</span><span class="sxs-lookup"><span data-stu-id="8e342-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="8e342-126">Quando si crea un nuovo corso sarà il tipo di impostazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="8e342-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8e342-127"><strong>Agenda</strong></span><span class="sxs-lookup"><span data-stu-id="8e342-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="8e342-128">Selezionare qesto tipo per pianificare i dettagli di ogni giorno di un corso di più giorni.</span><span class="sxs-lookup"><span data-stu-id="8e342-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8e342-129"><strong>Agenda + sessione</strong></span><span class="sxs-lookup"><span data-stu-id="8e342-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="8e342-130">Selezionare il tipo per i corsi più complessi.</span><span class="sxs-lookup"><span data-stu-id="8e342-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="8e342-131">Ad esempio, è possibile suddividere l'ordine del giorno per il corso in tracce e sessioni.</span><span class="sxs-lookup"><span data-stu-id="8e342-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="8e342-132"><strong>Traccia</strong>: le tracce sono argomenti specifici per un corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="8e342-133"><strong>Sessioni</strong>: le sessioni vengono divise in tracce e possono trattare processi o tecniche specifici attinenti a ciascuna traccia.</span><span class="sxs-lookup"><span data-stu-id="8e342-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="8e342-134">Attività del corso</span><span class="sxs-lookup"><span data-stu-id="8e342-134">Course tasks</span></span>
<span data-ttu-id="8e342-135">Per ogni corso, è possibile effettuare le seguenti attività.</span><span class="sxs-lookup"><span data-stu-id="8e342-135">For each course, you can complete the following tasks.</span></span>
- <span data-ttu-id="8e342-136">Registrare i partecipanti</span><span class="sxs-lookup"><span data-stu-id="8e342-136">Register participants</span></span>
- <span data-ttu-id="8e342-137">Specificare una scadenza per la registrazione</span><span class="sxs-lookup"><span data-stu-id="8e342-137">Specify a registration deadline</span></span>
- <span data-ttu-id="8e342-138">Definire il numero minimo e massimo di partecipanti</span><span class="sxs-lookup"><span data-stu-id="8e342-138">Define the minimum and maximum number of participants</span></span>
- <span data-ttu-id="8e342-139">Assegnare una sede del corso e una classe</span><span class="sxs-lookup"><span data-stu-id="8e342-139">Assign a course location and classroom</span></span>
- <span data-ttu-id="8e342-140">Hotel consigliati per i partecipanti al corso</span><span class="sxs-lookup"><span data-stu-id="8e342-140">Recommend hotels to course participants</span></span>
- <span data-ttu-id="8e342-141">Creare una descrizione del corso che potrà essere pubblicizzata su Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="8e342-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="8e342-142">**Nota** È possibile eliminare un corso solo se nessuno vi si è registrato.</span><span class="sxs-lookup"><span data-stu-id="8e342-142">**Note** You can delete a course only if no one has registered for it.</span></span> 

## <a name="course-statuses"></a><span data-ttu-id="8e342-143">Stati del corso</span><span class="sxs-lookup"><span data-stu-id="8e342-143">Course statuses</span></span>
<span data-ttu-id="8e342-144">Nella seguente tabella sono elencati gli stati possibili del corso e le azioni che è possibile completare quando il corso ha uno stato specifico.</span><span class="sxs-lookup"><span data-stu-id="8e342-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8e342-145">Stato</span><span class="sxs-lookup"><span data-stu-id="8e342-145">Status</span></span></th>
<th><span data-ttu-id="8e342-146">Azioni</span><span class="sxs-lookup"><span data-stu-id="8e342-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8e342-147"><strong>Creato</strong></span><span class="sxs-lookup"><span data-stu-id="8e342-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="8e342-148">Immettere e modificare le informazioni sul corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="8e342-149">Modificare lo stato del corso in <strong>Aperto</strong> in modo da poter registrare i lavoratori per il corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8e342-150"><strong>Aperto</strong></span><span class="sxs-lookup"><span data-stu-id="8e342-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="8e342-151">Registrare i partecipanti per il corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="8e342-152">Rimuovere i partecipanti dal corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="8e342-153">Confermare i partecipanti per il corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="8e342-154">Modificare lo stato del corso su<strong> Chiuso</strong> o <strong>Annullato</strong>.</span><span class="sxs-lookup"><span data-stu-id="8e342-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="8e342-155">Pianificare i questionari per i partecipanti a cui è assegnato lo stato <strong>Confermato</strong>.</span><span class="sxs-lookup"><span data-stu-id="8e342-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8e342-156"><strong>Chiuso</strong></span><span class="sxs-lookup"><span data-stu-id="8e342-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="8e342-157">È possibile riaprire il corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8e342-158"><strong>Annullato</strong></span><span class="sxs-lookup"><span data-stu-id="8e342-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="8e342-159">È possibile riaprire il corso.</span><span class="sxs-lookup"><span data-stu-id="8e342-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="8e342-160">Partecipanti al corso</span><span class="sxs-lookup"><span data-stu-id="8e342-160">Course participants</span></span>
<span data-ttu-id="8e342-161">I partecipanti a un corso sono i dipendenti che prendono parte a un evento o a un corso di formazione.</span><span class="sxs-lookup"><span data-stu-id="8e342-161">Course participants are workers who participate in a training course or event.</span></span> <span data-ttu-id="8e342-162">È possibile registrare solo i partecipanti ai corsi aperti.</span><span class="sxs-lookup"><span data-stu-id="8e342-162">You can only register participants for open courses.</span></span> <span data-ttu-id="8e342-163">Il numero minimo e massimo di partecipanti che è possibile registrare per un corso viene definito nella scheda dettaglio **Generale** sulla pagina **Corsi**.</span><span class="sxs-lookup"><span data-stu-id="8e342-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="8e342-164">Flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8e342-164">Workflow</span></span>
--------

<span data-ttu-id="8e342-165">I dipendenti registrati per un corso tramite la pagina **Dipendente self-service** possono avere la registrazione instradata tramite il flusso di lavoro per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="8e342-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span> <span data-ttu-id="8e342-166">Un flusso di lavoro può essere assegnato a un corso nella Scheda dettaglio **Generale** della pagina **Corsi**.</span><span class="sxs-lookup"><span data-stu-id="8e342-166">You can assign a workflow to a course on the **General** FastTab on the **Courses** page.</span></span>





