---
title: Iscrivere un dipendente a un piano di retribuzione variabile
description: Il responsabile di retribuzione e benefit può iscrivere i dipendenti a piani di retribuzione variabile per calcolare i premi in contanti e quelli non in contanti per i dipendenti.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2e591f471036c4b7f314155f1b56e87094ef1031
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009546"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="633f8-103">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="633f8-103">Enroll an employee in a variable compensation plan</span></span>

<span data-ttu-id="633f8-104">Il responsabile di retribuzione e benefit può iscrivere i dipendenti a piani di retribuzione variabile per calcolare i premi in contanti e quelli non in contanti per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="633f8-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="633f8-105">In questa procedura si presuppone che un piano di retribuzione variabile sia stato creato con il campo Abilita iscrizione impostato su Sì e che le regole di idoneità siano state create per il piano di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="633f8-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="633f8-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="633f8-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="633f8-107">Per avviare la procedura, andare a Risorse umane > Lavoratori > Dipendenti > Retribuzione > Iscrizione al piano di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="633f8-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="633f8-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="633f8-108">Click New.</span></span>
2. <span data-ttu-id="633f8-109">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="633f8-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="633f8-110">La ricerca del piano verrà filtrata per indicare solo i piani di retribuzione variabile per cui il dipendente è idoneo in base alle regole di idoneità.</span><span class="sxs-lookup"><span data-stu-id="633f8-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="633f8-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="633f8-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="633f8-112">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="633f8-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="633f8-113">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="633f8-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="633f8-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="633f8-114">Click Save.</span></span>
7. <span data-ttu-id="633f8-115">Attivare/disattivare l'espansione della sezione Sostituzioni.</span><span class="sxs-lookup"><span data-stu-id="633f8-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="633f8-116">Facoltativamente, la data della regola di assunzione può essere impostata per sostituire la data di assunzione di un dipendente quando la regola di assunzione specificata per il piano variabile selezione è Percentuale.</span><span class="sxs-lookup"><span data-stu-id="633f8-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="633f8-117">Se il piano variabile è una percentuale del piano di base, la percentuale di premio può essere sostituita per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="633f8-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="633f8-118">Se il piano di retribuzione variabile è un numero di piani di unità, il numero di unità può essere sostituito per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="633f8-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="633f8-119">Se al dipendente deve essere assegnato un importo forfettario per il premio, tale importo può essere impostato qui.</span><span class="sxs-lookup"><span data-stu-id="633f8-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="633f8-120">Attivare/disattivare l'espansione della sezione Sostituzioni organizzative.</span><span class="sxs-lookup"><span data-stu-id="633f8-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="633f8-121">Se è necessario prendere in considerazione le prestazioni del dipendente, le prestazioni dei diversi reparti o un reparto diverso da quello assegnato alla posizione del dipendente, il reparto può essere sostituito.</span><span class="sxs-lookup"><span data-stu-id="633f8-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="633f8-122">Il totale della colonna Percentuale deve ammontare a 100.</span><span class="sxs-lookup"><span data-stu-id="633f8-122">The Percent column should total 100.</span></span>  

