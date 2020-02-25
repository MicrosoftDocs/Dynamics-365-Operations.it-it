---
title: Configurare opzioni di idoneità per contatti personali
description: Configurare opzioni di idoneità per contatti personali in Microsoft Dynamics 365 Human Resources. I contatti personali possono essere beneficiari o persone a carico.
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
ms.openlocfilehash: a50c5e54d224a2f8607284eb105381ffb6ef7ad9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009565"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="91c80-104">Configurare opzioni di idoneità per contatti personali</span><span class="sxs-lookup"><span data-stu-id="91c80-104">Configure personal contact eligibility options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="91c80-105">In questo articolo viene illustrato come configurare i tipi di contatti personali da utilizzare nei benefit in Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="91c80-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="91c80-106">I contatti personali possono essere beneficiari o persone a carico.</span><span class="sxs-lookup"><span data-stu-id="91c80-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="91c80-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di idoneità per contatti personali**.</span><span class="sxs-lookup"><span data-stu-id="91c80-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="91c80-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="91c80-108">Select **New**.</span></span>

3. <span data-ttu-id="91c80-109">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="91c80-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="91c80-110">Campo</span><span class="sxs-lookup"><span data-stu-id="91c80-110">Field</span></span> | <span data-ttu-id="91c80-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91c80-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="91c80-112">**Opzione di idoneità**</span><span class="sxs-lookup"><span data-stu-id="91c80-112">**Eligibility option**</span></span> | <span data-ttu-id="91c80-113">Un nome o codice di opzione di idoneità univoco per identificare l'opzione di idoneità.</span><span class="sxs-lookup"><span data-stu-id="91c80-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="91c80-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="91c80-114">**Description**</span></span> | <span data-ttu-id="91c80-115">Una breve Descrizione dell'opzione di idoneità.</span><span class="sxs-lookup"><span data-stu-id="91c80-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="91c80-116">**Codice di idoneità contatto**</span><span class="sxs-lookup"><span data-stu-id="91c80-116">**Contact eligibility code**</span></span> | <span data-ttu-id="91c80-117">Codice di sistema che descrive meglio l'opzione di idoneità personale.</span><span class="sxs-lookup"><span data-stu-id="91c80-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="91c80-118">È possibile scegliere tra:</span><span class="sxs-lookup"><span data-stu-id="91c80-118">You can choose from:</span></span> <ul><li><span data-ttu-id="91c80-119">Rapporto</span><span class="sxs-lookup"><span data-stu-id="91c80-119">Relationship</span></span></li><li><span data-ttu-id="91c80-120">Studente</span><span class="sxs-lookup"><span data-stu-id="91c80-120">Student</span></span></li><li><span data-ttu-id="91c80-121">Parte dipendente troppo anziana</span><span class="sxs-lookup"><span data-stu-id="91c80-121">Overage dependent</span></span></li><li><span data-ttu-id="91c80-122">Parte dipendente disabilitata troppo anziana</span><span class="sxs-lookup"><span data-stu-id="91c80-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="91c80-123">**Stato**</span><span class="sxs-lookup"><span data-stu-id="91c80-123">**Status**</span></span> | <span data-ttu-id="91c80-124">Lo stato dell'opzione di idoneità.</span><span class="sxs-lookup"><span data-stu-id="91c80-124">The status of the eligibility option.</span></span> <span data-ttu-id="91c80-125">Se lo stato di un'opzione di idoneità è impostato su inattivo, non è possibile selezionare quell'opzione di idoneità per contatti personali.</span><span class="sxs-lookup"><span data-stu-id="91c80-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="91c80-126">**Rapporto**</span><span class="sxs-lookup"><span data-stu-id="91c80-126">**Relationship**</span></span> | <span data-ttu-id="91c80-127">Specifica la relazione tra il contatto personale e il dipendente.</span><span class="sxs-lookup"><span data-stu-id="91c80-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="91c80-128">Questo campo è attivo solo se il codice di idoneità del contatto è impostato su Relazione.</span><span class="sxs-lookup"><span data-stu-id="91c80-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="91c80-129">**Età**</span><span class="sxs-lookup"><span data-stu-id="91c80-129">**Age**</span></span> | <span data-ttu-id="91c80-130">L'età massima di un contatto personale idoneo per il piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="91c80-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="91c80-131">Questo campo è attivo solo se si seleziona una relazione.</span><span class="sxs-lookup"><span data-stu-id="91c80-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="91c80-132">Questa età viene confrontata all'età calcolata del contatto personale.</span><span class="sxs-lookup"><span data-stu-id="91c80-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="91c80-133">L'età calcolata è: (data di copertura - data di nascita del contatto personale / 365).</span><span class="sxs-lookup"><span data-stu-id="91c80-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="91c80-134">Questo numero è sempre un numero intero.</span><span class="sxs-lookup"><span data-stu-id="91c80-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="91c80-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91c80-135">Select **Save**.</span></span> 
