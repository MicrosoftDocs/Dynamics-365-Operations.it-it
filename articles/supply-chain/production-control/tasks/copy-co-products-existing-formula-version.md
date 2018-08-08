--- 
title: Copiare co-prodotti da una versione di formula esistente
description: Questa procedura mostra come copiare i co-prodotti da una versione di formula esistente in una versione di formula diversa per un prodotto rilasciato.
author: ShylaThompson
manager: AnnBe
ms.date: 06/06/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: a3620fe90826360616793962acb86b0aab7cefe5
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="4a4f0-103">Copiare co-prodotti da una versione di formula esistente</span><span class="sxs-lookup"><span data-stu-id="4a4f0-103">Copy co-products from an existing formula version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4a4f0-104">Questa procedura mostra come copiare i co-prodotti da una versione di formula esistente in una versione di formula diversa per un prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="4a4f0-105">Esiste un prerequisito per cui è presente almeno una versione di formula associata a co-prodotti.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="4a4f0-106">La società di dati dimostrativi USP2 è utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="4a4f0-107">Trovare un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="4a4f0-107">Find a released product</span></span>
1. <span data-ttu-id="4a4f0-108">Fare clic su Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-108">Go to Released products.</span></span>
2. <span data-ttu-id="4a4f0-109">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-109">Click Show filters.</span></span>
    * <span data-ttu-id="4a4f0-110">Il campo Tipo di produzione sta per essere aggiunto nella finestra di dialogo Filtro.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="4a4f0-111">Fare clic su Aggiungi un campo di filtro per aggiungere il campo Tipo di produzione.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="4a4f0-112">Al passaggio successivo è necessario immettere manualmente la formula nel campo Tipo di produzione prima di selezionare Applica.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="4a4f0-113">Questa imposta il filtro nell'elenco dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="4a4f0-114">Immettere manualmente la formula nel campo del Tipo di produzione.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="4a4f0-115">Fare clic su Applica.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="4a4f0-116">Selezionare un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="4a4f0-116">Select a released product</span></span>
1. <span data-ttu-id="4a4f0-117">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="4a4f0-118">Fare clic su Versioni formula.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-118">Click Formula versions.</span></span>
    * <span data-ttu-id="4a4f0-119">Nel riquadro azioni di progettazione, fare clic su Versioni formula.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="4a4f0-120">Copiare co-prodotti</span><span class="sxs-lookup"><span data-stu-id="4a4f0-120">Copy co-products</span></span>
1. <span data-ttu-id="4a4f0-121">Nel riquadro azioni, fare clic su Versione formula.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="4a4f0-122">Fare clic su Co-prodotti.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-122">Click Co-products.</span></span>
3. <span data-ttu-id="4a4f0-123">Fare clic su Copia.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-123">Click Copy.</span></span>
4. <span data-ttu-id="4a4f0-124">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="4a4f0-125">Nel campo Versione formula immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="4a4f0-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-126">Click OK.</span></span>
7. <span data-ttu-id="4a4f0-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4a4f0-127">Close the page.</span></span>


