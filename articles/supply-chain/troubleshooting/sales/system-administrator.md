---
title: Gli amministratori di sistema non possono annullare le sospensioni degli ordini perché non sono autorizzati
description: Gli amministratori di sistema non possono annullare le sospensioni degli ordini perché non sono autorizzati.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026660"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a>Gli amministratori di sistema non possono annullare le sospensioni degli ordini perché non sono autorizzati

Numero KB: 4614642

## <a name="symptoms"></a>Sintomi

Gli amministratori di sistema non possono annullare le sospensioni degli ordini cliente a meno che non dispongano del ruolo specifico assegnato nel codice di sospensione degli ordini.

## <a name="resolution"></a>Risoluzione

L'accesso ad alcune operazioni, come la cancellazione delle sospensioni degli ordini cliente, è determinato dall'impostazione di criteri aziendali. Gli amministratori di sistema in genere non sono autorizzati a eseguire operazioni di questo tipo. 

Più spesso, l'accesso per eseguire un'attività specifica è regolato da criteri aziendali e solo specifiche persone di un'organizzazione sono autorizzate a eseguire tale attività. Gli esempi includono approvazioni che sono il risultato di approvazioni del flusso di lavoro e attività specifiche che sono il risultato di una configurazione del flusso di lavoro.

Sebbene nessun flusso di lavoro sia associato alle sospensioni degli ordini, il principio è simile. Un ruolo rilevante designa il gruppo specifico di persone in un'organizzazione che hanno il diritto di annullare le sospensioni degli ordini. Questo diritto non dovrebbe essere necessariamente concesso a tutti gli amministratori, perché tale approccio viola i criteri aziendali definiti.
