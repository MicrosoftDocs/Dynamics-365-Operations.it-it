---
title: Metodi e convenzioni di ammortamento
description: Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento che sono supportati da Microsoft Dynamics AX.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 51c053e6c130d20258e02284d097431a18bb38cb
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-methods-and-conventions"></a>Metodi e convenzioni di ammortamento

Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento che sono supportati da Microsoft Dynamics AX.

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

 



<a name="see-also"></a>Vedere anche
--------

[Fixed asset depreciation](fixed-asset-depreciation.md)

[Straight line service life depreciation](Straight-line-service-life-depreciation.md)

[Reducing balance depreciation](reduce-balance-depreciation.md)

[Manual depreciation](manual-depreciation.md)

[Factor depreciation](factor-depreciation.md)

[Consumption depreciation](consumption-depreciation.md)

[Straight line life remaining depreciation](straight-line-life-remaining-depreciation.md)

[riduzione del 125 di ammortamento] saldi (125 percent-reducing-balance-depreciation.md)

[riduzione del 150 di ammortamento] saldi (150 percent-reducing-balance-depreciation.md)

[riduzione del 175 di ammortamento] saldi (175 percent-reducing-balance-depreciation.md)

[200 percent reducing balance depreciation](200-percent-reducing-balance-depreciation.md)


