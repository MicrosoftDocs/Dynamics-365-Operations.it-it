---
title: Impostare prodotti che possono essere prodotti o ottenuti
description: 'I prodotti possono essere originati in vari modi: possono essere prodotti (fabbricati) o approvvigionati (acquistati). Questo articolo descrive alcuni punti tipici da considerare quando si configurano i prodotti per supportare l''approvvigionamento multiplo.'
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 87a6fd8ad05e460b9620855da4bcb587ad3ac3ae
ms.openlocfilehash: 2ebe639b039e58c3173e0bf3eda5ff2f0351dbeb
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="set-up-products-that-can-be-produced-or-procured"></a><span data-ttu-id="f25d6-104">Impostare prodotti che possono essere prodotti o ottenuti</span><span class="sxs-lookup"><span data-stu-id="f25d6-104">Set up products that can be produced or procured</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f25d6-105">I prodotti possono essere originati in vari modi: possono essere prodotti (fabbricati) o approvvigionati (acquistati).</span><span class="sxs-lookup"><span data-stu-id="f25d6-105">Products can be sourced in various ways -  they can be produced (manufactured) or procured (purchased).</span></span> <span data-ttu-id="f25d6-106">Questo articolo descrive alcuni punti tipici da considerare quando si configurano i prodotti per supportare l'approvvigionamento multiplo.</span><span class="sxs-lookup"><span data-stu-id="f25d6-106">This article describes some typical points to consider when you configure products to support multi-sourcing.</span></span> 

<span data-ttu-id="f25d6-107">L'approvvigionamento multiplo è in genere utilizzato per un articolo acquistato che viene prodotto occasionalmente oppure quando un articolo che era principalmente un articolo prodotto viene modificato e diventa principalmente un articolo acquistato.</span><span class="sxs-lookup"><span data-stu-id="f25d6-107">Multi-sourcing is typically used for a purchased item that is occasionally manufactured, or when an item that was primarily a manufactured item is changed so that it's now primarily a purchased item.</span></span> <span data-ttu-id="f25d6-108">L'articolo viene inizialmente designato come articolo prodotto allo scopo di definire le informazioni relative alla distinta base e al ciclo di lavorazione e di supportare gli ordini di produzione ad esso relativi.</span><span class="sxs-lookup"><span data-stu-id="f25d6-108">The item is first designated as a manufactured item, so that bill of materials (BOM) and route information can be defined, and to support production orders for the item.</span></span> <span data-ttu-id="f25d6-109">Il tipo di produzione deve essere impostato su **DBA** (o, per l'elaborazione della produzione, **Formula** o **Co-prodotto**).</span><span class="sxs-lookup"><span data-stu-id="f25d6-109">The production type should be set to **BOM** (or, for process manufacturing, **Formula** or **Co-Product**).</span></span>

<span data-ttu-id="f25d6-110">Quando si utilizza il costo standard, il record relativo al costo dell'articolo può essere calcolato per l'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="f25d6-110">When you use standard cost, the item cost record can be calculated for the manufactured item.</span></span> <span data-ttu-id="f25d6-111">Tuttavia, il record relativo al costo dell'articolo potrebbe non corrispondere al costo standard desiderato ai fini degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="f25d6-111">However, the item cost record might not match the standard cost that you want for purchasing purposes.</span></span> <span data-ttu-id="f25d6-112">In tal caso, il costo standard deve essere immesso e attivato manualmente per il record relativo al costo dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="f25d6-112">In this case, the standard cost must be manually entered and activated for the item cost record.</span></span> <span data-ttu-id="f25d6-113">Per il calcolo dei costi, si studi la possibilità di utilizzare una DBA e un ciclo di lavorazione speciali che rappresentino la combinazione di forniture del prodotto nel corso di un periodo fiscale, per ridurre gli scostamenti nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f25d6-113">For the cost calculation, consider using a special BOM and route that represent the supply mix of the product over the course of a fiscal period, to minimize the variances over time.</span></span> <span data-ttu-id="f25d6-114">Un articolo prodotto presso un sito può inoltre essere trasferito a un altro sito,</span><span class="sxs-lookup"><span data-stu-id="f25d6-114">Additionally, a manufactured item at one site can be transferred to another site.</span></span> <span data-ttu-id="f25d6-115">in modo che il relativo costo debba essere immesso e attivato manualmente per il sito a cui l'articolo viene trasferito.</span><span class="sxs-lookup"><span data-stu-id="f25d6-115">Therefore, the item's cost must be manually entered and activated for the site that the item is transferred to.</span></span> <span data-ttu-id="f25d6-116">Quando si utilizza l'articolo prodotto come componente di prodotti di livello superiore, i costi del componente devono essere considerati come un articolo acquistato</span><span class="sxs-lookup"><span data-stu-id="f25d6-116">When you use the manufactured item as a component in higher-level products, the component's costs should be treated as a purchased item.</span></span> <span data-ttu-id="f25d6-117">e tale linea guida si applica indipendentemente dal fatto che siano stati calcolati oppure immessi manualmente.</span><span class="sxs-lookup"><span data-stu-id="f25d6-117">This guideline applies, regardless of whether the component’s costs were calculated or manually entered.</span></span> <span data-ttu-id="f25d6-118">In altri termini, in un calcolo DBA i costi dell'articolo devono essere trattati come un componente acquistato anziché essere calcolati in base alle informazioni della distinta base e del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="f25d6-118">In other words, a BOM calculation should treat the item's costs as a purchased component instead of using the item's BOM and route information to calculate costs.</span></span> 

<span data-ttu-id="f25d6-119">Per impedire l'esecuzione del calcolo, selezionare il flag **Interrompi esplosione** incorporato nel gruppo di calcolo DBA assegnato all'articolo.</span><span class="sxs-lookup"><span data-stu-id="f25d6-119">To prevent the calculation from occurring, select the **Stop explosion** flag that is embedded in the BOM calculation group that is assigned to the item.</span></span> <span data-ttu-id="f25d6-120">Per impedire che i calcoli della programmazione generale facciano esplodere i fabbisogni in relazione all'articolo, impostare l'intervallo di esplosione su 0 (zero) giorni nella copertura articoli o nel gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="f25d6-120">To prevent master scheduling calculations from exploding requirements through the item, set the explosion fence to 0 (zero) days in item coverage or in the coverage group.</span></span> <span data-ttu-id="f25d6-121">Il calcolo della programmazione generale considererà quindi l'articolo come un articolo acquistato e non verranno eseguiti ulteriori calcoli per le informazioni sulla distinta base e il ciclo di lavorazione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="f25d6-121">The master scheduling calculation will then treat the item as a purchased item and won't perform more calculations for the item's BOM and route information.</span></span>






