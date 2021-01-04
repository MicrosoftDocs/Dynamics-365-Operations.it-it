---
title: Risolvere i problemi di prelievo e imballaggio
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante il prelievo e l'imballaggio in Microsoft Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 74854fa95837dd8a133860e2a017be4c92ff84a3
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645479"
---
# <a name="troubleshoot-picking-and-packing"></a>Risolvere i problemi di prelievo e imballaggio

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante il prelievo e l'imballaggio in Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile lasciare vuoto l'ubicazione della dimensione se è impostato il numero di serie della dimensione".

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato questo messaggio di errore se si crea un ordine di trasferimento per un articolo con numero di serie utilizzando un magazzino abilitato per la gestione avanzata del magazzino (WMS) e quindi, al termine del lavoro, si tenta di confermare la spedizione.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Il campo **Ubicazione predefinita entrata** è vuoto per un magazzino di transito del magazzino di provenienza. Per risolvere questo problema, specificare un'ubicazione di ricevimento predefinita nel magazzino di transito. Assicurarsi che questa ubicazione sia controllata dalla targa.

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a>Viene visualizzato il seguente messaggio di errore: "Targa non valida".

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato questo messaggio di errore nell'app del magazzino quando si esegue la scansione di un ID targa.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Assicurarsi che l'ID della targa sia presente nella tabella delle targhe e che gli articoli e le quantità sulla targa siano disponibili (in altre parole, non sono bloccati).

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a>Viene visualizzato il seguente messaggio di errore: "Il campo "Peso carico"(=-%1) può contenere solo numeri positivi. L'aggiornamento è stato annullato."

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato questo messaggio di errore se è presente un lavoro aperto quando si elabora il lavoro da ubicazioni di imballaggio a ubicazioni di staging o da ubicazioni di staging a ubicazioni di ancoraggio.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per risolvere questo problema, andare a **Amministrazione di sistema \> Attività periodiche \> Database \> Controllo coerenza** ed eseguire il processo **Controllo coerenza peso carico magazzino**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Viene visualizzato il seguente messaggio di errore: "La quantità non è valida per l'unità %1."

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato questo messaggio di errore quando si tenta di eseguire un *prelievo condiviso* su più batch.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Il magazziniere deve utilizzare il processo *Prelievo breve* nell'app del magazzino. Se si tenta di prelevare più batch dalla stessa ubicazione, è possibile anche utilizzare l'opzione **Completo** nell'app del magazzino.

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a>Non èpossibile spostare l'inventario in un'ubicazione controllata dalla targa.

### <a name="issue-description"></a>Descrizione del problema

Non è possibile ridurre le quantità prelevate su un carico.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Nelle versioni precedenti, non è possibile ridurre le quantità prelevate su un carico. Tuttavia, ora è possibile annullare il prelievo in un'ubicazione controllata dalla targa. È necessario specificare un valore **Ubicazione** e un valore **Targa** per la riga di carico nella pagina **Riduci la quantità prelevata**.

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a>È possibile stampare una bolla di consegna o il contenuto di un imballaggio per magazzino?

### <a name="issue-description"></a>Descrizione del problema

Si desidera stampare una bolla di consegna o il contenuto di un imballaggio per magazzino o sito nella pagina **Aggiornamento della riga del modello di controllo di lavoro**.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Quando si stampa un documento utilizzando le impostazioni di gestione della stampa, limitare l'ambito (sito/magazzino) tramite la gestione della stampa anziché selezionando **Modifica impostazioni di stampa** nella pagina **Aggiornamento della riga del modello di controllo di lavoro**.

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Impossibile annullare un documento di trasporto dopo che è stato registrato da un ordine cliente.

### <a name="issue-description"></a>Descrizione del problema

Quando i processi di prelievo e spedizione sono abilitati per WMS, non è possibile annullare un documento di trasporto dopo che è stato registrato da un ordine cliente.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per correggere i documenti di trasporto registrati per gli articoli abilitati per WMS, la registrazione deve avvenire dal carico, non dall'ordine. Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. In generale, un ordine cliente prelevato e spedito tramite i processi di gestione del magazzino può essere aggiornato dal documento di trasporto dal carico o dalla spedizione e dal documento dell'ordine cliente stesso. Tuttavia, se si aggiorna l'ordine cliente dal documento dell'ordine cliente, lo storno del documento di trasporto non può ancora essere eseguito dal carico o dall'ordine cliente. Pertanto, si consiglia di utilizzare la registrazione della bolla di accompagnamento dal carico. In questo caso verrà abilitato lo storno che deve essere eseguito dal carico.

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile trovare lavoro sufficiente per il cluster".

### <a name="issue-description"></a>Descrizione del problema

Quando si usa il processo *Prelievo cluster diretto dal sistema*, se si configura un profilo cluster in cui, ad esempio, è possibile selezionare 10 ubicazioni, il processo funziona come pianificato quando c'è abbastanza lavoro per selezionare 10 ubicazioni. Tuttavia, se sono presenti solo otto ubicazioni da selezionare, viene visualizzato questo messaggio di errore perché non c'è lavoro sufficiente per un cluster.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per risolvere questo problema, modificare il profilo del cluster e impostare l'opzione **Attiva posizioni** su *No*.
