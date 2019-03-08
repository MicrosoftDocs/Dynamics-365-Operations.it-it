---
title: Impostare prezzi basati su attributi per prodotti configurabili
description: Questa procedura mostra come impostare prezzi basati su attributi.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8568b5f4933ae58bc2d55a169c798668e03bed2a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "333785"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="40d83-103">Impostare prezzi basati su attributi per prodotti configurabili</span><span class="sxs-lookup"><span data-stu-id="40d83-103">Set up attribute-based pricing for configurable products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="40d83-104">Questa procedura mostra come impostare prezzi basati su attributi.</span><span class="sxs-lookup"><span data-stu-id="40d83-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="40d83-105">Come prerequisito, è necessario disporre di un modello di configurazione prodotto contenente uno o più componenti e attributi.</span><span class="sxs-lookup"><span data-stu-id="40d83-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="40d83-106">Nell'esempio viene utilizzato il modello di prodotto High End Speaker della società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="40d83-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="40d83-107">In genere, un responsabile di prodotto usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="40d83-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="40d83-108">Creare un nuovo modello di prezzo</span><span class="sxs-lookup"><span data-stu-id="40d83-108">Create a new price model</span></span>
1. <span data-ttu-id="40d83-109">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="40d83-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="40d83-110">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="40d83-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="40d83-111">Nell'elenco, selezionare la riga High End Speaker, ma non fare clic sul collegamento corrispondente al nome.</span><span class="sxs-lookup"><span data-stu-id="40d83-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="40d83-112">Nel riquadro azioni, fare clic su Modello.</span><span class="sxs-lookup"><span data-stu-id="40d83-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="40d83-113">Fare clic su Modelli di prezzo.</span><span class="sxs-lookup"><span data-stu-id="40d83-113">Click Price models.</span></span>
6. <span data-ttu-id="40d83-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="40d83-114">Click New.</span></span>
7. <span data-ttu-id="40d83-115">Digitare un valore nel campo Nome modello di prezzo.</span><span class="sxs-lookup"><span data-stu-id="40d83-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="40d83-116">Utilizzare un nome che rende il modello semplice identificare.</span><span class="sxs-lookup"><span data-stu-id="40d83-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="40d83-117">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="40d83-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="40d83-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="40d83-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="40d83-119">Aggiungere elementi di prezzo</span><span class="sxs-lookup"><span data-stu-id="40d83-119">Add price elements</span></span>
1. <span data-ttu-id="40d83-120">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="40d83-120">Click Edit.</span></span>
    * <span data-ttu-id="40d83-121">Ciascun componente in un modello di prodotto può avere un elemento di prezzo base e un numero qualsiasi di regole di espressione del prezzo.</span><span class="sxs-lookup"><span data-stu-id="40d83-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="40d83-122">È inoltre possibile aggiungere i prezzi in valute diverse.</span><span class="sxs-lookup"><span data-stu-id="40d83-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="40d83-123">Digitare un valore nel campo Espressione prezzo di base.</span><span class="sxs-lookup"><span data-stu-id="40d83-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="40d83-124">Ad esempio, digitare 100.</span><span class="sxs-lookup"><span data-stu-id="40d83-124">For example, type 100.</span></span>   <span data-ttu-id="40d83-125">Un'espressione per il prezzo di base può essere un valore numerico o può essere costituita da un calcolo aritmetico che include uno o più attributi.</span><span class="sxs-lookup"><span data-stu-id="40d83-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="40d83-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="40d83-126">Click Add.</span></span>
4. <span data-ttu-id="40d83-127">Nel campo Nome digitare 'Rosewood'.</span><span class="sxs-lookup"><span data-stu-id="40d83-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="40d83-128">Il nome dell'espressione per il prezzo aiuta a identificare cosa l'elemento di prezzo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="40d83-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="40d83-129">In questo esempio, si crea un elemento di prezzo relativo all'opzione di rivestimento in palissandro per il cabinet dell'altoparlante.</span><span class="sxs-lookup"><span data-stu-id="40d83-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="40d83-130">Fare clic su Modifica condizione.</span><span class="sxs-lookup"><span data-stu-id="40d83-130">Click Edit condition.</span></span>
    * <span data-ttu-id="40d83-131">Uan condizione di prezzo consente di garantire che un elemento dell'espressione per il prezzo viene incluso nel prezzo di vendita solo se una combinazione specifica di attributi è presente.</span><span class="sxs-lookup"><span data-stu-id="40d83-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="40d83-132">Nel campo ConstraintBody, immettere 'CabinetFinish=="Rosewood"'.</span><span class="sxs-lookup"><span data-stu-id="40d83-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="40d83-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="40d83-133">Click OK.</span></span>
8. <span data-ttu-id="40d83-134">Nel campo Espressione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="40d83-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="40d83-135">Ad esempio, digitare 50.</span><span class="sxs-lookup"><span data-stu-id="40d83-135">For example, type 50.</span></span>  
9. <span data-ttu-id="40d83-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="40d83-136">Close the page.</span></span>
10. <span data-ttu-id="40d83-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="40d83-137">Close the page.</span></span>

