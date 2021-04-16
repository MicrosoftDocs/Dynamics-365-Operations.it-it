---
title: Modulo di informazioni sul ritiro
description: In questo argomento viene descritto il modulo di informazioni sul ritiro e la procedura per aggiungerlo alle pagine del checkout in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 063701d5cd5714febeb32907346d9f6e5c2a2ca1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804407"
---
# <a name="pickup-information-module"></a><span data-ttu-id="1380b-103">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="1380b-103">Pickup information module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1380b-104">In questo argomento viene descritto il modulo di informazioni sul ritiro e la procedura per aggiungerlo alle pagine del checkout in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1380b-104">This topic covers the pickup information module and describes how to add it to checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1380b-105">Il modulo di informazioni sul ritiro può essere utilizzato in un modulo checkout per mostrare le informazioni sul ritiro dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="1380b-105">The pickup information module can be used in a checkout module to show order pickup information.</span></span> <span data-ttu-id="1380b-106">I clienti possono visualizzare le date di ritiro e le fasce orarie disponibili, quindi selezionare un orario adatto per ritirare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="1380b-106">Customers can view available pickup dates and time slots, and then select a suitable time to pick up their order.</span></span> <span data-ttu-id="1380b-107">Ad esempio, un cliente può scegliere di ritirare un ordine alle 15.00 del 21 marzo dal negozio di San Francisco.</span><span class="sxs-lookup"><span data-stu-id="1380b-107">For example, a customer can choose to pick up an order at 3 PM on March 21 from the San Francisco store.</span></span>

<span data-ttu-id="1380b-108">Le fasce orarie di ritiro per i negozi appropriati devono essere configurate in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="1380b-108">Pickup time slots for the appropriate stores must be configured in Commerce headquarters.</span></span> <span data-ttu-id="1380b-109">Per ulteriori informazioni, vedere [Creare e aggiornare le fasce orarie per il ritiro del cliente](dev-itpro/pickup-timeslots.md).</span><span class="sxs-lookup"><span data-stu-id="1380b-109">For more information, see [Create and update time slots for customer pickup](dev-itpro/pickup-timeslots.md).</span></span>

<span data-ttu-id="1380b-110">Se un modulo di informazioni sul ritiro viene creato su una pagina checkout, ma non sono definiti intervalli di tempo per il negozio selezionato per il ritiro, il modulo mostrerà le informazioni, ma l'utente non sarà in grado di selezionare alcuna fascia oraria.</span><span class="sxs-lookup"><span data-stu-id="1380b-110">If a pickup information module is created on a checkout page, but no time slots are defined for the store that is selected for pickup, the module will show information, but the user won't be able to select any time slots.</span></span> <span data-ttu-id="1380b-111">Le fasce orarie sono opzionali e non sono necessarie per effettuare un ordine.</span><span class="sxs-lookup"><span data-stu-id="1380b-111">Time slots are optional and aren't required to place an order.</span></span>

<span data-ttu-id="1380b-112">Se vengono selezionati più articoli per il ritiro in più negozi, il modulo di informazioni sul ritiro consentirà all'utente di selezionare una fascia oraria per ogni negozio, a condizione che siano disponibili le fasce orarie per il negozio.</span><span class="sxs-lookup"><span data-stu-id="1380b-112">If multiple items are selected for pickup across multiple stores, the pickup information module will let the user select a time slot for each store, provided that time slots are available for it.</span></span>

> [!NOTE]
> <span data-ttu-id="1380b-113">Il supporto per le fasce orarie e il modulo di informazioni sul ritiro è disponibile in Dynamics 365 Commerce versione 10.0.15 e successive.</span><span class="sxs-lookup"><span data-stu-id="1380b-113">Support for time slots and the checkout pickup information module is available in Dynamics 365 Commerce version 10.0.15 and later.</span></span>

<span data-ttu-id="1380b-114">La seguente illustrazione mostra un esempio di selezione della fascia oraria tramite il modulo di informazioni sul ritiro in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="1380b-114">The following illustration shows an example of time slot selection through the pickup information module on a checkout page.</span></span>

![Esempio di un modulo di informazioni sul ritiro su una pagina checkout](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a><span data-ttu-id="1380b-116">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="1380b-116">Module properties</span></span>

- <span data-ttu-id="1380b-117">**Intestazione** – Immettere un'intestazione per il modulo.</span><span class="sxs-lookup"><span data-stu-id="1380b-117">**Heading** – Enter a heading for the module.</span></span>

## <a name="show-time-slot-information-after-an-order-is-placed"></a><span data-ttu-id="1380b-118">Mostrare le informazioni sulla fascia oraria dopo aver effettuato un ordine</span><span class="sxs-lookup"><span data-stu-id="1380b-118">Show time slot information after an order is placed</span></span>

<span data-ttu-id="1380b-119">Dopo aver effettuato un ordine, le informazioni sulla fascia oraria selezionata possono essere visualizzate nel [modulo di conferma dell'ordine](order-confirmation-module.md) e nel [modulo dettagli ordine](account-management.md#order-details-page).</span><span class="sxs-lookup"><span data-stu-id="1380b-119">After an order is placed, information about the selected time slot can be viewed in the [order confirmation module](order-confirmation-module.md) and the [order details module](account-management.md#order-details-page).</span></span> <span data-ttu-id="1380b-120">Entrambi questi moduli hanno la proprietà **Mostra informazioni sulla fascia oraria**.</span><span class="sxs-lookup"><span data-stu-id="1380b-120">Both these modules have a **Show timeslot information** property.</span></span> <span data-ttu-id="1380b-121">Per mostrare la fascia oraria selezionata durante il processo di ordinazione, questa proprietà deve essere impostata su **Vero**.</span><span class="sxs-lookup"><span data-stu-id="1380b-121">Before they can show the selected time slot during the order process, this property must be set to **True**.</span></span>

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a><span data-ttu-id="1380b-122">Aggiungere un modulo di informazioni sul ritiro a una pagina checkout</span><span class="sxs-lookup"><span data-stu-id="1380b-122">Add a checkout pickup information module to a page</span></span>

<span data-ttu-id="1380b-123">Per istruzioni su come aggiungere un moduli di informazioni sul ritiro a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="1380b-123">For instructions about how to add a pickup information module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="1380b-124">La seguente illustrazione mostra un esempio di una pagina checkout e-commerce che include fasce orarie per gli articoli della riga di ritiro.</span><span class="sxs-lookup"><span data-stu-id="1380b-124">The following illustration shows an example of an e-Commerce checkout page that includes time slots for pickup line items.</span></span>

![Esempio di una pagina checkout e-commerce che include fasce orarie per gli articoli della riga di ritiro.](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a><span data-ttu-id="1380b-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1380b-126">Additional resources</span></span>

[<span data-ttu-id="1380b-127">Creare e aggiornare le fasce orarie per il ritiro del cliente</span><span class="sxs-lookup"><span data-stu-id="1380b-127">Create and update time slots for customer pickup</span></span>](dev-itpro/pickup-timeslots.md)

[<span data-ttu-id="1380b-128">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="1380b-128">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="1380b-129">Modulo conferma ordine</span><span class="sxs-lookup"><span data-stu-id="1380b-129">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="1380b-130">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="1380b-130">Order details module</span></span>](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]