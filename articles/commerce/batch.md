---
title: Gestione migliorata degli articoli di cui viene tenuta traccia in batch
description: In questo argomento viene descritta la gestione migliorata dei batch di articoli di cui viene tenuta traccia durante il processo di registrazione dei rendiconti in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/09/2021
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
ms.openlocfilehash: 513b6ca84fa71e851a5a3e4275e0b6572789e1eb
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485785"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Gestione migliorata degli articoli di cui viene tenuta traccia in batch

[!include [banner](includes/banner.md)]

In questo argomento viene descritta la gestione migliorata dei batch di articoli di cui viene tenuta traccia durante il processo di registrazione dei rendiconti in Microsoft Dynamics 365 Commerce.

Nei POS di Dynamics 365 Commerce i numeri batch non possono essere acquisiti per gli articoli di cui viene tenuta traccia in batch al momento della vendita. Per configurazioni specifiche, tuttavia, quando le vendite vengono registrate in Commerce headquarters tramite ordini cliente o registrazione rendiconti, Commerce prevede che i numeri batch validi per gli articoli di cui viene tenuta traccia in batch esistano e vengano utilizzati durante il processo di fatturazione.

Se per i prodotti sono disponibili numeri di batch validi, questi ultimi vengono utilizzati nel processo di fatturazione degli ordini cliente e in quello di fatturazione degli stessi ordini dalla registrazione rendiconti. Se i numeri di batch validi non sono disponibili per i prodotti, il processo di fatturazione dell'ordine cliente non può essere registrato e l'utente POS riceve un messaggio di errore. La registrazione del rendiconto passa quindi in uno stato di errore, anche se è stato attivato l'inventario negativo per i prodotti.

I miglioramenti apportati a Commerce garantiscono che, qualora l'inventario negativo sia stato attivato per gli articoli di cui viene tenuta traccia in batch, la fatturazione degli ordini cliente eseguita tramite la registrazione rendiconti non venga bloccata per tali articoli se il valore di inventario è pari a 0 (zero) o se un numero batch non è disponibile. Quando i numeri batch non sono disponibili, la funzionalità migliorata utilizza un ID batch predefinito per le righe di vendita.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>Definire l'ID batch predefinito utilizzato per gli ordini cliente

Per definire l'ID batch predefinito utilizzato per gli ordini cliente, effettuare le seguenti operazioni.

1. In Commerce headquarters accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di commercio**.
1. Nella Scheda dettaglio **Ordine** della scheda **Ordini cliente** immettere un valore nel campo **ID batch predefinito**.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>Definire l'ID batch predefinito utilizzato per la fatturazione degli ordini cliente tramite la registrazione del rendiconto

Per definire l'ID batch predefinito utilizzato per la fatturazione degli ordini cliente tramite la registrazione del rendiconto, effettuare le seguenti operazioni.

1. In Commerce headquarters accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di commercio**.
1. Nella Scheda dettaglio **Aggiornamento dell'inventario** della scheda **Registrazione** immettere un valore nel campo **ID batch predefinito**.

> [!NOTE]
> - La funzionalità ID batch predefinito è disponibile solo quando i processi di magazzino avanzati sono abilitati per il magazzino e gli articoli del punto vendita. In una versione successiva, la funzionalità sarà supportata anche per scenari in cui la gestione avanzata magazzino non viene abilitata.
> - Il supporto per una migliore gestione degli articoli di cui viene tenuta traccia in batch durante la registrazione dei rendiconti per scenari diversi dalla gestione avanzata magazzino è stato introdotto in Commerce versione 10.0.5.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
