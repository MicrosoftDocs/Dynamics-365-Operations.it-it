---
title: Creare e aggiornare gli orari del punto vendita
description: In questo argomento viene descritto come creare e aggiornare gli orari del punto vendita in Commerce Headquarters.
author: josaw1
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 00c532dfa9ceed2cda6652496d874cb82785dc7b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230642"
---
# <a name="create-and-update-store-hours"></a><span data-ttu-id="fa40a-103">Creare e aggiornare gli orari del punto vendita</span><span class="sxs-lookup"><span data-stu-id="fa40a-103">Create and update store hours</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="fa40a-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="fa40a-104">Overview</span></span>

<span data-ttu-id="fa40a-105">I rivenditori possono creare e gestire gli orari di differenti punti vendita in tutte le aree geografiche da un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="fa40a-105">From a single place, retailers can create, maintain, and manage the store hours for different stores across geographic regions.</span></span> <span data-ttu-id="fa40a-106">Gli orari dei punti vendita possono quindi essere visualizzati nei terminali POS.</span><span class="sxs-lookup"><span data-stu-id="fa40a-106">The store hours can then be shown on point of sale (POS) terminals.</span></span> <span data-ttu-id="fa40a-107">In questo modo, i cassieri possono condividere tali orari con i clienti e fornire informazioni utili a quelli interessati a fare acquisti in altri punti vendita.</span><span class="sxs-lookup"><span data-stu-id="fa40a-107">In this way, cashiers can share store hours with customers and better help shoppers who are interested in inventory in other stores.</span></span> <span data-ttu-id="fa40a-108">Gli orari del punto vendita possono essere stampati sulle ricevute, nel caso in cui i clienti intendano ritornare al punto vendita in seguito.</span><span class="sxs-lookup"><span data-stu-id="fa40a-108">The store hours can also be printed on receipts, in case customers want to return to the store later.</span></span>

<span data-ttu-id="fa40a-109">Molteplici orari possono essere configurati in differenti canali.</span><span class="sxs-lookup"><span data-stu-id="fa40a-109">Multiple store hours can be configured across different channels.</span></span> <span data-ttu-id="fa40a-110">Questi canali includono negozi fisici, servizi clienti, dispositivi mobili e siti di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="fa40a-110">These channels include brick-and-mortar stores, call centers, mobile devices, and e-Commerce sites.</span></span>

<span data-ttu-id="fa40a-111">Se un cliente ha un ordine per un prelievo presso un altro punto vendita, il cassiere può selezionare le date in cui il prelievo sarà disponibile in quel punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fa40a-111">If a customer has a pickup order for a different store, the cashier can select dates when the pickup will be available in that store.</span></span> <span data-ttu-id="fa40a-112">La ricerca del punto vendita fornirà un riferimento alle date e agli orari del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fa40a-112">The store lookup will provide a reference to the dates and store times.</span></span> <span data-ttu-id="fa40a-113">Il cassiere può selezionare una data e un ubicazione nonché stampare una ricevuta di prelievo che include gli orari del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fa40a-113">The cashier can select a date and location, and can also print a pickup receipt that includes the store hours.</span></span>

<span data-ttu-id="fa40a-114">Questa funzionalità è disponibile in Microsoft Dynamics 365 Retail versioni 8.1.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="fa40a-114">This functionality is available in Microsoft Dynamics 365 Retail versions 8.1.2 and later.</span></span>

## <a name="configure-store-hours"></a><span data-ttu-id="fa40a-115">Configurare gli orari del punto vendita</span><span class="sxs-lookup"><span data-stu-id="fa40a-115">Configure store hours</span></span>

<span data-ttu-id="fa40a-116">Attenersi a questa procedura per configurare gli orari del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fa40a-116">Follow these steps to configure store hours.</span></span>

1. <span data-ttu-id="fa40a-117">Vai a **Retail e Commerce** \> **Impostazione canale** \> **Orario punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="fa40a-117">Go to **Retail and Commerce** \> **Channel Setup** \> **Store hours**.</span></span>
2. <span data-ttu-id="fa40a-118">Selezionare **Nuovo** per creare un nuovo modello di orari.</span><span class="sxs-lookup"><span data-stu-id="fa40a-118">Select **New** to create a new store hours template.</span></span> <span data-ttu-id="fa40a-119">Per utilizzare un modello esistente, selezionare il modello nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="fa40a-119">To use an existing template, select the template in the left pane.</span></span>
3. <span data-ttu-id="fa40a-120">Nella finestra di dialogo **Aggiungi intervallo**, definire l'intervallo di date, gli orari del punto vendita e tutte le festività necessarie.</span><span class="sxs-lookup"><span data-stu-id="fa40a-120">In the **Add range** dialog box, define the date range, the store hours, and any holidays that are required.</span></span>

    - <span data-ttu-id="fa40a-121">Se gli orari del punto vendita non cambiano, selezionare **Senza fine** nel campo **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="fa40a-121">If store hours don't change, select **Never ends** in the **End date** field.</span></span>
    - <span data-ttu-id="fa40a-122">Se gli orari del punto vendita si riferiscono a un mese, una settimana, o un giorno specifico, impostare le date appropriate nei campi **Data di fine** e **Data di inizio**.</span><span class="sxs-lookup"><span data-stu-id="fa40a-122">If the store hours are for a specific month, week, or day, set the appropriate dates in the **Start Date** and **End date** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa40a-123">È possibile creare più modelli con date di inizio e di fine che si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="fa40a-123">You can create multiple templates that have overlapping start and end dates.</span></span> <span data-ttu-id="fa40a-124">Di conseguenza, è ad esempio possibile definire gli orari dei punti vendita con fusi orari differenti.</span><span class="sxs-lookup"><span data-stu-id="fa40a-124">Therefore, you can, for example, define store hours for stores in different time zones.</span></span>

    <span data-ttu-id="fa40a-125">![Finestra di dialogo Aggiungi intervallo](../dev-itpro/media/Storehours1.png "Finestra di dialogo Aggiungi intervallo")</span><span class="sxs-lookup"><span data-stu-id="fa40a-125">![Add range dialog box](../dev-itpro/media/Storehours1.png "Add range dialog box")</span></span>

4. <span data-ttu-id="fa40a-126">Associare il modello di orari ai punti vendita in cui verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="fa40a-126">Associate the store hours template with the stores where it will be used.</span></span> <span data-ttu-id="fa40a-127">Nella finestra di dialogo **Scegli nodi organizzazione**, selezionare i punti vendita, le aree geografiche e le organizzazioni a cui il modello deve essere associato.</span><span class="sxs-lookup"><span data-stu-id="fa40a-127">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>

    - <span data-ttu-id="fa40a-128">Un solo modello di orari può essere associato a ogni punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fa40a-128">Only one store hours template can be associated with each store.</span></span>
    - <span data-ttu-id="fa40a-129">Utilizzare i pulsanti freccia per selezionare punti vendita, aree geoagrafiche o organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="fa40a-129">Use the arrow buttons to select stores, regions, or organizations.</span></span> <span data-ttu-id="fa40a-130">Il calendario sarà disponibile nei punti vendita o nei gruppi di punti vendita e sarà visibile nel POS come riferimento.</span><span class="sxs-lookup"><span data-stu-id="fa40a-130">The calendar will be available to the stores or store groups, and it will be visible at the POS for reference.</span></span>

    <span data-ttu-id="fa40a-131">![Finestra di dialogo Scegli nodi organizzazione](../dev-itpro/media/Storehours2.png "Finestra di dialogo Scegli nodi organizzazione")</span><span class="sxs-lookup"><span data-stu-id="fa40a-131">![Choose organization nodes dialog box](../dev-itpro/media/Storehours2.png "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="fa40a-132">Nella pagina **Programmazione della distribuzione**, eseguire i processi **1070** e **1090** per rendere disponibili gli orari del punto vendita nel POS.</span><span class="sxs-lookup"><span data-stu-id="fa40a-132">On the **Distribution schedule** page, run the **1070** and **1090** jobs to make the store hours available to the POS.</span></span>

## <a name="add-store-hours-to-printed-receipts"></a><span data-ttu-id="fa40a-133">Aggiungere gli orari del punto vendita sulle ricevute stampate</span><span class="sxs-lookup"><span data-stu-id="fa40a-133">Add store hours to printed receipts</span></span>

<span data-ttu-id="fa40a-134">Seguire questi passaggi per aggiungere gli orari del punto vendita sulle ricevute POS stampate.</span><span class="sxs-lookup"><span data-stu-id="fa40a-134">Follow these steps to add store hours to the printed POS receipts.</span></span>

1. <span data-ttu-id="fa40a-135">Aprire Designer ricevute.</span><span class="sxs-lookup"><span data-stu-id="fa40a-135">Open the receipt designer.</span></span>
2. <span data-ttu-id="fa40a-136">Selezionare **Piè di pagina** nell'angolo in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="fa40a-136">Select **Footer** in the lower-left corner.</span></span>
3. <span data-ttu-id="fa40a-137">Trascinare l'elemento **Orario punto vendita** dal riquadro sinistro sul piè di pagina nella parte inferiore del modello di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="fa40a-137">Drag the **Store hours** element from the left pane to the footer at the bottom of the receipt template.</span></span>
4. <span data-ttu-id="fa40a-138">È possibile modificare le etichette predefinite nell'elemento **Orario punto vendita** come necessario.</span><span class="sxs-lookup"><span data-stu-id="fa40a-138">You can edit the default label on the **Store hours** element as you require.</span></span>
5. <span data-ttu-id="fa40a-139">Salvare la ricevuta e chiudere Designer ricevute.</span><span class="sxs-lookup"><span data-stu-id="fa40a-139">Save the receipt, and close the receipt designer.</span></span>
6. <span data-ttu-id="fa40a-140">Nella pagina **Programmazione della distribuzione**, eseguire i processi **1070** e **1090**.</span><span class="sxs-lookup"><span data-stu-id="fa40a-140">On the **Distribution schedule** page, run the **1070** and **1090** jobs.</span></span>
7. <span data-ttu-id="fa40a-141">Accedere al POS.</span><span class="sxs-lookup"><span data-stu-id="fa40a-141">Sign in to the POS.</span></span>
8. <span data-ttu-id="fa40a-142">Completare una vendita e selezionare la stampa di una ricevuta.</span><span class="sxs-lookup"><span data-stu-id="fa40a-142">Complete a sale, and select to print a receipt.</span></span>

<span data-ttu-id="fa40a-143">Le ricevute POS ora includono gli orari del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fa40a-143">POS receipts now include the store hours.</span></span> <span data-ttu-id="fa40a-144">Se nel modello sono state incluse le festività, saranno visualizzate sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="fa40a-144">If any holidays were included in the template, they are shown on the receipt.</span></span>

<span data-ttu-id="fa40a-145">![Esempio di ricevuta](../dev-itpro/media/Storehours3.png "Esempio di ricevuta")</span><span class="sxs-lookup"><span data-stu-id="fa40a-145">![Receipt example](../dev-itpro/media/Storehours3.png "Receipt example")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]