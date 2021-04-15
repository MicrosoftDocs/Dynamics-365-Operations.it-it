---
title: Tipi di attributo di manutenzione
description: Nell'argomento viene descritto come creare tipi di attributo in Gestione cespiti.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 283cff931ce665ae09152c8f3d3c976b7c8b66ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808522"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="1fedb-103">Tipi di attributo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="1fedb-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1fedb-104">Nell'argomento viene descritto come creare tipi di attributo in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="1fedb-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="1fedb-105">Gli attributi consentono di descrivere le proprietà dei vari elementi.</span><span class="sxs-lookup"><span data-stu-id="1fedb-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="1fedb-106">È possibile impostare attributi per i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="1fedb-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="1fedb-107">Tipi di unità funzionali</span><span class="sxs-lookup"><span data-stu-id="1fedb-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="1fedb-108">Creare unità funzionali</span><span class="sxs-lookup"><span data-stu-id="1fedb-108">Create functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="1fedb-109">Tipi di cespite</span><span class="sxs-lookup"><span data-stu-id="1fedb-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="1fedb-110">Cespiti</span><span class="sxs-lookup"><span data-stu-id="1fedb-110">Assets</span></span>

<span data-ttu-id="1fedb-111">Gli attributi impostabili variano in base all'elemento.</span><span class="sxs-lookup"><span data-stu-id="1fedb-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="1fedb-112">Ad esempio, per una unità funzionale, è possibile impostare gli attributi per la configurazione e le dimensioni fisiche della ubicazione.</span><span class="sxs-lookup"><span data-stu-id="1fedb-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="1fedb-113">Per un tipo di cespite o un cespite, è possibile impostare gli attributi per il volume del motore, il consumo di energia e la massima capacità di carico in varie condizioni.</span><span class="sxs-lookup"><span data-stu-id="1fedb-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="1fedb-114">Creare tipi di attributo</span><span class="sxs-lookup"><span data-stu-id="1fedb-114">Create attribute types</span></span>

<span data-ttu-id="1fedb-115">È possibile creare propri tipi di attributo.</span><span class="sxs-lookup"><span data-stu-id="1fedb-115">You can create your own attribute types.</span></span> <span data-ttu-id="1fedb-116">Inoltre, è possibile trasferire le dimensioni prodotto alla pagina **Tipi di attributo**.</span><span class="sxs-lookup"><span data-stu-id="1fedb-116">Additionally, you can transfer product dimensions to the **Attribute types** page.</span></span>

1. <span data-ttu-id="1fedb-117">Selezionare **Gestione cespiti** \> **Impostazione** \> **Tipi di attributo**.</span><span class="sxs-lookup"><span data-stu-id="1fedb-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="1fedb-118">La prima volta che si impostano i tipi di attributo selezionare **Crea dimensioni prodotto** per trasferire automaticamente le dimensioni prodotto standard.</span><span class="sxs-lookup"><span data-stu-id="1fedb-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard product dimensions.</span></span>
3. <span data-ttu-id="1fedb-119">Selezionare **Nuovo** per creare un tipo di attibuto.</span><span class="sxs-lookup"><span data-stu-id="1fedb-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="1fedb-120">Nel campo **Tipo di attributo** immettere un nome per il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="1fedb-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="1fedb-121">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="1fedb-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="1fedb-122">Nel campo **Unità**, selezionare l'unità di attributo pertinente, secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="1fedb-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="1fedb-123">Nel campo **Tipo di dati** selezionare un tipo di dati per l'unità.</span><span class="sxs-lookup"><span data-stu-id="1fedb-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="1fedb-124">Se è stato selezionato **Stringa** come tipo di dati, seguire questi passaggi per creare valori per il tipo di attributo:</span><span class="sxs-lookup"><span data-stu-id="1fedb-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="1fedb-125">Selezionare il tipo di attributo, quindi selezionare **Valori**.</span><span class="sxs-lookup"><span data-stu-id="1fedb-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="1fedb-126">Nel campo **Valori attributi** selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1fedb-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="1fedb-127">Nel campo **Tipo di attributo** selezionare un tipo di attributo (dimensione).</span><span class="sxs-lookup"><span data-stu-id="1fedb-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="1fedb-128">Nel campo  **Valore** immettere un valore correlato.</span><span class="sxs-lookup"><span data-stu-id="1fedb-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="1fedb-129">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="1fedb-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="1fedb-130">Salvare il record.</span><span class="sxs-lookup"><span data-stu-id="1fedb-130">Save the record.</span></span>
    7. <span data-ttu-id="1fedb-131">Torna alla pagina **Tipi di attributo**.</span><span class="sxs-lookup"><span data-stu-id="1fedb-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="1fedb-132">Salvare il record.</span><span class="sxs-lookup"><span data-stu-id="1fedb-132">Save the record.</span></span>

    <span data-ttu-id="1fedb-133">Nel campo **Tipi di unità funzionali** viene visualizzato il numero di unità funzionali che utilizzano il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="1fedb-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="1fedb-134">Nel campo **Tipi di cespite** viene visualizzato il numero di tipi di cespite che lo utilizzano.</span><span class="sxs-lookup"><span data-stu-id="1fedb-134">The **Asset types** field shows the number of asset types that are using it.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]