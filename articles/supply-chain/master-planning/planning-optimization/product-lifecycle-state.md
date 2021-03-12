---
title: Escludere i prodotti con specifici stati del ciclo di vita del prodotto
description: Questo argomento spiega come escludere i prodotti in base al loro stato del ciclo di vita quando viene utilizzata la funzionalità Ottimizzazione pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 371d98eefa482fc3e430f2f0977ddffb9dd0d30e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645094"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>Escludere i prodotti con specifici stati del ciclo di vita del prodotto

[!include [banner](../../includes/banner.md)]

I prodotti rilasciati e le versioni del prodotto rilasciate includono un campo **Stato del ciclo di vita del prodotto**. Questo campo consente di controllare, tra le altre cose, quali prodotti sono inclusi durante la pianificazione generale. È possibile aggiungere, rimuovere e modificare gli stati del ciclo di vita come richiesto andando a **Gestione informazioni sul prodotto \> Impostazione \> Stato del ciclo di vita del prodotto**. Per ogni stato del ciclo di vita del prodotto, impostare l'opzione **Attivo per la pianificazione** su *Sì* se i prodotti con tale stato devono essere inclusi durante la pianificazione generale. Quando l'opzione è impostata su *No*, i prodotti e le varianti associati verranno esclusi da tutta la pianificazione generale e da tutti i calcoli a livello di distinta base (DBA).

I prodotti e le varianti rilasciati in cui il campo **Stato del ciclo di vita del prodotto** viene lasciato vuoto vengono trattati come se avessero uno stato del ciclo di vita del prodotto in cui l'opzione **Attivo per la pianificazione** è impostata su *Sì*. In altre parole, saranno inclusi durante la pianificazione generale.

> [!NOTE]
> Per evitare suggerimenti di offerta non necessari, si consiglia vivamente di associare tutti i prodotti e le varianti rilasciati obsoleti a uno stato del ciclo di vita del prodotto in cui l'opzione **Attivo per la pianificazione** è impostata su *No*. Questo approccio è particolarmente importante quando si lavora con varianti di configurazione del prodotto che non sono riutilizzabili, perché aiuterà a prevenire gli sprechi.

## <a name="related-resources"></a>Risorse correlate

Per ulteriori informazioni relative agli stati del ciclo di vita del prodotto, vedere [Panoramica dello stato del ciclo di vita del prodotto](../../pim/product-lifecycle.md).

Per informazioni dettagliate che includono i passaggi per utilizzare gli stati del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione generale e dal calcolo a livello di DBA, vedere [Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione generale](../../pim/tasks/exclude-products-master-planning.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]