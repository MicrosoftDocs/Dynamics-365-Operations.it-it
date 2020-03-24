---
title: Creare opzioni di copertura
description: Le opzioni di copertura in Microsoft Dynamics 365 Human Resources sono livelli di copertura per un partecipante a un piano o programma di benefit, come ad esempio Solo dipendente per un piano sanitario oppure 2x stipendio per un piano di assicurazione sulla vita.
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
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092708"
---
# <a name="create-coverage-options"></a><span data-ttu-id="bdb88-103">Creare opzioni di copertura</span><span class="sxs-lookup"><span data-stu-id="bdb88-103">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="bdb88-104">Le opzioni di copertura in Microsoft Dynamics 365 Human Resources sono livelli di copertura per un partecipante a un piano o programma di benefit, come ad esempio Solo dipendente per un piano sanitario oppure 2x stipendio per un piano di assicurazione sulla vita.</span><span class="sxs-lookup"><span data-stu-id="bdb88-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="bdb88-105">Una volta definite, le opzioni di copertura di benefit sono riutilizzabili e ogni opzione può essere associata a uno o più piani.</span><span class="sxs-lookup"><span data-stu-id="bdb88-105">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="bdb88-106">Dopo aver definito le opzioni di copertura, associarle a un tipo di piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="bdb88-106">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="bdb88-107">Il tipo di piano viene quindi associato a un piano o programma di benefit.</span><span class="sxs-lookup"><span data-stu-id="bdb88-107">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="bdb88-108">Le opzioni di copertura associate a un tipo di piano saranno disponibili per tutti i piani creati con quel tipo di piano.</span><span class="sxs-lookup"><span data-stu-id="bdb88-108">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="bdb88-109">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di copertura**.</span><span class="sxs-lookup"><span data-stu-id="bdb88-109">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="bdb88-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bdb88-110">Select **New**.</span></span>

3. <span data-ttu-id="bdb88-111">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="bdb88-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="bdb88-112">Campo</span><span class="sxs-lookup"><span data-stu-id="bdb88-112">Field</span></span> | <span data-ttu-id="bdb88-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdb88-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bdb88-114">**Opzione di copertura**</span><span class="sxs-lookup"><span data-stu-id="bdb88-114">**Coverage option**</span></span> | <span data-ttu-id="bdb88-115">Un nome di opzione di copertura univoco.</span><span class="sxs-lookup"><span data-stu-id="bdb88-115">A unique coverage option name.</span></span> |
   | <span data-ttu-id="bdb88-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="bdb88-116">**Description**</span></span> | <span data-ttu-id="bdb88-117">Una descrizione dell'opzione di copertura.</span><span class="sxs-lookup"><span data-stu-id="bdb88-117">A description of the coverage option.</span></span> |
   | <span data-ttu-id="bdb88-118">**Codice copertura**</span><span class="sxs-lookup"><span data-stu-id="bdb88-118">**Coverage code**</span></span> | <span data-ttu-id="bdb88-119">I codici di copertura assegnano importi minimi e massimi per ogni tipo di persona coperta idonea.</span><span class="sxs-lookup"><span data-stu-id="bdb88-119">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="bdb88-120">Un codice di copertura indica chi è coperto o l'importo di copertura consentito per un tipo di piano.</span><span class="sxs-lookup"><span data-stu-id="bdb88-120">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="bdb88-121">È possibile esprimere l'importo di copertura in dollari o come percentuale.</span><span class="sxs-lookup"><span data-stu-id="bdb88-121">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="bdb88-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bdb88-122">For example:</span></span></br></br><span data-ttu-id="bdb88-123">- **Dip+1** - Per essere idoneo, il dipendente deve avere una persona a carico selezionata (se sono selezionate più persone a carico, non è più idoneo).</span><span class="sxs-lookup"><span data-stu-id="bdb88-123">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="bdb88-124">- **Dip+ famiglia** - Per essere idoneo, il dipendente deve aver selezionato almeno due persone a carico.</span><span class="sxs-lookup"><span data-stu-id="bdb88-124">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="bdb88-125">**Numero massimo**</span><span class="sxs-lookup"><span data-stu-id="bdb88-125">**Maximum number**</span></span> | <span data-ttu-id="bdb88-126">Il numero massimo di persone a carico.</span><span class="sxs-lookup"><span data-stu-id="bdb88-126">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="bdb88-127">**Stato**</span><span class="sxs-lookup"><span data-stu-id="bdb88-127">**Status**</span></span> | <span data-ttu-id="bdb88-128">Lo stato dell'opzione di copertura.</span><span class="sxs-lookup"><span data-stu-id="bdb88-128">The status of the coverage option.</span></span> <span data-ttu-id="bdb88-129">Se lo stato dell'opzione di copertura è impostato su Non attivo, l'opzione di copertura non può essere selezionata nei tipi di piano.</span><span class="sxs-lookup"><span data-stu-id="bdb88-129">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="bdb88-130">**Percentuale**</span><span class="sxs-lookup"><span data-stu-id="bdb88-130">**Percent**</span></span> | <span data-ttu-id="bdb88-131">L'importo in percentuale.</span><span class="sxs-lookup"><span data-stu-id="bdb88-131">The percent amount.</span></span> <span data-ttu-id="bdb88-132">Questo campo è attivo solo se % x stipendio è stato selezionato nel campo Codice copertura.</span><span class="sxs-lookup"><span data-stu-id="bdb88-132">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="bdb88-133">**Divisore**</span><span class="sxs-lookup"><span data-stu-id="bdb88-133">**Divisor**</span></span> | <span data-ttu-id="bdb88-134">Il divisore da utilizzare nel calcolo quando si seleziona il codice di copertura % x stipendio.</span><span class="sxs-lookup"><span data-stu-id="bdb88-134">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="bdb88-135">**Percentuale minima**</span><span class="sxs-lookup"><span data-stu-id="bdb88-135">**Percent minimum**</span></span> | <span data-ttu-id="bdb88-136">La percentuale minima quando si seleziona il codice di copertura Percentuale.</span><span class="sxs-lookup"><span data-stu-id="bdb88-136">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="bdb88-137">**Percentuale massima**</span><span class="sxs-lookup"><span data-stu-id="bdb88-137">**Percent maximum**</span></span> | <span data-ttu-id="bdb88-138">La percentuale massima quando si seleziona il codice di copertura Percentuale.</span><span class="sxs-lookup"><span data-stu-id="bdb88-138">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="bdb88-139">Sotto **Opzioni di idoneità per contatti personali**, associare l'opzione di idoneità dei contatti personali appropriata a ciascuna opzione di copertura.</span><span class="sxs-lookup"><span data-stu-id="bdb88-139">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="bdb88-140">Sotto **Self service**, specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="bdb88-140">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="bdb88-141">Campo</span><span class="sxs-lookup"><span data-stu-id="bdb88-141">Field</span></span> | <span data-ttu-id="bdb88-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdb88-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bdb88-143">**Consenti importo di contribuzione dipendente**</span><span class="sxs-lookup"><span data-stu-id="bdb88-143">**Allow employee contribution amount**</span></span> | <span data-ttu-id="bdb88-144">Specifica se consentire ai dipendenti di modificare l'importo di contribuzione nel self-service dei benefit quando selezionano i benefit.</span><span class="sxs-lookup"><span data-stu-id="bdb88-144">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="bdb88-145">Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano di benefit in base all'importo di contribuzione immesso dal dipendente nel self-service dei benefit.</span><span class="sxs-lookup"><span data-stu-id="bdb88-145">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="bdb88-146">**Consenti importo di copertura dipendente**</span><span class="sxs-lookup"><span data-stu-id="bdb88-146">**Allow employee coverage amount**</span></span> | <span data-ttu-id="bdb88-147">Specifica se consentire ai dipendenti di modificare l'importo di copertura nel self-service dei benefit quando selezionano i benefit.</span><span class="sxs-lookup"><span data-stu-id="bdb88-147">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="bdb88-148">Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano di benefit in base all'importo di copertura immesso in Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="bdb88-148">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="bdb88-149">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bdb88-149">Select **Save**.</span></span> 
