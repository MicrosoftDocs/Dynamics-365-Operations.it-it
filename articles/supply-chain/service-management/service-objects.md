---
title: Panoramica oggetti di servizio
description: In questo articolo viene fornita una panoramica di come utilizzare gli oggetti assistenza.
author: sorenva
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8150a94677fe38f4caa6f3e0b5fb5d1be5972eaf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862413"
---
# <a name="service-objects-overview"></a>Panoramica oggetti di servizio

[!include [banner](../includes/banner.md)]

Gli oggetti assistenza sono i cespiti cliente e i prodotti per i quali è possibile prestare assistenza. A seconda del tipo di assistenza fornita, gli oggetti si distinguono in materiali e immateriali:

-  Gli oggetti materiali sono oggetti tangibili, ad esempio macchine o edifici, su cui è possibile effettuare assistenza costituita da attività concrete.

    Un oggetto assistenza tangibile può inoltre corrispondere a un articolo di tipo Assistenza creato nel modulo Dettagli prodotto rilasciato. A seconda del gruppo di dimensioni inventariali collegato all'articolo, è possibile creare un oggetto assistenza fino al di dettaglio che include il numero di serie dell'articolo. Questa funzionalità è utile nel caso in cui sia necessario tenere traccia dell'articolo esatto rappresentato dall'oggetto assistenza.

    Un oggetto assistenza materiale può inoltre essere un articolo non direttamente correlato alla produzione o alla supply chain della società. Ad esempio, un kit di strumenti utilizzato per le riparazioni in un ordine di assistenza può essere un oggetto assistenza non incluso nel magazzino. In questo caso, non lo si registra come articolo di magazzino.

-  Gli oggetti immateriali sono cose non fisiche, ad esempio un set di conti o un documento legale in cui è possibile eseguire un'attività di assistenza.

## <a name="example-of-an-intangible-service-object"></a>Esempio di un oggetto assistenza immateriale

La società A gestisce i record finanziari per diverse piccole imprese. Uno dei clienti della società A è la squadra di football locale, per cui la società A esegue la contabilità settimanale e il controllo annuale dei conti della società. I conti della società vengono impostati nel modulo Oggetti assistenza e vengono specificati come oggetto nel contratto di assistenza. Sono disponibili due righe del contratto di assistenza per l'oggetto. La riga 1 è la contabilità settimanale con un intervallo settimanale assegnato alla riga, e la riga 2 è il controllo annuale con un intervallo annuale assegnato.

## <a name="related-articles"></a>Articoli correlati

[Creare oggetti assistenza](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]