---
title: Risolvere i problemi della configurazione del magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante la configurazione di Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 9bbe92627f53b3b4b04597be144d602b3cae7ed7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646109"
---
# <a name="troubleshoot-warehouse-configuration"></a>Risolvere i problemi della configurazione del magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante la configurazione di Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>Viene visualizzato il seguente messaggio di errore: "La targa o l'ubicazione non è valida."

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato questo messaggio di errore quando si esegue la scansione di un ID targa o un'ubicazione.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Assicurarsi che l'ID targa non sia prenotato da qualcos'altro. Questo problema si verificava quando il valore scansionato da un utente nell'app del magazzino era sia un'ubicazione valida che un ID targa valido. Tuttavia, questo problema è stato risolto nella versione 10.0.11.

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a>Viene visualizzato il seguente messaggio di errore: "La targa deve essere specificata per questa ubicazione."

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato questo messaggio di errore se si crea un ordine di trasferimento utilizzando un magazzino abilitato per la gestione avanzata del magazzino (WMS) e quindi, al termine del lavoro, si tenta di confermare la spedizione.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Il campo **Ubicazione predefinita entrata** è vuoto per un magazzino di transito del magazzino di provenienza. Per risolvere questo problema, specificare un'ubicazione di ricevimento predefinita nel magazzino di transito. Assicurarsi che questa ubicazione sia controllata dalla targa.

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile creare una riga del modello di lavoro per la modifica dello stato dell'inventario perché il tipo di lavoro non è valido. Selezionare un tipo di lavoro diverso."

### <a name="issue-description"></a>Descrizione del problema

Per un modello di lavoro, non è possibile selezionare *Modifica stato inventario* nella colonna **Tipo di lavoro** della sezione **Dettagli modello di lavoro**.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. Il tipo di lavoro *Modifica stato inventario* viene utilizzato solo dai processi di sistema. Non può essere configurato. Poiché l'elenco dei tipi di lavoro è fisso come un'enumerazione, le voci aggiuntive non possono essere filtrate dal menu a discesa **Tipo di lavoro**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Viene visualizzato il seguente messaggio di errore: "La quantità non è valida per l'unità 1%."

### <a name="issue-description"></a>Descrizione del problema

La quantità non è valida per l'unitp *ea* quando è in corso un lavoro di prelievo con più targhe in un'unica ubicazione.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Verificare che i campi **ID gruppo sequenza unità** e **Conversioni unità** del prodotto o della variante di prodotto rilasciato siano impostati correttamente.

Notare che il messaggio di errore è stato migliorato nella versione 10.0.15 (vedere [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Il nuovo messaggio di errore è "La quantità non è valida. Previsto %1 %2."

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Nelle direttive di ubicazione per il lavoro di stoccaggio degli ordini cliente, l'opzione più SKU non valuta più azioni delle direttive di ubicazione.

### <a name="issue-description"></a>Descrizione del problema

Le direttive di ubicazione del tipo di ordine di lavoro *Ordini cliente* e il tipo di lavoro *Stoccaggio* non valutano più azioni della direttiva di ubicazione quando l'opzione **Più SKU** è selezionata. Viene valutata solo la prima azione della direttiva di ubicazione.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Una nuova funzionalità, *Valuta tutte le azioni per le direttive di ubicazione per più SKU*, è stato aggiunta nella versione 10.0.15 (vedere [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Questa funzionalità valuta tutte le azioni per le direttive di ubicazioni per più SKU. Se è necessaria questa funzione, usare [Gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivarla.

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a>Impossibile utilizzare l'app del magazzino per effettuare prelievi parziali.

### <a name="issue-description"></a>Descrizione del problema

Per gli ordini cliente e di trasferimento, non è possibile ignorare gli articoli ed eseguire prelievi parziali.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Nella pagina **Voci di menu del dispositivo mobile**, per ciascuna voce di menu impostata per elaborare ordini cliente o ordini di trasferimento, impostare l'opzione **Consenti suddivisione del lavoro** nella scheda dettaglio **Generale** su *Sì*.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>Come si modifica lo stato dell'inventario per il lavoro con quantità parziale?

### <a name="issue-description"></a>Descrizione del problema

Si desidera modificare lo stato dell'inventario per una quantità parziale di un batch.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per consentire ai lavoratori di apportare questa modifica, è possibile creare una voce di menu per l'app del magazzino. Creare o modificare una voce di menu per una delle seguenti impostazioni nella pagina **Voci di menu del dispositivo mobile**:

- **Modalità:** *Lavoro*
- **Utilizza lavoro esistente:** *No*
- **Processo di creazione lavoro:** *Spostamento*
- **Visualizza stato inventario:** *Sì*

È possibile impostare altri campi nella pagina in base alle proprie esigenze.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]