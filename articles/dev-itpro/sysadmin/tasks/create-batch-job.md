---
title: Creare un processo batch
description: Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d211dcd7cb47df135d395d2a993429746aa35a85
ms.sourcegitcommit: 6ba4006fb6a67ddd4b1e54e3d62b9d1239b5e5a3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "1700843"
---
# <a name="create-a-batch-job"></a>Creare un processo batch

[!include [task guide banner](../../includes/task-guide-banner.md)]

Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente. I processi batch vengono eseguiti con le credenziali di sicurezza dell'utente da cui sono stati creati. Per creare un processo batch, attenersi alla seguente procedura. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-the-batch-job"></a>Creare il processo batch
1. Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Descrizione processo**.
4. Nel campo **Data/ora di inizio programmate** immettere una data e un'ora.
5. Fare clic su **Salva**.

## <a name="create-a-recurrence"></a>Creare una ricorrenza
1. Nel riquadro azioni fare clic su **Processo batch**.
2. Fare clic su **Ricorrenza**. Usare queste opzioni per immettere un intervallo e un criterio per la ricorrenza.  
3. Fare clic su **OK**.

## <a name="add-alerts"></a>Aggiungere avvisi
1. Nel riquadro azioni fare clic su **Processo batch**.
2. Fare clic su **Avvisi**. Indicare se si desidera che i messaggi di avviso vengano inviati quando il processo batch termina, presenta una condizione di errore o viene annullato. Poi specificare se volete che gli allarmi vengano visualizzati come messaggi popup.   
3. Fare clic su **OK**.

## <a name="adjust-batch-job-status"></a>Modificare lo stato del processo batch
1. Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Selezionare il processo batch appropriato.
3. Nel riquadro azioni fare clic su **Processo batch > Funzioni > Cambia stato**.
4. Selezionare lo stato appropriato:
    - **Trattenuto**: impostare il processo batch su **trattenuto** di modo che sia trattenuto dallo scheduler dei processi batch. È equivalente a *fermo*.
    - **In attesa**: impostare il processo batch su **in attesa** di modo che sia in attesa di essere selezionato dallo scheduler di processi batch. E equivalente a *avvia*.
5. Fare clic su **OK**.
