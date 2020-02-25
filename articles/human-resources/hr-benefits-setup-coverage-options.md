---
title: Creare opzioni di copertura
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009488"
---
# <a name="create-coverage-options"></a><span data-ttu-id="fd88d-102">Creare opzioni di copertura</span><span class="sxs-lookup"><span data-stu-id="fd88d-102">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="fd88d-103">Le opzioni di copertura in Microsoft Dynamics 365 Human Resources sono livelli di copertura per un partecipante a un piano o programma di benefit, come ad esempio Solo dipendente per un piano sanitario oppure 2x stipendio per un piano di assicurazione sulla vita.</span><span class="sxs-lookup"><span data-stu-id="fd88d-103">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="fd88d-104">Una volta definite, le opzioni di copertura di benefit sono riutilizzabili e ogni opzione può essere associata a uno o più piani.</span><span class="sxs-lookup"><span data-stu-id="fd88d-104">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="fd88d-105">Dopo aver definito le opzioni di copertura, associarle a un tipo di piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="fd88d-105">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="fd88d-106">Il tipo di piano viene quindi associato a un piano o programma di benefit.</span><span class="sxs-lookup"><span data-stu-id="fd88d-106">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="fd88d-107">Le opzioni di copertura associate a un tipo di piano saranno disponibili per tutti i piani creati con quel tipo di piano.</span><span class="sxs-lookup"><span data-stu-id="fd88d-107">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="fd88d-108">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di copertura**.</span><span class="sxs-lookup"><span data-stu-id="fd88d-108">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="fd88d-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fd88d-109">Select **New**.</span></span>

3. <span data-ttu-id="fd88d-110">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="fd88d-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="fd88d-111">Campo</span><span class="sxs-lookup"><span data-stu-id="fd88d-111">Field</span></span> | <span data-ttu-id="fd88d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd88d-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="fd88d-113">**Opzione di copertura**</span><span class="sxs-lookup"><span data-stu-id="fd88d-113">**Coverage option**</span></span> | <span data-ttu-id="fd88d-114">Un nome di opzione di copertura univoco.</span><span class="sxs-lookup"><span data-stu-id="fd88d-114">A unique coverage option name.</span></span> |
   | <span data-ttu-id="fd88d-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fd88d-115">**Description**</span></span> | <span data-ttu-id="fd88d-116">Una descrizione dell'opzione di copertura.</span><span class="sxs-lookup"><span data-stu-id="fd88d-116">A description of the coverage option.</span></span> |
   | <span data-ttu-id="fd88d-117">**Codice copertura**</span><span class="sxs-lookup"><span data-stu-id="fd88d-117">**Coverage code**</span></span> | <span data-ttu-id="fd88d-118">I codici di copertura assegnano importi minimi e massimi per ogni tipo di persona coperta idonea.</span><span class="sxs-lookup"><span data-stu-id="fd88d-118">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="fd88d-119">Un codice di copertura indica chi è coperto o l'importo di copertura consentito per un tipo di piano.</span><span class="sxs-lookup"><span data-stu-id="fd88d-119">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="fd88d-120">È possibile esprimere l'importo di copertura in dollari o come percentuale.</span><span class="sxs-lookup"><span data-stu-id="fd88d-120">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="fd88d-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fd88d-121">For example:</span></span></br></br><span data-ttu-id="fd88d-122">- **Dip+1** - Per essere idoneo, il dipendente deve avere una persona a carico selezionata (se sono selezionate più persone a carico, non è più idoneo).</span><span class="sxs-lookup"><span data-stu-id="fd88d-122">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="fd88d-123">- **Dip+ famiglia** - Per essere idoneo, il dipendente deve aver selezionato almeno due persone a carico.</span><span class="sxs-lookup"><span data-stu-id="fd88d-123">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="fd88d-124">**Numero massimo**</span><span class="sxs-lookup"><span data-stu-id="fd88d-124">**Maximum number**</span></span> | <span data-ttu-id="fd88d-125">Il numero massimo di persone a carico.</span><span class="sxs-lookup"><span data-stu-id="fd88d-125">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="fd88d-126">**Stato**</span><span class="sxs-lookup"><span data-stu-id="fd88d-126">**Status**</span></span> | <span data-ttu-id="fd88d-127">Lo stato dell'opzione di copertura.</span><span class="sxs-lookup"><span data-stu-id="fd88d-127">The status of the coverage option.</span></span> <span data-ttu-id="fd88d-128">Se lo stato dell'opzione di copertura è impostato su Non attivo, l'opzione di copertura non può essere selezionata nei tipi di piano.</span><span class="sxs-lookup"><span data-stu-id="fd88d-128">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="fd88d-129">**Percentuale**</span><span class="sxs-lookup"><span data-stu-id="fd88d-129">**Percent**</span></span> | <span data-ttu-id="fd88d-130">L'importo in percentuale.</span><span class="sxs-lookup"><span data-stu-id="fd88d-130">The percent amount.</span></span> <span data-ttu-id="fd88d-131">Questo campo è attivo solo se % x stipendio è stato selezionato nel campo Codice copertura.</span><span class="sxs-lookup"><span data-stu-id="fd88d-131">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="fd88d-132">**Divisore**</span><span class="sxs-lookup"><span data-stu-id="fd88d-132">**Divisor**</span></span> | <span data-ttu-id="fd88d-133">Il divisore da utilizzare nel calcolo quando si seleziona il codice di copertura % x stipendio.</span><span class="sxs-lookup"><span data-stu-id="fd88d-133">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="fd88d-134">**Percentuale minima**</span><span class="sxs-lookup"><span data-stu-id="fd88d-134">**Percent minimum**</span></span> | <span data-ttu-id="fd88d-135">La percentuale minima quando si seleziona il codice di copertura Percentuale.</span><span class="sxs-lookup"><span data-stu-id="fd88d-135">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="fd88d-136">**Percentuale massima**</span><span class="sxs-lookup"><span data-stu-id="fd88d-136">**Percent maximum**</span></span> | <span data-ttu-id="fd88d-137">La percentuale massima quando si seleziona il codice di copertura Percentuale.</span><span class="sxs-lookup"><span data-stu-id="fd88d-137">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="fd88d-138">Sotto **Opzioni di idoneità per contatti personali**, associare l'opzione di idoneità dei contatti personali appropriata a ciascuna opzione di copertura.</span><span class="sxs-lookup"><span data-stu-id="fd88d-138">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="fd88d-139">Sotto **Self service**, specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="fd88d-139">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="fd88d-140">Campo</span><span class="sxs-lookup"><span data-stu-id="fd88d-140">Field</span></span> | <span data-ttu-id="fd88d-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd88d-141">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="fd88d-142">**Consenti importo di contribuzione dipendente**</span><span class="sxs-lookup"><span data-stu-id="fd88d-142">**Allow employee contribution amount**</span></span> | <span data-ttu-id="fd88d-143">Specifica se consentire ai dipendenti di modificare l'importo di contribuzione nel self-service dei benefit quando selezionano i benefit.</span><span class="sxs-lookup"><span data-stu-id="fd88d-143">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="fd88d-144">Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano di benefit in base all'importo di contribuzione immesso dal dipendente nel self-service dei benefit.</span><span class="sxs-lookup"><span data-stu-id="fd88d-144">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="fd88d-145">**Consenti importo di copertura dipendente**</span><span class="sxs-lookup"><span data-stu-id="fd88d-145">**Allow employee coverage amount**</span></span> | <span data-ttu-id="fd88d-146">Specifica se consentire ai dipendenti di modificare l'importo di copertura nel self-service dei benefit quando selezionano i benefit.</span><span class="sxs-lookup"><span data-stu-id="fd88d-146">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="fd88d-147">Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano di benefit in base all'importo di copertura immesso in Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="fd88d-147">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="fd88d-148">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fd88d-148">Select **Save**.</span></span> 
