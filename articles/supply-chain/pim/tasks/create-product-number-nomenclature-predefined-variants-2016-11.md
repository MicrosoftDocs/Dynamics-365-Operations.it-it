---
title: Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite
description: In questo argomento viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920659"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="6cc7d-103">Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="6cc7d-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6cc7d-104">In questo argomento viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="6cc7d-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6cc7d-106">La nuova nomenclatura di numero prodotto è assegnata al gruppo di dimensioni prodotto Colore e Dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="6cc7d-107">Questa attività viene in genere effettuata da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="6cc7d-108">Creare una nomenclatura di numero prodotto</span><span class="sxs-lookup"><span data-stu-id="6cc7d-108">Create a product number nomenclature</span></span>

1. <span data-ttu-id="6cc7d-109">Vai a **Gestione informazioni sul prodotto \> Imposta \> Nomenclatura di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-109">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="6cc7d-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-110">Select **New**.</span></span>
1. <span data-ttu-id="6cc7d-111">Nel campo **Nome**, immettere un nome di nomenclatura che consente di identificare il gruppo di dimensioni prodotto di destinazione, ad esempio `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-111">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
1. <span data-ttu-id="6cc7d-112">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6cc7d-112">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="6cc7d-113">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-113">Select **Add**.</span></span>
1. <span data-ttu-id="6cc7d-114">Selezionare **Numero rappresentazione generale prodotto**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-114">Select **Product master** number.</span></span>
1. <span data-ttu-id="6cc7d-115">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-115">Select **Add**.</span></span>
1. <span data-ttu-id="6cc7d-116">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-116">Select **Text constant**.</span></span>
1. <span data-ttu-id="6cc7d-117">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-117">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="6cc7d-118">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-118">Select **Add**.</span></span>
1. <span data-ttu-id="6cc7d-119">Seleziona **Colore**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-119">Select **Color**.</span></span>
1. <span data-ttu-id="6cc7d-120">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-120">Select **Add**.</span></span>
1. <span data-ttu-id="6cc7d-121">Selezionare **Costante testo**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-121">Select **Text constant**.</span></span>
1. <span data-ttu-id="6cc7d-122">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-122">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="6cc7d-123">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-123">Select **Add**.</span></span>
1. <span data-ttu-id="6cc7d-124">Seleziona **Dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-124">Select **Size**.</span></span>
1. <span data-ttu-id="6cc7d-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-125">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="6cc7d-126">Assegnare la nomenclatura a una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="6cc7d-126">Assign the nomenclature to a product master</span></span>

1. <span data-ttu-id="6cc7d-127">Selezionare **Gruppi di dimensioni prodotto**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-127">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="6cc7d-128">Selezionare il gruppo di **dimensioni prodotto SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-128">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="6cc7d-129">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-129">Select **Edit**.</span></span>
4. <span data-ttu-id="6cc7d-130">Selezionare **Sì** nel campo **Utilizza nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-130">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="6cc7d-131">Nel campo **Nomenclatura di numero di variante prodotto** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-131">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="6cc7d-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6cc7d-132">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]