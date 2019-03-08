---
title: Dividere un cespite
description: Questa guida attività suddividerà una percentuale di un libro cespiti in un nuovo libro cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "333371"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="b51da-103">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="b51da-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b51da-104">Questa guida attività suddividerà una percentuale di un libro cespiti in un nuovo libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="b51da-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="b51da-105">Utilizza il ruolo Ragioniere e i dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="b51da-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="b51da-106">Crea un nuovo cespite</span><span class="sxs-lookup"><span data-stu-id="b51da-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="b51da-107">Passare a Cespiti > Cespiti > Cespiti.</span><span class="sxs-lookup"><span data-stu-id="b51da-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="b51da-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b51da-108">Click New.</span></span>
3. <span data-ttu-id="b51da-109">Nel campo Cespiti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b51da-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="b51da-110">Si noti il numero cespite da utilizzare successivamente nel processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="b51da-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="b51da-111">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b51da-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="b51da-112">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="b51da-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="b51da-113">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="b51da-113">Split a fixed asset</span></span>
1. <span data-ttu-id="b51da-114">Nell'elenco, individuare e selezionare il cespite da dividere.</span><span class="sxs-lookup"><span data-stu-id="b51da-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="b51da-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b51da-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="b51da-116">Fare clic su Libri.</span><span class="sxs-lookup"><span data-stu-id="b51da-116">Click Books.</span></span>
    * <span data-ttu-id="b51da-117">Selezionare il libro per la divisione in base al nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="b51da-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="b51da-118">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="b51da-118">Click Functions.</span></span>
5. <span data-ttu-id="b51da-119">Fare clic su Dividi cespite.</span><span class="sxs-lookup"><span data-stu-id="b51da-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="b51da-120">Nel campo A cespite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b51da-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="b51da-121">Nel campo Al libro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b51da-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="b51da-122">Nel campo Data della transazione immettere una data.</span><span class="sxs-lookup"><span data-stu-id="b51da-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="b51da-123">Nel campo Percentuale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b51da-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="b51da-124">Nel campo Nome giornale di registrazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b51da-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="b51da-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b51da-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="b51da-126">Registrare la transazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b51da-126">Post the journal transaction</span></span>
1. <span data-ttu-id="b51da-127">Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="b51da-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="b51da-128">Nell'elenco, selezionare il giornale di registrazione creato con il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="b51da-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="b51da-129">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="b51da-129">Click Lines.</span></span>
    * <span data-ttu-id="b51da-130">Verificare le righe del giornale di registrazione create.</span><span class="sxs-lookup"><span data-stu-id="b51da-130">Verify the journal lines created.</span></span>  <span data-ttu-id="b51da-131">Una transazione di rettifica acquisizione viene creata per il cespite originario per diminuire il valore della percentuale specificata durante il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="b51da-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="b51da-132">Una transazione di acquisizione viene creata per il nuovo cespite per lo stesso importo.</span><span class="sxs-lookup"><span data-stu-id="b51da-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="b51da-133">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="b51da-133">Click Post.</span></span>

