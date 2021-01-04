---
title: Copiare co-prodotti da una versione di formula esistente
description: Questa procedura mostra come copiare i co-prodotti da una versione di formula esistente in una versione di formula diversa per un prodotto rilasciato.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 79b70ccbdac2061baf3896ecbd9449da3c38842a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430876"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="4cb7c-103">Copiare co-prodotti da una versione di formula esistente</span><span class="sxs-lookup"><span data-stu-id="4cb7c-103">Copy co-products from an existing formula version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4cb7c-104">Questa procedura mostra come copiare i co-prodotti da una versione di formula esistente in una versione di formula diversa per un prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="4cb7c-105">Esiste un prerequisito per cui è presente almeno una versione di formula associata a co-prodotti.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="4cb7c-106">La società di dati dimostrativi USP2 è utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="4cb7c-107">Trovare un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="4cb7c-107">Find a released product</span></span>
1. <span data-ttu-id="4cb7c-108">Fare clic su Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-108">Go to Released products.</span></span>
2. <span data-ttu-id="4cb7c-109">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-109">Click Show filters.</span></span>
    * <span data-ttu-id="4cb7c-110">Il campo Tipo di produzione sta per essere aggiunto nella finestra di dialogo Filtro.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="4cb7c-111">Fare clic su Aggiungi un campo di filtro per aggiungere il campo Tipo di produzione.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="4cb7c-112">Al passaggio successivo è necessario immettere manualmente la formula nel campo Tipo di produzione prima di selezionare Applica.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="4cb7c-113">Questa imposta il filtro nell'elenco dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="4cb7c-114">Immettere manualmente la formula nel campo del Tipo di produzione.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="4cb7c-115">Fare clic su Applica.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="4cb7c-116">Selezionare un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="4cb7c-116">Select a released product</span></span>
1. <span data-ttu-id="4cb7c-117">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="4cb7c-118">Fare clic su Versioni formula.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-118">Click Formula versions.</span></span>
    * <span data-ttu-id="4cb7c-119">Nel riquadro azioni di progettazione, fare clic su Versioni formula.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="4cb7c-120">Copiare co-prodotti</span><span class="sxs-lookup"><span data-stu-id="4cb7c-120">Copy co-products</span></span>
1. <span data-ttu-id="4cb7c-121">Nel riquadro azioni, fare clic su Versione formula.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="4cb7c-122">Fare clic su Co-prodotti.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-122">Click Co-products.</span></span>
3. <span data-ttu-id="4cb7c-123">Fare clic su Copia.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-123">Click Copy.</span></span>
4. <span data-ttu-id="4cb7c-124">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="4cb7c-125">Nel campo Versione formula immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="4cb7c-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-126">Click OK.</span></span>
7. <span data-ttu-id="4cb7c-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4cb7c-127">Close the page.</span></span>

