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
ms.openlocfilehash: 817802f1f2ad3ab07f35c28d3e833a14cd02cf8b9705c576325dc83933a0c6de
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751771"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>Il report Costi indiretti in esecuzione include gli ordini di produzione eliminati

Numero KB: 4612748

## <a name="symptoms"></a>Sintomi

Il report **Costi indiretti in esecuzione** presenta informazioni sugli ordini di produzione che sono stati parzialmente elaborati e successivamente eliminati.

## <a name="resolution"></a>Risoluzione

Quando storni un ordine di produzione, annulli anche tutte le transazioni di tale ordine di produzione. Quando elimini l'ordine di produzione, le tabelle del giornale di registrazione secondario e la contabilità generale mantengono tutte le transazioni ad esso correlate. I report mostreranno le transazioni nelle tabelle del giornale di registrazione secondario. Per l'ordine di produzione specifico, il valore netto dovrebbe essere 0,00.
