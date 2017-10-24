--- 
title: Creare un processo batch
description: "Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-batch-job"></a>Creare un processo batch

[!include[task guide banner](../../includes/task-guide-banner.md)]

Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente. I processi batch vengono eseguiti con le credenziali di sicurezza dell'utente da cui sono stati creati. Per creare un processo batch, attenersi alla seguente procedura. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-the-batch-job"></a>Creare il processo batch
1. Andare a Amministrazione sistema > Richieste di informazioni > Processi batch.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Descrizione processo.
4. Nel campo Data/ora di inizio programmate immettere una data e un'ora.
5. Fare clic su Salva.

## <a name="create-a-recurrence"></a>Creare una ricorrenza
1. Nel riquadro azioni fare clic su Processo batch.
2. Fare clic su Ricorrenza.
    * Usare queste opzioni per immettere un intervallo e un criterio per la ricorrenza.  
3. Fare clic su OK.

## <a name="add-alerts"></a>Aggiungere avvisi
1. Nel riquadro azioni fare clic su Processo batch.
2. Fare clic su Avvisi.
    * Indicare se si desidera che i messaggi di avviso vengano inviati quando il processo batch termina, presenta una condizione di errore o viene annullato. Poi specificare se volete che gli allarmi vengano visualizzati come messaggi popup.   
3. Fare clic su OK.


