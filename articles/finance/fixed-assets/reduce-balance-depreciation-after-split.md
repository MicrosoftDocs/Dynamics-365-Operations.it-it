---
title: Ridurre l'ammortamento a saldi decrescenti dopo una divisione
description: In questo argomento viene descritto il metodo utilizzato in Cespiti per calcolare l'ammortamento dopo la divisione di un cespite utilizzando il metodo di riduzione del saldo.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 615d17c71b904d426081d4c57492ba7e95c2c749
ms.sourcegitcommit: 65f9e2584c0530b1a71655aae09101691726b47f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "4650669"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>Ridurre l'ammortamento a saldi decrescenti dopo una divisione

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto il metodo utilizzato in Cespiti per calcolare l'ammortamento dopo la divisione di un cespite in un altro cespite utilizzando il metodo di riduzione del saldo. L'anno di ammortamento configurato nel libro cespiti è l'anno fiscale. Per ulteriori informazioni, vedi [Ridurre l'ammortamento del saldo](reduce-balance-depreciation.md) e [Dividere un cespite](tasks/split-fixed-asset.md).

Se dividi un cespite durante un periodo fiscale successivo al periodo in cui il cespite è stato acquisito, l'ammortamento del saldo ridotto contabilizzerà il valore contabile netto del cespite dell'anno precedente. Conterrà anche le transazioni di acquisizione e di rettifica dell'ammortamento generate dalla transazione che ha suddiviso il bene. Questo comportamento presuppone che il cespite sia stato acquisito in un anno fiscale e diviso in un anno fiscale successivo. L'importo che deve essere ammortizzato per il cespite originale dopo la suddivisione riflette l'NBV del cespite prima che il cespite fosse diviso e la transazione di rettifica dell'acquisizione e dell'ammortamento registrata per la divisione.

Ad esempio, sono in vigore le seguenti condizioni:

- Il periodo fiscale va dal 30 giugno al 1 luglio.
- La percentuale di saldo decrescente è del 18% e un cespite 'viene acquistato a giugno 2019 a un prezzo di acquisto di $10.000.
- L'ammortamento del primo anno fiscale è pari a $18.000, l'ammortamento mensile è pari a $150 e il cespite viene quindi ammortizzato fino a novembre 2019, per un importo di $738,75.
- A novembre 2019, l'80% del cespite viene diviso in un altro cespite.

[![Ridurre l'ammortamento a saldi decrescenti dopo una divisione](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

L'importo da ammortizzare per il cespite originale è $1.822,25. Questo importo è uguale al valore contabile netto prima della registrazione della transazione di divisione ($ 9.111,25), più la rettifica di acquisizione generata durante la registrazione della transazione di divisione (- $ 8.000), più la rettifica di ammortamento generata durante la transazione di divisione ($ 711). Pertanto, l'ammortamento per il secondo anno è (1.822,25 × 18 percento) ÷ 12 = $27,33.

L'importo da ammortizzare per il nuovo cespite nel primo anno è (8.000 × 18 percento) ÷ 12 = $120.
