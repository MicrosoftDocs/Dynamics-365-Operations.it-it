---
title: Spostamento della sequenza dei costi di fallback medi
description: Questo argomento fornisce informazioni sulle sequenze dei costi di fallback per lo spostamento di calcoli medi in Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 541b7ecca5c1c36999f573d6d0f2dc0c9e901631
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967585"
---
# <a name="moving-average-fallback-cost-sequence"></a><span data-ttu-id="8cafd-103">Spostamento della sequenza dei costi di fallback medi</span><span class="sxs-lookup"><span data-stu-id="8cafd-103">Moving average fallback cost sequence</span></span>

<span data-ttu-id="8cafd-104">Una modalità per calcolare il costo dell'inventario è costituito dall'utilizzo di una _media mobile_.</span><span class="sxs-lookup"><span data-stu-id="8cafd-104">One way that you can calculate the cost of your inventory is by using a _moving average_.</span></span> <span data-ttu-id="8cafd-105">Ad ogni articolo di inventario possono essere associati fino a tre valori di costo:</span><span class="sxs-lookup"><span data-stu-id="8cafd-105">Up to three cost values can be associated with each inventory item:</span></span>

- <span data-ttu-id="8cafd-106">**Ultimo rilascio** - L'ultimo costo di transazione viene assegnato prima che l'inventario diventi negativo</span><span class="sxs-lookup"><span data-stu-id="8cafd-106">**Last issue** – The last issue cost that was assigned before inventory went negative</span></span>
- <span data-ttu-id="8cafd-107">**Costo attivo** - È l'ultimo costo attivato in una versione di determinazione dei costi</span><span class="sxs-lookup"><span data-stu-id="8cafd-107">**Active cost** – The latest cost that was activated in a costing version</span></span>
- <span data-ttu-id="8cafd-108">**Prezzo dell'articolo** - È Il costo specificato per il prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="8cafd-108">**Item price** – The cost that is specified for the released product</span></span>

<span data-ttu-id="8cafd-109">Per determinare quale di questi valori di costo deve essere utilizzato nei calcoli della media mobile, il sistema utilizza la _sequenza dei costi di fallback_ per stabilire l'ordine di preferenza per i valori.</span><span class="sxs-lookup"><span data-stu-id="8cafd-109">To determine which of these cost values should be used in moving average calculations, the system uses a _fallback cost sequence_ to establish the order of preference for the values.</span></span> <span data-ttu-id="8cafd-110">Se il valore di costo preferito non è disponibile, il sistema utilizza il valore preferito successivo e così via.</span><span class="sxs-lookup"><span data-stu-id="8cafd-110">If the preferred cost value isn't available, the system uses the next-preferred value, and so on.</span></span>

<span data-ttu-id="8cafd-111">Nelle versioni precedenti di Microsoft Dynamics 365 Supply Chain Management, il sistema utilizzava una sequenza di costi di fallback fissa (_Ultimo rilascio - Costo attivo - Prezzo articolo_).</span><span class="sxs-lookup"><span data-stu-id="8cafd-111">In previous versions of Microsoft Dynamics 365 Supply Chain Management, the system used a fixed fallback cost sequence (_Last issue – Active cost – Item price_).</span></span> <span data-ttu-id="8cafd-112">Nella versione 10.0.11, questa sequenza è ancora la sequenza predefinita.</span><span class="sxs-lookup"><span data-stu-id="8cafd-112">In version 10.0.11, this sequence is still the default sequence.</span></span> <span data-ttu-id="8cafd-113">Tuttavia, è anche possibile attivare una funzione che consente di selezionare tra tre sequenze di costi di fallback disponibili.</span><span class="sxs-lookup"><span data-stu-id="8cafd-113">However, you can also turn on a feature that lets you select among three available fallback cost sequences.</span></span> <span data-ttu-id="8cafd-114">Questa funzione può essere particolarmente utile per le organizzazioni che utilizzano regolarmente valori di inventario negativi.</span><span class="sxs-lookup"><span data-stu-id="8cafd-114">This feature can be especially useful for organizations that regularly use negative inventory values.</span></span>

<span data-ttu-id="8cafd-115">Per rendere disponibile il selettore per la sequenza dei costi di fallback, è necessario usare [Gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare la funzione denominata _Spostamento della sequenza dei costi di fallback medi_.</span><span class="sxs-lookup"><span data-stu-id="8cafd-115">To make the selector for the fallback cost sequence available, you (or an admin) must use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named _Moving average fallback cost sequence_.</span></span>

<span data-ttu-id="8cafd-116">Per selezionare la sequenza dei costi di fallback per i calcoli della media mobile, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="8cafd-116">To select the fallback cost sequence for moving average calculations, follow these steps.</span></span>

1. <span data-ttu-id="8cafd-117">Aprire la pagina **Parametri**:</span><span class="sxs-lookup"><span data-stu-id="8cafd-117">Open the **Parameters** page.</span></span>
2. <span data-ttu-id="8cafd-118">Nella scheda **Contabilità di magazzino**, nella sezione, **Media mobile** impostare la **Sequenza di costi di fallback** su uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8cafd-118">On the **Inventory accounting** tab, in the **Moving average** section, set the **Fallback cost sequence** field to one of the following values:</span></span>

    - <span data-ttu-id="8cafd-119">**Ultimo rilascio - Costo attivo - Prezzo articolo** - Questa è la sequenza predefinita.</span><span class="sxs-lookup"><span data-stu-id="8cafd-119">**Last issue – Active cost – Item price** – This sequence is the default sequence.</span></span> <span data-ttu-id="8cafd-120">È la stessa sequenza usata se la funzione _Spostamento della sequenza dei costi di fallback medi_ non è attivata.</span><span class="sxs-lookup"><span data-stu-id="8cafd-120">It's the same sequence that is used if the _Moving average fallback cost sequence_ feature isn't turned on.</span></span>
    - <span data-ttu-id="8cafd-121">**Costo attivo - Ultimo rilascio**</span><span class="sxs-lookup"><span data-stu-id="8cafd-121">**Active cost – Last issue**</span></span>
    - <span data-ttu-id="8cafd-122">**Costo attivo - Prezzo dell'articolo** - Le organizzazioni potrebbero riscontrare problemi di prestazioni se utilizzano processi aziendali in cui l'inventario diventa regolarmente negativo e, allo stesso tempo, il volume delle transazioni è elevato.</span><span class="sxs-lookup"><span data-stu-id="8cafd-122">**Active cost – Item price** – Organizations might experience performance issues if they use business processes where inventory regularly goes negative and, at the same time, the transaction volume is high.</span></span> <span data-ttu-id="8cafd-123">Questa impostazione può aiutare a mitigare questi problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8cafd-123">This setting can help mitigate those performance issues.</span></span>

<span data-ttu-id="8cafd-124">![Parametri di contabilità inventario](media/inventory-accounting-parameters.png "Parametri di contabilità inventario")</span><span class="sxs-lookup"><span data-stu-id="8cafd-124">![Inventory accounting parameters](media/inventory-accounting-parameters.png "Inventory accounting parameters")</span></span>
