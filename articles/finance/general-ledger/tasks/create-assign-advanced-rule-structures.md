---
title: Creare e assegnare strutture di regole avanzate
description: In questo argomento viene descritto come creare e assegnare una struttura di regole avanzate a una struttura dei conti.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e6a3f7d174c91e357dce8a19ab50a5cd42a85561
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968604"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="b8324-103">Creare e assegnare strutture di regole avanzate</span><span class="sxs-lookup"><span data-stu-id="b8324-103">Create and assign advanced rule structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b8324-104">In questo argomento viene descritto come creare e assegnare una struttura di regole avanzate a una struttura dei conti.</span><span class="sxs-lookup"><span data-stu-id="b8324-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="b8324-105">Questa guida utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="b8324-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="b8324-106">Crea una struttura di regole avanzate</span><span class="sxs-lookup"><span data-stu-id="b8324-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="b8324-107">Passare a **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Strutture > Strutture regole avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b8324-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="b8324-108">Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="b8324-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="b8324-109">Nel campo **Struttura regole avanzate**, digitare un nome per descrivere la struttura delle regole.</span><span class="sxs-lookup"><span data-stu-id="b8324-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="b8324-110">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8324-110">Select **OK**.</span></span>
5. <span data-ttu-id="b8324-111">Selezionare **Aggiungi segmento**.</span><span class="sxs-lookup"><span data-stu-id="b8324-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="b8324-112">Selezionare una dimensione finanziaria nell'elenco di segmenti.</span><span class="sxs-lookup"><span data-stu-id="b8324-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="b8324-113">Ad esempio, **Punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="b8324-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="b8324-114">Selezionare **Aggiungi segmento**.</span><span class="sxs-lookup"><span data-stu-id="b8324-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="b8324-115">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="b8324-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="b8324-116">Applicare una struttura di regole avanzate a una struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="b8324-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="b8324-117">Passare a **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Strutture > Configura strutture dei conti**.</span><span class="sxs-lookup"><span data-stu-id="b8324-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="b8324-118">Nell'elenco, trovare e selezionare la struttura dei conti a cui applicare la regola avanzata.</span><span class="sxs-lookup"><span data-stu-id="b8324-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="b8324-119">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b8324-119">Select **Edit**.</span></span> <span data-ttu-id="b8324-120">È inoltre possibile fare clic su **Regole avanzate** e verrà richiesto di inserire la struttura dei conti in **modalità di bozza**.</span><span class="sxs-lookup"><span data-stu-id="b8324-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="b8324-121">Selezionare **Regole avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b8324-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="b8324-122">Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="b8324-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="b8324-123">Digitare un valore nel campo **Regola avanzata**.</span><span class="sxs-lookup"><span data-stu-id="b8324-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="b8324-124">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="b8324-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="b8324-125">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b8324-125">Select **Create**.</span></span>
9. <span data-ttu-id="b8324-126">Fare clic su **Aggiungi nuovi criteri**.</span><span class="sxs-lookup"><span data-stu-id="b8324-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="b8324-127">Nel campo **Percorso**, selezionare un conto principale o una dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="b8324-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="b8324-128">Nel campo **Operatore**, selezionare un'opzione, ad esempio **è compreso in** e **include**.</span><span class="sxs-lookup"><span data-stu-id="b8324-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="b8324-129">Digitare un valore nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="b8324-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="b8324-130">Digitare un valore nel campo **attraverso**.</span><span class="sxs-lookup"><span data-stu-id="b8324-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="b8324-131">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="b8324-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="b8324-132">Nell'elenco, individuare la struttura di regole avanzate da utilizzare quando vengono soddisfatti i criteri immessi.</span><span class="sxs-lookup"><span data-stu-id="b8324-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="b8324-133">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b8324-133">Select **Add**.</span></span>
17. <span data-ttu-id="b8324-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b8324-134">Close the page.</span></span>
18. <span data-ttu-id="b8324-135">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="b8324-135">Select **Activate**.</span></span>

