---
title: Risolvere i problemi relativi alle operazioni di magazzino in entrata
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in entrata in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 6d7fcb2ed32c57b8701bee5b90889a0a63e1f7061aa9014480ae8c543e1f229a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748669"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Risolvere i problemi relativi alle operazioni di magazzino in entrata

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in entrata in Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>Viene visualizzato il seguente messaggio di errore: "Ordine di controllo qualità %1 è stato generato. Impossibile trovare il profilo cluster per verificare la configurazione."

### <a name="issue-description"></a>Descrizione del problema

Questo messaggio di errore è correlato a un processo di ricezione in cui è attivata la gestione della qualità (QMS). A seconda delle configurazioni nel proprio ambiente, ulteriori dettagli sulla transazione che sta generando il messaggio di errore potrebbero aiutare a risolvere il problema.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Innanzitutto, esaminare l'impostazione di [prelievo cluster](set-up-cluster-picking.md) e assicurarsi che i profili del cluster siano impostati correttamente. Non è possibile utilizzare una voce di menu del dispositivo mobile per la selezione del cluster a meno che non siano stati configurati i profili del cluster. A seconda del proprio ambiente, potrebbe essere necessario rivedere anche altre configurazioni correlate.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>La ricezione di targhe miste non funziona per nessun codice smaltimento eccetto il credito.

### <a name="issue-description"></a>Descrizione del problema

Quando il campo **Azione** per un codice smaltimento è impostato su *Credito* o *Scarti*, è possibile usare solo la voce di menu [Ricevimento targa mista](mixed-license-plate-receiving.md) per elaborare gli articoli restituiti.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. Attualmente solo i [codici smaltimento](../service-management/set-up-disposition-codes.md) dove il campo **Azione** è impostato su *Credito* o *Scarti* sono supportati per la ricezione di targhe miste.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>Quando si esegue l'attività periodica Aggiorna entrate prodotti, vengono confermati gli ordini fornitore non confermati.

### <a name="issue-description"></a>Descrizione del problema

Dopo aver eseguito l'attività periodica *Aggiorna entrate prodotti*, il sistema conferma automaticamente gli ordini fornitore non confermati con stato di transazione di magazzino *Registrato*.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Una nuova funzione di gestione del carico in entrata, *Entrata in eccesso di quantità di carico*, risolve questo problema. Per attivare questa funzionalità andare all'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attivare le seguenti funzionalità (in questo ordine):

1. Associa operazioni di magazzino ordine fornitore con carico
1. Entrata in eccesso di quantità di carico

Per ulteriori informazioni, vedere [Registrare le quantità di prodotto registrate rispetto a ordini fornitore](inbound-load-handling.md#post-registered-quantities).

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a>Quando registro gli ordini in entrata, ricevo il seguente messaggio di errore: "La quantità non è valida".

### <a name="issue-description"></a>Descrizione del problema

Se il campo **Criteri di raggruppamento delle targhe** è impostato su *Definito dall'utente* per una voce di menu del dispositivo mobile utilizzata per registrare gli ordini in entrata, viene visualizzato un messaggio di errore ("La quantità non è valida") e non è possibile completare la registrazione.

### <a name="issue-cause"></a>Causa del problema

Quando *Definito dall'utente* viene utilizzato come criterio di raggruppamento delle targhe, il sistema suddivide l'inventario in entrata in targhe separate, come indicato dal gruppo di sequenze unità. Se vengono utilizzati numeri di batch o di serie per tenere traccia dell'articolo ricevuto, le quantità di ciascun batch o serie devono essere specificate per targa registrata. Se la quantità specificata per una targa supera la quantità che deve ancora essere ricevuta per le dimensioni correnti, viene visualizzato il messaggio di errore.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Quando registri un artciolo utilizzando una voce di menu del dispositivo mobile in cui il campo **Criterio di raggruppamento delle targhe** è impostato su *Definito dall'utente*, il sistema potrebbe richiedere la conferma o l'immissione di numeri di targa, numeri di lotto o numeri di serie.

Nella pagina di conferma della targa, il sistema mostrerà la quantità allocata per la targa corrente. Sulle pagine di conferma del batch o della serie, il sistema mostrerà la quantità che deve ancora essere ricevuta sulla targa corrente. Comprenderà anche un campo in cui è possibile inserire la quantità da registrare per quella combinazione di targa e batch o numero di serie. In questo caso, assicurati che la quantità che si sta registrando per la targa non superi la quantità che deve ancora essere ricevuta.

In alternativa, se vengono generate troppe targhe durante la registrazione dell'ordine in entrata, il valore del campo **Criterio di raggruppamento delle targhe** può essere modificato in *Raggruppamento targhe*, è possibile assegnare un nuovo gruppo di sequenze di unità all'articolo o l'opzione **Raggruppamento targhe** per il gruppo di sequenze di unità può essere disattivata.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
