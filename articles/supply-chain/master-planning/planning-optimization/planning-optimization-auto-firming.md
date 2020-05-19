---
title: Stabilizzazione automatica con l'ottimizzazione di pianificazione
description: In questo argomento viene illustrato come utilizzare la stabilizzazione automatica con l'ottimizzazione di pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 81c26b8a99f86d663d91ac4f549987262c0541ad
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323533"
---
# <a name="auto-firming-with-planning-optimization"></a><span data-ttu-id="bdf6a-103">Stabilizzazione automatica con l'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="bdf6a-103">Auto-firming with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bdf6a-104">La stabilizzazione automatica consente di stabilizzare ovvero rilasciare gli ordini pianificati nel processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="bdf6a-105">Quando gli ordini pianificati vengono stabilizzati, vengono trasformati negli ordini fornitore, di trasferimento o di produzione effettivi.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="bdf6a-106">Quando l'ottimizzazione di progettazione viene utilizzata, gli ordini pianificati vengono stabilizzati durante l'esecuzione di una pianificazione generale quando la data dell'ordine ovvero la data di inizio rientra nell'intervallo temporale specificato per la stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf6a-107">La stabilizzazione automatica di un ordine fornitore pianificato può avvenire solo se l'articolo è associato a un fornitore.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>

## <a name="turn-on-auto-firming"></a><span data-ttu-id="bdf6a-108">Attivare la stabilizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="bdf6a-108">Turn on auto-firming</span></span>

<span data-ttu-id="bdf6a-109">Per attivare la stabilizzazione automatica, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-109">To turn on auto-firming, follow these steps.</span></span>

1. <span data-ttu-id="bdf6a-110">Nell'area di lavoro **Gestione funzionalità**, scheda **Nuovo**, selezionare **Stabilizzazione automatica per l'ottimizzazione di pianificazione** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-110">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="bdf6a-111">Se la funzionalità non è presente nella scheda **Nuovo**, considerare le schede **Tutto** e **Non abilitato**.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="bdf6a-112">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-112">Select **Enable now**.</span></span> <span data-ttu-id="bdf6a-113">In alternativa, selezionare **Programmazione** e quindi selezionare l'ora in cui si desidera che la funzionalità sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="bdf6a-114">Impostare l'intervallo temporale della stabilizzazione</span><span class="sxs-lookup"><span data-stu-id="bdf6a-114">Set up the firming time fence</span></span>

<span data-ttu-id="bdf6a-115">L'intervallo temporale di stabilizzazione viene calcolato in avanti a partire dalla data di esecuzione della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-115">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="bdf6a-116">È definito dal numero di giorni immessi.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-116">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="bdf6a-117">È possibile controllare l'intervallo temporale nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="bdf6a-117">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="bdf6a-118">Per definire l'intervallo temporale predefinito per la stabilizzazione di un gruppo di copertura, andare a **Pianificazione generale** \> **Impostazione** \> **Copertura** \> **Gruppi di copertura** e selezionare un gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-118">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="bdf6a-119">Quindi, nella Scheda dettaglio **Altro**, nel campo **Intervallo temporale di stabilizzazione automatica (giorni)**, immettere il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-119">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="bdf6a-120">Per sovrascrivere l'intervallo temporale per la stabilizzazione definito per il gruppo di copertura per un articolo specifico, andare a **Gestione informazioni sul prodotto** \> **Prodotti rilasciati**, quindi nel riquadro azioni **Piano** selezionare **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-120">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the action pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="bdf6a-121">Nella scheda **Generale**, selezionare **Ignora intervalli temporali** e nel campo **Intervallo temporale di stabilizzazione automatico (giorni)**, immettere il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-121">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="bdf6a-122">Per sovrascrivere l'intervallo temporale per la stabilizzazione definito per il gruppo di copertura e la copertura articoli per un piano generale specifico, andare a **Pianificazione generale** \> **Impostazione** \> **Piani generali** e selezionare un piano generale.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-122">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="bdf6a-123">Quindi, nella Scheda dettaglio **Intervallo temporale in giorni**, impostare **Blocca** su **Sì** e immettere il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-123">Then, on the **Time fence in days** FastTab, set **Freeze** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="bdf6a-124">Se la stabilizzazione automatica è attivata per l'esecuzione di una pianificazione generale che utilizza l'ottimizzazione di pianificazione, il processo di stabilizzazione automatica viene eseguito in base all'impostazione di stabilizzazione automatica.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-124">If auto-firming is turned on for a master planning run that uses Planning Optimization, the auto-firming process is done according to the auto-firming setup.</span></span> <span data-ttu-id="bdf6a-125">Se la stabilizzazione automatica non è attivata o se la pianificazione viene avviata dalla pagina **Fabbisogno netto**, il processo di stabilizzazione automatica verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-125">If auto-firming isn't turned on, or if planning is started from the **Net requirements** page, the auto-firming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="bdf6a-126">Ottimizzazione di pianificazione rispetto al motore di pianificazione integrato di Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bdf6a-126">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="bdf6a-127">Sia l'ottimizzazione di pianificazione che il motore di pianificazione integrato in Microsoft Dynamics 365 Supply Chain Management possono essere utilizzati per stabilizzare automaticamente gli ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-127">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to auto-firm planned orders.</span></span> <span data-ttu-id="bdf6a-128">Tuttavia, esistono delle differenze importanti.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-128">However, there are some important differences.</span></span> <span data-ttu-id="bdf6a-129">Ad esempio, mentre l'ottimizzazione di pianificazione utilizza la data dell'ordine (ovvero la data di inizio) per determinare quali ordini pianificati devono essere consolidati, il motore di pianificazione integrato di Supply Chain Management utilizza la data del fabbisogno (ovvero la data di fine).</span><span class="sxs-lookup"><span data-stu-id="bdf6a-129">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="bdf6a-130">Di seguito è riportato un riepilogo delle differenze.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-130">Here is a summary of the differences.</span></span>

<span data-ttu-id="bdf6a-131">**Ottimizzazione pianificazione**</span><span class="sxs-lookup"><span data-stu-id="bdf6a-131">**Planning Optimization**</span></span>

- <span data-ttu-id="bdf6a-132">La stabilizzazione automatica si basa sulla data dell'ordine (data di inizio).</span><span class="sxs-lookup"><span data-stu-id="bdf6a-132">Auto-firming is based on the order date (start date).</span></span>
- <span data-ttu-id="bdf6a-133">Poiché la data dell'ordine (data di inizio) attiva la stabilizzazione, non è necessario considerare i lead time come parte dell'intervallo temporale per la stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-133">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="bdf6a-134">Se si desidera stabilizzare tutti gli ordini che devono iniziare nella settimana corrente, l'intervallo temporale per la stabilizzazione deve essere di una settimana.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-134">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="bdf6a-135">**Motore di pianificazione integrato di Supply Chain Management**</span><span class="sxs-lookup"><span data-stu-id="bdf6a-135">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="bdf6a-136">La stabilizzazione automatica si basa sulla data del fabbisogno (data di fine).</span><span class="sxs-lookup"><span data-stu-id="bdf6a-136">Auto-firming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="bdf6a-137">Per garantire che gli ordini vengano stabilizzati in tempo utile, l'intervallo temporale per la stabilizzazione deve essere più lungo del lead time.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-137">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="bdf6a-138">Se si desidera stabilizzare tutti gli ordini che devono iniziare nella settimana corrente, l'intervallo temporale per la stabilizzazione deve essere il lead time più una settimana.</span><span class="sxs-lookup"><span data-stu-id="bdf6a-138">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>
