---
title: Integrare la gestione cespiti con cespiti
description: Questo argomento spiega come integrare i moduli Cespiti e Gestione cespiti, in modo da poter collegare i cespiti ai cespiti in manutenzione.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: adc14019c243b1992cdaa22ef7aa32cb44bfffd9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253592"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="8f3ca-103">Integrare la gestione cespiti con cespiti</span><span class="sxs-lookup"><span data-stu-id="8f3ca-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8f3ca-104">Integrando i moduli **Gestione cespiti** e **Cespiti** è possibile collegare i cespiti ai cespiti in manutenzione.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="8f3ca-105">Gli utenti di cespiti possono quindi creare un cespite in manutenzione da un cespite nuovo o esistente e gli utenti della gestione cespiti possono associare un cespite in manutenzione con un cespite esistente.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="8f3ca-106">Questa funzione consente inoltre agli utenti di cespiti di visualizzare facilmente i costi registrati dagli ordini di lavoro per i relativi cespiti in manutenzione.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="8f3ca-107">In questo argomento, i *cespiti in manutenzione* si riferiscono ai cespiti del modulo **Gestione cespiti** e i *cespiti* si riferiscono ai cespiti del modulo **Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="8f3ca-108">Impostare un ubicazione predefinita per i nuovi cespiti in manutenzione creati dai cespiti (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8f3ca-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="8f3ca-109">Questa configurazione opzionale consente di impostare un'unità funzionale predefinita per i nuovi cespiti in manutenzione creati da cespiti.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="8f3ca-110">In genere questa configurazione viene eseguita solo una volta, se la si completa del tutto.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="8f3ca-111">Per completare la configurazione, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-112">Fare clic su **Gestione cespiti \> Impostazione \> Parametri di gestione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="8f3ca-113">Nella scheda **Cespiti**, nel campo **Unità funzionale** , selezionare l'unità predefinita.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="8f3ca-114">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="8f3ca-115">Utilizzare cespiti e cespiti in manutenzione integrati</span><span class="sxs-lookup"><span data-stu-id="8f3ca-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="8f3ca-116">Questa sezione fornisce una raccolta di procedure che mostrano vari modi per utilizzare le funzionalità di gestione cespiti e cespiti integrate.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="8f3ca-117">Associare un cespite in manutenzione esistente a un cespite</span><span class="sxs-lookup"><span data-stu-id="8f3ca-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="8f3ca-118">Per associare un cespite in manutenzione esistente a un cespite, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-119">Andare a **Gestione cespiti \> Cespiti \> Tutti i cespiti** (o **Cespiti attivi**).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="8f3ca-120">Selezionare un cespite.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-120">Select an asset.</span></span>
1. <span data-ttu-id="8f3ca-121">Nella scheda dettaglio **Cespiti**, nel campo **Numero cespite**, selezionare un cespite esistente.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="8f3ca-122">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="8f3ca-123">Visualizzare il cespite associato a un cespite in manutenzione selezionato</span><span class="sxs-lookup"><span data-stu-id="8f3ca-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="8f3ca-124">Per visualizzare il cespite associato a un cespite in manutenzione selezionato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-125">Andare a **Gestione cespiti \> Cespiti \> Tutti i cespiti** (o **Cespiti attivi**).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="8f3ca-126">Selezionare un cespite.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-126">Select an asset.</span></span>
1. <span data-ttu-id="8f3ca-127">Nella scheda dettaglio **Cespiti**, nel campo **Numero cespiti**, selezionare il collegamento.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="8f3ca-128">Viene visualizzata la pagina **Cespiti** per il cespite selezionato.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="8f3ca-129">(In genere, questa pagina è disponibile in **Cespiti \> Cespiti \> Cespiti**).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="8f3ca-130">Visualizzare il cespite di manutenzione associato a un cespite selezionato</span><span class="sxs-lookup"><span data-stu-id="8f3ca-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="8f3ca-131">Per visualizzare il cespite associato a un cespite di manutenzione selezionato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-132">Passare a **Cespiti \> Cespiti \> Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="8f3ca-133">Selezionare un cespite.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-133">Select an asset.</span></span>
1. <span data-ttu-id="8f3ca-134">Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Visualizza**, selezionare **Cespite in manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="8f3ca-135">Viene visualizzata la pagina **Cespite in manutenzione** per il cespite associato al cespite selezionato.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="8f3ca-136">(In genere, questa pagina è disponibile in **Gestione cespiti \> Cespiti \> Tutti i cespiti**).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="8f3ca-137">Visualizzare i costi di manutenzione associati a un cespite</span><span class="sxs-lookup"><span data-stu-id="8f3ca-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="8f3ca-138">Gli ordini di lavoro di gestione cespiti possono essere registrati per i cespiti in manutenzione e ognuno di questi ordini di lavoro ha in genere un costo.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="8f3ca-139">Quando un cespite è associato a un cespite in manutenzione, è possibile passare direttamente dal cespite per visualizzare i relativi costi.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="8f3ca-140">Per visualizzare i costi di manutenzione associati a un cespite, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-141">Passare a **Cespiti \> Cespiti \> Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="8f3ca-142">Selezionare un cespite.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-142">Select an asset.</span></span>
1. <span data-ttu-id="8f3ca-143">Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Visualizza**, selezionare **Costo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="8f3ca-144">Viene visualizzata la pagina **Costo di manutenzione** con i relativi costi.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="8f3ca-145">Creare un nuovo cespite in manutenzione per un cespite esistente</span><span class="sxs-lookup"><span data-stu-id="8f3ca-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="8f3ca-146">Per creare un nuovo cespite in manutenzione per un cespite esistente, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-147">Passare a **Cespiti \> Cespiti \> Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="8f3ca-148">Selezionare un cespite.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-148">Select an asset.</span></span>
1. <span data-ttu-id="8f3ca-149">Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Nuovo**, selezionare **Crea cespite in manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="8f3ca-150">(Se questa opzione non è disponibile, un cespite in manutenzione potrebbe già essere associato al cespite selezionato).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="8f3ca-151">Terminare la creazione del cespite come descritto in [Creare un cespite](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="8f3ca-152">Creare un nuovo cespite e aggiungere un nuovo cespite in manutenzione</span><span class="sxs-lookup"><span data-stu-id="8f3ca-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="8f3ca-153">Per creare un nuovo cespite e aggiungere un nuovo cespite in manutenzione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-154">Passare a **Cespiti \> Cespiti \> Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="8f3ca-155">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8f3ca-156">Terminare la creazione del cespite come descritto in [Creare un cespite](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="8f3ca-157">Nella scheda **Gestione cespiti** del riquadro azioni, nel gruppo **Nuovo**, selezionare **Crea cespite in manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="8f3ca-158">Terminare la creazione del cespite come descritto in [Creare un cespite](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="8f3ca-159">Rimuovere l'associazione tra due cespiti</span><span class="sxs-lookup"><span data-stu-id="8f3ca-159">Remove the association between two assets</span></span>

<span data-ttu-id="8f3ca-160">In alcuni casi, potrebbe essere necessario annullare l'associazione di un cespite in manutenzione dal relativo cespite.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="8f3ca-161">Ad esempio, se vuoi [creare un nuovo cespite in manutenzione](#new-maintenance-from-fixed) da un cespite, è necessario prima rimuovere qualsiasi associazione esistente.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="8f3ca-162">Per rimuovere un'associazione esistente tra un cespite in manutenzione e un cespite, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="8f3ca-163">Andare a **Gestione cespiti \> Cespiti \> Tutti i cespiti** (o **Cespiti attivi**).</span><span class="sxs-lookup"><span data-stu-id="8f3ca-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="8f3ca-164">Trovare e aprire il cespite.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="8f3ca-165">Nella scheda dettaglio **Cespite** cancellare il valore nel campo **Unità funzionale**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="8f3ca-166">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-166">On the Action Pane, select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]