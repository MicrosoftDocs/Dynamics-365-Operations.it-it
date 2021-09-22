---
title: Valuta tutte le azioni per direttive di ubicazione multi-SKU
description: Una nuova funzionalità è stata aggiunta per valutare tutte le azioni per direttive di ubicazioni di più unità di stockkeeping. Questa pagina illustra come attivare tale funzionalità.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 45995ed6f051cdf6be2b2985ff0e2cb1decf4cf0
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476751"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>L'opzione Più unità di stockkeeping non valuta le azioni per direttive di più ubicazioni

## <a name="symptoms"></a>Sintomi

Le direttive di ubicazione del tipo di ordine di lavoro *Ordini cliente* e il tipo di lavoro *Stoccaggio* non valutano più azioni della direttiva di ubicazione quando l'opzione **Più SKU** è selezionata. Viene valutata solo la prima azione della direttiva di ubicazione.

## <a name="resolution"></a>Risoluzione

Una nuova funzionalità, *Valuta tutte le azioni per le direttive di ubicazione per più SKU*, è stato aggiunta nella versione 10.0.15 (vedere [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Questa funzionalità valuta tutte le azioni per le direttive di ubicazioni per più SKU. Se è necessaria questa funzione, usare [Gestione delle funzionalità](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) per attivarla.
