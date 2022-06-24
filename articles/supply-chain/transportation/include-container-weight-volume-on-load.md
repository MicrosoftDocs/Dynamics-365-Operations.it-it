---
title: Includere peso e volume del contenitore nel carico
description: In questo articolo viene descritto come impostare e utilizzare la funzionalità che consente di includere peso e volume dei contenitori nei carichi.
author: Weijiesa
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66dc84171f8b175476f37f736489d3d83cacfe57
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897402"
---
# <a name="include-container-weight-and-volume-on-load"></a>Includere peso e volume del contenitore nel carico

[!include [banner](../includes/banner.md)]

La funzionalità che consente di includere peso e volume dei contenitori in un carico fornisce una chiara rappresentazione del peso e del volume totali dei contenitori e degli articoli in un carico.

Un carico contiene una o più spedizioni e tali spedizioni includono articoli distinti che appartengono a uno o più ordini cliente. Gli articoli sono immagazzinati in un contenitore e i contenitori vengono caricati in un carico. Anche gli articoli al di fuori di un contenitore possono far parte di un carico. In base a queste condizioni, il sistema calcola i valori relativi a peso e volume del carico prendendo in considerazione peso e volume dei contenitori e degli articoli.

Se i valori calcolati non sono precisi, è possibile rettificarli immettendo i valori effettivi del peso e del volume del carico. I valori per il peso e il volume sono utilizzati nei processi di gestione trasporto. Ad esempio, i valori sono utilizzati nella tariffa workbench del ciclo di lavorazione, in quanto consentono di definire la tariffa e il ciclo di lavorazione per i carichi, nonché per i metodi di pagamento del trasporto e per il check-in del conducente.

## <a name="where-it-applies"></a>Dove si applica

La funzionalità per l'importazione di peso e volume dei contenitori in un carico viene applicata ai processi di gestione trasporto, ad esempio la tariffa workbench del ciclo di lavorazione, i metodi di pagamento del trasporto e il check-in del conducente.

## <a name="how-it-is-set-up"></a>Come si imposta

Il numero di contenitori da prendere in considerazione per un carico viene calcolato in base al peso e al volume del contenitore e alla percentuale di utilizzo del contenitore.

-   Per impostare peso e volume di un contenitore, fare clic su **Gestione magazzino** \> **Impostazione** \> **Contenitori** \> **Tipi di contenitore**.

-   Per impostare la percentuale di utilizzo del contenitore, fare clic su **Gestione magazzino** \> **Impostazione** \> **Contenitori** \> **Gruppo di contenitori** e immettere un valore nel campo **Percentuale di utilizzo contenitore**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]