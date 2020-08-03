---
title: Spostamento della sequenza dei costi di fallback medi
description: Questo argomento fornisce informazioni sulle sequenze dei costi di fallback per lo spostamento di calcoli medi in Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 0538701588b9c71dff4c538711606913a359de6a
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597386"
---
# <a name="moving-average-fallback-cost-sequence"></a>Spostamento della sequenza dei costi di fallback medi

Una modalità per calcolare il costo dell'inventario è costituito dall'utilizzo di una _media mobile_. Ad ogni articolo di inventario possono essere associati fino a tre valori di costo:

- **Ultimo rilascio** - L'ultimo costo di transazione viene assegnato prima che l'inventario diventi negativo
- **Costo attivo** - È l'ultimo costo attivato in una versione di determinazione dei costi
- **Prezzo dell'articolo** - È Il costo specificato per il prodotto rilasciato

Per determinare quale di questi valori di costo deve essere utilizzato nei calcoli della media mobile, il sistema utilizza la _sequenza dei costi di fallback_ per stabilire l'ordine di preferenza per i valori. Se il valore di costo preferito non è disponibile, il sistema utilizza il valore preferito successivo e così via.

Nelle versioni precedenti di Microsoft Dynamics 365 Supply Chain Management, il sistema utilizzava una sequenza di costi di fallback fissa (_Ultimo rilascio - Costo attivo - Prezzo articolo_). Nella versione 10.0.11, questa sequenza è ancora la sequenza predefinita. Tuttavia, è anche possibile attivare una funzione che consente di selezionare tra tre sequenze di costi di fallback disponibili. Questa funzione può essere particolarmente utile per le organizzazioni che utilizzano regolarmente valori di inventario negativi.

Per rendere disponibile il selettore per la sequenza dei costi di fallback, è necessario usare [Gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare la funzione denominata _Spostamento della sequenza dei costi di fallback medi_.

Per selezionare la sequenza dei costi di fallback per i calcoli della media mobile, attenersi alla seguente procedura.

1. Aprire la pagina **Parametri**:
2. Nella scheda **Contabilità di magazzino**, nella sezione, **Media mobile** impostare la **Sequenza di costi di fallback** su uno dei seguenti valori:

    - **Ultimo rilascio - Costo attivo - Prezzo articolo** - Questa è la sequenza predefinita. È la stessa sequenza usata se la funzione _Spostamento della sequenza dei costi di fallback medi_ non è attivata.
    - **Costo attivo - Ultimo rilascio**
    - **Costo attivo - Prezzo dell'articolo** - Le organizzazioni potrebbero riscontrare problemi di prestazioni se utilizzano processi aziendali in cui l'inventario diventa regolarmente negativo e, allo stesso tempo, il volume delle transazioni è elevato. Questa impostazione può aiutare a mitigare questi problemi di prestazioni.

![Parametri di contabilità inventario](media/inventory-accounting-parameters.png "Parametri di contabilità inventario")
