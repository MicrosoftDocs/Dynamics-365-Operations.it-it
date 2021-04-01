---
title: Materiali pericolosi
description: Questo argomento fornisce informazioni su documenti relativi a materiali pericolosi immagazzinati nel proprio ambiente.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: d27ec5b65cc607c22d97c1dc44bb573bc2772611
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243179"
---
# <a name="hazardous-materials"></a>Materiali pericolosi

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le informazioni sui materiali pericolosi sono incluse in Gestione informazioni sul prodotto. Questo modulo fornisce anche documenti che possono essere stampati mediante Gestione magazzino.

Quando si spediscono materiali classificati come merci pericolose, è necessario includere ulteriori documenti con le spedizioni. La funzionalità Materiale pericoloso consente ai clienti di archiviare informazioni di classificazione e applicarle agli articoli rilasciati. Queste informazioni possono quindi essere utilizzate per preparare la documentazione di spedizione.

> [!IMPORTANT]
> Le funzioni relative ai materiali pericolosi in Microsoft Dynamics 365 Supply Chain Management forniscono una raccolta di campi di informazioni sul prodotto utili e funzionalità correlate che possono aiutare a registrare e consultare le informazioni relative ai prodotti pericolosi. Queste funzionalità possono anche aiutarti a progettare e stampare documenti di spedizione che includono le stesse informazioni sui materiali pericolosi che stai spedendo. Tuttavia, il sistema non è automaticamente conforme alle normative applicabili del proprio paese o area geografica. Sebbene questi strumenti abbiano lo scopo di aiutarti a rispettare le normative comuni, non sono sufficienti di per sé né sono garantiti a esserlo. La tua organizzazione è responsabile di conoscere tutte le normative applicabili e di adottare tutte le misure necessarie per rispettarle.

Per poter utilizzare questa funzionalità è necessario eseguire la configurazione seguente:

- **Gestione informazioni sul prodotto:** impostare codici che possono essere applicati ai prodotti rilasciati.
- **Gestione magazzino:** utilizzare documenti di spedizione aggiuntivi per stampare informazioni sulla spedizione.

## <a name="product-information-management"></a>Gestione informazioni sul prodotto

Gestione informazioni sul prodotto include una serie di tabelle di configurazione in cui è possibile aggiungere le informazioni di riferimento fornite negli elenchi di merci pericolose per trasporto via terra, aereo e marittimo.

Di seguito sono riportate alcune normative a cui si fa spesso riferimento:

- **ADR** - Normative relative al trasporto internazionale di merci pericolose via terra
- **CFR 49** - Normative negli Stati Uniti per il trasporto di merci pericolose
- **IMDG** – Il codice International Marine Dangerous Goods (IMDG)
- **IATA** - Le normative sulle merci pericolose della International Air Transport Association (IATA)

Ognuna di queste normative presenta un elenco di merci pericolose che include codici di riferimento. Gli elenchi per ciascun tipo di trasporto sono combinati in classificazioni internazionali condivise. Supply Chain Management fornisce una tabella di riferimento per i codici condivisi in tali elenchi. Ogni elenco include inoltre alcuni codici univoci che possono essere definiti.

Per iniziare a configurare queste informazioni, creare una normativa che è possibile utilizzare per configurare i parametri iniziali.

## <a name="warehouse-management"></a>Gestione magazzino

Quando si prepara una spedizione, è possibile stampare vari nuovi report. Questi report utilizzano le informazioni impostate in Gestione informazioni sul prodotto.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]