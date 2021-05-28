---
title: Errore quando il giornale di registrazione Dichiarato finito viene registrato
description: Quando registri il giornale di registrazione Dichiarato finito, viene visualizzato un messaggio di errore che informa che la quantità ordinata non può essere ridotta.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026632"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Errore quando il giornale di registrazione Dichiarato finito viene registrato

Numero KB: 4612891

## <a name="symptoms"></a>Sintomi

Quando registri il giornale di registrazione **Dichiarato finito**, si verifica un errore e viene visualizzato il seguente messaggio di errore:

> Impossibile ridurre la quantità ordinata perché non è presente un numero sufficiente di operazioni di magazzino aperte con stato Ordinato. Gli articoli sono acquistati, ricevuti o registrati.

Questo errore si verifica solo quando il campo **Quantità difettosa** è impostato nella prima riga del giornale di registrazione **Dichiarato finito** e il campo **Quantità idonea** è impostato nell'ultima riga. Se il campo **Quantità difettosa** è impostato nell'ultima riga, non si verificano errori.

## <a name="resolution"></a>Risoluzione

Per evitare questo errore, apri la pagina **Parametri di controllo produzione**, quindi nella scheda **Generale**, imposta l'opzione **Aumenta quantità rimanente con quantità difettosa** su *Sì*.
