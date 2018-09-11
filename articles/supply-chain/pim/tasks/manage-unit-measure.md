--- 
title: "Gestire unità di misura"
description: "Questa procedura illustra come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate."
author: sorenva
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 43e645eaf6d301379182c8279dd3657a36384d5e
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="4cb02-103">Gestire unità di misura</span><span class="sxs-lookup"><span data-stu-id="4cb02-103">Manage unit of measure</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4cb02-104">Questa procedura illustra come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate.</span><span class="sxs-lookup"><span data-stu-id="4cb02-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="4cb02-105">È possibile eseguire questa procedura nella società di dati dimostrativi oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="4cb02-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="4cb02-106">Andare a Gestione prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="4cb02-106">Go to Released product maintenance.</span></span>
2. <span data-ttu-id="4cb02-107">Fare clic su Unità.</span><span class="sxs-lookup"><span data-stu-id="4cb02-107">Click Units.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="4cb02-108">Creare un'unità di misura</span><span class="sxs-lookup"><span data-stu-id="4cb02-108">Create a unit of measure</span></span>
1. <span data-ttu-id="4cb02-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4cb02-109">Click New.</span></span>
2. <span data-ttu-id="4cb02-110">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="4cb02-110">In the Unit field, type a value.</span></span>
    * <span data-ttu-id="4cb02-111">Immettere l'ID o il simbolo da utilizzare quando si fa riferimento all'unità di misura.</span><span class="sxs-lookup"><span data-stu-id="4cb02-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="4cb02-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4cb02-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4cb02-113">Immettere un nome descrittivo dell'unità di misura specificato nella lingua del sistema.</span><span class="sxs-lookup"><span data-stu-id="4cb02-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="4cb02-114">Selezionare un'opzione nel campo Classe di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="4cb02-114">In the Unit class field, select an option.</span></span>
    * <span data-ttu-id="4cb02-115">La classe di unità di misura definisce il raggruppamento logico, ad esempio area, massa o quantità, a cui l'unità di misura appartiene.</span><span class="sxs-lookup"><span data-stu-id="4cb02-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="4cb02-116">Nel campo Precisione decimale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4cb02-116">In the Decimal precision field, enter a number.</span></span>
    * <span data-ttu-id="4cb02-117">Specificare il numero di decimali da utilizzare per l'arrotondamento dell'unità di misura convertita dopo il completamento di un calcolo.</span><span class="sxs-lookup"><span data-stu-id="4cb02-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="4cb02-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4cb02-118">Click Save.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="4cb02-119">Definire conversioni unità</span><span class="sxs-lookup"><span data-stu-id="4cb02-119">Define unit translations</span></span>
1. <span data-ttu-id="4cb02-120">Fare clic su Testi unità.</span><span class="sxs-lookup"><span data-stu-id="4cb02-120">Click Unit texts.</span></span>
2. <span data-ttu-id="4cb02-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4cb02-121">Click New.</span></span>
    * <span data-ttu-id="4cb02-122">Utilizzare il testo unità per creare una traduzione dell'ID o di un simbolo che rappresenta l'unità di misura per l'utilizzo in documenti esterni in lingue specifiche del fornitore o del cliente.</span><span class="sxs-lookup"><span data-stu-id="4cb02-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="4cb02-123">Nel campo Lingua immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4cb02-123">In the Language field, enter or select a value.</span></span>
4. <span data-ttu-id="4cb02-124">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="4cb02-124">In the Text field, type a value.</span></span>
5. <span data-ttu-id="4cb02-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4cb02-125">Click Save.</span></span>
6. <span data-ttu-id="4cb02-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4cb02-126">Close the page.</span></span>
7. <span data-ttu-id="4cb02-127">Fare clic su Descrizioni unità convertite.</span><span class="sxs-lookup"><span data-stu-id="4cb02-127">Click Translated unit descriptions.</span></span>
8. <span data-ttu-id="4cb02-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4cb02-128">Click New.</span></span>
    * <span data-ttu-id="4cb02-129">Definire descrizioni specifiche di una lingua per l'unità di misura.</span><span class="sxs-lookup"><span data-stu-id="4cb02-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="4cb02-130">Nel campo Lingua immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4cb02-130">In the Language field, enter or select a value.</span></span>
10. <span data-ttu-id="4cb02-131">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4cb02-131">In the Description field, type a value.</span></span>
11. <span data-ttu-id="4cb02-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4cb02-132">Click Save.</span></span>
12. <span data-ttu-id="4cb02-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4cb02-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="4cb02-134">Definire regole di conversione unità</span><span class="sxs-lookup"><span data-stu-id="4cb02-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="4cb02-135">Fare clic su Conversioni unità.</span><span class="sxs-lookup"><span data-stu-id="4cb02-135">Click Unit conversions.</span></span>
    * <span data-ttu-id="4cb02-136">Definire le regole per la conversione dell'unità di misura verso e da altre unità di misura incluse nella classe di unità di misura selezionata.</span><span class="sxs-lookup"><span data-stu-id="4cb02-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="4cb02-137">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4cb02-137">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="4cb02-138">Nel campo Fattore immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4cb02-138">In the Factor field, enter a number.</span></span>
    * <span data-ttu-id="4cb02-139">Fattore di conversione tra Dall'unità e All'unità.</span><span class="sxs-lookup"><span data-stu-id="4cb02-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="4cb02-140">Il fattore di conversione, ad esempio, da centimetro a metro è 100 perché in un metro sono presenti 100 centimetri.</span><span class="sxs-lookup"><span data-stu-id="4cb02-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="4cb02-141">Nel campo All'unità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4cb02-141">In the To unit field, enter or select a value.</span></span>
5. <span data-ttu-id="4cb02-142">Selezionare un'opzione nel campo Arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="4cb02-142">In the Rounding field, select an option.</span></span>
    * <span data-ttu-id="4cb02-143">Definire il modo in cui il valore convertito deve essere arrotondato.</span><span class="sxs-lookup"><span data-stu-id="4cb02-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="4cb02-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4cb02-144">Click OK.</span></span>
7. <span data-ttu-id="4cb02-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4cb02-145">Close the page.</span></span>


