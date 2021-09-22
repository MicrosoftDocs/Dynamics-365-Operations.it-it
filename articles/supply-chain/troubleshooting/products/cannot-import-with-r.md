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
ms.openlocfilehash: bf6eb0eb755de3f2842c235946bfd7ccad04ccf7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474726"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Impossibile importare un articolo utilizzando l'entità Prodotti rilasciati V2

Numero KB: 4611825

## <a name="symptoms"></a>Sintomi

Quando tenti di importare un articolo utilizzando l'entità *Prodotti rilasciati V2*, viene visualizzato un messaggio di errore simile al seguente:

> Impossibile creare un record in Articoli - Gruppi di dimensioni di tracciabilità (EcoResTrackingDimensionGroupItem). Numero articolo: 2040663, Batch. Record già esistente.

## <a name="resolution"></a>Risoluzione

Per importare nuovi prodotti rilasciati, devi utilizzare l'entità *Creazione prodotti rilasciati V2* anziché l'entità *Prodotti rilasciati V2*.
