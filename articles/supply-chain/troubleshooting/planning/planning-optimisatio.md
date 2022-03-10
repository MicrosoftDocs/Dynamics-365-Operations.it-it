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
ms.openlocfilehash: 94d569684a0bfa2398e98147b9b85531954f8d56748894034a048fa627230ef0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775509"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>Un ordine fornitore pianificato viene creato quando esiste un acquisto entro giorni negativi

Numero KB: 4614298

## <a name="symptoms"></a>Sintomi

Se il codice di copertura è *Min/Max*, Ottimizzazione pianificazione crea un ordine fornitore pianificato quando esiste un acquisto entro giorni negativi.

## <a name="resolution"></a>Risoluzione

Ottimizzazione pianificazione non supporta i giorni negativi. Tuttavia, garantisce sempre che gli ordini pianificati non vengano pianificati entro il lead time relativo alla data corrente. Ad esempio, il lead time di acquisto è di 10 giorni e un ordine fornitore dovrebbe arrivare otto giorni dopo la data odierna. In questo caso, l'ordine fornitore verrà utilizzato come offerta per la domanda che è di cinque giorni dalla data corrente.

Pertanto, ti consigliamo di modificare i lead time per coprire tutti (o quasi tutti) gli scenari.
