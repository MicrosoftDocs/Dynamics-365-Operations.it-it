---
title: Risolvere i problemi delle prenotazioni in Gestione magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5f3a9ab907c3cb0e6b99c414a78b6878bd5353274472c54e1f5eaf1d167f046a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773107"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Risolvere i problemi delle prenotazioni in Gestione magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.

Per argomenti relativi alle registrazioni di batch e numeri di serie, vedi [Risolvere i problemi relativi a gerarchie di prenotazione batch e numeri di serie di magazzino](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a>Viene visualizzato il seguente messaggio di errore "Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni".

### <a name="issue-description"></a>Descrizione del problema

Non è possibile annullare la prenotazione dell'inventario su una riga di vendita, perché c'è lavoro aperto per la riga.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Verificare se esiste un lavoro di gruppo di imballaggio aperto per portare l'articolo da una stazione di imballaggio a un'altra ubicazione (ad esempio *Portellone*). Rivedere i record delle pagine **Registro della cronologia di creazione del lavoro** e **Dettagli del lavoro** per determinare cosa sta fisicamente prenotando l'inventario, quindi completare o eliminare il lavoro per liberare la prenotazione.

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile aggiornare la quantità inventario -%1 a causa di transazioni di magazzino insufficienti per l'articolo %2."

### <a name="issue-description"></a>Descrizione del problema

Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate. Di seguito è riportato il messaggio di errore completo:

> Impossibile aggiornare la quantità di inventario -%1 perché non ci sono sufficienti transazioni di inventario per l'articolo %2 con le dimensioni specificate=%3, Colore=%4, Aggiunte=%5, Sito=%6, Magazzino=%7, Ubicazione=%8, Stato inventario=Disponibile, Targa=%9, Numero batch=%10 per ID riferimento %11 in ID lotto %12.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità. Ad esempio, queste transazioni potrebbero aprire ordini di controllo qualità, record di blocco dell'inventario o ordini di uscita.

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile prenotare le scorte fisiche perché nell'inventario sono disponibili solo 0,00".

### <a name="issue-description"></a>Descrizione del problema

Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate. Di seguito è riportato il messaggio di errore completo:

> Sito scorte fisiche=%1, Magazzino=%2, Stato inventario=Disponibile, Numero batch=%3, Proprietario=%4: %5 non può essere prenotato perché solo 0,00 sono disponibili nell'inventario.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo problema è probabilmente causato da un lavoro aperto. Completare il lavoro o ricevere senza crearlo. Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità. Ad esempio, queste transazioni potrebbero essere ordini di controllo qualità aperti, record di blocco dell'inventario o ordini di uscita.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
