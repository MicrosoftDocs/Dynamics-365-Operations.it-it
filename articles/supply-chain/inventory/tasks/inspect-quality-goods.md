---
title: "Verificare la qualità delle merci"
description: "Questa procedura illustra come elaborare un ordine di controllo qualità."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ab536047340bdebecb7c8317e20208c87a4776f7
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="a3ee6-103">Verificare la qualità delle merci</span><span class="sxs-lookup"><span data-stu-id="a3ee6-103">Inspect the quality of goods</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a3ee6-104">Questa procedura illustra come elaborare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="a3ee6-105">È possibile eseguire questa guida nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="a3ee6-106">Prima di iniziare questa procedura di esempio, è necessario confermare l'ordine fornitore "000016" e registrare un'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="a3ee6-107">In questo modo verrà automaticamente creato un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-107">This will automatically create a quality order.</span></span> <span data-ttu-id="a3ee6-108">Le ispezioni di controllo qualità sono in genere effettuati da un addetto al controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="a3ee6-109">Selezionare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-109">Select a quality order</span></span>
1. <span data-ttu-id="a3ee6-110">Andare a Gestione articoli > Attività periodiche > Gestione qualità > Ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="a3ee6-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a3ee6-112">Selezionare l'ordine di controllo qualità creato prima di aver avviato questa procedura.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="a3ee6-113">Registrazione dei risultati dei test</span><span class="sxs-lookup"><span data-stu-id="a3ee6-113">Record test results</span></span>
1. <span data-ttu-id="a3ee6-114">Fare clic su Risultati.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-114">Click Results.</span></span>
2. <span data-ttu-id="a3ee6-115">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-115">Click Edit.</span></span>
3. <span data-ttu-id="a3ee6-116">Nel campo Quantità risultante immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="a3ee6-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="a3ee6-118">Nel campo Risultato fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a3ee6-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a3ee6-120">In questo esempio il risultato è basato su un risultato predefinito.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="a3ee6-121">In genere viene registrato un risultato del test più specifico, ad esempio una dimensione o un altro valore simile.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="a3ee6-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a3ee6-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-123">Click Save.</span></span>
9. <span data-ttu-id="a3ee6-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="a3ee6-125">Convalida l'ordine di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="a3ee6-125">Validate the quality order</span></span>
1. <span data-ttu-id="a3ee6-126">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-126">Click Validate.</span></span>
2. <span data-ttu-id="a3ee6-127">Nel campo Convalidato da fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a3ee6-128">Selezionare l'utente che esegue l'ispezione.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="a3ee6-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a3ee6-130">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-130">Click Select.</span></span>
5. <span data-ttu-id="a3ee6-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-131">Click OK.</span></span>
6. <span data-ttu-id="a3ee6-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a3ee6-132">Close the page.</span></span>

