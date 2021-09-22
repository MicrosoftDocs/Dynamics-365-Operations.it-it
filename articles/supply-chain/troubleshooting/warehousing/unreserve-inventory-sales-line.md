---
title: Impossibile annullare la prenotazione dell'inventario su una riga dell'ordine cliente
description: Se c'è lavoro aperto per una riga di vendita e si tenta di annullare la prenotazione dell'inventario sulla riga, si riceve un errore. Completa o cancella il lavoro per liberare la prenotazione.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1a042065dc4cd637aff58e55cf16179b7022f6ca
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476777"
---
# <a name="cant-unreserve-inventory-on-a-sales-order-line"></a>Impossibile annullare la prenotazione dell'inventario su una riga dell'ordine cliente

## <a name="symptoms"></a>Sintomi

Se c'è lavoro aperto per una riga dell'ordine cliente e si tenta di annullare la prenotazione dell'inventario sulla riga, si riceve il seguente messaggio di errore:

> Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni.

## <a name="resolution"></a>Risoluzione

Verificare se esiste un lavoro di gruppo di imballaggio aperto per portare l'articolo da una stazione di imballaggio a un'altra ubicazione (ad esempio *Portellone*). Rivedere i record delle pagine **Registro della cronologia di creazione del lavoro** e **Dettagli del lavoro** per determinare cosa sta fisicamente prenotando l'inventario, quindi completare o eliminare il lavoro per liberare la prenotazione.
