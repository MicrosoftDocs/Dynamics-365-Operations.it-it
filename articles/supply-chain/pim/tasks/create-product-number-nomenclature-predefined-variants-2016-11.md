---
title: Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite
description: In questo argomento viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a4ad70a87cd8c6cab2e9853f4f6c52f574d318a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257422"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="ba803-103">Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="ba803-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba803-104">In questo argomento viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato.</span><span class="sxs-lookup"><span data-stu-id="ba803-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="ba803-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="ba803-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ba803-106">La nuova nomenclatura di numero prodotto è assegnata al gruppo di dimensioni prodotto Colore e Dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ba803-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="ba803-107">Questa attività viene in genere effettuata da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="ba803-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="ba803-108">Creare una nomenclatura di numero prodotto</span><span class="sxs-lookup"><span data-stu-id="ba803-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="ba803-109">Selezionare **Definizione modello di variante prodotto**.</span><span class="sxs-lookup"><span data-stu-id="ba803-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="ba803-110">Selezionare **Nomenclatura di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="ba803-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="ba803-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ba803-111">Select **New**.</span></span>
4. <span data-ttu-id="ba803-112">Nel campo **Nome**, immettere un nome di nomenclatura che consente di identificare il gruppo di dimensioni prodotto di destinazione, ad esempio `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="ba803-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="ba803-113">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ba803-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="ba803-114">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ba803-114">Select **Add**.</span></span>
7. <span data-ttu-id="ba803-115">Selezionare **Numero rappresentazione generale prodotto**.</span><span class="sxs-lookup"><span data-stu-id="ba803-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="ba803-116">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ba803-116">Select **Add**.</span></span>
9. <span data-ttu-id="ba803-117">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="ba803-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="ba803-118">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="ba803-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="ba803-119">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ba803-119">Select **Add**.</span></span>
12. <span data-ttu-id="ba803-120">Seleziona **Colore**.</span><span class="sxs-lookup"><span data-stu-id="ba803-120">Select **Color**.</span></span>
13. <span data-ttu-id="ba803-121">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ba803-121">Select **Add**.</span></span>
14. <span data-ttu-id="ba803-122">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="ba803-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="ba803-123">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="ba803-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="ba803-124">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ba803-124">Select **Add**.</span></span>
17. <span data-ttu-id="ba803-125">Seleziona **Dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="ba803-125">Select **Size**.</span></span>
18. <span data-ttu-id="ba803-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ba803-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="ba803-127">Assegnare la nomenclatura a una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="ba803-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="ba803-128">Selezionare **Gruppi di dimensioni prodotto**.</span><span class="sxs-lookup"><span data-stu-id="ba803-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="ba803-129">Selezionare il gruppo di **dimensioni prodotto SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="ba803-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="ba803-130">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ba803-130">Select **Edit**.</span></span>
4. <span data-ttu-id="ba803-131">Selezionare **Sì** nel campo **Utilizza nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="ba803-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="ba803-132">Nel campo **Nomenclatura di numero di variante prodotto** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ba803-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="ba803-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ba803-133">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]