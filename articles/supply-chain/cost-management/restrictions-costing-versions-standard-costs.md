---
title: Restrizioni per le versioni di determinazione costi per i costi standard
description: In questo articolo vengono elencate le restrizioni che sia applicano a una versione di determinazione costi per i costi standard.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5c00ae8952e2c80d97d039271a6f5c63e9a72f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867987"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Restrizioni per le versioni di determinazione costi per i costi standard

[!include [banner](../includes/banner.md)]

In questo articolo vengono elencate le restrizioni che sia applicano a una versione di determinazione costi per i costi standard. 

Le restrizioni seguenti aiutano a garantire la conformità ai principi di determinazione costi standard:

-  Le spese devono essere incluse nel costo di un articolo. Nel caso di un articolo prodotto, rappresentano i costi costanti ammortizzati nelle informazioni sulla distinta base (DBA) e sul ciclo di lavorazione. Pertanto, questi addebiti devono essere inclusi nel costo unitario. Nel caso di un articolo acquistato, vengono incluse anche nel costo unitario dell'articolo.

-  Il calcolo dei costi standard per un articolo prodotto deve basarsi sui record dei costi in una versione di determinazione costi per costi standard. È possibile utilizzare origini di dati di costo alternative solo con una versione di determinazione costi per costi pianificati, ad esempio accordi commerciali sui prezzi di acquisto per gli articoli acquistati. Le origini di dati di costo alternative vengono definite dal gruppo di calcolo DBA.

-  I calcoli DBA devono essere eseguiti nella modalità di esplosione a livello singolo.

I dati relativi al costo dell'articolo per i costi standard possono essere copiati in un'altra versione di determinazione costi contenente costi standard o pianificati. Tali dati per i costi pianificati tuttavia non potranno essere copiati in una versione di determinazione costi contenente costi standard, in quanto le restrizioni indicate in precedenza in questo articolo non sono applicabili ai costi pianificati.

## <a name="related-articles"></a>Articoli correlati

[Panoramica versioni di determinazione costi](costing-versions.md)

[Aggiornare i costi standard in un ambiente non di produzione](update-standard-costs-non-manufacturing-environment.md)

[Eseguire le operazioni preliminari alla gestione dei costi standard per gli articoli prodotti](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]