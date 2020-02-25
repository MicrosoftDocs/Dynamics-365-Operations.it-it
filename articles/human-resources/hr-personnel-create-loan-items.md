---
title: Crea articoli prestito
description: Gli articoli prestito sono record che consentono di tenere traccia degli articoli fisici, ad esempio telefoni o computer, che la società presta ai lavoratori.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5245b82c81178ff41d5351cd8f73650aa497d555
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009522"
---
# <a name="create-loan-items"></a><span data-ttu-id="204e2-103">Crea articoli prestito</span><span class="sxs-lookup"><span data-stu-id="204e2-103">Create loan items</span></span>



<span data-ttu-id="204e2-104">Gli articoli prestito sono record che consentono di tenere traccia degli articoli fisici, ad esempio telefoni o computer, che la società presta ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="204e2-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="204e2-105">Ogni articolo fisico deve avere un articolo prestito corrispondente.</span><span class="sxs-lookup"><span data-stu-id="204e2-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="204e2-106">Per ciascun record articolo prestito dovranno essere descritti la tipologia, il responsabile del prestito e la durata in giorni consentita per il prestito.</span><span class="sxs-lookup"><span data-stu-id="204e2-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="204e2-107">È possibile creare più articoli prestito, ad esempio chiavi, schede di accesso o divise, contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="204e2-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="204e2-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="204e2-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="204e2-109">Creare Tipi di prestito</span><span class="sxs-lookup"><span data-stu-id="204e2-109">Create Loan types</span></span>
1. <span data-ttu-id="204e2-110">Andare a Risorse umane > Lavoratori > Articoli prestito > Tipi di prestito.</span><span class="sxs-lookup"><span data-stu-id="204e2-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="204e2-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="204e2-111">Click New.</span></span>
3. <span data-ttu-id="204e2-112">Digitare un valore nel campo Tipo di prestito.</span><span class="sxs-lookup"><span data-stu-id="204e2-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="204e2-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="204e2-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="204e2-114">Immettere il numero di giorni in cui gli articoli assegnati a questo tipo di prestito possono essere scaduti.</span><span class="sxs-lookup"><span data-stu-id="204e2-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="204e2-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="204e2-115">Click Save.</span></span>
7. <span data-ttu-id="204e2-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="204e2-116">Close the page.</span></span>
8. <span data-ttu-id="204e2-117">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="204e2-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="204e2-118">Creare articoli prestito</span><span class="sxs-lookup"><span data-stu-id="204e2-118">Create Loan items</span></span>
1. <span data-ttu-id="204e2-119">Andare a Risorse umane > Lavoratori > Articoli prestito > Articoli prestito.</span><span class="sxs-lookup"><span data-stu-id="204e2-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="204e2-120">Fare clic su Crea articoli prestito.</span><span class="sxs-lookup"><span data-stu-id="204e2-120">Click Create loan items.</span></span>
3. <span data-ttu-id="204e2-121">Nel campo Qtà immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="204e2-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="204e2-122">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="204e2-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="204e2-123">Nel campo Tipo di prestito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="204e2-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="204e2-124">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="204e2-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="204e2-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="204e2-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="204e2-126">Immettere il numero di giorni per cui l'articolo può rimanere in prestito.</span><span class="sxs-lookup"><span data-stu-id="204e2-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="204e2-127">Il valore predefinito per il campo Prevista restituzione nella pagina Attrezzature concesse in prestito viene calcolato in base alla data corrente a cui viene aggiunto questo numero.</span><span class="sxs-lookup"><span data-stu-id="204e2-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="204e2-128">Nel campo Incaricato fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="204e2-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="204e2-129">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="204e2-129">Click Select.</span></span>
11. <span data-ttu-id="204e2-130">Nel campo Valore iniziale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="204e2-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="204e2-131">Nel campo Intervallo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="204e2-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="204e2-132">Digitare un valore nel campo Formato.</span><span class="sxs-lookup"><span data-stu-id="204e2-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="204e2-133">Se ad esempio il numero iniziale per un articolo in prestito è 10, immettere due simboli di numero nel campo Formato.</span><span class="sxs-lookup"><span data-stu-id="204e2-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="204e2-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="204e2-134">Click OK.</span></span>
15. <span data-ttu-id="204e2-135">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="204e2-135">Refresh the page.</span></span>

