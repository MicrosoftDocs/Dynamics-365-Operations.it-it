---
title: Imposta prelievo del cluster
description: In questo argomento viene descritto come impostare il prelievo cluster e l'utilizzo della conferma dell'articolo con prelievo cluster.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 009345e608c26887fedbe4a9c268367080593da2
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017577"
---
# <a name="set-up-cluster-picking"></a><span data-ttu-id="ff864-103">Imposta prelievo del cluster</span><span class="sxs-lookup"><span data-stu-id="ff864-103">Set up cluster picking</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ff864-104">In questo argomento viene descritto come abilitare i lavoratori a utilizzare i propri dispositivi mobili per raggruppare il lavoro di prelievo nei cluster, in modo che possano prelevare gli articoli da un unica ubicazione per più ordini di lavoro contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ff864-104">This topic describes how to enable workers to use their mobile devices to group picking work into clusters, so that they can pick items from a single location for multiple work orders at the same time.</span></span> <span data-ttu-id="ff864-105">Questo tipo di azione viene denominato *prelievo del cluster*.</span><span class="sxs-lookup"><span data-stu-id="ff864-105">This is called *cluster picking*.</span></span>

## <a name="about-cluster-picking"></a><span data-ttu-id="ff864-106">Informazioni sul prelievo del cluster</span><span class="sxs-lookup"><span data-stu-id="ff864-106">About cluster picking</span></span>

<span data-ttu-id="ff864-107">Dopo aver emesso gli ordini di lavoro al magazzino, il lavoratore può utilizzare un dispositivo mobile per assegnare gli ordini a un cluster.</span><span class="sxs-lookup"><span data-stu-id="ff864-107">After work orders are released to the warehouse, the worker can use a mobile device to assign the orders to a cluster.</span></span> <span data-ttu-id="ff864-108">Il cluster organizzerà il lavoro di prelievo per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="ff864-108">The cluster will organize the picking work for the worker.</span></span> <span data-ttu-id="ff864-109">Quando un ordine di lavoro viene assegnato a un cluster, il lavoratore deve utilizzare il prelievo del cluster per eseguire il lavoro di prelievo dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="ff864-109">When a work order is assigned to a cluster, the worker must use cluster picking to perform the picking work for the order.</span></span> <span data-ttu-id="ff864-110">Il lavoratore non potrà utilizzare altri metodi di prelievo.</span><span class="sxs-lookup"><span data-stu-id="ff864-110">The worker cannot use other picking methods.</span></span> <span data-ttu-id="ff864-111">Se un ordine di lavoro viene assegnato a un cluster per errore, il lavoratore dovrà interrompere il cluster e quindi ricrearlo.</span><span class="sxs-lookup"><span data-stu-id="ff864-111">If a work order is assigned to a cluster by mistake, the worker must break the cluster and then re-create it.</span></span>

<span data-ttu-id="ff864-112">Se necessario, un lavoratore può passare un cluster a un altro lavoratore.</span><span class="sxs-lookup"><span data-stu-id="ff864-112">If needed, a worker can pass a cluster to another worker.</span></span> <span data-ttu-id="ff864-113">Tale operazione modifica lo stato in Superato.</span><span class="sxs-lookup"><span data-stu-id="ff864-113">This changes the cluster status to Passed.</span></span> <span data-ttu-id="ff864-114">Quando il lavoratore utilizza un dispositivo mobile per indicare il completamento del prelievo e dello stoccaggio, è necessario confermare la spedizione o il carico nel client.</span><span class="sxs-lookup"><span data-stu-id="ff864-114">When the worker uses a mobile device to indicate that the picking and put away work is completed, the shipment or load must be confirmed in the client.</span></span>

## <a name="enable-cluster-picking"></a><span data-ttu-id="ff864-115">Abilita prelievo del cluster</span><span class="sxs-lookup"><span data-stu-id="ff864-115">Enable cluster picking</span></span>

<span data-ttu-id="ff864-116">Per abilitare il prelievo del cluster, è necessario impostare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ff864-116">To enable cluster picking, you must set up the following:</span></span>

- <span data-ttu-id="ff864-117">**Profili cluster** : consente di specificare se generare automaticamente gli ID del cluster, il numero di posizioni da utilizzare, quando interrompere i cluster e come ordinare in sequenza e verificare il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="ff864-117">**Cluster profiles** – Specify whether to automatically generate cluster   IDs, the number of positions to use, when to break clusters, and how to   sequence and verify the picking work.</span></span>

- <span data-ttu-id="ff864-118">**Modelli di lavoro** : consente di definire la modalità di creazione del lavoro di prelievo per il prelievo del cluster.</span><span class="sxs-lookup"><span data-stu-id="ff864-118">**Work templates** – Define how to create the picking work for cluster   picking.</span></span>

- <span data-ttu-id="ff864-119">**Direttive ubicazione** : consente di specificare dove prelevare gli articoli e dove inserirli.</span><span class="sxs-lookup"><span data-stu-id="ff864-119">**Location directives** – Specify where to pick items from, and where to put   them.</span></span>

- <span data-ttu-id="ff864-120">**Voci di menu del dispositivo mobile** : consente di configurare una voce di menu del dispositivo mobile per utilizzare il lavoro esistente che è diretto dal prelievo del cluster.</span><span class="sxs-lookup"><span data-stu-id="ff864-120">**Mobile device menu items** – Configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="ff864-121">È quindi necessario aggiungere la voce di menu a un menu del dispositivo mobile in modo che sia visualizzato sui dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ff864-121">You must then add the menu item to a mobile device menu so that it is displayed on mobile devices.</span></span>

- <span data-ttu-id="ff864-122">**Parametri di gestione magazzino** : consente di specificare la sequenza numerica da utilizzare se si desidera generare gli identificatori per i cluster.</span><span class="sxs-lookup"><span data-stu-id="ff864-122">**Warehouse management parameters** – Specify the number sequence to use if   you want to generate identifiers for clusters.</span></span>

## <a name="set-up-a-cluster-profile"></a><span data-ttu-id="ff864-123">Impostare un profilo del cluster</span><span class="sxs-lookup"><span data-stu-id="ff864-123">Set up a cluster profile</span></span>

<span data-ttu-id="ff864-124">Per impostare un profilo del cluster, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="ff864-124">To set up a cluster profile, follow these steps:</span></span>

1. <span data-ttu-id="ff864-125">Fai clic su **Gestione magazzino** \> **Impostazioni** \> **Dispositivo mobile** \>  **Profili cluster**.</span><span class="sxs-lookup"><span data-stu-id="ff864-125">Click **Warehouse management** \> **Setup** \> **Mobile device** \>  **Cluster profiles**.</span></span>

1. <span data-ttu-id="ff864-126">Fare clic su **Nuovo** per creare un nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="ff864-126">Click **New** to create a new profile.</span></span>

1. <span data-ttu-id="ff864-127">Fare clic su **Crea cluster** e in **Ordinamento cluster** fare su **Nuovo** per impostare i criteri di ordinamento per il cluster.</span><span class="sxs-lookup"><span data-stu-id="ff864-127">Click **Create cluster** and, under **Cluster sorting** , click **New** to set up the sorting criteria for the cluster.</span></span> <span data-ttu-id="ff864-128">I criteri di ordinamento controllano l'ordine in cui il lavoratore eseguirà il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="ff864-128">The sorting criteria control the order in which the worker will perform the picking work.</span></span> <span data-ttu-id="ff864-129">È possibile aggiungere un numero illimitato di criteri.</span><span class="sxs-lookup"><span data-stu-id="ff864-129">You can add as many criteria as needed.</span></span>

1. <span data-ttu-id="ff864-130">Nel campo **Numero progressivo** immetti un numero per definire l'ordine in cui verranno elaborati i criteri di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ff864-130">In the **Sequence number** field, enter a number to define the order in  which the sorting criteria are processed.</span></span>

1. <span data-ttu-id="ff864-131">Nel campo **Nome campo** selezionare il campo che determinerà l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ff864-131">In the **Field name** field, select the field that will determine the sorting.</span></span> <span data-ttu-id="ff864-132">Ad esempio, se si seleziona il campo **WMSLocationId** il lavoro verrà ordinato per posizione.</span><span class="sxs-lookup"><span data-stu-id="ff864-132">For example, if you select the **WMSLocationId** field, the work will be sorted by location.</span></span>

1. <span data-ttu-id="ff864-133">Nel campo **Ordinamento** selezionare una delle seguenti opzioni.</span><span class="sxs-lookup"><span data-stu-id="ff864-133">In the **Sorting** field, select one of the following options.</span></span>

| <span data-ttu-id="ff864-134">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="ff864-134">**Option**</span></span>     | <span data-ttu-id="ff864-135">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ff864-135">**Description**</span></span>                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ff864-136">**Crescente**</span><span class="sxs-lookup"><span data-stu-id="ff864-136">**Ascending**</span></span>  | <span data-ttu-id="ff864-137">Il lavoro di prelievo viene ordinato in ordine crescente in base ai criteri di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ff864-137">Picking work is sequenced in ascending order based on the sorting criteria.</span></span> <span data-ttu-id="ff864-138">Ad esempio, se si utilizza il campo **WMSLocationId** come criterio di ordinamento e l'ID della posizione è 1, 2, 3 e 4, l'utente preleverà prima dalla posizione 4.</span><span class="sxs-lookup"><span data-stu-id="ff864-138">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 4 first.</span></span> |
| <span data-ttu-id="ff864-139">**Decrescente**</span><span class="sxs-lookup"><span data-stu-id="ff864-139">**Descending**</span></span> | <span data-ttu-id="ff864-140">Il lavoro di prelievo viene ordinato in ordine decrescente in base ai criteri di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ff864-140">Picking work is sequenced in descending order based on the sorting criteria.</span></span> <span data-ttu-id="ff864-141">Ad esempio, se si utilizza il campo **WMSLocationId** come criterio di ordinamento e l'ID della posizione è 1, 2, 3 e 4, l'utente preleverà prima dalla posizione 1.</span><span class="sxs-lookup"><span data-stu-id="ff864-141">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 1 first.</span></span> |

## <a name="item-confirmation"></a><span data-ttu-id="ff864-142">Conferma articolo</span><span class="sxs-lookup"><span data-stu-id="ff864-142">Item confirmation</span></span>

<span data-ttu-id="ff864-143">Quando il prelievo cluster viene applicato, la conferma dell'articolo è essenziale per verificare che gli articoli vengano aggiunti ai cluster.</span><span class="sxs-lookup"><span data-stu-id="ff864-143">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="ff864-144">È possibile verificare gli articoli nel prelievo cluster durante il processo di prelievo cluster.</span><span class="sxs-lookup"><span data-stu-id="ff864-144">You can verify items in cluster picking during the cluster picking process.</span></span> <span data-ttu-id="ff864-145">L'impostazione dipende dall'impostazione dei codici a barre del prodotto.</span><span class="sxs-lookup"><span data-stu-id="ff864-145">The setup is based on the product bar code setup.</span></span>

### <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="ff864-146">Impostare la verifica dell'articolo con prelievo cluster</span><span class="sxs-lookup"><span data-stu-id="ff864-146">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="ff864-147">Su una voce di menu del dispositivo mobile, apri il modulo di configurazione per la conferma del lavoro:  **Gestione magazzino** \> **Gestione magazzino** \> **Configurazione** \>  **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="ff864-147">On a mobile device menu item, open the setup form for work confirmation:  **Warehouse management** \> **Warehouse management** \> **Setup** \>  **Mobile device** \> **Mobile device menu items**.</span></span>

1. <span data-ttu-id="ff864-148">Dalle voci di menu del dispositivo mobile, aprire la **configurazione della conferma del lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ff864-148">From the mobile device menu item, open **Work confirmation setup**.</span></span> <span data-ttu-id="ff864-149">L'opzione **Conferma prodotto** consente di verificare ogni pezzo di magazzino dal dispositivo mobile sottoposto a scansione.</span><span class="sxs-lookup"><span data-stu-id="ff864-149">The **Product confirmation** option allows you to verify each piece of inventory from the mobile device when scanned.</span></span>
