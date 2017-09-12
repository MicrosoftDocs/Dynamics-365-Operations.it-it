--- 
title: Dividere un cespite
description: "Questa guida attività suddividerà una percentuale di un libro cespiti in un nuovo libro cespiti."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="e9ff2-103">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="e9ff2-103">Split a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e9ff2-104">Questa guida attività suddividerà una percentuale di un libro cespiti in un nuovo libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="e9ff2-105">Utilizza il ruolo Ragioniere e i dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="e9ff2-106">Crea un nuovo cespite</span><span class="sxs-lookup"><span data-stu-id="e9ff2-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="e9ff2-107">Passare a Cespiti > Cespiti > Cespiti.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="e9ff2-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-108">Click New.</span></span>
3. <span data-ttu-id="e9ff2-109">Nel campo Cespiti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="e9ff2-110">Si noti il numero cespite da utilizzare successivamente nel processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="e9ff2-111">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="e9ff2-112">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="e9ff2-113">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="e9ff2-113">Split a fixed asset</span></span>
1. <span data-ttu-id="e9ff2-114">Nell'elenco, individuare e selezionare il cespite da dividere.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="e9ff2-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="e9ff2-116">Fare clic su Libri.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-116">Click Books.</span></span>
    * <span data-ttu-id="e9ff2-117">Selezionare il libro per la divisione in base al nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="e9ff2-118">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-118">Click Functions.</span></span>
5. <span data-ttu-id="e9ff2-119">Fare clic su Dividi cespite.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="e9ff2-120">Nel campo A cespite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="e9ff2-121">Nel campo Al libro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="e9ff2-122">Nel campo Data della transazione immettere una data.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="e9ff2-123">Nel campo Percentuale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="e9ff2-124">Nel campo Nome giornale di registrazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="e9ff2-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="e9ff2-126">Registrare la transazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="e9ff2-126">Post the journal transaction</span></span>
1. <span data-ttu-id="e9ff2-127">Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="e9ff2-128">Nell'elenco, selezionare il giornale di registrazione creato con il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="e9ff2-129">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-129">Click Lines.</span></span>
    * <span data-ttu-id="e9ff2-130">Verificare le righe del giornale di registrazione create.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-130">Verify the journal lines created.</span></span>  <span data-ttu-id="e9ff2-131">Una transazione di rettifica acquisizione viene creata per il cespite originario per diminuire il valore della percentuale specificata durante il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="e9ff2-132">Una transazione di acquisizione viene creata per il nuovo cespite per lo stesso importo.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="e9ff2-133">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-133">Click Post.</span></span>

