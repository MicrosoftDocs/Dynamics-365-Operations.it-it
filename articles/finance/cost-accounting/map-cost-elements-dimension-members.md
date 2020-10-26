---
title: Eseguire il mapping dei membri di dimensione elemento di costo a un set comune di membri di dimensione
description: Mappando membri delle dimensioni elemento di costo diversi a un set comune di membri delle dimensioni elemento di costo, si uniscono i dati in un formato comune per scopi di analisi.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c6a9618a762d3af840beb05d86518b3588118e80
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976357"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Eseguire il mapping dei membri di dimensione elemento di costo a un set comune di membri di dimensione

[!include [banner](../includes/banner.md)]

Mappando membri delle dimensioni elemento di costo diversi a un set comune di membri delle dimensioni elemento di costo, si uniscono i dati in un formato comune per scopi di analisi.

Se si è una società globale conforme ai requisiti contabili statutari, è possibile che si utilizzino più piani dei conti. Quando si importano i membri delle dimensioni elemento di costo da piani dei conti diversi, è possibile finire con una combinazione di conti. Tuttavia, questi conti potrebbero effettivamente avere la stessa natura e può essere opportuno analizzare e allocare i relativi costi utilizzando un formato comune.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Mappare i membri delle dimensioni elemento di costo a un formato comune
Nel seguente esempio viene illustrato come un controller di costi può creare una nuova dimensione elemento di costo nella contabilità industriale che mappa i membri delle dimensioni elemento di costo dalla struttura del piano dei conti negli Stati Uniti e dalla struttura del piano dei conti francese a un set comune di membri delle dimensioni elemento di costo. È quindi possibile utilizzare il set comune dei membri delle dimensioni elemento di costo per analizzare i dati sui costi delle due persone giuridiche in un movimento CoGe di contabilità industriale.

| Origine: piano dei conti statunitense                                          | Origine: piano dei conti francese                                          | Nuovo set comune di membri delle dimensioni elemento di costo                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Membri delle dimensioni elemento di costo importati dal piano dei conti statunitense | Membri delle dimensioni elemento di costo importati dal piano dei conti francese | Mapping dei membri delle dimensioni elemento di costo statunitensi e francesi a un set comune |
| 5001: Vendite                                                           | 5001: Vendite e annunci                                               | 5000: Vendite e annunci                                             |
| 5030: Annunci                                                     | 6390: Acquisti scorte\*                                                    | 7000: Spese di pulizia                                                 |
| 7001: Spese di pulizia                                               | 7001: Spesa di viaggio                                                      | 7001: Spese di viaggio                                                   |

\*Il membro della dimensione elemento di costo francese Acquisto scorte non è mappato.

## <a name="currency-conversion"></a>Conversione valutaria
I vari piani dei conti utilizzati possono essere impostati per l'utilizzo di valute diverse. In questo caso, assicurarsi di specificare una conversione valutaria, in modo che i dati relativi ai costi vengano elaborati con la valuta corretta, come definito nel conto CoGe di contabilità industriale in cui i membri delle dimensioni elemento di costo vengono utilizzati. Nell'esempio precedente, se il dollaro statunitense (USD) viene utilizzato nel conto CoGe di contabilità industriale, è necessario creare una conversione valutaria da USD a EUR (euro) per elaborare le transazioni per i membri delle dimensioni elemento di costo mappati.

## <a name="update-mappings-at-any-time"></a>Aggiornare i mapping in qualsiasi momento
È possibile aggiornare in qualsiasi momento le definizioni di mapping per una dimensione elemento di costo. Poiché i mapping non dipendono dalle date, le modifiche vengono applicate alla successiva elaborazione delle transazioni costi o esecuzione di calcoli dei costi.



