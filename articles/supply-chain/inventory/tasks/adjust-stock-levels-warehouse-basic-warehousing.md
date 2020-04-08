---
title: Rettificare i livelli di scorte in magazzino (immagazzinaggio base)
description: In questa procedura viene descritto dettagliatamente il processo per creare e registrare un giornale di registrazione di rettifica magazzino in modo da rettificare i livelli di scorte dei prodotti in magazzino.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c617517109146b96075d03b6f3549639a99d7d1c
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146079"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a><span data-ttu-id="77bea-103">Rettificare i livelli di scorte in magazzino (immagazzinaggio base)</span><span class="sxs-lookup"><span data-stu-id="77bea-103">Adjust stock levels in the warehouse (basic warehousing)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="77bea-104">In questa procedura viene descritto dettagliatamente il processo per creare e registrare un giornale di registrazione di rettifica magazzino in modo da rettificare i livelli di scorte dei prodotti in magazzino.</span><span class="sxs-lookup"><span data-stu-id="77bea-104">This procedure walks you through the process of creating and posting an inventory adjustment journal in order to adjust stock levels of products in the warehouse.</span></span> <span data-ttu-id="77bea-105">È necessario disporre di un nome del giornale di registrazione magazzino configurato per le rettifiche dell'inventario prima di iniziare la procedura.</span><span class="sxs-lookup"><span data-stu-id="77bea-105">You need to have an inventory journal name set up for inventory adjustments before you start this.</span></span> <span data-ttu-id="77bea-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="77bea-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="77bea-107">Queste attività verranno in genere svolte da un dipendente del magazzino.</span><span class="sxs-lookup"><span data-stu-id="77bea-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-adjustment-journal"></a><span data-ttu-id="77bea-108">Creare un giornale di registrazione di rettifica magazzino</span><span class="sxs-lookup"><span data-stu-id="77bea-108">Create an inventory adjustment journal</span></span>
1. <span data-ttu-id="77bea-109">Passare a Gestione articoli > Inserimenti nel giornale di registrazione > Articoli > Rettifica magazzino.</span><span class="sxs-lookup"><span data-stu-id="77bea-109">Go to Inventory management > Journal entries > Items > Inventory adjustment.</span></span>
2. <span data-ttu-id="77bea-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="77bea-110">Click New.</span></span>
3. <span data-ttu-id="77bea-111">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="77bea-111">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="77bea-112">Nell'elenco fare clic sul nome del giornale di registrazione di rettifica magazzino che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="77bea-112">In the list, click on the inventory adjustment journal name you want to use.</span></span>
    * <span data-ttu-id="77bea-113">Alcuni campi saranno popolati in base all'impostazione del nome del giornale di registrazione di rettifica magazzino selezionato.</span><span class="sxs-lookup"><span data-stu-id="77bea-113">Some other fields will be populated based on the setup of the inventory adjustment journal name you select.</span></span>  
5. <span data-ttu-id="77bea-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="77bea-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="77bea-115">Creare righe di giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="77bea-115">Create journal lines</span></span>
1. <span data-ttu-id="77bea-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="77bea-116">Click New.</span></span>
2. <span data-ttu-id="77bea-117">Selezionare il campo del numero di articolo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="77bea-117">In the list, mark the item number field.</span></span>
3. <span data-ttu-id="77bea-118">Nel campo Numero articolo selezionare un articolo.</span><span class="sxs-lookup"><span data-stu-id="77bea-118">In the Item number field, Select an item.</span></span> <span data-ttu-id="77bea-119">Se si utilizza la società di dati dimostrativi USMF, digitare "D0001".</span><span class="sxs-lookup"><span data-stu-id="77bea-119">If you are using demo data company USMF, type 'D0001'.</span></span>
4. <span data-ttu-id="77bea-120">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="77bea-120">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="77bea-121">Selezionare un sito nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="77bea-121">In the list, select a site.</span></span>
6. <span data-ttu-id="77bea-122">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="77bea-122">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="77bea-123">Selezionare un magazzino nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="77bea-123">In the list, select a warehouse.</span></span>
    * <span data-ttu-id="77bea-124">Se è stato selezionato un articolo con Ubicazione come dimensione obbligatoria, è necessario specificare l'ubicazione in questo campo.</span><span class="sxs-lookup"><span data-stu-id="77bea-124">If you have selected an item with Location as a mandatory dimension, you would have to specify the location here.</span></span>  
8. <span data-ttu-id="77bea-125">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="77bea-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="77bea-126">Nel campo del prezzo di costo viene specificato il costo per unità utilizzato per le entrate in magazzino.</span><span class="sxs-lookup"><span data-stu-id="77bea-126">The cost price field specifies the cost per unit for inventory receipts.</span></span> <span data-ttu-id="77bea-127">Se il costo non viene specificato per il numero articolo o se si desidera modificarlo manualmente, effettuarlo qui.</span><span class="sxs-lookup"><span data-stu-id="77bea-127">If the cost is not specified for the item number or if you wanted to change it manually, you would do this here.</span></span>  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a><span data-ttu-id="77bea-128">Convalidare e registrare il giornale di registrazione di rettifica magazzino</span><span class="sxs-lookup"><span data-stu-id="77bea-128">Validate and post the inventory adjustment journal</span></span>
1. <span data-ttu-id="77bea-129">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="77bea-129">Click Validate.</span></span>
2. <span data-ttu-id="77bea-130">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="77bea-130">Click OK.</span></span>
3. <span data-ttu-id="77bea-131">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="77bea-131">Click Post.</span></span>
    * <span data-ttu-id="77bea-132">Durante la registrazione di questo tipo di giornale di registrazione viene registrata un'entrata o un'uscita dal magazzino, vengono modificati il livello e il valore delle scorte e vengono generate le transazioni contabili.</span><span class="sxs-lookup"><span data-stu-id="77bea-132">When you post this kind of journal, an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
4. <span data-ttu-id="77bea-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="77bea-133">Click OK.</span></span>
5. <span data-ttu-id="77bea-134">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="77bea-134">Close the form.</span></span>
6. <span data-ttu-id="77bea-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="77bea-135">Close the page.</span></span>

