---
title: Il giornale di registrazione dell'inventario è bloccato e il processo batch del flusso di lavoro non funziona
description: Uno dei giornali di registrazione magazzino è bloccato da un'operazione e non viene rilasciato
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
ms.openlocfilehash: 8b21ec2e2b3b8546dcb138422c5540053392c179
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476741"
---
# <a name="your-inventory-journal-is-locked-and-the-workflow-batch-job-doesnt-work"></a>Il giornale di registrazione dell'inventario è bloccato e il processo batch del flusso di lavoro non funziona

## <a name="symptoms"></a>Sintomi

Uno dei tuoi giornali di registrazione magazzino è bloccato da un'operazione e non viene rilasciato. Ad esempio, se si verifica un errore sconosciuto durante la registrazione (che è un'operazione di blocco del sistema), il giornale di registrazione potrebbe rimanere nello stato di blocco del sistema. In questo caso, il gestore dell'elemento di lavoro del flusso di lavoro genererà un errore mentre blocca la convalida.

## <a name="resolution"></a>Risoluzione

Accedi all'istanza di SQL Server per Supply Chain Management e verifica se **InventJournalTable.SystemBlocked** è impostato su *1*. In tal caso, accertati che il giornale di registrazione non sia in stato bloccato e quindi reimposta **InventJournalTable.SystemBlocked** su *0*.
