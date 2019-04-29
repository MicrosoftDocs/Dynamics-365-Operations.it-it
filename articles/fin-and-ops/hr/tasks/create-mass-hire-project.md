---
title: Creare un progetto di assunzione collettiva
description: Questa procedura descrive il processo di configurazione del progetto di assunzione collettiva.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea0f4638a968d2aecf4e3bb27acbd19e6455a8b3
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "856740"
---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="a2fcf-103">Creare un progetto di assunzione collettiva</span><span class="sxs-lookup"><span data-stu-id="a2fcf-103">Create a mass hire project</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a2fcf-104">Questa procedura descrive il processo di configurazione del progetto di assunzione collettiva.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="a2fcf-105">Un responsabile della selezione può utilizzare i progetti di assunzione collettiva per creare facilmente più posizioni e assumere una serie di lavoratori per tali posizioni.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="a2fcf-106">Per iniziare questa procedura, andare a Risorse umane > Selezione del personale > Progetti di assunzione collettiva.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="a2fcf-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="a2fcf-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-108">Click New.</span></span>
2. <span data-ttu-id="a2fcf-109">Digitare un valore nel campo Progetto di assunzione collettiva.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="a2fcf-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="a2fcf-111">Nel campo Avvio progetto immettere una data.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="a2fcf-112">Nel campo Fine progetto immettere una data.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="a2fcf-113">Fare clic su Apri progetto.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-113">Click Open project.</span></span>
7. <span data-ttu-id="a2fcf-114">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-114">Click Yes.</span></span>
8. <span data-ttu-id="a2fcf-115">Fare clic su Crea posizioni.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-115">Click Create positions.</span></span>
9. <span data-ttu-id="a2fcf-116">Nel campo Quantità immettere il numero di posizioni da creare</span><span class="sxs-lookup"><span data-stu-id="a2fcf-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="a2fcf-117">La data di inizio diventerà la data di assunzione per i nuovi lavoratori.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="a2fcf-118">La data di fine diventerà la data di fine rapporto per i nuovi lavoratori.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="a2fcf-119">Specificare se i nuovi lavoratori saranno dipendenti o terzisti.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="a2fcf-120">Nel campo Mansione fare clic sul pulsante a discesa per selezionare la mansione per cui creare le posizioni.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="a2fcf-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="a2fcf-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a2fcf-123">Il valore equivalente al tempo pieno predefinito deriverà dalla mansione selezionata.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="a2fcf-124">Se necessario, questo valore può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="a2fcf-125">Facoltativamente, selezionare il reparto per le nuove posizioni.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="a2fcf-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-126">Click OK.</span></span>

