---
title: Ottimizzare le prestazioni con attività di pulizia automatica
description: In questo articolo viene spiegato come risolvere alcuni problemi di prestazioni con Microsoft Dynamics 365 Human Resources tramite la pulizia della cronologia dei processi batch.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a983fde8ba393ab25f2b330014e04a1379f0e4d0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009503"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Ottimizzare le prestazioni con le attività di pulizia automatiche

**Problema**

Microsoft Dynamics 365 Human Resources può riscontrare problemi di prestazioni se la cronologia dei processi batch diventa troppo grande.

**Causa**

I processi batch eseguiti frequentemente possono portare a una crescita insostenibile della cronologia dei processi batch. Questo può causare problemi di prestazioni. 

**Risoluzione**

Pianificare un'attività automatica per ripulire la cronologia dei processi batch. Si consiglia di impostare l'attività da eseguire settimanalmente, ma potrebbe essere necessario eseguire la pulizia più o meno frequentemente, a seconda del proprio ambiente. La seguente procedura contiene le impostazioni consigliate, ma è possibile modificarle in base alle proprie esigenze.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Nella barra **Ricerca**, immettere **Pulizia storico processi batch**.

   ![Cercare Pulizia storico processi batch](media/talent-batch-history-cleanup-search-bar.png)

3. In **Limite cronologico (giorni)**, immettere **30**.

   ![Impostare il limite cronologico su 30](media/talent-batch-history-cleanup-history-limit.png)

4. Selezionare **Esecuzione in background** e quindi selezionare **Ricorrenza**.

   ![Impostare la ricorrenza](media/talent-batch-history-cleanup-recurrence.png)

5. In **Definisci ricorrenza**, impostare la **Data di inizio** e **Ora di inizio** in modo che si verificano durante le ore non lavorative o nel fine settimana, quindi selezionare **Nessuna data di fine**. 

   ![Definire la data e l'ora di inizio della ricorrenza](media/talent-batch-history-cleanup-define-recurrence.png)

6. In **Criterio di ricorrenza**, selezionare **Giorni** e impostare **Ripeti dopo l'intervallo specificato** su **7**.

   ![Impostare la pulizia con frequenza settimanale](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Selezionare **OK**.

8. Apportare le modifiche necessarie a tutti gli altri parametri in **Esegui in background** e selezionare **OK**.

