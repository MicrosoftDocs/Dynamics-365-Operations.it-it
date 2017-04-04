---
title: Gestisci ordini pianificati
description: "Questo articolo fornisce informazioni sulla modalità di gestione degli ordini pianificati. Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell&quot;ordine pianificato selezionato."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c01a192e637bfe74a60370290db72c439faf40d0
ms.lasthandoff: 03/31/2017


---

# <a name="maintain-planned-orders"></a>Gestisci ordini pianificati

Questo articolo fornisce informazioni sulla modalità di gestione degli ordini pianificati. Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato.

È possibile gestire gli ordini pianificati nell'area di lavoro **Pianificazione generale**, nell'elenco **Ordine pianificato** o negli elenchi **Ordini di produzione pianificati**, **Ordini fornitore pianificati** e **Trasferimento pianificato**. È possibile utilizzare il campo **Stato** per tenere facilmente traccia dell'avanzamento. Vengono utilizzati i valori seguenti:

-   Agli ordini pianificati generati mediante la pianificazione generale viene assegnato uno stato di **Inevaso**.
-   A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Completato**.
-   A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Approvato**. Questo stato indica che si approva la stabilizzazione dell'ordine pianificato, ma che questa operazione non è ancora stata effettuata.

**Nota:** un ordine pianificato approvato viene trasferito con lo stato corrente al calcolo successivo della pianificazione generale. È possibile stabilizzare gli ordini pianificati facendo clic su **Stabilizza**. Di seguito sono riportati gli ordini pianificati che è possibile stabilizzare:

-   L'ordine pianificato selezionato.
-   Più ordini pianificati.
-   Ordini pianificati generati da un'esplosione nella pagina **Esplosione**. Fare clic su **Ordini pianificati**, selezionare l'ordine pianificato, quindi fare clic su **Stabilizza**.

Quando un ordine pianificato viene stabilizzato, viene spostato nella sezione relativa agli ordini del modulo rilevante. **Nota:** è possibile fare clic con il pulsante destro del mouse su un ordine pianificato che ha uno stato particolare e filtrare altri ordini pianificati con lo stesso stato. Questa funzionalità è utile se, ad esempio, si desidera filtrare tutti gli ordini pianificati che hanno uno stato di **Approvato**, in modo da poterli stabilizzare.

<a name="see-also"></a>Vedere anche
--------

[Master plans](master-plans.md)


