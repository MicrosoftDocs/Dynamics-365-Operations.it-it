---
title: Visualizzazione di spese per un articolo prodotto
description: I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante.
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: d65e3c4220c05d143d57413749ef805fd58dcf08
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813269"
---
# <a name="display-charges-for-a-manufactured-item"></a>Visualizzazione di spese per un articolo prodotto

[!include [banner](../includes/banner.md)]

I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante.

È possibile visualizzare l'importo calcolato delle spese di un articolo con i costi unitari dell'articolo. Tuttavia, le spese vengono talvolta visualizzate come due campi separati e non vengono incluse nei costi unitari dell'articolo. Quando le spese vengono visualizzate come campi separati, un campo indica l'importo totale delle varie e l'altro le dimensioni lotto di determinazione costi utilizzate per ammortizzare l'importo. Nella Pagina Prezzo articolo, ad esempio, le spese vengono visualizzate come due campi separati. Tuttavia, nella pagina Completo viene visualizzato il costo totale dell'articolo per unità e i costi ammortizzati vengono inclusi nei costi unitari.

Le spese per un articolo prodotto vengono sempre incluse nel costo unitario dell'articolo ai fini dei costi standard, mentre possono essere incluse facoltativamente nel caso di costi pianificati. La decisione di includere le spese nel costo di un articolo prodotto viene applicata da criteri in una versione di determinazione costi. Quando si attiva il record di costo di un articolo, le spese vengono aggiornate per le informazioni di costo di base dell'articolo visualizzate nella pagina Prezzo articolo. Le spese vengono visualizzate come due campi separati e non vengono incluse nel costo unitario dell'articolo. Le informazioni di costo di base dell'articolo vengono aggiornate a ogni attivazione, anche se quest'ultima riguarda siti diversi. Tali informazioni devono pertanto essere considerate come informazioni di riferimento.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]