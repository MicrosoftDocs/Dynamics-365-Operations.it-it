---
title: Accumula piani di congedo e assenza
description: È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba60fc2e5b17ec32aa6ad7eb104e8ae55ddee3bb
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092340"
---
# <a name="accrue-leave-and-absence-plans"></a>Accumula piani di congedo e assenza

È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Accumulare congedi e assenze per più dipendenti

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Gestisci congedo**, selezionare **Accumula piani di congedo e assenza**.

3. Nella finestra di dialogo **Accumula piani di congedo e assenza**, in **Accumula a partire da**, selezionare **Data odierna** o **Data personalizzata** e immettere una data personalizzata.

4. Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere informazioni per il processo di accumulo.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. Il processo di accumulo verrà eseguito con i parametri impostati.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Accumulare congedi e assenze per un dipendente

1. Nel record del dipendente, selezionare **Congedo**.

2. Selezionare **Accumula congedi e assenze**.

3. Nella finestra di dialogo **Accumula piani di congedo e assenza**, in **Accumula a partire da**, selezionare **Data odierna** o **Data personalizzata** e immettere una data personalizzata.

4. Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere informazioni per il processo di accumulo.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. Il processo di accumulo verrà eseguito con i parametri impostati.

## <a name="preview-features-for-leave-and-absence"></a>Funzionalità di anteprima di Congedo e assenza

[!include [banner](includes/preview-feature-leave-absence.md)]

È possibile abilitare le seguenti funzionalità di anteprima per Congedo e assenza:

- **Elimina accumuli congedi e assenze**. Consente di eliminare i record di accumuli per un piano e un intervallo di date specifici. Le date di accumulo devono essere quelle odierne o nel futuro.

- **Controllo accumuli congedi**. Viene visualizzata ogni volta che qualcuno esegue o elimina un accumulo per uno o tutti i dipendenti, insieme alla data e a chi ha eseguito l'azione.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Creare un piano di congedo e assenza](hr-leave-and-absence-plans.md)