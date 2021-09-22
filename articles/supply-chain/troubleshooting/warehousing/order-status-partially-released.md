---
title: Lo stato dell'ordine rimane Parzialmente rilasciato dopo la fatturazione
description: In alcuni casi, lo stato di un ordine cliente rimane Parzialmente rilasciato anche dopo la fatturazione dell'ordine. Questa pagina spiega i motivi e una possibile soluzione.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8bfe7ecfd4beb6e77e8dd1e23ccd896d067bdb51
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476778"
---
# <a name="order-status-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Lo stato dell'ordine rimane Parzialmente anche rilasciato dopo la fatturazione dell'ordine cliente

## <a name="symptoms"></a>Sintomi

Un ordine cliente è un ordine di consegna, ma uno o più articoli hanno una modalità di consegna diversa. Dopo che l'ordine è stato fatturato, ha ancora lo stato di rilascio *Parzialmente rilasciato*.

Ad esempio, un ordine cliente ha due articoli: uno per la consegna e uno per il ritiro. Sia la consegna che il ritiro sono stati effettuati. Pertanto, entrambe le righe sono state fatturate. Tuttavia, lo stato di rilascio è ancora mostrato come *Parzialmente rilasciato*, che è fuorviante.

## <a name="workaround"></a>Soluzione alternativa

Lo stato di rilascio si applica solo alle righe ordine in cui gli articoli sono abilitati per la gestione del magazzino. Pertanto, lo stato di rilascio rimane *Parzialmente rilasciato* in questo scenario. Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. È possibile aggiungere un'estensione come parte del documento di trasporto e del processo di fatturazione per aggiornare lo stato di rilascio.
