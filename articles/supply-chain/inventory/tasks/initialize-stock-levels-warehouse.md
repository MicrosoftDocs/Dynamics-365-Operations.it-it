---
title: Inizializzare i livelli di scorte in magazzino
description: Questa procedura mostra come aggiornare manualmente l'inventario disponibile tramite un giornale di registrazione movimenti Inventario.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bfa40c19e34631edb68b8cff42e7f72eb9ce2ad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "332290"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a><span data-ttu-id="c6c31-103">Inizializzare i livelli di scorte in magazzino</span><span class="sxs-lookup"><span data-stu-id="c6c31-103">Initialize stock levels in the warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c6c31-104">Questa procedura mostra come aggiornare manualmente l'inventario disponibile tramite un giornale di registrazione movimenti Inventario.</span><span class="sxs-lookup"><span data-stu-id="c6c31-104">This procedure shows you how to get the on-hand inventory updated manually using an Inventory movement journal.</span></span> <span data-ttu-id="c6c31-105">(È inoltre possibile aggiornare l'inventario disponibile importando le transazioni nelle entità di dati). È possibile eseguire questa guida nella società di dati dimostrativi USMF in cui tutti i prerequisiti come il nome del giornale di registrazione, l'impostazione dell'articolo, i profili di registrazione e i conti sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="c6c31-105">(It’s also possible to update on-hand inventory by importing transactions in data entities.) You can run this guide in demo data company USMF where all the prerequisites like journal name, item setup, posting profiles, and accounts are available.</span></span> <span data-ttu-id="c6c31-106">La guida suggerisce valori specifici per l'articolo e le dimensioni utilizzati.</span><span class="sxs-lookup"><span data-stu-id="c6c31-106">The guide suggests specific values for the item and dimensions that are used.</span></span> <span data-ttu-id="c6c31-107">Se si sceglie un altro articolo, è possibile che sia necessario immettere valori per le diverse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c6c31-107">If you choose a different item, you may need to enter values for different dimensions.</span></span>

1. <span data-ttu-id="c6c31-108">Passare a Gestione articoli > Inserimenti nel giornale di registrazione > Articoli > Movimenti.</span><span class="sxs-lookup"><span data-stu-id="c6c31-108">Go to Inventory management > Journal entries > Items > Movement.</span></span>
2. <span data-ttu-id="c6c31-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c6c31-109">Click New.</span></span>
3. <span data-ttu-id="c6c31-110">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c6c31-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="c6c31-111">Selezionare IMov.</span><span class="sxs-lookup"><span data-stu-id="c6c31-111">Select IMov.</span></span>
    * <span data-ttu-id="c6c31-112">La procedura consigliata consiste nell'utilizzare diversi modelli di nomi del giornale di registrazione per scopi commerciale differenti.</span><span class="sxs-lookup"><span data-stu-id="c6c31-112">It’s a good practise to use different journal name templates for the different business purposes.</span></span>  
5. <span data-ttu-id="c6c31-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c6c31-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c6c31-114">Nel campo Conto di contropartita specificare i valori "140200".</span><span class="sxs-lookup"><span data-stu-id="c6c31-114">In the Offset account field, specify the values '140200'.</span></span>
    * <span data-ttu-id="c6c31-115">Si tratta del conto di contropartita che sarà il conto predefinito sulle righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c6c31-115">This is the offset account that will be the default account on the journal lines.</span></span> <span data-ttu-id="c6c31-116">È possibile ignorare l'impostazione predefinita per assegnare conti di contropartita diversi per riga.</span><span class="sxs-lookup"><span data-stu-id="c6c31-116">It’s possible to override the default to assign different offset accounts per line.</span></span>  
7. <span data-ttu-id="c6c31-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c6c31-117">Click OK.</span></span>
8. <span data-ttu-id="c6c31-118">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c6c31-118">Click New.</span></span>
9. <span data-ttu-id="c6c31-119">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c6c31-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="c6c31-120">Selezionare l'articolo A0001.</span><span class="sxs-lookup"><span data-stu-id="c6c31-120">Select item A0001.</span></span>
11. <span data-ttu-id="c6c31-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c6c31-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="c6c31-122">Fare clic sulla scheda Dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="c6c31-122">Click the Inventory dimensions tab.</span></span>
13. <span data-ttu-id="c6c31-123">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c6c31-123">In the Site field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="c6c31-124">Selezionare sito 1.</span><span class="sxs-lookup"><span data-stu-id="c6c31-124">Select site 1.</span></span>
15. <span data-ttu-id="c6c31-125">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c6c31-125">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="c6c31-126">Selezionare magazzino 13.</span><span class="sxs-lookup"><span data-stu-id="c6c31-126">Select warehouse 13.</span></span>
17. <span data-ttu-id="c6c31-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c6c31-127">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="c6c31-128">Nel campo Ubicazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c6c31-128">In the Location field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="c6c31-129">Selezionare ubicazione 13.</span><span class="sxs-lookup"><span data-stu-id="c6c31-129">Select location 13.</span></span>
20. <span data-ttu-id="c6c31-130">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c6c31-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="c6c31-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c6c31-131">Click Save.</span></span>
22. <span data-ttu-id="c6c31-132">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="c6c31-132">Click Post.</span></span>
23. <span data-ttu-id="c6c31-133">Selezionare o deselezionare la casella di controllo Trasferisci tutti gli errori di registrazione in un nuovo giornale.</span><span class="sxs-lookup"><span data-stu-id="c6c31-133">Check or uncheck the Transfer all posting errors to a new journal check box.</span></span>
    * <span data-ttu-id="c6c31-134">Se si abilita l'opzione, tutte le righe che non verranno registrate verranno copiate in un nuovo giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c6c31-134">If you enable this option, any lines that fail to post will be copied to a new journal.</span></span> <span data-ttu-id="c6c31-135">È possibile utilizzare le informazioni nel registro per correggere i problemi e registrare di nuovo le righe.</span><span class="sxs-lookup"><span data-stu-id="c6c31-135">You can use the information in the log to correct the issues and then re-post the lines.</span></span>  
24. <span data-ttu-id="c6c31-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c6c31-136">Click OK.</span></span>
25. <span data-ttu-id="c6c31-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c6c31-137">Close the page.</span></span>
26. <span data-ttu-id="c6c31-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c6c31-138">Close the page.</span></span>

