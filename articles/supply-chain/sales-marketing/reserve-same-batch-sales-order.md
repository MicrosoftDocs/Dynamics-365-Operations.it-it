---
title: Prenotare lo stesso batch per un ordine cliente
description: Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.
author: omulvad
manager: tfehr
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c7745b1306142678760318cc47f54b93d6f727a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231818"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="cfb0b-103">Prenotare lo stesso batch per un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="cfb0b-103">Reserve the same batch for a sales order</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cfb0b-104">Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="cfb0b-105">La prenotazione dello stesso batch consente di prenotare le scorte per una riga di ordine cliente da un unico lotto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="cfb0b-106">Ad esempio, un cliente che ordina carta da parati può richiedere che l'intero ordine venga coperto dallo stesso batch o lotto per evitare di ricevere rotoli non omogenei tra loro.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="cfb0b-107">Per impostare un prodotto per l'utilizzo della prenotazione dello stesso batch, è necessario che siano attive le seguenti impostazioni nei gruppi di modelli di articoli, nel gruppo di dimensioni di tracciabilità e nel gruppo di dimensioni di immagazzinamento:</span><span class="sxs-lookup"><span data-stu-id="cfb0b-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

- <span data-ttu-id="cfb0b-108">**Gruppi di modelli di articoli**: il gruppo di modelli di articoli deve avere i campi **Selezione stesso batch** e **Fabbisogno consolidato** selezionati nel gruppo di campi **Prenotazione** dei criteri di inventario.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
- <span data-ttu-id="cfb0b-109">**Gruppi di dimensioni di tracciabilità**: il gruppo di dimensioni di tracciabilità deve avere il campo **Piano di copertura per dimensione** selezionato per numero batch.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
- <span data-ttu-id="cfb0b-110">**Gruppi di dimensioni di immagazzinamento**: il gruppo di dimensioni di immagazzinamento deve avere il campo **Piano di copertura per dimensione** selezionato per **Sito** e **Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="cfb0b-111">Quando si prenotano scorte di un prodotto in una riga ordine cliente impostata per la selezione stesso batch, il sistema tenta la prenotazione della quantità ordinata da un unico batch di magazzino.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, the system tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="cfb0b-112">Vengono inoltre considerati eventuali requisiti specifici di attributi batch.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="cfb0b-113">Se la quantità non può essere coperta da un unico batch, viene visualizzata la pagina **Conflitto di stessa prenotazione batch**.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="cfb0b-114">In questa pagina vengono descritte le problematiche e anche le azioni che è possibile intraprendere per continuare con la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="cfb0b-115">Le seguenti condizioni possono impedire la prenotazione del batch:</span><span class="sxs-lookup"><span data-stu-id="cfb0b-115">The following conditions might prevent the batch from being reserved:</span></span>

- <span data-ttu-id="cfb0b-116">Il codice smaltimento batch presenta la voce **Blocca prenotazione** per le vendite contrassegnata come **Bloccata**.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
- <span data-ttu-id="cfb0b-117">Il batch è scaduto in base alla data di scadenza e ai giorni di vendita del cliente eventualmente applicabili.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="cfb0b-118">L'articolo può comunque essere idoneo alla prenotazione se il gruppo di modelli di articoli per l'articolo è controllato in base alla data FEFO (First Expired, First Out) e se il campo della data di consumo consigliata è selezionato come criterio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
- <span data-ttu-id="cfb0b-119">I giorni di durata a scaffale rimanenti per il batch sono insufficienti in base alla data di scadenza e alla data di consumo consigliata, più gli eventuali giorni di vendita del cliente.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>

<span data-ttu-id="cfb0b-120">Per gli articoli associati a un gruppo di dimensioni di immagazzinamento con **Usa processi di gestione magazzino** abilitato, è possibile prenotare specifici numeri di lotto utilizzando una gerarchia di prenotazione con la dimensione di inventario del numero di lotto definita sopra la dimensione della posizione.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-120">For items associated with a storage dimension group that has **Use warehouse management processes** enabled, you can reserve specific batch numbers by using a reservation hierarchy with the batch number inventory dimension defined above the location dimension.</span></span> <span data-ttu-id="cfb0b-121">La pagina **Prenotazione batch** per le righe ordine cliente e trasferimento consente inoltre di selezionare e prenotare più righe in base ai numeri di batch disponibili.</span><span class="sxs-lookup"><span data-stu-id="cfb0b-121">The **Batch reservation** page for sales and transfer order lines also lets you select and reserve multiple lines based on the available batch numbers.</span></span> <span data-ttu-id="cfb0b-122">Per ulteriori informazioni sulle operazioni da eseguire se si utilizza una gerarchia di prenotazione con la dimensione del numero di batch al di sotto della posizione, vedere [Criteri flessibili di prenotazione delle dimensioni a livello di magazzino](../warehousing/flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="cfb0b-122">For more information about what to do if you are using a reservation hierarchy that has the batch number dimension below the location, see [Flexible warehouse-level dimension reservation policy](../warehousing/flexible-warehouse-level-dimension-reservation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]