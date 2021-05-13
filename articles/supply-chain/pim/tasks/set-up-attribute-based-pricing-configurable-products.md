---
title: Impostare prezzi basati su attributi per prodotti configurabili
description: In questo argomento viene illustrato come impostare prezzi basati su attributi.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921243"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="6d729-103">Impostare prezzi basati su attributi per prodotti configurabili</span><span class="sxs-lookup"><span data-stu-id="6d729-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6d729-104">In questo argomento viene illustrato come impostare prezzi basati su attributi.</span><span class="sxs-lookup"><span data-stu-id="6d729-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="6d729-105">Come prerequisito, è necessario disporre di un modello di configurazione prodotto contenente uno o più componenti e attributi.</span><span class="sxs-lookup"><span data-stu-id="6d729-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="6d729-106">Nell'esempio viene utilizzato il modello di prodotto High End Speaker della società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="6d729-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="6d729-107">In genere, un responsabile di prodotto usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="6d729-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="6d729-108">Creare un nuovo modello di prezzo</span><span class="sxs-lookup"><span data-stu-id="6d729-108">Create a new price model</span></span>

1. <span data-ttu-id="6d729-109">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="6d729-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="6d729-110">Nell'elenco, selezionare la riga **High End Speaker**, ma non il collegamento per il nome.</span><span class="sxs-lookup"><span data-stu-id="6d729-110">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
1. <span data-ttu-id="6d729-111">Nel Riquadro azioni selezionare **Modello**.</span><span class="sxs-lookup"><span data-stu-id="6d729-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="6d729-112">Selezionare **Modelli di prezzo**.</span><span class="sxs-lookup"><span data-stu-id="6d729-112">Select **Price models**.</span></span>
1. <span data-ttu-id="6d729-113">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6d729-113">Select **New**.</span></span>
1. <span data-ttu-id="6d729-114">Digitare un valore nel campo **Nome modello di prezzo**.</span><span class="sxs-lookup"><span data-stu-id="6d729-114">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="6d729-115">Utilizzare un nome che rende il modello semplice identificare.</span><span class="sxs-lookup"><span data-stu-id="6d729-115">Use a name that makes the model easy to identify.</span></span>  
1. <span data-ttu-id="6d729-116">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6d729-116">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="6d729-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6d729-117">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="6d729-118">Aggiungere elementi di prezzo</span><span class="sxs-lookup"><span data-stu-id="6d729-118">Add price elements</span></span>

1. <span data-ttu-id="6d729-119">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6d729-119">Select **Edit**.</span></span> <span data-ttu-id="6d729-120">Ciascun componente in un modello di prodotto può avere un elemento di prezzo base e un numero qualsiasi di regole di espressione del prezzo.</span><span class="sxs-lookup"><span data-stu-id="6d729-120">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="6d729-121">È inoltre possibile aggiungere i prezzi in valute diverse.</span><span class="sxs-lookup"><span data-stu-id="6d729-121">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="6d729-122">Digitare un valore nel campo **Espressione prezzo di base**.</span><span class="sxs-lookup"><span data-stu-id="6d729-122">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="6d729-123">Ad esempio, digitare 100.</span><span class="sxs-lookup"><span data-stu-id="6d729-123">For example, type 100.</span></span> <span data-ttu-id="6d729-124">Un'espressione per il prezzo di base può essere un valore numerico o può essere costituita da un calcolo aritmetico che include uno o più attributi.</span><span class="sxs-lookup"><span data-stu-id="6d729-124">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="6d729-125">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6d729-125">Select **Add**.</span></span>
4. <span data-ttu-id="6d729-126">Nel campo **Nome**, digitare `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="6d729-126">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="6d729-127">Il nome dell'espressione per il prezzo aiuta a identificare cosa l'elemento di prezzo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="6d729-127">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="6d729-128">In questo esempio, si crea un elemento di prezzo relativo all'opzione di rivestimento in palissandro per il cabinet dell'altoparlante.</span><span class="sxs-lookup"><span data-stu-id="6d729-128">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="6d729-129">Selezionare **Modifica condizione**.</span><span class="sxs-lookup"><span data-stu-id="6d729-129">Select **Edit condition**.</span></span> <span data-ttu-id="6d729-130">Uan condizione di prezzo consente di garantire che un elemento dell'espressione per il prezzo viene incluso nel prezzo di vendita solo se una combinazione specifica di attributi è presente.</span><span class="sxs-lookup"><span data-stu-id="6d729-130">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="6d729-131">Nel campo **ConstraintBody** immettere `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="6d729-131">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="6d729-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d729-132">Select **OK**.</span></span>
8. <span data-ttu-id="6d729-133">Nel campo **Espressione** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6d729-133">In the **Expression** field, type a value.</span></span> <span data-ttu-id="6d729-134">Ad esempio, digitare `50`.</span><span class="sxs-lookup"><span data-stu-id="6d729-134">For example, type `50`.</span></span> 
9. <span data-ttu-id="6d729-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6d729-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]