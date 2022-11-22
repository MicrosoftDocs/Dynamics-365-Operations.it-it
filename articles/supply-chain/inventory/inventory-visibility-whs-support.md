---
title: Supporto Inventory Visibility per articoli WMS
description: Questo articolo descrive il supporto di Visibilità inventario per gli articoli abilitati per i processi di gestione del magazzino (articoli WMS).
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: bed402ecf20c19e81b2687efd90dba600460971a
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762741"
---
# <a name="inventory-visibility-support-for-wms-items"></a>Supporto Inventory Visibility per articoli WMS

[!include [banner](../includes/banner.md)]

Questo articolo descrive il supporto di Visibilità inventario per gli articoli abilitati per i processi di gestione del magazzino (WMS). La funzionalità che aggiunge questa capacità alla visibilità inventario è denominata *WMS avanzato*.

## <a name="wms-items"></a>Articoli WMS

Un articolo WMS è un articolo abilitato per i processi di gestione del magazzino (WMS) ed elaborato in un magazzino che è anche abilitato per WMS.

Per ulteriori informazioni su WMS e il modulo **Gestione magazzino** in Microsoft Dynamics 365 Supply Chain Management, vedi [Panoramica di Gestione magazzino](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Ambito della funzione

La funzione WMS avanzata per la visibilità inventario si concentra sui calcoli delle quantità disponibili basati su query delle scorte disponibili. La funzionalità non consente di utilizzare Visibilità inventario per gestire le attività di elaborazione del magazzino in generale. La visibilità inventario non espone concetti specifici del magazzino ai suoi utenti. Di seguito sono riportati alcuni esempi di concetti:

- Gerarchia prenotazioni
- Se un articolo o un magazzino è abilitato per WMS
- ID gruppo di sequenze unità
- Processi specifici del magazzino, come spedizioni, carichi, cicli e lavori

Visibilità inventario deduce queste informazioni, in base ai dati inviati da Supply Chain Management. I dati specifici di WMS (in altre parole, i dati della tabella `WHSInventReserve`) non sono visibili agli utenti.

Quando si utilizza la funzione WMS avanzata per la visibilità inventario, tutti i risultati delle query saranno identici ai risultati delle query eseguite direttamente in Supply Chain Management. Tuttavia, non saranno identici ai risultati delle query eseguite utilizzando l'app per dispositivi mobili Warehouse Management, poiché l'app per dispositivi mobili utilizza una logica di calcolo leggermente diversa.

## <a name="when-to-use-the-feature"></a>Quando utilizzare la funzionalità

Ti consigliamo di utilizzare la funzione WMS per la visibilità inventario negli scenari in cui sono soddisfatte tutte le seguenti condizioni:

- Stai sincronizzando i dati di Supply Chain Management con la visibilità inventario.
- Stai utilizzando WMS in Supply Chain Management.
- Gli utenti effettuano prenotazioni per gli articoli WMS a livelli sotto il livello di magazzino (ad esempio, a livello di targa perché stai elaborando il lavoro di magazzino).

In altri scenari, i risultati delle query disponibili saranno gli stessi, indipendentemente dal fatto che la funzionalità WMS avanzata per la visibilità dell'inventario sia abilitata. Inoltre, le prestazioni saranno migliori se non si abilita la funzionalità in questi scenari, perché ci sono meno calcoli e meno sovraccarico.

## <a name="enable-the-wms-feature-for-inventory-visibility"></a>Abilitare la funzionalità WMS per la visibilità inventario

Per abilitare la funzionalità WMS per la visibilità inventario, segui questi passaggi.

1. Accedi a Supply Chain Management come amministratore.
1. Apri l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e abilita le seguente funzionalità in questo ordine:

    1. *Integrazione di Visibilità magazzino*
    1. *Abilita articoli di magazzino in Visibilità inventario*

1. Vai a **Inventory Management \> Impostazione \> Visibilità dell'inventario integration parameters**.
1. Nella Scheda **Abilita articoli WMS**, imposta l'opzione **Abilita articoli WMS** su *Sì*.
1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Apri la pagina **Configurazione**, e poi, nella scheda **Gestione funzionalità** attiva la funzione *AdvancedWHS*.
1. In Supply Chain Management vai in **Gestione articoli \> Attività periodiche \> Integrazione di Visibilità magazzino**.
1. Nel riquadro azioni seleziona **Disabilita** per disabilitare temporaneamente la visibilità inventario.
1. Nel riquadro azioni seleziona **Abilita** per riattivare la visibilità inventario. Il componente aggiuntivo viene ricaricato e la nuova funzionalità è ora abilitata. I tuoi dati relativi a WMS iniziano a essere sincronizzati con la visibilità inventario.

## <a name="query-on-hand-quantities-of-wms-items"></a>Query delle quantità disponibili di articoli WMS

Per eseguire query degli articoli WMS, usi la stessa [API e sintassi dei messaggi](inventory-visibility-api.md) che utilizzi per articoli non WMS. Non è necessario specificare se un articolo è un articolo WMS o un articolo non WMS. Visibilità inventario distingue automaticamente gli articoli, in base ai dati archiviati.

I risultati delle query per gli articoli WMS sono essenzialmente gli stessi dei risultati per gli articoli non WMS. L'unica differenza è che le seguenti misure fisiche dall'origine dati `fno` vengono calcolate in base alla logica WMS in Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Tutte le altre misure fisiche vengono calcolate esattamente come quando la funzionalità WMS per la visibilità inventario è disabilitata.

Per informazioni dettagliate su come funzionano i calcoli disponibili per gli articoli WMS, vedi il white paper [Prenotazioni in Gestione Magazzino](https://www.microsoft.com/download/details.aspx?id=43284).

## <a name="on-hand-list-view-and-data-entity-for-wms-items"></a>Visualizzazione elenco disponibilità ed entità dati per gli articoli WMS

La pagina **Precarica il riepilogo di visibilità inventario** fornisce una vista per l'entità *Risultati di precaricamento delle query sull'indice di disponibilità*. Diversamente dall'entità *Riepilogo inventario*, l'entità *Risultati di precaricamento delle query sull'indice di disponibilità* fornisce un elenco di scorte disponibili per i prodotti insieme alle dimensioni selezionate. La visibilità inventario sincronizza i dati di riepilogo precaricati ogni 15 minuti.

Se utilizzi Visibilità dell'inventario con gli articoli WMS e desideri visualizzare l'elenco delle disponibilità per gli articoli WMS, è consigliabile abilitare la funzionalità *Precarica riepilogo visibilità inventario* (vedi anche [Precaricare una query di scorte disponibili ottimizzata](inventory-visibility-power-platform.md#preload-streamlined-onhand-query)). Un'entità di dati corrispondente in Dataverse archivia il risultato del precaricamento della query, che viene aggiornato ogni 15 minuti. Il nome dell'entità dati è `Onhand Index Query Preload Result`.

> [!IMPORTANT]
> L'entità Dataverse è di sola lettura. Puoi visualizzare ed esportare i dati nelle entità Visibilità inventario, ma **non modificarli**.

Sono vietate le modifiche alle quantità di articoli WMS archiviate nell'origine dati (`fno`) di Supply Chain Management. Questo comportamento corrisponde al comportamento di altre funzionalità di Visibilità inventario. Questa restrizione viene applicata per aiutare a prevenire i conflitti.

## <a name="wms-item-compatibility-for-other-functions-in-inventory-visibility"></a>Compatibilità articoli WMS per altre funzioni in Visibilità inventario

[Prenotazioni temporanee](inventory-visibility-reservations.md) e l'[allocazione di scorte](inventory-visibility-allocation.md) di articoli WMS sono supportati. È possibile includere misure fisiche relative a WMS nei calcoli delle allocazioni e delle prenotazioni temporanee.

## <a name="calculate-available-to-promise-quantities"></a>Calcolare le quantità available-to-promise

La soluzione supporta pienamente il calcolo [available-to-promise (ATP)](inventory-visibility-available-to-promise.md) per gli articoli WMS. Puoi definire i calcoli ATP senza preoccuparti dei dettagli specifici della WMS.
