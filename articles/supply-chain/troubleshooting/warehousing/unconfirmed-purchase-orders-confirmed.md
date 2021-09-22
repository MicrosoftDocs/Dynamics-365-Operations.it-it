---
title: L'attività di aggiornamento delle ricevute dei prodotti conferma gli ordini non confermati
description: Dopo aver eseguito Aggiorna entrate prodotti, il sistema conferma gli ordini non confermati con stato Registrato. Scopri la funzione che risolve questo problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 171a978efc6b55b92f429381e72036cb1b3296c6
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476733"
---
# <a name="unconfirmed-purchase-orders-are-confirmed-after-running-update-product-receipts"></a>Gli ordini fornitore non confermati vengono confermati dopo l'esecuzione di Aggiorna entrate prodotti

## <a name="symptoms"></a>Sintomi

Dopo aver eseguito l'attività periodica *Aggiorna entrate prodotti*, il sistema conferma automaticamente gli ordini fornitore non confermati con stato di transazione di magazzino *Registrato*.

## <a name="resolution"></a>Risoluzione

Una nuova funzione di gestione del carico in entrata, *Entrata in eccesso di quantità di carico*, risolve questo problema. Per attivare questa funzionalità andare all'area di lavoro [Gestione funzionalità](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) e attivare le seguenti funzionalità in questo ordine:

1. Associa operazioni di magazzino ordine fornitore con carico
2. Entrata in eccesso di quantità di carico

Per ulteriori informazioni, vedere [Registrare le quantità di prodotto registrate rispetto a ordini fornitore](/dynamics365/supply-chain/warehousing/inbound-load-handling).
