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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924257"
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
