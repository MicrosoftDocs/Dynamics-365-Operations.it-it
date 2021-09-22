---
title: Quantità non valida per lavori di prelievo con più targhe
description: Quando è presente lavoro di prelievo con più targhe in un'unica ubicazione, la quantità non è valida per l'unità ea. Verificare che i seguenti campi siano corretti.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5b245f71e80339fee3e42cfffa0396078a56926e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476727"
---
# <a name="quantity-not-valid-when-theres-picking-work-with-multiple-lps-in-one-location"></a>Quantità non valida quando è presente lavoro di prelievo con più targhe in un'unica ubicazione

## <a name="symptoms"></a>Sintomi

Quando è presente lavoro di prelievo con più targhe in un'unica ubicazione, la quantità non è valida per l'unità *ea* e si riceve il messaggio di errore seguente:

> Quantità non valida per l'unità 1%.

## <a name="resolution"></a>Risoluzione

Verificare che i campi **ID gruppo sequenza unità** e **Conversioni unità** del prodotto o della variante di prodotto rilasciato siano impostati correttamente.

Notare che il messaggio di errore è stato migliorato nella versione 10.0.15 per mostrare la quantità prevista (vedere [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Il nuovo messaggio di errore è:

> Quantità non valida. Valore previsto %1 %2.
