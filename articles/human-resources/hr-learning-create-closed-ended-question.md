---
title: Creare una domanda chiusa
description: Le domande chiuse consentono di fornire opzioni tra cui l'intervistato può scegliere.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8758b74f9ce7c8687b7c2925ccd04cd512602db0
ms.sourcegitcommit: 8246ba3872a1f3eaa18c8bb1ba86d3c2142a6e10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2021
ms.locfileid: "7465175"
---
# <a name="create-a-closed-ended-question"></a>Creare una domanda chiusa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Le domande chiuse consentono di fornire opzioni tra cui l'intervistato può scegliere. È necessario innanzitutto creare il gruppo di risposte, quindi creare la domanda che utilizzerà il gruppo di risposte. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-an-answer-group"></a>Creare un gruppo di risposte
1. Andare a **Questionario** > **Progettazione** > **Gruppi di risposte**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Gruppo di risposte**.
4. Digitare un valore nel campo **Descrizione**
    * Utilizzare la funzionalità dei parametri casuali per posizionare in modo casuale le risposte un ordine diverso ogni volta che il gruppo di risposte viene utilizzato per una domanda.  
5. Fare clic su **Risposta**.
6. Fare clic su **Nuovo**.
    * Un numero progressivo controlla l'ordine in cui le risposte vengono visualizzate, a meno che l'opzione Parametri casuali non sia selezionata per il gruppo di risposte.  
    * Alle risposte possono essere assegnati punti da utilizzare per l'assegnazione di punteggio nel questionario.  
7. Nel campo **Punti** immettere un numero.
    * La risposta corretta può essere contrassegnata per indicare che la risposta selezionata è quella corretta. Questo può essere utilizzato per assegnare punteggio nel questionario.  
8. Digitare un valore nel campo **Risposta**.
    * Continuare a creare opzioni di selezione della risposta per il gruppo di risposte.  
9. Fare clic su **Nuovo**.
10. Nel campo **Punti** immettere un numero.
11. Digitare un valore nel campo **Risposta**.
12. Fare clic su **Nuovo**.
13. Nel campo **Punti** immettere un numero.
14. Digitare un valore nel campo **Risposta**.
15. Fare clic su **Nuovo**.
16. Nel campo **Punti** immettere un numero.
17. Digitare un valore nel campo **Risposta**.
18. Fare clic su **Nuovo**.
19. Nel campo **Punti** immettere un numero.
20. Digitare un valore nel campo **Risposta**.
21. Chiudere la pagina.
22. Chiudere la pagina.

## <a name="create-the-question"></a>Creare la domanda
1. Andare a **Questionario** > **Progettazione** > **Domande**.
2. Fare clic su **Nuovo**.
3. Utilizzare il campo Tipo per raggruppare domande correlate.
    * È possibile utilizzare i tipi di input casella di controllo, pulsante alternativo o casella combinata per le domande chiuse.  
4. Nel campo **Tipo di input** selezionare un'opzione.
5. Nel campo **Gruppo di risposte** immettere o selezionare un valore.
6. Digitare un valore nel campo **Testo**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
