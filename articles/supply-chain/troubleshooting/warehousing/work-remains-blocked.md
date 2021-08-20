---
title: Il lavoro resta bloccato
description: Il lavoro resta bloccato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 898390c78bb26fb8a44f77a10ad27a00720f7d1a3396cec5fff10e9d6b93364d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768572"
---
# <a name="work-remains-blocked"></a>Il lavoro resta bloccato

Codice di errore: WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> Il lavoro %1 rimane bloccato poiché lo stato dell'ondata correlata %2 è %3.

## <a name="cause"></a>Causa

Il lavoro è attualmente in fase di elaborazione in un ciclo e non può essere sbloccato, come indicato da una delle seguenti condizioni:

- Nella scheda **Motivi di blocco** il campo **Motivo blocco lavoro** per una o più righe è impostato su *Ciclo di elaborazione*.
- Quando si seleziona **Ciclo** nel gruppo **Informazioni correlate** della scheda **Informazioni correlate** del riquadro azioni, il campo **Stato ciclo** è impostato su *In elaborazione*.

## <a name="resolution"></a>Risoluzione

Nella scheda **Informazioni correlate** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Ciclo**. Quindi Nel riquadro azioni, nella pagina **Cicli**, nella scheda **Ciclo** e, nel gruppo **Ciclo**, seleziona **Pulizia dati ciclo**.

## <a name="workaround"></a>Soluzione alternativa

Se i passaggi precedenti non hanno risolto il problema, puoi annullare il lavoro seguendo questi passaggi.

1. Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.
1. Nel campo **ID lavoro**, specifica l'ID del lavoro che desideri annullare e che attualmente ha valore **Stato lavoro** uguale a *Aperto*, *In corso*, *Annullato*, *Combinato* o *Chiuso*.
1. Selezionare **OK**.
1. Selezionare **Sì** per confermare che si desidera annullare il lavoro.

Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).
