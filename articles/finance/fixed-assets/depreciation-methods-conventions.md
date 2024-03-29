---
title: Metodi e convenzioni di ammortamento
description: Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento che sono supportati da Microsoft Dynamics 365 Finance.
author: moaamer
ms.date: 12/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 066e571485602907d167b2ed1f7530b2285a02b6
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714175"
---
# <a name="depreciation-methods-and-conventions"></a>Metodi e convenzioni di ammortamento

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento supportati.

È possibile selezionare diversi metodi e convenzioni di ammortamento. Scopo dei metodi è l'allocazione del valore ammortizzabile del cespite ai periodi fiscali. Tale valore corrisponde al prezzo di acquisizione da cui viene dedotto un valore di scarto, se presente. 

Se si utilizzano le convenzioni di ammortamento e si modifica la data di esecuzione dell'ultimo ammortamento di un cespite, determinando l'annullamento di alcuni ammortamenti, l'ammortamento relativo all'ultimo anno può risultare maggiore o minore del previsto. L'ammortamento viene rettificato in base al numero di periodi di ammortamento interessati dalla modifica della data di esecuzione dell'ultimo ammortamento.

Ad esempio, se si utilizza la convenzione di ammortamento semestrale su tre anni, l'ammortamento viene in genere eseguito su tre anni e mezzo. Se durante questo intervallo di tempo la data di esecuzione dell'ultimo ammortamento viene modificata, il numero di periodi interessati nell'ultimo anno di ammortamento viene esteso. Se si sposta la data di tre mesi, nell'ultimo anno verranno considerati nove mesi di ammortamento, mentre normalmente dovrebbero essere solo sei.

È possibile selezionare una delle convenzioni di ammortamento riportate di seguito.


-   Semestre
-   Mese intero
-   Metà trimestre
-   Metà mese (giorno 1 del mese)
-   Metà mese (giorno 15 del mese)
-   Semestre (inizio anno)
-   Semestre (prossimo anno)

È possibile selezionare uno dei metodi di ammortamento riportate di seguito.
-   Vita utile a quote costanti
-   A saldi decrescenti
-   Manuale
-   Fattore
-   Consumo
-   Vita utile rimanente a quote costanti
-   Saldo decrescente 200%
-   Saldo decrescente 175%
-   Saldo decrescente 150%
-   Saldo decrescente 125%





## <a name="additional-resources"></a>Risorse aggiuntive

[Ammortamento cespiti](fixed-asset-depreciation.md)

[Ammortamento a quote costanti basato sulla vita utile](Straight-line-service-life-depreciation.md)

[Ammortamento a saldi decrescenti](reduce-balance-depreciation.md)

[Ammortamento manuale](manual-depreciation.md)

[Ammortamento basato su coefficiente](factor-depreciation.md)

[Ammortamento del consumo](consumption-depreciation.md)

[Ammortamento basato sulla vita utile rimanente a quote costanti](straight-line-life-remaining-depreciation.md)

[Ammortamento a saldi decrescenti del 125%](125-percent-reducing-balance-depreciation.md)

[Riduzione del 150% dell'ammortamento del saldo](150-percent-reducing-balance-depreciation.md)

[Riduzione del 175% dell'ammortamento del saldo](175-percent-reducing-balance-depreciation.md)

[Riduzione del 200% dell'ammortamento del saldo](200-percent-reducing-balance-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
