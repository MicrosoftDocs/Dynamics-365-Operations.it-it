---
title: Impossibile effettuare prenotazioni scorte perché sono disponibili 0,00
description: Ricevi un errore che dice che il sistema non può effettuare prenotazioni perché solo 0,00 sono disponibili nell'inventario. Questo problema è probabilmente causato da un lavoro aperto.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 75d72f7ee1bdecca5a087b75b1de9907b9d244ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476799"
---
# <a name="system-cant-make-reservations-because-000-are-available-in-the-inventory"></a>Il sistema non può effettuare prenotazioni scorte perché sono disponibili 0,00 nell'inventario

## <a name="symptoms"></a>Sintomi

Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate. Verrà visualizzato il seguente messaggio di errore:

> Sito scorte fisiche=%1, Magazzino=%2, Stato inventario=Disponibile, Numero batch=%3, Proprietario=%4: %5 non può essere prenotato perché solo 0,00 sono disponibili nell'inventario.

## <a name="resolution"></a>Risoluzione

Questo problema è probabilmente causato da un lavoro aperto. Completare il lavoro o ricevere senza crearlo. Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità. Ad esempio, queste transazioni potrebbero essere ordini di controllo qualità aperti, record di blocco dell'inventario o ordini di uscita.
