---
title: Risolvere i problemi di allestimento del carico e spedizioni
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza l'allestimento del carico e le spedizioni in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: f49a91afe9281f912d6d3579ac8e52cb1d8e5b5d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994031"
---
# <a name="troubleshoot-load-building-and-shipments"></a>Risolvere i problemi di allestimento del carico e spedizioni

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza l'allestimento del carico e le spedizioni in Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile creare una riga di carico per questa riga ordine perché contiene dimensioni di inventario non valide."

### <a name="issue-description"></a>Descrizione del problema

Quando si tenta di rilasciare un ordine di reso cliente al magazzino, viene visualizzato il seguente messaggio di errore:

> Impossibile creare una riga di carico per questa riga ordine perché contiene dimensioni di inventario non valide. Non è possibile fare riferimento a dimensioni di inventario che si trovano sotto la dimensione di ubicazione nella gerarchia di prenotazione. Rimuovere le dimensioni non valide dalla riga ordine.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Il prodotto non supporta l'elaborazione del carico per un processo di reso cliente. Pertanto, non è possibile rilasciare l'ordine di reso cliente al magazzino.

Nelle transazioni di ordini cliente, non è possibile fare riferimento a dimensioni di inventario che si trovano sotto la dimensione di **ubicazione** nella gerarchia di prenotazione. La risoluzione consiste nel rimuovere le dimensioni non valide dalla riga ordine.

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a>Viene visualizzato il seguente messaggio di errore: "Una delle righe è già caricata. Impossibile rilasciare al magazzino."

### <a name="issue-description"></a>Descrizione del problema

Se si creano manualmente i carichi o se si imposta il processo in modo che i carichi siano già creati prima che avvenga l'immissione della riga dell'ordine cliente, si presume che il rilascio successivo verrà eseguito manualmente e che verranno utilizzati il percorso e la classificazione dal carico.

In un altro possibile scenario, si tenta di eseguire un rilascio automatico al magazzino, ma il processo del ciclo non è riuscito a creare lavoro. Pertanto, viene comunque creata una spedizione o un carico aperto. Questa spedizione o carico aperto blocca quindi i tentativi successivi di rilasciare automaticamente l'ordine fino a quando non si elimina la spedizione o il carico aperto oppure si rielabora manualmente il ciclo.

### <a name="issue-resolution"></a>Risoluzione dei problemi

È possibile rilasciare dalla pagina dell'ordine cliente oppure è possibile eseguire il rilascio automatico dalla pagina di rilascio dell'ordine cliente, solo se non esiste alcun carico prima del rilascio al magazzino. Il carico verrà creato automaticamente dopo l'elaborazione del ciclo.

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile elaborare la correzione della bolla di consegna. La bolla di consegna contiene solo articoli soggetti a processi di gestione del magazzino, in quanto non sono supportati dalla correzione della bolla di consegna."

### <a name="issue-description"></a>Descrizione del problema

Dopo aver registrato una bolla di consegna, non è possibile annullarla, perché il pulsante **Annulla** non è disponibile. Inoltre, non è possibile correggere la bolla di consegna. Se si tenta viene visualizzato questo messaggio di errore.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per correggere i documenti di trasporto registrati per gli articoli abilitati per la gestione avanzata del magazzino (WMS), è necessario che la avvenga dal carico, non dall'ordine.

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a>Come si può creare lavoro da carichi in uscita invece che da cicli?

### <a name="issue-description"></a>Descrizione del problema

Ecco un modo per riprodurre questo problema.

1. Creare un carico in uscita utilizzando una riga ciclo o un ordine di trasferimento.
2. Rilascia il carico al magazzino.
3. Notare che non è stato ancora generato alcun lavoro di prelievo.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Se il lavoro deve essere generato immediatamente quando il carico viene rilasciato, è necessario configurare il modello di ciclo di conseguenza. Sul modello di ciclo, impostare le seguenti opzioni su *Sì*:

- Automatizza creazione ondata
- Elabora ondata al rilascio in magazzino
- Automatizza rilascio ondata

## <a name="i-cant-re-release-a-partially-shipped-load"></a>Impossibile rilasciare nuovamente un carico spedito parzialmente.

### <a name="issue-description"></a>Descrizione del problema

Non è possibile rilasciare un carico spedito parzialmente al magazzino. Quando si effettua il rilascio al magazzino, viene visualizzato il messaggio "Operazione completata", ma non accade nulla e non viene creato alcun lavoro per la quantità rimanente. Questo problema si verifica quando si utilizza la funzionalità di carico di trasporto e c'è una prenotazione incompleta.

### <a name="issue-resolution"></a>Risoluzione dei problemi

[Il problema KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("I carichi parzialmente spediti possono essere nuovamente elaborati e inclusi nel ciclo") è stato corretto nel [rilascio 10.0.15](../get-started/whats-new-scm-10-0-15.md).
