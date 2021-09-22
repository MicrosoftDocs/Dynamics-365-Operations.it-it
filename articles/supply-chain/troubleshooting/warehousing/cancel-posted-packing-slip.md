---
title: Impossibile annullare un documento di trasporto dopo che è stato registrato da un ordine
description: Quando i processi di prelievo e spedizione sono abilitati per WMS, non è possibile annullare un documento di trasporto dopo che è stato registrato da un ordine cliente. Questa pagina offre una soluzione alternativa.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d20e66e2721560b8409eb63c3546a79adc188c7c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476821"
---
# <a name="cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Impossibile annullare un documento di trasporto dopo che è stato registrato da un ordine cliente

## <a name="symptoms"></a>Sintomi

Quando i processi di prelievo e spedizione sono abilitati per la gestione avanzata del magazzino (WMS), non è possibile annullare un documento di trasporto dopo che è stato registrato da un ordine cliente.

## <a name="resolution"></a>Risoluzione

Per correggere i documenti di trasporto registrati per gli articoli abilitati per WMS, la registrazione deve avvenire dal carico, non dall'ordine. Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità.  

In generale, un ordine cliente prelevato e spedito tramite i processi di gestione del magazzino può essere aggiornato dal documento di trasporto dal carico o dalla spedizione e dal documento dell'ordine cliente stesso. Tuttavia, se si aggiorna l'ordine cliente dal documento dell'ordine cliente, lo storno del documento di trasporto non può ancora essere eseguito dal carico o dall'ordine cliente. Pertanto, si consiglia di utilizzare la registrazione della bolla di accompagnamento dal carico. In questo caso verrà abilitato lo storno che deve essere eseguito dal carico.
