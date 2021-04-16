---
title: Impostare un indice carburante vettore
description: Questa guida illustra come creare un paese di indice carburante, un indice carburante e un indice carburante del vettore.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1e972f2ba8211c47b11a4b83dac9ff60f813b1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837586"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="cff69-103">Impostare un indice carburante vettore</span><span class="sxs-lookup"><span data-stu-id="cff69-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cff69-104">Questa guida illustra come creare un paese di indice carburante, un indice carburante e un indice carburante del vettore.</span><span class="sxs-lookup"><span data-stu-id="cff69-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="cff69-105">Il paese di indice carburante specifica il paese in cui l'indice carburante deve essere applicato e l'indice carburante specifica un prezzo del carburante per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="cff69-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="cff69-106">Per riflettere la modifica dei prezzi carburante nel tempo, è possibile associare più indici carburante a un vettore.</span><span class="sxs-lookup"><span data-stu-id="cff69-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="cff69-107">Queste attività in genere vengono effettuate da un coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="cff69-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="cff69-108">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="cff69-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="cff69-109">Creare un paese di indice carburante</span><span class="sxs-lookup"><span data-stu-id="cff69-109">Create a fuel index region</span></span>
1. <span data-ttu-id="cff69-110">Andare a Gestione trasporto > Impostazioni > Indici carburante > Paesi indice carburante.</span><span class="sxs-lookup"><span data-stu-id="cff69-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="cff69-111">È necessario creare prima i diversi paesi in cui si opera e in cui si calcolano i supplementi carburante diversi.</span><span class="sxs-lookup"><span data-stu-id="cff69-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="cff69-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cff69-112">Click New.</span></span>
3. <span data-ttu-id="cff69-113">Nel campo Paese digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="cff69-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="cff69-114">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="cff69-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="cff69-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cff69-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="cff69-116">Creare un indice carburante</span><span class="sxs-lookup"><span data-stu-id="cff69-116">Create a fuel index</span></span>
1. <span data-ttu-id="cff69-117">Andare a Gestione trasporto > Impostazioni > Indici carburante > Indici carburante.</span><span class="sxs-lookup"><span data-stu-id="cff69-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="cff69-118">Per i paesi impostati è necessario immettere i prezzi correnti per il carburante.</span><span class="sxs-lookup"><span data-stu-id="cff69-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="cff69-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cff69-119">Click New.</span></span>
3. <span data-ttu-id="cff69-120">Nel campo Paese fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cff69-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="cff69-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cff69-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="cff69-122">Immettere un numero nel campo Prezzo per gallone.</span><span class="sxs-lookup"><span data-stu-id="cff69-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="cff69-123">Nel campo Data e ora di inizio effettive immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="cff69-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="cff69-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cff69-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="cff69-125">Creare un indice carburante vettore</span><span class="sxs-lookup"><span data-stu-id="cff69-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="cff69-126">Andare a Gestione trasporto > Impostazioni > Indici carburante > Indici carburante vettore.</span><span class="sxs-lookup"><span data-stu-id="cff69-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="cff69-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cff69-127">Click New.</span></span>
3. <span data-ttu-id="cff69-128">Nel campo Indice carburante vettore immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="cff69-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="cff69-129">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="cff69-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="cff69-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cff69-130">Click New.</span></span>
6. <span data-ttu-id="cff69-131">Nel campo Data e ora di inizio effettive immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="cff69-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="cff69-132">Nel campo Da PPG immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="cff69-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="cff69-133">In questo esempio, è possibile impostare il campo Da PPG su 1,95.</span><span class="sxs-lookup"><span data-stu-id="cff69-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="cff69-134">Nel campo A PPG immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="cff69-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="cff69-135">In questo esempio, è possibile impostare il campo A PPG su 2.</span><span class="sxs-lookup"><span data-stu-id="cff69-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="cff69-136">Nel campo Percentuale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="cff69-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="cff69-137">In questo esempio, è possibile impostare la percentuale su 3.</span><span class="sxs-lookup"><span data-stu-id="cff69-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="cff69-138">Nel campo Valuta fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cff69-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="cff69-139">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="cff69-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="cff69-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cff69-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="cff69-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cff69-141">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]