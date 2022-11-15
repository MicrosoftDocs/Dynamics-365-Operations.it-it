---
title: Annullare un processo creato utilizzando il motore di pianificazione generale deprecato
description: In questo articolo viene descritto come annullare un processo attivo di pianificazione che utilizza il motore di pianificazione generale deprecato.
author: t-benebo
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7b71a43f407050dccb7550db7c4b6a98a596d589
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740879"
---
# <a name="cancel-a-job-that-was-created-using-the-deprecated-master-planning-engine"></a>Annullare un processo creato utilizzando il motore di pianificazione generale deprecato

[!include [banner](../includes/banner.md)]

Esistono più opzioni per annullare un processo creato utilizzando il motore di pianificazione generale deprecato. Ad esempio, è possibile che si desideri annullare un processo di pianificazione generale se è stato avviato per errore o è in esecuzione più a lungo del previsto e si desidera terminarlo.

Il modo migliore per annullare un processo di pianificazione è dalla pagina **Processi di pianificazione non completati**. Le opzioni alternative dalle pagine **Processi batch** e **Processi batch avanzati** devono essere utilizzate solo se l'annullamento del processo di pianificazione generale dalla pagina **Processi di pianificazione non completati** non viene completato in pochi minuti.

## <a name="preferred-cancel-option"></a>Opzione di annullamento preferita

### <a name="cancel-master-planning-job-from-the-unfinished-planning-processes-page"></a>Annullare il processo di pianificazione generale dalla pagina Processi di pianificazione non completati

1. Andare a **Pianificazione generale > Richieste di informazioni e report > Panificazione generale > Processi di pianificazione non completati**.
2. Selezionare la riga del processo di pianificazione che si desidera annullare.
3. Selezionare **Annulla**.

## <a name="additional-cancel-options"></a>Ulteriori opzioni di annullamento

Queste devono essere utilizzate solo se l'annullamento del processo di pianificazione generale dalla pagina **Processi di pianificazione non completati** non viene completato in pochi minuti.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Eliminare il processo di pianificazione generale dalla pagina **Processi batch**

1. Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Selezionare la riga del processo di pianificazione che si desidera eliminare.
3. Selezionare **Elimina**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Interrompere l'attività del processo di pianificazione generale dalla pagina **Processi batch avanzati**

1. Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Se l'ID processo non è visualizzato nell'elenco, fare clic su **Passa al modulo avanzato**, altrimenti procedere con il passaggio successivo.
3. Aprire il processo batch Seleziona **ID processo** del processo batch con le attività che si desidera terminare.
4. In **Attività batch**, selezionare le attività da terminare.
5. Seleziona **Cambia stato**, scegli **Annullamento** e fai clic su **OK**.
6. Nella scheda dettaglio **Attività batch**, fare clic su **Interrompi**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]