---
title: Configurare un passaggio di approvazione in un flusso di lavoro
description: "In questo argomento viene descritto come configurare le proprietà per un passaggio del processo di approvazione."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 61b3107516c7af8d1c0f4c427bdffa9be0fbc18d
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017


---

# <a name="configure-an-approval-step-in-a-workflow"></a>Configurare un passaggio di approvazione in un flusso di lavoro

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come configurare le proprietà per un passaggio del processo di approvazione.

Per configurare un passaggio di approvazione, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sul passaggio di approvazione, quindi scegliere **Proprietà** per aprire la pagina **Proprietà**. Per configurare le proprietà del passaggio di approvazione, attenersi alle procedure indicate di seguito.

## <a name="name-the-step"></a>Assegnare un nome al passaggio
Per immettere un nome per il passaggio di approvazione, effettuare le operazioni indicate di seguito.

1.  Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2.  Nel campo **Nome** immettere un nome univoco per il passaggio del processo di approvazione.

## <a name="enter-a-subject-line-and-instructions"></a>Immettere una riga di argomento e le istruzioni
La riga di argomento e le istruzioni sono necessarie agli utenti assegnati al passaggio di approvazione. Se ad esempio si configura un passaggio di approvazione per richieste di acquisto, l'utente assegnato al passaggio visualizzerà la riga di argomento e le istruzioni nel modulo **Richieste di acquisto**. La riga di argomento si trova nella barra dei messaggi della pagina. L'utente può fare clic sull'icona nella barra per visualizzare le istruzioni. Per immettere una riga di argomento e le istruzioni, effettuare le operazioni indicate di seguito.

1.  Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2.  Nel campo **Argomento elemento di lavoro** immettere la riga di argomento.
3.  Per personalizzare la riga di argomento, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della riga di argomento. Per inserire un segnaposto, effettuare le operazioni seguenti:
    1.  Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.
    2.  Fare clic su **Inserisci segnaposto**.
    3.  Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4.  Fare clic su **Inserisci**.

4.  Per aggiungere traduzioni della riga di argomento, effettuare le operazioni seguenti:
    1.  Fare clic su **Traduzioni**.
    2.  Nella pagina visualizzata fare clic su **Aggiungi**.
    3.  Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4.  Nel campo **Testo tradotto** immettere il testo.
    5.  Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 3.
    6.  Fare clic su **Chiudi**.

5.  Nel campo **Istruzioni elemento di lavoro** immettere le istruzioni.
6.  Per personalizzare le istruzioni, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione. Per inserire un segnaposto, effettuare le operazioni seguenti:
    1.  Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.
    2.  Fare clic su **Inserisci segnaposto**.
    3.  Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4.  Fare clic su **Inserisci**.

7.  Per aggiungere traduzioni delle istruzioni, effettuare le operazioni seguenti:
    1.  Fare clic su **Traduzioni**.
    2.  Nella pagina visualizzata fare clic su **Aggiungi**.
    3.  Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4.  Nel campo **Testo tradotto** immettere il testo.
    5.  Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 6.
    6.  Fare clic su **Chiudi**.

## <a name="assign-the-approval-step"></a>Assegnare il passaggio di approvazione
Per specificare gli utenti a cui assegnare il passaggio del processo di approvazione, effettuare le operazioni indicate di seguito.

1.  Nel riquadro sinistro, fare clic sull'icona **Assegnazione**.
2.  Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 3.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opzione</th>
    <th>Utenti a cui viene assegnato il passaggio del processo di approvazione</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Partecipante</td>
    <td>Utenti assegnati a un ruolo o un gruppo specifico</td>
    <td><ol>
    <li>Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui assegnare il passaggio nell'elenco <strong>Tipo di partecipante</strong>.</li>
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui assegnare il passaggio.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Gerarchia</td>
    <td>Utenti in una specifica gerarchia organizzativa</td>
    <td><ol>
    <li>Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui assegnare il passaggio nell'elenco <strong>Tipo di gerarchia</strong>.</li>
    <li>Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia. Questi nomi rappresentano gli utenti a cui può essere assegnato il passaggio. Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema: <ol>
    <li>Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</li>
    <li>Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>. Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</li>
    </ol></li>
    <li>Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo il passaggio deve essere assegnato: <ul>
    <li><strong>Assegna a tutti gli utenti recuperati</strong> - Il passaggio viene assegnato a tutti gli utenti nell'intervallo.</li>
    <li><strong>Assegna solo all'ultimo utente recuperato</strong> - Il passaggio viene assegnato solo all'ultimo utente dell'intervallo.</li>
    <li><strong>Escludi utenti con la seguente condizione:</strong> - Il passaggio non viene assegnato ad alcun utente nell'intervallo che soddisfa una specifica condizione. Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Utente del flusso di lavoro</td>
    <td>Utenti nel flusso di lavoro corrente</td>
    <td><ul>
    <li>Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Utente</td>
    <td>Utenti specifici di Microsoft Dynamics 365 for Finance and Operations</td>
    <td><ol>
    <li>Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</li>
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti di Finance and Operations. Selezionare gli utenti a cui assegnare il passaggio, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

3.  Nella scheda **Limite di tempo**, nel campo **Durata** specificare il periodo di tempo entro cui un utente deve eseguire un'azione o inviare una risposta per i documenti che giungono al passaggio di approvazione. Consente di selezionare una delle opzioni indicate di seguito.
    -   **Ore**: immettere il numero di ore entro cui l'utente deve inviare una risposta. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    -   **Giorni**: immettere il numero di giorni entro cui l'utente deve inviare una risposta. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    -   **Settimane**: immettere il numero di settimane entro cui l'utente deve inviare una risposta.
    -   **Mesi**: selezionare il giorno e la settimana entro cui l'utente deve inviare una risposta. È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana del mese.
    -   **Anni**: selezionare il giorno, la settimana e il mese entro cui l'utente deve inviare una risposta. È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana di dicembre.

    Se l'utente non esegue un'azione sul documento nel tempo prestabilito, il documento scadrà. Un documento scaduto viene riassegnato in base alle opzioni selezionate nell'area **Riassegnazione** della pagina.
4.  Se il passaggio di approvazione è stato assegnato a più utenti o a un gruppo di utenti, fare clic sulla scheda **Criteri completamento**, quindi selezionare una delle opzioni seguenti:
    -   **Approvatore singolo**: l'azione applicata al documento viene determinata dalla persona che risponde per prima. Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000. La nota spese è attualmente assegnata a Luisa, Raffaella e Davide. Se Luisa risponde per prima, al documento verrà applicata l'azione eseguita da tale utente. Se Luisa rifiuta il documento, la nota spese rifiutata viene reinviata a Giorgio. Dopo che Luisa avrà approvato il documento, verrà inviato a Elena per l'approvazione. ![Flusso di lavoro con processo di approvazione](./media/workflow_multipleusersinstep.gif)
    -   **Maggioranza degli approvatori**: l'azione applicata al documento viene determinata dalla maggioranza degli approvatori che rispondono. Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000. La nota spese è attualmente assegnata a Luisa, Raffaella e Davide. Se Luisa e Raffaella sono i primi due approvatori a rispondere, al documento verrà applicata l'azione eseguita da tali utenti.
        -   Se Luisa approva il documento e Raffaella lo rifiuta, il documento rifiutato verrà reinviato a Giorgio.
        -   Se Luisa e Raffaella approvano il documento, quest'ultimo verrà inviato a Elena per l'approvazione.
    -   **Percentuale di approvatori**: l'azione applicata al documento viene determinata da una percentuale specifica di approvatori che rispondono. Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000. La nota spese è attualmente assegnata a Luisa, Raffaella e Davide e la percentuale immessa è **50**. Se Luisa e Raffaella sono i primi due approvatori a rispondere, al documento verrà applicata l'azione eseguita da tali utenti, in quanto soddisfano il requisito per il 50% degli approvatori.
        -   Se Luisa approva il documento e Raffaella lo rifiuta, il documento rifiutato verrà reinviato a Giorgio.
        -   Se Luisa e Raffaella approvano il documento, quest'ultimo verrà inviato a Elena per l'approvazione.
    -   **Tutti gli approvatori**: tutti gli approvatori dovranno approvare il documento. In caso contrario il flusso di lavoro non potrà continuare. Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000. La nota spese è attualmente assegnata a Luisa, Raffaella e Davide. Se Luisa e Raffaella approvano il documento e Davide lo rifiuta, il documento rifiutato verrà reinviato a Giorgio. Se Luisa, Raffaella e Davide approvano il documento, quest'ultimo viene inviato a Elena per l'approvazione.

## <a name="specify-when-the-approval-step-is-required"></a>Specificare quando è necessario il passaggio di approvazione
È possibile specificare quando è necessario il passaggio di approvazione. Il passaggio di approvazione può essere necessario sempre o solo se vengono soddisfatte specifiche condizioni.

### <a name="the-approval-step-is-always-required"></a>Passaggio di approvazione sempre necessario

Se il passaggio di approvazione è sempre necessario, effettuare le operazioni seguenti.

1.  Nel riquadro sinistro fare clic su **Condizione**.
2.  Selezionare l'opzione **Esegui sempre questo passaggio**.

### <a name="the-approval-step-is-required-in-specific-conditions"></a>Passaggio di approvazione necessario in presenza di condizioni specifiche

È possibile che il passaggio di approvazione che si sta configurando sia necessario solo se vengono soddisfatte specifiche condizioni. Si supponga ad esempio di dover configurare un passaggio di approvazione per un flusso di lavoro relativo a una richiesta di acquisto e di voler eseguire tale passaggio solo quando l'importo della richiesta di acquisto è maggiore di USD 10.000. Per specificare quando è necessario il passaggio di approvazione, effettuare le operazioni seguenti.

1.  Nel riquadro sinistro fare clic su **Condizione**.
2.  Selezionare l'opzione **Esegui questo passaggio solo quando è soddisfatta la seguente condizione**.
3.  Immettere una condizione.
4.  Immettere altre condizioni, se necessario.
5.  Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:
    1.  Fare clic su **Test**.
    2.  Nella pagina **Test condizione flusso di lavoro**, nell'area **Convalida condizione**, selezionare un record.
    3.  Fare clic su **Test**. Il sistema valuta il record per determinare se soddisfa le condizioni definite.
    4.  Fare clic su **OK** o su **Annulla** per tornare alla pagina **Proprietà**.

## <a name="specify-what-happens-when-the-document-is-overdue"></a>Specificare l'azione da eseguire quando il documento è scaduto
Se un utente non esegue un'azione su un documento nel tempo prestabilito, il documento scadrà. Un documento scaduto può essere riassegnato o assegnato automaticamente a un altro utente per l'approvazione. Per riassegnare il documento scaduto, effettuare le operazioni seguenti.

1.  Nel riquadro sinistro fare clic su **Riassegnazione**.
2.  Selezionare la casella di controllo **Utilizza percorso di riassegnazione** per creare un percorso di riassegnazione. Il documento verrà assegnato automaticamente agli utenti elencati nel percorso. La tabella indicata di seguito rappresenta un esempio di percorso di riassegnazione.
    | Sequenza | Percorso di riassegnazione      |
    |----------|----------------------|
    | 1        | Assegna a: Maria     |
    | 2        | Assegna a: Francesca      |
    | 3        | Azione finale: Rifiuta |

    In questo esempio il documento scaduto viene assegnato a Maria. Se Maria non invia una risposta nel tempo prestabilito, il documento verrà assegnato a Francesca. Se Francesca non invia una risposta nel tempo prestabilito, il documento verrà rifiutato.
3.  Per aggiungere un utente al percorso di riassegnazione, fare clic su **Aggiungi riassegnazione**. Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 4.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opzione</th>
    <th>Utenti a cui viene riassegnato il documento</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Gerarchia</td>
    <td>Utenti in una specifica gerarchia organizzativa</td>
    <td><ol>
    <li>Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui riassegnare il documento nell'elenco <strong>Tipo di gerarchia</strong>.</li>
    <li>Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia. Questi nomi rappresentano gli utenti a cui può essere riassegnato il documento. Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema: <ol>
    <li>Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</li>
    <li>Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>. Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</li>
    </ol></li>
    <li>Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo il documento deve essere riassegnato: <ul>
    <li><strong>Assegna a tutti gli utenti recuperati</strong> - Il documento viene riassegnato a tutti gli utenti nell'intervallo.</li>
    <li><strong>Assegna solo all'ultimo utente recuperato</strong> - Il documento viene riassegnato solo all'ultimo utente dell'intervallo.</li>
    <li><strong>Escludi utenti con la seguente condizione:</strong> - Il documento non viene riassegnato ad alcun utente nell'intervallo che soddisfa una specifica condizione. Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Utente del flusso di lavoro</td>
    <td>Utenti nel flusso di lavoro corrente</td>
    <td><ul>
    <li>Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Utente</td>
    <td>Utenti specifici di Finance and Operations</td>
    <td><ol>
    <li>Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</li>
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti di Finance and Operations. Selezionare gli utenti a cui riassegnare il documento, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  Nella scheda **Limite di tempo**, nel campo **Durata** specificare il periodo di tempo entro cui un utente deve eseguire un'azione o inviare una risposta per i documenti. Consente di selezionare una delle opzioni indicate di seguito.
    -   **Ore**: immettere il numero di ore entro cui l'utente deve inviare una risposta. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    -   **Giorni**: immettere il numero di giorni entro cui l'utente deve inviare una risposta. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    -   **Settimane**: immettere il numero di settimane entro cui l'utente deve inviare una risposta.
    -   **Mesi**: selezionare il giorno e la settimana entro cui l'utente deve inviare una risposta. È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana del mese.
    -   **Anni**: selezionare il giorno, la settimana e il mese entro cui l'utente deve inviare una risposta. È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana di dicembre.

5.  Ripetere i passaggi da 3 a 4 per ogni utente che si desidera aggiungere al percorso di riassegnazione. È possibile modificare l'ordine degli utenti.
6.  Se gli utenti nel percorso di riassegnazione non inviano una risposta nel tempo prestabilito, verrà automaticamente eseguita un'azione sul documento dal sistema. Per specificare l'azione presa dal sistema, selezionare la riga **Azione**, quindi nella scheda **Termina azione** selezionare un'opzione.





