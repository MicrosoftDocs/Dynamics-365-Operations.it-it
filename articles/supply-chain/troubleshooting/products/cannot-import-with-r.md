---
title: Impossibile importare un articolo utilizzando l'entità Prodotti rilasciati V2
description: Impossibile importare un articolo utilizzando l'entità Prodotti rilasciati V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026635"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Impossibile importare un articolo utilizzando l'entità Prodotti rilasciati V2

Numero KB: 4611825

## <a name="symptoms"></a>Sintomi

Quando tenti di importare un articolo utilizzando l'entità *Prodotti rilasciati V2*, viene visualizzato un messaggio di errore simile al seguente:

> Impossibile creare un record in Articoli - Gruppi di dimensioni di tracciabilità (EcoResTrackingDimensionGroupItem). Numero articolo: 2040663, Batch. Record già esistente.

## <a name="resolution"></a>Risoluzione

Per importare nuovi prodotti rilasciati, devi utilizzare l'entità *Creazione prodotti rilasciati V2* anziché l'entità *Prodotti rilasciati V2*.
