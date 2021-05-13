---
title: Il lavoro non può essere annullato perché è bloccato
description: Il lavoro non può essere annullato perché è bloccato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924281"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a>Il lavoro non può essere annullato perché è bloccato

Codice di errore: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> Il lavoro %1 non può essere annullato perché bloccato dal tipo di motivo %2. Il lavoro deve essere sbloccato per poterlo annullare.

## <a name="cause"></a>Causa

Il lavoro è bloccato e non può essere annullato.

Nella pagina **Lavoro**, nella scheda **Generale**, l'opzione **Bloccato** è impostata su *Sì*. Questa impostazione indica che il lavoro è bloccato. La scheda **Motivi di blocco** mostra il motivo per cui il lavoro è stato bloccato.

## <a name="resolution"></a>Risoluzione

Per sbloccare il lavoro, seleziona la scheda **Motivi di blocco**, quindi segui uno di questi passaggi:

- Se il campo **Motivo blocco lavoro** è impostato su *Motivo indefinito*: Nel riquadro azioni, nella scheda **Lavoro**, gruppo **Lavoro** gruppo, selezionare **Sblocca lavoro**.
- Se il campo **Motivo blocco lavoro** campo è impostato su *Ciclo di elaborazione*: Nel riquadro azioni, scheda **Informazioni correlate**, nel gruppo **Informazioni correlate** selezionare **Ciclo**. Quindi Nel riquadro azioni, nella pagina **Cicli**, nella scheda **Ciclo** e, nel gruppo **Ciclo**, seleziona **Pulizia dati ciclo**.

## <a name="workaround"></a>Soluzione alternativa

Se i passaggi precedenti non hanno risolto il problema, puoi annullare il lavoro seguendo questi passaggi.

1. Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.
1. Nel campo **ID lavoro**, specifica l'ID del lavoro che desideri annullare e che attualmente ha valore **Stato lavoro** uguale a *Aperto*, *In corso*, *Annullato*, *Combinato* o *Chiuso*.
1. Selezionare **OK**.
1. Selezionare **Sì** per confermare che si desidera annullare il lavoro.

Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).
