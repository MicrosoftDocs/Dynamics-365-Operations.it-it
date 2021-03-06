---
title: Gestione migliorata degli articoli di cui viene tenuta traccia in batch
description: In questo argomento vengono descritti i miglioramenti apportati alla gestione dei batch di articoli di cui viene tenuta traccia durante il processo di registrazione dei rendiconti.
author: josaw1
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 2453ed711d47e062c82d3888ff471b770b5bb2ef
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799711"
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]