---
title: Eseguire le operazioni preliminari alla gestione dei costi standard per gli articoli prodotti
description: In questo argomento vengono descritti i passaggi per la gestione dei costi per gli articoli prodotti.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 866da2ce58e33676c2fa4bb2d6abfde891a5d021
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214598"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a><span data-ttu-id="2c6d1-103">Eseguire le operazioni preliminari alla gestione dei costi standard per gli articoli prodotti</span><span class="sxs-lookup"><span data-stu-id="2c6d1-103">Prepare to maintain standard costs for manufactured items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c6d1-104">In questo argomento vengono descritti i passaggi per la gestione dei costi per gli articoli prodotti.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-104">This topic describes the steps for preparing to maintain costs for manufactured items.</span></span> <span data-ttu-id="2c6d1-105">I passaggi per gli articoli prodotti sono leggermente diversi dai passaggi per gli articoli acquistati.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-105">The steps for manufactured items differ slightly from the steps for purchased items.</span></span>

<span data-ttu-id="2c6d1-106">I criteri che vengono assegnati agli articoli prodotti possono incidere sui calcoli dei costi degli articoli prodotti principali.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-106">Policies that are assigned to manufactured items can affect the cost calculations for the parent manufactured items.</span></span> <span data-ttu-id="2c6d1-107">Per la preparazione alla gestione dei costi degli articoli prodotti effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-107">To prepare to maintain costs for manufactured items, follow these steps.</span></span>

1. <span data-ttu-id="2c6d1-108">Assegnare un gruppo di modelli di articoli all'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-108">Assign an item model group to the manufactured item.</span></span> 

   <span data-ttu-id="2c6d1-109">Il gruppo di modelli di articoli identifica i costi standard che verranno utilizzati.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-109">The item model group identifies that standard costs will be used.</span></span>

2. <span data-ttu-id="2c6d1-110">Assegnare un gruppo di articoli all'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-110">Assign an item group to the manufactured item.</span></span> 

   <span data-ttu-id="2c6d1-111">Nel gruppo di articoli sono contenuti conti CoGe validi per l'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-111">The item group contains ledger accounts that apply to the manufactured item.</span></span> <span data-ttu-id="2c6d1-112">Nei conti CoGe di un articolo prodotto associato a un modello inventariale Costo standard sono inclusi diversi scostamenti produzione, lo scostamento delle variazioni di costo e la rivalutazione del costo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-112">The ledger accounts for a manufactured item that has a standard cost inventory model include several production variances, the cost change variance, and the inventory cost revaluation.</span></span>

3. <span data-ttu-id="2c6d1-113">Assegnare l'unità di misura di magazzino all'articolo.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-113">Assign the inventory unit of measure to the item.</span></span> 

   <span data-ttu-id="2c6d1-114">I costi dell'articolo sono sempre espressi nell'unità di misura di magazzino dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-114">The item's costs are always expressed in the item's inventory unit of measure.</span></span>

4. <span data-ttu-id="2c6d1-115">Non assegnare un gruppo di costi all'articolo prodotto, a meno che l'articolo non debba essere gestito come articolo acquistato.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-115">Don't assign a cost group to the manufactured item unless the item will be treated as a purchased item.</span></span>

5. <span data-ttu-id="2c6d1-116">Assegnare un gruppo di calcolo distinta base (DBA) all'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-116">Assign a bill of materials (BOM) calculation group to the manufactured item.</span></span> 

   <span data-ttu-id="2c6d1-117">Il gruppo di calcolo DBA dell'articolo definisce le condizioni di avviso applicabili.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-117">The item's BOM calculation group defines warning conditions that apply.</span></span> <span data-ttu-id="2c6d1-118">In questo modo, quando un calcolo DBA viene eseguito, i messaggi di avviso possono essere generati relativamente a possibili origini di errori di calcolo.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-118">In that way, when a BOM calculation is done, warning messages can be generated about possible sources of calculation errors.</span></span> <span data-ttu-id="2c6d1-119">In un messaggio di avviso ad esempio, può essere segnalato se non è presente una DBA o un ciclo di lavorazione attivo.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-119">For example, a warning message can identify when an active BOM or route doesn't exist.</span></span> <span data-ttu-id="2c6d1-120">Nel gruppo di calcolo DBA è contenuto un criterio di interruzione esplosione che indica quando deve essere gestito un articolo prodotto come articolo acquistato.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-120">The BOM calculation group contains a stop explosion policy that indicates when a manufactured item should be treated as a purchased item.</span></span>

6. <span data-ttu-id="2c6d1-121">Se l'articolo prodotto ha dei costi costanti, assegnare una quantità ordine standard ad esso.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-121">If the manufactured item has constant costs, assign a standard order quantity to it.</span></span> 

   <span data-ttu-id="2c6d1-122">La quantità ordine standard rappresenta le dimensioni lotto di contabilità per ammortizzare i costi costanti,</span><span class="sxs-lookup"><span data-stu-id="2c6d1-122">The standard order quantity is an accounting lot size for amortizing constant costs.</span></span> <span data-ttu-id="2c6d1-123">Esempi di costi costanti includono i tempi di impostazione nelle operazioni dei cicli di lavorazione e una quantità di componenti costante nella distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="2c6d1-123">Examples of constant costs include setup times in routing operations and a constant component quantity in the BOM.</span></span>

7. <span data-ttu-id="2c6d1-124">Definire la DBA per l'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-124">Define the BOM for the manufactured item.</span></span> 

   <span data-ttu-id="2c6d1-125">È possibile definire una o più versioni DBA per l'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-125">One or more BOM versions can be defined for the manufactured item.</span></span> <span data-ttu-id="2c6d1-126">Verificare che le versioni desiderate siano state contrassegnate come approvate e attive e che le date di validità siano quelle desiderate.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-126">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="2c6d1-127">La versione DBA può essere a livello aziendale o specifica di un sito.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-127">The BOM version can be company-wide or site-specific.</span></span>

8. <span data-ttu-id="2c6d1-128">Definire il ciclo di lavorazione dell'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-128">Define the routing for the manufactured item.</span></span> 

   <span data-ttu-id="2c6d1-129">È possibile definire una o più versioni di cicli di lavorazione per l'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-129">One or more route versions can be defined for the manufactured item.</span></span> <span data-ttu-id="2c6d1-130">Verificare che le versioni desiderate siano state contrassegnate come approvate e attive e che le date di validità siano quelle desiderate.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-130">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="2c6d1-131">La versione del ciclo di lavorazione deve essere specifica di un sito.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-131">The route version must be site-specific.</span></span>

<span data-ttu-id="2c6d1-132">Se si desidera utilizzare informazioni del ciclo di lavorazione per la determinazione costi sono necessari ulteriori operazioni di preparazione.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-132">If you want to use routing information for costing purposes, additional preparation steps are required.</span></span> <span data-ttu-id="2c6d1-133">Le categorie di costo assegnate alle operazioni dei cicli di lavorazione ad esempio devono essere corrette e complete.</span><span class="sxs-lookup"><span data-stu-id="2c6d1-133">For example, the cost categories that are assigned to routing operations must be correct and completed.</span></span>

<a name="related-topics"></a><span data-ttu-id="2c6d1-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2c6d1-134">Related topics</span></span>
--------

[<span data-ttu-id="2c6d1-135">Ammortamento dei costi costanti per un articolo prodotto</span><span class="sxs-lookup"><span data-stu-id="2c6d1-135">Amortize constant costs for a manufactured item</span></span>](amortize-constant-costs-manufactured-item.md)

[<span data-ttu-id="2c6d1-136">Impostare prodotti che possono essere prodotti o ottenuti</span><span class="sxs-lookup"><span data-stu-id="2c6d1-136">Set up products that can be produced or procured</span></span>](manufactured-items-treated-as-purchased-items.md)

