---
title: Molteplici transazioni di magazzino per numeri batch quando l'opzione All'aggiornamento fisico è disabilitata
description: Molteplici transazioni di magazzino vengono create dopo aver rettificato una riga ordine fornitore di articoli in cui l'opzione All'aggiornamento fisico del gruppo di numeri batch è impostata su No.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026657"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a>Molteplici transazioni di magazzino per numeri batch quando l'opzione All'aggiornamento fisico è disabilitata

Numero KB: 4613390

## <a name="symptoms"></a>Sintomi

Molteplici transazioni di magazzino vengono create dopo aver rettificato una riga di ordine fornitore di articoli in cui l'opzione **All'aggiornamento fisico** del gruppo di numeri batch è impostata su *No*.

Quando crei un articolo in cui l'opzione **All'aggiornamento fisico** del gruppo di numeri batch è impostata su *No*, il sistema crea automaticamente un nuovo numero batch se modifichi la quantità di una riga di acquisto e salvi la pagina dell'ordine fornitore.

## <a name="resolution"></a>Risoluzione

L'impostazione **All'aggiornamento fisico** per i gruppi di numeri batch funziona nel modo seguente:

- Quando l'opzione è impostata su *Sì*, i nuovi numeri batch vengono creati solo dopo un aggiornamento fisico (ad esempio, quando gli articoli vengono spediti o ricevuti).
- Quando l'opzione è impostata su *No*, viene creato un nuovo numero batch ogni volta che si verifica un aggiornamento applicabile (ad esempio, quando una nuova quantità viene aggiunta a un ordine fornitore).
