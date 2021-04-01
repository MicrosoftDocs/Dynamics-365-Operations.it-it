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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0c02246a20ef28c0f4f28b73dfe5ff56f38a68b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247046"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="4072a-103"> Creare e associare una postazione hardware</span><span class="sxs-lookup"><span data-stu-id="4072a-103">Create and associate a hardware station</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4072a-104">In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="4072a-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="4072a-105">Un nuovo profilo hardware verrà creato e utilizzato per aggiungere le nuove stazioni hardware a un punto vendita predefinito (canale).</span><span class="sxs-lookup"><span data-stu-id="4072a-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="4072a-106">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="4072a-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="4072a-107">Passare a Funzionalità fondamentali commercio > Canali </span><span class="sxs-lookup"><span data-stu-id="4072a-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="4072a-108">> ..</span><span class="sxs-lookup"><span data-stu-id="4072a-108">> ..</span></span> <span data-ttu-id="4072a-109">> ..</span><span class="sxs-lookup"><span data-stu-id="4072a-109">> ..</span></span> <span data-ttu-id="4072a-110">> Profili stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="4072a-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="4072a-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4072a-111">Click New.</span></span>
3. <span data-ttu-id="4072a-112">Nel campo ID stazione hardware, immettere 'TestHWProfile'.</span><span class="sxs-lookup"><span data-stu-id="4072a-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="4072a-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="4072a-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4072a-114">Immettere un numero nel campo Numero porta.</span><span class="sxs-lookup"><span data-stu-id="4072a-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="4072a-115">Nel campo Profilo hardware fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4072a-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="4072a-116">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4072a-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="4072a-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4072a-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="4072a-118">Nel campo Nome pacchetto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4072a-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="4072a-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4072a-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4072a-120">Si tratta del collo standard fornito con un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="4072a-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="4072a-121">Il numero di versione può variare.</span><span class="sxs-lookup"><span data-stu-id="4072a-121">The version number may vary.</span></span>  
11. <span data-ttu-id="4072a-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4072a-122">Click Save.</span></span>
12. <span data-ttu-id="4072a-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4072a-123">Close the page.</span></span>
13. <span data-ttu-id="4072a-124">Passare a Retail e Commerce > Canali > Tutti i punti vendita.</span><span class="sxs-lookup"><span data-stu-id="4072a-124">Go to Retail and Commerce > Channels > All stores.</span></span>
14. <span data-ttu-id="4072a-125">Nell'elenco selezionare la riga 17.</span><span class="sxs-lookup"><span data-stu-id="4072a-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="4072a-126">Se si utilizza la società di dati dimostrativi USRT, questo valore corrisponde al punto vendita Houston.</span><span class="sxs-lookup"><span data-stu-id="4072a-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="4072a-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4072a-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="4072a-128">Attivare l'espansione della sezione Stazioni hardware.</span><span class="sxs-lookup"><span data-stu-id="4072a-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="4072a-129">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4072a-129">Click Add.</span></span>
18. <span data-ttu-id="4072a-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4072a-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="4072a-131">Nel campo ID profilo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4072a-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="4072a-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4072a-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4072a-133">Deve essere il nuovo profilo di stazione hardware creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="4072a-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="4072a-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4072a-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="4072a-135">Digitare un valore nel campo Nome host.</span><span class="sxs-lookup"><span data-stu-id="4072a-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="4072a-136">Digitare un valore nel campo ID terminale EFT.</span><span class="sxs-lookup"><span data-stu-id="4072a-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="4072a-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4072a-137">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]