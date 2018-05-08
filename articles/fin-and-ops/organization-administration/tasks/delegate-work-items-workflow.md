--- 
title: Delegare elementi di lavoro in un flusso di lavoro
description: "Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4765fec0cdce0e2f8859c979ff97d20aa6b20bfa
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="delegate-work-items-in-a-workflow"></a>Delegare elementi di lavoro in un flusso di lavoro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti. La procedura consente di configurare il sistema in modo da delegare automaticamente gli elementi di lavoro a un altro utente.



La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="set-up-automatic-delegation"></a>Impostare la delega automatica
1. Passare a Comune > Impostazioni > Opzioni utente.
2. Fare clic sulla scheda Flusso di lavoro.
    * Assicurarsi che la sezione Delega sia espansa.    Per configurare il sistema in modo da delegare automaticamente gli elementi di lavoro ad altri utenti, è necessario creare regole di delega, che specificano il momento in cui determinati tipi di elementi di lavoro vengono delegati. Per creare una regola di delega, completare i passaggi seguenti:  
3. Scegliere Aggiungi.
4. Nel campo Ambito selezionare un'opzione.
    * Tutto: consente di delegare tutti gli elementi di lavoro assegnati all'utente.    Modulo: consente di delegare solo gli elementi di lavoro correlati a un tipo specifico di flusso di lavoro. Se si seleziona questa opzione, è necessario selezionare il tipo di flusso di lavoro nel campo Nome.    Flusso di lavoro: consente di delegare solo gli elementi di lavoro correlati a un flusso di lavoro specifico. Se si seleziona questa opzione, è necessario selezionare il flusso di lavoro nel campo Nome.  
5. Nel campo Delega selezionare l'utente a cui si desidera delegare gli elementi di lavoro.
    * Specificare il momento in cui gli elementi di lavoro devono essere delegati automaticamente nei campi Data/ora di inizio e Data/ora di fine.  
6. Nel campo Data/ora di inizio immettere una data e un'ora.
7. Nel campo Data/ora di fine immettere una data e un'ora.
8. Selezionare la casella di controllo Attivato per attivare la regola di delega.
    * Se è stato selezionato Modulo come ambito, è necessario selezionare il modulo nel campo Nome.    Se è stato selezionato Flusso di lavoro come ambito, è necessario selezionare lo specifico flusso di lavoro da delegare nel campo Nome.  
9. Nel campo Commento immettere un commento che spiega il motivo della delega degli elementi di lavoro.


