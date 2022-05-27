---
title: Ottimizzare le prestazioni con attività di pulizia automatica
description: Questo argomento spiega come migliorare le prestazioni in Microsoft Dynamics 365 Human Resources pulendo la cronologia dei lavori batch.
author: twheeloc
ms.date: 08/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 47cd132c188c39c8700cae6035ae75d0ce71d841
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687221"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Ottimizzare le prestazioni con attività di pulizia automatica


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problema**

Microsoft Dynamics 365 Human Resources può riscontrare problemi di prestazioni se la cronologia dei processi batch diventa troppo grande.

**Causa**

I processi batch eseguiti frequentemente possono portare a una crescita insostenibile della cronologia dei processi batch. Questo può causare problemi di prestazioni. 

**Risoluzione**

Pianificare un'attività automatica per ripulire la cronologia dei processi batch. Si consiglia di impostare l'attività da eseguire settimanalmente, ma potrebbe essere necessario eseguire la pulizia più o meno frequentemente, a seconda del proprio ambiente. La seguente procedura contiene le impostazioni consigliate, ma è possibile modificarle in base alle proprie esigenze.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Nella barra **Ricerca**, immettere **Pulizia storico processi batch**.

   ![Cercare Pulizia storico processi batch.](media/talent-batch-history-cleanup-search-bar.png)

3. In **Limite cronologico (giorni)**, immettere **30**.

   ![Impostare il limite cronologico su 30.](media/talent-batch-history-cleanup-history-limit.png)

4. Selezionare **Esecuzione in background** e quindi selezionare **Ricorrenza**.

   ![Impostare la ricorrenza.](media/talent-batch-history-cleanup-recurrence.png)

5. In **Definisci ricorrenza**, impostare la **Data di inizio** e **Ora di inizio** in modo che si verificano durante le ore non lavorative o nel fine settimana, quindi selezionare **Nessuna data di fine**. 

   ![Definire la data e l'ora di inizio della ricorrenza.](media/talent-batch-history-cleanup-define-recurrence.png)

6. In **Criterio di ricorrenza**, selezionare **Giorni** e impostare **Ripeti dopo l'intervallo specificato** su **7**.

   ![Impostare la pulizia con frequenza settimanale.](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Selezionare **OK**.

8. Apportare le modifiche necessarie a tutti gli altri parametri in **Esegui in background** e selezionare **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
