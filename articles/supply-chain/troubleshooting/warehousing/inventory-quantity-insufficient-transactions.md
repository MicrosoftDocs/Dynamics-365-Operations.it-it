---
title: Quantità di inventario non aggiornata a causa di transazioni insufficienti
description: La quantità di inventario - 1% non può essere aggiornata perché non vi sono sufficienti transazioni di inventario per l'articolo %2 con le dimensioni specificate.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88130a969039dd741c8ea4fbaabe81acf0e6fb6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476719"
---
# <a name="system-cant-update-inventory-quantity-because-of-insufficient-transactions"></a>Il sistema non può aggiornare la quantità di inventario a causa di transazioni insufficienti

## <a name="symptoms"></a>Sintomi

Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate. Verrà visualizzato il seguente messaggio di errore:

> Impossibile aggiornare la quantità di inventario -%1 perché non ci sono sufficienti transazioni di inventario per l'articolo %2 con le dimensioni specificate=%3, Colore=%4, Aggiunte=%5, Sito=%6, Magazzino=%7, Ubicazione=%8, Stato inventario=Disponibile, Targa=%9, Numero batch=%10 per ID riferimento %11 in ID lotto %12.

## <a name="resolution"></a>Risoluzione

Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità. Ad esempio, queste transazioni potrebbero aprire ordini di controllo qualità, record di blocco dell'inventario o ordini di uscita.
