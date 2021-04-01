---
title: Risolvere i problemi delle prenotazioni in Gestione magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: a9a5d20732a802fc58c392853af8334bbc07de73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248717"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Risolvere i problemi delle prenotazioni in Gestione magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.

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

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Viene visualizzato il seguente messaggio di errore: "Per essere assegnate al ciclo, le righe di carico devono specificare le dimensioni sopra l'ubicazione. Per assegnare queste dimensioni, prenotare e ricreare la riga di carico. "

### <a name="issue-description"></a>Descrizione del problema

Quando si utilizza un articolo che ha una gerarchia di prenotazione "sopra il batch" (con la dimensione **Numero batch** posizionata *sopra* la dimensione **Ubicazione**), il comando **Rilascia in magazzino** nella pagina **Workbench di pianificazione del carico** per una quantità parziale non funziona. Viene visualizzato questo messaggio di errore e non viene creato alcun lavoro per la quantità parziale.

Tuttavia se si utilizza un articolo che ha una gerarchia di prenotazione "sotto il batch" (con la dimensione **Numero batch** posizionata *sotto* la dimensione **Ubicazione**), è possibile rilasciare il carico dalla pagina **Workbench di pianificazione del carico** per una quantità parziale.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. Se si inserisce una dimensione sopra la dimensione **Ubicazione** nella gerarchia di prenotazione, deve essere specificata prima del rilascio al magazzino. Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione della funzionalità durante i rilasci al magazzino dal workbench di pianificazione del carico. Le quantità parziali non possono essere rilasciate se una o più dimensioni sopra **Ubicazione** non sono specificate.

Per ulteriori informazioni, vedere [Criteri flessibili di prenotazione delle dimensioni a livello di magazzino](flexible-warehouse-level-dimension-reservation.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]