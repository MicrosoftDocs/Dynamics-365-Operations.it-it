---
title: Panoramica della pianificazione generale e delle funzionalità multisito
description: Nella pianificazione generale devono essere prese in considerazione le impostazioni delle dimensioni inventariali relative al sito e al magazzino.
author: t-benebo
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2434"
- intro-internal
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 289763931703eb354ae78fa18f37cd00f1102de8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844911"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Panoramica della pianificazione generale e delle funzionalità multisito

[!include [banner](../includes/banner.md)]

Nella pianificazione generale devono essere prese in considerazione le impostazioni delle dimensioni inventariali relative al sito e al magazzino. 

La dimensione sito è obbligatoria ed è possibile impostare la dimensione magazzino come obbligatoria.

Quando una dimensione è obbligatoria, è necessario immettere un valore di dimensione in tutte le operazioni di magazzino. Pertanto, durante la pianificazione principale, il sito e il magazzino per la domanda iniziale sono noti. La dimensione sito è inoltre una dimensione coerente. Di conseguenza, durante l'esplosione della domanda a livello inferiore, il valore del sito rimane invariato.

Quando invece il magazzino non è impostato come obbligatorio, potrebbe non essere ricavabile dalla domanda iniziale. Il motore di pianificazione dovrà determinare il magazzino da utilizzare in base alle impostazioni definite per l'articolo, i singoli magazzini e i dettagli della riga dell'ordine.

Negli articoli riportati di seguito viene descritta la logica in base alla quale il motore di pianificazione determina il magazzino da utilizzare a seconda delle impostazioni definite.

[Pianificazione generale a livello di sito e magazzino, magazzino obbligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Pianificazione generale per copertura a livello di sito, magazzino obbligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Pianificazione generale a livello di sito e magazzino, magazzino non obbligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Pianificazione generale per copertura a livello di sito, magazzino non obbligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Determinare la versione DBA](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]