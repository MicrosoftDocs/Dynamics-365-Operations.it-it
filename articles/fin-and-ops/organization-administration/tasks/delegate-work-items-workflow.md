---
title: Delegare elementi di lavoro in un flusso di lavoro
description: Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f85a1318822ceaf829134bf2eb3581e350d5bea4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "346251"
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

