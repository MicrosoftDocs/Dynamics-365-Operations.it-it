---
title: Creare e assegnare i criteri di allocazione costi a un'unità di controllo costi
description: Utilizzare questa procedura per creare e assegnare i criteri di allocazione costi e le regole corrispondenti a un'unità di controllo costi.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f0422a9aaf95184b556293bf6ebcaf4dcfb5b59
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178475"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="b4d53-103">Creare e assegnare i criteri di allocazione costi a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="b4d53-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b4d53-104">Utilizzare questa procedura per creare e assegnare i criteri di allocazione costi e le regole corrispondenti a un'unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="b4d53-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="b4d53-105">Questa registrazione utilizza i dati dimostrativi della società USP2.</span><span class="sxs-lookup"><span data-stu-id="b4d53-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="b4d53-106">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="b4d53-106">Create a policy</span></span>
1. <span data-ttu-id="b4d53-107">Andare a Contabilità industriale > Criteri > Criteri di allocazione costi.</span><span class="sxs-lookup"><span data-stu-id="b4d53-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="b4d53-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b4d53-108">Click New.</span></span>
3. <span data-ttu-id="b4d53-109">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="b4d53-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="b4d53-110">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="b4d53-111">Selezionare Organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b4d53-111">Select Organization.</span></span>  
5. <span data-ttu-id="b4d53-112">Nel campo Dimensione statistica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="b4d53-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b4d53-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="b4d53-114">Creare regole di allocazione</span><span class="sxs-lookup"><span data-stu-id="b4d53-114">Create allocation rules</span></span>
1. <span data-ttu-id="b4d53-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b4d53-115">Click New.</span></span>
2. <span data-ttu-id="b4d53-116">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b4d53-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="b4d53-117">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="b4d53-118">Nel campo Comportamento costo selezionare "Totale".</span><span class="sxs-lookup"><span data-stu-id="b4d53-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="b4d53-119">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="b4d53-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b4d53-120">Click New.</span></span>
7. <span data-ttu-id="b4d53-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b4d53-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="b4d53-122">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="b4d53-123">Nel campo Comportamento costo selezionare "Totale".</span><span class="sxs-lookup"><span data-stu-id="b4d53-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="b4d53-124">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="b4d53-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b4d53-125">Click New.</span></span>
12. <span data-ttu-id="b4d53-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b4d53-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="b4d53-127">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="b4d53-128">Nel campo Comportamento costo selezionare "Totale".</span><span class="sxs-lookup"><span data-stu-id="b4d53-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="b4d53-129">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="b4d53-130">Continuare fino a quando non sono state create tutte le regole.</span><span class="sxs-lookup"><span data-stu-id="b4d53-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="b4d53-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b4d53-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="b4d53-132">Assegnare i criteri a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="b4d53-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="b4d53-133">Fare clic su Assegnazioni criteri per unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="b4d53-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="b4d53-134">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b4d53-134">Click New.</span></span>
3. <span data-ttu-id="b4d53-135">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b4d53-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b4d53-136">Immettere una data nel campo Valido dalla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="b4d53-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="b4d53-137">Le regole hanno una data di validità.</span><span class="sxs-lookup"><span data-stu-id="b4d53-137">The rules are date-effective.</span></span> <span data-ttu-id="b4d53-138">Un utente o il sistema può farle scadere se ne viene creata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="b4d53-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="b4d53-139">Nel campo Unità di controllo costi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b4d53-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="b4d53-140">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b4d53-140">Click Save.</span></span>

