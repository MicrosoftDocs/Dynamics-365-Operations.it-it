---
title: Creare e gestire un blocco scorte
description: Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte.
author: perlynne
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12c6e047e15aaab157e6de70f4a09f500af2965f
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383460"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="f53af-103">Creare e gestire un blocco scorte</span><span class="sxs-lookup"><span data-stu-id="f53af-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f53af-104">Questa procedura illustra come impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita tramite il blocco scorte.</span><span class="sxs-lookup"><span data-stu-id="f53af-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="f53af-105">È possibile eseguire la procedura utilizzando la società di dati dimostrativi USMF con i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="f53af-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="f53af-106">È necessario disporre di un articolo con scorte disponibili fisiche disponibili prima di iniziare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f53af-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="f53af-107">Creare un blocco scorte</span><span class="sxs-lookup"><span data-stu-id="f53af-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="f53af-108">Nel **pannello di navigazione** andare a **Moduli > Gestione articoli > Attività periodiche > Gestione qualità > Blocco scorte**.</span><span class="sxs-lookup"><span data-stu-id="f53af-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="f53af-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f53af-109">Click **New**.</span></span>
3. <span data-ttu-id="f53af-110">Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f53af-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f53af-111">Selezionare dall'elenco l'articolo da scegliere.</span><span class="sxs-lookup"><span data-stu-id="f53af-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="f53af-112">Selezionare un numero di articolo con scorte fisiche disponibili che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="f53af-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="f53af-113">Se si utilizza USMF, è possibile selezionare l'articolo M9201.</span><span class="sxs-lookup"><span data-stu-id="f53af-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="f53af-114">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f53af-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="f53af-115">Se si utilizza l'articolo M9201, è necessario selezionare un valore inferiore a 200.</span><span class="sxs-lookup"><span data-stu-id="f53af-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="f53af-116">Espandere la Scheda dettaglio **Dimensioni inventariali**.</span><span class="sxs-lookup"><span data-stu-id="f53af-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="f53af-117">Nel campo **Magazzino** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f53af-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f53af-118">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f53af-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="f53af-119">Se si utilizza l'articolo M9201, è possibile selezionare il magazzino 51.</span><span class="sxs-lookup"><span data-stu-id="f53af-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="f53af-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f53af-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="f53af-121">Aggiornare le condizioni del blocco scorte</span><span class="sxs-lookup"><span data-stu-id="f53af-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="f53af-122">Nella Scheda dettaglio **Generale**, nel campo **Quantità**, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f53af-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="f53af-123">Aggiornare il campo quantità in magazzino in base alla quantità da bloccare.</span><span class="sxs-lookup"><span data-stu-id="f53af-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="f53af-124">Nel campo **Data prevista** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="f53af-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="f53af-125">Potrebbe essere utile indicare il momento in cui si prevede che le scorte bloccate diventino disponibili per la prenotazione assegnando una data prevista.</span><span class="sxs-lookup"><span data-stu-id="f53af-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="f53af-126">Se l'opzione Entrate previste è selezionata per il blocco scorte, impostazione predefinita quando si crea manualmente un blocco, tale data verrà visualizzata sulla transazione prevista.</span><span class="sxs-lookup"><span data-stu-id="f53af-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="f53af-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f53af-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="f53af-128">Rimuovere il blocco scorte</span><span class="sxs-lookup"><span data-stu-id="f53af-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="f53af-129">Nel **Riquadro azioni** fai clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f53af-129">On the **Action Pane**, click **Delete**.</span></span>
2. <span data-ttu-id="f53af-130">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f53af-130">Click **Yes**.</span></span>
3. <span data-ttu-id="f53af-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f53af-131">Close the page.</span></span>

