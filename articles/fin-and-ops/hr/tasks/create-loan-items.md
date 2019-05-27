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
ms.openlocfilehash: 75b2f17eb41ead7422276f72429eb6ede2ef4759
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1507891"
---
# <a name="create-loan-items"></a><span data-ttu-id="db87d-103">Crea articoli prestito</span><span class="sxs-lookup"><span data-stu-id="db87d-103">Create loan items</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db87d-104">Gli articoli prestito sono record che consentono di tenere traccia degli articoli fisici, ad esempio telefoni o computer, che la società presta ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="db87d-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="db87d-105">Ogni articolo fisico deve avere un articolo prestito corrispondente.</span><span class="sxs-lookup"><span data-stu-id="db87d-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="db87d-106">Per ciascun record articolo prestito dovranno essere descritti la tipologia, il responsabile del prestito e la durata in giorni consentita per il prestito.</span><span class="sxs-lookup"><span data-stu-id="db87d-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="db87d-107">È possibile creare più articoli prestito, ad esempio chiavi, schede di accesso o divise, contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="db87d-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="db87d-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="db87d-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="db87d-109">Creare Tipi di prestito</span><span class="sxs-lookup"><span data-stu-id="db87d-109">Create Loan types</span></span>
1. <span data-ttu-id="db87d-110">Andare a Risorse umane > Lavoratori > Articoli prestito > Tipi di prestito.</span><span class="sxs-lookup"><span data-stu-id="db87d-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="db87d-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="db87d-111">Click New.</span></span>
3. <span data-ttu-id="db87d-112">Digitare un valore nel campo Tipo di prestito.</span><span class="sxs-lookup"><span data-stu-id="db87d-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="db87d-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="db87d-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db87d-114">Immettere il numero di giorni in cui gli articoli assegnati a questo tipo di prestito possono essere scaduti.</span><span class="sxs-lookup"><span data-stu-id="db87d-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="db87d-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="db87d-115">Click Save.</span></span>
7. <span data-ttu-id="db87d-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="db87d-116">Close the page.</span></span>
8. <span data-ttu-id="db87d-117">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="db87d-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="db87d-118">Creare articoli prestito</span><span class="sxs-lookup"><span data-stu-id="db87d-118">Create Loan items</span></span>
1. <span data-ttu-id="db87d-119">Andare a Risorse umane > Lavoratori > Articoli prestito > Articoli prestito.</span><span class="sxs-lookup"><span data-stu-id="db87d-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="db87d-120">Fare clic su Crea articoli prestito.</span><span class="sxs-lookup"><span data-stu-id="db87d-120">Click Create loan items.</span></span>
3. <span data-ttu-id="db87d-121">Nel campo Qtà immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="db87d-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="db87d-122">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="db87d-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db87d-123">Nel campo Tipo di prestito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="db87d-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="db87d-124">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="db87d-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="db87d-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="db87d-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="db87d-126">Immettere il numero di giorni per cui l'articolo può rimanere in prestito.</span><span class="sxs-lookup"><span data-stu-id="db87d-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="db87d-127">Il valore predefinito per il campo Prevista restituzione nella pagina Attrezzature concesse in prestito viene calcolato in base alla data corrente a cui viene aggiunto questo numero.</span><span class="sxs-lookup"><span data-stu-id="db87d-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="db87d-128">Nel campo Incaricato fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="db87d-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="db87d-129">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="db87d-129">Click Select.</span></span>
11. <span data-ttu-id="db87d-130">Nel campo Valore iniziale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="db87d-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="db87d-131">Nel campo Intervallo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="db87d-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="db87d-132">Digitare un valore nel campo Formato.</span><span class="sxs-lookup"><span data-stu-id="db87d-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="db87d-133">Se ad esempio il numero iniziale per un articolo in prestito è 10, immettere due simboli di numero nel campo Formato.</span><span class="sxs-lookup"><span data-stu-id="db87d-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="db87d-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="db87d-134">Click OK.</span></span>
15. <span data-ttu-id="db87d-135">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="db87d-135">Refresh the page.</span></span>

