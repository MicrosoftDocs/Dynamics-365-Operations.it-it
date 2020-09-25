---
title: Crea un nuovo progetto
description: Questo argomento fornisce informazioni su come creare un nuovo progetto.
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
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760583"
---
# <a name="create-a-new-project"></a><span data-ttu-id="36a15-103">Crea un nuovo progetto</span><span class="sxs-lookup"><span data-stu-id="36a15-103">Create a new project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36a15-104">Completare i passaggi seguenti per creare un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-104">Complete the following steps to create a new project.</span></span>

1. <span data-ttu-id="36a15-105">Nella pagina **Gestione progetti** selezionare **Nuovo progetto**, quindi immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="36a15-105">On the **Project management** page, select **New project**, and enter the following values:</span></span>

    - <span data-ttu-id="36a15-106">**Tipo di progetto:** Tempistica e materiali</span><span class="sxs-lookup"><span data-stu-id="36a15-106">**Project type:** Time and material</span></span>
    - <span data-ttu-id="36a15-107">**Nome progetto:** Fase 2 di aggiornamento di XYZ</span><span class="sxs-lookup"><span data-stu-id="36a15-107">**Project name:** XYZ Upgrade Phase 2</span></span>
    - <span data-ttu-id="36a15-108">**Gruppo di progetti:** TM\_WIP</span><span class="sxs-lookup"><span data-stu-id="36a15-108">**Project group:** TM\_WIP</span></span>
    - <span data-ttu-id="36a15-109">**ID contratto progetto:** 00000002</span><span class="sxs-lookup"><span data-stu-id="36a15-109">**Project contract ID:** 00000002</span></span>

2. <span data-ttu-id="36a15-110">Selezionare **Crea progetto**.</span><span class="sxs-lookup"><span data-stu-id="36a15-110">Select **Create project**.</span></span>

## <a name="assign-a-resource-to-a-project"></a><span data-ttu-id="36a15-111">Assegnare una risorsa a un progetto</span><span class="sxs-lookup"><span data-stu-id="36a15-111">Assign a resource to a project</span></span>

1. <span data-ttu-id="36a15-112">Nella pagina **Lavoratori**, nell'elenco **Lavoratori**, selezionare il record per il lavoratore di cui sono state impostate le competenze e aprire il relativo record.</span><span class="sxs-lookup"><span data-stu-id="36a15-112">On the **Workers** page, in the **Workers** list, select the record for the worker that you previously set up competencies for, and open the worker record.</span></span>
2. <span data-ttu-id="36a15-113">Nel riquadro azioni, scheda **Progetto**, gruppo **Impostazione**, selezionare **Assegna progetti**.</span><span class="sxs-lookup"><span data-stu-id="36a15-113">On the Action Pane, on the **Project** tab, in the **Setup** group, select **Assign projects**.</span></span>
3. <span data-ttu-id="36a15-114">Nella pagina **Assegnazioni progetto convalida risorse**, nella scheda **Progetti**, nel campo **Aggiungere il progetto ai progetti selezionati**, filtrare in base al progetto **Fase 2 di aggiornamento di XYZ**.</span><span class="sxs-lookup"><span data-stu-id="36a15-114">On the **Resource validation project assignments** page, on the **Projects** tab, in the **Add the project to selected projects** field, filter on the **XYZ Upgrade Phase 2** project.</span></span>
4. <span data-ttu-id="36a15-115">Nel riquadro **Progetti rimanenti** selezionare un progetto e fare clic sul pulsante freccia per aggiungerlo al riquadro **Progetti selezionati**.</span><span class="sxs-lookup"><span data-stu-id="36a15-115">In the **Remaining projects** pane, select a project, and then select the arrow button to add it to the **Selected projects** pane.</span></span>

<span data-ttu-id="36a15-116">Se necessario, è anche possibile assegnare categorie per una risorsa.</span><span class="sxs-lookup"><span data-stu-id="36a15-116">You can also assign categories for a resource as you require.</span></span> <span data-ttu-id="36a15-117">Il tipo di categoria è **Costo** o **Ricavi**.</span><span class="sxs-lookup"><span data-stu-id="36a15-117">The category type is either **Cost** or **Revenue**.</span></span> <span data-ttu-id="36a15-118">Il tipo di categoria viene determinato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36a15-118">The category type is determined by your organization.</span></span> <span data-ttu-id="36a15-119">Se per una risorsa non vi sono categorie assegnate, Finance cerca la categoria predefinita nei prezzi orari per costi e ricavi.</span><span class="sxs-lookup"><span data-stu-id="36a15-119">If no categories are assigned for a resource, Finance looks up the default category on hour prices for cost and revenue.</span></span>

## <a name="set-up-project-resource-and-role-characteristics"></a><span data-ttu-id="36a15-120">Impostare le caratteristiche dei ruoli e delle risorse del progetto</span><span class="sxs-lookup"><span data-stu-id="36a15-120">Set up project resource and role characteristics</span></span>

<span data-ttu-id="36a15-121">Un manager di progetto può utilizzare la funzionalità di assegnazione delle risorse al progetto per creare i ruoli necessari per il progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-121">A project manager can use the project resourcing functionality to create the roles that are required for the project.</span></span> <span data-ttu-id="36a15-122">I ruoli possono essere utilizzati se le risorse confermate sono ancora sconosciute durante la prenotazione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="36a15-122">Roles can be used if confirmed resources are still unknown when resources are being reserved.</span></span> <span data-ttu-id="36a15-123">I ruoli possono essere utilizzare per prenotare temporaneamente le risorse come pianificate, in modo da poter continuare le fasi di pianificazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-123">Roles can be temporarily reserved as planned resources, so that you can continue the project planning stages.</span></span>

<span data-ttu-id="36a15-124">[![Esempio di un ruolo](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span><span class="sxs-lookup"><span data-stu-id="36a15-124">[![Example of a role](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span></span> 

<span data-ttu-id="36a15-125">**Scenario**: Contoso è stato assunto per completare un progetto di tempistica e materiali con uno statuto di progetto approvato.</span><span class="sxs-lookup"><span data-stu-id="36a15-125">**Scenario:** Contoso was hired to complete a Time and material project that has an approved project charter.</span></span> <span data-ttu-id="36a15-126">Il secondo manager di progetto sta ancora completando l'ambito del progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-126">The junior project manager is still completing the scope of the project.</span></span> <span data-ttu-id="36a15-127">Il responsabile delle risorse sta al momento identificando le risorse specifiche che verranno prenotare per il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-127">The resource manager is currently identifying specific resources that will be reserved to work on the new project.</span></span> <span data-ttu-id="36a15-128">A causa della natura fondamentale del progetto, uno dei ruoli richiesti dalla sponsor di progetto è Manager di progetto principale.</span><span class="sxs-lookup"><span data-stu-id="36a15-128">Because of the critical nature of the project, the project sponsor requested Senior project manager as one of the roles.</span></span> <span data-ttu-id="36a15-129">Il responsabile delle risorse deve acquisire la nuova risorsa e definisce il ruolo del sistema, qualora il secondo manager di progetto minore richieda le informazioni sulle risorse durante la pianificazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-129">The resource manager must acquire the new resource and define the role in the system in case the junior project manager requires the resource information during project planning.</span></span>

<span data-ttu-id="36a15-130">La procedura seguente mostra come il manager di risorse può impostare il ruolo di manager di progetto principale e associare le caratteristiche delle risorse.</span><span class="sxs-lookup"><span data-stu-id="36a15-130">The following steps show how the resource manager can set up the Senior project manager role and associate resource characteristics with it.</span></span> <span data-ttu-id="36a15-131">Successivamente, il ruolo può essere utilizzato per cercare le risorse disponibili che corrispondono alle competenze delle risorse richieste.</span><span class="sxs-lookup"><span data-stu-id="36a15-131">Later, the role can be used to search for available resources that match the required resource competencies.</span></span>

1. <span data-ttu-id="36a15-132">Nella pagina **Impostazione ruoli** selezionare **Nuovo progetto**, quindi immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="36a15-132">On the **Setup roles** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="36a15-133">**ID ruolo:** Manager di progetto principale</span><span class="sxs-lookup"><span data-stu-id="36a15-133">**Role ID:** Senior Project Manager</span></span>
    - <span data-ttu-id="36a15-134">**Descrizione:** Manager di progetto principale</span><span class="sxs-lookup"><span data-stu-id="36a15-134">**Description:** Senior Project Manager</span></span>

2. <span data-ttu-id="36a15-135">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="36a15-135">Select **Create**.</span></span>
3. <span data-ttu-id="36a15-136">Selezionare il ruolo **Manager di progetto principale** e quindi **Configurare le caratteristiche**.</span><span class="sxs-lookup"><span data-stu-id="36a15-136">Select the **Senior Project Manager** role, and then select **Configure characteristics**.</span></span>
4. <span data-ttu-id="36a15-137">Nel campo **Tipo caratteristiche** selezionare **Competenza**.</span><span class="sxs-lookup"><span data-stu-id="36a15-137">In the **Characteristics type** field, select **Skill**.</span></span>
5. <span data-ttu-id="36a15-138">Nel campo **Caratteristiche disponibili** immettere la competenza che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="36a15-138">In the **Available characteristics** field, enter the skill to search for.</span></span>
6. <span data-ttu-id="36a15-139">Nel campo **Tipo di caratteristica** selezionare **Certificato**.</span><span class="sxs-lookup"><span data-stu-id="36a15-139">In the **Characteristic type** field, select **Certificate**.</span></span>
7. <span data-ttu-id="36a15-140">Nel campo **Caratteristiche disponibili** immettere il tipo di certificato che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="36a15-140">In the **Available characteristics** field, enter the certificate type to search for.</span></span>

## <a name="assign-a-project-resource-to-a-project"></a><span data-ttu-id="36a15-141">Assegnare una risorsa a un progetto</span><span class="sxs-lookup"><span data-stu-id="36a15-141">Assign a project resource to a project</span></span>

1. <span data-ttu-id="36a15-142">Nella pagina **Tutti i progetti**, selezionare il progetto **Fase 2 di aggiornamento di XYZ**.</span><span class="sxs-lookup"><span data-stu-id="36a15-142">On the **All projects** page, select the **XYZ Upgrade Phase 2** project.</span></span>
2. <span data-ttu-id="36a15-143">Nella scheda **Team progetto e programmazione**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="36a15-143">On the **Project team and scheduling** tab, select **Add**.</span></span>
3. <span data-ttu-id="36a15-144">Nel campo **Ruolo** selezionare **Membro del team**.</span><span class="sxs-lookup"><span data-stu-id="36a15-144">In the **Role** field, select **Team member**.</span></span>
4. <span data-ttu-id="36a15-145">Selezionare **Prenota da calendario**.</span><span class="sxs-lookup"><span data-stu-id="36a15-145">Select **Book from calendar**.</span></span>
5. <span data-ttu-id="36a15-146">Nella pagina **Disponibilità risorse** selezionare **Impostazioni visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="36a15-146">On the **Resource availability** page, select **View settings**.</span></span>
6. <span data-ttu-id="36a15-147">Nella pagina **Modifica impostazioni visualizzazione** immettere i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="36a15-147">On the **Adjust view settings** page, enter the following values:</span></span>

    - <span data-ttu-id="36a15-148">**Formato per la visualizzazione dell'intervallo di date:** Giorno</span><span class="sxs-lookup"><span data-stu-id="36a15-148">**Format for date range view:** Day</span></span>
    - <span data-ttu-id="36a15-149">**Visualizza descrizioni disponibili:** Sì</span><span class="sxs-lookup"><span data-stu-id="36a15-149">**Display availability descriptions:** Yes</span></span>
    - <span data-ttu-id="36a15-150">**Visualizza capacità rimanente:** Sì</span><span class="sxs-lookup"><span data-stu-id="36a15-150">**Display remaining capacity:** Yes</span></span>

7. <span data-ttu-id="36a15-151">Nell'elenco di risorse, selezionare una risorsa.</span><span class="sxs-lookup"><span data-stu-id="36a15-151">In the list of resources, select a resource.</span></span>
8. <span data-ttu-id="36a15-152">Selezionare **Prenotazione definitiva** e **Intera capacità**.</span><span class="sxs-lookup"><span data-stu-id="36a15-152">Select **Hard book** and **Full capacity**.</span></span>

## <a name="assign-a-resource-to-a-default-role"></a><span data-ttu-id="36a15-153">Assegnare una risorsa a un ruolo predefinito</span><span class="sxs-lookup"><span data-stu-id="36a15-153">Assign a resource to a default role</span></span>

<span data-ttu-id="36a15-154">Per aiutare i manager di progetto o risorse, è possibile analizzare ulteriormente le risorse prenotabili per un progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-154">To help project or resource managers can drill down further on the resources that can be reserved for a project.</span></span> <span data-ttu-id="36a15-155">È possibile associare un ruolo predefinito a una risorsa esistente o una risorsa appena acquisita.</span><span class="sxs-lookup"><span data-stu-id="36a15-155">You can associate a default role with an existing resource or a newly acquired resource.</span></span> <span data-ttu-id="36a15-156">Ad esempio, quando Daniel è stato assunto, aveva l'esperienza e le competenze per ricoprire il ruolo di business analyst.</span><span class="sxs-lookup"><span data-stu-id="36a15-156">For example, when Daniel was hired, he had the experience and skills to fill the Business analyst role.</span></span> <span data-ttu-id="36a15-157">Il responsabile delle risorse ha assegnato questo ruolo come ruolo standard a Daniel.</span><span class="sxs-lookup"><span data-stu-id="36a15-157">The resource manager assigned this role as Daniel's default role.</span></span> <span data-ttu-id="36a15-158">Di conseguenza, il responsabile delle risorse ha aggiunto Daniel a un gruppo di business analyst che sono disponibili per lavorare ai progetti.</span><span class="sxs-lookup"><span data-stu-id="36a15-158">Therefore, the resource manager added Daniel to a pool of business analysts who are available to work on projects.</span></span>

<span data-ttu-id="36a15-159">Durante la prenotazione delle risorse, i manager di progetto possono filtrare le risorse disponibili a lavorare sui progetti.</span><span class="sxs-lookup"><span data-stu-id="36a15-159">During resource reservation, project managers can filter the role resources that are available to work on projects.</span></span> <span data-ttu-id="36a15-160">Possono utilizzare queste informazioni come criterio quando eseguono analisi decisionali basate su più criteri per soddisfare la capacità delle risorse.</span><span class="sxs-lookup"><span data-stu-id="36a15-160">They can use this information as one criterion when they perform multi-criteria decision analysis during resource fulfillment.</span></span> <span data-ttu-id="36a15-161">Possono anche aggiungere altre caratteristiche di risorse al filtro per cercare le risorse con competenze, istruzione ed esperienze specifiche per un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-161">They can also add other resource characteristics to the filter to search for resources that have specific skills, education, and experience for a given project.</span></span>

<span data-ttu-id="36a15-162">**Scenario:** è stato avviato un progetto approvato e il ruolo di manager di progetto principale è stato prenotato come risorsa pianificata durante la fase di pianificazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="36a15-162">**Scenario:** An approved project has started, and the Senior project manager role was reserved as a planned resource during the project planning stage.</span></span> <span data-ttu-id="36a15-163">Il manager delle risorse ha ora acquisito una risorsa per ricoprire il ruolo di manager di progetto principale.</span><span class="sxs-lookup"><span data-stu-id="36a15-163">The resource manager has now acquired a resource to fulfill the Senior project manager role.</span></span>

1. <span data-ttu-id="36a15-164">Nella pagina **Elenco risorse** selezionare **Daniel Goldschmidt**.</span><span class="sxs-lookup"><span data-stu-id="36a15-164">On the **Resources list** page, select **Daniel Goldschmidt**.</span></span>
2. <span data-ttu-id="36a15-165">Nella pagina **Ruolo risorsa** selezionare **Nuovo**, quindi immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="36a15-165">On the **Resource role** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="36a15-166">**Validità:** immettere la data corrente.</span><span class="sxs-lookup"><span data-stu-id="36a15-166">**Effective:** Enter the current date.</span></span>
    - <span data-ttu-id="36a15-167">**Scadenza:** immettere **Mai**.</span><span class="sxs-lookup"><span data-stu-id="36a15-167">**Expiration:** Enter **Never**.</span></span>
    - <span data-ttu-id="36a15-168">**Ruolo:** immettere **Manager di progetto principale**</span><span class="sxs-lookup"><span data-stu-id="36a15-168">**Role:** Enter **Senior Project Manager**.</span></span>

3. <span data-ttu-id="36a15-169">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="36a15-169">Select **Save**, and then close the page.</span></span>
4. <span data-ttu-id="36a15-170">Nella scheda **Competenze** aggiungere la competenza **PMP** e il certificato **PMP**.</span><span class="sxs-lookup"><span data-stu-id="36a15-170">On the **Competencies** tab, add the **ProjectMgmt** skill and the **PMP** certificate.</span></span>
