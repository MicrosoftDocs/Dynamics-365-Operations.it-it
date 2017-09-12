--- 
title: " Creare e associare una postazione hardware"
description: In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2705008908699bda9479eb54a4827c71f402b603
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="7aa99-103"> Creare e associare una postazione hardware</span><span class="sxs-lookup"><span data-stu-id="7aa99-103">Create and associate a hardware station</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="7aa99-104">In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="7aa99-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="7aa99-105">Un nuovo profilo hardware verrà creato e utilizzato per aggiungere le nuove stazioni hardware a un punto vendita predefinito (canale).</span><span class="sxs-lookup"><span data-stu-id="7aa99-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="7aa99-106">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="7aa99-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="7aa99-107">Passare a Funzionalità fondamentali commercio > Canali </span><span class="sxs-lookup"><span data-stu-id="7aa99-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="7aa99-108">> ..</span><span class="sxs-lookup"><span data-stu-id="7aa99-108">> ..</span></span> <span data-ttu-id="7aa99-109">> ..</span><span class="sxs-lookup"><span data-stu-id="7aa99-109">> ..</span></span> <span data-ttu-id="7aa99-110">> Profili stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="7aa99-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="7aa99-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7aa99-111">Click New.</span></span>
3. <span data-ttu-id="7aa99-112">Nel campo ID stazione hardware, immettere 'TestHWProfile'.</span><span class="sxs-lookup"><span data-stu-id="7aa99-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="7aa99-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7aa99-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7aa99-114">Immettere un numero nel campo Numero porta.</span><span class="sxs-lookup"><span data-stu-id="7aa99-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="7aa99-115">Nel campo Profilo hardware fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7aa99-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7aa99-116">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7aa99-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="7aa99-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7aa99-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7aa99-118">Nel campo Nome pacchetto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7aa99-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="7aa99-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7aa99-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7aa99-120">Si tratta del collo standard fornito con un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="7aa99-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="7aa99-121">Il numero di versione può variare.</span><span class="sxs-lookup"><span data-stu-id="7aa99-121">The version number may vary.</span></span>  
11. <span data-ttu-id="7aa99-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7aa99-122">Click Save.</span></span>
12. <span data-ttu-id="7aa99-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7aa99-123">Close the page.</span></span>
13. <span data-ttu-id="7aa99-124">Passare a Vendita al dettaglio e commercio > Canali > Tutti i punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="7aa99-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="7aa99-125">Nell'elenco selezionare la riga 17.</span><span class="sxs-lookup"><span data-stu-id="7aa99-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="7aa99-126">Se si utilizza la società di dati dimostrativi USRT, questo valore corrisponde al punto vendita Houston.</span><span class="sxs-lookup"><span data-stu-id="7aa99-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="7aa99-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7aa99-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="7aa99-128">Attivare l'espansione della sezione Stazioni hardware.</span><span class="sxs-lookup"><span data-stu-id="7aa99-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="7aa99-129">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7aa99-129">Click Add.</span></span>
18. <span data-ttu-id="7aa99-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7aa99-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="7aa99-131">Nel campo ID profilo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7aa99-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="7aa99-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7aa99-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7aa99-133">Deve essere il nuovo profilo di stazione hardware creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="7aa99-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="7aa99-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7aa99-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="7aa99-135">Digitare un valore nel campo Nome host.</span><span class="sxs-lookup"><span data-stu-id="7aa99-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="7aa99-136">Digitare un valore nel campo ID terminale EFT.</span><span class="sxs-lookup"><span data-stu-id="7aa99-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="7aa99-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7aa99-137">Click Save.</span></span>


