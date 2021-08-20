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
ms.openlocfilehash: cf307964a07c2b69eb5e4ef2cf9dc094482736d0970e333e84f674c9be6331c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740529"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Una sola etichetta viene stampata per più intestazioni lavoro su un unico scontrino

Numero KB: 4614667

## <a name="symptoms"></a>Sintomi

Molteplici intestazioni lavoro vengono create per la stessa targa di destinazione come parte di un singolo evento di ricezione dell'app di magazzino. Tuttavia, solo un'etichetta della targa viene stampata al ricevimento del prodotto.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto.

Nella progettazione corrente, viene sempre generata una singola etichetta di targa, indipendentemente dal numero di combinazioni di intestazioni lavoro e righe lavoro esistenti. L'etichetta generata include le informazioni per una sola combinazione.

Per risolvere questo problema, assicurati che la creazione dell'intestazione lavoro sia sempre mappata a una sola targa di destinazione.
