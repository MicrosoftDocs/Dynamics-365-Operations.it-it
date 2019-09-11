---
title: Creare e gestire un blocco scorte
description: Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte.
author: perlynne
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2485eaf31226b11106895074ae0ad95e561777b
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916601"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="e3f4e-103">Creare e gestire un blocco scorte</span><span class="sxs-lookup"><span data-stu-id="e3f4e-103">Create and maintain an inventory blocking</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3f4e-104">Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="e3f4e-105">È possibile eseguire la procedura utilizzando la società di dati dimostrativi USMF con i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="e3f4e-106">È necessario disporre di un articolo con scorte disponibili fisiche disponibili prima di iniziare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="e3f4e-107">Creare un blocco scorte</span><span class="sxs-lookup"><span data-stu-id="e3f4e-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="e3f4e-108">Nel **pannello di navigazione** andare a **Moduli > Gestione articoli > Attività periodiche > Gestione qualità > Blocco scorte**.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="e3f4e-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-109">Click **New**.</span></span>
3. <span data-ttu-id="e3f4e-110">Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e3f4e-111">Selezionare dall'elenco l'articolo da scegliere.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="e3f4e-112">Selezionare un numero di articolo con scorte fisiche disponibili che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="e3f4e-113">Se si utilizza USMF, è possibile selezionare l'articolo M9201.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-113">If you’re using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="e3f4e-114">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="e3f4e-115">Se si utilizza l'articolo M9201, è necessario selezionare un valore inferiore a 200.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-115">If you’re using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="e3f4e-116">Espandere la Scheda dettaglio **Dimensioni inventariali**.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="e3f4e-117">Nel campo **Magazzino** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="e3f4e-118">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="e3f4e-119">Se si utilizza l'articolo M9201, è possibile selezionare il magazzino 51.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-119">If you’re using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="e3f4e-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="e3f4e-121">Aggiornare le condizioni del blocco scorte</span><span class="sxs-lookup"><span data-stu-id="e3f4e-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="e3f4e-122">Nella Scheda dettaglio **Generale**, nel campo **Quantità**, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="e3f4e-123">Aggiornare il campo quantità in magazzino in base alla quantità da bloccare.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="e3f4e-124">Nel campo **Data prevista** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="e3f4e-125">Potrebbe essere utile indicare il momento in cui si prevede che le scorte bloccate diventino disponibili per la prenotazione assegnando una data prevista.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="e3f4e-126">Se l'opzione Entrate previste è selezionata per il blocco scorte, impostazione predefinita quando si crea manualmente un blocco, tale data verrà visualizzata sulla transazione prevista.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="e3f4e-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="e3f4e-128">Rimuovere il blocco scorte</span><span class="sxs-lookup"><span data-stu-id="e3f4e-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="e3f4e-129">Nel **riquadro azioni** fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-129">On the **Action pane**, click **Delete**.</span></span>
2. <span data-ttu-id="e3f4e-130">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-130">Click **Yes**.</span></span>
3. <span data-ttu-id="e3f4e-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e3f4e-131">Close the page.</span></span>

