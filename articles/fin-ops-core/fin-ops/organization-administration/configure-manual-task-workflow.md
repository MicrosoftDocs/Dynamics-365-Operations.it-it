---
title: Configurare le attività manuali in un flusso di lavoro
description: In questo argomento viene descritto come configurare le proprietà per un'attività manuale.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b114448db4f70ec1ef3fcae539030238659f37393e6d5ae126666348343ad47
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712487"
---
# <a name="configure-manual-tasks-in-a-workflow"></a>Configurare le attività manuali in un flusso di lavoro

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come configurare le proprietà per un'attività manuale.

Per configurare un'attività manuale, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'attività, quindi scegliere **Proprietà** per aprire la pagina **Proprietà**. Per configurare le proprietà dell'attività manuale, attenersi alle procedure indicate di seguito.

## <a name="name-the-task"></a>Assegnare un nome all'attività

Per immettere un nome per l'attività manuale, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Nome** immettere un nome univoco per l'attività.

## <a name="enter-a-subject-line-and-instructions"></a>Immettere una riga di argomento e le istruzioni

La riga di argomento e le istruzioni sono necessarie agli utenti assegnati all'attività. Se ad esempio si configura un'attività per richieste di acquisto, l'utente assegnato all'attività visualizzerà la riga di argomento e le istruzioni nella pagina **Richieste di acquisto**. La riga di argomento si trova nella barra dei messaggi della pagina. L'utente può fare clic sull'icona nella barra per visualizzare le istruzioni. Per immettere una riga di argomento e le istruzioni, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Argomento elemento di lavoro** immettere la riga di argomento.
3. Per personalizzare la riga di argomento, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della riga di argomento. Per inserire un segnaposto, effettuare le operazioni seguenti:

    1. Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.
    2. Fare clic su **Inserisci segnaposto**.
    3. Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4. Fare clic su **Inserisci**.

4. Per aggiungere traduzioni della riga di argomento, effettuare le operazioni seguenti:

    1. Fare clic su **Traduzioni**.
    2. Nella pagina visualizzata fare clic su **Aggiungi**.
    3. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4. Nel campo **Testo tradotto** immettere il testo.
    5. Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 3.
    6. Fare clic su **Chiudi**.

5. Nel campo **Istruzioni elemento di lavoro** immettere le istruzioni.
6. Per personalizzare le istruzioni, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione. Per inserire un segnaposto, effettuare le operazioni seguenti:

    1. Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.
    2. Fare clic su **Inserisci segnaposto**.
    3. Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4. Fare clic su **Inserisci**.

7. Per aggiungere traduzioni delle istruzioni, effettuare le operazioni seguenti:

    1. Fare clic su **Traduzioni**.
    2. Nella pagina visualizzata fare clic su **Aggiungi**.
    3. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4. Nel campo **Testo tradotto** immettere il testo.
    5. Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 6.
    6. Fare clic su **Chiudi**.

## <a name="assign-the-task"></a>Assegnare l'attività

Per specificare gli utenti a cui assegnare l'attività manuale, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Assegnazione**.
2. Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 3.

    <table>
    <thead>
    <tr>
    <th>Opzione</th>
    <th>Utenti a cui viene assegnata l'attività</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Partecipante</td>
    <td>Utenti assegnati a un ruolo o un gruppo specifico</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui assegnare l'attività nell'elenco <strong>Tipo di partecipante</strong>.</li>
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il gruppo o il ruolo a cui assegnare l'attività.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Gerarchia</td>
    <td>Utenti in una specifica gerarchia organizzativa</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui assegnare l'attività nell'elenco <strong>Tipo di gerarchia</strong>.</li>
    <li>Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia. Questi nomi rappresentano gli utenti a cui può essere assegnata l'attività. Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema: <ol>
    <li>Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</li>
    <li>Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>. Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</li>
    </ol>
    </li>
    <li>Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo l'attività deve essere assegnata: <ul>
    <li><strong>Assegna a tutti gli utenti recuperati</strong> - L'attività viene assegnata a tutti gli utenti nell'intervallo.</li>
    <li><strong>Assegna solo all'ultimo utente recuperato</strong> - L'attività viene assegnata solo all'ultimo utente dell'intervallo.</li>
    <li><strong>Escludi utenti con la seguente condizione:</strong> - L'attività non viene assegnata ad alcun utente nell'intervallo che soddisfa una specifica condizione. Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utente del flusso di lavoro</td>
    <td>Utenti nel flusso di lavoro corrente</td>
    <td>
    <ul>
    <li>Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Utente</td>
    <td>Utenti specifici</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</li>
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti. Selezionare gli utenti a cui assegnare l'attività, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Coda</td>
    <td>Coda di elementi di lavoro</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Coda</strong> fare clic sulla scheda <strong>Basato su coda</strong>.</li>
    <li>Per assegnare l'attività a una specifica coda, effettuare le operazioni seguenti: <ol>
    <li>Nell'elenco <strong>Tipo coda</strong> selezionare <strong>Coda di elementi di lavoro</strong>.</li>
    <li>Nell'elenco <strong>Nome coda</strong> selezionare la coda.</li>
    </ol>
    </li>
    <li>Se una specifica condizione deve determinare la coda a cui viene assegnata l'attività, effettuare le operazioni seguenti: <ol>
    <li>Nell'elenco <strong>Tipo coda</strong> selezionare <strong>Code di elementi di lavoro condizionali</strong>.</li>
    <li>Nell'elenco <strong>Nome coda</strong> selezionare <strong>Coda condizionale</strong>.</li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] Questa opzione viene utilizzata solo per alcuni flussi di lavoro, ad esempio la gestione dei casi.</blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. Nella scheda **Limite di tempo**, nel campo **Durata** specificare il tempo a disposizione di un utente per completare l'attività. Consente di selezionare una delle opzioni indicate di seguito.

    - **Ore**: immettere il numero di ore a disposizione dell'utente per completare l'attività. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Giorni**: immettere il numero di giorni a disposizione dell'utente per completare l'attività. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Settimane**: immettere il numero di settimane a disposizione dell'utente per completare l'attività.
    - **Mesi**: selezionare il giorno e la settimana entro cui l'utente deve completare l'attività. È ad esempio possibile scegliere che l'utente completi l'attività entro il venerdì della terza settimana del mese.
    - **Anni**: selezionare il giorno, la settimana e il mese entro cui l'utente deve completare l'attività. È ad esempio possibile scegliere che l'utente completi l'attività entro il venerdì della terza settimana di dicembre.

    Se l'utente non completa l'attività nel tempo prestabilito, l'attività scadrà. Un'attività scaduta può essere riassegnata in base alle opzioni selezionate nell'area **Riassegnazione** della pagina.

## <a name="specify-what-happens-when-the-task-is-overdue"></a>Specificare l'azione da eseguire quando l'attività è scaduta

Se un utente non completa l'attività manuale nel tempo prestabilito, l'attività scadrà. Un'attività scaduta può essere riassegnata o assegnata automaticamente a un altro utente. Per riassegnare l'attività scaduta, effettuare le operazioni seguenti.

1. Nel riquadro sinistro fare clic su **Riassegnazione**.
2. Selezionare la casella di controllo **Utilizza percorso di riassegnazione** per creare un percorso di riassegnazione. L'attività verrà assegnata automaticamente agli utenti elencati nel percorso. La tabella indicata di seguito rappresenta un esempio di percorso di riassegnazione.

    | Sequenza | Percorso di riassegnazione      |
    |----------|----------------------|
    | 1        | Assegna a: Maria     |
    | 2        | Assegna a: Francesca      |
    | 3        | Azione finale: Rifiuta |

    In questo esempio l'attività scaduta viene assegnata a Maria. Se Maria non completa l'attività nel tempo prestabilito, l'attività verrà assegnata a Francesca. Se Francesca non completa l'attività nel tempo prestabilito, il sistema rifiuta il documento inviato per l'elaborazione.

3. Per aggiungere un utente al percorso di riassegnazione, fare clic su **Aggiungi riassegnazione**. Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 4.

    <table>
    <thead>
    <tr>
    <th>Opzione</th>
    <th>Utenti a cui viene riassegnata l'attività</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Gerarchia</td>
    <td>Utenti in una specifica gerarchia organizzativa</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui riassegnare l'attività nell'elenco <strong>Tipo di gerarchia</strong>.</li>
    <li>Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia. Questi nomi rappresentano gli utenti a cui può essere riassegnata l'attività. Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema: <ol>
    <li>Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</li>
    <li>Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>. Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</li>
    </ol>
    </li>
    <li>Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo l'attività deve essere riassegnata: <ul>
    <li><strong>Assegna a tutti gli utenti recuperati</strong> - L'attività viene riassegnata a tutti gli utenti nell'intervallo.</li>
    <li><strong>Assegna solo all'ultimo utente recuperato</strong> - L'attività viene riassegnata solo all'ultimo utente dell'intervallo.</li>
    <li><strong>Escludi utenti con la seguente condizione:</strong> - L'attività non viene riassegnata ad alcun utente nell'intervallo che soddisfa una specifica condizione. Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utente del flusso di lavoro</td>
    <td>Utenti nel flusso di lavoro corrente</td>
    <td>
    <ul>
    <li>Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Utente</td>
    <td>Utenti specifici</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</li>
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti. Selezionare gli utenti a cui riassegnare l'attività, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Nella scheda **Limite di tempo**, nel campo **Durata** specificare il tempo a disposizione di un utente per completare l'attività. Consente di selezionare una delle opzioni indicate di seguito.

    - **Ore**: immettere il numero di ore a disposizione dell'utente per completare l'attività. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Giorni**: immettere il numero di giorni a disposizione dell'utente per completare l'attività. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Settimane**: immettere il numero di settimane a disposizione dell'utente per completare l'attività.
    - **Mesi**: selezionare il giorno e la settimana entro cui l'utente deve completare l'attività. È ad esempio possibile scegliere che l'utente completi l'attività entro il venerdì della terza settimana del mese.
    - **Anni**: selezionare il giorno, la settimana e il mese entro cui l'utente deve completare l'attività. È ad esempio possibile scegliere che l'utente completi l'attività entro il venerdì della terza settimana di dicembre.

5. Ripetere i passaggi da 3 a 4 per ogni utente che si desidera aggiungere al percorso di riassegnazione. È possibile modificare l'ordine degli utenti.
6. Se gli utenti nel percorso di riassegnazione non completano l'attività nel tempo prestabilito, verrà eseguita un'azione sull'attività dal sistema. Per specificare l'azione presa dal sistema, selezionare la riga **Azione**, quindi nella scheda **Termina azione** selezionare un'opzione.

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a>Specificare quando il sistema deve eseguire automaticamente un'azione sull'attività

È possibile configurare il sistema in modo che venga eseguita automaticamente un'azione sull'attività, se vengono soddisfatte specifiche condizioni. Si supponga, ad esempio, che un'attività richieda che un membro del reparto responsabile delle note spese verifichi le ricevute inviate insieme a una nota spese. In base alle politiche aziendali, tale attività deve essere eseguita se l'importo totale della nota spese è maggiore di USD 100. In questo scenario è possibile configurare il sistema in modo che l'attività venga contrassegnata automaticamente come **Completa** quando l'importo totale è inferiore a 100. Per specificare quando il sistema deve eseguire automaticamente un'azione sull'attività manuale, attenersi alla procedura indicata di seguito.

1. Nel riquadro sinistro fare clic su **Azioni automatiche**.
2. Selezionare la casella di controllo **Attiva azioni automatiche**.
3. Fare clic su **Aggiungi condizione**.
4. Immettere una condizione.
5. Immettere altre condizioni, se necessario.
6. Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:

    1. Fare clic su **Test**.
    2. Nella pagina **Test condizione flusso di lavoro**, nell'area **Convalida condizione**, selezionare un record.
    3. Fare clic su **Test**. Il sistema valuta il record per determinare se soddisfa le condizioni definite.
    4. Fare clic su **OK** o su **Annulla** per tornare alla pagina **Proprietà**.

7. Nell'elenco **Azione completamento automatico** selezionare l'azione che dovrà essere eseguita sull'attività dal sistema.

## <a name="specify-when-notifications-are-sent"></a>Specificare quando verranno inviare le notifiche

È possibile inviare notifiche agli utenti quando un'attività manuale è stata delegata, riassegnata, completata o rifiutata oppure quando è stata richiesta una modifica. Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro fare clic su **Notifiche**.
2. Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:

    - **Delega**: se l'attività è stata assegnata a un altro utente.
    - **Riassegna**: se l'utente assegnato non ha completato l'attività nel tempo prestabilito.
    - **Completa**: se l'utente assegnato ha completato l'attività.
    - **Rifiuta**: se l'utente assegnato ha rifiutato il documento inviato.
    - **Richiedi modifica**: se l'utente assegnato ha richiesto una modifica al documento inviato.

3. Scegliere la riga per un evento selezionato nel passaggio 2.
4. Nella scheda **Testo notifiche** immettere il testo della notifica nella casella di testo.
5. Per personalizzare la notifica, è possibile inserire segnaposto. I segnaposto verranno sostituiti con le informazioni appropriate al momento della visualizzazione della notifica. Per inserire un segnaposto, effettuare le operazioni seguenti:

    1. Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.
    2. Fare clic su **Inserisci segnaposto**.
    3. Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4. Fare clic su **Inserisci**.

6. Per aggiungere traduzioni della notifica, effettuare le operazioni seguenti:

    1. Fare clic su **Traduzioni**.
    2. Nella pagina visualizzata fare clic su **Aggiungi**.
    3. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4. Nel campo **Testo tradotto** immettere il testo.
    5. Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 5.
    6. Fare clic su **Chiudi**.

7. Nella scheda **Destinatario** specificare il destinatario cui inviare le notifiche. Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 8.

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
    <td>Partecipante</td>
    <td>Utenti assegnati a un ruolo o un gruppo specifico</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui inviare le notifiche nell'elenco <strong>Tipo di partecipante</strong>.</li>
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utente del flusso di lavoro</td>
    <td>Utenti nel flusso di lavoro corrente</td>
    <td>
    <ul>
    <li>Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Utente</td>
    <td>Utenti specifici</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</li>
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti. Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Ripetere i passaggi dal 3 al 7 per ciascun evento selezionato nel passaggio 2.

## <a name="set-a-time-limit"></a>Impostare un limite di tempo

Se è necessario completare l'attività manuale in un periodo di tempo specifico, attenersi alla procedura indicata di seguito.

> [!NOTE]
> Le opzioni selezionate in questi passaggi prevalgono su quelle selezionate nelle aree **Assegnazione** e **Riassegnazione** della pagina.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.
2. Selezionare la casella di controllo **Imposta un limite di tempo per l'elemento del flusso di lavoro**.
3. Nel campo **Durata** specificare il momento in cui completare l'attività. Consente di selezionare una delle opzioni indicate di seguito.

    - **Ore**: immettere il numero di ore entro cui deve essere completata l'attività. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Giorni**: immettere il numero di giorni entro cui deve essere completata l'attività. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Settimane**: immettere il numero di settimane entro cui deve essere completata l'attività.
    - **Mesi**: selezionare il giorno e la settimana entro cui deve essere completata l'attività. È ad esempio possibile scegliere di completare il processo di approvazione entro il venerdì della terza settimana del mese.
    - **Anni**: selezionare il giorno, la settimana e il mese entro cui deve essere completata l'attività. È ad esempio possibile scegliere che l'attività venga completata entro il venerdì della terza settimana di dicembre.

4. Se viene superato il limite di tempo, l'azione sull'attività verrà eseguita dal sistema. Nell'elenco **Azione** selezionare l'azione che dovrà essere eseguita dal sistema.

## <a name="specify-which-actions-are-available-to-the-user"></a>Specificare le azioni disponibili per l'utente

Quando l'attività manuale viene assegnata a un utente, quest'ultimo dovrà eseguire un'azione sull'attività. Per specificare le azioni che possono essere eseguite dall'utente sull'attività, attenersi alla procedura indicata di seguito.

> [!NOTE]
> Le azioni disponibili variano in base al modo in cui l'attività è stata progettata.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.
2. Selezionare la casella di controllo **Completa** se si desidera consentire all'utente di contrassegnare l'attività come **Completa**.
3. Selezionare la casella di controllo **Rifiuta** se si desidera consentire all'utente di rifiutare il documento inviato.
4. Selezionare la casella di controllo **Richiedi modifica** se si desidera consentire all'utente di richiedere modifiche del documento inviato.
5. Selezionare la casella di controllo **Delega** se si desidera consentire all'utente di assegnare l'attività a un altro utente.
6. Selezionare la casella di controllo **Riassegna** se si desidera consentire all'utente di riassegnare l'attività a un altro utente nella coda di elementi di lavoro.
7. Selezionare la casella di controllo **Rilascio** se si desidera consentire all'utente di riassegnare l'attività alla coda di elementi di lavoro. Un altro utente potrà quindi completare l'attività.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]