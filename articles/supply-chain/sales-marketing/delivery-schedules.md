---
title: Programmazioni consegna
description: Le programmazioni consegna consentono di tenere traccia della quantità della riga ordine quando si utilizzano più consegne per un singolo ordine cliente, una singola offerta di vendita o un singolo ordine fornitore.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc25ff113291b2a8a0a7ba15637e4d094feb9aae
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431311"
---
# <a name="delivery-schedules"></a><span data-ttu-id="25a08-103">Programmazioni consegna</span><span class="sxs-lookup"><span data-stu-id="25a08-103">Delivery schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25a08-104">Le programmazioni consegna consentono di tenere traccia della quantità della riga ordine quando si utilizzano più consegne per un singolo ordine cliente, una singola offerta di vendita o un singolo ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="25a08-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="25a08-105">Usare una programmazione consegna quando la quantità totale di una riga ordine o offerta deve essere consegnata in più spedizioni.</span><span class="sxs-lookup"><span data-stu-id="25a08-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="25a08-106">Le singole spedizioni sono rappresentate dalle righe consegna.</span><span class="sxs-lookup"><span data-stu-id="25a08-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="25a08-107">Due o più righe consegna formano una programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="25a08-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="25a08-108">Le righe consegna possono avere date di consegna, quantità, modalità di consegna e dimensioni di immagazzinamento diverse, ad esempio sito e magazzino.</span><span class="sxs-lookup"><span data-stu-id="25a08-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="25a08-109">**Esempio di una programmazione consegna**</span><span class="sxs-lookup"><span data-stu-id="25a08-109">**Example of a delivery schedule**</span></span>

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="25a08-110">Ordine totale (riga ordine originale)</span><span class="sxs-lookup"><span data-stu-id="25a08-110">Total order (original order line)</span></span> | <span data-ttu-id="25a08-111">600 sedie</span><span class="sxs-lookup"><span data-stu-id="25a08-111">600 chairs</span></span>                               |
| <span data-ttu-id="25a08-112">Programmazione consegna richiesta</span><span class="sxs-lookup"><span data-stu-id="25a08-112">Requested delivery schedule</span></span>       | <span data-ttu-id="25a08-113">100 sedie al mese</span><span class="sxs-lookup"><span data-stu-id="25a08-113">100 chairs per month</span></span>                     |
| <span data-ttu-id="25a08-114">Intervallo temporale di consegna richiesto</span><span class="sxs-lookup"><span data-stu-id="25a08-114">Requested time frame for delivery</span></span> | <span data-ttu-id="25a08-115">6 mesi, il primo giorno di ogni mese</span><span class="sxs-lookup"><span data-stu-id="25a08-115">6 months, on the first day of each month</span></span> |

<span data-ttu-id="25a08-116">In questo scenario il cliente richiede la consegna di 600 sedie in batch di 100 sedie da consegnare in un periodo di sei mesi.</span><span class="sxs-lookup"><span data-stu-id="25a08-116">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="25a08-117">Per tenere traccia dei fabbisogni di consegna, si crea una programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="25a08-117">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="25a08-118">Nella pagina di programmazione consegna creare sei righe consegna separate.</span><span class="sxs-lookup"><span data-stu-id="25a08-118">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="25a08-119">In ogni riga consegna inserire 100 sedie e indicare la data di consegna di tale lotto.</span><span class="sxs-lookup"><span data-stu-id="25a08-119">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="25a08-120">In questo caso ogni riga viene compensata il primo del mese per sei mesi consecutivi.</span><span class="sxs-lookup"><span data-stu-id="25a08-120">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="25a08-121">Quando si crea una programmazione consegna, il tipo di riga ordine originale viene automaticamente cambiato in **Riga ordine con più consegne**.</span><span class="sxs-lookup"><span data-stu-id="25a08-121">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="25a08-122">Una riga di questo tipo viene definita una riga commerciali e viene contrassegnata da un'icona.</span><span class="sxs-lookup"><span data-stu-id="25a08-122">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="25a08-123">La riga consegna è contrassegnata da un'icona diversa.</span><span class="sxs-lookup"><span data-stu-id="25a08-123">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="25a08-124">Se si modifica una quantità in una riga consegna, la riga commerciale viene aggiornata alla quantità totale della programmazione consegna.</span><span class="sxs-lookup"><span data-stu-id="25a08-124">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="25a08-125">Se un accordo commerciale ha definito uno sconto totale per l'ordine, la programmazione consegna assicura che l'ordine sia idoneo per lo sconto sull'ordine totale anche quando l'ordine è diviso in più consegne.</span><span class="sxs-lookup"><span data-stu-id="25a08-125">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="25a08-126">Gli ordini con una programmazione consegna vengono elaborati a fronte delle righe consegna.</span><span class="sxs-lookup"><span data-stu-id="25a08-126">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="25a08-127">L'elaborazione include la registrazione dei documenti di trasporto, delle entrate prodotti e della fatturazione.</span><span class="sxs-lookup"><span data-stu-id="25a08-127">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="25a08-128">Stampe di documenti di ordini e offerte con una programmazione consegna indicano solo le righe consegna.</span><span class="sxs-lookup"><span data-stu-id="25a08-128">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="25a08-129">Non mostrano le righe originali (righe commerciali).</span><span class="sxs-lookup"><span data-stu-id="25a08-129">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="25a08-130">**Nota:** inoltre, solo le righe consegna vengono visualizzate quando vengono eseguite le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="25a08-130">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="25a08-131">Registra</span><span class="sxs-lookup"><span data-stu-id="25a08-131">Post</span></span>
-   <span data-ttu-id="25a08-132">Si duplicano pagine</span><span class="sxs-lookup"><span data-stu-id="25a08-132">Copy pages</span></span>
-   <span data-ttu-id="25a08-133">Si sfogliano le pagine elenco e i report</span><span class="sxs-lookup"><span data-stu-id="25a08-133">Browse list pages and reports</span></span>

<span data-ttu-id="25a08-134">Quando si confermano le offerte di vendita, negli ordini clienti risultanti viene visualizzata l'intera programmazione consegna, incluse le righe ordine con più consegne.</span><span class="sxs-lookup"><span data-stu-id="25a08-134">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="25a08-135">La programmazione consegna viene visualizzata per intero anche in tutte le pagine principali, ad esempio ordini cliente, offerte di vendita e ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="25a08-135">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>



