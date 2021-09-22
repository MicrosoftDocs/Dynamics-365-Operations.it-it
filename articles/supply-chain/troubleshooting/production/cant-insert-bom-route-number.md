---
title: Impossibile inserire la versione attiva della distinta base e dei numeri dei cicli di lavorazione
description: Se il sito predefinito e il magazzino sono già definiti per un prodotto selezionato, non verrà richiesto di inserire la versione attiva della distinta base e dei numeri dei cicli di lavorazione.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 241618d70f01c85df946a48493f5d84e0964218e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476721"
---
# <a name="cant-insert-bill-of-material-and-route-when-creating-a-new-production-order"></a>Impossibile inserire la distinta base e il ciclo di lavorazione durante la creazione di un nuovo ordine di produzione

## <a name="symptoms"></a>Sintomi

Quando si crea un nuovo ordine di produzione, dopo aver immesso il numero articolo, i campi **Sito** e **Magazzino** vengono impostati automaticamente sul sito e sul magazzino predefiniti definiti nella pagina **Impostazioni dell'ordine predefinite** per l'articolo prodotti finiti. Inoltre, il numero della distinta base attiva e il numero del ciclo di lavorazione vengono inseriti automaticamente, quindi non viene visualizzato il seguente messaggio che richiede tali valori:

> Inserire la versione attiva per distinta base e ciclo di lavorazione?

## <a name="resolution"></a>Risoluzione

Non viene richiesto di inserire i numeri della distinta base e del ciclo di lavorazione se si seleziona un prodotto per il quale sono già definiti un sito e un magazzino nella pagina **Impostazioni dell'ordine predefinite**. Vengono richiesti solo se questi valori non sono definiti per il prodotto selezionato.
