---
title: Configurare opzioni di idoneità per contatti personali
description: Configurare opzioni di idoneità per contatti personali in Microsoft Dynamics 365 Human Resources. I contatti personali possono essere beneficiari o persone a carico.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 68364b0cc1c579a3ee9813474c9d3f6e4df1c05d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419219"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="74794-104">Configurare opzioni di idoneità per contatti personali</span><span class="sxs-lookup"><span data-stu-id="74794-104">Configure personal contact eligibility options</span></span>

<span data-ttu-id="74794-105">In questo articolo viene illustrato come configurare i tipi di contatti personali da utilizzare nei benefit in Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="74794-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="74794-106">I contatti personali possono essere beneficiari o persone a carico.</span><span class="sxs-lookup"><span data-stu-id="74794-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="74794-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di idoneità per contatti personali**.</span><span class="sxs-lookup"><span data-stu-id="74794-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="74794-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="74794-108">Select **New**.</span></span>

3. <span data-ttu-id="74794-109">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="74794-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="74794-110">Campo</span><span class="sxs-lookup"><span data-stu-id="74794-110">Field</span></span> | <span data-ttu-id="74794-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74794-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="74794-112">**Opzione di idoneità**</span><span class="sxs-lookup"><span data-stu-id="74794-112">**Eligibility option**</span></span> | <span data-ttu-id="74794-113">Un nome o codice di opzione di idoneità univoco per identificare l'opzione di idoneità.</span><span class="sxs-lookup"><span data-stu-id="74794-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="74794-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="74794-114">**Description**</span></span> | <span data-ttu-id="74794-115">Una breve Descrizione dell'opzione di idoneità.</span><span class="sxs-lookup"><span data-stu-id="74794-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="74794-116">**Codice di idoneità contatto**</span><span class="sxs-lookup"><span data-stu-id="74794-116">**Contact eligibility code**</span></span> | <span data-ttu-id="74794-117">Codice di sistema che descrive meglio l'opzione di idoneità personale.</span><span class="sxs-lookup"><span data-stu-id="74794-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="74794-118">È possibile scegliere tra:</span><span class="sxs-lookup"><span data-stu-id="74794-118">You can choose from:</span></span> <ul><li><span data-ttu-id="74794-119">Rapporto</span><span class="sxs-lookup"><span data-stu-id="74794-119">Relationship</span></span></li><li><span data-ttu-id="74794-120">Studente</span><span class="sxs-lookup"><span data-stu-id="74794-120">Student</span></span></li><li><span data-ttu-id="74794-121">Parte dipendente troppo anziana</span><span class="sxs-lookup"><span data-stu-id="74794-121">Overage dependent</span></span></li><li><span data-ttu-id="74794-122">Parte dipendente disabilitata troppo anziana</span><span class="sxs-lookup"><span data-stu-id="74794-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="74794-123">**Stato**</span><span class="sxs-lookup"><span data-stu-id="74794-123">**Status**</span></span> | <span data-ttu-id="74794-124">Lo stato dell'opzione di idoneità.</span><span class="sxs-lookup"><span data-stu-id="74794-124">The status of the eligibility option.</span></span> <span data-ttu-id="74794-125">Se lo stato di un'opzione di idoneità è impostato su inattivo, non è possibile selezionare quell'opzione di idoneità per contatti personali.</span><span class="sxs-lookup"><span data-stu-id="74794-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="74794-126">**Rapporto**</span><span class="sxs-lookup"><span data-stu-id="74794-126">**Relationship**</span></span> | <span data-ttu-id="74794-127">Specifica la relazione tra il contatto personale e il dipendente.</span><span class="sxs-lookup"><span data-stu-id="74794-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="74794-128">Questo campo è attivo solo se il codice di idoneità del contatto è impostato su Relazione.</span><span class="sxs-lookup"><span data-stu-id="74794-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="74794-129">**Età**</span><span class="sxs-lookup"><span data-stu-id="74794-129">**Age**</span></span> | <span data-ttu-id="74794-130">L'età massima di un contatto personale idoneo per il piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="74794-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="74794-131">Questo campo è attivo solo se si seleziona una relazione.</span><span class="sxs-lookup"><span data-stu-id="74794-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="74794-132">Questa età viene confrontata all'età calcolata del contatto personale.</span><span class="sxs-lookup"><span data-stu-id="74794-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="74794-133">L'età calcolata è: (data di copertura - data di nascita del contatto personale / 365).</span><span class="sxs-lookup"><span data-stu-id="74794-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="74794-134">Questo numero è sempre un numero intero.</span><span class="sxs-lookup"><span data-stu-id="74794-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="74794-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="74794-135">Select **Save**.</span></span> 
