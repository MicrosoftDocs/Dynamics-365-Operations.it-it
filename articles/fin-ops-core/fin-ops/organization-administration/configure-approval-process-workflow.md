---
title: Configurare i processi di approvazione in un flusso di lavoro
description: Per configurare le proprietà del processo di approvazione, attenersi alla procedura indicata di seguito.
author: ChrisGarty
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998ee15d828feefb0a9691138ae8001331283d5b866386500f5cf5de48291b43
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756323"
---
# <a name="configure-approval-processes-in-a-workflow"></a>Configurare i processi di approvazione in un flusso di lavoro

[!include [banner](../includes/banner.md)]

Per configurare le proprietà del processo di approvazione, attenersi alla procedura indicata di seguito.

Per configurare un processo di approvazione, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento di approvazione e scegliere **Proprietà** per aprire il modulo **Proprietà**.

## <a name="name-the-approval-process"></a>Assegnare un nome al processo di approvazione

Per immettere un nome per il processo di approvazione, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Nome** immettere un nome univoco per il processo di approvazione.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Specificare se il sistema esegue automaticamente un'azione sul documento

È possibile configurare il sistema in modo che venga automaticamente eseguita un'azione sul documento, se vengono soddisfatte determinate condizioni. Il sistema può ad esempio approvare le note spese con importi totali inferiori a USD 100. Per specificare se il sistema esegue automaticamente un'azione sul documento, attenersi alla procedura indicata di seguito.

1. Nel riquadro sinistro fare clic su **Azioni automatiche**.
2. Selezionare la casella di controllo **Attiva azioni automatiche**.
3. Fare clic su **Aggiungi condizione**.
4. Immettere una condizione.
5. Se necessario, immettere condizioni aggiuntive.
6. Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:

    1. Fare clic su **Test** per aprire il modulo **Test condizione flusso di lavoro**.
    2. Selezionare un record nell'area **Convalida condizione** del modulo.
    3. Fare clic su **Test**. Il sistema valuta il record per determinare se soddisfa le condizioni definite.
    4. Fare clic su **OK** o **Annulla** per tornare al modulo **Proprietà**.

7. Nell'elenco **Azione completamento automatico** selezionare l'azione che dovrà essere eseguita sul documento.

## <a name="specify-when-notifications-are-sent"></a>Specificare quando verranno inviate le notifiche

È possibile inviare notifiche agli utenti se un documento è stato approvato, rifiutato, delegato o riassegnato oppure se è stata richiesta una modifica. Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro fare clic su **Notifiche**.
2. Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:

    - **Delega**: se un documento è stato assegnato a un altro utente per l'approvazione.
    - **Riassegna**: se l'utente assegnato non ha eseguito un'azione sul documento nel tempo prestabilito.
    - **Approva**: se un documento è stato approvato.
    - **Rifiuta**: se un documento è stato rifiutato.
    - **Richiedi modifica**: se l'utente assegnato ha richiesto una modifica a un documento inviato.

3. Scegliere la riga per un evento selezionato nel passaggio 2.
4. Fare clic sulla scheda **Testo notifiche**.
5. Nella casella di testo immettere il testo per la notifica.
6. Per personalizzare il testo, è possibile inserire segnaposto che verranno sostituiti con i dati appropriati al momento della visualizzazione. Per inserire un segnaposto, effettuare le operazioni seguenti:

    1. Fare clic sulla casella di testo nel punto in cui verrà visualizzato il segnaposto.
    2. Fare clic su **Inserisci segnaposto**.
    3. Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4. Fare clic su **Inserisci**.

7. Per aggiungere traduzioni della notifica, fare clic su **Traduzioni**. Nel modulo visualizzato attenersi alla procedura indicata di seguito.

    1. Fare clic su **Aggiungi**.
    2. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    3. Nella casella di testo **Testo tradotto** immettere il testo.
    4. Per personalizzare il testo, inserire segnaposto.
    5. Fare clic su **Chiudi**.

8. Fare clic sulla scheda **Destinatario**.
9. Specificare i destinatari delle notifiche. Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 10.

    <table>
    <thead>
    <tr>
    <th>Opzione</th>
    <th>Destinatari delle notifiche</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><strong>Partecipante</strong></td>
    <td>Utenti assegnati a un ruolo o un gruppo specifico</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Partecipante</strong> fare clic sulla scheda <strong>Basato sui ruoli</strong>.</li>
    <li>Nell'elenco <strong>Tipo di partecipante</strong> selezionare il tipo di gruppo o ruolo a cui si desidera inviare notifiche.</li>
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Utente del flusso di lavoro</strong></td>
    <td>Utenti che partecipano al flusso di lavoro corrente</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, fare clic sulla scheda <strong>Utente del flusso di lavoro</strong>.</li>
    <li>Nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Utente</strong></td>
    <td>Utenti specifici</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</li>
    <li>Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. Ripetere i passaggi dal 3 al 9 per ciascun evento selezionato nel passaggio 2.

## <a name="specify-a-final-approver"></a>Specificare un approvatore finale

È possibile designare un approvatore finale per gli scenari in cui l'approvatore è la persona che ha inviato il documento per l'approvazione e si utilizza "Non consentire l'approvazione da parte dell'autore dell'invio". Per specificare un approvatore finale, effettuare le operazioni indicate di seguito.

1. Nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento di approvazione e selezionare **Proprietà** per aprire il modulo **Proprietà**.
2. Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.
3. Selezionare la casella di controllo **Usa approvatore finale**.
4. Selezionare nell'elenco un utente che si desidera impostare come approvatore finale.

## <a name="set-a-time-limit"></a>Impostare un limite di tempo

Se è necessario completare il processo di approvazione in un periodo di tempo specifico, attenersi alla procedura indicata di seguito.

> [!NOTE]
> Le opzioni selezionate in questi passaggi prevalgono su quelle selezionate nelle aree **Assegnazione** e **Riassegnazione** di ogni passaggio di approvazione.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.
2. Selezionare la casella di controllo **Imposta un limite di tempo** per **l'elemento del flusso di lavorol'elemento del flusso di lavoro**.
3. Nel campo **Durata** specificare il momento in cui completare il processo di approvazione. Consente di selezionare una delle opzioni indicate di seguito.

    - **Ore**: immettere il numero di ore entro le quali deve essere completato il processo di approvazione. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Giorni**: immettere il numero di giorni entro i quali deve essere completato il processo di approvazione. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Settimane**: immettere il numero di settimane entro le quali deve essere completato il processo di approvazione.
    - **Mesi**: selezionare il giorno e la settimana entro i quali deve essere completato il processo di approvazione. È ad esempio possibile scegliere di completare il processo di approvazione entro il venerdì della terza settimana del mese.
    - **Anni**: selezionare il giorno, la settimana e il mese entro i quali deve essere completato il processo di approvazione. È ad esempio possibile scegliere di completare il processo di approvazione entro il venerdì della terza settimana di dicembre.

4. Se viene superato il limite di tempo, l'azione verrà eseguita dal sistema. Nell'elenco **Azione** selezionare l'azione che dovrà essere eseguita dal sistema.

## <a name="specify-which-actions-are-available-to-the-user"></a>Specificare le azioni disponibili per l'utente

Quando un documento viene assegnato per l'approvazione a un utente, quest'ultimo deve eseguire un'azione su di esso. Per specificare le azioni che l'utente può eseguire sul documento inviato, attenersi alla procedura indicata di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.
2. Selezionare la casella di controllo **Approva** se l'utente può approvare il documento.
3. Selezionare la casella di controllo **Rifiuta** se l'utente può rifiutare il documento.
4. Selezionare la casella di controllo **Richiedi modifica** se l'utente può richiedere modifiche al documento.
5. Selezionare la casella di controllo **Delega** se l'utente può assegnare il documento a un altro utente per l'approvazione.

> [!NOTE]
> La casella di controllo **Attiva azioni dall'elenco di lavoro in Enterprise Portal** è stata rimossa.

## <a name="configure-the-approval-steps"></a> Configurare i passaggi di approvazione

Un processo di approvazione è costituito da passaggi di approvazione. Per aggiungere passaggi al processo e configurarli, attenersi alla procedura indicata di seguito.

1. Nell'editor flusso di lavoro fare doppio clic sul processo di approvazione. Verranno visualizzati i passaggi del processo di approvazione.
2. Per aggiungere un passaggio di approvazione, trascinarlo dall'area **Elementi flusso di lavoro** nella canvas.
3. Per configurare un passaggio di approvazione, vedere [Configurare i passaggi di approvazione in un flusso di lavoro](configure-approval-step-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]