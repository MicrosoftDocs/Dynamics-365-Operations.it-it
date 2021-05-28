---
title: Un ordine fornitore pianificato viene creato quando esiste un acquisto entro giorni negativi
description: Se il codice di copertura è Min/Max, Ottimizzazione pianificazione crea un ordine fornitore pianificato quando esiste un acquisto entro giorni negativi.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026649"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>Un ordine fornitore pianificato viene creato quando esiste un acquisto entro giorni negativi

Numero KB: 4614298

## <a name="symptoms"></a>Sintomi

Se il codice di copertura è *Min/Max*, Ottimizzazione pianificazione crea un ordine fornitore pianificato quando esiste un acquisto entro giorni negativi.

## <a name="resolution"></a>Risoluzione

Ottimizzazione pianificazione non supporta i giorni negativi. Tuttavia, garantisce sempre che gli ordini pianificati non vengano pianificati entro il lead time relativo alla data corrente. Ad esempio, il lead time di acquisto è di 10 giorni e un ordine fornitore dovrebbe arrivare otto giorni dopo la data odierna. In questo caso, l'ordine fornitore verrà utilizzato come offerta per la domanda che è di cinque giorni dalla data corrente.

Pertanto, ti consigliamo di modificare i lead time per coprire tutti (o quasi tutti) gli scenari.
