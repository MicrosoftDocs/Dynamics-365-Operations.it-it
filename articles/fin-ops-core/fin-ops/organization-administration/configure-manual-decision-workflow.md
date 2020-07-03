---
title: Configurare le decisioni manuali in un flusso di lavoro
description: In questo argomento viene descritto come configurare le proprietà per una decisione manuale.
author: sericks007
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130cb50369c13bc3478340023c94f169ee5250cf
ms.sourcegitcommit: a5009c8958037afbaa1dd4f1469255b187ced93a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "3455035"
---
# <a name="configure-manual-decisions-in-a-workflow"></a>Configurare le decisioni manuali in un flusso di lavoro

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come configurare le proprietà per una decisione manuale.

Per configurare una decisione manuale, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sulla decisione e scegliere **Proprietà** per aprire la pagina **Proprietà**. Per configurare le proprietà della decisione manuale, attenersi alle procedure indicate di seguito.

## <a name="name-the-decision"></a>Assegnare un nome alla decisione

Per immettere un nome per la decisione manuale, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Nome** immettere un nome univoco per la decisione manuale.

## <a name="enter-a-subject-line-and-instructions"></a>Immettere una riga di argomento e le istruzioni

La riga di argomento e le istruzioni sono necessarie agli utenti assegnati alla decisione manuale. Se ad esempio si configura una decisione per richieste di acquisto, l'utente assegnato alla decisione visualizzerà la riga di argomento e le istruzioni nella pagina **Richieste di acquisto**. La riga di argomento si trova nella barra dei messaggi della pagina. L'utente può fare clic sull'icona nella barra per visualizzare le istruzioni. Per immettere una riga di argomento e le istruzioni, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nella scheda **Istruzioni**, nel campo **Argomento elemento di lavoro** immettere la riga di argomento.
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

## <a name="specify-the-possible-outcomes-of-a-decision"></a>Specificare i possibili risultati di una decisione

Se un documento viene assegnato a un decisore, a quest'ultimo viene in genere rivolta una domanda. La risposta tipica a questa domanda è **Sì** o **No** oppure **Vero** o **Falso**. Per specificare i possibili risultati della decisione manuale, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nella scheda **Risultati**, nel campo **Risultato 1** immettere il nome del risultato o l'opzione.
3. Per aggiungere traduzioni del risultato, effettuare le operazioni seguenti:

    1. Fare clic su **Traduzioni**.
    2. Nella pagina visualizzata fare clic su **Aggiungi**.
    3. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4. Nel campo **Testo tradotto** immettere il testo.
    5. Fare clic su **Chiudi**.

4. Nel campo **Risultato 2** immettere il nome del risultato oppure l'opzione.
5. Per aggiungere traduzioni del risultato, effettuare le operazioni seguenti:

    1. Fare clic su **Traduzioni**.
    2. Nella pagina visualizzata fare clic su **Aggiungi**.
    3. Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4. Nel campo **Testo tradotto** immettere il testo.
    5. Fare clic su **Chiudi**.

## <a name="specify-when-notifications-are-sent"></a>Specificare quando verranno inviate le notifiche

È possibile inviare notifiche agli utenti quando è stata presa, delegata o riassegnata una decisione. Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro fare clic su **Notifiche**.
2. Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:

    - **\[Prima scelta\]** – L'utente assegnato ha selezionato **\[Prima scelta\]**.
    - **\[Seconda scelta\]** – L'utente assegnato ha selezionato **\[Seconda scelta\]**.
    - **Delega**: se l'utente assegnato ha delegato la decisione a un altro utente.
    - **Riassegna**: se l'utente assegnato non ha preso la decisione nel tempo prestabilito.

3. Scegliere la riga per un evento selezionato nel passaggio 2.
4. Nella scheda **Testo notifiche** immettere il testo della notifica nella casella di testo.
5. Per personalizzare la notifica, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione della notifica. Per inserire un segnaposto, effettuare le operazioni seguenti:

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
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il gruppo a cui inviare notifiche.</li>
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

## <a name="assign-a-decision"></a>Assegnare una decisione

Per specificare gli utenti a cui assegnare una decisione manuale, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Assegnazione**.
2. Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 3.

    <table>
    <thead>
    <tr>
    <th>Opzione</th>
    <th>Utenti a cui viene assegnata la decisione</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Partecipante</td>
    <td>Utenti assegnati a un ruolo o un gruppo specifico</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui assegnare la decisione nell'elenco <strong>Tipo di partecipante</strong>.</li>
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui assegnare la decisione.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Gerarchia</td>
    <td>Utenti in una specifica gerarchia organizzativa</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui assegnare la decisione nell'elenco <strong>Tipo di gerarchia</strong>.</li>
    <li>Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia. Questi nomi rappresentano gli utenti a cui può essere assegnata la decisione. Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema: <ol>
    <li>Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</li>
    <li>Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>. Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</li>
    </ol>
    </li>
    <li>Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo la decisione deve essere assegnata: <ul>
    <li><strong>Assegna a tutti gli utenti recuperati</strong> - La decisione viene assegnata a tutti gli utenti nell'intervallo.</li>
    <li><strong>Assegna solo all'ultimo utente recuperato</strong> - La decisione viene assegnata solo all'ultimo utente dell'intervallo.</li>
    <li><strong>Escludi utenti con la seguente condizione:</strong> - La decisione non viene assegnata ad alcun utente nell'intervallo che soddisfa una specifica condizione. Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</li>
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
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti. Selezionare gli utenti a cui assegnare la decisione, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. Nella scheda **Limite di tempo**, nel campo **Durata** specificare il tempo a disposizione di un utente per prendere la decisione. Consente di selezionare una delle opzioni indicate di seguito.

    - **Ore**: immettere il numero di ore a disposizione dell'utente per prendere la decisione. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Giorni**: immettere il numero di giorni a disposizione dell'utente per prendere la decisione. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Settimane**: immettere il numero di settimane a disposizione dell'utente per prendere la decisione.
    - **Mesi**: selezionare il giorno e la settimana entro i quali l'utente deve prendere la decisione. È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana del mese.
    - **Anni**: selezionare il giorno, la settimana e il mese entro i quali l'utente deve prendere la decisione. È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana di dicembre.

    Se l'utente non prende la decisione nel tempo prestabilito, la decisione scadrà. Una decisione scaduta viene riassegnata in base alle opzioni selezionate nell'area **Riassegnazione** della pagina.

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>Specificare l'azione da eseguire se una decisione è scaduta

Se l'utente non prende la decisione nel tempo prestabilito, la decisione scadrà. Una decisione scaduta può essere riassegnata o assegnata automaticamente a un altro utente. Per riassegnare la decisione scaduta, effettuare le operazioni seguenti:

1. Nel riquadro sinistro fare clic su **Riassegnazione**.
2. Selezionare la casella di controllo **Utilizza percorso di riassegnazione** per creare un percorso di riassegnazione. La decisione viene assegnata automaticamente agli utenti elencati nel percorso. La tabella indicata di seguito rappresenta un esempio di percorso di riassegnazione.

    | Sequenza | Percorso riassegnazione            |
    |----------|----------------------------|
    | 1        | Assegna a: Maria           |
    | 2        | Assegna a: Francesca            |
    | 3        | Azione finale: \[Prima scelta\] |

    In questo esempio la decisione scaduta viene assegnata a Maria. Se Maria non prende la decisione nel tempo prestabilito, la decisione verrà assegnata a Francesca. Se Francesca non prende la decisione nel tempo prestabilito, verrà selezionato  **\[Prima scelta\]** come decisione.

3. Per aggiungere un utente al percorso di riassegnazione, fare clic su **Aggiungi riassegnazione**. Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 4.

    <table>
    <thead>
    <tr>
    <th>Opzione</th>
    <th>Utenti a cui viene riassegnata la decisione</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Gerarchia</td>
    <td>Utenti in una specifica gerarchia organizzativa</td>
    <td>
    <ol>
    <li>Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui riassegnare la decisione nell'elenco <strong>Tipo di gerarchia</strong>.</li>
    <li>Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia. Questi nomi rappresentano gli utenti a cui può essere riassegnata la decisione. Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema: <ol>
    <li>Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</li>
    <li>Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>. Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</li>
    </ol>
    </li>
    <li>Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo la decisione deve essere riassegnata: <ul>
    <li><strong>Assegna a tutti gli utenti recuperati</strong> - La decisione viene riassegnata a tutti gli utenti nell'intervallo.</li>
    <li><strong>Assegna solo all'ultimo utente recuperato</strong> - La decisione viene riassegnata solo all'ultimo utente dell'intervallo.</li>
    <li><strong>Escludi utenti con la seguente condizione:</strong> - La decisione non viene riassegnata ad alcun utente nell'intervallo che soddisfa una specifica condizione. Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</li>
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
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti. Selezionare gli utenti a cui riassegnare la decisione, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Nella scheda **Limite di tempo**, nel campo **Durata** specificare il tempo a disposizione di un utente per prendere la decisione. Consente di selezionare una delle opzioni indicate di seguito.

    - **Ore**: immettere il numero di ore a disposizione dell'utente per prendere la decisione. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Giorni**: immettere il numero di giorni a disposizione dell'utente per prendere la decisione. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Settimane**: immettere il numero di settimane a disposizione dell'utente per prendere la decisione.
    - **Mesi**: selezionare il giorno e la settimana entro i quali l'utente deve prendere la decisione. È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana del mese.
    - **Anni**: selezionare il giorno, la settimana e il mese entro i quali l'utente deve prendere la decisione. È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana di dicembre.

5. Ripetere i passaggi da 3 a 4 per ogni utente che si desidera aggiungere al percorso di riassegnazione. È possibile modificare l'ordine degli utenti.
6. Se gli utenti nel percorso di riassegnazione non prendono la decisione nel tempo prestabilito, la decisione verrà presa dal sistema. Per specificare l'opzione selezionata dal sistema, selezionare la riga **Azione**, quindi nella scheda **Termina azione** selezionare un'opzione.

## <a name="set-a-time-limit"></a>Impostare un limite di tempo

Per prendere la decisione in un periodo di tempo specifico, effettuare le operazioni seguenti:

> [!NOTE]
> Le opzioni selezionate in questi passaggi prevalgono su quelle selezionate nelle aree **Assegnazione** e **Riassegnazione** della pagina.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.
2. Selezionare la casella di controllo **Imposta un limite di tempo per l'elemento del flusso di lavoro**.
3. Nel campo **Durata** specificare il momento in cui prendere la decisione. Consente di selezionare una delle opzioni indicate di seguito.

    - **Ore**: immettere il numero di ore. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Giorni**: immettere il numero di giorni. Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.
    - **Settimane**: immettere il numero di settimane.
    - **Mesi**: selezionare il giorno e la settimana entro i quali prendere la decisione. È ad esempio possibile scegliere di far prendere la decisione entro il venerdì della terza settimana del mese.
    - **Anni**: selezionare il giorno, la settimana e il mese entro i quali prendere la decisione. È ad esempio possibile scegliere di far prendere la decisione entro il venerdì della terza settimana di dicembre.

4. Se viene superato il limite di tempo, la decisione verrà presa dal sistema. Nell'elenco **Azione** selezionare l'opzione che dovrà essere selezionata dal sistema.
