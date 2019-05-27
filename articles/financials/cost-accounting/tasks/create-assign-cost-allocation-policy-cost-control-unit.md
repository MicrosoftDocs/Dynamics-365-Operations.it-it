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
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 92f41eb99b84bbc596e79b413971f9d92f2555b6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543912"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="d1a81-103">Creare e assegnare i criteri di allocazione costi a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="d1a81-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d1a81-104">Utilizzare questa procedura per creare e assegnare i criteri di allocazione costi e le regole corrispondenti a un'unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="d1a81-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="d1a81-105">Questa registrazione utilizza i dati dimostrativi della società USP2.</span><span class="sxs-lookup"><span data-stu-id="d1a81-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="d1a81-106">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="d1a81-106">Create a policy</span></span>
1. <span data-ttu-id="d1a81-107">Andare a Contabilità industriale > Criteri > Criteri di allocazione costi.</span><span class="sxs-lookup"><span data-stu-id="d1a81-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="d1a81-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d1a81-108">Click New.</span></span>
3. <span data-ttu-id="d1a81-109">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="d1a81-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="d1a81-110">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="d1a81-111">Selezionare Organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1a81-111">Select Organization.</span></span>  
5. <span data-ttu-id="d1a81-112">Nel campo Dimensione statistica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="d1a81-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d1a81-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="d1a81-114">Creare regole di allocazione</span><span class="sxs-lookup"><span data-stu-id="d1a81-114">Create allocation rules</span></span>
1. <span data-ttu-id="d1a81-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d1a81-115">Click New.</span></span>
2. <span data-ttu-id="d1a81-116">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d1a81-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="d1a81-117">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="d1a81-118">Nel campo Comportamento costo selezionare "Totale".</span><span class="sxs-lookup"><span data-stu-id="d1a81-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="d1a81-119">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="d1a81-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d1a81-120">Click New.</span></span>
7. <span data-ttu-id="d1a81-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d1a81-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="d1a81-122">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="d1a81-123">Nel campo Comportamento costo selezionare "Totale".</span><span class="sxs-lookup"><span data-stu-id="d1a81-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="d1a81-124">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="d1a81-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d1a81-125">Click New.</span></span>
12. <span data-ttu-id="d1a81-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d1a81-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="d1a81-127">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="d1a81-128">Nel campo Comportamento costo selezionare "Totale".</span><span class="sxs-lookup"><span data-stu-id="d1a81-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="d1a81-129">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="d1a81-130">Continuare fino a quando non sono state create tutte le regole.</span><span class="sxs-lookup"><span data-stu-id="d1a81-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="d1a81-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d1a81-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="d1a81-132">Assegnare i criteri a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="d1a81-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="d1a81-133">Fare clic su Assegnazioni criteri per unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="d1a81-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="d1a81-134">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d1a81-134">Click New.</span></span>
3. <span data-ttu-id="d1a81-135">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d1a81-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d1a81-136">Immettere una data nel campo Valido dalla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1a81-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="d1a81-137">Le regole hanno una data di validità.</span><span class="sxs-lookup"><span data-stu-id="d1a81-137">The rules are date-effective.</span></span> <span data-ttu-id="d1a81-138">Un utente o il sistema può farle scadere se ne viene creata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="d1a81-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="d1a81-139">Nel campo Unità di controllo costi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1a81-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="d1a81-140">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d1a81-140">Click Save.</span></span>

