---
title: Prenotare lo stesso batch per un ordine cliente
description: Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2d6089d07b0f8bc1a36703b5b1c2f24af72770d5
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="1b253-103">Prenotare lo stesso batch per un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="1b253-103">Reserve the same batch for a sales order</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b253-104">Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.</span><span class="sxs-lookup"><span data-stu-id="1b253-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="1b253-105">La prenotazione dello stesso batch consente di prenotare le scorte per una riga di ordine cliente da un unico lotto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="1b253-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="1b253-106">Ad esempio, un cliente che ordina carta da parati può richiedere che l'intero ordine venga coperto dallo stesso batch o lotto per evitare di ricevere rotoli non omogenei tra loro.</span><span class="sxs-lookup"><span data-stu-id="1b253-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="1b253-107">Per impostare un prodotto per l'utilizzo della prenotazione dello stesso batch, è necessario che siano attive le seguenti impostazioni nei gruppi di modelli di articoli, nel gruppo di dimensioni di tracciabilità e nel gruppo di dimensioni di immagazzinamento:</span><span class="sxs-lookup"><span data-stu-id="1b253-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

-   <span data-ttu-id="1b253-108">**Gruppi di modelli di articoli**: il gruppo di modelli di articoli deve avere i campi **Selezione stesso batch** e **Fabbisogno consolidato** selezionati nel gruppo di campi **Prenotazione** dei criteri di inventario.</span><span class="sxs-lookup"><span data-stu-id="1b253-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
-   <span data-ttu-id="1b253-109">**Gruppi di dimensioni di tracciabilità**: il gruppo di dimensioni di tracciabilità deve avere il campo **Piano di copertura per dimensione** selezionato per numero batch.</span><span class="sxs-lookup"><span data-stu-id="1b253-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
-   <span data-ttu-id="1b253-110">**Gruppi di dimensioni di immagazzinamento**: il gruppo di dimensioni di immagazzinamento deve avere il campo **Piano di copertura per dimensione** selezionato per **Sito** e **Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="1b253-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="1b253-111">Quando si prenotano scorte di un prodotto in una riga ordine cliente impostata per la selezione stesso batch, in Microsoft Dynamics 365 for Finance and Operations viene tentata la prenotazione della quantità ordinata da un unico batch di magazzino.</span><span class="sxs-lookup"><span data-stu-id="1b253-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, Microsoft Dynamics 365 for Finance and Operations tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="1b253-112">Vengono inoltre considerati eventuali requisiti specifici di attributi batch.</span><span class="sxs-lookup"><span data-stu-id="1b253-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="1b253-113">Se la quantità non può essere coperta da un unico batch, viene visualizzata la pagina **Conflitto di stessa prenotazione batch**.</span><span class="sxs-lookup"><span data-stu-id="1b253-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="1b253-114">In questa pagina vengono descritte le problematiche e anche le azioni che è possibile intraprendere per continuare con la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="1b253-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="1b253-115">Le seguenti condizioni possono impedire la prenotazione del batch:</span><span class="sxs-lookup"><span data-stu-id="1b253-115">The following conditions might prevent the batch from being reserved:</span></span>

-   <span data-ttu-id="1b253-116">Il codice smaltimento batch presenta la voce **Blocca prenotazione** per le vendite contrassegnata come **Bloccata**.</span><span class="sxs-lookup"><span data-stu-id="1b253-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
-   <span data-ttu-id="1b253-117">Il batch è scaduto in base alla data di scadenza e ai giorni di vendita del cliente eventualmente applicabili.</span><span class="sxs-lookup"><span data-stu-id="1b253-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="1b253-118">L'articolo può comunque essere idoneo alla prenotazione se il gruppo di modelli di articoli per l'articolo è controllato in base alla data FEFO (First Expired, First Out) e se il campo della data di consumo consigliata è selezionato come criterio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="1b253-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
-   <span data-ttu-id="1b253-119">I giorni di durata a scaffale rimanenti per il batch sono insufficienti in base alla data di scadenza e alla data di consumo consigliata, più gli eventuali giorni di vendita del cliente.</span><span class="sxs-lookup"><span data-stu-id="1b253-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>





