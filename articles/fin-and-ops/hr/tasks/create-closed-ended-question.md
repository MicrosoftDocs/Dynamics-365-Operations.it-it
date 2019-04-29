---
title: Creare una domanda chiusa
description: Le domande chiuse consentono di fornire opzioni tra cui l'intervistato può scegliere.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92e4f9697fc00798d917db6f7f50d7e3b8739233
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "858654"
---
# <a name="create-a-closed-ended-question"></a>Creare una domanda chiusa

[!include [task guide banner](../../includes/task-guide-banner.md)]

Le domande chiuse consentono di fornire opzioni tra cui l'intervistato può scegliere. È necessario innanzitutto creare il gruppo di risposte, quindi creare la domanda che utilizzerà il gruppo di risposte. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-an-answer-group"></a>Creare un gruppo di risposte
1. Andare a Questionario > Progettazione > Gruppi di risposte.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Gruppo di risposte.
4. Nel campo Descrizione digitare un valore.
    * Utilizzare la funzionalità dei parametri casuali per posizionare in modo casuale le risposte un ordine diverso ogni volta che il gruppo di risposte viene utilizzato per una domanda.  
5. Fare clic su Risposta.
6. Fare clic su Nuovo.
    * Un numero progressivo controlla l'ordine in cui le risposte vengono visualizzate, a meno che l'opzione Parametri casuali non sia selezionata per il gruppo di risposte.  
    * Alle risposte possono essere assegnati punti da utilizzare per l'assegnazione di punteggio nel questionario.  
7. Nel campo Punti immettere un numero.
    * La risposta corretta può essere contrassegnata per indicare che la risposta selezionata è quella corretta. Questo può essere utilizzato per assegnare punteggio nel questionario.  
8. Digitare un valore nel campo Risposta.
    * Continuare a creare opzioni di selezione della risposta per il gruppo di risposte.  
9. Fare clic su Nuovo.
10. Nel campo Punti immettere un numero.
11. Digitare un valore nel campo Risposta.
12. Fare clic su Nuovo.
13. Nel campo Punti immettere un numero.
14. Digitare un valore nel campo Risposta.
15. Fare clic su Nuovo.
16. Nel campo Punti immettere un numero.
17. Digitare un valore nel campo Risposta.
18. Fare clic su Nuovo.
19. Nel campo Punti immettere un numero.
20. Digitare un valore nel campo Risposta.
21. Chiudere la pagina.
22. Chiudere la pagina.

## <a name="create-the-question"></a>Creare la domanda
1. Andare a Questionario > Progettazione > Domande.
2. Fare clic su Nuovo.
3. Utilizzare il campo Tipo per raggruppare domande correlate.
    * È possibile utilizzare i tipi di input casella di controllo, pulsante alternativo o casella combinata per le domande chiuse.  
4. Nel campo Tipo di input selezionare un'opzione.
5. Nel campo Gruppo di risposte immettere o selezionare un valore.
6. Digitare un valore nel campo Testo.

