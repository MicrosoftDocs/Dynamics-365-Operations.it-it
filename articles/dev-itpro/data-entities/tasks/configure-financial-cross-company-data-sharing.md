--- 
title: Configurare condivisione dati interaziendali finanziari
description: "Questa procedura mostra come configurare, abilitare, convalidare e risolvere i conflitti quando vengono condivisi i dati tra due società."
author: aprilolson
manager: AnnBe
ms.date: 06/22/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 779722bd3acd10a85b089a4d30757b62293ea4e4
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="5087d-103">Configurare condivisione dati interaziendali finanziari</span><span class="sxs-lookup"><span data-stu-id="5087d-103">Configure financial cross-company data sharing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5087d-104">Questa procedura mostra come configurare, abilitare, convalidare e risolvere i conflitti quando vengono condivisi i dati tra due società.</span><span class="sxs-lookup"><span data-stu-id="5087d-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="5087d-105">Utilizza la società USMF e il modello di condivisione dei dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="5087d-105">It uses the USMF company and the Financial data sharing template.</span></span>



<span data-ttu-id="5087d-106">Questa guida attività richiede la piattaforma 7.1 o una versione successiva di Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="5087d-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="5087d-107">Andare a Amministrazione sistema > Aree di lavoro > Gestione dati.</span><span class="sxs-lookup"><span data-stu-id="5087d-107">Go to System administration > Workspaces > Data management.</span></span>
2. <span data-ttu-id="5087d-108">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="5087d-108">Click Import.</span></span>
3. <span data-ttu-id="5087d-109">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5087d-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="5087d-110">Nel campo Formato dati di origine selezionare Tipo di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5087d-110">In the Source data format field, select the Package type.</span></span>
    * <span data-ttu-id="5087d-111">Fare clic su Carica.</span><span class="sxs-lookup"><span data-stu-id="5087d-111">Click Upload.</span></span> <span data-ttu-id="5087d-112">Spostarsi nell'ubicazione del file pacchetto del modello di condivisione dei dati finanziari e selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="5087d-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>  
5. <span data-ttu-id="5087d-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5087d-113">Click Save.</span></span>
6. <span data-ttu-id="5087d-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5087d-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5087d-115">Selezionare i criteri appena creati di condivisione dei dati.</span><span class="sxs-lookup"><span data-stu-id="5087d-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="5087d-116">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="5087d-116">Click Import.</span></span>
8. <span data-ttu-id="5087d-117">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="5087d-117">Click Close.</span></span>
9. <span data-ttu-id="5087d-118">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="5087d-118">Refresh the page.</span></span>
10. <span data-ttu-id="5087d-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5087d-119">Close the page.</span></span>
11. <span data-ttu-id="5087d-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5087d-120">Close the page.</span></span>
12. <span data-ttu-id="5087d-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5087d-121">Close the page.</span></span>
13. <span data-ttu-id="5087d-122">Andare a Amministrazione sistema > Impostazione > Configura condivisione dati interaziendali.</span><span class="sxs-lookup"><span data-stu-id="5087d-122">Go to System administration > Setup > Configure cross-company data sharing.</span></span>
14. <span data-ttu-id="5087d-123">Nell'elenco trovare e selezionare Giorni di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5087d-123">In the list, find and select Payment days.</span></span>
15. <span data-ttu-id="5087d-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5087d-124">Click Add.</span></span>
16. <span data-ttu-id="5087d-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5087d-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="5087d-126">Digitare "USSI" nel campo Società.</span><span class="sxs-lookup"><span data-stu-id="5087d-126">In the Company field, type 'USSI'.</span></span>
18. <span data-ttu-id="5087d-127">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5087d-127">Click Add.</span></span>
19. <span data-ttu-id="5087d-128">Digitare "USMF" nel campo Società.</span><span class="sxs-lookup"><span data-stu-id="5087d-128">In the Company field, type 'USMF'.</span></span>
20. <span data-ttu-id="5087d-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5087d-129">Click Save.</span></span>
21. <span data-ttu-id="5087d-130">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="5087d-130">Click Enable.</span></span>
22. <span data-ttu-id="5087d-131">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="5087d-131">Click Yes.</span></span>
23. <span data-ttu-id="5087d-132">Fare clic su Cerca problemi di condivisione.</span><span class="sxs-lookup"><span data-stu-id="5087d-132">Click Find sharing issues.</span></span>
24. <span data-ttu-id="5087d-133">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="5087d-133">Click Yes.</span></span>
25. <span data-ttu-id="5087d-134">Fare clic su Aggiorna valore campo.</span><span class="sxs-lookup"><span data-stu-id="5087d-134">Click Update field value.</span></span>
26. <span data-ttu-id="5087d-135">Fare clic su Utilizza valore di società 1.</span><span class="sxs-lookup"><span data-stu-id="5087d-135">Click Use value from company 1.</span></span>
27. <span data-ttu-id="5087d-136">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="5087d-136">Refresh the page.</span></span>
28. <span data-ttu-id="5087d-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5087d-137">Close the page.</span></span>


