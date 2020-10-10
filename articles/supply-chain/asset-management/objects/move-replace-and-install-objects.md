---
title: Spostare, sostituire e installare cespiti
description: Viene descritto come spostare, sostituire e installare cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec150adb35eb0600844245b14cbec9e9632ab337
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889555"
---
# <a name="move-replace-and-install-assets"></a><span data-ttu-id="e086c-103">Spostare, sostituire e installare cespiti</span><span class="sxs-lookup"><span data-stu-id="e086c-103">Move, replace, and install assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e086c-104">Viene descritto come spostare, sostituire e installare cespiti in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-104">This topic explains how to move, replace, and install assets in Asset Management.</span></span> <span data-ttu-id="e086c-105">È possibile creare singoli cespiti che non hanno relazioni ad altri cespiti, oppure creare una struttura di cespiti che include un cespite padre (cespite di primo livello) e cespiti figlio correlati (cespiti secondari).</span><span class="sxs-lookup"><span data-stu-id="e086c-105">You can create individual assets that have no relations to other assets, or you can create an asset structure that includes a parent asset (top-level asset) and related child assets (sub-assets).</span></span> <span data-ttu-id="e086c-106">In Gestione cespiti, sono disponibili tre metodi per spostare e di cambiare l'ubicazione di un cespite:</span><span class="sxs-lookup"><span data-stu-id="e086c-106">In Asset Management, there are three approaches to moving and changing the location of an asset:</span></span>

- <span data-ttu-id="e086c-107">**Spostamento**- sposta il cespite in un'altra struttura di cespiti o in un'altra ubicazione nella stessa struttura di cespiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-107">**Move** – Move an asset either to another asset structure or to another location in the same asset structure.</span></span>
- <span data-ttu-id="e086c-108">**Sostituzione** - Rimuove temporaneamente un cespite da una struttura di cespiti perché possa essere riparato o rinnovato, quindi aggiunge il cespite rinnovato alla stessa struttura di cespiti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e086c-108">**Replace** – Temporarily remove an asset from an asset structure so that it can be repaired or refurbished, and then add the refurbished asset back to the asset structure later.</span></span> <span data-ttu-id="e086c-109">In alternativa, sostituisce definitivamente un cespite con un nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="e086c-109">Alternatively, permanently replace a used asset with a new asset.</span></span>
- <span data-ttu-id="e086c-110">**Installazione** - Installa un cespite padre e tutti i cespiti figlio correlati in una unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="e086c-110">**Install** – Install a parent asset and any related child assets on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="e086c-111">Cespite che si sposta, sostituisce o installa potrebbe essere correlato a un'altra unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="e086c-111">The asset that you move, replace, or install might be related to another functional location.</span></span> <span data-ttu-id="e086c-112">In tal caso, il cespite potrebbe utilizzare le dimensioni finanziarie dell'unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="e086c-112">In that case, the asset might use financial dimensions of the functional location.</span></span> <span data-ttu-id="e086c-113">Nella pagina **Tipi di unità funzionali**, è possibile impostare la gestione delle dimensioni finanziarie nelle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="e086c-113">On the **Functional location types** page, you set up the handling of financial dimensions on functional locations.</span></span>

## <a name="move-asset"></a><span data-ttu-id="e086c-114">Sposta cespite</span><span class="sxs-lookup"><span data-stu-id="e086c-114">Move asset</span></span>

<span data-ttu-id="e086c-115">Usare la funzione **Sposta cespite** per spostare il cespite in un'altra struttura di cespiti o in un'altra ubicazione nella stessa struttura di cespiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-115">Use the **Move asset** function to move an asset either to another asset structure or to another location in the same asset structure.</span></span> <span data-ttu-id="e086c-116">È inoltre possibile spostare un cespite da una struttura dei cespiti in modo che si trasformi in un cespite autonomo che non ha relazioni di struttura.</span><span class="sxs-lookup"><span data-stu-id="e086c-116">You can also move an asset out of an asset structure so that it becomes a standalone asset that has no structure relations.</span></span>

> [!NOTE]
> <span data-ttu-id="e086c-117">Non utilizzare questa funzione se i cespiti sono in riparazione o vengono temporaneamente sostituiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-117">Don't use this function if assets are being repaired or temporarily replaced.</span></span> <span data-ttu-id="e086c-118">Invece, utilizzare la funzionalità **Sostituisci cespite** che viene descritta più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e086c-118">Instead, use the **Replace asset** functionality that is described later in this topic.</span></span>

1. <span data-ttu-id="e086c-119">Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**.</span><span class="sxs-lookup"><span data-stu-id="e086c-119">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="e086c-120">Selezionare il cespite da spostare nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e086c-120">In the list, select the asset to move.</span></span> <span data-ttu-id="e086c-121">Se il cespite ha cespiti figlio, si spostano anche quelli.</span><span class="sxs-lookup"><span data-stu-id="e086c-121">If the asset has child assets, you also move those assets.</span></span>
3. <span data-ttu-id="e086c-122">Selezionare **Sposta cespite**.</span><span class="sxs-lookup"><span data-stu-id="e086c-122">Select **Move asset**.</span></span>
4. <span data-ttu-id="e086c-123">Per spostare il cespite in modo che diventi parte di una struttura di cespiti, selezionare il nuovo cespite padre nel campo **Cespite padre**.</span><span class="sxs-lookup"><span data-stu-id="e086c-123">To move the asset so that it becomes part of an asset structure, select the new parent asset in the **Parent asset** field.</span></span> <span data-ttu-id="e086c-124">Se si sposta un cespite figlio e si desidera renderlo un cespite autonomo che non ha relazioni di struttura, lasciare vuoto il campo **Cespite padre**.</span><span class="sxs-lookup"><span data-stu-id="e086c-124">If you're moving a child asset, and you want to make it a standalone asset that has no structure relations, leave the **Parent asset** field blank.</span></span>
5. <span data-ttu-id="e086c-125">Il campo **Validità** viene impostato automaticamente sulla data e ora corrente.</span><span class="sxs-lookup"><span data-stu-id="e086c-125">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="e086c-126">Tuttavia, è possibile selezionare una data e un'ora diverse per l'inizio della validità dello movimento del cespite.</span><span class="sxs-lookup"><span data-stu-id="e086c-126">However, you can select a different date and time that the asset move is valid from.</span></span>
6. <span data-ttu-id="e086c-127">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e086c-127">Select **OK**.</span></span>

## <a name="replace-asset"></a><span data-ttu-id="e086c-128">Sostituisci cespite</span><span class="sxs-lookup"><span data-stu-id="e086c-128">Replace asset</span></span>

<span data-ttu-id="e086c-129">Utilizzare la funzione **Sostituisci cespite** in relazione alle riparazioni, al rinnovo, o la sostituzione permanente di un cespite logoro con un nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="e086c-129">Use the **Replace asset** function in connection with repairs, refurbishment, or permanent replacement of a worn-out asset by a new asset.</span></span> <span data-ttu-id="e086c-130">Questa funzione viene utilizzata per sostituire i cespiti figlio in una struttura di cespiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-130">This function is used to replace child assets in an asset structure.</span></span> <span data-ttu-id="e086c-131">Per i cespiti padre (ovvero cespiti che non hanno attualmente un cespite padre), la sostituzione viene effettuata in un'unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="e086c-131">For parent assets (that is, assets that don't currently have a parent asset), this replacement is done on a functional location.</span></span> <span data-ttu-id="e086c-132">Per ulteriori informazioni su come sostituire i cespiti padre in un'unità funzionale, vedere [Installare cespiti nelle unità funzionali](../functional-locations/install-objects-on-functional-locations.md).</span><span class="sxs-lookup"><span data-stu-id="e086c-132">For more information about how to replace parent assets on a functional location, see [Install assets on functional locations](../functional-locations/install-objects-on-functional-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e086c-133">Se l'officina riparazioni è correlata al reparto di produzione, è possibile creare unità funzionali quali **Riparazione**, **Scarti** e **Immagazzinamento** per gestire la riparazione e la sostituzione dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-133">If a repair shop is related to your production department, you can create functional locations such as **Repair**, **Scrap**, and **Storage** to handle the repair and replacement of assets.</span></span>

1. <span data-ttu-id="e086c-134">Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**.</span><span class="sxs-lookup"><span data-stu-id="e086c-134">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="e086c-135">Nell'elenco selezionare il cespite figlio da sostituire.</span><span class="sxs-lookup"><span data-stu-id="e086c-135">In the list, select the child asset to replace.</span></span> <span data-ttu-id="e086c-136">Se il cespite ha cespiti figlio, si sostituiscono anche quelli.</span><span class="sxs-lookup"><span data-stu-id="e086c-136">If the asset has child assets, you also replace those assets.</span></span>
3. <span data-ttu-id="e086c-137">Selezionare **Sostituisci cespite**.</span><span class="sxs-lookup"><span data-stu-id="e086c-137">Select **Replace asset**.</span></span>

    <span data-ttu-id="e086c-138">Il campo **Struttura modificata** indica la data e ora dell'ultimo spostamento del cespite selezionato e i cespiti figlio correlati nella struttura di cespiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-138">The **Structure change** field shows the last date and time that the selected asset and related child assets were moved in the asset structure.</span></span>

4. <span data-ttu-id="e086c-139">Nella sezione **Cespite selezionato**, nel campo **Unità funzionale di destinazione**, selezionare l'unità funzionale in cui spostare il cespite.</span><span class="sxs-lookup"><span data-stu-id="e086c-139">In the **Selected asset** section, in the **Target functional location** field, select the functional location to move the asset to.</span></span> <span data-ttu-id="e086c-140">Ad esempio, selezionare **Scarti** o **Riparazione**.</span><span class="sxs-lookup"><span data-stu-id="e086c-140">For example, select the **Repair** or **Scrap** location.</span></span>

    <span data-ttu-id="e086c-141">Nella sezione **Cespite padre**, il campo **Validità** indica la data e ora dell'ultima installazione o spostamento del cespite padre e i cespiti figlio correlati nell'unità funzionale corrente.</span><span class="sxs-lookup"><span data-stu-id="e086c-141">In the **Parent asset** section, the **Effective** field shows the last date and time that the parent asset and related child assets were installed or moved on the current functional location.</span></span>

5. <span data-ttu-id="e086c-142">Nella sezione **Nuovo cespite**, nel campo **Cespite**, selezionare il cespite da inserire in sostituzione permanente o temporanea del cespite selezionato.</span><span class="sxs-lookup"><span data-stu-id="e086c-142">In the **New asset** section, in the **Asset** field, select the asset to insert as a temporary or permanent replacement for the selected asset.</span></span> <span data-ttu-id="e086c-143">Questo cespite potrebbe essere attualmente ubicato in un'altra unità funzionale, ad esempio **Immagazzinamento**.</span><span class="sxs-lookup"><span data-stu-id="e086c-143">This asset might currently be located on another functional location, such as **Storage**.</span></span>
7. <span data-ttu-id="e086c-144">Nella sezione **Data di inizio validità** Il campo **Validità** viene impostato automaticamente sulla data e ora corrente.</span><span class="sxs-lookup"><span data-stu-id="e086c-144">In the **Effective from** section, the **Effective** field is set to the current date and time by default.</span></span> <span data-ttu-id="e086c-145">Tuttavia, è possibile selezionare una data e un'ora diverse per l'inizio della validità della sostituzione del cespite.</span><span class="sxs-lookup"><span data-stu-id="e086c-145">However, you can select a different date and time that the asset replacement is valid from.</span></span>
8. <span data-ttu-id="e086c-146">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e086c-146">Select **OK**.</span></span>

## <a name="install-asset"></a><span data-ttu-id="e086c-147">Installa cespite</span><span class="sxs-lookup"><span data-stu-id="e086c-147">Install asset</span></span>

<span data-ttu-id="e086c-148">Utilizzare la funzione **Installa cespite** per installare una struttura di cespiti in una unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="e086c-148">Use the **Install asset** function to install an asset structure on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="e086c-149">Selezionare sempre un cespite padre.</span><span class="sxs-lookup"><span data-stu-id="e086c-149">Always select a parent asset.</span></span> <span data-ttu-id="e086c-150">Il cespite padre e i cespiti figlio correlati verranno spostati nell'unità funzionale selezionata.</span><span class="sxs-lookup"><span data-stu-id="e086c-150">The parent asset and related child assets will be moved to the selected functional location.</span></span>

1. <span data-ttu-id="e086c-151">Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**.</span><span class="sxs-lookup"><span data-stu-id="e086c-151">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="e086c-152">Nell'elenco, selezionare il cespite padre da installare in un'altra unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="e086c-152">In the list, select the parent asset to install on another functional location.</span></span>
3. <span data-ttu-id="e086c-153">Selezionare **Installa cespite**.</span><span class="sxs-lookup"><span data-stu-id="e086c-153">Select **Install asset**.</span></span>

    <span data-ttu-id="e086c-154">La sezione **Attributi** mostra gli attributi cespite impostati sul cespite padre.</span><span class="sxs-lookup"><span data-stu-id="e086c-154">The **Attributes** section shows the asset attributes that are set up on the parent asset.</span></span>

4. <span data-ttu-id="e086c-155">Selezionare la nuova ubicazione nel campo **Unità funzionale**.</span><span class="sxs-lookup"><span data-stu-id="e086c-155">In the **Functional location** field, select the new location.</span></span>
5. <span data-ttu-id="e086c-156">Il campo **Validità** viene impostato automaticamente sulla data e ora corrente.</span><span class="sxs-lookup"><span data-stu-id="e086c-156">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="e086c-157">Tuttavia, è possibile selezionare una data e un'ora diverse per l'inizio della validità della installazione nella struttura di cespiti.</span><span class="sxs-lookup"><span data-stu-id="e086c-157">However, you can select a different date and time that the installation on the asset structure is valid from.</span></span>
6. <span data-ttu-id="e086c-158">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e086c-158">Select **OK**.</span></span>
