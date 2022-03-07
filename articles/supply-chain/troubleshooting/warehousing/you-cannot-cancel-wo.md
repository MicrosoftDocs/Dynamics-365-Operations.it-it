---
title: Non puoi annullare il lavoro di un utente
description: Non puoi annullare il lavoro di un utente
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924403"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a>Non puoi annullare il lavoro di un utente

Codice errore: WAX708

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> Impossibile annullare il lavoro di un utente.

## <a name="cause"></a>Causa

Il lavoro è bloccato da un utente e non può essere annullato. Per verificare ciò, apri l'ID lavoro e quindi apri la scheda **Generale**. Se il lavoro è bloccato, il campo **Stato del lavoro** sarà impostato su *In corso*, e il campo **Bloccato da** è impostato su un ID utente.

## <a name="resolution"></a>Risoluzione

Per annullare il lavoro, seguire questi passaggi.

1. Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.
1. Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare.
1. Selezionare **OK**.
1. Selezionare **Sì** per confermare che si desidera annullare il lavoro.

Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).
