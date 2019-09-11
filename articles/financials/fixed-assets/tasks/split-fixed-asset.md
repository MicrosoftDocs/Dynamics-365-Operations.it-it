---
title: Dividere un cespite
description: In questo argomento viene descritto come suddividere una percentuale di un libro cespiti in un nuovo libro cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867585"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="f0816-103">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="f0816-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f0816-104">In questo argomento viene descritto come suddividere una percentuale di un libro cespiti in un nuovo libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="f0816-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="f0816-105">Utilizza il ruolo Ragioniere e i dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="f0816-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="f0816-106">Crea un nuovo cespite</span><span class="sxs-lookup"><span data-stu-id="f0816-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="f0816-107">Nel pannello di navigazione, passare a **Moduli > Cespiti > Cespiti > Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="f0816-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="f0816-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f0816-108">Select **New**.</span></span>
3. <span data-ttu-id="f0816-109">Nel campo **Gruppo cespite** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f0816-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="f0816-110">Si noti il numero cespite da utilizzare successivamente nel processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="f0816-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="f0816-111">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="f0816-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="f0816-112">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="f0816-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="f0816-113">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="f0816-113">Split a fixed asset</span></span>
1. <span data-ttu-id="f0816-114">Nell'elenco, individuare e selezionare il collegamento del cespite da dividere.</span><span class="sxs-lookup"><span data-stu-id="f0816-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="f0816-115">Selezionare **Libri**.</span><span class="sxs-lookup"><span data-stu-id="f0816-115">Select **Books**.</span></span> <span data-ttu-id="f0816-116">Selezionare il libro per la divisione in base al nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="f0816-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="f0816-117">Selezionare **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="f0816-117">Select **Functions**.</span></span>
4. <span data-ttu-id="f0816-118">Selezionare **Dividi cespite**.</span><span class="sxs-lookup"><span data-stu-id="f0816-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="f0816-119">Nel campo **A cespite** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f0816-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="f0816-120">Nel campo **Al libro** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f0816-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="f0816-121">Nel campo **Data della transazione** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="f0816-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="f0816-122">Nel campo **Percentuale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f0816-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="f0816-123">Nel campo **Nome giornale di registrazione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f0816-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="f0816-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0816-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="f0816-125">Registrare la transazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="f0816-125">Post the journal transaction</span></span>
1. <span data-ttu-id="f0816-126">Nel pannello di navigazione, andare a **Moduli > Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="f0816-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="f0816-127">Nell'elenco, selezionare il giornale di registrazione creato con il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="f0816-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="f0816-128">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="f0816-128">Select **Lines**.</span></span>

    - <span data-ttu-id="f0816-129">Verificare le righe del giornale di registrazione create.</span><span class="sxs-lookup"><span data-stu-id="f0816-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="f0816-130">Una transazione di rettifica acquisizione viene creata per il cespite originario per diminuire il valore della percentuale specificata durante il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="f0816-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="f0816-131">Una transazione di acquisizione viene creata per il nuovo cespite per lo stesso importo.</span><span class="sxs-lookup"><span data-stu-id="f0816-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="f0816-132">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="f0816-132">Select **Post**.</span></span>

