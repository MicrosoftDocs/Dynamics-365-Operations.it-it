---
title: Creare piani di benefit per i lavoratori
description: È possibile creare piani di benefit per i lavoratori in Microsoft Dynamics 365 Human Resources per selezionare piani di benefit per i dipendenti e confermare la selezione dei piani di benefit.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanEmployee, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5ac357bbef4bf84b9eaf153834bc7a609240c45e
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464228"
---
# <a name="create-worker-benefit-plans"></a><span data-ttu-id="986f0-103">Creare piani di benefit per i lavoratori</span><span class="sxs-lookup"><span data-stu-id="986f0-103">Create worker benefit plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="986f0-104">È possibile creare piani di benefit per i lavoratori in Microsoft Dynamics 365 Human Resources per selezionare piani di benefit per i dipendenti e confermare la selezione dei piani di benefit.</span><span class="sxs-lookup"><span data-stu-id="986f0-104">You can create worker benefit plans in Microsoft Dynamics 365 Human Resources to select benefit plans for employees and to confirm benefit plan selections.</span></span> <span data-ttu-id="986f0-105">In genere, i dipendenti selezionano personalmente i piani di benefit utilizzando Dipendente self-service e quindi un amministratore dei benefit conferma le selezioni.</span><span class="sxs-lookup"><span data-stu-id="986f0-105">Typically, employees select benefit plans themselves by using Employee self service, and then a benefits administrator confirms the selections.</span></span> 

1. <span data-ttu-id="986f0-106">Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="986f0-106">In the **Benefits management** workspace, under **Plans**, select **Worker benefit plans**.</span></span>

2. <span data-ttu-id="986f0-107">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="986f0-107">Select **New**.</span></span>

3. <span data-ttu-id="986f0-108">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="986f0-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="986f0-109">Campo</span><span class="sxs-lookup"><span data-stu-id="986f0-109">Field</span></span> | <span data-ttu-id="986f0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="986f0-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="986f0-111">Periodo</span><span class="sxs-lookup"><span data-stu-id="986f0-111">Period</span></span> | <span data-ttu-id="986f0-112">Specifica un periodo di benefit da utilizzare per filtrare i piani nella scheda dettaglio Piani. Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-112">Specifies a benefits period to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> <span data-ttu-id="986f0-113">Ad esempio, selezionare un periodo creato denominato 2015 per confermare tutte le selezioni di iscrizione ai benefit per il 2015.</span><span class="sxs-lookup"><span data-stu-id="986f0-113">For example, select a period you created called 2015 to confirm all the benefit enrollment selections for 2015.</span></span> |
   | <span data-ttu-id="986f0-114">Lavoro</span><span class="sxs-lookup"><span data-stu-id="986f0-114">Worker</span></span> | <span data-ttu-id="986f0-115">Specifica un lavoratore da utilizzare per filtrare i piani nella scheda dettaglio Piani. Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-115">Specifies a worker to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="986f0-116">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="986f0-116">Legal entity</span></span> | <span data-ttu-id="986f0-117">Specifica una persona giuridica da utilizzare per filtrare i piani nella scheda dettaglio Piani. Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-117">Specifies a legal entity to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="986f0-118">Opzione di copertura</span><span class="sxs-lookup"><span data-stu-id="986f0-118">Coverage option</span></span> | <span data-ttu-id="986f0-119">Specifica un'opzione di copertura da utilizzare per filtrare i piani nella scheda dettaglio Piani. Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-119">Specifies a coverage option to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="986f0-120">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="986f0-120">Default</span></span> | <span data-ttu-id="986f0-121">Filtra i piani di benefit a seconda che sia o meno un piano predefinito.</span><span class="sxs-lookup"><span data-stu-id="986f0-121">Filters the benefit plans based on whether they are a default plan.</span></span> <span data-ttu-id="986f0-122">Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-122">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="986f0-123">Stato</span><span class="sxs-lookup"><span data-stu-id="986f0-123">Status</span></span> | <span data-ttu-id="986f0-124">Filtra i piani di benefit in base al relativo stato.</span><span class="sxs-lookup"><span data-stu-id="986f0-124">Filters benefit plans based on their status.</span></span> <span data-ttu-id="986f0-125">Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-125">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="986f0-126">Conferma</span><span class="sxs-lookup"><span data-stu-id="986f0-126">Confirmation</span></span> | <span data-ttu-id="986f0-127">Specifica lo stato di conferma da utilizzare per filtrare i piani nella scheda dettaglio Piani. Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-127">Specifies the confirmation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="986f0-128">Annullamento</span><span class="sxs-lookup"><span data-stu-id="986f0-128">Cancellation</span></span> | <span data-ttu-id="986f0-129">Specifica lo stato di annullamento da utilizzare per filtrare i piani nella scheda dettaglio Piani. Filtrare i piani per selezionare un sottoinsieme di tutti i record di piani in modo da poter confermare il sottoinsieme.</span><span class="sxs-lookup"><span data-stu-id="986f0-129">Specifies the cancellation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="986f0-130">Filtro con data di validità</span><span class="sxs-lookup"><span data-stu-id="986f0-130">Effective date filter</span></span> | <span data-ttu-id="986f0-131">Filtra i piani a seconda che siano scaduti, attivi o saranno attivi in futuro.</span><span class="sxs-lookup"><span data-stu-id="986f0-131">Filters the plans based on whether they’re expired, active, or will be active in the future.</span></span> <span data-ttu-id="986f0-132">Selezionare le caselle di controllo che corrispondono ai piani che si desidera visualizzare nella scheda dettaglio Piani.</span><span class="sxs-lookup"><span data-stu-id="986f0-132">Select the check boxes that correspond to the plans you want to see in the Plans fast tab.</span></span> |
   | <span data-ttu-id="986f0-133">Piani</span><span class="sxs-lookup"><span data-stu-id="986f0-133">Plans</span></span> | <span data-ttu-id="986f0-134">La scheda dettagli Piani contiene i piani che soddisfano i criteri di filtro specificati.</span><span class="sxs-lookup"><span data-stu-id="986f0-134">The Plans fast tab contains the plans that meet the filter criteria you specified.</span></span> <span data-ttu-id="986f0-135">Le opzioni di configurazione pertinenti impostate dal personale delle risorse umane e le selezioni di iscrizione scelte dai dipendenti sono incluse in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="986f0-135">The relevant configuration options that were set by HR staff and the enrollment selections that were chosen by employees are included on each line.</span></span> <span data-ttu-id="986f0-136">Il campo Qualificato specifica se esiste un conflitto di convalida con la selezione del piano.</span><span class="sxs-lookup"><span data-stu-id="986f0-136">The Qualified field specifies whether there is a validation conflict with the plan selection.</span></span> |

4. <span data-ttu-id="986f0-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="986f0-137">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]