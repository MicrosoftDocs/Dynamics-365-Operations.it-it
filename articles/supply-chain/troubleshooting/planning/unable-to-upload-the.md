---
title: Impossibile aggiornare il costo unitario previsto quando si importano record di previsione della domanda
description: Quando si utilizzano entità di dati per importare record di previsione della domanda, il prezzo di costo dei record esistenti non viene aggiornato di modo che corrisponda ai dati importati.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026647"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Impossibile aggiornare il costo unitario previsto quando si importano record di previsione della domanda

Numero KB: 4614109

## <a name="symptoms"></a>Sintomi

Quando utilizzi entità di dati per importare record di previsione della domanda, il valore **Costo unitario previsto** dei record esistenti non viene aggiornato di modo che corrisponda ai dati importati.

## <a name="cause"></a>Causa

**Costo unitario previsto** è un campo di sola lettura. Il valore si basa sul costo unitario del prodotto e non può essere impostato direttamente tramite importazione.

## <a name="resolution"></a>Risoluzione

Poiché il campo è di sola lettura, non è possibile importare valori per lo stesso. Il valore verrà calcolato in base alla logica aziendale esistente.
