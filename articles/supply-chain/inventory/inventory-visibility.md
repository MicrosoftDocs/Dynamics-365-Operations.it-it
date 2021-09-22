---
title: Panoramica del componente aggiuntivo Visibilità dell'inventario
description: Questo argomento spiega cos'è la visibilità dell'inventario e ne descrive le caratteristiche.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 644eb0d682c35bd604c188aa02e4a6c69b3ff209
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474990"
---
# <a name="inventory-visibility-add-in-overview"></a>Panoramica del componente aggiuntivo Visibilità dell'inventario

[!include [banner](../includes/banner.md)]

Il componente aggiuntivo di Visibilità dell'inventario (chiamato anche *Visibilità dell'inventario*) è un microservizio indipendente e altamente scalabile che permette il monitoraggio dell'inventario in tempo reale. Pertanto, fornisce una visione globale dell'inventario.

I sistemi esterni accedono al servizio tramite API RESTful. In questo modo, possono interrogare le informazioni on-hand su determinati set di dimensioni o apportare modifiche al vostro inventario in diverse fonti di dati personalizzate.

Come un microservizio che è costruito su Microsoft Dataverse, Visibilità dell'inventario fornisce estensibilità. Puoi usare Power Apps per costruire applicazioni. Puoi anche applicare Power BI per fornire funzionalità personalizzate che soddisfino i requisiti aziendali.

È possibile integrare Visibilità dell'inventario con più sistemi di terze parti impostando le opzioni di configurazione per le dimensioni standardizzate dell'inventario e impostando i tipi di transazione. Visibilità dell'inventario supporta anche l'estensibilità personalizzata attraverso quantità calcolate configurabili.

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Integrazione della visibilità dell'inventario con Dynamics 365 Supply Chain Management

La soluzione integrata estrae i dati dell'inventario da Dynamics 365 Supply Chain Management e traccia continuamente i cambiamenti dell'inventario. Per ulteriori informazioni, vedere [Installare e configurare Visibilità inventario](inventory-visibility-setup.md) e [Configurare Visibilità inventario](inventory-visibility-configuration.md).

## <a name="get-a-global-view-of-inventory"></a>Ottenere una visione globale dell'inventario

La soluzione integrata permette di definire le proprie fonti di dati e centralizzare i dati di inventario. Per ulteriori informazioni, vedere [Configurare Visibilità inventario](inventory-visibility-configuration.md).

Ci sono due approcci per visualizzare l'inventario:

- Invia una query attraverso l'API ad alte prestazioni. Questa API può restituire dati di inventario quasi in tempo reale direttamente da un'istanza nella cache. Puoi trovare contratti ed esempi nelle [API pubbliche di Visibilità dell'inventario](inventory-visibility-api.md).
- Visualizza l'elenco grezzo di disponibilità. Questa lista è sincronizzata periodicamente da un'istanza nella cache ed è visibile in Dataverse. Per ulteriori informazioni, vedi l' [applicazione Visibilità dell'inventario](inventory-visibility-power-platform.md).

## <a name="soft-reservations"></a>Prenotazioni morbide

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

La soft reservation si applica quando un'azienda deve riservare una quantità specifica di prodotti per supportare, per esempio, l'adempimento dell'ordine di vendita che evita l'over-selling. Quando un ordine di vendita viene creato e confermato in Supply Chain Management o in altri sistemi di gestione degli ordini, una richiesta di riserva della quantità viene inviata a Visibilità dell'inventario. La visibilità dell'inventario ti permette di riservare i prodotti che hanno dettagli sulle dimensioni e specifici tipi di transazioni d'inventario. (Per maggiori informazioni, vedere l' [applicazione Visibilità dell'inventario](inventory-visibility-power-platform.md)) Dopo che la quantità è stata riservata con successo, viene restituito un ID di prenotazione. Puoi usare questo ID di prenotazione per ricollegarvi all'ordine originale nel Supply Chain Management o in altri sistemi di gestione degli ordini.

La funzionalità è progettata in modo che una prenotazione in Visibilità dell'inventario non cambi la quantità totale. Invece, segnala solo la quantità riservata. (Per questa ragione, si chiama *prenotazione morbida*) La quantità riservata soft può essere compensata quando i prodotti vengono consumati in Supply Chain Management o in un sistema di terze parti chiamando nuovamente l'API per fare una deduzione della quantità e aggiornare la quantità totale in Visibilità dell'inventario. Per maggiori informazioni, vedere [Prenotazioni di visibilità dell'inventario](inventory-visibility-reservations.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
