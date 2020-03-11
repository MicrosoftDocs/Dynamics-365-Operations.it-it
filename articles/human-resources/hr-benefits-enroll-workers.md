---
title: Iscrivere e rimuovere benefit da lavoratori
description: Questa procedura dimostra come un singolo lavoratore può essere iscritto a uno o più benefit e come più lavoratori possono essere iscritti a un benefit.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmWorkerEnrollment, HcmBenefitByEligibilityLookup, HcmMassBenefitEnrollment, HcmBenefitLookup, HcmMassBenefitEnrollmentResults
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 2e150032eb4c620a883520a2b24b74c66fca1fb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009609"
---
# <a name="enroll-and-remove-benefits-from-workers"></a><span data-ttu-id="30914-103">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="30914-103">Enroll and remove benefits from workers</span></span>



<span data-ttu-id="30914-104">Questa procedura dimostra come un singolo lavoratore può essere iscritto a uno o più benefit e come più lavoratori possono essere iscritti a un benefit.</span><span class="sxs-lookup"><span data-stu-id="30914-104">This procedure demonstrates how a single worker can be enrolled in one or more benefits, as well as multiple workers can be enrolled in a benefit.</span></span> <span data-ttu-id="30914-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="30914-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="enroll-a-single-worker-in-benefits"></a><span data-ttu-id="30914-106">Iscrivere un singolo lavoratore a un benefit</span><span class="sxs-lookup"><span data-stu-id="30914-106">Enroll a single worker in benefits</span></span>
1. <span data-ttu-id="30914-107">Andare a Risorse umane > Lavoratori > Dipendenti.</span><span class="sxs-lookup"><span data-stu-id="30914-107">Go to Human resources > Workers > Employees</span></span>
2. <span data-ttu-id="30914-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="30914-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="30914-109">Fare clic su Benefit.</span><span class="sxs-lookup"><span data-stu-id="30914-109">Click Benefits.</span></span>
4. <span data-ttu-id="30914-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="30914-110">Click New.</span></span>
5. <span data-ttu-id="30914-111">Nel campo Benefit immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="30914-111">In the Benefit field, enter or select a value.</span></span>
6. <span data-ttu-id="30914-112">Nel campo Data di inizio copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="30914-112">In the Coverage start date field, enter a date and time.</span></span>
7. <span data-ttu-id="30914-113">Nel campo Data di fine copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="30914-113">In the Coverage end date field, enter a date and time.</span></span>
8. <span data-ttu-id="30914-114">Espandere la sezione dei beneficiari se i beneficiari devono essere aggiunti al benefit.</span><span class="sxs-lookup"><span data-stu-id="30914-114">Expand the Beneficiaries section if beneficiaries need to be added to the benefit.</span></span> <span data-ttu-id="30914-115">È inoltre possibile aggiungere dipendenti da questa pagina, se applicabile al benefit.</span><span class="sxs-lookup"><span data-stu-id="30914-115">You can also add dependents from this page if applicable to the benefit.</span></span>
9. <span data-ttu-id="30914-116">È inoltre possibile modificare i dettagli di una iscrizione del benefit o eliminare un'iscrizione in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="30914-116">You can also edit the details of a benefit enrollment or delete an enrollment on this page.</span></span> <span data-ttu-id="30914-117">Al termine delle modifiche all'iscrizione del benefit, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="30914-117">When you have finished making changes to the benefit enrollment, close the page.</span></span>

## <a name="enroll-multiple-workers-in-a-benefit"></a><span data-ttu-id="30914-118">Iscrivere più lavoratori a un benefit</span><span class="sxs-lookup"><span data-stu-id="30914-118">Enroll multiple workers in a benefit</span></span>
1. <span data-ttu-id="30914-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="30914-119">Close the page.</span></span>
2. <span data-ttu-id="30914-120">Andare a Risorse umane > Lavoratori > Dipendenti.</span><span class="sxs-lookup"><span data-stu-id="30914-120">Go to Human resources > Workers > Employees</span></span>
3. <span data-ttu-id="30914-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30914-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="30914-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="30914-122">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="30914-123">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="30914-123">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="30914-124">Fare clic su Iscrivere in benefit.</span><span class="sxs-lookup"><span data-stu-id="30914-124">Click Enroll in benefits.</span></span>
7. <span data-ttu-id="30914-125">Nel campo Benefit immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="30914-125">In the Benefit field, enter or select a value.</span></span>
8. <span data-ttu-id="30914-126">Nel campo Data di inizio copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="30914-126">In the Coverage start date field, enter a date and time.</span></span>
9. <span data-ttu-id="30914-127">Nel campo Data di fine copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="30914-127">In the Coverage end date field, enter a date and time.</span></span>
10. <span data-ttu-id="30914-128">Fare clic su Iscrivi.</span><span class="sxs-lookup"><span data-stu-id="30914-128">Click Enroll.</span></span>
11. <span data-ttu-id="30914-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="30914-129">Close the page.</span></span>
12. <span data-ttu-id="30914-130">Andare a Risorse umane > Benefit > Iscrizione > Risultati iscrizione al benefit.</span><span class="sxs-lookup"><span data-stu-id="30914-130">Go to Human Resources > Benefits > Enrollment > Benefit enrollment results</span></span>
13. <span data-ttu-id="30914-131">Individuare il record di risultati del benefit cercato</span><span class="sxs-lookup"><span data-stu-id="30914-131">Find the benefit results record that you are looking for.</span></span>
14. <span data-ttu-id="30914-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30914-132">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="30914-133">La pagina consente la visualizzazione dei dipendenti iscritti al benefit e di tutti i dipendenti non iscritti.</span><span class="sxs-lookup"><span data-stu-id="30914-133">This page allows you to view which employees have been enrolled in the benefit, as well as any employees who were not enrolled.</span></span>
