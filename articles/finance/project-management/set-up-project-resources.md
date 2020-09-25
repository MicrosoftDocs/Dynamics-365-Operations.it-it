---
title: Impostare le risorse del progetto
description: Questo argomento fornisce informazioni sulla configurazione o sulla richiesta delle risorse di progetto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760588"
---
# <a name="set-up-project-resources"></a><span data-ttu-id="74c41-103">Impostare le risorse del progetto</span><span class="sxs-lookup"><span data-stu-id="74c41-103">Set up project resources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74c41-104">È necessario impostare un calendario e associarlo a un dipendente o un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="74c41-104">You must set up a calendar and associate it with an employee or a worker.</span></span> <span data-ttu-id="74c41-105">Il calendario viene utilizzato per programmare il progetto e l'orario di lavoro delle risorse per esso prenotate.</span><span class="sxs-lookup"><span data-stu-id="74c41-105">The calendar is used to schedule the project and the working time of the resources that are reserved for the project.</span></span> <span data-ttu-id="74c41-106">Durante l'impostazione del calendario, i manager di progetto possono eseguire il livellamento delle risorse nell'ambito della relativa ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="74c41-106">During calendar setup, project managers can do resource leveling as part of resource optimization.</span></span> <span data-ttu-id="74c41-107">In base alla programmazione del calendario, è possibile porre restrizioni sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="74c41-107">Based on the calendar schedule, restrictions can be put on resources.</span></span> <span data-ttu-id="74c41-108">È possibile impostare un calendario nella pagina **calendari**.</span><span class="sxs-lookup"><span data-stu-id="74c41-108">You can set up a calendar on the **Calendars** page.</span></span>

<span data-ttu-id="74c41-109">Quando si imposta un lavoratore come risorsa di progetto, è possibile selezionare uno dei lavoratori che lavorano nella società per il quale si desidera impostare le risorse.</span><span class="sxs-lookup"><span data-stu-id="74c41-109">When you set up a worker as a project resource, you can select from workers who work in the company that you're setting up resources for.</span></span> <span data-ttu-id="74c41-110">In alternativa, è possibile selezionare i lavoratori da altre società della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="74c41-110">Alternatively, you can select workers from other companies in your organization.</span></span> <span data-ttu-id="74c41-111">Questi lavoratori sono noti come risorse interaziendali.</span><span class="sxs-lookup"><span data-stu-id="74c41-111">These workers are known as intercompany resources.</span></span>

<span data-ttu-id="74c41-112">Nelle procedure indicate di seguito viene descritto come impostare un lavoratore come risorsa di progetto nella società e come impostare una risorsa di progetto interaziendale.</span><span class="sxs-lookup"><span data-stu-id="74c41-112">The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.</span></span>

## <a name="set-up-a-worker-as-a-project-resource"></a><span data-ttu-id="74c41-113">Impostare un lavoratore come risorsa del progetto</span><span class="sxs-lookup"><span data-stu-id="74c41-113">Set up a worker as a project resource</span></span>

1. <span data-ttu-id="74c41-114">Nella pagina **Lavoratori**, in **Lavoratori** selezionare il lavoratore che si intende aggiungere come risorsa del progetto e aprire il relativo record.</span><span class="sxs-lookup"><span data-stu-id="74c41-114">On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.</span></span>
2. <span data-ttu-id="74c41-115">Nel Riquadro azioni, selezionare **Progetto** &gt; **Impostazioni** &gt; **Impostazione progetto**.</span><span class="sxs-lookup"><span data-stu-id="74c41-115">On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.</span></span>
3. <span data-ttu-id="74c41-116">Selezionare un calendario, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="74c41-116">Select a calendar, and then close the page.</span></span>

<span data-ttu-id="74c41-117">È anche possibile specificare progetti predefiniti per una risorsa come tipo di pre-assegnazione.</span><span class="sxs-lookup"><span data-stu-id="74c41-117">You can also specify default projects for a resource as a type of pre-assignment.</span></span> <span data-ttu-id="74c41-118">Le pre-assegnazioni possono essere utilizzate quando il manager di risorse o progetto sa in anticipo su quali progetti la risorsa lavorerà.</span><span class="sxs-lookup"><span data-stu-id="74c41-118">Pre-assignments can be used when the resource manager or project manager knows which projects the resource will be working on in advance.</span></span> <span data-ttu-id="74c41-119">Le pre-assegnazioni possono anche essere basate sulla richiesta di uno sponsor o di un cliente del progetto.</span><span class="sxs-lookup"><span data-stu-id="74c41-119">Pre-assignments can also be based on the request of a project sponsor or customer.</span></span> <span data-ttu-id="74c41-120">Per pre-assegnare un progetto, nella pagina **Assegna progetti**, scheda **Progetti**, elenco **Progetti rimanenti**, selezionare il progetto appropriato.</span><span class="sxs-lookup"><span data-stu-id="74c41-120">To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.</span></span>

## <a name="set-up-an-intercompany-resource"></a><span data-ttu-id="74c41-121">Impostare una risorsa interaziendale</span><span class="sxs-lookup"><span data-stu-id="74c41-121">Set up an intercompany resource</span></span>

<span data-ttu-id="74c41-122">Quando si imposta un lavoratore come risorsa interaziendale, è necessario completare l'impostazione nella società che concede in prestito la risorsa e nella società che la prende in prestito.</span><span class="sxs-lookup"><span data-stu-id="74c41-122">When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.</span></span>

### <a name="in-the-lending-company"></a><span data-ttu-id="74c41-123">Nella società che concede in prestito la risorsa</span><span class="sxs-lookup"><span data-stu-id="74c41-123">In the lending company</span></span>

1. <span data-ttu-id="74c41-124">In Finance, verificare che la società di concessione sia selezionata e quindi completare la procedura nella sezione precedente, "Impostare un lavoratore come risorsa del progetto".</span><span class="sxs-lookup"><span data-stu-id="74c41-124">In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."</span></span>
2. <span data-ttu-id="74c41-125">Nella pagina **Contabilità interaziendale**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="74c41-125">On the **Intercompany accounting** page, select **New**.</span></span>
3. <span data-ttu-id="74c41-126">Nel campo **ID persona giuridica** selezionare la società di concessione.</span><span class="sxs-lookup"><span data-stu-id="74c41-126">In the **Legal entity ID** field, select the lending company.</span></span> <span data-ttu-id="74c41-127">Completare i campi rimanenti come appropriati e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="74c41-127">Fill in the remaining fields as appropriate, and then select **Save**.</span></span>
4. <span data-ttu-id="74c41-128">Nella pagina **Prezzo di trasferimento**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="74c41-128">On the **Transfer price** page, select **New**.</span></span>
5. <span data-ttu-id="74c41-129">Nel campo **Persona giuridica richiedente** selezionare la società appropriata.</span><span class="sxs-lookup"><span data-stu-id="74c41-129">In the **Borrowing legal entity** field, select the appropriate company.</span></span>
6. <span data-ttu-id="74c41-130">Per concedere alla società richiedente solo la risorsa creata all'inizio di questa sezione nel campo **Risorsa**, selezionare il nome della risorsa creata.</span><span class="sxs-lookup"><span data-stu-id="74c41-130">To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created.</span></span> <span data-ttu-id="74c41-131">Per redenre disponibili tutte le risorse nella società di concessione alla società richiedente, lasciare vuoto il campo **Risorsa**.</span><span class="sxs-lookup"><span data-stu-id="74c41-131">To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.</span></span>
7. <span data-ttu-id="74c41-132">Nella pagina **Parametri Gestione progetti e contabilità**, nella scheda **Interaziendale**, impostare il campo **Abilita programmazione risorse interaziendale e fogli presenze** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="74c41-132">On the **Project management and accounting parameters** page, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.</span></span>

### <a name="in-the-borrowing-company"></a><span data-ttu-id="74c41-133">Nella società che prende in prestito la risorsa</span><span class="sxs-lookup"><span data-stu-id="74c41-133">In the borrowing company</span></span>

- <span data-ttu-id="74c41-134">Nella pagina **Elenco risorse**, nel filtro di ricerca, immettere il nome della risorsa creata nella procedura precedente per la società di concessione per verificare che il nome sia incluso nell'elenco di risorse per la società di prestito.</span><span class="sxs-lookup"><span data-stu-id="74c41-134">On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.</span></span>

## <a name="request-project-resources"></a><span data-ttu-id="74c41-135">Richiedere risorse di progetto</span><span class="sxs-lookup"><span data-stu-id="74c41-135">Request project resources</span></span>
<span data-ttu-id="74c41-136">La funzionalità per la programmazione di risorse di progetto consente solo ai manager di risorse di distribuire risorse con personale per gli impegni o progetti.</span><span class="sxs-lookup"><span data-stu-id="74c41-136">The functionality for project resource scheduling only lets resource managers distribute staffed resources on engagements or projects.</span></span> <span data-ttu-id="74c41-137">Per attivare questa funzionalità, è necessario completare le seguenti attività o verificare che siano state completate:</span><span class="sxs-lookup"><span data-stu-id="74c41-137">To enable this functionality, complete the following tasks, or verify that they have been completed:</span></span>

- <span data-ttu-id="74c41-138">Consente di impostare sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="74c41-138">Set up number sequences.</span></span>
- <span data-ttu-id="74c41-139">Impostare i flussi di lavoro di Gestione progetti e contabilità.</span><span class="sxs-lookup"><span data-stu-id="74c41-139">Set up project management and accounting workflows.</span></span>
- <span data-ttu-id="74c41-140">Abilitare i flussi di lavoro della richiesta di risorse.</span><span class="sxs-lookup"><span data-stu-id="74c41-140">Enable resource request workflows.</span></span>

<span data-ttu-id="74c41-141">Una volta completate le attività precedenti, è possibile completare le seguenti attività come necessario:</span><span class="sxs-lookup"><span data-stu-id="74c41-141">After the preceding tasks have been completed, you can complete the following tasks as you require:</span></span>

- <span data-ttu-id="74c41-142">Creare una richiesta di risorse da una risorsa con personale e prenotazione preliminare.</span><span class="sxs-lookup"><span data-stu-id="74c41-142">Create a resource request from a soft-booked staffed resource.</span></span>
- <span data-ttu-id="74c41-143">Monitorare le richieste risorsa.</span><span class="sxs-lookup"><span data-stu-id="74c41-143">Monitor resource requests.</span></span>
- <span data-ttu-id="74c41-144">Completare le richieste risorsa.</span><span class="sxs-lookup"><span data-stu-id="74c41-144">Fulfill resource requests.</span></span>
- <span data-ttu-id="74c41-145">Richiedere una risorsa con personale da un WBS.</span><span class="sxs-lookup"><span data-stu-id="74c41-145">Request a staffed resource from a WBS.</span></span>
- <span data-ttu-id="74c41-146">Prenotare le risorse per un progetto senza avere una richiesta per una risorsa con personale.</span><span class="sxs-lookup"><span data-stu-id="74c41-146">Book resources to a project without having a request for a staffed resource.</span></span>
