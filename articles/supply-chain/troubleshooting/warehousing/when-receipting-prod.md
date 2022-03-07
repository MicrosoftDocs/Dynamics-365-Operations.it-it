---
title: Una sola etichetta viene stampata per più intestazioni lavoro su un unico scontrino
description: Una sola etichetta viene stampata per più intestazioni lavoro su un unico scontrino.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026642"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Una sola etichetta viene stampata per più intestazioni lavoro su un unico scontrino

Numero KB: 4614667

## <a name="symptoms"></a>Sintomi

Molteplici intestazioni lavoro vengono create per la stessa targa di destinazione come parte di un singolo evento di ricezione dell'app di magazzino. Tuttavia, solo un'etichetta della targa viene stampata al ricevimento del prodotto.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto.

Nella progettazione corrente, viene sempre generata una singola etichetta di targa, indipendentemente dal numero di combinazioni di intestazioni lavoro e righe lavoro esistenti. L'etichetta generata include le informazioni per una sola combinazione.

Per risolvere questo problema, assicurati che la creazione dell'intestazione lavoro sia sempre mappata a una sola targa di destinazione.
