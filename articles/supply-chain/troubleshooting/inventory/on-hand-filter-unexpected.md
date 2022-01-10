---
title: Il riquadro dei filtri nella pagina elenco Elenco scorte disponibili non funziona come previsto.
description: I filtri nel riquadro dei filtri nella pagina "Elenco scorte disponibili" non filtra i risultati come previsto.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 2b2b233e22378c8710a63dce83d168bfd89eba7f
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920500"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Il riquadro dei filtri nella pagina elenco Elenco scorte disponibili non funziona come previsto.

## <a name="symptoms"></a>Sintomi

I filtri nel riquadro dei filtri nella pagina **Elenco scorte disponibili** non filtra i risultati come previsto.

## <a name="resolution"></a>Risoluzione

La pagina **Elenco scorte disponibili** è assemblata da una tabella dettagliata di scorte disponibili che include tutte le dimensioni disponibili. Tuttavia, l'elenco in questa pagina è un riepilogo. Pertanto, potrebbe combinare le righe dalla tabella di origine aggregando i valori in base alle dimensioni visualizzate.

I filtri configurati nel riquadro dei filtri si applicano alla tabella di origine, non all'elenco aggregato. Questo comportamento a volte può produrre risultati imprevisti, come mostrato in [questi esempi](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples).

Comunque, i [filtri forniti nella griglia](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *si applicano* all'elenco aggregato. Questi filtri includono sia un filtro rapido nella parte superiore della griglia sia il filtro per ciascuna intestazione di colonna.
