---
title: La richiesta di prenotazione automatica viene visualizzata con l'inventario disponibile
description: Quando si utilizza un articolo in un magazzino in cui non sono abilitati i processi di magazzino, la richiesta di prenotazione automatica viene visualizzata. Specificare tutte le dimensioni sopra Ubicazione.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a15502ce8c5bc61d37cedd746985176408a2f362
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476805"
---
# <a name="auto-reservation-prompt-for-batch-number-is-shown-even-with-available-inventory"></a>La richiesta di prenotazione automatica per numero di batch viene visualizzata anche con l'inventario disponibile

## <a name="symptoms"></a>Sintomi

Quando usi un oggetto con una gerarchia di prenotazione *batch-above* in un magazzino che non ha abilitato i processi di magazzino e la prenotazione automatica è abilitata, la richiesta di prenotazione automatica per un numero di batch viene visualizzata anche se è disponibile un solo batch per il prelievo.

Tuttavia, quando utilizzi lo stesso articolo in un magazzino in cui sono abilitati i processi di magazzino, la richiesta di prenotazione automatica non viene visualizzata.

## <a name="resolution"></a>Risoluzione

Se una gerarchia di prenotazione è definita come *batch-above* o *serial-above*, la dimensione di riferimento (**Numero batch** o **Numero di serie**) deve sempre essere specificata su ordini di domanda. I processi di magazzino potrebbero essere in grado di completare le informazioni se è disponibile un singolo batch o numero di serie. Tuttavia, poiché il magazzino non è abilitato per i processi di magazzino, l'utente deve sempre specificare tutte le dimensioni sopra **Ubicazione**.
