---
title: "Recentemente aggiunto modificando le funzionalità in Registrazione attività"
description: "Se si utilizza la funzione Registrazione attività per creare le aree di attività, è possibile modificare più efficiente i file utilizzando la funzionalità descritta in questo wiki."
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
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: c4f9ac515eab6ed8b194fc8985f6d3fae40ced38
ms.lasthandoff: 03/31/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Recentemente aggiunto modificando le funzionalità in Registrazione attività

Se si utilizza la funzione Registrazione attività per creare le aree di attività, è possibile modificare più efficiente i file utilizzando la funzionalità descritta in questo wiki.

Queste funzionalità sono disponibili ** registrazione &gt; di modifica Registrazione &gt; attività le impostazioni ** il menu.

-   Inserire i passaggi senza immettere di nuovo l'intero file.
-   Spostare i passaggi in una secondario senza immettere di nuovo l'intero file.
-   Campi di nome e descrizione del giornale di crollo.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Inserire i passaggi senza immettere di nuovo l'intero file
È possibile aggiungere un passaggio in un punto qualsiasi in una guida di attività senza riprodure o immettere di nuovo l'intero file.

1.  Selezionare la fase di scadenza che si desidera inserire il nuovo passaggio inserire. Verificare che il passaggio sia evidenziato.

Per consentire la funzione Registrazione attività per inserire un passaggio, è necessario che la pagina aperta corretta. Verrà visualizzata la pagina corretta la finestra in cui il nuovo processo si verifica. In Registrazione attività è un meccanismo che determina la finalità della pagina è attiva e renderà non valida la funzionalità se la pagina corretta non aperta. 

![[] (tg1. /media/tg1.png)](. /media/tg1.png) 


Al nella pagina corretta, ** passaggio di inserimento ** diventa disponibile.

![[] (tg2. /media/tg2-231x300.png)](. /media/tg2.png)

2. Fare clic su ** passaggio di inserimento **.

Quando si fa clic su ** passaggio di inserimento **, i record Switch registrazione della modalità record. Qualsiasi azione del installata ora verrà registrata e aggiunte configurati come operazioni.

3. Fare clic su ** ** interruzione.

È possibile ripetere il processo, l'aggiunta di un numero illimitato di operazioni o spostare tutti i compiti secondari e Nuovo margine (vedere di seguito per i compiti secondari).

4. Al termine di modifica della Guida di attività, fare clic su ** modificare i fatti ** quindi selezionare una delle opzioni per salvare o emettere la Guida di attività.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Spostare i passaggi in una secondario senza immettere di nuovo l'intero file
È possibile spostare i passaggi in una secondario senza riprodure o immettere di nuovo l'intero file. È inoltre possibile spostare il passaggio di una secondario o il passaggio di una secondario di fine per raggruppare un blocco esistente di passaggi.

1.  Selezionare la fase o il passaggio di una secondario che si desidera spostare. Verificare che il passaggio sia evidenziato.
2.  Fare clic su ellissi, quindi fare clic su ** spostare il passaggio dopo **.

![[] (tg3. /media/tg3.png)](. /media/tg3.png)

3. Selezionano il passaggio o il passaggio di una secondario che si desidera spostare dopo il passaggio o il passaggio di una secondario. In Registrazione attività muoverà il passaggio.

4. Per spostare il passaggio di una secondario di fine, selezionarlo, fare clic sugli ellissi, fare clic su ** spostare il passaggio dopo ** quindi selezionare il passaggio di scadenza che si desidera il passaggio di una secondario di fine possibile.

Se si desidera che il primo passaggio nella Guida di attività trovarsi in una secondario, creare un passaggio della secondario come secondo passaggio quindi immettere la prima fase in. È possibile aggiungere o spostare tutti i passaggi o compiti secondari secondo le esigenze.

5. Al termine di modifica della Guida di attività, fare clic su ** modificare i fatti ** quindi selezionare una delle opzioni per salvare o emettere la Guida di attività.

## <a name="collapse-recording-name-and-description"></a>Nome e la descrizione di registrazione di crollo
È possibile espandere e comprimere ** nome di registrazione e ** ** descrizione di registrazione ** campi. Quando questi campi sono crollati, più passaggi saranno visibili in Registrazione attività di modificare il riquadro. 

![[] (tg4. /media/tg4-300x252.png)](. /media/tg4.png)  

<a name="see-also"></a>Vedere anche
--------

[Creare documentazione o formazione utilizzando le registrazioni di attività](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

Riferimento veloce [] Registrazione attività (/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


