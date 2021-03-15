---
title: Risolvere i problemi dei rilasci parziali e delle spedizioni parziali
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano rilasci parziali e spedizioni parziali in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 33323a8aed44cf19db6c2c937abcb09f7e05b6c1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993954"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a>Risolvere i problemi dei rilasci parziali e delle spedizioni parziali

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano rilasci parziali e spedizioni parziali in Microsoft Dynamics 365 Supply Chain Management.

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Lo stato di rilascio di un ordine cliente rimane Rilasciato parzialmente anche dopo che l'ordine cliente è stato fatturato.

### <a name="issue-description"></a>Descrizione del problema

Un ordine cliente è un ordine di consegna, ma uno o più articoli hanno una modalità di consegna diversa. Dopo che l'ordine è stato fatturato, ha ancora lo stato di rilascio *Parzialmente rilasciato*.

Ad esempio, un ordine cliente ha due articoli: uno per la consegna e uno per il ritiro. Sia la consegna che il ritiro sono stati effettuati. Pertanto, entrambe le righe sono state fatturate. Tuttavia, lo stato di rilascio è ancora mostrato come *Parzialmente rilasciato*, che è fuorviante.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Lo stato di rilascio si applica solo alle righe ordine in cui gli articoli sono abilitati per la gestione del magazzino. Pertanto, lo stato di rilascio rimane *Parzialmente rilasciato* in questo scenario. Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. È possibile aggiungere un'estensione come parte del documento di trasporto e del processo di fatturazione per aggiornare lo stato di rilascio.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]