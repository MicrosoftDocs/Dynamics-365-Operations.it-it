---
title: Panoramica dei materiali pericolosi
description: Questo argomento fornisce una panoramica delle funzionalità correlate alla gestione e alla documentazione dei materiali pericolosi per la gestione delle informazioni sul prodotto e la gestione del magazzino.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 34c0a19308bb5159faa9a4ab06bf65e58da0deb1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430901"
---
# <a name="hazardous-materials-overview"></a>Panoramica dei materiali pericolosi

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Per rimanere conformi alle normative sulla spedizione e sul trasporto, le organizzazioni che spediscono materiali classificati come merci pericolose devono includere documenti aggiuntivi con le loro spedizioni. La funzione dei materiali pericolosi consente ai clienti di memorizzare le informazioni relative agli articoli rilasciati. Queste informazioni possono quindi essere utilizzate per preparare la documentazione di spedizione. Un'organizzazione che spedisce merci pericolose deve avere propri processi e procedure per la gestione del processo di spedizione. Microsoft Dynamics 365 Supply Chain Management è solo uno strumento che può aiutare a generare i documenti richiesti.

Il diagramma seguente illustra i passaggi necessari per impostare e utilizzare la funzione dei materiali pericolosi.

![Impostazione e utilizzo della funzione dei materiali pericolosi](media/hazmat-overview.png "Impostazione e utilizzo della funzione dei materiali pericolosi")

La funzione dei materiali pericolosi viene impostata nella gestione delle informazioni sul prodotto e fornisce i documenti che possono essere stampati tramite la gestione del magazzino. Pertanto, in linea di massima, queste sono le due aree principali in cui è possibile rivedere, impostare e utilizzare la funzionalità di questa funzione:

- **Gestione informazioni sul prodotto:** impostare codici che possono essere applicati a un prodotto rilasciato.
- **Gestione magazzino**: utilizzare i documenti di spedizione aggiuntivi che verranno stampati per le spedizioni.

> [!IMPORTANT]
> Le funzioni relative ai materiali pericolosi in Supply Chain Management forniscono una raccolta di campi di informazioni sul prodotto utili e funzionalità correlate che possono aiutare a registrare e consultare le informazioni relative ai prodotti pericolosi. Queste funzionalità possono anche aiutarti a progettare e stampare documenti di spedizione che includono le stesse informazioni sui materiali pericolosi che stai spedendo. Tuttavia, il sistema non è automaticamente conforme alle normative applicabili del proprio paese o area geografica. Sebbene questi strumenti abbiano lo scopo di aiutarti a rispettare le normative comuni, non sono sufficienti di per sé né sono garantiti a esserlo. La tua organizzazione è responsabile di conoscere tutte le normative applicabili e di adottare tutte le misure necessarie per rispettarle.

## <a name="product-information-management"></a>Gestione informazioni sul prodotto

Gestione informazioni sul prodotto fornisce una serie di tabelle di configurazione in cui è possibile immettere le informazioni di riferimento per i diversi elenchi di merci pericolose per trasporto via terra, aereo e marittimo.

Quando questa funzionalità è stata sviluppata, sono state considerate le seguenti normative comuni:

- **ADR** - Normative relative al trasporto internazionale di merci pericolose via terra
- **CFR 49** - Normative negli Stati Uniti per il trasporto di merci pericolose
- **IMDG** – Il codice International Marine Dangerous Goods (IMDG)
- **IATA** - Le normative sulle merci pericolose della International Air Transport Association (IATA)

Ogni serie di normative fornisce elenchi standard di merci pericolose e codici di riferimento. Pertanto Supply Chain Management fornisce una tabella di riferimento per i codici comuni in tali elenchi. Ogni elenco include inoltre alcuni codici univoci che possono essere definiti.

Per ulteriori informazioni su come impostare normative e valori per i materiali pericolosi e su come assegnare i valori ai prodotti pertinenti, vedere i seguenti argomenti:

- [Impostare i materiali pericolosi](hazmat-setup.md)
- [Materiali pericolosi in prodotti, ordini, spedizioni e carichi](hazmat-items.md)

## <a name="warehouse-management"></a>Gestione magazzino

Quando si prepara una spedizione in Gestione magazzino, è possibile stampare diversi nuovi report che utilizzano le informazioni impostate in Gestione informazioni sul prodotto. Per ulteriori informazioni sui report disponibili e su come utilizzarli, vedere [Richieste di informazioni e report sui materiali pericolosi](hazmat-reports.md).
