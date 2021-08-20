---
title: Panoramica degli oggetti assistenza
description: Gli oggetti assistenza sono i cespiti cliente e i prodotti per i quali è possibile prestare assistenza.
author: ShylaThompson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 161d17d14af6351409e2405ae104f2b87e363ce349dd9b8e26d2c14e5fb9fa14
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770170"
---
# <a name="service-objects-overview"></a>Panoramica degli oggetti assistenza

[!include [banner](../includes/banner.md)]

Gli oggetti assistenza sono i cespiti cliente e i prodotti per i quali è possibile prestare assistenza. A seconda del tipo di assistenza fornita, gli oggetti si distinguono in materiali e immateriali:

-  Gli oggetti materiali sono oggetti tangibili, ad esempio macchine o edifici, su cui è possibile effettuare assistenza costituita da attività concrete.

    Un oggetto assistenza tangibile può inoltre corrispondere a un articolo di tipo Assistenza creato nel modulo Dettagli prodotto rilasciato. A seconda del gruppo di dimensioni inventariali collegato all'articolo, è possibile creare un oggetto assistenza fino al di dettaglio che include il numero di serie dell'articolo. Questa funzionalità è utile nel caso in cui sia necessario tenere traccia dell'articolo esatto rappresentato dall'oggetto assistenza.

    Un oggetto assistenza materiale può inoltre essere un articolo non direttamente correlato alla produzione o alla supply chain della società. Ad esempio, un kit di strumenti utilizzato per le riparazioni in un ordine di assistenza può essere un oggetto assistenza non incluso nel magazzino. In questo caso, non registrarlo come articolo di magazzino.

-  Gli oggetti immateriali sono cose non fisiche, ad esempio un set di conti o un documento legale in cui è possibile eseguire un'attività di assistenza.

## <a name="example-of-an-intangible-service-object"></a>Esempio di un oggetto assistenza immateriale

La società A gestisce i record finanziari per diverse piccole imprese. Uno dei clienti della società A è la squadra di football locale, per cui la società A esegue la contabilità settimanale e il controllo annuale dei conti della società. I conti della società vengono impostati nel modulo Oggetti assistenza e vengono specificati come oggetto nel contratto di assistenza. Sono disponibili due righe del contratto di assistenza per l'oggetto. La riga 1 è la contabilità settimanale con un intervallo settimanale assegnato alla riga, e la riga 2 è il controllo annuale con un intervallo annuale assegnato.

## <a name="related-topics"></a>Argomenti correlati

[Creare oggetti assistenza](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]