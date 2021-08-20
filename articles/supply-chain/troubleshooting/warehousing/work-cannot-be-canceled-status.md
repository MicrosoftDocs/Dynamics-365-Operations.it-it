---
title: Il lavoro non può essere annullato a causa del suo stato
description: Il lavoro non può essere annullato a causa del suo stato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f983501b490c5516525b4d5904603ed62e8799f9e6124e5672b36a12804ecb0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755980"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a>Il lavoro non può essere annullato a causa del suo stato

Codice errore: WAX2190

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> Impossibile annullare il lavoro %1 poiché ha uno stato %2.

## <a name="cause"></a>Causa

Il lavoro non può essere annullato nel suo stato attuale.

L'intestazione del lavoro o le righe di lavoro non hanno il valore **Stato lavoro** previsto. Il campo **Stato lavoro** nell'intestazione del lavoro non è impostato su *Aperto* o *In corso*.

## <a name="resolution"></a>Risoluzione

Per annullare il lavoro, seguire questi passaggi.

1. Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.
1. Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare.
1. Selezionare **OK**.
1. Selezionare **Sì** per confermare che si desidera annullare il lavoro.

Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).
