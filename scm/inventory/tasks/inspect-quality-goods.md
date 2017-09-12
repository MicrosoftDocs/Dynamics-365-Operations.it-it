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
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: aeed7eab750c606ea0009fa7c51baf96e2f9de51
ms.contentlocale: it-it
ms.lasthandoff: 09/12/2017

---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="f944b-103">Verificare la qualità delle merci</span><span class="sxs-lookup"><span data-stu-id="f944b-103">Inspect the quality of goods</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f944b-104">Questa procedura illustra come elaborare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="f944b-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="f944b-105">È possibile eseguire questa guida nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="f944b-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="f944b-106">Prima di iniziare questa procedura di esempio, è necessario confermare l'ordine fornitore "000016" e registrare un'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="f944b-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="f944b-107">In questo modo verrà automaticamente creato un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="f944b-107">This will automatically create a quality order.</span></span> <span data-ttu-id="f944b-108">Le ispezioni di controllo qualità sono in genere effettuati da un addetto al controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="f944b-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="f944b-109">Selezionare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="f944b-109">Select a quality order</span></span>
1. <span data-ttu-id="f944b-110">Andare a Gestione articoli > Attività periodiche > Gestione qualità > Ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="f944b-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="f944b-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f944b-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f944b-112">Selezionare l'ordine di controllo qualità creato prima di aver avviato questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f944b-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="f944b-113">Registrazione dei risultati dei test</span><span class="sxs-lookup"><span data-stu-id="f944b-113">Record test results</span></span>
1. <span data-ttu-id="f944b-114">Fare clic su Risultati.</span><span class="sxs-lookup"><span data-stu-id="f944b-114">Click Results.</span></span>
2. <span data-ttu-id="f944b-115">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="f944b-115">Click Edit.</span></span>
3. <span data-ttu-id="f944b-116">Nel campo Quantità risultante immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f944b-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="f944b-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f944b-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="f944b-118">Nel campo Risultato fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f944b-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f944b-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f944b-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f944b-120">In questo esempio il risultato è basato su un risultato predefinito.</span><span class="sxs-lookup"><span data-stu-id="f944b-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="f944b-121">In genere viene registrato un risultato del test più specifico, ad esempio una dimensione o un altro valore simile.</span><span class="sxs-lookup"><span data-stu-id="f944b-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="f944b-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f944b-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f944b-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f944b-123">Click Save.</span></span>
9. <span data-ttu-id="f944b-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f944b-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="f944b-125">Convalida l'ordine di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="f944b-125">Validate the quality order</span></span>
1. <span data-ttu-id="f944b-126">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="f944b-126">Click Validate.</span></span>
2. <span data-ttu-id="f944b-127">Nel campo Convalidato da fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f944b-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f944b-128">Selezionare l'utente che esegue l'ispezione.</span><span class="sxs-lookup"><span data-stu-id="f944b-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="f944b-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f944b-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f944b-130">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="f944b-130">Click Select.</span></span>
5. <span data-ttu-id="f944b-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f944b-131">Click OK.</span></span>
6. <span data-ttu-id="f944b-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f944b-132">Close the page.</span></span>

