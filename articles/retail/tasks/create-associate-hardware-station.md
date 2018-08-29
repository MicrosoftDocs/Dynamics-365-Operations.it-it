--- 
title: Creare stazioni hardware
description: In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 3551e37c6aae37c01b5cacff8b908faaf75fb3e2
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="create-hardware-stations"></a><span data-ttu-id="381e6-103">Creare stazioni hardware</span><span class="sxs-lookup"><span data-stu-id="381e6-103">Create hardware stations</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="381e6-104">In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="381e6-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="381e6-105">Un nuovo profilo hardware verrà creato e utilizzato per aggiungere le nuove stazioni hardware a un punto vendita predefinito (canale).</span><span class="sxs-lookup"><span data-stu-id="381e6-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="381e6-106">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="381e6-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="381e6-107">Passare a Funzionalità fondamentali commercio > Canali </span><span class="sxs-lookup"><span data-stu-id="381e6-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="381e6-108">> ..</span><span class="sxs-lookup"><span data-stu-id="381e6-108">> ..</span></span> <span data-ttu-id="381e6-109">> ..</span><span class="sxs-lookup"><span data-stu-id="381e6-109">> ..</span></span> <span data-ttu-id="381e6-110">> Profili stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="381e6-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="381e6-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="381e6-111">Click New.</span></span>
3. <span data-ttu-id="381e6-112">Nel campo ID stazione hardware, immettere 'TestHWProfile'.</span><span class="sxs-lookup"><span data-stu-id="381e6-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="381e6-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="381e6-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="381e6-114">Immettere un numero nel campo Numero porta.</span><span class="sxs-lookup"><span data-stu-id="381e6-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="381e6-115">Nel campo Profilo hardware fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="381e6-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="381e6-116">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="381e6-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="381e6-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="381e6-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="381e6-118">Nel campo Nome pacchetto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="381e6-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="381e6-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="381e6-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="381e6-120">Si tratta del collo standard fornito con un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="381e6-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="381e6-121">Il numero di versione può variare.</span><span class="sxs-lookup"><span data-stu-id="381e6-121">The version number may vary.</span></span>  
11. <span data-ttu-id="381e6-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="381e6-122">Click Save.</span></span>
12. <span data-ttu-id="381e6-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="381e6-123">Close the page.</span></span>
13. <span data-ttu-id="381e6-124">Passare a Vendita al dettaglio e commercio > Canali > Tutti i punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="381e6-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="381e6-125">Nell'elenco selezionare la riga 17.</span><span class="sxs-lookup"><span data-stu-id="381e6-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="381e6-126">Se si utilizza la società di dati dimostrativi USRT, questo valore corrisponde al punto vendita Houston.</span><span class="sxs-lookup"><span data-stu-id="381e6-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="381e6-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="381e6-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="381e6-128">Attivare l'espansione della sezione Stazioni hardware.</span><span class="sxs-lookup"><span data-stu-id="381e6-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="381e6-129">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="381e6-129">Click Add.</span></span>
18. <span data-ttu-id="381e6-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="381e6-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="381e6-131">Nel campo ID profilo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="381e6-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="381e6-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="381e6-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="381e6-133">Deve essere il nuovo profilo di stazione hardware creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="381e6-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="381e6-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="381e6-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="381e6-135">Digitare un valore nel campo Nome host.</span><span class="sxs-lookup"><span data-stu-id="381e6-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="381e6-136">Digitare un valore nel campo ID terminale EFT.</span><span class="sxs-lookup"><span data-stu-id="381e6-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="381e6-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="381e6-137">Click Save.</span></span>


