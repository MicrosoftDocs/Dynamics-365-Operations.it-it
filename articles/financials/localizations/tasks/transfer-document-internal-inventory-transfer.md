---
title: Generare un documento di trasferimento per un trasferimento scorte interno
description: In questa procedura viene illustrato come creare documenti di trasferimento per il movimento di merci in una società.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4da59781f3357a6713eebba03d87c5127b8cd3b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848626"
---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a><span data-ttu-id="c383d-103">Generare un documento di trasferimento per un trasferimento scorte interno</span><span class="sxs-lookup"><span data-stu-id="c383d-103">Generate a transfer document for an internal inventory transfer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c383d-104">In questa procedura viene illustrato come creare documenti di trasferimento per il movimento di merci in una società.</span><span class="sxs-lookup"><span data-stu-id="c383d-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="c383d-105">Questa procedura è disponibile solo per le persone giuridiche con un indirizzo principale in Lituania.</span><span class="sxs-lookup"><span data-stu-id="c383d-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="c383d-106">La procedura è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Lituania.</span><span class="sxs-lookup"><span data-stu-id="c383d-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="c383d-107">Prima di poter eseguire la procedura, è necessario completare la procedura 'Impostare documenti di trasferimento per il movimento di merci in una società'.</span><span class="sxs-lookup"><span data-stu-id="c383d-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="c383d-108">Questa procedura è destinata ai contabili di inventario.</span><span class="sxs-lookup"><span data-stu-id="c383d-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="c383d-109">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="c383d-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="c383d-110">Creare un ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="c383d-110">Create a transfer order</span></span>
1. <span data-ttu-id="c383d-111">Andare a Gestione articoli > Ordini in entrata > Ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="c383d-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="c383d-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c383d-112">Click New.</span></span>
3. <span data-ttu-id="c383d-113">Nel campo Magazzino origine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="c383d-114">Nel campo Magazzino destinazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="c383d-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c383d-115">Click Add.</span></span>
6. <span data-ttu-id="c383d-116">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c383d-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="c383d-117">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="c383d-118">Immettere i dettagli di trasporto per l'ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="c383d-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="c383d-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c383d-119">Click Save.</span></span>
2. <span data-ttu-id="c383d-120">Nel riquadro azioni fare clic su Spedisci.</span><span class="sxs-lookup"><span data-stu-id="c383d-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="c383d-121">Fare clic su Dettagli trasporto.</span><span class="sxs-lookup"><span data-stu-id="c383d-121">Click Transportation details.</span></span>
4. <span data-ttu-id="c383d-122">Selezionare Sì nel campo Stampa dettagli di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c383d-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="c383d-123">Nel campo Beni emessi da immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="c383d-124">Nel campo Collo digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="c383d-125">Nel campo Livello di rischio del carico, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="c383d-126">Nel campo Vettore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="c383d-127">Nel campo Modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="c383d-128">Nel campo Numero di registrazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="c383d-129">Nel campo Numero rimorchio digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="c383d-130">Nel campo Conducente immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c383d-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="c383d-131">Digitare un valore nel campo Nome conducente.</span><span class="sxs-lookup"><span data-stu-id="c383d-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="c383d-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c383d-132">Click Save.</span></span>
15. <span data-ttu-id="c383d-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c383d-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="c383d-134">Visualizzare il documento di trasporto per l'ordine di trasferimento non registrato</span><span class="sxs-lookup"><span data-stu-id="c383d-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="c383d-135">Fare clic su Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c383d-135">Click Packing slip.</span></span>
2. <span data-ttu-id="c383d-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c383d-136">Click OK.</span></span>
3. <span data-ttu-id="c383d-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c383d-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="c383d-138">Visualizzare il documento di trasporto per l'ordine di trasferimento registrato</span><span class="sxs-lookup"><span data-stu-id="c383d-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="c383d-139">Nel riquadro azioni fare clic su Ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="c383d-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="c383d-140">Nel riquadro azioni fare clic su Spedisci.</span><span class="sxs-lookup"><span data-stu-id="c383d-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="c383d-141">Fare clic su Ordine di trasferimento spedizione.</span><span class="sxs-lookup"><span data-stu-id="c383d-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="c383d-142">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="c383d-142">Click the General tab.</span></span>
5. <span data-ttu-id="c383d-143">Nel campo Aggiorna selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="c383d-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="c383d-144">Fare clic sulla scheda Panoramica.</span><span class="sxs-lookup"><span data-stu-id="c383d-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="c383d-145">Digitare un valore nel campo Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c383d-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="c383d-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c383d-146">Click OK.</span></span>
9. <span data-ttu-id="c383d-147">Nel riquadro azioni fare clic su Spedisci.</span><span class="sxs-lookup"><span data-stu-id="c383d-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="c383d-148">Fare clic su Documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c383d-148">Click Packing slip.</span></span>
11. <span data-ttu-id="c383d-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c383d-149">Click OK.</span></span>

