---
title: Creare un processo batch
description: Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: fbb844ebcf8d4b47b127132a5bf0ea45fa40f747
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562883"
---
# <a name="create-a-batch-job"></a>Creare un processo batch

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

