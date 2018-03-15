--- 
title: " Impostare regole e parametri per cross-docking e distribuzione push"
description: In questa procedura vengono descritti i passaggi per creare le regole di rifornimento.
author: josaw1
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: f3a20b7bf476cae854c7f7c86d89d73e44b6749b
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="8375a-103"> Impostare regole e parametri per cross-docking e distribuzione push</span><span class="sxs-lookup"><span data-stu-id="8375a-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8375a-104">In questa procedura vengono descritti i passaggi per creare le regole di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="8375a-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="8375a-105">Le regole di rifornimento possono essere utilizzate per controllare il modo in cui i prodotti vengono distribuiti nei punti vendita utilizzando il cross-docking e la distribuzione push.</span><span class="sxs-lookup"><span data-stu-id="8375a-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="8375a-106">Le regole di rifornimento possono essere impostate per punti vendita o gruppi di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="8375a-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="8375a-107">Il peso definito per ogni riga in una regola controllerà la quantità di prodotti che verranno distribuiti tra i punti vendita quando vengono utilizzate le regole di rifornimento come metodo di distribuzione nel cross-docking o nella distribuzione push.</span><span class="sxs-lookup"><span data-stu-id="8375a-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="8375a-108">Questa procedura utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="8375a-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="8375a-109">Passare a Regole di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="8375a-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="8375a-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8375a-110">Click New.</span></span>
3. <span data-ttu-id="8375a-111">Digitare un valore nel campo Regola di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="8375a-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="8375a-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8375a-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8375a-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8375a-113">Click Save.</span></span>
6. <span data-ttu-id="8375a-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8375a-114">Click Add.</span></span>
7. <span data-ttu-id="8375a-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8375a-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8375a-116">È possibile selezionare Gerarchia di rifornimenti o Canale per il tipo.</span><span class="sxs-lookup"><span data-stu-id="8375a-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="8375a-117">Il valore controlla se la selezione in Nome sarà una gerarchia di canali o un canale specifico.</span><span class="sxs-lookup"><span data-stu-id="8375a-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="8375a-118">Per questo esempio, lasciare il campo impostato su Gerarchia di rifornimenti.</span><span class="sxs-lookup"><span data-stu-id="8375a-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="8375a-119">Selezionare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="8375a-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="8375a-120">Il valore predefinito per il peso viene acquisito dal peso definito nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="8375a-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="8375a-121">Questo peso può essere utilizzato per la regola di rifornimento oppure è possibile immettere un nuovo peso nel campo Peso.</span><span class="sxs-lookup"><span data-stu-id="8375a-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="8375a-122">Immettere un numero nel campo Peso.</span><span class="sxs-lookup"><span data-stu-id="8375a-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="8375a-123">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8375a-123">Click Add.</span></span>
11. <span data-ttu-id="8375a-124">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8375a-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="8375a-125">Selezionare "Canale" nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="8375a-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="8375a-126">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8375a-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="8375a-127">Immettere un numero nel campo Peso.</span><span class="sxs-lookup"><span data-stu-id="8375a-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="8375a-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8375a-128">Click Save.</span></span>


