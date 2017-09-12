--- 
title: "Impostare i documenti di trasferimento per il movimento di merci all'interno di una società"
description: "In questa procedura viene illustrato come creare documenti di trasferimento per il movimento di merci in una società."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2f10f627f33108b8750a1d71d24a99763178e2ef
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a><span data-ttu-id="fc2c8-103">Impostare i documenti di trasferimento per il movimento di merci all'interno di una società</span><span class="sxs-lookup"><span data-stu-id="fc2c8-103">Set up the transfer documents for goods movement inside a company</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc2c8-104">In questa procedura viene illustrato come creare documenti di trasferimento per il movimento di merci in una società.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="fc2c8-105">Questa procedura è disponibile solo per le persone giuridiche con un indirizzo principale in Lituania.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="fc2c8-106">La procedura è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Lituania.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="fc2c8-107">Prima di poter eseguire la procedura, è necessario completare la procedura 'Impostare documenti di trasferimento per il movimento di merci in una società'.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="fc2c8-108">Questa procedura è destinata ai contabili di inventario.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="fc2c8-109">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="fc2c8-110">Creare un ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="fc2c8-110">Create a transfer order</span></span>
1. <span data-ttu-id="fc2c8-111">Andare a Gestione articoli > Ordini in entrata > Ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="fc2c8-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-112">Click New.</span></span>
3. <span data-ttu-id="fc2c8-113">Nel campo Magazzino origine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="fc2c8-114">Nel campo Magazzino destinazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="fc2c8-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-115">Click Add.</span></span>
6. <span data-ttu-id="fc2c8-116">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="fc2c8-117">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="fc2c8-118">Immettere i dettagli di trasporto per l'ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="fc2c8-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="fc2c8-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-119">Click Save.</span></span>
2. <span data-ttu-id="fc2c8-120">Nel riquadro azioni fare clic su Spedisci.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="fc2c8-121">Fare clic su Dettagli trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-121">Click Transportation details.</span></span>
4. <span data-ttu-id="fc2c8-122">Selezionare Sì nel campo Stampa dettagli di trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="fc2c8-123">Nel campo Beni emessi da immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="fc2c8-124">Nel campo Collo digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="fc2c8-125">Nel campo Livello di rischio del carico, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="fc2c8-126">Nel campo Vettore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="fc2c8-127">Nel campo Modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="fc2c8-128">Nel campo Numero di registrazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="fc2c8-129">Nel campo Numero rimorchio digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="fc2c8-130">Nel campo Conducente immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="fc2c8-131">Digitare un valore nel campo Nome conducente.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="fc2c8-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-132">Click Save.</span></span>
15. <span data-ttu-id="fc2c8-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="fc2c8-134">Visualizzare il documento di trasporto per l'ordine di trasferimento non registrato</span><span class="sxs-lookup"><span data-stu-id="fc2c8-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="fc2c8-135">Fare clic su Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-135">Click Packing slip.</span></span>
2. <span data-ttu-id="fc2c8-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-136">Click OK.</span></span>
3. <span data-ttu-id="fc2c8-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="fc2c8-138">Visualizzare il documento di trasporto per l'ordine di trasferimento registrato</span><span class="sxs-lookup"><span data-stu-id="fc2c8-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="fc2c8-139">Nel riquadro azioni fare clic su Ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="fc2c8-140">Nel riquadro azioni fare clic su Spedisci.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="fc2c8-141">Fare clic su Ordine di trasferimento spedizione.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="fc2c8-142">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-142">Click the General tab.</span></span>
5. <span data-ttu-id="fc2c8-143">Nel campo Aggiorna selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="fc2c8-144">Fare clic sulla scheda Panoramica.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="fc2c8-145">Digitare un valore nel campo Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="fc2c8-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-146">Click OK.</span></span>
9. <span data-ttu-id="fc2c8-147">Nel riquadro azioni fare clic su Spedisci.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="fc2c8-148">Fare clic su Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-148">Click Packing slip.</span></span>
11. <span data-ttu-id="fc2c8-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc2c8-149">Click OK.</span></span>

