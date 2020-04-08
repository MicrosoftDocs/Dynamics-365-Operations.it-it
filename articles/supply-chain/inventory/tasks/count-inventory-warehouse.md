---
title: Contare le scorte magazzino
description: In questa argomento vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 53e9457074b696efaf5958b3a3b4616f06f5a6ff
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145763"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="c4580-103">Contare le scorte magazzino</span><span class="sxs-lookup"><span data-stu-id="c4580-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c4580-104">In questa argomento vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="c4580-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="c4580-105">In questa procedura si applica la "funzionalità di gestione magazzino di base", disponibile nel modulo Gestione articoli e non la funzionalità di gestione del magazzino disponibile nel modulo Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="c4580-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="c4580-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="c4580-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="c4580-107">Se si utilizzano propri dati, assicurarsi di aver configurato prodotti e ubicazioni e aver creato un nome di giornale di registrazione magazzino per il conteggio dei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c4580-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="c4580-108">Il conteggio delle scorte viene in genere eseguito da un dipendente del reparto magazzino.</span><span class="sxs-lookup"><span data-stu-id="c4580-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="c4580-109">Creare un giornale di registrazione conteggi scorte</span><span class="sxs-lookup"><span data-stu-id="c4580-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="c4580-110">Andare a **Pannello di navigazione > Moduli > Gestione inventario > Inserimenti nel giornale di registrazione > Conteggio articoli > Conteggio**.</span><span class="sxs-lookup"><span data-stu-id="c4580-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="c4580-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c4580-111">Select **New**.</span></span>
3. <span data-ttu-id="c4580-112">Nel campo **Nome**, selezionare il nome di giornale di registrazione conteggi scorte che si desidera utilizzare dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c4580-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="c4580-113">Alcuni campi saranno popolati in base all'impostazione del nome giornale di registrazione conteggio scorte selezionato.</span><span class="sxs-lookup"><span data-stu-id="c4580-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="c4580-114">Nel campo **Lavoratore** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c4580-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c4580-115">**Selezionare** dall'elenco il lavoratore desiderato.</span><span class="sxs-lookup"><span data-stu-id="c4580-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="c4580-116">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4580-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="c4580-117">Crea righe di giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c4580-117">Create journal lines</span></span>
1. <span data-ttu-id="c4580-118">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c4580-118">Select **New**.</span></span>
2. <span data-ttu-id="c4580-119">Nel campo **Numero articolo** fare clic sul record desiderato dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c4580-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="c4580-120">Se si utilizza la società di dati dimostrativi USMF, selezionare **A0001**.</span><span class="sxs-lookup"><span data-stu-id="c4580-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="c4580-121">Nel campo **Sito** fare clic sul record desiderato dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c4580-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="c4580-122">Se si utilizza la società di dati dimostrativi USMF, selezionare il sito **2**.</span><span class="sxs-lookup"><span data-stu-id="c4580-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="c4580-123">Nel campo **Magazzino** fare clic sul record desiderato dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c4580-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="c4580-124">Se si utilizza la società di dati dimostrativi USMF, selezionare il magazzino **24**.</span><span class="sxs-lookup"><span data-stu-id="c4580-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="c4580-125">Nel campo **Ubicazione** fare clic sul record desiderato dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c4580-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="c4580-126">Se si utilizza la società di dati dimostrativi USMF, selezionare l'ubicazione **BULK-001**.</span><span class="sxs-lookup"><span data-stu-id="c4580-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="c4580-127">Nel campo Conteggiato immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c4580-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="c4580-128">Se si immette un numero diverso dal numero indicato nel campo **Disponibilità**, il campo **Quantità** viene aggiornato per visualizzare la discrepanza.</span><span class="sxs-lookup"><span data-stu-id="c4580-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="c4580-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c4580-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="c4580-130">Registrare il giornale di registrazione conteggi scorte</span><span class="sxs-lookup"><span data-stu-id="c4580-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="c4580-131">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="c4580-131">Select **Post**.</span></span> <span data-ttu-id="c4580-132">Durante la registrazione di giornale di registrazione conteggio scorte, se l'importo conteggiato è diverso dall'importo che viene dichiarato nel campo **Disponibilità**, viene registrata un'entrata o un'uscita dal magazzino, vengono modificati il livello e il valore delle scorte e vengono generate le transazioni contabili.</span><span class="sxs-lookup"><span data-stu-id="c4580-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="c4580-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4580-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="c4580-134">Visualizza operazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="c4580-134">View inventory transactions</span></span>
1. <span data-ttu-id="c4580-135">Selezionare **Scorte**.</span><span class="sxs-lookup"><span data-stu-id="c4580-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="c4580-136">Selezionare **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="c4580-136">Select **Transactions**.</span></span> <span data-ttu-id="c4580-137">È possibile visualizzare tutte le transazioni correlate che verranno create quando si registra il giornale di registrazione conteggi scorte.</span><span class="sxs-lookup"><span data-stu-id="c4580-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

