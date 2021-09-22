---
title: Lacune funzionali tra il valore dell'inventario/i report di aging e le relative versioni di archiviazione
description: Lacune funzionali tra il valore dell'inventario/i report di aging e le relative versioni di archiviazione
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a72e2d32e755e137cebbc0bf7afb0bed08fb93f2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476792"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>Lacune funzionali tra il valore dell'inventario/i report di aging e le relative versioni di archiviazione

Le funzionalità [archiviazione del report di aging dell'inventario](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage.md) e il [report sull'archiviazione valori di magazzino](/dynamics365/supply-chain/cost-management/inventory-value-report-storage.md) consentono a Supply Chain Management di visualizzare grandi volumi di transazioni di magazzino. In ogni caso, i risultati del report vengono salvati per l'esplorazione e l'esportazione, a differenza delle versioni non di archiviazione di questi report. Tuttavia, alcune funzionalità presenti nelle versioni non di archiviazione di questi report non esistono nelle versioni di archiviazione. Le seguenti sottosezioni riepilogano le differenze e forniscono soluzioni alternative.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>I report di archiviazione non includono i totali parziali, anche se sono abilitati nel layout del report

I totali parziali possono causare problemi durante l'esportazione del risultato, soprattutto se gli utenti modificano la sequenza del record.

Per controllare i subtotali, è possibile esportare il risultato in Microsoft Excel. In alternativa, se vuoi controllare i totali parziali in Supply Chain Management, utilizza [Gestione funzionalità](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitare le funzionalità *Nuovo controllo griglia* e *Raggruppamento in griglie* che forniscono un modo molto più flessibile per vedere il totale parziale di qualsiasi gruppo per colonna. Per ulteriori informazioni, vedere [Funzionalità di griglia](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities.md).

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Il report di archiviazione valori di magazzino non supporta le informazioni sul conto di contabilità generale

È possibile eseguire il bilancio di prova per ottenere il saldo dei conti inventario e confrontarlo con il report **Archiviazione valori di magazzino**.
