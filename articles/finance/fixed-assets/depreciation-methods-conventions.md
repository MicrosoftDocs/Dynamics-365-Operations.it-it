---
title: Metodi e convenzioni di ammortamento
description: Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento che sono supportati da Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f1320d0adaad783f856ed6404039e7954920340
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187339"
---
# <a name="depreciation-methods-and-conventions"></a>Metodi e convenzioni di ammortamento

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento supportati.

È possibile selezionare diversi metodi e convenzioni di ammortamento. Scopo dei metodi è l'allocazione del valore ammortizzabile del cespite ai periodi fiscali. Tale valore corrisponde al prezzo di acquisizione da cui viene dedotto un valore di scarto, se presente. 

Se si utilizzano le convenzioni di ammortamento e si modifica la data di esecuzione dell'ultimo ammortamento di un cespite, determinando l'annullamento di alcuni ammortamenti, l'ammortamento relativo all'ultimo anno può risultare maggiore o minore del previsto. L'ammortamento viene rettificato in base al numero di periodi di ammortamento interessati dalla modifica della data di esecuzione dell'ultimo ammortamento.

Ad esempio, se si utilizza la convenzione di ammortamento semestrale su tre anni, l'ammortamento viene in genere eseguito su 3 anni e mezzo. Se durante questo intervallo di tempo la data di esecuzione dell'ultimo ammortamento viene modificata, il numero di periodi interessati nell'ultimo anno di ammortamento viene esteso. Se si sposta la data di tre mesi, nell'ultimo anno verranno considerati nove mesi di ammortamento, mentre normalmente dovrebbero essere solo sei.

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





<a name="additional-resources"></a>Risorse aggiuntive
--------

[Ammortamento dei cespiti](fixed-asset-depreciation.md)

[Ammortamento a quote costanti basato sulla vita utile](Straight-line-service-life-depreciation.md)

[Ammortamento a saldi decrescenti](reduce-balance-depreciation.md)

[Ammortamento manuale](manual-depreciation.md)

[Ammortamento basato su coefficiente](factor-depreciation.md)

[Ammortamento del consumo](consumption-depreciation.md)

[Ammortamento basato sulla vita utile rimanente a quote costanti](straight-line-life-remaining-depreciation.md)

[Riduzione del 125% dell'ammortamento del saldo](125-percent-reducing-balance-depreciation.md)

[Riduzione del 150% dell'ammortamento del saldo](150-percent-reducing-balance-depreciation.md)

[Riduzione del 175% dell'ammortamento del saldo](175-percent-reducing-balance-depreciation.md)

[Riduzione del 200% dell'ammortamento del saldo](200-percent-reducing-balance-depreciation.md)


