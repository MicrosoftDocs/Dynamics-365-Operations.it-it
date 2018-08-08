---
title: Rifornimento immediato
description: In questo argomento viene descritto come utilizzare il rifornimento immediato per il rifornimento del magazzino quando una direttiva ubicazione non riesce ad allocare scorte.
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: ab1f06951d5daceaf002b2cc23236dd818457985
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="immediate-replenishment"></a><span data-ttu-id="41d18-103">Rifornimento immediato</span><span class="sxs-lookup"><span data-stu-id="41d18-103">Immediate replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41d18-104">Il rifornimento immediato consente di rifornire il magazzino immediatamente dopo che una riga di direttiva ubicazione non è riuscita ad allocare scorte.</span><span class="sxs-lookup"><span data-stu-id="41d18-104">Immediate replenishment lets you replenish inventory immediately after a location directive line fails to allocate inventory.</span></span> <span data-ttu-id="41d18-105">Il rifornimento si basa su una singola riga nell'impostazione della direttiva ubicazione.</span><span class="sxs-lookup"><span data-stu-id="41d18-105">The replenishment is based on a single line in the setup of the location directive.</span></span> <span data-ttu-id="41d18-106">Se non sono disponibili scorte nell'unità di misura specificata dalla riga, il rifornimento di tale unità di misura viene eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="41d18-106">If inventory isn't on hand in the unit of measure that is specified by that line, replenishment of that unit of measure occurs immediately.</span></span>

<span data-ttu-id="41d18-107">Il rifornimento immediato rappresenta un'alternativa al metodo in cui l'allocazione delle scorte si base su più righe nella direttiva ubicazione e in cui la domanda viene sommata alla fine dell'allocazione e rifornita nell'unità di misura specificata dall'ultima riga della direttiva ubicazione.</span><span class="sxs-lookup"><span data-stu-id="41d18-107">Immediate replenishment provides an alternative to the method where the allocation of inventory is based on more lines in the location directive, and where the demand is summed at the end of the allocation and replenished in the unit of measure that is specified by the last line in the location directive.</span></span>

<span data-ttu-id="41d18-108">I vantaggi offerti dal rifornimento immediato sono che il rifornimento può essere limitato da unità specifiche e la quantità può essere indirizzata a ubicazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="41d18-108">The benefits of using immediate replenishment are that replenishment can be limited by specific units and the quantity can be directed to specific locations.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="41d18-109">Scenario aziendale</span><span class="sxs-lookup"><span data-stu-id="41d18-109">Business scenario</span></span>

<span data-ttu-id="41d18-110">Ad esempio, si dispone di un magazzino che ha aree di prelievo diverse per le unità di misura "scatola" e "singola unità".</span><span class="sxs-lookup"><span data-stu-id="41d18-110">For example, you have a warehouse that has separate picking areas for the "box" and "each" units of measure.</span></span> <span data-ttu-id="41d18-111">Si desidera ottimizzare il processo di prelievo selezionando quante più scatole possibili e successivamente selezionando la quantità rimanente che è minore di una scatola dall'area "singola unità".</span><span class="sxs-lookup"><span data-stu-id="41d18-111">You want to optimize the picking process by picking as many boxes as possible and then picking any remaining quantity that is less than a box from the "each" area.</span></span>

<span data-ttu-id="41d18-112">In questo caso, è possibile utilizzare il rifornimento immediato.</span><span class="sxs-lookup"><span data-stu-id="41d18-112">In this case, you can use immediate replenishment.</span></span> <span data-ttu-id="41d18-113">Nella direttiva ubicazione, è possibile impostare il rifornimento immediato per le scatole in modo da utilizzare il rifornimento della domanda non appena si verifica una carenza di scatole che possono essere prelevate per la quantità della domanda.</span><span class="sxs-lookup"><span data-stu-id="41d18-113">In the location directive, you can set up immediate replenishment for boxes so that demand replenishment is used as soon as there is a shortage of boxes that can be picked for the demand quantity.</span></span> <span data-ttu-id="41d18-114">In questo modo, si ottimizza il processo di prelievo in modo che il prelievo includa quante più scatole possibili.</span><span class="sxs-lookup"><span data-stu-id="41d18-114">In this way, you optimize the picking process so that picking includes as many boxes as possible.</span></span> <span data-ttu-id="41d18-115">Il rifornimento immediato genererà il rifornimento delle scatole e la domanda non verrà superata cosicché le quantità verranno prelevate nell'unità di misura "singola unità".</span><span class="sxs-lookup"><span data-stu-id="41d18-115">Immediate replenishment will generate replenishment of the boxes, and the demand won't be passed on so that the quantities are picked in the "each" unit of measure.</span></span> <span data-ttu-id="41d18-116">In altre parole, solo le quantità che si suppone vengano prelevate nell'unità di misura "singola unità" (vale a dire le quantità che sono minori di una scatola) verranno prelevate dall'area "singola unità".</span><span class="sxs-lookup"><span data-stu-id="41d18-116">In other words, only the quantities that are supposed to be picked in the "each" unit of measure (that is, quantities that are less than a box) will be picked from the "each" area.</span></span> <span data-ttu-id="41d18-117">Se nell'area "scatola" si verifica una carenza, è possibile prelevare quante più scatole possibili dalla domanda totale.</span><span class="sxs-lookup"><span data-stu-id="41d18-117">If a shortage occurs in the "box" area, you can pick as many boxes as possible out of the total demand.</span></span> <span data-ttu-id="41d18-118">Le quantità rimanenti verranno prelevate dall'area "singola unità".</span><span class="sxs-lookup"><span data-stu-id="41d18-118">The remaining quantities will then be picked from the "each" area.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="41d18-119">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="41d18-119">Where it applies</span></span>

<span data-ttu-id="41d18-120">Il rifornimento immediato viene utilizzato durante l'esecuzione dell'ondata se l'allocazione ha esito negativo per una riga di direttiva ubicazione per la quale è impostato un modello di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="41d18-120">Immediate replenishment is used during wave execution if allocation fails for a location directive line that a replenishment template is set for.</span></span>

## <a name="set-up-immediate-replenishment"></a><span data-ttu-id="41d18-121">Impostare il rifornimento immediato</span><span class="sxs-lookup"><span data-stu-id="41d18-121">Set up immediate replenishment</span></span>

- <span data-ttu-id="41d18-122">Passare a **Gestione magazzino** \> **Impostazioni** \> **Direttive ubicazione**, quindi nella scheda **Righe**, nell'elenco **Modello per il rifornimento immediato**, selezionare un modello di rifornimento per la domanda di ondata.</span><span class="sxs-lookup"><span data-stu-id="41d18-122">Go to **Warehouse management** \> **Setup** \> **Location directives**, and then, on the **Lines** tab, in the **Immediate replenishment template** list, select a replenishment template for wave demand.</span></span>

<span data-ttu-id="41d18-123">Il modello di rifornimento viene applicato se la riga di direttiva ubicazione non riesce ad allocare un'unità di misura dedicata.</span><span class="sxs-lookup"><span data-stu-id="41d18-123">The replenishment template is applied if the location directive line fails to allocate a dedicated unit of measure.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="41d18-124">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="41d18-124">Troubleshooting</span></span>

<span data-ttu-id="41d18-125">Se si seleziona il rifornimento immediato per una riga di direttiva ubicazione, ma non viene generato alcun lavoro di rifornimento quando si utilizzano modelli di rifornimento della domanda per quella riga di direttiva ubicazione, possono esserci due cause:</span><span class="sxs-lookup"><span data-stu-id="41d18-125">If immediate replenishment is selected for a location directive line, but no replenishment work is generated when you use demand replenishment templates for that location directive line, two main causes must be investigated:</span></span>

- <span data-ttu-id="41d18-126">Assicurarsi che il modello di rifornimento della domanda applicato sia impostato in modo da utilizzare i modelli di ubicazione corretti e i modelli di lavoro del tipo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="41d18-126">Make sure that the demand replenishment template that is applied is set up to use the correct location templates and work templates of the **Replenishment** type.</span></span>
- <span data-ttu-id="41d18-127">Assicurarsi che ci siano scorte disponibili sufficienti presso le ubicazioni in cui il modello di rifornimento della domanda cerca le scorte disponibili per il rifornimento.</span><span class="sxs-lookup"><span data-stu-id="41d18-127">Make sure that there is enough on-hand inventory at the locations where the demand replenishment template searches for on-hand inventory for replenishment.</span></span>

