---
title: Le transazioni possono essere registrate in un conto CoGe sospeso
description: Se un'entrata prodotti viene annullata, il sistema consente la registrazione delle transazioni in conti CoGe sospesi, anche se i conti principali sono sospesi
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 20df0ee4107ad62bec0dd9a683660fe2375a3dd1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476816"
---
# <a name="transactions-can-be-posted-to-a-suspended-ledger-account"></a>Le transazioni possono essere registrate in un conto CoGe sospeso

## <a name="symptoms"></a>Sintomi

Se un'entrata prodotti viene annullata, il sistema consente la registrazione delle transazioni nei conti CoGe sospesi, anche se i conti principali sono sospesi.

## <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Nella pagina **Parametri contabilità fornitori**, nella scheda **Generale**, assicurati che l'opzione **Registra entrata prodotti nella contabilità generale** sia impostata su *Sì*.
1. Crea un ordine fornitore e aggiungi una riga ordine con una quantità di *1.000* per un prodotto.
1. Conferma l'ordine fornitore.
1. Registra l'entrata del prodotto e controlla i giustificativi.
1. Sospendi i relativi conti principali, *200140* e *140200*.
1. Annulla l'entrata del prodotto registrata.
1. Si noti che le transazioni possono essere registrate nei conti CoGe sospesi.

## <a name="resolution"></a>Risoluzione

Le transazioni possono essere registrate nei conti CoGe sospesi quando le entrate prodotti vengono annullate, poiché questo comportamento consente registrazioni corrette.
