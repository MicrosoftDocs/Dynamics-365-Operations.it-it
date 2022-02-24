---
title: Programmare i colloqui in Attract
description: In questo argomento vengono fornite informazioni sulla programmazione del colloquio e sulle attività di riscontro in Attract.
author: hasrivas
manager: AnnBe
ms.date: 04/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: shielas
ms.openlocfilehash: 33eba9796ca997fde4be9a46050207d313551bde
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461667"
---
# <a name="schedule-interviews-in-attract"></a>Programmare i colloqui in Attract

[!include [banner](includes/banner.md)]

## <a name="scheduler-activity"></a>Attività responsabile della programmazione

L'attività programmazione è facoltativa e include due componenti: Richiesta disponibilità candidato e Programmazione. Componente Disponibilità candidato consente di utilizzare la posta elettronica per richiedere la disponibilità del candidato. Il componente Programmazione consente di programmare i colloqui con il candidato e il team di assunzione.

Per impostare l'attività programmazione e includere o limitare i candidati da programmare, selezionare un valore nel campo **Chi si sta programmando**. Le opzioni disponibili sono **Tutti i candidati**, **Candidati esterni** e **Candidati interni**. Ad esempio, per ignorare i candidati interni nel primo ciclo di programmazione, è possibile assegnare l'attività di programmazione solo ai candidati esterni impostando **Chi si sta programmando** su **Candidati esterni**.

### <a name="candidate-availability-request"></a>Richiesta disponibilità candidato

Per inviare un messaggio di posta elettronica ai candidati allo scopo di richiederne la disponibilità, selezionare il campo **Richiedi disponibilità candidato**. Se il campo non è selezionato, questo passaggio non verrà visualizzato nel processo di assunzione per la mansione.

Per inviare la richiesta di disponibilità, fare clic su **Invia richiesta**, scegliere le date disponibili e un modello di messaggio di posta elettronica e quindi inviare il messaggio al candidato.

[![Vista selezionatore in Attract per inviare la richiesta di disponibilità del candidato](./media/scheduler-candidate-request.png)](./media/scheduler-candidate-request.png)

Quando il candidato riceve un messaggio di posta elettronica per rispondere alla richiesta, può accedere al portale del candidato, scegliere le date in cui è disponibile e fare clic su **Invia**.

### <a name="schedule"></a>Programmazione
Per la programmazione del colloquio sono disponibili più configurazioni che possono essere utilizzate per creare rapidamente e inviare il ciclo di colloquio ai responsabili del colloquio e al candidato.

1. Fare clic su **Crea programmazione** e nella casella **Aggiungi responsabili del colloquio**, elencare tutti i responsabili del colloquio che faranno parte del ciclo di colloquio.
[![Vista responsabile del colloquio in Attract per avviare la programmazione di un ciclo di colloquio](./media/schedule-start-over.png)](./media/schedule-start-over.png)   
    Se il candidato ha risposto alla richiesta di disponibilità per il colloquio, nel campo **Data colloquio** verrà visualizzata la data selezionata. È possibile selezionare una data differente se necessario.
    
    Se si seleziona il campo **Imposta come colloquio di gruppo**, il gruppo di responsabili del colloquio a sinistra viene spostato in un singolo ciclo di colloquio di gruppo per creare il colloquio. Sarà quindi necessario definire una sequenza specifica per i colloqui.
    
    La programmazione dei colloqui deve soddisfare al meglio la disponibilità dei partecipanti. In caso di candidato interno, è possibile includerne la disponibilità nel suggerimento di programmazione.
    
    Per una riunione online, selezionare il campo **Aggiungi riunioni di Skype** e ciascun evento di colloquio avrà un collegamento **Skype for Business** disponibile.

2. Selezionare la durata del colloquio per ogni evento di colloquio e fare clic su **OK** per avviare la creazione della programmazione.

    Se il campo **Suggerimenti** è selezionato, i suggerimenti saranno visualizzati e la griglia di colloqui sarà prepopolata. Sarà possibile visualizzare la disponibilità nel calendario corrente di tutti i responsabili del colloquio selezionati. Sarà inoltre possibile visualizzare il calendario del candidato se si tratta di un candidato interno. Per gli intervistatori e i candidati interni, è possibile visualizzare le fasce orarie occupate, le ore lavorative, le ore fuori sede nonché identificare se hanno contrassegnato i propri calendari come al lavoro altrove per specifiche fasce orarie. 

3. Se non vi sono suggerimenti disponibili, nella colonna **Responsabili del colloquio**, fare clic su una fascia oraria, indicare il titolo e i dettagli del colloquio e immettere le informazioni sull'ubicazione, come necessario. È possibile scegliere di includere il collegamento **Skype for Business** per il colloquio.

4. Per includere ulteriori responsabili del colloquio, fare clic sulla colonna della griglia **Aggiungi colloquio** per selezionare uno o più responsabili del colloquio. È possibile utilizzare i puntini di sospensione (...) per rimuovere un colloquio dal ciclo.
    
5. Se i colloqui sono programmati in un fuso orario diverso, selezionare la città o il fuso orario dall'elenco a discesa in alto a destra. La griglia di disponibilità del responsabile del colloquio verrà aggiornata in base al nuovo fuso orario. La selezione del fuso orario verrà ora visualizzata anche nella visualizzazione **Riepilogo colloquio**, che sarà condivisa con i responsabili del colloquio e il candidato. 

6. Fare clic su **Invia a responsabili del colloquio** per inviare gli inviti alla riunione ai responsabili del colloquio interessati.

    Dopo l'invio delle richieste di colloquio ai responsabili del colloquio, questi possono rispondere direttamente all'invito ricevuto tramite posta elettronica.

    >[!NOTE]
    > Per tutti i colloqui 1:1, i promemoria vengono inviati ai responsabili del colloquio ogni 24 ore se il responsabile del colloquio non ha risposto (accettato o rifiutato) alla richiesta di colloquio.

    > Per tutti i colloqui di gruppo, non sono disponibili promemoria automatici per la richiesta di colloquio. Per attivare manualmente un promemoria, modificare il colloquio e utilizzare l'opzione **Aggiorna e invia** per inviare la richiesta agli intervistatori.

    Le risposte dei responsabili del colloquio vengono acquisite e visualizzate in Attract. Se un responsabile del colloquio declina l'invito, si riceverà una notifica che informa della necessità di apportare una modifica. Per visualizzare la risposta nella griglia **Responsabile della programmazione**, fare clic sull'icona fumetto.

[![Vista selezionatore in Attract della risposta di un responsabile del colloquio](./media/schedule-interviewer-response2.png)](./media/schedule-interviewer-response2.png)

7. Quando la programmazione del colloquio è pronta per essere condivisa con il candidato, fare clic su **Invia al candidato**. È possibile scegliere di visualizzare o nascondere i nomi dei responsabili del colloquio e le fasce orarie con il candidato.

8. Selezionare un modello di messaggio di posta elettronica e inviare il riepilogo del colloquio al candidato. Il candidato può visualizzare queste informazioni nel messaggio di posta elettronica nonché sul portale del candidato.
    
>[!NOTE] 
> La disponibilità del calendario di un candidato viene visualizzata solo in caso di candidato interno. Analogamente, i suggerimenti relativi alla programmazione dei colloqui possono essere ottimizzati solo per un candidato interno. Attualmente, i candidati (interni o esterni) non ricevono un invito alla riunione tramite posta elettronica, ma solo un riepilogo dei colloqui.

I candidati riceveranno il messaggio di posta elettronica che riepiloga il relativo ciclo di colloquio. I messaggi di posta elettronica contengono un file .ics che può essere salvato nei calendari personali per agevolare l'accesso e le notifiche relative al colloquio.

>[!TIP] 
> Nel caso si rispedisca la programmazione del colloquio al candidato, questo riceverà un altro file .ics allegato. Si consiglia di aggiornare i modelli di messaggio di posta elettronica per il riepilogo del colloquio del candidato per assicurarsi che questo elimini gli eventi di colloquio aggiunti in precedenza e non veda i duplicati nel relativo calendario. 

## <a name="feedback-activity"></a>Attività di riscontro

L'attività di riscontro è facoltativa in un modello di posizioni lavorative. Questa attività consente ai partecipanti al colloquio di fornire suggerimenti o commenti per un candidato. 

Per includere o limitare i candidati su cui fornire un riscontro, selezionare un valore nel campo **Su chi gli intervistatori devono fornire un riscontro**.  Le opzioni disponibili sono **Tutti i candidati**, **Candidati esterni** e **Candidati interni**. Ad esempio, se si desidera ignorare i candidati interni nel primo ciclo della programmazione, impostare **Su chi gli intervistatori devono fornire un riscontro** su **Candidati esterni**.

Se si seleziona il campo **Eredita i partecipanti di feedback dal team di assunzione**, il selezionatore, il responsabile delle assunzioni e quelli del colloquio vengono immessi automaticamente nell'attività di riscontro. Le organizzazioni possono consentire ai responsabili del colloquio di visualizzare il riscontro di altre persone prima di inviare la propria riscontro. Le organizzazioni possono inoltre possibile consentire ai responsabili del colloquio di modificare il riscontro dopo averlo inviato. Ai responsabili del colloquio viene ricordato di inviare il riscontro per i colloqui che hanno condotto di recente in base alla configurazione preimpostata nel modello di posizioni lavorative. Il responsabile assunzioni o un selezionatore può inoltre scegliere di ricordare manualmente a un responsabile del colloquio di inviare il riscontro.

## <a name="interview-activity"></a>Attività di colloquio

L'attività di colloquio è un'attività facoltativa con tre componenti: **Richiesta disponibilità candidato**, **Programmazione** e **Riscontro**. Utilizzare l'attività di colloquio nel modello posizioni lavorative se si desidera includere la richiesta di disponibilità del candidato, la programmazione e il riscontro durante il processo anziché utilizzarle singolarmente.

Per includere o limitare i candidati da intervistare, selezionare un valore nel campo **Chi si sta esaminando**. Le opzioni disponibili sono **Tutti i candidati**, **Candidati esterni** e **Candidati interni**. Ad esempio, se si desidera ignorare i candidati interni nel primo ciclo del colloquio, impostare **Chi si sta esaminando** su **Candidati esterni**.
