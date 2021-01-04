---
title: Dati master zona di gestione trasporto
description: Questo argomento spiega come la gestione dei trasporti consente di suddividere le ubicazioni geografiche in zone.
author: Henrikan
manager: ''
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSZoneMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2112e7131281cd485b580fd71536981c1ba4aefd
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431615"
---
# <a name="transportation-management-zone-master"></a>Dati master zona di gestione trasporto

[!include [banner](../includes/banner.md)]

La gestione dei trasporti consente di suddividere le ubicazioni geografiche in zone. La suddivisione delle posizioni in zone può aiutare a:

- **Semplificare i prezzi di trasporto** - La determinazione del prezzo per zona può essere più semplice di quella basata sulla posizione individuale, soprattutto quando le località di trasporto sono sparse.
- **Ottimizzare la pianificazione del carico** - Consolidando i carichi per zone.
- **Ottimizzare la pianificazione del percorso** - Assegnando piani di percorso specifici a zone specifiche.

Le zone vengono definite in base ai valori dei campi dei metadati (come paese, intervallo di codici di avviamento postale o servizio del vettore) che qualificano ciascuna zona. Le definizioni di zona non sono necessarie se i prezzi di trasporto non utilizzano un concetto di zona.
