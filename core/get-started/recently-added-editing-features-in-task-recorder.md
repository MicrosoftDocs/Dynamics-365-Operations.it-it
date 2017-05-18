---
title: "Funzionalità di modifica recentemente aggiunte in Registrazione attività"
description: "Se si utilizza Registrazione attività per creare guide attività, è possibile modificare i file in modo più efficiente utilizzando la funzionalità descritta in questo argomento."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core
ms.custom: 266464
ms.assetid: b4640e67-4b92-4855-8041-1bfc71aadc47
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 3be54879494948f75b192fcc22239b9064173220
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Funzionalità di modifica recentemente aggiunte in Registrazione attività

[!include[banner](../includes/banner.md)]


Se si utilizza Registrazione attività per creare guide attività, è possibile modificare i file in modo più efficiente utilizzando la funzionalità descritta in questo argomento.

Queste funzioni sono disponibili nel menu **Impostazioni &gt; Registrazione attività &gt; Modifica registrazione**.

-   Inserire i passaggi senza registrare di nuovo l'intero file.
-   Spostare i passaggi in un'attività secondaria senza registrare di nuovo l'intero file.
-   Comprimere i campi del nome e della descrizione della registrazione.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Inserire i passaggi senza registrare di nuovo l'intero file
È possibile ora aggiungere un passaggio in qualsiasi punto in una guida attività senza riprodurre o registrare di nuovo l'intero file.

1.  Selezionare il passaggio dopo il quale si desidera inserire il nuovo passaggio. Verificare che il passaggio sia evidenziato.

Per consentire a Registrazione attività di inserire un passaggio, è necessario che sia aperta la pagina corretta. La pagina corretta è quella in cui viene effettuato il nuovo passaggio. Registrazione attività dispone di un meccanismo che determina qual è la pagina attiva e disabiliterà la funzionalità se la pagina corretta non è aperta. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Se è aperta la pagina corretta, l'opzione **Inserisci passaggio** diventa disponibile.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Fare clic su **Inserisci passaggio**.

Quando si fa clic su **Inserisci passaggio**, Registrazione attività passa alla modalità di registrazione. Qualsiasi azione intrapresa nell'interfaccia utente verrà ora registrata e aggiunta sul posto come passaggi.

3. Fare clic su **Interrompi**.

È possibile ripetere il processo, aggiungendo un numero illimitato di passaggi o spostando tutte le attività secondarie necessarie (vedere di seguito per le attività secondarie).

4. Al termine della modifica della guida attività, fare clic su **Fine modifica**, quindi selezionare una delle opzioni per salvare o pubblicare la guida attività.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Spostare i passaggi in un'attività secondaria senza registrare di nuovo l'intero file
È possibile spostare i passaggi in un'attività secondaria senza riprodurre o registrare di nuovo l'intero file. È inoltre possibile spostare il passaggio dell'attività secondaria o il passaggio dell'attività secondaria finale se si desidera raggruppare un blocco esistente di passaggi.

1.  Selezionare il passaggio o il passaggio dell'attività secondaria che si desidera spostare. Verificare che il passaggio sia evidenziato.
2.  Fare clic sui puntini di sospensione, quindi su **Sposta passaggio dopo**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Selezionare il passaggio o il passaggio di un'attività secondaria dopo il quale si desidera spostare il passaggio o il passaggio dell'attività secondaria. Registrazione attività sposterà il passaggio.

4. Per spostare il passaggio di un'attività secondaria finale, selezionarlo, fare clic sui puntini di sospensione, quindi su **Sposta passaggio dopo**, quindi selezionare il passaggio dopo il quale si desidera inserire il passaggio dell'attività secondaria finale.

Se si desidera che il primo passaggio nella guida attività sia all'interno di un'attività secondaria, creare un passaggio dell'attività secondaria come secondo passaggio, quindi spostare il primo passaggio all'interno di esso. È possibile aggiungere o spostare tutti i passaggi o le attività secondarie necessari.

5. Al termine della modifica della guida attività, fare clic su **Fine modifica**, quindi selezionare una delle opzioni per salvare o pubblicare la guida attività.

## <a name="collapse-recording-name-and-description"></a>Comprimere nome e descrizione della registrazione
È possibile espandere e comprimere i campi **Nome registrazione** e **Descrizione registrazione**. Quando questi campi sono compressi, più passaggi saranno visibili nel riquadro di modifica Registrazione attività. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Vedere anche
--------

[Creare documentazione o formazione utilizzando le registrazioni di attività](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Riferimento rapido Registrazione attività](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)




