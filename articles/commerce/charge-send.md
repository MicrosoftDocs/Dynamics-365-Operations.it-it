---
title: Spedire ordine da un altro punto vendita usando la funzionalità Addebita invio
description: In questo argomento viene descritta la funzionalità Addebita invio.
author: ashishmsft
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: b9e0c4f55fd823bf7471edfe6ce1d424b0179d21
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800473"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a><span data-ttu-id="386f4-103">Spedire ordine da un altro punto vendita usando la funzionalità Addebita invio</span><span class="sxs-lookup"><span data-stu-id="386f4-103">Ship orders from another store by using the Charge send feature</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="386f4-104">Con la funzionalità Addebita invio di Commerce, è possibile piazzare ordini cliente in un punto vendita e spedirli da un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="386f4-104">With the Charge send feature in Commerce, customer orders can be placed in one store and shipped from another store.</span></span>

<span data-ttu-id="386f4-105">Gli ordini cliente nel client POS supportano molteplici opzioni di evasione.</span><span class="sxs-lookup"><span data-stu-id="386f4-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="386f4-106">Alcuni esempi di opzioni di evasione includono:</span><span class="sxs-lookup"><span data-stu-id="386f4-106">Some examples of fulfillment options include:</span></span>

- <span data-ttu-id="386f4-107">Prelievo nello stessa punto vendita a una data diversa.</span><span class="sxs-lookup"><span data-stu-id="386f4-107">Pick up from the same store on a different date.</span></span>
- <span data-ttu-id="386f4-108">Prelievo in un punto vendita differente alla stessa data o a una data differente.</span><span class="sxs-lookup"><span data-stu-id="386f4-108">Pick up from a different store on the same date or a different date.</span></span>
- <span data-ttu-id="386f4-109">Spedizione dal magazzino di spedizione predefinito assegnato al punto vendita e consegna a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="386f4-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="386f4-110">La funzionalità Addebita invio utilizza le seguenti operazioni POS: Spedisci tutti i prodotti e Spedisci prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="386f4-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="386f4-111">Ciò consente all'addetto del punto vendita di selezionare l'ubicazione "Spedisci da" da cui evadere l'ordine o la riga ordine.</span><span class="sxs-lookup"><span data-stu-id="386f4-111">This allows the store clerk to select the "ship from" location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="386f4-112">Per impostazione predefinita, l'ubicazione "Spedisci da" è il magazzino di spedizione associato al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="386f4-112">By default, the "ship from" location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="386f4-113">L'addetto del punto vendita può tuttavia modificare tale ubicazione e selezionare qualsiasi punto vendita definito nel gruppo di localizzatori di punti vendita assegnato al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="386f4-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span>

<span data-ttu-id="386f4-114">La funzionalità di selezione degli indirizzi di "spedizione" rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="386f4-114">The ability to select "ship to" addresses remains unchanged.</span></span>

<span data-ttu-id="386f4-115">I metodi di spedizione che possono essere utilizzati per evadere la riga dell'ordine sono basati sulla configurazione delle modalità di consegna valide per prodotti e indirizzi.</span><span class="sxs-lookup"><span data-stu-id="386f4-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="386f4-116">Poiché le regole sulle modalità di consegna valide vengono gestite solo in Headquarters (HQ), il client POS esegua una chiamata in tempo reale per recuperare le modalità di consegna valide per una riga di spedizione.</span><span class="sxs-lookup"><span data-stu-id="386f4-116">Because the rules about valid of modes of delivery are maintained only in the Headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]