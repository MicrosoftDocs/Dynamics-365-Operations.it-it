---
title: Creare un ordine fornitore disciplinato dal budget
description: Utilizzare questa procedura per creare un ordine fornitore controllato in relazione al budget disponibile.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0054745394d6a21599d8f07605f78ffdd7f575ab
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150541"
---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="1f55c-103">Creare un ordine fornitore disciplinato dal budget</span><span class="sxs-lookup"><span data-stu-id="1f55c-103">Create a purchase order governed by budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1f55c-104">Utilizzare questa procedura per creare un ordine fornitore controllato in relazione al budget disponibile.</span><span class="sxs-lookup"><span data-stu-id="1f55c-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="1f55c-105">Questa registrazione utilizza i dati dimostrativi della società USMF.</span><span class="sxs-lookup"><span data-stu-id="1f55c-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="1f55c-106">Esaminare la configurazione di controllo del budget</span><span class="sxs-lookup"><span data-stu-id="1f55c-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="1f55c-107">Andare a Impostazioni budget > Setup > Controllo del budget > Configurazione controllo del budget.</span><span class="sxs-lookup"><span data-stu-id="1f55c-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="1f55c-108">Fare clic sulla scheda Fondi budget disponibili.</span><span class="sxs-lookup"><span data-stu-id="1f55c-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="1f55c-109">Fare clic sulla scheda Documenti e giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="1f55c-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="1f55c-110">Fare clic sulla scheda Definisci regole di controllo del budget.</span><span class="sxs-lookup"><span data-stu-id="1f55c-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="1f55c-111">Fare clic sulla scheda Definisci i gruppi di budget.</span><span class="sxs-lookup"><span data-stu-id="1f55c-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="1f55c-112">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1f55c-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="1f55c-113">Creare l'intestazione ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="1f55c-113">Create the purchase order header</span></span>
1. <span data-ttu-id="1f55c-114">Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="1f55c-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="1f55c-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1f55c-115">Click New.</span></span>
3. <span data-ttu-id="1f55c-116">Nel campo Conto fornitore, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1f55c-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="1f55c-117">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="1f55c-117">Expand the General section.</span></span>
5. <span data-ttu-id="1f55c-118">Nel campo Data di registrazione impostare la data '2016-01-01'.</span><span class="sxs-lookup"><span data-stu-id="1f55c-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="1f55c-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="1f55c-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="1f55c-120">Aggiungere una riga ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="1f55c-120">Add a purchase order line</span></span>
1. <span data-ttu-id="1f55c-121">Nel campo Categoria di approvvigionamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1f55c-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="1f55c-122">Imposta la quantità su '2'.</span><span class="sxs-lookup"><span data-stu-id="1f55c-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="1f55c-123">Nel campo Unità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1f55c-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="1f55c-124">Impostare il prezzo unitario su '10000'.</span><span class="sxs-lookup"><span data-stu-id="1f55c-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="1f55c-125">Fare clic su Dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="1f55c-125">Click Financials.</span></span>
6. <span data-ttu-id="1f55c-126">Fare clic su Distribuisci importi.</span><span class="sxs-lookup"><span data-stu-id="1f55c-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="1f55c-127">Nel campo Conto CoGe specificare il valore '601300-001-023--'.</span><span class="sxs-lookup"><span data-stu-id="1f55c-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="1f55c-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1f55c-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="1f55c-129">Esegui verifica budget</span><span class="sxs-lookup"><span data-stu-id="1f55c-129">Perform budget checking</span></span>
1. <span data-ttu-id="1f55c-130">Fare clic su Dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="1f55c-130">Click Financials.</span></span>
2. <span data-ttu-id="1f55c-131">Fare clic su Esegui verifica budget.</span><span class="sxs-lookup"><span data-stu-id="1f55c-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="1f55c-132">Fare clic su Dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="1f55c-132">Click Financials.</span></span>
4. <span data-ttu-id="1f55c-133">Fare clic su Errori o avvisi verifica budget.</span><span class="sxs-lookup"><span data-stu-id="1f55c-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="1f55c-134">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="1f55c-134">Click Close.</span></span>

