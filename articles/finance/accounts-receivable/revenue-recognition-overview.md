---
title: Panoramica del riconoscimento ricavi
description: In questo argomento vengono fornite informazioni sulla funzionalità di riconoscimento dei ricavi. Questa funzionalità fornisce un framework flessibile che consente di definire regole specifiche della società per riconoscere sia il prezzo che la programmazione dei ricavi per ordini con più elementi.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: d1aeb0cf556582ff53ca00c6bb8d863a088950b9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184119"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="fc30d-104">Panoramica del riconoscimento ricavi</span><span class="sxs-lookup"><span data-stu-id="fc30d-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> <span data-ttu-id="fc30d-105">Il riconoscimento ricavi non può ancora essere attivato tramite la gestione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="fc30d-105">The Revenue recognition feature can't yet be turned on through Feature management.</span></span> <span data-ttu-id="fc30d-106">Per attivarlo, attualmente è necessario utilizzare le chiavi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fc30d-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="fc30d-107">Le società di settori che vendono più elementi, ad esempio prodotti, servizi, sottoscrizioni e così via, devono essere in grado di separare gli ordini con più elementi in modo che sia possibile riconoscere i ricavi in base a un set di linee guida specifiche della società e del settore.</span><span class="sxs-lookup"><span data-stu-id="fc30d-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="fc30d-108">In generale, il processo di riconoscimento ricavi può essere utilizzato in genere per eseguire queste attività:</span><span class="sxs-lookup"><span data-stu-id="fc30d-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="fc30d-109">Allocare i ricavi per garantire che il prezzo dei ricavi venga riconosciuto correttamente in base al valore dei componenti presenti negli ordini con più elementi.</span><span class="sxs-lookup"><span data-stu-id="fc30d-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="fc30d-110">Differire i ricavi in base a una programmazione che rappresenta l'intervallo di tempo contrattuale e le percentuali per riconoscere i ricavi nel tempo.</span><span class="sxs-lookup"><span data-stu-id="fc30d-110">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

<span data-ttu-id="fc30d-111">La funzionalità di riconoscimento ricavi fornisce un framework flessibile che consente di definire regole specifiche della società per riconoscere sia il prezzo che la programmazione dei ricavi.</span><span class="sxs-lookup"><span data-stu-id="fc30d-111">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="fc30d-112">I prodotti rilasciati vengono utilizzati per supportare il riconoscimento ricavi sui documenti degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="fc30d-112">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="fc30d-113">I prodotti rilasciati contengono le impostazioni necessarie per determinare il prezzo e la programmazione dei ricavi.</span><span class="sxs-lookup"><span data-stu-id="fc30d-113">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="fc30d-114">L'ordine cliente può derivare da un progetto di tempistica e materiali.</span><span class="sxs-lookup"><span data-stu-id="fc30d-114">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="fc30d-115">Le società possono utilizzare la funzionalità di programmazione dei ricavi senza utilizzare quella relativa ai prezzi.</span><span class="sxs-lookup"><span data-stu-id="fc30d-115">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="fc30d-116">Di conseguenza, il prezzo nelle righe dell'ordine cliente verrà utilizzato come ricavo o come ricavo differito.</span><span class="sxs-lookup"><span data-stu-id="fc30d-116">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="fc30d-117">Se nella riga ordine cliente è presente una programmazione ricavi, il prezzo in tale riga verrà differito.</span><span class="sxs-lookup"><span data-stu-id="fc30d-117">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="fc30d-118">Se nella riga ordine cliente non è presente alcuna programmazione ricavi, il prezzo in tale riga verrà registrato in un conto ricavi al momento della fatturazione.</span><span class="sxs-lookup"><span data-stu-id="fc30d-118">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="fc30d-119">Il prezzo dei ricavi viene calcolato quando l'ordine cliente viene confermato o quando viene registrata la fattura.</span><span class="sxs-lookup"><span data-stu-id="fc30d-119">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="fc30d-120">Per visualizzare in anteprima il prezzo dei ricavi prima della registrazione della fattura, è necessario confermare l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="fc30d-120">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="fc30d-121">Quando l'ordine cliente viene confermato, se in una riga dell'ordine cliente è presente una programmazione dei ricavi, viene creata anche una programmazione dei ricavi prevista.</span><span class="sxs-lookup"><span data-stu-id="fc30d-121">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="fc30d-122">Quando l'ordine cliente viene fatturato, la programmazione dei ricavi prevista viene eliminata e sostituita con la programmazione del riconoscimento ricavi effettiva.</span><span class="sxs-lookup"><span data-stu-id="fc30d-122">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="fc30d-123">I dettagli della programmazione per il riconoscimento dei ricavi vengono mantenuti per ogni riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="fc30d-123">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="fc30d-124">Di conseguenza, il responsabile del riconoscimento ricavi può visualizzare i dettagli e rilasciare le righe sui ricavi quando l'obbligo contrattuale è stato soddisfatto.</span><span class="sxs-lookup"><span data-stu-id="fc30d-124">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="fc30d-125">Al termine di ogni periodo, il responsabile del riconoscimento ricavi può creare un giornale di registrazione ricavi per rilasciare tutte le righe di programmazione in scadenza prima o in corrispondenza di una data definita.</span><span class="sxs-lookup"><span data-stu-id="fc30d-125">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="fc30d-126">Tale giornale non viene registrato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="fc30d-126">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="fc30d-127">Di conseguenza, il responsabile del riconoscimento ricavi può verificare che gli importi corretti vengano rilasciati dai ricavi differiti a quelli effettivi.</span><span class="sxs-lookup"><span data-stu-id="fc30d-127">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="fc30d-128">Se una modifica del contratto determina l'aggiunta di una nuova riga ordine cliente all'ordine cliente esistente oppure a uno nuovo, è possibile eseguire un processo di riassegnazione per correggere il prezzo dei ricavi in tutte le righe dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="fc30d-128">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>
