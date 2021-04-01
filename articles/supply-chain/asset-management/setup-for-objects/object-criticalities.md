---
title: Tipi di criticità dei cespiti
description: L'argomento descrive i tipi di criticità dei cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c771e7ebda94687ab5442347e74c82b01ad2fcc6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245421"
---
# <a name="asset-criticality-types"></a><span data-ttu-id="5645f-103">Tipi di criticità dei cespiti</span><span class="sxs-lookup"><span data-stu-id="5645f-103">Asset criticality types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="5645f-104">L'argomento descrive i tipi di criticità dei cespiti in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="5645f-104">The topic explains asset criticality types in Asset Management.</span></span> <span data-ttu-id="5645f-105">La criticità dei cespiti è correlata ai cespiti e viene trasferita agli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5645f-105">Asset criticality is related to assets and is transferred to work orders.</span></span> <span data-ttu-id="5645f-106">Non può essere modificata in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5645f-106">It can't be changed on a work order.</span></span> <span data-ttu-id="5645f-107">La criticità dei cespiti viene utilizzata per calcolare la criticità dell'ordine di lavoro durante la programmazione dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5645f-107">Asset criticality is used to calculate work order criticality during work order scheduling.</span></span> <span data-ttu-id="5645f-108">Ovvero, è utilizzata per calcolare la misura in cui un processo di manutenzione di un cespite influisce sulla programmazione di produzione e la produttività della società.</span><span class="sxs-lookup"><span data-stu-id="5645f-108">In other words, it's used to calculate the extent to which a maintenance job on an asset affects the production schedule and productivity in your company.</span></span> <span data-ttu-id="5645f-109">Per ulteriori informazioni sull'impostazione relativa al calcolo dei punteggi di valutazione per la programmazione degli ordini di lavoro, vedere [Parametri di Gestione cespiti](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5645f-109">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span>

<span data-ttu-id="5645f-110">Per impostare la criticità, è necessario innanzitutto creare i tipi di criticità che devono essere utilizzati nell'impostazione del cespite.</span><span class="sxs-lookup"><span data-stu-id="5645f-110">To set up criticality, you first create the criticality types that should be used in the asset setup.</span></span> <span data-ttu-id="5645f-111">Si imposteranno quindi le criticità dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="5645f-111">You then set up asset criticalities.</span></span>

## <a name="set-up-criticality-types"></a><span data-ttu-id="5645f-112">Impostare i tipi di criticità</span><span class="sxs-lookup"><span data-stu-id="5645f-112">Set up criticality types</span></span>

1. <span data-ttu-id="5645f-113">Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Tipi di criticità**.</span><span class="sxs-lookup"><span data-stu-id="5645f-113">Select **Asset management** \> **Setup** \> **Assets** \> **Criticality types**.</span></span>
2. <span data-ttu-id="5645f-114">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="5645f-114">Select **New** to create a record.</span></span>
3. <span data-ttu-id="5645f-115">Nel campo **Criticità**, immettere un numero che indica la criticità.</span><span class="sxs-lookup"><span data-stu-id="5645f-115">In the **Criticality** field, enter a number that indicates the criticality.</span></span>
4. <span data-ttu-id="5645f-116">Nel campo **Nome** immettere un nome per il tipo di criticità.</span><span class="sxs-lookup"><span data-stu-id="5645f-116">In the **Name** field, enter a name for the criticality type.</span></span>
5. <span data-ttu-id="5645f-117">Nel campo **Fattore** immettere un fattore.</span><span class="sxs-lookup"><span data-stu-id="5645f-117">In the **Factor** field, enter a factor.</span></span> <span data-ttu-id="5645f-118">Il fattore viene utilizzato durante il calcolo della programmazione dell'ordine di lavoro per determinare il record di criticità da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5645f-118">This factor is used during the calculation of work order scheduling to determine the criticality record that should be used.</span></span> <span data-ttu-id="5645f-119">Il record con il più alto fattore viene utilizzato sempre. Questa impostazione è rilevante se, come illustrato nella figura seguente, righe di criticità vengono create con lo stesso valore di criticità.</span><span class="sxs-lookup"><span data-stu-id="5645f-119">(The record that has the highest factor is always used.) This setting is relevant if, as shown in the following illustration, criticality lines are created that have the same criticality value.</span></span>

    ![Pagina Tipi di criticità](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a><span data-ttu-id="5645f-121">Impostare la criticità cespiti</span><span class="sxs-lookup"><span data-stu-id="5645f-121">Set up asset criticalities</span></span>

1. <span data-ttu-id="5645f-122">Selezionare **Gestione cespiti** \> **Impostazione** \> **Criticità cespiti**.</span><span class="sxs-lookup"><span data-stu-id="5645f-122">Select **Asset management** \> **Setup** \> **Asset criticalities**.</span></span>
2. <span data-ttu-id="5645f-123">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="5645f-123">Select **New** to create a record.</span></span>
3. <span data-ttu-id="5645f-124">A seconda del livello di dettaglio necessario per la criticità cespiti, selezionare opzioni appropriate nei campi **Unità funzionale**, **Tipo di cespite**, **Produttore**, **Modello**, **Cespite**, **Categoria tipo di processo**, **Tipo di processo**, **Variante tipo di processo** e **Fabbisogno processo**.</span><span class="sxs-lookup"><span data-stu-id="5645f-124">Depending on the required level of detail for asset criticality, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5645f-125">Quando una criticità cespiti è selezionata, Gestione cespiti analizza tutti i record di criticità cespiti per verificare la presenza di una corrispondenza possibile.</span><span class="sxs-lookup"><span data-stu-id="5645f-125">When an asset criticality is selected, Asset Management goes through all asset criticality records to check for a possible match.</span></span> <span data-ttu-id="5645f-126">Controlla sempre la combinazione più specifica per prima.</span><span class="sxs-lookup"><span data-stu-id="5645f-126">It always checks the most specific combination first.</span></span> <span data-ttu-id="5645f-127">In altre parole, Gestione cespiti controlla prima **Fabbisogno processo**.</span><span class="sxs-lookup"><span data-stu-id="5645f-127">In other words, Asset Management first checks **Job requirement**.</span></span> <span data-ttu-id="5645f-128">Se non trova corrispondenza, controlla **Variante tipo di processo**.</span><span class="sxs-lookup"><span data-stu-id="5645f-128">If no match is found, it checks **Job type variant**.</span></span> <span data-ttu-id="5645f-129">Se non trova corrispondenza, controlla **Tipo di processo** e così via.</span><span class="sxs-lookup"><span data-stu-id="5645f-129">If no match is found, it checks **Job type**, and so on.</span></span> <span data-ttu-id="5645f-130">Come si vede nel layout della pagina, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="5645f-130">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="5645f-131">Se non viene trovata alcuna corrispondenza, il record "predefinito" senza selezioni viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5645f-131">If no match is found, the "default" record that has no selections is used.</span></span>

4. <span data-ttu-id="5645f-132">Nel campo  **Criticità**, selezionare uno dei valori di criticità creati nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="5645f-132">In the **Criticality** field, select one of the criticality values that you created in the previous procedure.</span></span>

### <a name="notes-about-criticality-setup"></a><span data-ttu-id="5645f-133">Note sull'impostazione di criticità</span><span class="sxs-lookup"><span data-stu-id="5645f-133">Notes about criticality setup</span></span>

- <span data-ttu-id="5645f-134">Se si modifica una criticità cespiti in questa impostazione dopo che è stata già utilizzata in un ordine di lavoro, la criticità nell'ordine di lavoro non viene aggiornata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="5645f-134">If you change an asset criticality in this setup after you've already used it on a work order, the criticality on the work order isn't updated accordingly.</span></span>
- <span data-ttu-id="5645f-135">La criticità in un ordine di lavoro viene ricalcolata ogni volta in cui una riga di ordine di lavoro viene aggiunta o eliminatq dall'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5645f-135">The criticality on a work order is recalculated every time that a work order line is added to or deleted from the work order.</span></span>
- <span data-ttu-id="5645f-136">Se un ordine di lavoro contiene più processi dell'ordine di lavoro, la più alta criticità, a seconda del campo **Fattore** della pagina **Tipi di criticità**, è sempre utilizzata nell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5645f-136">If a work order contains several work order jobs, the highest criticality, according to the **Factor** field on the **Criticality types** page, is always used on the work order.</span></span>
- <span data-ttu-id="5645f-137">In genere, la criticità cespiti può cambiare in un periodo.</span><span class="sxs-lookup"><span data-stu-id="5645f-137">Generally, asset criticality can change over a period.</span></span> <span data-ttu-id="5645f-138">La criticità può essere influenzata dall'acquisto di nuova apparecchiatura, rinnovamenti, e così via.</span><span class="sxs-lookup"><span data-stu-id="5645f-138">Criticality can be affected by the purchase of new equipment, refurbishments, and so on.</span></span> <span data-ttu-id="5645f-139">Si consiglia di rivalutare le criticità dei cespiti a intervalli regolari, (ad esempio una volta l'anno o ogni due anni) per assicurarsi che le definizioni di criticità corrispondano alla impostazione di produzione corrente.</span><span class="sxs-lookup"><span data-stu-id="5645f-139">Consider reevaluating your asset criticalities at regular intervals (for example, once per year or every other year) to make sure that your criticality definitions match your current production setup.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]