---
title: Produttori e modelli di cespiti
description: In questo argomento viene descritto come impostare i produttori di cespiti e i relativi modelli in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b77605070387871335c480e25cbe23af1155d6e8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812170"
---
# <a name="asset-manufacturers-and-models"></a><span data-ttu-id="b7194-103">Produttori e modelli di cespiti</span><span class="sxs-lookup"><span data-stu-id="b7194-103">Asset manufacturers and models</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b7194-104">In questo argomento viene descritto come impostare i produttori di cespiti e i relativi modelli in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="b7194-104">This topic explains how to set up asset manufacturers and related models in Asset Management.</span></span> <span data-ttu-id="b7194-105">I modelli possono essere correlati ai tipi di cespite.</span><span class="sxs-lookup"><span data-stu-id="b7194-105">Models can be related to asset types.</span></span>

## <a name="set-up-product-model-relations"></a><span data-ttu-id="b7194-106">Impostare le relazioni prodotto-modello</span><span class="sxs-lookup"><span data-stu-id="b7194-106">Set up product-model relations</span></span>

1. <span data-ttu-id="b7194-107">Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Produttore e modello**.</span><span class="sxs-lookup"><span data-stu-id="b7194-107">Select **Asset management** \> **Setup** \> **Assets** \> **Manufacturer and model**.</span></span>
2. <span data-ttu-id="b7194-108">Selezionare **Nuovo** per creare un nuovo prodotto.</span><span class="sxs-lookup"><span data-stu-id="b7194-108">Select **New** to create a new product.</span></span>
3. <span data-ttu-id="b7194-109">Nel campo  **Produttore** immettere un nome per il produttore di cespiti.</span><span class="sxs-lookup"><span data-stu-id="b7194-109">In the **Manufacturer** field, enter a name for the asset manufacturer.</span></span>
4. <span data-ttu-id="b7194-110">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b7194-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="b7194-111">Nella Scheda dettaglio **Modelli**, selezionare **Aggiungi** per creare un modello di cespite che deve essere correlato al produttore di cespiti.</span><span class="sxs-lookup"><span data-stu-id="b7194-111">On the **Models** FastTab, select **Add** to create an asset model that should be related to the asset manufacturer.</span></span>
6. <span data-ttu-id="b7194-112">Nel campo **Modello** immettere un nome per il modello di cespite.</span><span class="sxs-lookup"><span data-stu-id="b7194-112">In the **Model** field, enter a name for the asset model.</span></span>
7. <span data-ttu-id="b7194-113">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b7194-113">In the **Description** field, enter a description.</span></span>
8. <span data-ttu-id="b7194-114">Nel campo **Tipo di cespite**, selezionare il tipo di cespite a cui il modello del produttore deve essere correlato.</span><span class="sxs-lookup"><span data-stu-id="b7194-114">In the **Asset type** field, select the asset type that the manufacturer model should be related to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7194-115">È inoltre possibile impostare le relazioni per i tipi, i produttori e modelli di cespite nella ricerca **Tipi di cespite**.</span><span class="sxs-lookup"><span data-stu-id="b7194-115">You can also set up relations for asset types, manufacturers, and models in the **Asset types** lookup.</span></span> <span data-ttu-id="b7194-116">Per ulteriori informazioni, vedere [Tipi di cespite](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="b7194-116">For more information, see [Asset types](../setup-for-objects/object-types.md).</span></span>

    <span data-ttu-id="b7194-117">Nella Scheda dettaglio **Dettagli**, il campo **Modelli** mostra il numero di modelli di cespite impostati per il produttore di cespiti selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7194-117">In the **Details** FastTab, the **Models** field shows the number of asset models that are set up on the selected asset manufacturer.</span></span> <span data-ttu-id="b7194-118">Nel campo **Cespiti** viene visualizzato il numero di cespiti che utilizzano il produttore selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7194-118">The **Assets** field shows the number of assets that are using the selected manufacturer.</span></span>
    
    <span data-ttu-id="b7194-119">Nel campo **Cespiti** viene visualizzato il numero di oggetti che utilizzano il modello del produttore.</span><span class="sxs-lookup"><span data-stu-id="b7194-119">The **Assets** field shows the number of objects that are using the manufacturer model.</span></span>

> [!NOTE]
> <span data-ttu-id="b7194-120">Un tipo di cespite può avere nessuna relazione con modelli del produttore di cespiti, può essere correlato a un modello del produttore di cespiti o può essere correlato a più modelli del produttore di cespiti.</span><span class="sxs-lookup"><span data-stu-id="b7194-120">An asset type can have no asset manufacturer model relations, it can be related to one asset manufacturer model, or it can be related multiple asset manufacturer models.</span></span> <span data-ttu-id="b7194-121">Se un tipo di cespite è correlato ad almeno un modello del produttore, solo combinazioni impostate nella ricerca **Modello del produttore** possono essere selezionate nelle pagine di Gestione cespiti in cui una combinazione di tipo, di produttore e di modello di cespite può essere configurata.</span><span class="sxs-lookup"><span data-stu-id="b7194-121">If an asset type is related to at least one manufacturer model, only the combinations that are set up in the **Manufacturer model** lookup can be selected on those Asset Management pages where a combination of an asset type, manufacturer, and model can be set up.</span></span> <span data-ttu-id="b7194-122">Queste pagine includono **Tutti i cespiti**, **Livelli di servizio cespiti**, **Valori predefiniti tipo di processo** e **Righe budget di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="b7194-122">These pages include **All assets**, **Asset service levels**, **Job type defaults**, and **Maintenance budget lines**.</span></span> <span data-ttu-id="b7194-123">Se alcuni tipi di cespite non sono correlati ad alcun modello del produttore, solo i tipi di cespite e modelli del produttore che non hanno nessuna relazione con i tipi di cespite, vengono visualizzati nelle pagine.</span><span class="sxs-lookup"><span data-stu-id="b7194-123">If some asset types aren't related to any manufacturer model, only those asset types, and manufacturer models that also have no relation to asset types, are shown on the pages.</span></span>

## <a name="select-a-manufacturer-and-model-on-an-object"></a><span data-ttu-id="b7194-124">Selezionare un produttore e un modello per un oggetto</span><span class="sxs-lookup"><span data-stu-id="b7194-124">Select a manufacturer and model on an object</span></span>

1. <span data-ttu-id="b7194-125">Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="b7194-125">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="b7194-126">Nella colonna **Cespite**, selezionare il collegamento per il cespite.</span><span class="sxs-lookup"><span data-stu-id="b7194-126">In the **Asset** column, select the link for the asset.</span></span> <span data-ttu-id="b7194-127">Viene visualizzata la pagina **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b7194-127">The **Details** page appears.</span></span>
3. <span data-ttu-id="b7194-128">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b7194-128">Select **Edit**.</span></span>
4. <span data-ttu-id="b7194-129">Nella Scheda dettaglio **Generale**, selezionare i valori nei campi **Modello** e **Produttore**.</span><span class="sxs-lookup"><span data-stu-id="b7194-129">On the **General** FastTab, select values in the **Manufacturer** and **Model** fields.</span></span>
