---
title: Il report Costi indiretti in esecuzione include gli ordini di produzione eliminati
description: Il report Costi indiretti in esecuzione presenta informazioni sugli ordini di produzione che sono stati parzialmente elaborati e successivamente eliminati.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026644"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>Il report Costi indiretti in esecuzione include gli ordini di produzione eliminati

Numero KB: 4612748

## <a name="symptoms"></a>Sintomi

Il report **Costi indiretti in esecuzione** presenta informazioni sugli ordini di produzione che sono stati parzialmente elaborati e successivamente eliminati.

## <a name="resolution"></a>Risoluzione

Quando storni un ordine di produzione, annulli anche tutte le transazioni di tale ordine di produzione. Quando elimini l'ordine di produzione, le tabelle del giornale di registrazione secondario e la contabilità generale mantengono tutte le transazioni ad esso correlate. I report mostreranno le transazioni nelle tabelle del giornale di registrazione secondario. Per l'ordine di produzione specifico, il valore netto dovrebbe essere 0,00.
