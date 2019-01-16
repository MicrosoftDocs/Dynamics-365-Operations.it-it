---
title: "Spedire ordine da un altro punto vendita usando la funzionalità Addebita invio"
description: "In questo argomento viene descritta la funzionalità Addebita invio."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: e5351086c56d13ef98937aec066be00cdf88fd37
ms.contentlocale: it-it
ms.lasthandoff: 01/04/2019

---

# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Spedire ordine da un altro punto vendita usando la funzionalità Addebita invio

[!include [banner](includes/banner.md)]

Con la funzionalità Addebita invio di Dynamics 365 for Retail, è possibile piazzare ordini cliente in un punto vendita e spedirli da un altro punto vendita.

Gli ordini cliente nel client POS supportano molteplici opzioni di evasione. Alcuni esempi di opzioni di evasione includono:

- Prelievo nello stessa punto vendita a una data diversa.
- Prelievo in un punto vendita differente alla stessa data o a una data differente.
- Spedizione dal magazzino di spedizione predefinito assegnato al punto vendita e consegna a una data specifica.

La funzionalità Addebita invio utilizza le seguenti operazioni POS: Spedisci tutti i prodotti e Spedisci prodotti selezionati. Ciò consente all'addetto del punto vendita di selezionare l'ubicazione "Spedisci da" da cui evadere l'ordine o la riga ordine. Per impostazione predefinita, l'ubicazione "Spedisci da" è il magazzino di spedizione associato al punto vendita. L'addetto del punto vendita può tuttavia modificare tale ubicazione e selezionare qualsiasi punto vendita definito nel gruppo di localizzatori di punti vendita assegnato al punto vendita.

La funzionalità di selezione degli indirizzi di "spedizione" rimane invariata.

I metodi di spedizione che possono essere utilizzati per evadere la riga dell'ordine sono basati sulla configurazione delle modalità di consegna valide per prodotti e indirizzi. Poiché le regole sulle modalità di consegna valide vengono gestite solo in Retail Headquarters (HQ), il client POS esegua una chiamata in tempo reale per recuperare le modalità di consegna valide per una riga di spedizione.

