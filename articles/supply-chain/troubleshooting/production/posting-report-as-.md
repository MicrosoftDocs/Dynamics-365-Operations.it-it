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
ms.openlocfilehash: 50a11aba46519a3a81c313aa1f685d45dcf35f64b50bc921d93968efab13b7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750932"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Errore quando il giornale di registrazione Dichiarato finito viene registrato

Numero KB: 4612891

## <a name="symptoms"></a>Sintomi

Quando registri il giornale di registrazione **Dichiarato finito**, si verifica un errore e viene visualizzato il seguente messaggio di errore:

> Impossibile ridurre la quantità ordinata perché non è presente un numero sufficiente di operazioni di magazzino aperte con stato Ordinato. Gli articoli sono acquistati, ricevuti o registrati.

Questo errore si verifica solo quando il campo **Quantità difettosa** è impostato nella prima riga del giornale di registrazione **Dichiarato finito** e il campo **Quantità idonea** è impostato nell'ultima riga. Se il campo **Quantità difettosa** è impostato nell'ultima riga, non si verificano errori.

## <a name="resolution"></a>Risoluzione

Per evitare questo errore, apri la pagina **Parametri di controllo produzione**, quindi nella scheda **Generale**, imposta l'opzione **Aumenta quantità rimanente con quantità difettosa** su *Sì*.
