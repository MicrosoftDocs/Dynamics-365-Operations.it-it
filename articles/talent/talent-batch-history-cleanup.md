---
title: Ottimizzare le prestazioni con le attività di pulizia automatiche
description: In questo argomento viene spiegato come risolvere alcuni problemi di prestazioni con Microsoft Dynamics 365 Talent tramite la pulizia della cronologia dei processi batch.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a053c9094151f4e12e4aadc533dd272258779540
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832584"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Ottimizzare le prestazioni con le attività di pulizia automatiche

[!include [banner](includes/banner.md)]

**Problema**

Microsoft Dynamics 365 Talent può riscontrare problemi di prestazioni se la cronologia dei processi batch diventa troppo grande.

**Causa**

I processi batch eseguiti frequentemente possono portare a una crescita insostenibile della cronologia dei processi batch. Questo può causare problemi di prestazioni. 

**Risoluzione**

Pianificare un'attività automatica per ripulire la cronologia dei processi batch. Si consiglia di impostare l'attività da eseguire settimanalmente, ma potrebbe essere necessario eseguire la pulizia più o meno frequentemente, a seconda del proprio ambiente. La seguente procedura contiene le impostazioni consigliate, ma è possibile modificarle in base alle proprie esigenze.

1. In Talent, selezionare **Amministrazione sistema**.

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

