--- 
title: Creare un numero di prodotto per le varianti prodotto predefinite
description: "In questa guida viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6294e4608b31c37aa713e3a7a2028b409b5a8366
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a><span data-ttu-id="4ced7-103">Creare un numero di prodotto per le varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="4ced7-103">Create a product number for predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4ced7-104">In questa guida viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato.</span><span class="sxs-lookup"><span data-stu-id="4ced7-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="4ced7-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="4ced7-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="4ced7-106">La nuova nomenclatura di numero prodotto è assegnata al gruppo di dimensioni prodotto Colore e Dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4ced7-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="4ced7-107">Questa attività viene in genere effettuata da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="4ced7-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="4ced7-108">Creare una nomenclatura di numero prodotto</span><span class="sxs-lookup"><span data-stu-id="4ced7-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="4ced7-109">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="4ced7-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="4ced7-110">Fare clic su Nomenclatura di prodotto.</span><span class="sxs-lookup"><span data-stu-id="4ced7-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="4ced7-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4ced7-111">Click New.</span></span>
4. <span data-ttu-id="4ced7-112">Nel campo Nome, immettere un nome di nomenclatura che consente di identificare il gruppo di dimensioni prodotto di destinazione, ad esempio ColorSize.</span><span class="sxs-lookup"><span data-stu-id="4ced7-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="4ced7-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4ced7-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="4ced7-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4ced7-114">Click Add.</span></span>
7. <span data-ttu-id="4ced7-115">Fare clic su Numero rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="4ced7-115">Click Product master number.</span></span>
8. <span data-ttu-id="4ced7-116">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4ced7-116">Click Add.</span></span>
9. <span data-ttu-id="4ced7-117">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="4ced7-117">Click Text constant.</span></span>
10. <span data-ttu-id="4ced7-118">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="4ced7-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="4ced7-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4ced7-119">Click Add.</span></span>
12. <span data-ttu-id="4ced7-120">Fare clic su Colore.</span><span class="sxs-lookup"><span data-stu-id="4ced7-120">Click Color.</span></span>
13. <span data-ttu-id="4ced7-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4ced7-121">Click Add.</span></span>
14. <span data-ttu-id="4ced7-122">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="4ced7-122">Click Text constant.</span></span>
15. <span data-ttu-id="4ced7-123">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="4ced7-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="4ced7-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4ced7-124">Click Add.</span></span>
17. <span data-ttu-id="4ced7-125">Fare clic su Dimensione.</span><span class="sxs-lookup"><span data-stu-id="4ced7-125">Click Size.</span></span>
18. <span data-ttu-id="4ced7-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4ced7-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="4ced7-127">Assegnare la nomenclatura a una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="4ced7-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="4ced7-128">Fare clic su Gruppi di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="4ced7-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="4ced7-129">Selezionare il gruppo di dimensioni prodotto SizeCol.</span><span class="sxs-lookup"><span data-stu-id="4ced7-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="4ced7-130">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="4ced7-130">Click Edit.</span></span>
4. <span data-ttu-id="4ced7-131">Selezionare Sì nel campo Utilizza nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="4ced7-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="4ced7-132">Nel campo Nomenclatura di numero di variante prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4ced7-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="4ced7-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4ced7-133">Close the page.</span></span>


