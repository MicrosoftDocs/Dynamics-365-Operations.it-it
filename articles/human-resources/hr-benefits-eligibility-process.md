---
title: Elaborare l'idoneità al benefit
description: In questa procedura vengono descritti i passaggi per utilizzare il processo di idoneità al benefit.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 57e3e1dde4b4c8038b151dabf17af0f911f2ba07
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009563"
---
# <a name="benefit-eligibility-process"></a><span data-ttu-id="35876-103">Elaborare l'idoneità al benefit</span><span class="sxs-lookup"><span data-stu-id="35876-103">Benefit eligibility process</span></span>

<span data-ttu-id="35876-104">In questa procedura vengono descritti i passaggi per utilizzare il processo di idoneità al benefit.</span><span class="sxs-lookup"><span data-stu-id="35876-104">This procedure shows how the benefit eligibility process works.</span></span> <span data-ttu-id="35876-105">Al termine del processo, sarà possibile visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="35876-105">When the process is complete you can view the results.</span></span> <span data-ttu-id="35876-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="35876-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="35876-107">Andare a Risorse umane > Benefit > Benefit.</span><span class="sxs-lookup"><span data-stu-id="35876-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="35876-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="35876-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="35876-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="35876-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="35876-110">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="35876-110">Click Edit.</span></span>
5. <span data-ttu-id="35876-111">Nel campo Idoneità, selezionare 'Basato su regole'.</span><span class="sxs-lookup"><span data-stu-id="35876-111">In the Eligibility field, select 'Rule based'.</span></span>
6. <span data-ttu-id="35876-112">Nel campo Tipo di regola, selezionare la regola dei criteri di benefit che si desidera applicare al benefit.</span><span class="sxs-lookup"><span data-stu-id="35876-112">In the Rule type field, select the benefit policy rule you would like applied to the benefit.</span></span>
7. <span data-ttu-id="35876-113">Nel riquadro azioni fare clic su Benefit.</span><span class="sxs-lookup"><span data-stu-id="35876-113">On the Action Pane, click Benefit.</span></span>
8. <span data-ttu-id="35876-114">Fare clic su Crea evento di idoneità per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="35876-114">Click Create eligibility event to open the drop dialog.</span></span>
9. <span data-ttu-id="35876-115">Digitare un valore nel campo Evento.</span><span class="sxs-lookup"><span data-stu-id="35876-115">In the Event field, type a value.</span></span>
10. <span data-ttu-id="35876-116">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="35876-116">In the Description field, type a value.</span></span>
11. <span data-ttu-id="35876-117">Nel campo Tipo di evento, selezionare 'Iscrizione aperta'.</span><span class="sxs-lookup"><span data-stu-id="35876-117">In the Event type field, select 'Open enrollment'.</span></span>
12. <span data-ttu-id="35876-118">Nel campo Data di inizio copertura immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="35876-118">In the Coverage start date field, enter a date and time.</span></span>
13. <span data-ttu-id="35876-119">Nel campo Data di inizio periodo iscrizione immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="35876-119">In the Enrollment period start date field, enter a date and time.</span></span>
14. <span data-ttu-id="35876-120">Nel campo Giorni per l'iscrizione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="35876-120">In the Days to enroll field, enter a number.</span></span>
15. <span data-ttu-id="35876-121">Fare clic su Crea evento.</span><span class="sxs-lookup"><span data-stu-id="35876-121">Click Create event.</span></span>
16. <span data-ttu-id="35876-122">Fare clic su Aggiungi nella scheda dettaglio Lavoratori.</span><span class="sxs-lookup"><span data-stu-id="35876-122">Click Add in the Workers FastTab.</span></span>
17. <span data-ttu-id="35876-123">Nel campo Visualizza per tipo, selezionare 'Dipendenti'.</span><span class="sxs-lookup"><span data-stu-id="35876-123">In the Show by type field, select 'Employees'.</span></span>
18. <span data-ttu-id="35876-124">Nel campo Visualizza per persona giuridica, selezionare 'Persona giuridica corrente'.</span><span class="sxs-lookup"><span data-stu-id="35876-124">In the Show by legal entity field, select 'Current legal entity'.</span></span>
19. <span data-ttu-id="35876-125">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="35876-125">In the list, mark or unmark all rows.</span></span>
20. <span data-ttu-id="35876-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="35876-126">Click OK.</span></span>
21. <span data-ttu-id="35876-127">Fare clic su Elabora.</span><span class="sxs-lookup"><span data-stu-id="35876-127">Click Process.</span></span>
22. <span data-ttu-id="35876-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="35876-128">Click OK.</span></span>
23. <span data-ttu-id="35876-129">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="35876-129">Refresh the page.</span></span>
24. <span data-ttu-id="35876-130">Fare clic su Mostra risultati.</span><span class="sxs-lookup"><span data-stu-id="35876-130">Click Show results.</span></span>
25. <span data-ttu-id="35876-131">Apri filtro di colonna Stato.</span><span class="sxs-lookup"><span data-stu-id="35876-131">Open Status column filter.</span></span>
26. <span data-ttu-id="35876-132">Ordina da A a Z</span><span class="sxs-lookup"><span data-stu-id="35876-132">Sort A to Z</span></span>
