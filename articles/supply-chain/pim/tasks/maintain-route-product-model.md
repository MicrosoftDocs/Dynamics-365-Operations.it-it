---
title: Gestisci ciclo di lavorazione per un modello di prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921267"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="1ba6a-103">Gestisci ciclo di lavorazione per un modello di prodotto</span><span class="sxs-lookup"><span data-stu-id="1ba6a-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ba6a-104">L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="1ba6a-105">Questa procedura utilizza il modello High end speaker della società di dati dimostrativi USMF per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>

## <a name="add-a-route-operation"></a><span data-ttu-id="1ba6a-106">Aggiungere un'operazione del ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="1ba6a-106">Add a route operation</span></span>

1. <span data-ttu-id="1ba6a-107">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="1ba6a-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1ba6a-109">Selezionare il modello High end speaker per questo esercizio.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-109">Select the High end speaker model for this exercise.</span></span>  
1. <span data-ttu-id="1ba6a-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="1ba6a-111">Espandere la sezione **Operazioni ciclo di lavorazione**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-111">Expand the **Route operations** section.</span></span>
1. <span data-ttu-id="1ba6a-112">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-112">Select **Add**.</span></span>
1. <span data-ttu-id="1ba6a-113">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="1ba6a-114">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1ba6a-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="1ba6a-115">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-115">Select **Save**.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="1ba6a-116">Immettere i dettagli operazione ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="1ba6a-116">Enter route operation details</span></span>

1. <span data-ttu-id="1ba6a-117">Fare clic su **Dettagli operazione ciclo di lavorazione**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-117">Select **Route operation details**.</span></span>
1. <span data-ttu-id="1ba6a-118">Nel campo **Operazione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-118">In the **Operation** field, enter or select a value.</span></span>
1. <span data-ttu-id="1ba6a-119">Nel campo **Oper. n.**</span><span class="sxs-lookup"><span data-stu-id="1ba6a-119">In the **Oper. No.**</span></span> <span data-ttu-id="1ba6a-120">immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-120">field, enter a number.</span></span>
    * <span data-ttu-id="1ba6a-121">I numeri di operazione determinano la sequenza del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-121">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="1ba6a-122">Ogni proprietà di un'operazione del ciclo di lavorazione può ottenere un valore statico o essere sottoposta al mapping a un attributo.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-122">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="1ba6a-123">Il mapping a un attributo determinerà l'impostazione del valore come parte di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-123">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
1. <span data-ttu-id="1ba6a-124">Nel campo **Gruppo di cicli di lavorazione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-124">In the **Route group** field, enter or select a value.</span></span>
    * <span data-ttu-id="1ba6a-125">Il gruppo di cicli di lavorazione determina il comportamento essenziale di costi, consumo e impostazione.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-125">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
1. <span data-ttu-id="1ba6a-126">Seleziona la scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-126">Select the **Setup** tab.</span></span>
1. <span data-ttu-id="1ba6a-127">Seleziona la scheda **Tempi**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-127">Select the **Times** tab.</span></span>
1. <span data-ttu-id="1ba6a-128">Nel campo **Qtà lavorazione** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-128">In the **Process qty.** field, enter a number.</span></span>
    * <span data-ttu-id="1ba6a-129">Determinare quante elaborazioni verranno eseguite durante un'operazione.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-129">Determine how many will be processed during one operation.</span></span>  
1. <span data-ttu-id="1ba6a-130">Nel campo **Ore/Ora** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-130">In the **Hours/time** field, enter a number.</span></span>
    * <span data-ttu-id="1ba6a-131">Inserire il rapporto durata.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-131">Enter the time ratio.</span></span>  
1. <span data-ttu-id="1ba6a-132">Selezionare la casella di controllo **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-132">Select the **Set** check box.</span></span>
1. <span data-ttu-id="1ba6a-133">Nel campo **Tempo di esecuzione** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-133">In the **Run time** field, enter a number.</span></span>
    * <span data-ttu-id="1ba6a-134">Determinare l'ora di elaborazione per la quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-134">Determine the processing time for the quantity that you have specified.</span></span>  
1. <span data-ttu-id="1ba6a-135">Selezionare la scheda **Requisiti risorsa**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-135">Select the **Resource requirements** tab.</span></span>
1. <span data-ttu-id="1ba6a-136">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-136">Select **Add**.</span></span>
1. <span data-ttu-id="1ba6a-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-137">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="1ba6a-138">Nel campo **Tipo di requisito** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-138">In the **Requirement type** field, select an option.</span></span>
    * <span data-ttu-id="1ba6a-139">Decidere se si desidera specificare risorse o funzionalità specifiche di cui si deve disporre.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-139">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
1. <span data-ttu-id="1ba6a-140">Nel campo **Requisito** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-140">In the **Requirement** field, enter or select a value.</span></span>
1. <span data-ttu-id="1ba6a-141">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ba6a-141">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]