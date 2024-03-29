---
title: Accumula piani di congedo e assenza
description: È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.
author: twheeloc
ms.date: 09/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aac35177ca120b1ae1b4759b98278fafadc3e033
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702131"
---
# <a name="accrue-leave-and-absence-plans"></a>Accumula piani di congedo e assenza

>[!Important]
>La funzionalità indicata in questo articolo è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Accumulare congedi e assenze per più dipendenti

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Gestisci congedo**, selezionare **Accumula piani di congedo e assenza**.

3. Viene visualizzata la finestra di dialogo **Accumula piani di congedo e assenza**. In **Accumula a partire da** selezionare **Data odierna** o selezionare **Data personalizzata** e inserire una data personalizzata.

4. Per eseguire gli accumuli per tutte le società, selezionare **Tutte le società**. Per elaborare gli accumuli per un unico piano di ferie, selezionare **No** per **Tutti i piani**, quindi selezionare un **Piano di congedo**. Se si selezionano tutte le società, non è possibile selezionare un singolo piano di congedo.

5. Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

    1. Immettere informazioni per il processo di accumulo.
    2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.
    3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.
    4. Selezionare **OK**. Il processo di accumulo verrà eseguito con i parametri impostati. 

## <a name="accrue-leave-and-absence-for-an-employee"></a>Accumulare congedi e assenze per un dipendente

1. Nel record del dipendente, selezionare **Congedo**.

2. Selezionare **Accumula congedi e assenze**.

3. Viene visualizzata la finestra di dialogo **Accumula piani di congedo e assenza**. In **Accumula a partire da** selezionare **Data odierna** o selezionare **Data personalizzata** e inserire una data personalizzata.

4. Per eseguire gli accumuli per tutte le società, selezionare **Tutte le società**. Per elaborare gli accumuli per un unico piano di ferie, selezionare **No** per **Tutti i piani**, quindi selezionare un **Piano di congedo**. Se si selezionano tutte le società, non è possibile selezionare un singolo piano di congedo.

5. Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere informazioni per il processo di accumulo.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. Il processo di accumulo verrà eseguito con i parametri impostati.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Eliminare gli accumuli di congedi e assenze per più dipendenti

Consente di eliminare i record di accumuli per un piano e un intervallo di date specifici. Le date di accumulo devono essere quelle odierne o nel futuro.

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Gestisci congedo**, selezionare **Elimina accumuli piani di congedo e assenza**.

3. Nella finestra di dialogo **Elimina accumuli piani di congedo e assenza** selezionare **Piano di congedo**.

4. Se applicabile, selezionare **Elimina rettifiche saldo**.

5. Immettere o selezionare una **data accumulo congedo**. Questa data deve essere la data odierna o una futura.

6. Selezionare **OK**. Il processo di accumulo elimina gli accumuli con i parametri impostati.

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Eliminare gli accumuli di congedi e assenze per un singolo dipendente

1. Nel record del dipendente, selezionare **Congedo**.

2. Selezionare **Elimina accumuli piani di congedo e assenza**.

3. Nella finestra di dialogo **Elimina accumuli piani di congedo e assenza** selezionare **Piano di congedo**.

4. Se applicabile, selezionare **Elimina rettifiche saldo**.

5. Immettere o selezionare una **data accumulo congedo**. Questa data deve essere la data odierna o una futura.

6. Selezionare **OK**. Il processo di accumulo elimina gli accumuli con i parametri impostati.

## <a name="review-leave-accrual-and-deletion-processes"></a>Revisionare i processi di accumulo ed eliminazione dei congedi

**Controllo accumuli congedi** viene visualizzato ogni volta che si esegue o si elimina un accumulo per uno o tutti i dipendenti. Vengono visualizzate anche la data e la persona che ha eseguito l'azione.

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.
2. Sotto **Gestisci congedo**, selezionare **Elimina controllo accumuli congedi**.

## <a name="leave-accrual-rounding"></a>Arrotondamento accumulo per congedo
Quando un dipendente è iscritto o non iscritto, l'arrotondamento della maturazione delle ferie verrà ripartito proporzionalmente. In precedenza, l'arrotondamento era consentito solo quando un piano di ferie era impostato in modo proporzionale e un dipendente veniva iscritto/cancellato a metà del periodo. I ratei per ferie ora verranno arrotondati indipendentemente dall'iscrizione/cancellazione a metà periodo o all'inizio di un periodo.

## <a name="leave-accrual-transaction-auditing"></a>Controllo transazione accumulo per congedo

Questa funzionalità consente ai responsabili delle ferie e delle assenze di comprendere le transazioni di accumulo di ferie e assenze relative ai saldi di ferie di un dipendente per un tipo di ferie specifico.

Per visualizzare i dettagli della transazione.

1. Nel record del dipendente, selezionare **Congedo**.

2. Seleziona **Visualizza tempo libero**, quindi seleziona la scheda **Saldi**.

Per visualizzare le transazioni di maturazione relative a un tipo di ferie specifico, seleziona il valore numerico nella colonna **Saldo corrente**.

Per visualizzare i dettagli della transazione per un importo di accumulo specifico, seleziona una riga di accumulo, apri il pannello **Informazioni correlate** a destra, quindi apri la sezione **Dettagli transazioni**. La sezione Dettagli transazioni mostra:

- Modifiche al saldo del tipo di congedo del dipendente
- Dettagli sull'impiego per quel periodo di maturazione specificato
- Dettagli sul periodo di maturazione e sui tassi
- Eventuali modifiche apportate alle configurazioni del piano di congedo

![Visualizzare il controllo delle transazioni di accumulo dei congedi.](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>Vedere anche

[Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)</br>
[Creare un piano di congedo e assenza](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
