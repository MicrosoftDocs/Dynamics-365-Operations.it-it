---
title: Ritardi
description: "Questo articolo fornisce informazioni sulle date ritardate nella pianificazione generale. Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9113c7728c5d23b70e3809bab31136aff63c6acf
ms.lasthandoff: 03/31/2017


---

# <a name="delays"></a>Ritardi

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni sulle date ritardate nella pianificazione generale. Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta.

La pianificazione generale può calcolare la prima data di evasione possibile per una transazione, in base ai lead time, alla disponibilità del materiale, alla disponibilità della capacità e a vari parametri di pianificazione. 

Se la pianificazione generale calcola una data dell'ordine che precede la data corrente, l'ordine non può essere evaso in tempo. Di conseguenza, l'ordine viene ritardato. In questo caso, la pianificazione generale pianifica in anticipo l'ordine a partire dalla data corrente e include i lead time. Questi lead time cominciano con qualsiasi articolo componente di livello inferiore. L'ordine riceve quindi una data ritardata. Una data ritardata è una data di scadenza realistica basata sui dati correnti. La pianificazione generale calcola anche il numero di giorni di ritardo. 

In alcune situazioni, è possibile scegliere di non calcolare i ritardi, ad esempio quando gli utenti sanno che possono velocizzare i lead time selezionando modalità di consegna alternative. 

È possibile configurare la modalità di calcolo dei ritardi per un gruppo di copertura. È quindi possibile collegare il gruppo di copertura a un articolo successivamente. 

Nella pagina **Parametri di pianificazione generale**, è possibile impostare l'ora di inizio per il calcolo dei ritardi. Se un ordine viene evaso dopo questo orario, viene aggiunto un ritardo di un giorno alla data di ritardo dell'ordine. 

**Nota:** nelle versioni precedenti, i ritardi calcolati erano denominati *messaggi di ritardo*, la data di ritardo era denominata *data ritardo* e una transazione ritardata era definita *una transazione impostata su una data futura*.

<a name="see-also"></a>Vedere anche
--------

[Impostazioni copertura](coverage-settings.md)




