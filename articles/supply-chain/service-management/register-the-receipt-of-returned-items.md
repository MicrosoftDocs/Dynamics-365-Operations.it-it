---
title: Registrare il ricevimento di resi
description: È possibile registrare il ricevimento di resi utilizzando il modulo Panoramica arrivi o il modulo Registrazione.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42ca1d4d2d9b45d79cf479833f83e498e3b73540
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430891"
---
# <a name="register-the-receipt-of-returned-items"></a><span data-ttu-id="94acc-103">Registrare il ricevimento di resi</span><span class="sxs-lookup"><span data-stu-id="94acc-103">Register the receipt of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="94acc-104">Sono disponibili due metodi per registrare il ricevimento di resi.</span><span class="sxs-lookup"><span data-stu-id="94acc-104">There are two methods for registering the receipt of returned items.</span></span> <span data-ttu-id="94acc-105">Il primo metodo è un processo di ricevimento in magazzino che utilizza il modulo **Panoramica arrivi**.</span><span class="sxs-lookup"><span data-stu-id="94acc-105">The first method is a warehouse receiving process that uses the **Arrival overview** form.</span></span> <span data-ttu-id="94acc-106">Il secondo utilizza il modulo **Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="94acc-106">The second uses the **Registration** form.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a><span data-ttu-id="94acc-107">Registrare il ricevimento di resi nel modulo Panoramica arrivi</span><span class="sxs-lookup"><span data-stu-id="94acc-107">Register the receipt of returned items in the Arrival overview form</span></span>

<span data-ttu-id="94acc-108">È possibile utilizzare il modulo **Panoramica arrivi** per identificare la spedizione di un reso in base al relativo numero autorizzazione reso (NAR).</span><span class="sxs-lookup"><span data-stu-id="94acc-108">You can use the **Arrival overview** form to identify a return shipment by its Return Material Authorization (RMA) number.</span></span> <span data-ttu-id="94acc-109">Se un nome di giornale di registrazione viene definito nella scheda **Impostazione** e le righe del giornale di registrazione che corrispondono alle righe selezionate nel modulo **Panoramica arrivi** esistono, una nuova intestazione giornale di registrazione viene creata quando si fa clic su **Inizia arrivo**.</span><span class="sxs-lookup"><span data-stu-id="94acc-109">If a journal name is defined on the **Setup** tab, and journal lines that correspond to the lines selected on the **Arrival overview** form exist, a new journal header is created when you click **Start arrival**.</span></span>

1.  <span data-ttu-id="94acc-110">Fare clic su **Gestione articoli** \> **Periodico** \> **Panoramica arrivi**.</span><span class="sxs-lookup"><span data-stu-id="94acc-110">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="94acc-111">Nel campo **Nome impostazioni** selezionare **Ordine di reso** e fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="94acc-111">In the **Setup name** field, select **Return order**, and then click **Update**.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="94acc-112">È possibile utilizzare i campi <STRONG>Intervallo</STRONG> per limitare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="94acc-112">You can use the <STRONG>Range</STRONG> fields to narrow the search results.</span></span> <span data-ttu-id="94acc-113">Per ottenere un risultato preciso è possibile digitare o selezionare il codice NAR nel campo <STRONG>Codice NAR</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="94acc-113">You can type or select the RMA number in the <STRONG>RMA number</STRONG> field for an exact result.</span></span> <span data-ttu-id="94acc-114">Per definire e salvare un set di filtri che limiteranno gli arrivi in entrata visualizzati, fare clic sulla scheda <STRONG>Impostazione</STRONG>. I filtri disponibili includono tipi, magazzini e banchine.</span><span class="sxs-lookup"><span data-stu-id="94acc-114">To define and save a set of filters that will restrict which incoming arrivals are displayed, click the <STRONG>Setup</STRONG> tab. The available filters include types, warehouses, and docks.</span></span></P>

    

    > [!WARNING]
    > <P><span data-ttu-id="94acc-115">Gli ordini di reso non possono essere combinati con altri tipi di arrivi nel modulo <STRONG>Panoramica arrivi</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="94acc-115">Return orders cannot be mixed with other arrival types in the <STRONG>Arrival overview</STRONG> form.</span></span> <span data-ttu-id="94acc-116">Di conseguenza, il riferimento verrà sempre un ordine cliente, ma nessun ID di ordine cliente verrà specificato nell'intestazione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="94acc-116">Therefore, the reference will always be sales order, but no sales order ID will be specified on the journal header.</span></span></P>



3.  <span data-ttu-id="94acc-117">Nella griglia **Ricevute** individuare la riga corrispondente al reso, quindi selezionare la casella di controllo nella colonna **Selezionato per arrivo**.</span><span class="sxs-lookup"><span data-stu-id="94acc-117">In the **Receipts** grid, locate the line that matches the item being returned, and then select the check box in the **Select for arrival** column.</span></span>

4.  <span data-ttu-id="94acc-118">Per escludere determinate righe dal ricevimento dei resi, ad esempio gli articoli dell'ordine originario non inclusi nella spedizione reso, deselezionare le caselle associate **Selezionato per arrivi** della tabella **Righe** nella parte inferiore del modulo.</span><span class="sxs-lookup"><span data-stu-id="94acc-118">To exclude certain lines from the return receipt, such as items from the original order that were not included in the return shipment, clear the associated **Select for arrival** check boxes in the **Lines** table in the lower part of the form.</span></span>

5.  <span data-ttu-id="94acc-119">Fare clic sul pulsante **Inizia arrivo** per creare un giornale di registrazione arrivi.</span><span class="sxs-lookup"><span data-stu-id="94acc-119">Click the **Start arrival** button to create an arrival journal.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="94acc-120">È possibile selezionare più ordini di reso e includerli tutti in un unico processo di arrivo.</span><span class="sxs-lookup"><span data-stu-id="94acc-120">You can select multiple return orders and include them all in a single arrival process.</span></span> <span data-ttu-id="94acc-121">Ciascuna riga dell'ordine di reso verrà copiata in una riga corrispondente del giornale di registrazione arrivi articoli.</span><span class="sxs-lookup"><span data-stu-id="94acc-121">Each return order line will be copied into a corresponding item arrival journal line.</span></span></P>

    

    > [!NOTE]
    > <P><span data-ttu-id="94acc-122">È inoltre possibile creare manualmente un giornale di registrazione arrivi tramite il modulo <STRONG>Arrivo articoli</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="94acc-122">You can also manually create an arrival journal by using the <STRONG>Item arrival</STRONG> form.</span></span> 



6.  <span data-ttu-id="94acc-123">Fare clic su **Gestione inventario** \> **Giornali di registrazione** \> **Arrivo articoli** \> **Arrivo articoli**.</span><span class="sxs-lookup"><span data-stu-id="94acc-123">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>

7.  <span data-ttu-id="94acc-124">Selezionare il giornale di registrazione arrivi appena creato e fare clic su **Righe** per aprire il modulo **Righe giornale di registrazione, ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="94acc-124">Select the arrival journal that you just created and then click **Lines** to open the **Journal lines, locations** form.</span></span>

8.  <span data-ttu-id="94acc-125">Nella scheda **Generale**, rettificare il numero nel campo **Quantità**, se necessario, quindi assegnare un codice smaltimento nel campo **Codice smaltimento**.</span><span class="sxs-lookup"><span data-stu-id="94acc-125">On the **General** tab, adjust the number in the **Quantity** field, if it is required, and then assign a disposition code in the **Disposition code** field.</span></span>
    
    <span data-ttu-id="94acc-126">In alternativa, è possibile selezionare la casella di controllo **Gestione quarantena** per inviare i resi tramite un processo di ispezione nel contesto di un ordine di quarantena.</span><span class="sxs-lookup"><span data-stu-id="94acc-126">Alternatively, you can select the **Quarantine management** check box to have the returned items sent through an inspection process in the context of a quarantine order.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="94acc-127">Se si inviano i resi tramite quarantena, non è possibile specificare un codice smaltimento.</span><span class="sxs-lookup"><span data-stu-id="94acc-127">If you send the returned items through quarantine, you cannot specify a disposition code.</span></span></P>



9.  <span data-ttu-id="94acc-128">Fare clic sul pulsante **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="94acc-128">Click the **Validate** button.</span></span>

10. <span data-ttu-id="94acc-129">Se dal processo di convalida non risulta alcun errore, fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="94acc-129">If there are no errors in the validation process, click **Post**.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a><span data-ttu-id="94acc-130">Registrare il ricevimento di resi nel modulo Registrazione</span><span class="sxs-lookup"><span data-stu-id="94acc-130">Register the receipt of returned items in the Registration form</span></span>

<span data-ttu-id="94acc-131">In alternativa all'uso del modulo **Panoramica arrivi**, è possibile utilizzare il modulo **Registrazione** per registrare l'arrivo dei resi.</span><span class="sxs-lookup"><span data-stu-id="94acc-131">As an alternative to using the **Arrival overview** form, you can use the **Registration** form to register the arrival of returned items.</span></span>

1.  <span data-ttu-id="94acc-132">Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini di reso** \> **Tutti gli ordini di reso**.</span><span class="sxs-lookup"><span data-stu-id="94acc-132">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span> <span data-ttu-id="94acc-133">Creare un nuovo ordine di reso o aprire l'ordine di reso dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="94acc-133">Create a new return order or open the return order from the list.</span></span> <span data-ttu-id="94acc-134">Nella Scheda dettaglio **Righe** selezionare la riga ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="94acc-134">On the **Lines** FastTab, select the return order line.</span></span> <span data-ttu-id="94acc-135">Fare clic su **Aggiorna riga**, quindi su **Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="94acc-135">Click **Update line**, and then click **Registration**.</span></span>

2.  <span data-ttu-id="94acc-136">Assegnare un codice smaltimento nel campo **Codice smaltimento**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94acc-136">Assign a disposition code in the **Disposition code** field, and then click **OK**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="94acc-137">Non è possibile inviare l'articolo per l'ispezione come ordine di quarantena utilizzando il modulo <STRONG>Registrazione</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="94acc-137">It is not possible to send the item for inspection as a quarantine order using the <STRONG>Registration</STRONG> form.</span></span></P>



3.  <span data-ttu-id="94acc-138">Nella griglia **Transazioni**, selezionare la transazione da registrare.</span><span class="sxs-lookup"><span data-stu-id="94acc-138">In the **Transactions** grid, select the transaction to be registered.</span></span>

4.  <span data-ttu-id="94acc-139">Nella griglia **Registra ora**, scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94acc-139">In the **Register now** grid, click **Add**.</span></span> <span data-ttu-id="94acc-140">Ripetere i due passaggi precedenti finché tutti i resi non compaiano nella griglia **Registra ora**.</span><span class="sxs-lookup"><span data-stu-id="94acc-140">Repeat the previous two steps until all of the returned items appear in the **Register now** grid.</span></span>

5.  <span data-ttu-id="94acc-141">Fare clic su **Registra tutto**.</span><span class="sxs-lookup"><span data-stu-id="94acc-141">Click **Post all**.</span></span>

## <a name="see-also"></a><span data-ttu-id="94acc-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94acc-142">See also</span></span>

<span data-ttu-id="94acc-143">[Panoramica arrivi (modulo)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="94acc-143">[Arrival overview (form)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span></span>

  


