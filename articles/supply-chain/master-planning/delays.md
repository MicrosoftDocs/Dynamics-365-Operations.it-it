---
title: Ritardi
description: Questo articolo fornisce informazioni sulle date ritardate nella pianificazione generale. Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta.
author: t-benebo
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e7e0150e40193f2f799677ad19cae2ea589afc0
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740632"
---
# <a name="delays"></a>Ritardi

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle date ritardate nella pianificazione generale. Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta.

La pianificazione generale può calcolare la prima data di evasione possibile per una transazione, in base ai lead time, alla disponibilità del materiale, alla disponibilità della capacità e a vari parametri di pianificazione. 

Se la pianificazione generale calcola una data dell'ordine che precede la data corrente, l'ordine non può essere evaso in tempo. Di conseguenza, l'ordine viene ritardato. In questo caso, la pianificazione generale pianifica in anticipo l'ordine a partire dalla data corrente e include i lead time. Questi lead time cominciano con qualsiasi articolo componente di livello inferiore. L'ordine riceve quindi una data ritardata. Una data ritardata è una data di scadenza realistica basata sui dati correnti. La pianificazione generale calcola anche il numero di giorni di ritardo. 

In alcune situazioni, è possibile scegliere di non calcolare i ritardi, ad esempio quando gli utenti sanno che possono velocizzare i lead time selezionando modalità di consegna alternative. 

È possibile configurare la modalità di calcolo dei ritardi per un gruppo di copertura. È quindi possibile collegare il gruppo di copertura a un articolo successivamente. 

Nella pagina **Parametri di pianificazione generale**, è possibile impostare l'ora di inizio per il calcolo dei ritardi. Se un ordine viene evaso dopo questo orario, viene aggiunto un ritardo di un giorno alla data di ritardo dell'ordine. 

> [!NOTE]
> Nelle versioni precedenti, i ritardi calcolati erano denominati *messaggi di ritardo*, la data di ritardo era denominata *data ritardo* e una transazione ritardata era definita una *transazione impostata su una data futura*.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>Ritardi limitati nell'impostazione della produzione con più livelli DBA
Quando si lavora con ritardi in un'impostazione di produzione con più livelli DBA, è importante notare che solo gli articoli direttamente sopra l'articolo (nella struttura DBA) che causa il ritardo verranno aggiornati con un ritardo nell'ambito dell'esecuzione della pianificazione generale. Gli altri elementi nella struttura della DBA non vengono applicati al ritardo fino alla prima esecuzione della pianificazione generale, quando l'ordine pianificato per il livello superiore viene approvato o stabilizzato. 

Per aggirare questa limitazione nota, gli ordini di produzione nella parte superiore della struttura DBA con ritardi possono essere approvati (o stabilizzati) prima della successiva esecuzione della pianificazione generale. In questo modo verrà mantenuto il ritardo dell'ordine di produzione pianificato ritardato approvato e tutti i componenti sottostanti verranno aggiornati di conseguenza.
I messaggi di azione possono anche essere utilizzati per identificare gli ordini pianificati che possono essere spostati a una data successiva, a causa di altri ritardi nella struttura della DBA.

## <a name="desired-date"></a>Data desiderata

Nella pagina **Ordine pianificato**, sotto la scheda **Ritardi** è visualizzata la **data desiderata** per l'ordine pianificato. La data desiderata di un ordine pianificato è la data di base per i ritardi, ovvero una data calcolata uguale alla **data richiesta** calcolata a partire dal **fabbisogno netto**. Se l'ordine pianificato è una riga DBA, una riga di produzione o una riga kanban, la data desiderata si basa sulla **data fabbisogno** e la data desiderata non verrà visualizzata nella pagina **Ordine pianificato**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Impostazioni della copertura](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]