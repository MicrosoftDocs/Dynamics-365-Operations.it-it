---
title: Creare e assegnare strutture di regole avanzate
description: Questa guida di attività descrive come creare e assegnare una struttura di regole avanzate a una struttura dei conti.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd62254c20cf5d77677d03c7d7335fb793d7f5f2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558908"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="f917b-103">Creare e assegnare strutture di regole avanzate</span><span class="sxs-lookup"><span data-stu-id="f917b-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f917b-104">Questa guida di attività descrive come creare e assegnare una struttura di regole avanzate a una struttura dei conti.</span><span class="sxs-lookup"><span data-stu-id="f917b-104">This task guide steps through creating and assigning an advanced rule structure to an account structure.</span></span> <span data-ttu-id="f917b-105">Questa guida utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="f917b-105">This guide uses the USMF demo company.</span></span>


## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="f917b-106">Crea una struttura di regole avanzate</span><span class="sxs-lookup"><span data-stu-id="f917b-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="f917b-107">Andare a Contabilità generale > Piano dei conti > Strutture > Strutture regole avanzate.</span><span class="sxs-lookup"><span data-stu-id="f917b-107">Go to General ledger > Chart of accounts > Structures > Advanced rule structures.</span></span>
2. <span data-ttu-id="f917b-108">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f917b-108">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="f917b-109">Nel campo Struttura regole avanzate, digitare un nome per descrivere la struttura delle regole.</span><span class="sxs-lookup"><span data-stu-id="f917b-109">In the Advanced rule structure field, type a name to descritbe the rule structure.</span></span>
4. <span data-ttu-id="f917b-110">Nel campo Descrizione, immettere un valore per descrivere la struttura.</span><span class="sxs-lookup"><span data-stu-id="f917b-110">In the Description field, type a value to describe the structure.</span></span>
5. <span data-ttu-id="f917b-111">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f917b-111">Click OK.</span></span>
6. <span data-ttu-id="f917b-112">Fare clic su Aggiungi segmento.</span><span class="sxs-lookup"><span data-stu-id="f917b-112">Click Add segment.</span></span>
7. <span data-ttu-id="f917b-113">Selezionare una dimensione finanziaria nell'elenco di segmenti.</span><span class="sxs-lookup"><span data-stu-id="f917b-113">In the list of segments, select a financial dimension.</span></span>
    * <span data-ttu-id="f917b-114">Ad esempio, Punto vendita.</span><span class="sxs-lookup"><span data-stu-id="f917b-114">For example, Store.</span></span>  
8. <span data-ttu-id="f917b-115">Fare clic su Aggiungi segmento.</span><span class="sxs-lookup"><span data-stu-id="f917b-115">Click Add segment.</span></span>
9. <span data-ttu-id="f917b-116">Nell'elenco, fare clic sul collegamento della struttura di regole avanzate per visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="f917b-116">In the list, click the link of the advanced rule structure to view it.</span></span>
10. <span data-ttu-id="f917b-117">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="f917b-117">Click Activate.</span></span>
11. <span data-ttu-id="f917b-118">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="f917b-118">Click Activate.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="f917b-119">Applicare una struttura di regole avanzate a una struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="f917b-119">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="f917b-120">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="f917b-120">Close the form.</span></span>
2. <span data-ttu-id="f917b-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f917b-121">Close the page.</span></span>
3. <span data-ttu-id="f917b-122">Andare a Contabilità generale > Piano dei conti > Strutture > Configura strutture dei conti.</span><span class="sxs-lookup"><span data-stu-id="f917b-122">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
4. <span data-ttu-id="f917b-123">Nell'elenco, trovare e selezionare la struttura dei conti a cui applicare la regola avanzata.</span><span class="sxs-lookup"><span data-stu-id="f917b-123">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
5. <span data-ttu-id="f917b-124">Fare clic sul nome della struttura dei conti per aprirla.</span><span class="sxs-lookup"><span data-stu-id="f917b-124">Click the name of the account structure to open it.</span></span>
6. <span data-ttu-id="f917b-125">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="f917b-125">Click Edit.</span></span>
    * <span data-ttu-id="f917b-126">È inoltre possibile fare clic su Regole avanzate e verrà richiesto di inserire la struttura dei conti in modalità di bozza.</span><span class="sxs-lookup"><span data-stu-id="f917b-126">You can also click Advanced rules and you will be prompted to put the account structure in Draft mode.</span></span>  
7. <span data-ttu-id="f917b-127">Fare clic su Regole avanzate.</span><span class="sxs-lookup"><span data-stu-id="f917b-127">Click Advanced rules.</span></span>
8. <span data-ttu-id="f917b-128">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f917b-128">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="f917b-129">Digitare un valore nel campo Regola avanzata.</span><span class="sxs-lookup"><span data-stu-id="f917b-129">In the Advanced rule field, type a value.</span></span>
10. <span data-ttu-id="f917b-130">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f917b-130">In the Name field, type a value.</span></span>
11. <span data-ttu-id="f917b-131">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="f917b-131">Click Create.</span></span>
12. <span data-ttu-id="f917b-132">Fare clic su Aggiungi nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="f917b-132">Click Add new criteria.</span></span>
13. <span data-ttu-id="f917b-133">Nel campo Percorso, selezionare un conto principale o una dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="f917b-133">In the Where field, select main account or a financial dimension.</span></span>
14. <span data-ttu-id="f917b-134">Nel campo Operatore, selezionare un'opzione, ad esempio è compreso in e include.</span><span class="sxs-lookup"><span data-stu-id="f917b-134">In the Operator field, select an option, such as is between and includes.</span></span>
15. <span data-ttu-id="f917b-135">Digitare un valore nel campo Valore.</span><span class="sxs-lookup"><span data-stu-id="f917b-135">In the Value field, type a value.</span></span>
16. <span data-ttu-id="f917b-136">Digitare un valore nel campo attraverso.</span><span class="sxs-lookup"><span data-stu-id="f917b-136">In the through field, type a value.</span></span>
17. <span data-ttu-id="f917b-137">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f917b-137">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="f917b-138">Nell'elenco, individuare la struttura di regole avanzate da utilizzare quando vengono soddisfatti i criteri immessi.</span><span class="sxs-lookup"><span data-stu-id="f917b-138">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
19. <span data-ttu-id="f917b-139">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="f917b-139">Click Add.</span></span>
20. <span data-ttu-id="f917b-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f917b-140">Close the page.</span></span>
21. <span data-ttu-id="f917b-141">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="f917b-141">Click Activate.</span></span>
22. <span data-ttu-id="f917b-142">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="f917b-142">Click Activate.</span></span>

