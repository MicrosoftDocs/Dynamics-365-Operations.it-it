---
title: Configurare le proprietà del flusso di lavoro
description: In questo articolo viene descritto come configurare le proprietà per un flusso di lavoro.
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec604ed9614b80b3b24c670911b4ea480d6131e2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876443"
---
# <a name="configure-workflow-properties"></a>Configurare le proprietà del flusso di lavoro

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

In questo articolo viene descritto come configurare le proprietà per un flusso di lavoro.

Per configurare le proprietà di un flusso di lavoro, aprirlo nell'editor flusso di lavoro. Fare clic sulla canvas dell'editor flusso di lavoro, quindi scegliere **Proprietà** per aprire la pagina **Proprietà**. Per configurare le diverse proprietà del flusso di lavoro, attenersi alle procedure indicate di seguito.

## <a name="name-the-workflow"></a>Assegnare un nome al flusso di lavoro

Per immettere un nome per il flusso di lavoro, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Nome** immettere un nome univoco per il flusso di lavoro. Se ad esempio si creano flussi di lavoro relativi alle richieste di acquisto per ciascun paese in cui opera una società, è possibile assegnare a uno di questi flussi di lavoro il nome **Richieste di acquisto Danimarca** o **Richieste di acquisto Spagna**.

## <a name="specify-the-workflow-owner"></a>Specificare il proprietario del flusso di lavoro

Il proprietario del flusso di lavoro è la persona che si occuperà della gestione e della manutenzione del flusso. Per specificare il proprietario del flusso di lavoro, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nell'elenco **Proprietario** selezionare il nome della persona che gestirà il flusso di lavoro.

## <a name="select-an-email-template"></a>Selezionare un modello di messaggio di posta elettronica

Per selezionare il modello di messaggio di posta elettronica che verrà utilizzato per generare notifiche per il flusso di lavoro, attenersi alla procedura indicata di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nell'elenco **Modelli di messaggio di posta elettronica per le notifiche del flusso di lavoro** selezionare il modello.

## <a name="enter-instructions-for-users"></a>Immettere istruzioni per gli utenti

È possibile fornire istruzioni agli utenti che invieranno documenti per l'elaborazione e l'approvazione. Questi utenti vengono indicati come *iniziatori*. Si supponga ad esempio di dover creare un flusso di lavoro relativo alle richieste di acquisto e di immettere le istruzioni. Tali istruzioni possono essere visualizzate dagli utenti che immettono richieste di acquisto nella pagina **Richieste di acquisto**. Per visualizzare le istruzioni, l'iniziatore dovrà fare clic sull'icona nell barra dei messaggi del flusso di lavoro. Per immettere istruzioni per gli utenti, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Istruzioni di invio** immettere le istruzioni.
3. Per personalizzare le istruzioni, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione. Per inserire un segnaposto, effettuare le operazioni seguenti:

    1. Fare clic sul campo **Istruzioni di invio** per specificare il punto in cui deve essere inserito il segnaposto.
    2. Fare clic su **Inserisci segnaposto**.
    3. Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4. Fare clic su **Inserisci**.

4. Per aggiungere traduzioni delle istruzioni, effettuare le operazioni seguenti:

    1. Fare clic su **Traduzioni**.
    2. Nella pagina visualizzata fare clic su **Aggiungi**.
    3. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4. Nel campo **Testo tradotto** immettere il testo.
    5. Per personalizzare il testo, è possibile inserire segnaposto. Per istruzioni su come immettere un segnaposto, vedere il passaggio 3.
    6. Fare clic su **Chiudi**.

> [!NOTE]
> I segnaposto non possono essere aggiunti utilizzando copia e incolla perché le informazioni sulla destinazione non vengono incollate correttamente. Utilizza l'interfaccia per aggiungere segnaposto.

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a>Specificare quando questo flusso di lavoro viene utilizzato con le condizioni di attivazione

È possibile creare più flussi di lavoro basati sullo stesso tipo di flusso di lavoro. Se sono presenti più flussi di lavoro basati sullo stesso tipo, è necessario specificare quando verrà utilizzato ciascun flusso utilizzando le condizioni di attivazione. Se le condizioni di attivazione non vengono soddisfatte, viene utilizzato il flusso di lavoro predefinito. Allo stesso modo, se esiste una sola configurazione del flusso di lavoro definita per un tipo di flusso di lavoro, tale configurazione del flusso di lavoro verrà utilizzata indipendentemente dalle condizioni di attivazione.

Una società può creare ad esempio flussi di lavoro relativi alle richieste di acquisto per ciascun paese in cui opera, ad esempio Richieste di acquisto Danimarca e Richieste di acquisto Spagna con le seguenti condizioni:

- Richieste di acquisto Danimarca: questo flusso di lavoro viene utilizzato quando sussiste la condizione paese = DK.
- Richieste di acquisto Spagna: questo flusso di lavoro viene utilizzato quando sussiste la condizione paese = ES.

Per specificare quando verrà utilizzato il flusso di lavoro che si sta configurando, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro fare clic su **Attivazione**.
2. Selezionare la casella di controllo **Imposta le condizioni per eseguire il flusso di lavoro**.
3. Fare clic su **Aggiungi condizione**.
4. Immettere una condizione.
5. Immettere altre condizioni, se necessario.
6. Eseguire il flusso di lavoro con alcuni record di destinazione per verificare che la condizione includa ed escluda correttamente i record.

## <a name="specify-when-notifications-are-sent"></a>Specificare quando verranno inviare le notifiche

Quando si invia un documento per l'elaborazione, viene creata un'istanza del flusso di lavoro. È possibile inviare notifiche agli utenti quando le istanze basate sul flusso di lavoro corrente vengono avviate, completate, terminate o arrestate a causa di un errore. Per specificare quando verranno inviate le notifiche, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro fare clic su **Notifiche**.
2. Selezionare la casella di controllo per ogni evento che attiverà notifiche:

    - **Avviato**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene avviata.
    - **Interrotto**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene interrotta a causa di un errore.
    - **Completato**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene completata.
    - **Irreversibile**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene interrotta a causa di un errore irreversibile.
    - **Terminato**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene terminata.

3. Scegliere la riga per un evento selezionato nel passaggio 2.
4. Nella scheda **Testo notifiche** immettere il testo della notifica.
5. Per personalizzare il testo, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione del testo. Per inserire un segnaposto, effettuare le operazioni seguenti:

    1. Fare clic sul campo per specificare il punto in cui deve essere inserito il segnaposto.
    2. Fare clic su **Inserisci segnaposto**.
    3. Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4. Fare clic su **Inserisci**.
    5. Un comune segnaposto **Testo di notifica** da includere è "Note più recenti: %Workflow.Last note%", che visualizza tutti i commenti dal passaggio precedente.

6. Per aggiungere traduzioni del testo, effettuare le operazioni seguenti:

    1. Fare clic su **Traduzioni**.
    2. Nella pagina visualizzata fare clic su **Aggiungi**.
    3. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4. Nel campo **Testo tradotto** immettere il testo.
    5. Per personalizzare il testo, è possibile inserire segnaposto. Per istruzioni su come immettere un segnaposto, vedere il passaggio 5.
    6. Fare clic su **Chiudi**.

7. Nella scheda **Destinatario** utilizzare le opzioni seguenti per specificare l'utente che deve ricevere le notifiche.

    <table>
    <thead>
    <tr>
    <th>Opzione</th>
    <th>Le notifiche vengono inviate a questi utenti</th>
    <th>Per inviare notifiche, effettuare le operazioni seguenti.</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Partecipante</td>
    <td>Utenti assegnati a un ruolo o un gruppo specifico</td>
    <td>
    <ol>
    <li>Nella scheda <strong>Destinatario</strong> fare clic su <strong>Partecipante</strong>.</li>
    <li>Nella scheda <strong>Basato sui ruoli</strong>, nell'elenco <strong>Tipo di partecipante</strong> selezionare il tipo di gruppo o il ruolo a cui inviare le notifiche.</li>
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utente del flusso di lavoro</td>
    <td>Utenti che partecipano al flusso di lavoro corrente</td>
    <td>
    <ol>
    <li>Nella scheda <strong>Destinatario</strong>, fare clic su <strong>Utente del flusso di lavoro</strong>.</li>
    <li>Nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un partecipante al flusso di lavoro.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utente</td>
    <td>Utenti specifici</td>
    <td>
    <ol>
    <li>Nella scheda <strong>Destinatario</strong>, fare clic su <strong>Utente</strong>.</li>
    <li>Nella scheda <strong>Utente</strong>, nell'elenco <strong>Utenti disponibili</strong> sono presenti tutti gli utenti. Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Ripetere i passaggi dal 3 al 7 per ciascun evento selezionato nel passaggio 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Immettere commenti sulle modifiche apportate al flusso di lavoro.

Per immettere commenti sulle modifiche apportate al flusso di lavoro, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro fare clic su **Note**.
2. Nel campo **Immettere commenti sul flusso di lavoro** immettere i commenti.
3. Rivedere i commenti. Dopo aver aggiunto i commenti, non sarà più possibile modificarli.
4. Fare clic su **Aggiungi** per aggiungere commenti all'are **Cronologia commenti**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]