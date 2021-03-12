---
title: Spedizione parziale di un carico di trasporto
description: In questo argomento viene descritto come spedire parzialmente un carico e posticipare la pianificazione della capacità del carico.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 68a3d175e89e89d0909b140863b1aa61a184fce6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963287"
---
# <a name="partial-shipment-of-a-transport-load"></a><span data-ttu-id="b7371-103">Spedizione parziale di un carico di trasporto</span><span class="sxs-lookup"><span data-stu-id="b7371-103">Partial shipment of a transport load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b7371-104">Con la spedizione parziale dei carichi, è possibile gestire i carichi in cui la capacità non può essere determinata fino a quando tutte le righe di vendita non sono state aggiunte a un carico.</span><span class="sxs-lookup"><span data-stu-id="b7371-104">By setting up partial shipment of loads, you can handle loads where the capacity can't be determined until all the sales lines have been added to a load.</span></span> <span data-ttu-id="b7371-105">Il processo può quindi essere finalizzato una volta che si conosce il conteggio esatto dei pallet.</span><span class="sxs-lookup"><span data-stu-id="b7371-105">The process can then be finalized when the exact pallet count is known.</span></span> <span data-ttu-id="b7371-106">Pertanto, non è necessario decidere quali pallet verranno assegnati a cui trasporto fino al momento in cui un trasporto non viene caricato fisicamente in magazzino approntato.</span><span class="sxs-lookup"><span data-stu-id="b7371-106">Therefore, you don't have to decide which pallets will be assigned to which transport until the moment when a transport is being physically loaded out of the staged inventory.</span></span>

<span data-ttu-id="b7371-107">Questa funzionalità offre un'alternativa all'applicazione di una struttura più rigida, in cui è necessario stabilire quali pallet verranno assegnati a quale trasporto prima di poter creare il lavoro di prelievo o il lavoro di carico.</span><span class="sxs-lookup"><span data-stu-id="b7371-107">This feature offers an alternative to the enforcement of a more rigid structure, where you must determine which pallets will be assigned to which transport before picking work or loading work can be created.</span></span> <span data-ttu-id="b7371-108">Gli utenti possono invece configurare carichi individuali per la conferma di una spedizione parziale.</span><span class="sxs-lookup"><span data-stu-id="b7371-108">Instead, users can configure individual loads for a partial shipment confirmation.</span></span> <span data-ttu-id="b7371-109">Possono quindi avvenire i processi di caricamento del trasporto per quei carichi.</span><span class="sxs-lookup"><span data-stu-id="b7371-109">The transport loading processes for those loads can then occur.</span></span> <span data-ttu-id="b7371-110">Di conseguenza, il reparto di pianificazione del trasporto può pianificare i carichi senza dover considerare la capacità dei trasporti individuali.</span><span class="sxs-lookup"><span data-stu-id="b7371-110">Therefore, the transportation planning department can plan loads without having to consider the capacity of individual transports.</span></span>

<span data-ttu-id="b7371-111">Al momento del caricamento, i lavoratori possono definire un nuovo carico di trasporto in cui può essere caricato un pallet.</span><span class="sxs-lookup"><span data-stu-id="b7371-111">At the time of loading, workers can define a new transport load that a pallet can be loaded to.</span></span> <span data-ttu-id="b7371-112">In alternativa, è possibile identificare un carico di trasporto esistente.</span><span class="sxs-lookup"><span data-stu-id="b7371-112">Alternatively, they can identify an existing transport load.</span></span> <span data-ttu-id="b7371-113">Questi dati possono essere registrati mediante un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b7371-113">This data can be recorded via a mobile device.</span></span> <span data-ttu-id="b7371-114">Di conseguenza, più addetti al magazzino possono caricare scorte dagli stessi carichi o da carichi diversi nello stesso camion.</span><span class="sxs-lookup"><span data-stu-id="b7371-114">Therefore, several warehouse workers can load inventory from the same loads or different loads onto the same truck.</span></span> <span data-ttu-id="b7371-115">I carichi possono quindi essere spediti in toto o parzialmente.</span><span class="sxs-lookup"><span data-stu-id="b7371-115">The loads can then be fully or partially shipped.</span></span>

> [!NOTE] 
> <span data-ttu-id="b7371-116">Per caricare scorte da un carico a un determinato carico di trasporto e spedire parzialmente il carico, il lavoro deve essere generato utilizzando una classe di caricamento in un modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b7371-116">In order to load inventory from a load to a specific transport load and partially ship the load, work must be generated by using a loading class in a work template.</span></span> <span data-ttu-id="b7371-117">Il tipo di prelievo ordinario del tipo **Prelievo** non può essere caricato in un carico di trasporto come un camion.</span><span class="sxs-lookup"><span data-stu-id="b7371-117">Ordinary picking work of the **Picking** type can't be loaded to a transport load such as a truck.</span></span>

## <a name="set-up-transport-loads-for-partial-shipment"></a><span data-ttu-id="b7371-118">Impostare carichi di trasporto per la spedizione parziale</span><span class="sxs-lookup"><span data-stu-id="b7371-118">Set up transport loads for partial shipment</span></span>

<span data-ttu-id="b7371-119">L'impostazione della spedizione parziale di carichi è costituita dalle due procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="b7371-119">The setup for partial shipment of loads consists of the following two procedures.</span></span>

### <a name="set-the-loading-strategy"></a><span data-ttu-id="b7371-120">Impostare la strategia di caricamento</span><span class="sxs-lookup"><span data-stu-id="b7371-120">Set the loading strategy</span></span>

<span data-ttu-id="b7371-121">È necessario attivare il caricamento parziale impostando la strategia di caricamento.</span><span class="sxs-lookup"><span data-stu-id="b7371-121">You must enable partial loading by setting the loading strategy.</span></span> <span data-ttu-id="b7371-122">È possibile impostare la strategia di caricamento dopo aver creato un carico.</span><span class="sxs-lookup"><span data-stu-id="b7371-122">You can set the loading strategy after you've created a load.</span></span>

1. <span data-ttu-id="b7371-123">Selezionare **Gestione magazzino** \> **Carichi** \> **Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="b7371-123">Select **Warehouse management** \> **Loads** \> **All loads**.</span></span>
2. <span data-ttu-id="b7371-124">Selezionare un carico, quindi fare clic su **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="b7371-124">Select a load, and then click **Header**.</span></span>
3. <span data-ttu-id="b7371-125">Nel campo **Strategia di caricamento** selezionare **Spedizione carico parziale consentita**.</span><span class="sxs-lookup"><span data-stu-id="b7371-125">In the **Loading strategy** field, select **Partial load shipping allowed**.</span></span>

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a><span data-ttu-id="b7371-126">Creare una voce di menu per il caricamento dei carichi di trasporto</span><span class="sxs-lookup"><span data-stu-id="b7371-126">Create a menu item for loading of transport loads</span></span>

<span data-ttu-id="b7371-127">È necessario creare una nuova voce di menu che consenta il caricamento dei carichi di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b7371-127">You must create a new menu item that enables transport loads to be loaded.</span></span> <span data-ttu-id="b7371-128">Un carico di trasporto consente di raggruppare righe di lavoro di uno o più carichi.</span><span class="sxs-lookup"><span data-stu-id="b7371-128">A transport load lets you group work lines from one load or multiple loads.</span></span> <span data-ttu-id="b7371-129">Tutto quello che viene aggiunto al carico di trasporto può quindi essere spedito utilizzando uno scanner del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b7371-129">Everything that is added to the transport load can then be shipped by using a mobile scanner.</span></span>

1. <span data-ttu-id="b7371-130">Selezionare **Gestione magazzino** \> **Impostazioni** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="b7371-130">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="b7371-131">Selezionare **Nuovo**, quindi nel campo **Modo**, selezionare **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b7371-131">Select **New**, and then, in the **Mode** field, select **Work**.</span></span>
3. <span data-ttu-id="b7371-132">Impostare l'opzione **Utilizza lavoro esistente** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b7371-132">Set the **Use existing work** option to **Yes**.</span></span>
4. <span data-ttu-id="b7371-133">Nella scheda **Generale**, nelc ampo **Diretto da** selezionare **Caricamento di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="b7371-133">On the **General** tab, in the **Directed by** field, select **Transport loading**.</span></span>
5. <span data-ttu-id="b7371-134">Per attivare la conferma di spedizione su uno scanner di dispositivo mobile, nel campo **Tipo consentito di conferma spedizione** selezionare **Carico di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="b7371-134">To enable shipment confirmation on a mobile scanner, in the **Allowed ship confirmation type** field, select **Transport load**.</span></span>

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a><span data-ttu-id="b7371-135">Confermare la spedizione di un carico di trasporto dal client</span><span class="sxs-lookup"><span data-stu-id="b7371-135">Confirm shipment of a transport load from the client</span></span>

<span data-ttu-id="b7371-136">Questa impostazione consente di confermare un carico di trasporto che include un intero carico o caricato parzialmente da spedire.</span><span class="sxs-lookup"><span data-stu-id="b7371-136">This setup lets you confirm a transport load that includes a full load or a partially loaded load to be shipped.</span></span>

1. <span data-ttu-id="b7371-137">Selezionare **Gestione magazzino** \> **Carichi** \> **Carichi di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="b7371-137">Select **Warehouse management** \> **Loads** \> **Transport loads**.</span></span>
2. <span data-ttu-id="b7371-138">Nel riquadro azioni, nella scheda **Spedisci e ricevi**, nel gruppo **Conferma** selezionare **Trasporto**.</span><span class="sxs-lookup"><span data-stu-id="b7371-138">On the Action Pane, on the **Ship and receive** tab, in the **Confirm** group, select **Transport**.</span></span>
