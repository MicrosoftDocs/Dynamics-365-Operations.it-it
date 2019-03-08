---
title: " Creare e associare una postazione hardware"
description: In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80df4fa663d208e28f5c9b031b6610d29286171c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "330565"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="70f43-103"> Creare e associare una postazione hardware</span><span class="sxs-lookup"><span data-stu-id="70f43-103">Create and associate a hardware station</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="70f43-104">In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="70f43-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="70f43-105">Un nuovo profilo hardware verrà creato e utilizzato per aggiungere le nuove stazioni hardware a un punto vendita predefinito (canale).</span><span class="sxs-lookup"><span data-stu-id="70f43-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="70f43-106">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="70f43-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="70f43-107">Passare a Funzionalità fondamentali commercio > Canali </span><span class="sxs-lookup"><span data-stu-id="70f43-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="70f43-108">> ..</span><span class="sxs-lookup"><span data-stu-id="70f43-108">> ..</span></span> <span data-ttu-id="70f43-109">> ..</span><span class="sxs-lookup"><span data-stu-id="70f43-109">> ..</span></span> <span data-ttu-id="70f43-110">> Profili stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="70f43-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="70f43-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="70f43-111">Click New.</span></span>
3. <span data-ttu-id="70f43-112">Nel campo ID stazione hardware, immettere 'TestHWProfile'.</span><span class="sxs-lookup"><span data-stu-id="70f43-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="70f43-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="70f43-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="70f43-114">Immettere un numero nel campo Numero porta.</span><span class="sxs-lookup"><span data-stu-id="70f43-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="70f43-115">Nel campo Profilo hardware fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="70f43-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="70f43-116">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="70f43-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="70f43-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="70f43-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="70f43-118">Nel campo Nome pacchetto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="70f43-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="70f43-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="70f43-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="70f43-120">Si tratta del collo standard fornito con un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="70f43-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="70f43-121">Il numero di versione può variare.</span><span class="sxs-lookup"><span data-stu-id="70f43-121">The version number may vary.</span></span>  
11. <span data-ttu-id="70f43-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="70f43-122">Click Save.</span></span>
12. <span data-ttu-id="70f43-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="70f43-123">Close the page.</span></span>
13. <span data-ttu-id="70f43-124">Passare a Vendita al dettaglio e commercio > Canali > Tutti i punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="70f43-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="70f43-125">Nell'elenco selezionare la riga 17.</span><span class="sxs-lookup"><span data-stu-id="70f43-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="70f43-126">Se si utilizza la società di dati dimostrativi USRT, questo valore corrisponde al punto vendita Houston.</span><span class="sxs-lookup"><span data-stu-id="70f43-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="70f43-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="70f43-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="70f43-128">Attivare l'espansione della sezione Stazioni hardware.</span><span class="sxs-lookup"><span data-stu-id="70f43-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="70f43-129">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="70f43-129">Click Add.</span></span>
18. <span data-ttu-id="70f43-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="70f43-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="70f43-131">Nel campo ID profilo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="70f43-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="70f43-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="70f43-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="70f43-133">Deve essere il nuovo profilo di stazione hardware creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="70f43-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="70f43-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="70f43-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="70f43-135">Digitare un valore nel campo Nome host.</span><span class="sxs-lookup"><span data-stu-id="70f43-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="70f43-136">Digitare un valore nel campo ID terminale EFT.</span><span class="sxs-lookup"><span data-stu-id="70f43-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="70f43-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="70f43-137">Click Save.</span></span>

