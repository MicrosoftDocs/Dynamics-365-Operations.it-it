---
title: Annullare un processo di pianificazione generale
description: In questo argomento viene descritto come annullare un processo di pianificazione attivo che utilizza la funzionalità di pianificazione incorporata.
author: ChristianRytt
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 66d5b10e1471b98274d4049df18a2e53873f789a
ms.sourcegitcommit: 92cd55028be556a0bd41b6972c9c6d14b695dfa0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2020
ms.locfileid: "2947482"
---
# <a name="cancel-a-master-planning-job"></a>Annullare un processo di pianificazione generale

In Microsoft Dynamics 365 Supply Chain Management, ci sono più opzioni per annullare un processo di pianificazione generale. Ad esempio, è possibile che si desideri annullare un processo di pianificazione generale se è stato avviato per errore o è in esecuzione più a lungo del previsto e si desidera terminarlo. Il modo migliore per annullare un processo di pianificazione è dalla pagina **Processi di pianificazione non completati**. Le opzioni alternative dalle pagine **Processi batch**e **Processi batch avanzati** devono essere utilizzate solo se l'annullamento del processo di pianificazione generale dalla pagina **Processi di pianificazione non completati** non viene completato in pochi minuti.

## <a name="preferred-cancel-option"></a>Opzione di annullamento preferita
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>Annullare il processo di pianificazione generale dalla pagina **Processi di pianificazione non completati**
1. Andare a **Pianificazione generale > Richieste di informazioni e report > Panificazione generale > Processi di pianificazione non completati**.
2. Selezionare la riga del processo di pianificazione che si desidera annullare.
3. Fare clic su **Annulla**.

## <a name="additional-cancel-options"></a>Ulteriori opzioni di annullamento
Queste devono essere utilizzate solo se l'annullamento del processo di pianificazione generale dalla pagina **Processi di pianificazione non completati** non viene completato in pochi minuti.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Eliminare il processo di pianificazione generale dalla pagina **Processi batch**
1. Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Selezionare la riga del processo di pianificazione che si desidera eliminare.
3. Fare clic su **Elimina**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Interrompere l'attività del processo di pianificazione generale dalla pagina **Processi batch avanzati**
1. Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Se l'ID processo non è visualizzato nell'elenco, fare clic su **Passa al modulo avanzato**, altrimenti procedere con il passaggio successivo.
3. Aprire il processo batch Fare clic su **ID processo** del processo batch con le attività che si desidera terminare.
4. In **Attività batch**, selezionare le attività da terminare.
5. Nella scheda dettaglio **Attività batch**, fare clic su **Interrompi**.
