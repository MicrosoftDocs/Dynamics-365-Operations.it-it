---
title: La pianificazione generale genera ordini pianificati per prodotti fittizi
description: L'esecuzione della pianificazione generale genera ordini pianificati per prodotti fittizi.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026650"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>La pianificazione generale genera ordini pianificati per prodotti fittizi

Numero KB: 4614729

## <a name="symptoms"></a>Sintomi

L'esecuzione della pianificazione generale genera ordini pianificati per prodotti fittizi.

## <a name="resolution"></a>Risoluzione

L'impostazione dell'opzione **Fittizio** per prodotti rilasciati determina il tipo di riga predefinito nella distinta base (DBA). Quando l'opzione **Fittizio** è impostata su *Sì*, il sistema creerà comunque ordini pianificati per l'articolo, ma l'opzione **Fabbisogno direttamente derivato** di ogni ordine pianificato sarà impostata su *Sì*. Pertanto, l'ordine di produzione pianificato non può essere stabilizzato da solo. Al contrario, verrà sempre incluso automaticamente quando viene stabilizzato l'ordine di produzione padre. Inoltre, le righe della distinta base dell'ordine fittizio pianificato verranno incluse nella distinta base dell'ordine di produzione padre.
