---
title: Scorte disponibili non considerate per gli articoli superiori al batch
description: Alcuni modelli di assegnazione non considerano le scorte disponibili correnti per gli articoli superiori al batch. Il numero batch o di serie deve essere specificato nell'ordine della domanda.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: df5642b32f5e053144230eab3dbcf633f526279a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476768"
---
# <a name="slotting-templates-dont-consider-on-hand-inventory-for-batch-above-items"></a>I modelli di assegnazione non considerano le scorte disponibili per gli articoli superiori al batch

## <a name="symptoms"></a>Sintomi

I modelli di assegnazione che hanno il criterio di assegnazione *Considera scorte*, non considerano le scorte disponibili correnti per gli articoli *batch-above*. Lo considerano solo se il numero di batch è specificato nella riga dell'ordine cliente.

Tuttavia, quando usi articoli *batch-below*, le scorte disponibili correnti sono considerate come previsto.

Per ulteriori informazioni, vedi [Assegnazione magazzino](/dynamics365/supply-chain/warehousing/warehouse-slotting).

## <a name="resolution"></a>Risoluzione

L'intestazione del modello di assegnazione può essere definita per la strategia della domanda *Ordinato*, *Prenotato*, o *Rilasciato*. Per la strategia della domanda *Ordinato* si applicano gli stessi requisiti della gerarchia di prenotazione che si applicano alla prenotazione o al rilascio ai processi di magazzino. Pertanto, per gli articoli che hanno gerarchie di prenotazione *batch-above* e *serial-below*, il batch o il numero di serie devono essere specificati nell'ordine di domanda (vendita o trasferimento).

In alternativa, la strategia della domanda *Prenotato* può essere utilizzata per selezionare il batch o il numero di serie prima che venga generata la domanda di assegnazione del magazzino.
