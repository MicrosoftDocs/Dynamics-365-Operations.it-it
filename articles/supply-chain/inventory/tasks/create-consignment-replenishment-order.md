---
title: Creare nuovo ordine di rifornimento spedizione
description: In questo argomento viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione.
author: mkirknel
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e993190150e2d82088390d8db4b7c5ada2b0161
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018355"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="849a4-103">Creare nuovo ordine di rifornimento spedizione</span><span class="sxs-lookup"><span data-stu-id="849a4-103">Create a consignment replenishment order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="849a4-104">In questo argomento viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione.</span><span class="sxs-lookup"><span data-stu-id="849a4-104">This topic explains how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="849a4-105">Viene inoltre illustrato come registrare un'entrata prodotti in modo da registrare l'inventario di spedizione come scorte disponibili di proprietà del fornitore.</span><span class="sxs-lookup"><span data-stu-id="849a4-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="849a4-106">Questa procedura viene in genere eseguita da un responsabile approvvigionamenti.</span><span class="sxs-lookup"><span data-stu-id="849a4-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="849a4-107">È possibile utilizzare questa guida nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="849a4-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="849a4-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="849a4-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="849a4-109">Creare nuovo ordine di rifornimento spedizione</span><span class="sxs-lookup"><span data-stu-id="849a4-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="849a4-110">Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Spedizione > Ordini di rifornimento spedizione**.</span><span class="sxs-lookup"><span data-stu-id="849a4-110">In the navigation pane, go to **Modules > Procurement and sourcing > Consignment > Consignment replenishment orders**.</span></span>
2. <span data-ttu-id="849a4-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="849a4-111">Select **New**.</span></span>
3. <span data-ttu-id="849a4-112">Nel campo **Conto fornitore** , selezionare il fornitore **US-104** (è necessario selezionare un fornitore che viene registrato come proprietario nella pagina **Proprietari inventario** ).</span><span class="sxs-lookup"><span data-stu-id="849a4-112">In the **Vendor account** field, select vendor **US-104** (you must select a vendor that's registered as an owner in the **inventory owners** page).</span></span> 
4. <span data-ttu-id="849a4-113">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="849a4-113">Select **OK**.</span></span>
5. <span data-ttu-id="849a4-114">Selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="849a4-114">Select **Add line**.</span></span>
6. <span data-ttu-id="849a4-115">Nel campo **Numero articolo** , digitare `M9211CI` (è necessario selezionare un articolo impostato per l'inventario spedizione).</span><span class="sxs-lookup"><span data-stu-id="849a4-115">In the **Item number** field, type `M9211CI` (you must select an item that is set up for consignment inventory).</span></span>
7. <span data-ttu-id="849a4-116">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="849a4-116">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="849a4-117">Nel campo **Data di consegna richiesta** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="849a4-117">In the **Requested delivery date** field, enter a date.</span></span> <span data-ttu-id="849a4-118">Le date di richiesta e conferma vengono utilizzate dal motore MRP per l'arrivo previsto delle merci.</span><span class="sxs-lookup"><span data-stu-id="849a4-118">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="849a4-119">Immettere una data nel campo **Data di consegna confermata**.</span><span class="sxs-lookup"><span data-stu-id="849a4-119">In the **Confirmed delivery date** field, enter a date.</span></span>
10. <span data-ttu-id="849a4-120">Espandere la sezione **Dettagli riga**.</span><span class="sxs-lookup"><span data-stu-id="849a4-120">Expand the **Line details** section.</span></span>
11. <span data-ttu-id="849a4-121">Selezionare la scheda **Dimensioni inventariali**.</span><span class="sxs-lookup"><span data-stu-id="849a4-121">Select the **Inventory dimensions** tab.</span></span>
12. <span data-ttu-id="849a4-122">Per visualizzare il proprietario nel campo **Proprietario dimensioni inventariali** , aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="849a4-122">To show the owner in the **Inventory dimensions owner** field, refresh the page.</span></span> <span data-ttu-id="849a4-123">Il fornitore US-104 è ora elencato come proprietario.</span><span class="sxs-lookup"><span data-stu-id="849a4-123">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="849a4-124">Controllare lo stato delle transazioni di inventario</span><span class="sxs-lookup"><span data-stu-id="849a4-124">Check the inventory transaction status</span></span>
1. <span data-ttu-id="849a4-125">Selezionare **Scorte**.</span><span class="sxs-lookup"><span data-stu-id="849a4-125">Select **Inventory**.</span></span>
2. <span data-ttu-id="849a4-126">Selezionare **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="849a4-126">Select **Transactions**.</span></span>
3. <span data-ttu-id="849a4-127">Nella riga desiderata, da notare che il campo **Entrata** è impostato su **Ordinato**.</span><span class="sxs-lookup"><span data-stu-id="849a4-127">In the desired row, notice that the **Receipt** field is set to **Ordered**.</span></span>  
4. <span data-ttu-id="849a4-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="849a4-128">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="849a4-129">Ricevi articoli</span><span class="sxs-lookup"><span data-stu-id="849a4-129">Receive items</span></span>
1. <span data-ttu-id="849a4-130">Selezionare **Entrata prodotti**.</span><span class="sxs-lookup"><span data-stu-id="849a4-130">Select **Product receipt**.</span></span>
2. <span data-ttu-id="849a4-131">Digitare un valore nel campo **Entrata prodotti esterna**.</span><span class="sxs-lookup"><span data-stu-id="849a4-131">In the **External product receipt** field, type a value.</span></span>
3. <span data-ttu-id="849a4-132">Nel campo **Quantità** , immettere un numero minore del numero riportato.</span><span class="sxs-lookup"><span data-stu-id="849a4-132">In the **Quantity** field, enter a number that's lower than the number that's shown there.</span></span> 
4. <span data-ttu-id="849a4-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="849a4-133">Select **OK**.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="849a4-134">Controllare le scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="849a4-134">Check the on-hand inventory</span></span>
1. <span data-ttu-id="849a4-135">Selezionare **Scorte**.</span><span class="sxs-lookup"><span data-stu-id="849a4-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="849a4-136">Seleziona **Disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="849a4-136">Select **On-hand**.</span></span>
3. <span data-ttu-id="849a4-137">Selezionare **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="849a4-137">Select **Overview**.</span></span> <span data-ttu-id="849a4-138">Gli articoli ricevuti come inventario di spedizione di proprietà del fornitore sono scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="849a4-138">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="849a4-139">La quantità rimanente nell'ordine di rifornimento spedizione è indicata nel campo **Ordinata in totale**.</span><span class="sxs-lookup"><span data-stu-id="849a4-139">The remaining quantity on the consignment replenishment order is shown in the **Ordered in total** field.</span></span>  
4. <span data-ttu-id="849a4-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="849a4-140">Close the page.</span></span>

