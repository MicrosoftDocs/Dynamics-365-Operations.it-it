---
title: Gestione migliorata degli articoli di cui viene tenuta traccia in batch
description: In questo argomento vengono descritti i miglioramenti apportati alla gestione dei batch di articoli di cui viene tenuta traccia durante il processo di registrazione rendiconti di vendita al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4456fc3d5bc4547fa8211642b11ca6df455fa187
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617391"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="eb67d-103">Gestione migliorata degli articoli di cui viene tenuta traccia in batch</span><span class="sxs-lookup"><span data-stu-id="eb67d-103">Improved handling of batch-tracked items</span></span>

<span data-ttu-id="eb67d-104">Nei POS di Microsoft Dynamics 365 for Retail i numeri batch non possono essere acquisiti per gli articoli di cui viene tenuta traccia in batch al momento della vendita.</span><span class="sxs-lookup"><span data-stu-id="eb67d-104">In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="eb67d-105">Per configurazioni specifiche, tuttavia, quando le vendite vengono registrate nelle sedi tramite ordini cliente o registrazione rendiconti, il sistema Microsoft Dynamics prevede che i numeri batch validi per gli articoli di cui viene tenuta traccia in batch esistano e vengano utilizzati durante il processo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="eb67d-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="eb67d-106">Se per i prodotti sono disponibili numeri di batch validi, questi ultimi vengono utilizzati nel processo di fatturazione degli ordini cliente e in quello di fatturazione degli stessi ordini dalla registrazione rendiconti.</span><span class="sxs-lookup"><span data-stu-id="eb67d-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="eb67d-107">In caso contrario, il processo di fatturazione degli ordini cliente non può essere registrato e l'utente POS riceve un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="eb67d-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="eb67d-108">A questo punto nella registrazione rendiconti si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="eb67d-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="eb67d-109">Questo stato di errore si verifica anche quando per i prodotti è stato attivato l'inventario negativo.</span><span class="sxs-lookup"><span data-stu-id="eb67d-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="eb67d-110">I miglioramenti apportati in Microsoft Dynamics for Retail versione 10.0.4 e successive garantiscono che, qualora l'inventario negativo sia stato attivato per gli articoli di cui viene tenuta traccia in batch, la fatturazione degli ordini cliente eseguita tramite la registrazione rendiconti non venga bloccata per tali articoli se il valore di inventario è pari a zero o se un numero batch non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="eb67d-110">Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="eb67d-111">Quando i numeri batch non sono disponibili, la nuova funzionalità utilizza un ID batch predefinito per le righe di vendita.</span><span class="sxs-lookup"><span data-stu-id="eb67d-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="eb67d-112">Per definire l'ID batch predefinito utilizzato per gli ordini cliente, nella scheda **Ordini cliente** della pagina **Parametri di vendita al dettaglio** impostare il campo **ID batch predefinito** nella Scheda dettaglio **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="eb67d-112">To define the default batch ID that is used for customer orders, on the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="eb67d-113">Per definire l'ID batch utilizzato per la fatturazione degli ordini cliente tramite la registrazione rendiconti, nella scheda **Registrazione** della pagina **Parametri di vendita al dettaglio** impostare il campo **ID batch predefinito** nella Scheda dettaglio **Aggiornamento dell'inventario**.</span><span class="sxs-lookup"><span data-stu-id="eb67d-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Retail parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="eb67d-114">Questa funzionalità è disponibile solo quando i processi di magazzino avanzati sono attivati per il magazzino e gli articoli del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="eb67d-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="eb67d-115">In una versione successiva, la funzionalità sarà supportata anche per scenari in cui la gestione avanzata magazzino non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="eb67d-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>
