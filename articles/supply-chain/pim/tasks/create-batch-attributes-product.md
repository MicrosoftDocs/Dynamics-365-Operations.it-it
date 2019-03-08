---
title: Creare gli attributi batch per un prodotto
description: Questa procedura illustra come creare un attributo batch, come assegnare intervalli di valori predefiniti e come includere l'attributo in un gruppo.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: 65153dbcfa69046e4f38eb6ffa013bb6fb87ebd8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "330657"
---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="16cbe-103">Creare gli attributi batch per un prodotto</span><span class="sxs-lookup"><span data-stu-id="16cbe-103">Create batch attributes for a product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="16cbe-104">Questa procedura illustra come creare un attributo batch, come assegnare intervalli di valori predefiniti e come includere l'attributo in un gruppo.</span><span class="sxs-lookup"><span data-stu-id="16cbe-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="16cbe-105">La società di dati dimostrativi utilizzata per creare questa procedura è USP2.</span><span class="sxs-lookup"><span data-stu-id="16cbe-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="16cbe-106">Andare a Gestione articoli > Impostazioni > Batch > Attributi batch.</span><span class="sxs-lookup"><span data-stu-id="16cbe-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="16cbe-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="16cbe-107">Click New.</span></span>
3. <span data-ttu-id="16cbe-108">Digitare un valore nel campo Attributo.</span><span class="sxs-lookup"><span data-stu-id="16cbe-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="16cbe-109">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="16cbe-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="16cbe-110">Nel campo Tipo di attributo selezionare "Frazione".</span><span class="sxs-lookup"><span data-stu-id="16cbe-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="16cbe-111">Questa procedura utilizza il tipo Frazione per consentire i valori decimali.</span><span class="sxs-lookup"><span data-stu-id="16cbe-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="16cbe-112">È possibile selezionare altri tipi di attributo.</span><span class="sxs-lookup"><span data-stu-id="16cbe-112">You can select other attribute types.</span></span> <span data-ttu-id="16cbe-113">Se si seleziona il tipo di enumerazione, è necessario immettere i valori nell'elenco di enumerazione prima di immettere un valore nel campo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16cbe-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="16cbe-114">Nel campo Minimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="16cbe-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="16cbe-115">Nel campo Massimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="16cbe-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="16cbe-116">Nel campo Incremento immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="16cbe-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="16cbe-117">Nel campo Destinazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="16cbe-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="16cbe-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="16cbe-118">Click Save.</span></span>
11. <span data-ttu-id="16cbe-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="16cbe-119">Close the page.</span></span>
12. <span data-ttu-id="16cbe-120">Andare a Gestione articoli > Impostazioni > Batch > Gruppi di attributi batch.</span><span class="sxs-lookup"><span data-stu-id="16cbe-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="16cbe-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="16cbe-121">Click New.</span></span>
14. <span data-ttu-id="16cbe-122">Digitare un valore nel campo Gruppo di attributi.</span><span class="sxs-lookup"><span data-stu-id="16cbe-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="16cbe-123">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="16cbe-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="16cbe-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="16cbe-124">Click Save.</span></span>
17. <span data-ttu-id="16cbe-125">Fare clic su Attributi del gruppo.</span><span class="sxs-lookup"><span data-stu-id="16cbe-125">Click Group attributes.</span></span>
18. <span data-ttu-id="16cbe-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="16cbe-126">Click New.</span></span>
19. <span data-ttu-id="16cbe-127">Nel campo Attributo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="16cbe-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="16cbe-128">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="16cbe-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="16cbe-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="16cbe-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="16cbe-130">Un attributo può essere incluso in uno qualsiasi dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="16cbe-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="16cbe-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="16cbe-131">Click Save.</span></span>
23. <span data-ttu-id="16cbe-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="16cbe-132">Close the page.</span></span>

