---
title: Pianificazione con quantità disponibili negative
description: Questo articolo spiega come viene gestita la disponibilità negativa.
author: t-benebo
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: b4fc8b37fd800e3b4652513f150f9806bf1d5d67
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741124"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Pianificazione con quantità disponibili negative

[!include [banner](../../includes/banner.md)]

Se il sistema mostra una quantità aggregata disponibile negativa, il motore di pianificazione considera la quantità come 0 (zero) per evitare un eccesso di offerta. Ecco come funziona questa funzionalità:

1. La pianificazione generale aggrega le quantità disponibile al livello più basso delle dimensioni di copertura. (Ad esempio, se *Ubicazione* non è una dimensione di copertura, la pianificazione generale aggrega le quantità disponibile a livello di *magazzino*.)
1. Se la quantità disponibile aggregata al livello più basso delle dimensioni di copertura è negativa, il sistema presuppone che la quantità disponibile sia effettivamente 0 (zero).

> [!IMPORTANT]
> Il sistema di pianificazione può essere preciso solo parimenti ai dati di input. Se i dati di input non sono accurati, i record con quantità disponibili negative indicano che le informazioni sulle scorte in Microsoft Dynamics 365 Supply Chain Management non sono sincronizzate con il mondo reale. Pertanto, il risultato della pianificazione sarà imperfetto. Per ottenere un risultato di pianificazione preciso, è necessario ridurre al minimo il numero di record che mostrano una quantità disponibile negativa.

## <a name="example-1"></a>Esempio 1

Il magazzino 13 è configurato nel modo seguente:

- **Codice di copertura:** Min/Max
- **Minimo:** 15 pezzi (pz.)
- **Massimo:** 25 pz.

Il livello più basso di dimensioni di copertura è *magazzino* e le seguenti quantità disponibili sono registrate presso il livello *ubicazione*:

- **Sito 1, magazzino 13, ubicazione 1:** 20 pz.
- **Sito 1, magazzino 13, ubicazione 2:** &minus;8 pz.

Pertanto, la quantità disponibile aggregata per il magazzino 13 è di 12 pz. (= 20 pz. &minus; 8 pz.).

In questo caso, il motore di pianificazione utilizza una quantità disponibile aggregata di 12 pz. per il magazzino 13.

Il risultato è un ordine pianificato di 13 pz. (= 25 pz. &minus; 12 pz.) per ricaricare il magazzino 13 da 12 pz. a 25 pz.

## <a name="example-2"></a>Esempio 2

Il magazzino 13 è configurato nel modo seguente:

- **Codice di copertura:** Min/Max
- **Minimo:** 15 pz.
- **Massimo:** 25 pz.

Il livello più basso di dimensioni di copertura è *magazzino* e le seguenti quantità disponibili sono registrate presso il livello *ubicazione*:

- **Sito 1, magazzino 13, ubicazione 1:** 4 pz.
- **Sito 1, magazzino 13, ubicazione 2:** &minus;8 pz.

Pertanto, la quantità disponibile aggregata per il magazzino 13 è di &minus;4 pz. (= 4 pz. &minus; 8 pz.). In altre parole, è inferiore a 0 (zero).

In questo caso, il motore di pianificazione presuppone che la quantità disponibile per il magazzino 13 sia 0 pz. anziché &minus;4 pz.

Il risultato è un ordine pianificato di 25 pz. (= 25 pz. &minus; 0 pz.) per ricaricare il magazzino 13 da 0 pz. a 25 pz.

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Pianificazione in caso di prenotazione a fronte di scorte disponibili negative

Se modifichi l'inventario mentre esistono prenotazioni fisiche, puoi causare una situazione in cui un ordine viene prenotato fisicamente a fronte di un inventario negativo. In questo caso, poiché esiste una prenotazione fisica, è necessario disporre di una fornitura per coprire la quantità prenotata. Pertanto, è necessario il rifornimento, quindi il sistema creerà un ordine pianificato per rifornire la quantità che non può essere coperta dalle scorte disponibili esistenti o per coprirla con un ordine esistente per l'articolo.

Nel seguente scenario di esempio viene illustrato questo aspetto.

### <a name="example"></a>Esempio

Il sistema è configurato nel seguente modo:

- Il prodotto *FG* esiste e ha *10* pezzi di scorte disponibili.
- La configurazione del prodotto consente l'inventario fisico negativo.
- Esiste un ordine cliente per una quantità di *10* pezzi di prodotto *FG*.
- La quantità dell'ordine cliente viene prenotata fisicamente per le scorte disponibili esistenti.

Quindi regoli la quantità del prodotto *FG* in modo che le scorte disponibili diventino 5. Poiché l'inventario dei prodotti disponibili è 5, la quantità dell'ordine cliente è ora riservata su una quantità che non è disponibile (sarebbe simile se l'inventario disponibile fosse 0, nel qual caso l'ordine cliente sarebbe riservato su un inventario negativo). Se ora esegui la pianificazione generale, verrà creato un ordine pianificato di quantità 5 per *FG* per fornire l'ordine cliente, poiché la pianificazione generale utilizzerà sempre la fornitura esistente o creerà un nuovo ordine pianificato per fornire la prenotazione fisica.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
