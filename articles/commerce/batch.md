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
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004207"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Gestione migliorata degli articoli di cui viene tenuta traccia in batch


[!include [banner](includes/banner.md)]


Nei POS, non è possibile acquisire i numeri batch per gli articoli di cui viene tenuta traccia in batch al momento della vendita. Per configurazioni specifiche, tuttavia, quando le vendite vengono registrate nelle sedi tramite ordini cliente o registrazione rendiconti, il sistema Microsoft Dynamics prevede che i numeri batch validi per gli articoli di cui viene tenuta traccia in batch esistano e vengano utilizzati durante il processo di fatturazione.

Se per i prodotti sono disponibili numeri di batch validi, questi ultimi vengono utilizzati nel processo di fatturazione degli ordini cliente e in quello di fatturazione degli stessi ordini dalla registrazione rendiconti. In caso contrario, il processo di fatturazione degli ordini cliente non può essere registrato e l'utente POS riceve un messaggio di errore. A questo punto nella registrazione rendiconti si verifica un errore. Questo stato di errore si verifica anche quando per i prodotti è stato attivato l'inventario negativo.

I miglioramenti apportati in Retail 10.0.4 e versioni successive garantiscono che, qualora l'inventario negativo sia stato attivato per gli articoli di cui viene tenuta traccia in batch, la fatturazione degli ordini cliente eseguita tramite la registrazione rendiconti non venga bloccata per tali articoli se il valore di inventario è pari a 0 (zero) o se un numero batch non è disponibile. Quando i numeri batch non sono disponibili, la nuova funzionalità utilizza un ID batch predefinito per le righe di vendita.

Per definire l'ID batch predefinito utilizzato per gli ordini cliente, nella scheda **Ordini cliente** della pagina **Parametri di commercio** impostare il campo **ID batch predefinito** nella Scheda dettaglio **Ordine**.

Per definire l'ID batch utilizzato per la fatturazione degli ordini cliente tramite la registrazione rendiconti, nella scheda **Registrazione** della pagina **Parametri di commercio** impostare il campo **ID batch predefinito** nella Scheda dettaglio **Aggiorna inventario**.

> [!NOTE]
> Questa funzionalità è disponibile solo quando i processi di magazzino avanzati sono attivati per il magazzino e gli articoli del punto vendita. In una versione successiva, la funzionalità sarà supportata anche per scenari in cui la gestione avanzata magazzino non viene utilizzata.

> [!NOTE]
> Il supporto per una migliore gestione degli articoli di cui viene tenuta traccia in batch durante la registrazione dei rendiconti per scenari diversi dalla gestione avanzata magazzino è stato introdotto in Retail versione 10.0.5.
