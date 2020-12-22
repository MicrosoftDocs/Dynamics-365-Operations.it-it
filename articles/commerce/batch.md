---
title: Gestione migliorata degli articoli di cui viene tenuta traccia in batch
description: In questo argomento vengono descritti i miglioramenti apportati alla gestione dei batch di articoli di cui viene tenuta traccia durante il processo di registrazione dei rendiconti.
author: josaw1
manager: AnnBe
ms.date: 11/04/2019
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
ms.openlocfilehash: ecff18f0a34d22ef359f473fa6aaaff16c811bb6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459313"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="1b766-103">Gestione migliorata degli articoli di cui viene tenuta traccia in batch</span><span class="sxs-lookup"><span data-stu-id="1b766-103">Improved handling of batch-tracked items</span></span>


[!include [banner](includes/banner.md)]


<span data-ttu-id="1b766-104">Nei POS, non è possibile acquisire i numeri batch per gli articoli di cui viene tenuta traccia in batch al momento della vendita.</span><span class="sxs-lookup"><span data-stu-id="1b766-104">In Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="1b766-105">Per configurazioni specifiche, tuttavia, quando le vendite vengono registrate nelle sedi tramite ordini cliente o registrazione rendiconti, il sistema Microsoft Dynamics prevede che i numeri batch validi per gli articoli di cui viene tenuta traccia in batch esistano e vengano utilizzati durante il processo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="1b766-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="1b766-106">Se per i prodotti sono disponibili numeri di batch validi, questi ultimi vengono utilizzati nel processo di fatturazione degli ordini cliente e in quello di fatturazione degli stessi ordini dalla registrazione rendiconti.</span><span class="sxs-lookup"><span data-stu-id="1b766-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="1b766-107">In caso contrario, il processo di fatturazione degli ordini cliente non può essere registrato e l'utente POS riceve un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="1b766-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="1b766-108">A questo punto nella registrazione rendiconti si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="1b766-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="1b766-109">Questo stato di errore si verifica anche quando per i prodotti è stato attivato l'inventario negativo.</span><span class="sxs-lookup"><span data-stu-id="1b766-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="1b766-110">I miglioramenti apportati in Retail 10.0.4 e versioni successive garantiscono che, qualora l'inventario negativo sia stato attivato per gli articoli di cui viene tenuta traccia in batch, la fatturazione degli ordini cliente eseguita tramite la registrazione rendiconti non venga bloccata per tali articoli se il valore di inventario è pari a 0 (zero) o se un numero batch non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1b766-110">Improvements that have been made in Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="1b766-111">Quando i numeri batch non sono disponibili, la nuova funzionalità utilizza un ID batch predefinito per le righe di vendita.</span><span class="sxs-lookup"><span data-stu-id="1b766-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="1b766-112">Per definire l'ID batch predefinito utilizzato per gli ordini cliente, nella scheda **Ordini cliente** della pagina **Parametri di commercio** impostare il campo **ID batch predefinito** nella Scheda dettaglio **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="1b766-112">To define the default batch ID that is used for customer orders, on the **Commerce parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="1b766-113">Per definire l'ID batch utilizzato per la fatturazione degli ordini cliente tramite la registrazione rendiconti, nella scheda **Registrazione** della pagina **Parametri di commercio** impostare il campo **ID batch predefinito** nella Scheda dettaglio **Aggiorna inventario**.</span><span class="sxs-lookup"><span data-stu-id="1b766-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Commerce parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="1b766-114">Questa funzionalità è disponibile solo quando i processi di magazzino avanzati sono attivati per il magazzino e gli articoli del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="1b766-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="1b766-115">In una versione successiva, la funzionalità sarà supportata anche per scenari in cui la gestione avanzata magazzino non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="1b766-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="1b766-116">Il supporto per una migliore gestione degli articoli di cui viene tenuta traccia in batch durante la registrazione dei rendiconti per scenari diversi dalla gestione avanzata magazzino è stato introdotto in Retail versione 10.0.5.</span><span class="sxs-lookup"><span data-stu-id="1b766-116">Support for improved handling of batch-tracked items during statement posting for non-advanced warehouse management scenarios was introduced in Retail version 10.0.5.</span></span>
