---
title: Stesso accordo commerciale selezionato durante la creazione delle righe di ordine cliente
description: Se è presente più di un accordo commerciale definito per una determinata data, durante la creazione delle righe di ordine cliente viene sempre selezionato quello con il prezzo più basso.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a586a399fb349965b972191bec1271651bec5fcb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476773"
---
# <a name="if-two-trade-agreements-exist-for-overlapping-dates-the-same-one-is-always-selected"></a>Se esistono due accordi commerciali per date sovrapposte, viene sempre selezionato lo stesso

## <a name="symptoms"></a>Sintomi

Se due accordi commerciali sono definiti per lo stesso periodo o periodi sovrapposti, lo stesso accordo commerciale sembra essere selezionato ogni volta che si creano righe ordine cliente che contengono tali articoli.

## <a name="resolution"></a>Risoluzione

Se è presente più di un accordo commerciale per una determinata data, viene sempre selezionato l'accordo commerciale con il prezzo più basso. Per altre informazioni, scarica il seguente white paper: [Accordi commerciali in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).
