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
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6527c4887ccd3085d63dd64c104a94e6354f536b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996461"
---
# <a name="transportation-management-zone-master"></a><span data-ttu-id="ec7a7-103">Dati master zona di gestione trasporto</span><span class="sxs-lookup"><span data-stu-id="ec7a7-103">Transportation management zone master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec7a7-104">La gestione dei trasporti consente di suddividere le ubicazioni geografiche in zone.</span><span class="sxs-lookup"><span data-stu-id="ec7a7-104">Transport management lets you divide geographic locations into zones.</span></span> <span data-ttu-id="ec7a7-105">La suddivisione delle posizioni in zone può aiutare a:</span><span class="sxs-lookup"><span data-stu-id="ec7a7-105">Dividing locations into zones can help to:</span></span>

- <span data-ttu-id="ec7a7-106">**Semplificare i prezzi di trasporto** - La determinazione del prezzo per zona può essere più semplice di quella basata sulla posizione individuale, soprattutto quando le località di trasporto sono sparse.</span><span class="sxs-lookup"><span data-stu-id="ec7a7-106">**Simplify transportation pricing** – Zone-wise pricing can be simpler than individual location-based pricing, especially when transportation locations are scattered.</span></span>
- <span data-ttu-id="ec7a7-107">**Ottimizzare la pianificazione del carico** - Consolidando i carichi per zone.</span><span class="sxs-lookup"><span data-stu-id="ec7a7-107">**Optimize load planning** – By consolidating loads by zones.</span></span>
- <span data-ttu-id="ec7a7-108">**Ottimizzare la pianificazione del percorso** - Assegnando piani di percorso specifici a zone specifiche.</span><span class="sxs-lookup"><span data-stu-id="ec7a7-108">**Optimize route planning** – By assigning specific route plans to specific zones.</span></span>

<span data-ttu-id="ec7a7-109">Le zone vengono definite in base ai valori dei campi dei metadati (come paese, intervallo di codici di avviamento postale o servizio del vettore) che qualificano ciascuna zona.</span><span class="sxs-lookup"><span data-stu-id="ec7a7-109">You define zones based on the metadata field values (such as country, zip code range, or carrier service) that qualify each zone.</span></span> <span data-ttu-id="ec7a7-110">Le definizioni di zona non sono necessarie se i prezzi di trasporto non utilizzano un concetto di zona.</span><span class="sxs-lookup"><span data-stu-id="ec7a7-110">Zone definitions aren't required if your transportation pricing doesn't employ a zone concept.</span></span>
