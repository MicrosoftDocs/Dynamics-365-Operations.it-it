---
title: Pianificazione con quantità disponibili negative
description: Questo argomento spiega come vengono gestite le quantità disponibili negative quando si utilizza l'ottimizzazione della pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 72ed2ba42c6233461743492fe6776f376195ada6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983468"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Pianificazione con quantità disponibili negative

[!include [banner](../../includes/banner.md)]

Se il sistema mostra una quantità aggregata disponibile negativa, il motore di pianificazione considera la quantità come 0 (zero) per evitare un eccesso di offerta. Ecco come funziona questa funzionalità:

1. La funzione di ottimizzazione della pianificazione aggrega le quantità disponibile al livello più basso delle dimensioni di copertura. (Ad esempio, se *Ubicazione* non è una dimensione di copertura, la pianificazione dell'ottimizzazione aggrega le quantità disponibile a livello di *magazzino*.)
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

## <a name="related-resources"></a>Risorse correlate

[Panoramica sull'ottimizzazione della pianificazione](planning-optimization-overview.md)

[Introduzione all'ottimizzazione della pianificazione](get-started.md)

[Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)
