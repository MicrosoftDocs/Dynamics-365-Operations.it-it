---
title: Configurazione prodotto basata su dimensioni
description: "La configurazione prodotto basata su dimensioni rappresenta una soluzione semplice per la creazione di più varianti prodotto da una singola rappresentazione generale prodotto e dalle relative distinte base."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 89f01401f1d937a72ae7e59b784cf034b48aaf1f
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="dimension-based-product-configuration"></a><span data-ttu-id="363cd-103">Configurazione prodotto basata su dimensioni</span><span class="sxs-lookup"><span data-stu-id="363cd-103">Dimension-based product configuration</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="363cd-104">La configurazione prodotto basata su dimensioni rappresenta una soluzione semplice per la creazione di più varianti prodotto da una singola rappresentazione generale prodotto e dalle relative distinte base.</span><span class="sxs-lookup"><span data-stu-id="363cd-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="363cd-105">La configurazione prodotto basata su dimensioni è una delle tre tecnologie incorporate di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="363cd-106">Le altre due tecnologie sono varianti predefinite e configurazione basata su vincoli.</span><span class="sxs-lookup"><span data-stu-id="363cd-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="363cd-107">Tutte e tre le tecnologie utilizzano una rappresentazione generale prodotto come punto di inizio e consentono all'utente di creare più varianti prodotto per una rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="363cd-108">Concetti chiave</span><span class="sxs-lookup"><span data-stu-id="363cd-108">Key concepts</span></span>
<span data-ttu-id="363cd-109">La configurazione prodotto basata su dimensioni si fonde sui concetti chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="363cd-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="363cd-110">Rappresentazioni generali prodotto</span><span class="sxs-lookup"><span data-stu-id="363cd-110">Product masters</span></span>
-   <span data-ttu-id="363cd-111">Dimensione prodotto configurazione</span><span class="sxs-lookup"><span data-stu-id="363cd-111">Configuration product dimension</span></span>
-   <span data-ttu-id="363cd-112">Gruppi di configurazioni</span><span class="sxs-lookup"><span data-stu-id="363cd-112">Configuration groups</span></span>
-   <span data-ttu-id="363cd-113">Distinta base (DBA)</span><span class="sxs-lookup"><span data-stu-id="363cd-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="363cd-114">Ciclo di lavorazione di configurazione</span><span class="sxs-lookup"><span data-stu-id="363cd-114">Configuration route</span></span>
-   <span data-ttu-id="363cd-115">Regole di configurazione</span><span class="sxs-lookup"><span data-stu-id="363cd-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="363cd-116">Rappresentazioni generali prodotto</span><span class="sxs-lookup"><span data-stu-id="363cd-116">Product masters</span></span>

<span data-ttu-id="363cd-117">Una rappresentazione generale prodotto rappresenta il punto di partenza per qualsiasi processo di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="363cd-118">Per la configurazione prodotto basata su dimensioni è necessaria una rappresentazione generale prodotto con questa tecnologia di configurazione specifica e un gruppo di dimensioni prodotto che include la dimensione prodotto configurazione.</span><span class="sxs-lookup"><span data-stu-id="363cd-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="363cd-119">Dimensione prodotto configurazione</span><span class="sxs-lookup"><span data-stu-id="363cd-119">Configuration product dimension</span></span>

<span data-ttu-id="363cd-120">La dimensione prodotto configurazione consente di identificare le varianti prodotto per una rappresentazione generale prodotto con la tecnologia di configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="363cd-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="363cd-121">Il valore della dimensione di configurazione viene immesso dall'utente e deve consentire l'identificazione delle singole varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="363cd-122">Gruppi di configurazioni</span><span class="sxs-lookup"><span data-stu-id="363cd-122">Configuration groups</span></span>

<span data-ttu-id="363cd-123">I gruppi di configurazioni vengono definiti in un archivio centrale e possono essere utilizzati per tutti i modelli di configurazione prodotto basati su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="363cd-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="363cd-124">I gruppi di configurazioni sono associati alle singole righe DBA e tengono insieme un gruppo di righe che si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="363cd-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="363cd-125">Ciò significa che solo una riga di un gruppo può essere selezionata per una singola variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="363cd-126">Distinta base (DBA)</span><span class="sxs-lookup"><span data-stu-id="363cd-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="363cd-127">La DBA rappresenta i blocchi predefiniti per una configurazione prodotto basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="363cd-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="363cd-128">Deve includere tutti i prodotti diversi che possono essere utilizzati in qualsiasi variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="363cd-129">Ogni riga nella DBA può fare riferimento a un gruppo di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="363cd-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="363cd-130">Se una riga non fa riferimento a un gruppo di configurazioni, verrà inclusa in tutte le varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="363cd-131">Ciclo di lavorazione di configurazione</span><span class="sxs-lookup"><span data-stu-id="363cd-131">Configuration route</span></span>

<span data-ttu-id="363cd-132">Il ciclo di lavorazione di configurazione determina la sequenza dei gruppi di configurazioni, che vengono visualizzati all'utente durante il processo di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="363cd-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="363cd-133">Regole di configurazione</span><span class="sxs-lookup"><span data-stu-id="363cd-133">Configuration rules</span></span>

<span data-ttu-id="363cd-134">Le regole di configurazione rappresentano un meccanismo per assicurarsi che un prodotto incluso in un gruppo di configurazioni in una DBA determini l'inclusione o l'esclusione di un prodotto in un gruppo di configurazioni diverso nella stessa DBA.</span><span class="sxs-lookup"><span data-stu-id="363cd-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="363cd-135">Processo di modellizzazione prodotto</span><span class="sxs-lookup"><span data-stu-id="363cd-135">Product modeling process</span></span>
<span data-ttu-id="363cd-136">La sequenza naturale per generare un modello prodotto per un prodotto basato su dimensioni parte dalla definizione dei gruppi di configurazioni competenti.</span><span class="sxs-lookup"><span data-stu-id="363cd-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="363cd-137">È importante assicurarsi che tutti i prodotti che verranno utilizzati nella DBA siano stati rilasciati alla società per la quale il modello prodotto è stato sviluppato.</span><span class="sxs-lookup"><span data-stu-id="363cd-137">It is important to ensure that all products which will be used in the BOM have been relased to the company that the product model is built for.</span></span> <span data-ttu-id="363cd-138">Con queste blocchi predefiniti configurati, l'utente può creare la DBA e assegnare gruppi di configurazione in tutte le righe DBA rilevanti.</span><span class="sxs-lookup"><span data-stu-id="363cd-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="363cd-139">Quando la DBA è completata, un ciclo di lavorazione di configurazione può essere definito per l'ordine di gruppi di configurazioni nella sequenza appropriata.</span><span class="sxs-lookup"><span data-stu-id="363cd-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="363cd-140">\[caption id="attachment\_282671" align="alignnone" width="1187"\][![Processo di modellizzazione prodotto basato su dimensioni](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Processo di modellizzazione prodotto basato su dimensioni\[/caption\] Se sono disponibili alcuni prodotti provenienti da gruppi di configurazione diversi che devono o non devono essere utilizzati insieme, è possibile creare regole di configurazione che imporranno tali relazioni tra i prodotti.</span><span class="sxs-lookup"><span data-stu-id="363cd-140">\[caption id="attachment\_282671" align="alignnone" width="1187"\][![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Dimension-based product modeling process\[/caption\] If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="363cd-141">Dopo che la DBA è stata collegata a una rappresentazione generale prodotto basata su dimensioni tramite una versione DBA ed entrambe sono state approvate e attivate, è possibile creare le configurazioni prodotto e inserire un nome per ciascuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="363cd-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="363cd-142">È possibile definire le configurazioni prima che vengano generate tutte le transazioni oppure quando si verifica la necessità di una configurazione.</span><span class="sxs-lookup"><span data-stu-id="363cd-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="363cd-143">Utilizzo suggerito</span><span class="sxs-lookup"><span data-stu-id="363cd-143">Suggested use</span></span>

<span data-ttu-id="363cd-144">La tecnologia di configurazione basata su dimensioni è consigliata per i prodotti con variabilità limitata e la combinazione di dimensione, colore, stile e configurazione delle dimensioni prodotto standard è inadatta per l'identificazione di varianti prodotto specifiche.</span><span class="sxs-lookup"><span data-stu-id="363cd-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="363cd-145">Un esempio potrebbe essere bicicletta con altezza di telaio, dimensione delle rotelle, i tipi del freno e ingranaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="363cd-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>




