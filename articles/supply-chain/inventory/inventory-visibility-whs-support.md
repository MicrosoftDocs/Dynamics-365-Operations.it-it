---
title: Supporto Inventory Visibility per articoli WHS
description: Questo argomento descrive il supporto di Visibilità inventario per gli articoli abilitati per i processi di magazzino avanzati (articoli WHS).
author: yufeihuang
ms.date: 03/10/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: cfbff05697f4159cb74d110887b8029f28fbf96b
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625398"
---
# <a name="inventory-visibility-support-for-whs-items"></a>Supporto Inventory Visibility per articoli WHS

[!include [banner](../includes/banner.md)]

Questo argomento descrive il supporto di Visibilità inventario per gli articoli abilitati per i processi di magazzino avanzati (articoli WHS). La funzionalità che aggiunge questa capacità alla visibilità inventario è denominata *WHS avanzato*.

## <a name="whs-items"></a>Articoli WHS

Un articolo WHS è un articolo abilitato per i processi di magazzino avanzati (WHS) ed elaborato in un magazzino che è anche abilitato WHS.

Per ulteriori informazioni su WHS e il modulo **Gestione magazzino** in Microsoft Dynamics 365 Supply Chain Management, vedi [Panoramica di Gestione magazzino](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Ambito della funzione

La funzione WHS avanzata per la visibilità inventario si concentra sui calcoli delle quantità disponibili basati su query delle scorte disponibili. La funzionalità non consente di utilizzare Visibilità inventario per gestire le attività di elaborazione del magazzino in generale. La visibilità inventario non espone concetti specifici del magazzino ai suoi utenti. Di seguito sono riportati alcuni esempi di concetti:

- Gerarchia prenotazioni
- Se un articolo o un magazzino è abilitato per WHS
- ID gruppo di sequenze unità
- Processi specifici del magazzino, come spedizioni, carichi, cicli e lavori

Visibilità inventario deduce queste informazioni, in base ai dati inviati da Supply Chain Management. I dati specifici di WHS (in altre parole, i dati della tabella `WHSInventReserve`) non sono visibili agli utenti.

Quando si utilizza la funzione WHS avanzata per la visibilità inventario, tutti i risultati delle query saranno identici ai risultati delle query eseguite direttamente in Supply Chain Management. Tuttavia, non saranno identici ai risultati delle query eseguite utilizzando l'app per dispositivi mobili Warehouse Management, poiché l'app per dispositivi mobili utilizza una logica di calcolo leggermente diversa.

## <a name="when-to-use-the-feature"></a>Quando utilizzare la funzionalità

Ti consigliamo di utilizzare la funzione WHS avanzata per la visibilità inventario negli scenari in cui sono soddisfatte tutte le seguenti condizioni:

- Stai sincronizzando i dati di Supply Chain Management con la visibilità inventario.
- Stai utilizzando WHS in Supply Chain Management.
- Gli utenti effettuano prenotazioni per gli articoli WHS a livelli diversi dal livello di magazzino (ad esempio, perché stai utilizzando il lavoro di magazzino).

In altri scenari, i risultati delle query disponibili saranno gli stessi, indipendentemente dal fatto che la funzionalità WHS avanzata per la visibilità dell'inventario sia abilitata. Inoltre, le prestazioni saranno migliori se non si abilita la funzionalità in questi scenari, perché ci sono meno calcoli e meno sovraccarico.

## <a name="enable-the-advanced-whs-feature-for-inventory-visibility"></a>Abilitare la funzione WHS avanzata per la visibilità inventario

Per abilitare la funzione WHS avanzata per la visibilità inventario, segui questi passaggi.

1. Accedi a Supply Chain Management come amministratore.
1. Apri l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e abilita le seguente funzionalità in questo ordine:

    1. *Integrazione di Visibilità magazzino*
    1. *Abilita articoli di magazzino in Visibilità inventario*

1. Vai a **Inventory Management \> Impostazione \> Visibilità dell'inventario integration parameters**.
1. Nella Scheda **Abilita articoli WHS**, imposta l'opzione **Abilita articoli WHS** su *Sì*.
1. Accedere a Power Apps.
1. Apri la pagina **Configurazione**, e poi, nella scheda **Gestione funzionalità** attiva la funzione *AdvancedWHS*.
1. In Supply Chain Management vai in **Gestione articoli \> Attività periodiche \> Integrazione di Visibilità magazzino**.
1. Nel riquadro azioni seleziona **Disabilita** per disabilitare temporaneamente la visibilità inventario.
1. Nel riquadro azioni seleziona **Abilita** per riattivare la visibilità inventario. Il componente aggiuntivo viene ricaricato e la nuova funzionalità è ora abilitata. I tuoi dati relativi a WHS iniziano a essere sincronizzati con la visibilità inventario.

## <a name="query-on-hand-quantities-of-whs-items"></a>Query delle quantità disponibili di articoli WHS

Per eseguire query degli articoli WHS, usi la stessa [API e sintassi dei messaggi](inventory-visibility-api.md) che utilizzi per articoli non WHS. Non è necessario specificare se un articolo è un articolo WHS o un articolo non WHS. Visibilità inventario distingue automaticamente gli articoli, in base ai dati archiviati.

I risultati delle query per gli articoli WHS sono essenzialmente gli stessi dei risultati per gli articoli non WHS. L'unica differenza è che le seguenti misure fisiche dall'origine dati `fno` vengono calcolate in base alla logica WHS in Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Tutte le altre misure fisiche vengono calcolate esattamente come quando la funzione WHS avanzata per la visibilità inventario è disabilitata.

Per informazioni dettagliate su come funzionano i calcoli disponibili per gli articoli WHS, vedi il white paper [Prenotazioni in Gestione Magazzino](https://www.microsoft.com/download/details.aspx?id=43284).

Le entità di dati che vengono esportate in Dataverse non possono ancora aggiornare le quantità per gli articoli WHS. Le quantità mostrate nelle entità di dati sono corrette sia per gli articoli non WHS che per le quantità che non sono interessate dalla logica WHS (cioè le misure eccetto `AvailPhysical`, `AvailOrdered`, `ReservPhysical`, e `ReservOrdered` nell'origine dati `fno`).

Sono vietate le modifiche alle quantità di articoli WHS archiviate nell'origine dati di Supply Chain Management. Come per altre funzionalità di Visibilità inventario, questa restrizione viene applicata per aiutare a prevenire i conflitti.

## <a name="soft-reservations-on-whs-items-in-inventory-visibility"></a>Prenotazione temporanee di articoli WHS di visibilità inventario

In generale, le [prenotazioni temporanee](inventory-visibility-reservations.md) sugli articoli WHS sono supportate. È possibile includere misure fisiche relative a WHS nei calcoli delle prenotazioni temporanee. 

In una nota limitazione, il calcolo *disponibile per la prenotazione* non è attualmente supportato per gli articoli WHS. Pertanto, se è presente una prenotazione al di sopra delle dimensioni correnti in cui si verifica una prenotazione temporanea, il calcolo *disponibile per la prenotazione* non è corretto. Le prenotazioni temporanee non saranno interessate quando l'opzione **ifCheckAvailForReserv** è disabilitata nell'[API di prenotazione temporanea](inventory-visibility-api.md#create-one-reservation-event).

Questo vincolo si applica anche alle funzionalità e alle personalizzazioni basate su prenotazioni temporanee (come l'allocazione).

## <a name="calculate-available-to-promise-quantities"></a>Calcolare le quantità available-to-promise

La soluzione supporta pienamente il calcolo [available-to-promise (ATP)](inventory-visibility-available-to-promise.md) per gli articoli WHS. Puoi definire i calcoli ATP senza preoccuparti dei dettagli specifici della WHS.
