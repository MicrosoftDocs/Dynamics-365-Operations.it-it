--- 
title: Gestire DBA per un modello di configurazione prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 380e902f9c8266f583e44fa7ea643dc5d5ab52d3
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="39fa0-103">Gestire DBA per un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="39fa0-103">Maintain BOM for a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="39fa0-104">L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.</span><span class="sxs-lookup"><span data-stu-id="39fa0-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="39fa0-105">Il modello High end speaker della società di dati dimostrativi USMF è utilizzato per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="39fa0-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="39fa0-106">Aggiungere una riga DBA</span><span class="sxs-lookup"><span data-stu-id="39fa0-106">Add a BOM line</span></span>
1. <span data-ttu-id="39fa0-107">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="39fa0-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="39fa0-108">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="39fa0-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="39fa0-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="39fa0-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="39fa0-110">Selezionare High end speaker per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="39fa0-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="39fa0-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="39fa0-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="39fa0-112">Espandere la sezione Righe DBA.</span><span class="sxs-lookup"><span data-stu-id="39fa0-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="39fa0-113">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="39fa0-113">Click Add.</span></span>
7. <span data-ttu-id="39fa0-114">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="39fa0-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="39fa0-115">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="39fa0-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="39fa0-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="39fa0-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="39fa0-117">Aggiungere i dettagli riga DBA</span><span class="sxs-lookup"><span data-stu-id="39fa0-117">Add BOM line details</span></span>
1. <span data-ttu-id="39fa0-118">Fare clic su Dettagli riga DBA.</span><span class="sxs-lookup"><span data-stu-id="39fa0-118">Click BOM line details.</span></span>
2. <span data-ttu-id="39fa0-119">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="39fa0-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="39fa0-120">Ad esempio, è possibile selezionare l'articolo M0055.</span><span class="sxs-lookup"><span data-stu-id="39fa0-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="39fa0-121">Per ogni proprietà di riga DBA, è possibile scegliere se prende un valore fisso o viene sottoposta al mapping a un attributo.</span><span class="sxs-lookup"><span data-stu-id="39fa0-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="39fa0-122">Selezionare la casella di controllo Imposta.</span><span class="sxs-lookup"><span data-stu-id="39fa0-122">Select the Set check box.</span></span>
4. <span data-ttu-id="39fa0-123">Selezionare Sì nel campo Calcolo.</span><span class="sxs-lookup"><span data-stu-id="39fa0-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="39fa0-124">Impostando la proprietà Calcolo su Sì, si garantisce che la riga DBA venga inclusa nei calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="39fa0-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="39fa0-125">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="39fa0-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="39fa0-126">Selezionare la casella di controllo Imposta.</span><span class="sxs-lookup"><span data-stu-id="39fa0-126">Select the Set check box.</span></span>
7. <span data-ttu-id="39fa0-127">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="39fa0-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="39fa0-128">Il campo Quantità determina la quantità dell'articolo che verrà incluso nella DBA.</span><span class="sxs-lookup"><span data-stu-id="39fa0-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="39fa0-129">Ovviamente può essere utilizzato per il mapping di attributo.</span><span class="sxs-lookup"><span data-stu-id="39fa0-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="39fa0-130">Fare clic sulla scheda Dimensione.</span><span class="sxs-lookup"><span data-stu-id="39fa0-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="39fa0-131">Verificare se le dimensioni prodotto sono attive e nel qual caso è necessario assegnare un valore o un attributo.</span><span class="sxs-lookup"><span data-stu-id="39fa0-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="39fa0-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="39fa0-132">Click OK.</span></span>


