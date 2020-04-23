---
title: Impostare vettori di spedizione
description: In questo argomento viene descritto come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e6a29dce877a53d125c5a151da6cfbb13d46b29
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201596"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="fb400-103">Impostare vettori di spedizione</span><span class="sxs-lookup"><span data-stu-id="fb400-103">Set up shipping carriers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fb400-104">In questo argomento viene descritto come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto.</span><span class="sxs-lookup"><span data-stu-id="fb400-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="fb400-105">Un coordinatore dei trasporti può quindi assegnare un vettore di spedizione a un carico in entrata o in uscita.</span><span class="sxs-lookup"><span data-stu-id="fb400-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="fb400-106">Creare un nuovo vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="fb400-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="fb400-107">Andare a **Pannello di navigazione > Moduli > Gestione trasporto > Impostazioni > Vettori > Vettori spedizione**.</span><span class="sxs-lookup"><span data-stu-id="fb400-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="fb400-108">Nel riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fb400-108">Select **New** in the Action pane.</span></span>
3. <span data-ttu-id="fb400-109">Nel campo **Vettore spedizione** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb400-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="fb400-110">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="fb400-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="fb400-111">Nel campo **Modo**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="fb400-112">Inserire le informazioni generali per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="fb400-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="fb400-113">Attivare/disattivare l'espansione della sezione **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="fb400-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="fb400-114">Selezionare o deselezionare la casella di controllo **Attiva vettore di spedizione**.</span><span class="sxs-lookup"><span data-stu-id="fb400-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="fb400-115">Nel campo **Conto fornitore**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="fb400-116">Selezionare il conto fornitore a cui assegnare il vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="fb400-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="fb400-117">Nel campo **Tipo di pagamento trasporto** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="fb400-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="fb400-118">Selezionare **Manuale** per utilizzare la pagina Metodo di pagamento trasporto o selezionare **EDI** per aggiornare il metodo di pagamento utilizzando il formato EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="fb400-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="fb400-119">Selezionare o deselezionare la casella di controllo **Attiva valutazione vettore**.</span><span class="sxs-lookup"><span data-stu-id="fb400-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="fb400-120">Creare i servizi necessari per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="fb400-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="fb400-121">Attivare/disattivare l'espansione della sezione **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="fb400-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="fb400-122">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fb400-122">Select **New**.</span></span>
3. <span data-ttu-id="fb400-123">Nel campo **Servizio trasporto** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb400-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="fb400-124">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="fb400-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="fb400-125">Nel campo **Metodo di trasporto**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="fb400-126">Impostare l'indirizzo del vettore (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="fb400-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="fb400-127">Attiva/disattiva l'espansione della sezione **Indirizzi**.</span><span class="sxs-lookup"><span data-stu-id="fb400-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="fb400-128">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fb400-128">Select **New**.</span></span>
3. <span data-ttu-id="fb400-129">Digitare un valore nel campo **Nome o descrizione**.</span><span class="sxs-lookup"><span data-stu-id="fb400-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="fb400-130">Nel campo **Paese**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="fb400-131">Nel campo **Codice postale (CAP)**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="fb400-132">Digitare un valore nel campo **Via**.</span><span class="sxs-lookup"><span data-stu-id="fb400-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="fb400-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb400-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="fb400-134">Impostare il profilo di valutazione per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="fb400-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="fb400-135">Attivare/disattivare l'espansione della sezione **Profili valutazione**.</span><span class="sxs-lookup"><span data-stu-id="fb400-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="fb400-136">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fb400-136">Select **New**.</span></span>
3. <span data-ttu-id="fb400-137">Nel campo **Profilo valutazione** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb400-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="fb400-138">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="fb400-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="fb400-139">Nel campo **Sito**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="fb400-140">Nel campo **Magazzino**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="fb400-141">Nel campo **Motore tariffe**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="fb400-142">Selezionare il motore tariffe in base al contratto stipulato con il vettore.</span><span class="sxs-lookup"><span data-stu-id="fb400-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="fb400-143">Nel campo **Tariffa principale**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="fb400-144">Nel campo **Motore tempo di transito**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb400-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="fb400-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fb400-145">Select **Save**.</span></span>

