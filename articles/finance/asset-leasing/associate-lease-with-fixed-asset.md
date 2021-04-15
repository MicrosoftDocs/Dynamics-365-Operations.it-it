---
title: Associare cespiti a leasing
description: L'argomento spiega come associare un cespite esistente a un nuovo leasing.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0e2261755d98ee38564b4b864daf8e79551d1239
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814082"
---
# <a name="associate-fixed-assets-with-leases"></a><span data-ttu-id="c7bb4-103">Associare cespiti a leasing</span><span class="sxs-lookup"><span data-stu-id="c7bb4-103">Associate fixed assets with leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7bb4-104">L'argomento spiega come associare un cespite esistente a un nuovo leasing.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-104">The topic explains how to associate an existing fixed asset with a new lease.</span></span> <span data-ttu-id="c7bb4-105">Quando si associa un cespite a un leasing, il valore dell'Asset Right of use al riconoscimento iniziale sarà il costo di acquisizione del cespite.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-105">When you associate a fixed asset with a lease, the right-of-use (ROU) asset value at initial recognition will be the acquisition cost of the fixed asset.</span></span>

<span data-ttu-id="c7bb4-106">Prima di poter associare un cespite a un leasing, è necessario creare un record per il cespite in Cespiti.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-106">Before you can associate a fixed asset with a lease, you must create a record for the fixed asset in Fixed assets.</span></span> <span data-ttu-id="c7bb4-107">Quindi, nella pagina **Riepilogo leasing**, devi creare un leasing e collegare il cespite a tale leasing.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-107">Then, on the **Lease summary** page, you must create a lease and link the asset to that lease.</span></span>

1. <span data-ttu-id="c7bb4-108">Aggiungi un leasing seguendo i passaggi in [Aggiungere o copiare leasing](add-lease.md).</span><span class="sxs-lookup"><span data-stu-id="c7bb4-108">Add a lease by following the steps in [Add or copy leases](add-lease.md).</span></span> <span data-ttu-id="c7bb4-109">Nella pagina **Aggiungi leasing**, nel campi **Numero cespite** seleziona il cespite non è stato ancora acquisito.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-109">On the **Add lease** page, in the **Fixed asset number** field, select the asset that hasn't yet been acquired.</span></span>
2. <span data-ttu-id="c7bb4-110">Seleziona **Libri** e conferma lo scadenziario pagamenti.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-110">Select **Books**, and confirm the payment schedule.</span></span>
3. <span data-ttu-id="c7bb4-111">Seleziona **Riconoscimento iniziale**.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-111">Select **Initial recognition**.</span></span>
4. <span data-ttu-id="c7bb4-112">Seleziona **Giornale di registrazione leasing cespite**.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-112">Select **Asset leasing journal**.</span></span>

    <span data-ttu-id="c7bb4-113">La scrittura contabile di riconoscimento iniziale per il leasing addebita il cespite per l'importo che di solito viene addebitato al conto Asset ROU.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-113">The initial recognition journal entry for the lease debits the fixed asset for the amount that is usually debited to the ROU asset account.</span></span>

    <span data-ttu-id="c7bb4-114">Ora puoi visualizzare il tipo di transazione e registrare il cespite.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-114">You can now view the transaction type and book for the fixed asset.</span></span>

5. <span data-ttu-id="c7bb4-115">Seleziona **Dettagli gironale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-115">Select **Journal details**.</span></span>
6. <span data-ttu-id="c7bb4-116">Seleziona **Righe** per visualizzare le singole righe per la scrittura contabile.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-116">Select **Lines** to view the individual lines for the journal entry.</span></span>
7. <span data-ttu-id="c7bb4-117">Seleziona la riga del giornale di registrazione che contiene il cespite, quindi seleziona la scheda **Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-117">Select the journal line that contains the asset, and then select the **Fixed Assets** tab.</span></span>

    <span data-ttu-id="c7bb4-118">La scheda **Cespiti** mostra il tipo di transazione e il libro.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-118">The **Fixed assets** tab shows the transaction type and the book.</span></span> <span data-ttu-id="c7bb4-119">Per impostazione predefinita, il campo **Tipo di transazione** è impostato su **Acquisizione** e il campo **Libro** è impostato sul libro corrente per il cespite.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-119">By default, the **Transaction type** field is set to **Acquisition**, and the **Book** field is set to the current book for the fixed asset.</span></span>

<span data-ttu-id="c7bb4-120">Dopo aver registrato la scrittura contabile di riconoscimento iniziale, la transazione viene visualizzata come transazione di acquisizione per il cespite.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-120">After you post the initial recognition journal entry, the transaction appears as an acquisition transaction for the fixed asset.</span></span> <span data-ttu-id="c7bb4-121">Per visualizzare la tabella delle transazioni, vai a **Cespiti \> Cespiti \> Immobilizzazioni**, seleziona il cespite appropriato, quindi seleziona **Valutazioni**.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-121">To view the transaction table, go to **Fixed assets \> Fixed assets \> Fixed assets**, select the appropriate asset, and then select **Valuations**.</span></span> <span data-ttu-id="c7bb4-122">Dovrebbe essere visibile che la scrittura contabile di riconoscimento iniziale ha creato una transazione di acquisizione per il cespite specificato.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-122">You should see that the initial recognition journal entry has created an acquisition transaction for the specified fixed asset.</span></span>

<span data-ttu-id="c7bb4-123">Il cespite può ora essere ammortizzato utilizzando la funzionalità di ammortamento standard in Cespiti.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-123">The fixed asset can now be depreciated by using the standard depreciation functionality in Fixed assets.</span></span> <span data-ttu-id="c7bb4-124">Per ulteriori informazioni sull'ammortamento, vedi [Metodi e convenzioni di ammortamento](../fixed-assets/depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="c7bb4-124">For more information about depreciation, see [Depreciation methods and conventions](../fixed-assets/depreciation-methods-conventions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7bb4-125">Se associ un cespite a un leasing, i pulsanti **Ammortamento dei cespiti** e **Riduzione del valore del leasing** sono disabilitati in Leasing cespite.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-125">If you associate a fixed asset with a lease, the **Asset depreciation** and **Lease impairment** buttons are disabled in Asset leasing.</span></span> <span data-ttu-id="c7bb4-126">Puoi visualizzare l'ammortamento dei cespiti e le transazioni di riduzione del leasing da Cespiti.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-126">You can view asset depreciation and lease impairment transactions from Fixed assets.</span></span> <span data-ttu-id="c7bb4-127">Anche il pulsante **Transazioni cespiti** che apre un modulo di richiesta è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-127">The **Asset transactions** button, which opens an inquiry form is also disabled.</span></span> <span data-ttu-id="c7bb4-128">Puoi anche aprire il modulo di richiesta **Transazioni cespiti** in Cespiti.</span><span class="sxs-lookup"><span data-stu-id="c7bb4-128">You can also open the **Asset transactions** inquiry form in Fixed assets.</span></span>  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]