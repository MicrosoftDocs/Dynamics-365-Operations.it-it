---
title: Iscrivere e rimuovere benefit da lavoratori
description: Questa procedura dimostra come un singolo lavoratore può essere iscritto a uno o più benefit e come più lavoratori possono essere iscritti a un benefit.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmWorkerEnrollment, HcmBenefitByEligibilityLookup, HcmMassBenefitEnrollment, HcmBenefitLookup, HcmMassBenefitEnrollmentResults, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: cb56d11cb3acd1e8e39765284269234fc632f17f
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465104"
---
# <a name="enroll-and-remove-benefits-from-workers"></a><span data-ttu-id="ff9e1-103">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="ff9e1-103">Enroll and remove benefits from workers</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="ff9e1-104">Questa procedura dimostra come un singolo lavoratore può essere iscritto a uno o più benefit e come più lavoratori possono essere iscritti a un benefit.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-104">This procedure demonstrates how a single worker can be enrolled in one or more benefits, as well as multiple workers can be enrolled in a benefit.</span></span> <span data-ttu-id="ff9e1-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="enroll-a-single-worker-in-benefits"></a><span data-ttu-id="ff9e1-106">Iscrivere un singolo lavoratore a un benefit</span><span class="sxs-lookup"><span data-stu-id="ff9e1-106">Enroll a single worker in benefits</span></span>
1. <span data-ttu-id="ff9e1-107">Andare a Risorse umane > Lavoratori > Dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-107">Go to Human resources > Workers > Employees</span></span>
2. <span data-ttu-id="ff9e1-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ff9e1-109">Fare clic su Benefit.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-109">Click Benefits.</span></span>
4. <span data-ttu-id="ff9e1-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-110">Click New.</span></span>
5. <span data-ttu-id="ff9e1-111">Nel campo Benefit immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-111">In the Benefit field, enter or select a value.</span></span>
6. <span data-ttu-id="ff9e1-112">Nel campo Data di inizio copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-112">In the Coverage start date field, enter a date and time.</span></span>
7. <span data-ttu-id="ff9e1-113">Nel campo Data di fine copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-113">In the Coverage end date field, enter a date and time.</span></span>
8. <span data-ttu-id="ff9e1-114">Espandere la sezione dei beneficiari se i beneficiari devono essere aggiunti al benefit.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-114">Expand the Beneficiaries section if beneficiaries need to be added to the benefit.</span></span> <span data-ttu-id="ff9e1-115">È inoltre possibile aggiungere dipendenti da questa pagina, se applicabile al benefit.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-115">You can also add dependents from this page if applicable to the benefit.</span></span>
9. <span data-ttu-id="ff9e1-116">È inoltre possibile modificare i dettagli di una iscrizione del benefit o eliminare un'iscrizione in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-116">You can also edit the details of a benefit enrollment or delete an enrollment on this page.</span></span> <span data-ttu-id="ff9e1-117">Al termine delle modifiche all'iscrizione del benefit, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-117">When you have finished making changes to the benefit enrollment, close the page.</span></span>

## <a name="enroll-multiple-workers-in-a-benefit"></a><span data-ttu-id="ff9e1-118">Iscrivere più lavoratori a un benefit</span><span class="sxs-lookup"><span data-stu-id="ff9e1-118">Enroll multiple workers in a benefit</span></span>
1. <span data-ttu-id="ff9e1-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-119">Close the page.</span></span>
2. <span data-ttu-id="ff9e1-120">Andare a Risorse umane > Lavoratori > Dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-120">Go to Human resources > Workers > Employees</span></span>
3. <span data-ttu-id="ff9e1-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ff9e1-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-122">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ff9e1-123">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-123">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="ff9e1-124">Fare clic su Iscrivere in benefit.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-124">Click Enroll in benefits.</span></span>
7. <span data-ttu-id="ff9e1-125">Nel campo Benefit immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-125">In the Benefit field, enter or select a value.</span></span>
8. <span data-ttu-id="ff9e1-126">Nel campo Data di inizio copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-126">In the Coverage start date field, enter a date and time.</span></span>
9. <span data-ttu-id="ff9e1-127">Nel campo Data di fine copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-127">In the Coverage end date field, enter a date and time.</span></span>
10. <span data-ttu-id="ff9e1-128">Fare clic su Iscrivi.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-128">Click Enroll.</span></span>
11. <span data-ttu-id="ff9e1-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-129">Close the page.</span></span>
12. <span data-ttu-id="ff9e1-130">Andare a Risorse umane > Benefit > Iscrizione > Risultati iscrizione al benefit.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-130">Go to Human Resources > Benefits > Enrollment > Benefit enrollment results</span></span>
13. <span data-ttu-id="ff9e1-131">Individuare il record di risultati del benefit cercato</span><span class="sxs-lookup"><span data-stu-id="ff9e1-131">Find the benefit results record that you are looking for.</span></span>
14. <span data-ttu-id="ff9e1-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-132">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="ff9e1-133">La pagina consente la visualizzazione dei dipendenti iscritti al benefit e di tutti i dipendenti non iscritti.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-133">This page allows you to view which employees have been enrolled in the benefit, as well as any employees who were not enrolled.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]