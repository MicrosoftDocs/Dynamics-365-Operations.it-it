---
title: Delegare elementi di lavoro in un flusso di lavoro
description: Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti.
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 128dce6a1b852d908e01c348cb767088031b11a5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070099"
---
# <a name="delegate-work-items-in-a-workflow"></a>Delegare elementi di lavoro in un flusso di lavoro

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

## <a name="manually-delegate-a-work-item"></a>Delegare manualmente un elemento di lavoro

Per delegare un singolo elemento di lavoro, selezionare l'opzione **Delega** nel menu **Flusso di lavoro** e immettere il nome dell'utente da delegare con un commento. In questo modo si riassegnerà l'elemento di lavoro a tale utente di modo che possa completarlo.

## <a name="manually-delegate-multiple-work-items"></a>Delega manuale di più elementi di lavoro

Più elementi di lavoro possono essere delegati insieme dalla pagina **Elementi di lavoro assegnati a me**. I seguenti tipi di flusso di lavoro sono idonei per la delega di massa: flusso di lavoro di approvazione del contratto di acquisto, flusso di lavoro dell'ordine di acquisto, revisione della richiesta di acquisto e flusso di lavoro della fattura fornitore. La funzionalità **Delega più elementi di lavoro** è disabilitata per impostazione predefinita e può essere abilitata in **Aree di lavoro > Gestione funzionalità**. Contatta l'amministratore di sistema per assistenza nell'abilitazione di questa funzionalità.
1.  Vai a **Comune> Comune> Elementi di lavoro> Elementi di lavoro assegnati a me**.
2.  Seleziona gli elementi di lavoro che verranno delegati.
3.  Fai clic sul menu **Delegare elementi di lavoro**.
4.  Nel campo **Utente** seleziona l'utente a cui vuoi delegare gli elementi di lavoro.
5.  Nel campo **Commento** immettere un commento che spiega il motivo della delega degli elementi di lavoro.
6.  Fai clic sul pulsante **Delega elementi di lavoro** per completare la delega degli elementi di lavoro.

## <a name="automatically-delegate-work-items"></a>Delegare automaticamente elementi di lavoro

Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire sugli elementi di lavoro per un periodo di tempo, è possibile delegare automaticamente i nuovi elementi di lavoro ad altri utenti utilizzando la pagina **Opzioni utente**.

### <a name="set-up-automatic-delegation"></a>Impostare la delega automatica
1. Passare a **Comune > Impostazioni > Opzioni utente**.
2. Fare clic sulla scheda **Flusso di lavoro**. Assicurarsi che la sezione Delega sia espansa. Per configurare il sistema in modo da delegare automaticamente gli elementi di lavoro ad altri utenti, è necessario creare regole di delega, che specificano il momento in cui determinati tipi di elementi di lavoro vengono delegati. Per creare una regola di delega, completare i passaggi seguenti:  
3. Scegliere **Aggiungi**.
4. Nel campo **Ambito** selezionare un'opzione:
    - Tutto: consente di delegare tutti gli elementi di lavoro assegnati all'utente.
    - Modulo: consente di delegare solo gli elementi di lavoro correlati a un tipo specifico di flusso di lavoro. Se si seleziona questa opzione, è necessario selezionare il tipo di flusso di lavoro nel campo **Nome**.
    - Flusso di lavoro: consente di delegare solo gli elementi di lavoro correlati a un flusso di lavoro specifico. Se si seleziona questa opzione, è necessario selezionare il flusso di lavoro nel campo **Nome**.  
5. Nel campo **Nome**.
    - Come ambito **Modulo**, selezionare il modulo di destinazione.
    - Come ambito **Flusso di lavoro**, selezionare il flusso di lavoro di destinazione.
6. Nel campo **Delega** selezionare l'utente a cui si desidera delegare gli elementi di lavoro. Specificare il momento in cui gli elementi di lavoro devono essere delegati automaticamente nei campi **Data/ora di inizio** e **Data/ora di fine**.  
7. Nel campo **Data/ora di inizio** immettere una data e un'ora.
8. Nel campo **Data/ora di fine** immettere una data e un'ora.
9. Selezionare la casella di controllo **Attivato** per attivare la regola di delega. 
10. Nel campo **Commento** immettere un commento che spiega il motivo della delega degli elementi di lavoro.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]