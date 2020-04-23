---
title: Creare un nuovo layout di magazzino
description: In questo argomento viene descritto come impostare le informazioni sulle ubicazioni in un magazzino.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09666e95cc90913f1bf8555b9ff2c48aa55369ed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214023"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="d5284-103">Creare un nuovo layout di magazzino</span><span class="sxs-lookup"><span data-stu-id="d5284-103">Create a new warehouse layout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5284-104">In questo argomento viene descritto come impostare le informazioni sulle ubicazioni in un magazzino.</span><span class="sxs-lookup"><span data-stu-id="d5284-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="d5284-105">È applicabile solo ai magazzini creati utilizzando "Operazioni di magazzino di base" del modulo Gestione inventario, non ai magazzini creati nel modulo Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="d5284-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="d5284-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="d5284-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="d5284-107">Impostare la capacità dell'ubicazione predefinita</span><span class="sxs-lookup"><span data-stu-id="d5284-107">Set the default location capacity</span></span>
1. <span data-ttu-id="d5284-108">Nel pannello di navigazione, andare a **Moduli > Gestione magazzino > Impostazione > Parametri di gestione articoli e magazzino**.</span><span class="sxs-lookup"><span data-stu-id="d5284-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="d5284-109">Selezionare la scheda **Ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="d5284-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="d5284-110">Nel campo **Larghezza standard** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d5284-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="d5284-111">Nel campo **Profondità standard** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d5284-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="d5284-112">Nel campo **Altezza standard** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d5284-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="d5284-113">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d5284-113">Select **Save**.</span></span>
7. <span data-ttu-id="d5284-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5284-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="d5284-115">Definire il formato del nome dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="d5284-115">Define the location name format</span></span>
1. <span data-ttu-id="d5284-116">Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazione > Attività periodiche > Suddivisione scorte > Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="d5284-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="d5284-117">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d5284-117">Select **New**.</span></span>
3. <span data-ttu-id="d5284-118">Digitare un valore nel campo **Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="d5284-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="d5284-119">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="d5284-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="d5284-120">Nel campo **Sito** selezionare il record desiderato nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="d5284-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="d5284-121">Attivare/disattivare l'espansione della sezione **Nomi ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="d5284-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="d5284-122">Le opzioni di questa sezione definiscono il formato predefinito per i nomi delle ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="d5284-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="d5284-123">Nel nostro esempio, includeremo il numero di sezione, il numero di scaffale e il numero di ripiano.</span><span class="sxs-lookup"><span data-stu-id="d5284-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="d5284-124">Impostare l'opzione **Includi sezione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d5284-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="d5284-125">Impostare l'opzione **Includi scaffale** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d5284-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="d5284-126">Nel campo **Formato** digitare un valore per lo scaffale.</span><span class="sxs-lookup"><span data-stu-id="d5284-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="d5284-127">Impostare l'opzione **Includi ripiano** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d5284-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="d5284-128">Nel campo **Formato** digitare un valore per il ripiano.</span><span class="sxs-lookup"><span data-stu-id="d5284-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="d5284-129">Definire le ubicazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="d5284-129">Define warehouse locations</span></span>
1. <span data-ttu-id="d5284-130">Nel riquadro azioni selezionare **Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="d5284-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="d5284-131">Selezionare **Creazione guidata ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="d5284-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="d5284-132">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d5284-132">Select **Next**.</span></span>
4. <span data-ttu-id="d5284-133">Deselezionare l'opzione **Banchine di uscita**.</span><span class="sxs-lookup"><span data-stu-id="d5284-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="d5284-134">Deselezionare l'opzione **Ubicazioni di stoccaggio**.</span><span class="sxs-lookup"><span data-stu-id="d5284-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="d5284-135">Selezionare **Avanti** fino a che non viene visualizzato **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d5284-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="d5284-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5284-136">Close the page.</span></span>
8. <span data-ttu-id="d5284-137">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5284-137">Refresh the page.</span></span>

