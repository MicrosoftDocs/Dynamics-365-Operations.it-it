---
title: L'ultima riga di lavoro chiusa deve essere un inserimento
description: L'ultima riga di lavoro chiusa deve essere un inserimento
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
ms.openlocfilehash: bbc5797df2b7465b36ec5ea546a67441626daeb1c72f82dfca4eb7db3503b713
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760276"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>L'ultima riga di lavoro chiusa deve essere un inserimento

Codice errore: WAX1285

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> L'ultima riga di lavoro chiusa deve essere un inserimento.

## <a name="cause"></a>Causa

Il lavoro non può essere annullato nel suo stato attuale.

Nell'ultima riga di lavoro, il campo **Stato lavoro** è impostato su *Chiuso*, ma **Tipo di lavoro** non è impostato su *Inserisci*.

## <a name="resolution"></a>Risoluzione

Per annullare il lavoro, seguire questi passaggi.

1. Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.
1. Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare.
1. Selezionare **OK**.
1. Selezionare **Sì** per confermare che si desidera annullare il lavoro.

Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).
