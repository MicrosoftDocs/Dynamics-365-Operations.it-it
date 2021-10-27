---
title: Miglioramenti delle prestazioni di pulizia della cronologia delle vendite
description: Questo argomento descrive la funzionalità di miglioramento delle prestazioni di pulizia della cronologia delle vendite e come abilitarla.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 563ac90dc8c037066b8ccd6d8986e089a66245af
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "7641468"
---
# <a name="saleshistorycleanupperformanceimprovements"></a>Miglioramenti delle prestazioni di pulizia della cronologia delle vendite

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Il processo batch periodico di **pulizia della cronologia delle vendite** può richiedere molto tempo se eseguito raramente in ambienti con un volume elevato di aggiornamenti delle vendite. In queste situazioni, la funzionalità *Miglioramenti delle prestazioni di pulizia della cronologia delle vendite* può aiutare a ridurre la durata dell'esecuzione e migliorare l'affidabilità.

La funzione migliora il lavoro di pulizia esistente nei seguenti modi:

- Suddivide la pulizia in batch (è possibile modificare la dimensione del batch tramite personalizzazioni).
- Funzionerà per un massimo di 2 ore (è possibile modificare la durata tramite personalizzazioni).
- Ove possibile, le funzionalità del database verranno sfruttate per ridurre al minimo il blocco ed evitare di unire tabelle transazionali durante la pulizia.

Dopo aver abilitato la funzionalità, il lavoro in batch **pulizia della cronologia degli aggiornamenti delle vendite** (**Vendite e marketing \> Attività periodo \> Pulizia \> Pulizia della cronologia degli aggiornamenti delle vendite**) verrà eseguito come prima, ma con prestazioni migliori per un massimo di 2 ore. Ciò significa che potrebbe essere necessario eseguirlo più volte per ripulire tutti i dati per un intervallo di tempo di conservazione specifico.

## <a name="turn-on-the-saleshistorycleanupperformanceimprovements-feature"></a>Abilita la funzionalità di miglioramento delle prestazioni della pulizia della cronologia delle vendite

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Vendite e marketing*
- **Nome funzionalità:** *Miglioramenti delle prestazioni di pulizia della cronologia delle vendite*
