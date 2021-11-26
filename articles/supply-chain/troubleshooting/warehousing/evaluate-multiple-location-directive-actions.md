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
ms.openlocfilehash: ea265166902f85c2c09cae08ee6de5cd7094e1b4
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778404"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>L'opzione Più unità di stockkeeping non valuta le azioni per direttive di più ubicazioni

## <a name="symptoms"></a>Sintomi

Le direttive di ubicazione del tipo di ordine di lavoro *Ordini cliente* e il tipo di lavoro *Stoccaggio* non valutano più azioni della direttiva di ubicazione quando l'opzione **Più SKU** è selezionata. Viene valutata solo la prima azione della direttiva di ubicazione.

## <a name="resolution"></a>Risoluzione

Una nuova funzionalità, *Valuta tutte le azioni per le direttive di ubicazione per più SKU*, è stato aggiunta nella versione 10.0.15 (vedere [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Questa funzionalità valuta tutte le azioni per le direttive di ubicazioni per più SKU. A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla o disabilitarla se necessario.
