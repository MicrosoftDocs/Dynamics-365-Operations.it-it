---
title: Progettare un questionario
description: In questo argomento viene descritto il processo per creare un questionario. Il primo passaggio consiste nel progettare il questionario. Quando si progetta un questionario, non si scrivono solo le domande e le risposte, ma si crea anche la struttura che consente di registrare e tabulare le risposte.
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e406be47f33f388ad8088524700c4f3e331998c8
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="design-a-questionnaire"></a>Progettare un questionario

[!include[banner](includes/banner.md)]

In questo argomento viene descritto il processo per creare un questionario. Il primo passaggio consiste nel progettare il questionario. Quando si progetta un questionario, non si scrivono solo le domande e le risposte, ma si crea anche la struttura che consente di registrare e tabulare le risposte. 

Un'attenta progettazione del questionario consente di migliorare la qualità dei dati raccolti. Mediante un'attenta progettazione, è possibile aggiornare selezionare le opzioni appropriate al momento opportuno per un questionario. I seguenti passaggi possono risultare utili per pianificare un questionario efficace:

-   Definire chiaramente lo scopo del questionario per garantire che le domande sono a supporto dello scopo.
-   Determinare la singola persona o il gruppo di persone che dovranno completare il questionario.
-   Scrivere le domande che verranno visualizzate nel questionario e includere le opzioni di risposta, se applicabile.
-   Assicurarsi che il questionario scorra logicamente, in modo che gli intervistati siano coinvolti.
-   Disporre le domande e le risposte nell'ordine in cui devono essere presentate agli intervistati.
-   Decidere come devono essere valutati i risultati, se applicabile.
-   Decidere se sono necessarie funzionalità aggiuntive. Ad esempio, indicare se e come i risultati devono essere classificati, se un limite di tempo è necessario o se tutte le domande sono obbligatorie.

La fase di progettazione include quattro categorie di attività da completare in questo ordine:

1.  Impostare prerequisiti, se necessario.
2.  Impostare gruppi di risposte e risposte, se applicabile.
3.  Impostare domande e la relativa associazione ai gruppi di risposte.
4.  Impostare il questionario e collegare le relative domande.

## <a name="prerequisites"></a>Prerequisiti
Alcuni prerequisiti devono essere specificati prima di cerare questionari, risposte e domande. Tuttavia, non tutti i prerequisiti sono necessari per un completo funzionamento.

### <a name="required"></a>Obbligatorio

| Prerequisito        | Descrizione                |
|---------------------|----------------------------|
| Tipi di questionario | Classificare i questionari. |
| Tipi di domanda      | Classificare le domande.      |

### <a name="optional"></a>Facoltativo

| Prerequisito             | Descrizione                                                    |
|--------------------------|----------------------------------------------------------------|
| Parametri Gestione questionari | Modificare i controlli di base e le impostazioni predefinite per i questionari. |

### <a name="questionnaire-types"></a>Tipi di questionario

I tipi di questionario sono obbligatori e devono essere assegnati quando si crea un questionario. I tipi di questionario consentono di gestire e classificare i questionari più facilmente. Utilizzare i tipi di questionario per classificare i questionari e differenziarli tra loro. Ad esempio, se si dispone di più questionari da cui eseguire la selezione, è possibile filtrarli per tipo per rendere più semplice la ricerca di un questionario specifico. Di seguito sono riportati alcuni tipi di questionario:

-   Sviluppo risorse umane
-   Sondaggi clienti
-   Processo di verifica

### <a name="question-types"></a>Tipi di domanda

I tipi di domanda sono obbligatori e devono essere assegnati quando si crea una domanda. 

Utilizzare i tipi di domanda per eseguire la classificazione per il reporting. I tipi di domanda rendono anche più semplice individuare le domande, poiché è possibile utilizzare i tipi come filtri nella pagina **Domande**. Di seguito sono riportati alcuni tipi di domande:

-   Risorse umane
-   Gestione aziendale
-   Valutazione corso

### <a name="questionnaire-parameters"></a>Parametri Gestione questionari

Parametri Gestione questionari sono facoltativi. È possibile non utilizzarli, in base ai requisiti della società. 

I parametri Gestione questionari definiscono l'anonimato, i codici di sequenza numerica e i tipi di riferimento di un questionario. Quando un'organizzazione distribuisce un questionario, potrebbe essere utile l'opzione che consente agli intervistati di rimanere anonimi. 

I codici di sequenza numerica sono utilizzati per organizzare le domande e le risposte. In base ai codici di sequenza numerica, i valori vengono automaticamente assegnati agli articoli. 

È consigliabile definire tutti i parametri prima di iniziare a creare i dati. È possibile modificare le impostazioni dei parametri di gestione questionari in qualsiasi momento.

## <a name="questionnaire-components"></a>Componenti di questionario
Nei questionari sono disponibili tre elementi principali: gruppi di risposte contenenti le risposte alle domande a scelta multipla, le domande e il questionario. È possibile facoltativamente raggruppare le domande di un questionario in gruppi di risultati. I gruppi di risultati consentono di classificare le domande e analizzare ulteriormente il questionario. 

[![Componenti di questionario](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>Gruppi di risposte e risposte

Gli intervistati possono rispondere a una domanda in due modi, in base all'argomento della domanda:

-   Le domande aperte non richiedono risposte in un formato specifico. Gli intervistati possono digitare una risposta sotto forma di testo, un numero, una data o un'ora. Queste domande in genere richiedono l'inserimento nelle risposte di informazioni soggettive da parte degli intervistati, ad esempio un'opinione, una descrizione, una valutazione o una stima.
-   Le domande chiuse richiedono che l'intervistato selezioni una risposta in un elenco di risposte corrette possibili.

Per fornire un elenco di risposte possibili per le domande chiuse, è possibile creare le risposte nella pagina **Gruppi di risposte**. 

I gruppi di risposte e le risposte sono componenti che costituiscono la parte principale delle informazioni da cui vengono create le domande. Dopo aver creato un gruppo di risposte, è possibile associarlo a una domanda nel campo **Gruppo di risposte** nella pagina **Domande**. 

Un gruppo di risposte può essere utilizzato per più domande dello stesso questionario e in più questionari. 

**Nota:** Se si modifica il testo della risposta in gruppi di risposte già stati utilizzati in questionari completati, i dati possono diventare difficili da valutare e i risultati del questionario possono non essere più validi. Se è necessario modificare un gruppo di risposte, considerare la possibilità di creare un nuovo gruppo di risposte anziché modificarne uno esistente. Non è possibile eliminare i gruppi di risposte collegati a una domanda o una risposta o a cui è già stata fornita una risposta.

### <a name="questions"></a>Domande

Un questionario deve contenere domande Le domande possono essere aperte o chiuse.

-   Le risposte alle domande libere non vengono verificate e gli intervistati possono immettere le relative risposte.
-   Le domande chiuse richiedono un elenco di opzioni di risposta predefinite e le domande possono essere strutturate per consentire a un intervistato di selezionare più risposte. Le domande devono essere progettate per ottenere informazioni specifiche da un intervistato e devono essere collegate a un gruppo di risposte che fornisce le opzioni di risposta per ciascuna domanda chiusa. 
     -  **Nota:** Prima di impostare le domande chiuse, è necessario creare i gruppi di risposte e le risposte..

Le domande possono essere disposte in una gerarchia di domande condizionali, in modo che le domande secondarie dipendono dalla risposta selezionata da un intervistato per la domanda precedente. È possibile scrivere prima le domande e disporle in una gerarchia in seguito.

## <a name="setting-up-questionnaires"></a>Impostazione dei questionari
**Nota:** Prima di impostare un questionario, è necessario impostare le domande, le risposte e i prerequisiti. 

Per ciascun questionario è possibile specificare le seguenti informazioni:

-   Il tempo totale o il limite di tempo concesso per rispondere alle domande obbligatorie.
-   Se tutte le domande sono obbligatorie.
-   Se calcolare i punti di un questionario.
-   Come classificare i risultati.
-   Se il questionario sarà disponibile per un set limitato di intervistati.
-   Se un modello di modulo deve essere visualizzato come sfondo di ciascuna pagina del questionario.
-   Se le note aggiuntive sono necessarie per chiarire agli intervistati lo scopo del questionario.
-   Se si desidera visualizzare le domande in un ordine fisso o selezionarle casualmente.
-   Se le domande devono essere sottoposte solo se vengono fornite le risposte specifiche per le risposte precedenti.

### <a name="set-up-a-questionnaire"></a>Impostare un questionario

La pagina principale utilizzata per impostare un questionario la **Questionari**. Per impostare un questionario, completare le seguenti attività in ordine:

1.  Creare un questionario.
2.  Eseguire uno dei passaggi seguenti per collegare le domande al questionario:
    -   Se si utilizzano i gruppi di risultati, è possibile collegare le domande a un questionario utilizzando i gruppi di risultati. Innanzitutto impostare i gruppi di risultati per il questionario, quindi aggiunge le domande ai gruppi di risultati.
    -   Se non si utilizzano i gruppi di risultati, è possibile collegare le domande direttamente al questionario.

3.  Impostare una gerarchia di domande condizionali, se necessario.
4.  Eseguire il test del questionario.

Nella pagina **Questionari** fare clic su **Convalida** per verificare se il questionario è stato creato correttamente. Tuttavia, si consiglia anche di completare il questionario e di eseguirne il test prima della distribuzione.

### <a name="modify-a-questionnaire"></a>Modificare un questionario

Nella pagina **Questionari** è possibile eseguire le attività indicate di seguito:

-   Modificare le informazioni nel questionario, ad esempio i gruppi di risultati e le domande.
-   Eliminare e aggiungere domande.
-   Apportare modifiche nei gruppi di risultati e nel numero progressivo. 

**Attenzione:** Prestare attenzione alla modifica dei questionari che sono già stati completati. Le modifiche possono ridurre l'accuratezza delle statistiche e renderle una base di valutazione inadeguata. Considerare la possibilità di creare una nuova domanda invece di modificarne una a cui si è già risposto.

In un questionario, non è possibile eliminare i seguenti tipi di domande:

-   Domande collegate a un questionario.
-   Domande già risposte e che si trovano quindi nella finestra di dialogo **Risposte**.

### <a name="result-groups"></a>Gruppi di risultati

I gruppi di risultati sono facoltativi quando si allegano delle domande a un questionario. 

Un gruppo di risultati viene utilizzato per calcolare i punti e classificare i risultati di un questionario. Se si utilizzano i gruppi di risultati, è possibile eseguire le attività seguenti:

-   Valutare i risultati del questionario in base alle statistiche punti.
-   Valutare il punteggio di un intervistato per ciascun gruppo di risultati impostato.
-   Per un'analisi più precisa dei risultati, generare statistiche per ciascun gruppo di risultati.
-   Stampare un report contenente i risultati per ciascun gruppo di risultati nonché i punti/testi facoltativi basati sui punti ottenuti in ciascun gruppo di risultati.

**Nota:** Prima di poter impostare i gruppi di risultati, occorre completare le seguenti attività:

-   Impostare domande chiuse. Per una domanda chiusa, il tipo di input nella pagina **Domande** deve essere **Casella di controllo**, **Pulsante alternativo** o **Casella combinata**.
-   Definire i punti per le risposte nei gruppi di risposte che sono assegnati a ciascuna domanda.
-   Impostare un questionario.

Per collegare delle domande a un questionario utilizzando i gruppi di risultati, impostare innanzitutto i gruppi di risultati per il questionario, quindi aggiungere le domande ai gruppi. Se non si utilizzano i gruppi di risultati, è possibile collegare le domande direttamente a un questionario. 

È possibile impostare più gruppi di risultati per valutare i punti ottenuti da un intervistato in ciascuna categoria. Una volta completato il questionario, è possibile visualizzare i punti che sono stati ottenuti per ciascun gruppo di risultati. 

**suggerimento:** Per valutare un questionario utilizzando i punti, ma non le categorie distinte, è possibile aggiungere tutte le domande a un singolo gruppo di risultati. 

Per ciascun gruppo di risultati, è possibile inoltre impostare uno o più messaggi basati su punti che gli intervistati visualizzano dopo il completamento di un questionario. Il testo visualizzato può variare in base al punteggio ottenuto da un intervistato in un gruppo di risultati. Per utilizzare i messaggi basati su punti, è necessario definire intervalli di punti e immettere una descrizione per ciascun intervallo. Quando un intervistato raggiunge un punteggio in un determinato intervallo, il testo relativo a tale intervallo verrà inserito nel report dei risultati. 

Poiché un gruppo di risultati è correlato ai punti associati a set specifici di domande in un questionario, è possibile utilizzare solo un gruppo specifico di risultati per un questionario.

#### <a name="example-pointstexts-for-result-group-3"></a>Esempio: punti/testi per il gruppo di risultati 3

Si utilizza un questionario per un test relativo all'attitudine al comando con 15 domande in tre categorie. Creare tre gruppi di risultati e aggiungere cinque domande a ciascun gruppo di risultati. I punti vengono totalizzati nei tre gruppi. I tre gruppi di risultati sono i seguenti:

-   Capacità creative
-   Capacità di comando
-   Capacità tecniche

Per utilizzare i messaggi basati su punti, è possibile impostare intervalli di testo per ciascun gruppo di risultati. A ciascuna domanda sono assegnati due punti. Di conseguenza, il totale massimo di punti per ogni gruppo di risultati è 10. 

Nella seguente tabella vengono riportati i messaggi in base ai punti definiti per il gruppo di risultati "attitudini al comando".

| Intervallo di punti | Testo                                       |
|----------------|--------------------------------------------|
| Da 1 a 3         | Attitudini al comando di medio livello.     |
| Da 4 a 7         | Buone attitudini al comando.        |
| Da 8 a 10        | Ottime attitudini al comando. |

È possibile impostare intervalli di punti e testi per ciascun gruppo di risultati nel questionario. I testi che corrispondono al punteggio di ogni intervistato sono visualizzati per ciascun gruppo di risultati. 

**Nota:** È possibile modificare gli intervalli e i testi. Tuttavia, se il questionario è stato completato, eventuali modifiche potrebbero determinare delle differenze tra i report dei risultati nuovi e precedenti.

### <a name="conditional-question-hierarchies"></a>Gerarchie di domande condizionali

Le gerarchie di domande condizionali sono facoltative quando si imposta un questionario. 

**Nota:** Prima che sia possibile impostare una gerarchia di domande condizionali, è necessario che le domande a cui sono assegnati i gruppi di risposte siano collegate al questionario. 

Per utilizzare le domande condizionali per creare una gerarchia di domande in un questionario, è possibile fare in modo che la sequenza in cui sono presentate le domande dipenda dalla risposta selezionata da un intervistato per ciascuna domanda. Basando la sequenza delle domande sulle risposte dell'intervistato, è possibile modificare il questionario quando l'intervistato lo completa.

#### <a name="examples"></a>Esempi

Una persona giuridica offre sia gli articoli sia i servizi ai clienti. Come accade in genere in questi casi, alcuni clienti acquistano solo gli articoli, altri solo i servizi e alcuni acquistano entrambi. Pertanto, se la persona giuridica distribuisce un sondaggio relativo alla soddisfazione clienti, può applicare una struttura condizionale al questionario in modo da evitare che i clienti che acquistano solo servizi debbano rispondere alle domande sugli articoli. 

In alternativa, è possibile impostare un questionario in modo che se un intervistato seleziona la risposta A per la domanda 1, la domanda 2 è quella successiva nella sequenza. Tuttavia, se l'intervistato seleziona la risposta B per la domanda 1, la domanda successiva è la numero 5.

<a name="see-also"></a>Vedere anche
--------

[Utilizzo di questionari](questionnaires.md)

[Distribuzione e completamento di questionari](distribute-questionnaires.md)

[Visualizzare e valutare i risultati di un questionario](evaluate-questionnaire-results.md)


