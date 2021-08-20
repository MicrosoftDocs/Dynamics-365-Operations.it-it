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
ms.openlocfilehash: f3170bcb723e2d7483258bb0ecf786e62f2aa3d196745074c2ac554bc212ec55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742006"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>La pianificazione generale genera ordini pianificati per prodotti fittizi

Numero KB: 4614729

## <a name="symptoms"></a>Sintomi

L'esecuzione della pianificazione generale genera ordini pianificati per prodotti fittizi.

## <a name="resolution"></a>Risoluzione

L'impostazione dell'opzione **Fittizio** per prodotti rilasciati determina il tipo di riga predefinito nella distinta base (DBA). Quando l'opzione **Fittizio** è impostata su *Sì*, il sistema creerà comunque ordini pianificati per l'articolo, ma l'opzione **Fabbisogno direttamente derivato** di ogni ordine pianificato sarà impostata su *Sì*. Pertanto, l'ordine di produzione pianificato non può essere stabilizzato da solo. Al contrario, verrà sempre incluso automaticamente quando viene stabilizzato l'ordine di produzione padre. Inoltre, le righe della distinta base dell'ordine fittizio pianificato verranno incluse nella distinta base dell'ordine di produzione padre.
