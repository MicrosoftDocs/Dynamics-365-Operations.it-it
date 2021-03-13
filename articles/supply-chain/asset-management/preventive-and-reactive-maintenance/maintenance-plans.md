---
title: Piani di manutenzione
description: In questo argomento vengono descritti i piani di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9ec4929e9ea608318b83a2ae6033c4b25855f4dd
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "5077552"
---
# <a name="maintenance-plans"></a>Piani di manutenzione

[!include [banner](../../includes/banner.md)]

Un piano di manutenzione definisce quando deve essere eseguito un processo di manutenzione preventiva pre-pianificato per un cespite. I piani di manutenzione possono essere associati a cespiti, tipi di cespite, unità funzionali o tipi di unità funzionali, ma innanzitutto si creano i piani di manutenzione da utilizzare nella società.

Un piano di manutenzione può includere molteplici righe di piano di manutenzione. Il tipo di processo di manutenzione e l'intervallo sono specificati nella riga di piano di manutenzione. Sono disponibili due tipi di righe di piano di manutenzione:

- Tempo
- Contatore

Le righe di piano di manutenzione di tipo "Tempo" sono utilizzate per la manutenzione pianificata ricorrente basata su un intervallo di tempo fisso. Le righe di piano di manutenzione di tipo "Contatore" sono utilizzate per la manutenzione pianificata o reattiva basata su registrazioni contatore di cespite. Un piano di manutenzione possono includere varie righe di piano di manutenzione di entrambi i tipi.

>[!NOTE]
>Se nessun valore di contatore è stato registrato per un tipo di contatore in un cespite, le righe di piano di manutenzione vengono omesse.

Innanzitutto, si creano i piani di manutenzione necessari per i processi di manutenzione preventiva e si selezionano i tipi di cespite, i cespiti, i tipi di unità funzionali e le unità funzionali che devono essere associate a ogni piano di manutenzione. Successivamente, se necessario, è anche possibile aggiungere piani di manutenzione a un cespite o un'unità funzionale selezionando **Tutti i cespiti** \> selezionare il cespite \> Scheda dettaglio **Piani di manutenzione cespiti** o **Tutte le unità funzionali** \> selezionare l'unità funzionale \> Scheda dettaglio **Piani di manutenzione**.

Se si aggiunge un piano di manutenzione ai tipi di cespite o ai tipi di unità funzionale, quando si creano nuovi cespiti o unità funzionali con tali tipi di cespite o tipi di unità funzionali, il cespite o l'unità funzionale viene automaticamente aggiunto al piano di manutenzione. La data di inizio della relazione con un piano di manutenzione sarà la data corrente, che può essere necessario rettificare.

## <a name="set-up-maintenance-plans"></a>Imposta i piani di manutenzione

In questa sezione viene descritto come impostare le righe di piano di manutenzione e sono riportati esempi di come possono essere utilizzate.

1. Passare a **Gestione cespiti \> Impostazione \> Manutenzione preventiva \> Piani di manutenzione**.

1. Selezionare **Nuovo** per creare una nuova sequenza.

1. Immettere un ID nel campo **Sequenza manutenzione** e un nome nel campo **Nome**.

1. Nel campo **Data piano**, immettere la data di inizio a partire dalla quale è possibile eseguire la pianificazione per il piano di manutenzione. Da notare che le righe di piano di manutenzione basate su tempo possono avere altre date di piano.

1. Impostare l'interruttore **Attivo** su "Sì" per attivare il piano di manutenzione.

    >[!NOTE]
    >Se si disattiva un piano di manutenzione, non verranno create registrazioni di programmazione nel programma di manutenzione quando si esegue un processo di piano di manutenzione di programmazione.

1. I campi **Giorni di tolleranza prima** e **Giorni di tolleranza dopo** sono relativi alle righe di piano di manutenzione in cui la casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** è selezionata (vedere il passaggio 17). I campi "Tolleranza" vengono utilizzati per estendere l'intervallo in giorni nel quale, se vi sono più piani di manutenzione che si sovrappongono, il processo più completo/più grande viene creato come riga di programma di manutenzione durante la programmazione del piano di manutenzione, mentre i processi che si sovrappongono più frequenti vengono omessi durante la programmazione del piano di manutenzione. Immettere il numero di giorni nel campo **Giorni di tolleranza prima**, ad esempio "2".

1. Se è stato immesso un valore in **Giorni di tolleranza prima**, inserire anche il numero di giorni nel campo **Giorni di tolleranza dopo**, ad esempio "2".

    >[!NOTE]
    >L'esempio descritto in questo passaggio e in quello precedente significa che se varie righe di piano di manutenzione si sovrappongono e la casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** è selezionata per una o più righe, il periodo di omissione delle righe di programma di manutenzione viene esteso fino a un totale di cinque giorni (la data di inizio prevista nella riga di programma di manutenzione *e* due giorni prima *e* due giorni dopo quella data).

1. I campi nel gruppo **Dettagli** nella Scheda dettaglio **Dettagli** visualizzano il numero di righe di piano di manutenzione impostate nel piano di manutenzione e il numero di cespiti e unità funzionali associati al piano di manutenzione.

1. Nella Scheda dettaglio **Righe**, selezionare **Aggiungi riga tempo** o **Aggiungi riga contatore cespiti** per creare una nuova riga di piano di manutenzione.

1. Immettere una descrizione per la riga nel campo **Descrizione ordine di lavoro**. La descrizione viene trasferita agli ordini di lavoro correlati.

1. Selezionare il tipo di processo al quale la riga di piano di manutenzione è associata nel campo **Tipo di processo di manutenzione**.

1. Nei campi **Variante tipi di processo di manutenzione** e **Settore** selezionare la variante e il settore associato al tipo di processo di manutenzione.

1. Nei campi **Termina entro giorni** e **Termina entro ore**, è possibile immettere la data di fine prevista in giorni o ore. La data di fine prevista viene immessa in relazione alla data di inizio prevista, che viene calcolata quando vengono create le righe di programma di manutenzione. Ad esempio, è possibile immettere "7" nel campo **Termina entro giorni** per indicare che il processo associato deve essere completato entro una settimana dalla data di inizio prevista.

1. Nel campo **Tipo di intervallo**, selezionare il tipo di intervallo da utilizzare nella riga di piano di manutenzione, ad esempio "Ripetuto" o "Una volta". Fare riferimento alla tabella [Panoramica dei tipi di intervallo](#interval-types) sotto per una descrizione della relazione tra i tipi dell'intervallo e i tipi di riga.

1. Il campo **Periodo** si riferisce solo ai tipi di riga basati su tempo. Selezionare il tipo di periodo associato alla frequenza del periodo.

1. Nel campo **Frequenza periodo**, immettere il numero di volte che la riga deve essere utilizzata per la pianificazione dei processi di manutenzione preventiva. Esempio: se è stata creata una riga di tipo "Contatore", il contatore in uso designa la quantità di produzione e si inserisce "20000" in questo campo, le nuove righe di sequenza di manutenzione vengono create durante la programmazione di manutenzione preventiva ogni volta che è prevista una produzione di altri 20.000 articoli.

1. La casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** si riferisce a tipi di riga basati su tempo e su contatore. Selezionare la casella di controllo per eliminare le voci di programma di manutenzione create alla stessa data. Ciò è utile se, ad esempio, è stata creata una riga di ispezione di 1 mese, una riga di ispezione di 6 mesi e una riga di ispezione di 1 anno. Per l'ispezione di 1 anno, si desidera eseguire solo tale ispezione e non le altre due, che rientrerebbero anch'esse nell'intervallo di tempo indicato. Per impostare correttamente questo esempio, si imposta la riga di ispezione di 1 anno come prima riga, la riga di 6 mesi come seconda riga e la riga di 1 mese come terza riga e si seleziona la casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** per le righe di 1 mese e di 6 mesi. In tal modo si garantisce che quando si raggiunge il limite di un anno, le ispezioni per un mese e sei mesi vengono omesse e una riga di programma di manutenzione viene creata solo per la riga di ispezione di 1 anno.

    >[!NOTE]
    >L'esempio descritto in questo passaggio mostra che il processo più completo, che contiene il maggior numero di attività e che non viene eseguito spesso, deve essere sempre inserito come prima riga. I processi più frequenti sono quindi immessi come righe distinte nell'ordine di frequenza, posizionando il processo più frequente nella parte inferiore dell'elenco.

1. Il campo **Contatore** si riferisce solo ai tipi di riga basati su contatore. Selezionare il tipo di contatore da utilizzare nella riga. Se un tipo di contatore non è attivo in un cespite associato, la riga di piano di manutenzione viene omessa.

1. Il campo **Intervallo temporale contatore cespiti in giorni** fa riferimento solo ai tipi di riga basati su contatore. Immettere un numero che definisce fino a quanti giorni a ritroso le registrazioni contatore vengono controllate quando si esegue la programmazione del piano di manutenzione. Ovvero fino a quale data passata i dati (registrazioni contatore esistenti) vengono utilizzati come base per il calcolo della tendenza che determina il numero di righe di programma di manutenzione che vengono create.

    >*Esempio:* se le registrazioni contatore sono previste una volta al mese, è possibile immettere "365" in questo campo in quanto la programmazione del piano di manutenzione sarà sempre basata sugli ultimi 12 mesi e quindi creerà righe di programma di manutenzione basate silla tendenza dell'anno precedente. D'altra parte, se si immette il numero "10" in questo campo, si prevedono registrazioni contatore più frequenti, ad esempio, su base giornaliera. Ciò significa che quando si programma il piano di manutenzione, le registrazioni contatore per gli ultimi 10 giorni vengono utilizzate come base per la programmazione delle righe di programma di manutenzione.

1. Il campo **Data piano** si riferisce solo ai tipi di riga basati su tempo. Se la riga di piano di manutenzione ha un'altra data di pianificazione rispetto all'intero piano di manutenzione, selezionare una data nel campo **Data piano** nella riga.

1. Nel campo **Livello servizio**, è possibile selezionare un livello di servizio di ordine di lavoro come ulteriori delimitazione nella riga di piano di manutenzione, da utilizzare come livello di servizio negli ordini di lavoro.

1. Selezionare la casella di controllo **Crea automaticamente** se un ordine di lavoro deve essere creato automaticamente in base alla riga di piano di manutenzione selezionata quando si programmano piani di manutenzione.

1. Se è stata selezionata la casella di controllo **Crea automaticamente**, è possibile selezionare un tipo di ordine di lavoro per l'ordine di lavoro creato automaticamente nel campo **Tipo di ordine di lavoro**. Se è stata selezionata la casella di controllo **Crea automaticamente** e non si seleziona un tipo di ordine di lavoro in questo campo, viene utilizzato il tipo di ordine di lavoro selezionato in **Gestione cespiti \> Imposta \> Parametri di gestione cespiti \> collegamento Ordini di lavoro** \> campo **Tipo di ordine di lavoro preventivo**.

1. Utilizzare i campi **Stagione da** e **Stagione a** per creare una riga di piano di manutenzione basata su tempo ripetuta entro un periodo di 12 mesi. *Esempio:* l'attrezzatura utilizzata per la gestione delle aree verdi richiede un intervento ogni primavera entro un periodo predefinito. Immettere la data di inizio del periodo da ripetere nel campo **Stagione da**.

1. Immettere la data di fine del periodo da ripetere nel campo **Stagione a**.

1. Nel campo **Periodo risultante**, viene visualizzato il periodo corrente da ripetere. Quando il periodo corrente è trascorso e si inizia un nuovo anno, il periodo visualizzato in questo campo verrà aggiornato per riflettere il periodo successivo nella sequenza di ripetizione.

1. Nella Scheda dettaglio **Cespiti**, selezionare i cespiti che devono essere associati al piano di manutenzione.

1. Nella Scheda dettaglio **Tipi di cespite**, selezionare i tipi di cespite che devono essere associati al piano di manutenzione.

1. Nella Scheda dettaglio **Unità funzionali**, selezionare le unità funzionali che devono essere associate al piano di manutenzione. Se necessario, è possibile rendere l'impostazione più specifica selezionando un tipo, un produttore e un modello di cespite associati.

1. Nella Scheda dettaglio **Tipi di unità funzionali**, selezionare i tipi di unità funzionali che devono essere associati al piano di manutenzione.

>[!NOTE]
>Quando gli ordini di lavoro vengono creati manualmente nei cespiti coperti da un garanzia fornitore, viene visualizzata una finestra di dialogo per informare l'utente della garanzia. La creazione dell'ordine di lavoro può quindi essere annullata. La verifica di una relazione di garanzia viene omessa per gli ordini di lavoro creati automaticamente.

<a id="interval-types"></a>

## <a name="interval-types-overview"></a>Panoramica dei tipi di intervallo

| Tipo e descrizione dell'intervallo | Tipo di riga: tempo | Tipo di riga: contatore |
|---|---|---|
| **Tipo di intervallo: ripetuto dalla data del piano** Il conteggio inizia dalla data del piano utilizzata. Quando si programmano piani di manutenzione, le righe del programma di manutenzione vengono create quando si raggiunge l'intervallo. | Viene utilizzata la **Data di piano** nella riga di piano di manutenzione. Se nessuna data di piano viene selezionata nella riga, viene utilizzata la **Data di piano** per il piano di manutenzione. Esempio: se si immette "3" nel campo **Frequenza periodo** e "Anno" è selezionato nel campo **Periodo**, una nuova riga di programma di manutenzione viene creata una volta ogni 3 anni. | Viene utilizzata la **Data di piano** per il piano di manutenzione. Se il contatore è stato sostituito, l'ultima data di sostituzione viene utilizzata come data di piano. |
| **Tipo di intervallo: ripetuto dalla data di inizio** Il conteggio inizia dalla data di inizio nella relazione cespite. La data viene selezionata nella visualizzazione dettagli **Tutti i cespiti** \> Scheda dettaglio **Piani di manutenzione cespiti** \> campo **Data di inizio** o nella visualizzazione dettagli **Tutte le aree funzionali** \> Scheda dettaglio **Piani di manutenzione** \> campo **Data di inizio**. Quando si programmano piani di manutenzione, una riga di programma di manutenzione viene creata quando si raggiunge l'intervallo. | Viene utilizzata la data di inizio della riga di piano di manutenzione nel cespite o nell'unità funzionale. Se tale campo è vuoto, viene utilizzata la **Data di piano** per il piano di manutenzione. | Viene utilizzata la data di inizio della riga di piano di manutenzione nel cespite o nell'unità funzionale. Se tale campo è vuoto, viene utilizzata la **Data di piano** per il piano di manutenzione. |
| **ITipo di intervallo: ripetuto dall'ultimo ordine di lavoro** Il conteggio inizia dalla data e dall'ora di fine effettive dell'ultimo ordine di lavoro completato per il cespite con il tipo di processo di manutenzione specifico/la combinazione di settore/variante di tipi di processo di manutenzione. Quella data e quell'ora sono visualizzate nel campo **Fine effettiva** nella visualizzazione dettagli **Tutti gli ordini di lavoro**. | Viene utilizzata la data e l'ora di fine effettive dell'ordine di lavoro completato per il cespite con la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione specifica. Se non viene trovato un ordine di lavoro completato, viene invece utilizzata una delle date usate nel tipo di intervallo "Ripetuto da data di inizio" descritto sopra. | Viene utilizzata la data e l'ora di fine effettive dell'ordine di lavoro completato per il cespite *e* la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione . Se la data e l'ora di fine non sono state specificate nell'ordine di lavoro, viene invece utilizzata una delle date usate nel tipo di intervallo "Ripetuto da data di inizio" descritto sopra. |
| **Tipo di intervallo: una volta dalla data di piano** Vedere la descrizione del tipo di intervallo "Ripetuto dalla data di piano" visto sopra. La sola differenza è che questo tipo di intervallo deve essere utilizzato una sola volta. | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di piano" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico. | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di piano" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico. **Nota: 1** Il tipo di intervallo è pertinente solo se il contatore viene sostituito ogni volta che si esegue un processo di manutenzione o di assistenza. Se, per un qualsiasi motivo, un contatore è stato sostituito prima della fine dell'intervallo pianificato, un nuovo periodo viene calcolato per il processo dal momento della sostituzione del contatore. **Nota 2:** se il contatore viene sostituito durante il completamento del processo di manutenzione o di assistenza, questo tipo di intervallo funziona come tipo di intervallo "Ripetuto dalla data di piano" visto sopra. |
| **Tipo di intervallo: una volta dalla data di inizio** Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di inizio" visto precedentemente. La sola differenza è che questo tipo di intervallo deve essere utilizzato una sola volta. | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di inizio" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico. | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di inizio" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico. La **Nota 1** è valida anche per questo tipo di intervallo. **Nota 3:** se il contatore viene sostituito durante il completamento del processo di manutenzione o di assistenza, questo tipo di intervallo funziona come tipo di intervallo "Ripetuto dalla data di inizio" visto sopra. |
| **Tipo di intervallo: quando superiore** Questo tipo di intervallo si riferisce solo ai contatori e viene utilizzato per indicare un limite superiore impostato nella riga di piano di manutenzione. Le voci del programma di manutenzione avranno la data e l'ora di inizio previste della registrazione contatore, ovvero tali voci verranno create con una data di inizio prevista uguale o antecedente alla data di sistema. | Non applicabile | L'intervallo contatore indica un limite superiore. Se tale limite viene superato quando si crea una registrazione contatore, viene creata una riga di programma di manutenzione quando si programma la manutenzione preventiva. |
| **Tipo di intervallo: quando inferiore** Questo tipo di intervallo si riferisce solo ai contatori e viene utilizzato per indicare un limite inferiore impostato nella riga di piano di manutenzione. Le voci del programma di manutenzione avranno la data e l'ora di inizio previste della registrazione contatore, ovvero tali voci verranno create con una data di inizio prevista uguale o antecedente alla data di sistema. | Non applicabile | L'intervallo contatore indica un limite inferiore. Se tale limite viene superato quando si crea una registrazione contatore, viene creata una riga di programma di manutenzione quando si programma la manutenzione preventiva. |
| **Tipo di intervallo: Collegato alla data di inizio** Questo tipo di intervallo crea una riga del programma di manutenzione una sola volta. Un piano di manutenzione può contenere più righe del piano di manutenzione utilizzando questo tipo di intervallo e tali righe sono collegate. In genere, si crea un piano di manutenzione che contiene righe soltanto di questo tipo di intervallo. Le righe di programma di manutenzione vengono create identificando la riga di piano di manutenzione che ha la prima data e ora di inizio previste. | Vedere la descrizione di "Una volta dalla data di inizio" esposta precedentemente. Esempio: si creano due righe in un piano di manutenzione per un processo di assistenza per un auto: una riga basata su tempo con un periodo di un anno e una basata su contatore con un limite di 25.000 km. Una riga di programma di manutenzione viene creata per il limite che viene raggiunto per primo. Per questo tipo di riga si crea la riga con il periodo di un anno. | Vedere la descrizione di "Una volta dalla data di inizio" esposta precedentemente. Esempio: si creano due righe in un piano di manutenzione per un processo di assistenza per un auto: una riga basata su tempo con un periodo di un anno e una basata su contatore con un limite di 25.000 km. Una riga di programma di manutenzione viene creata per il limite che viene raggiunto per primo. Per questo tipo di riga si crea la riga con il limite di 25.000 km. Esempio che crea due righe contatore: è anche possibile impostare un piano di manutenzione con due righe basate su contatore collegate in cui la prima riga ha un limite di 10.000 articoli prodotti e la seconda riga è relativa alla macchina o al centro di lavoro che richiede un intervento dopo 3.000 ore. |
| **Tipo di intervallo: Collegato dall'ultimo ordine di lavoro** Questo tipo di intervallo crea nuove righe del programma di manutenzione dopo ogni ordine di lavoro completato. Un piano di manutenzione può contenere più righe utilizzando questo tipo di intervallo e tali righe sono collegate. In genere, si crea un piano di manutenzione che contiene righe del piano di manutenzione soltanto di questo tipo di intervallo. Le righe di programma di manutenzione vengono create identificando la riga di piano di manutenzione che ha la prima data e ora di inizio previste. | In pratica questo tipo di intervallo funziona come "Collegato dalla data di inizio" descritto sopra. La sola differenza è la data su cui il tipo di intervallo è basato. La data utilizzata è la data e l'ora effettive nell'ultimo ordine di lavoro completato nel cespite *e* la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione. | In pratica questo tipo di intervallo funziona come "Collegato dalla data di inizio" descritto sopra. La sola differenza è la data su cui il tipo di intervallo è basato. La data utilizzata è la data e l'ora effettive nell'ultimo ordine di lavoro completato nel cespite *e* la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione. |
| **Tipo di intervallo: ripetuto sul valore aggregato (solo contatore)** Quando viene eseguito il piano di manutenzione, verrà creata una riga di manutenzione programmata ogni volta che il valore accumulato per un contatore di cespiti raggiunge la frequenza del periodo o un multiplo pari della frequenza del periodo. La frequenza del periodo viene definita nella riga di piano di manutenzione.<p>Per ulteriori informazioni su come abilitare e utilizzare questa funzionalità, vedere la sezione [Miglioramenti alla manutenzione basata su contatore](#counter-based-maintenance) più avanti in questo argomento. | Non applicabile | **Esempio:** un contatore delle ore è configurato per il cespite AK-101. Viene inoltre configurata una riga del piano di cespiti per il cespite. Il tipo di intervallo di questa riga è *Ripetuto sul valore aggregato (solo contatore)* e la frequenza del periodo è *1000*. Quando viene eseguito il piano di manutenzione, verrà generata una riga di manutenzione pianificata quando il valore aggregato per il contatore supera 1.000 ore. Quindi, quando il valore aggregato per il contatore supera le 2.000 ore, verrà generata un'altra riga di manutenzione pianificata e così via per ogni 1.000 ore aggiuntive. |
| **Tipo di intervallo: una volta sul valore aggregato (solo contatore)** Quando viene eseguito il piano di manutenzione, verrà creata una riga di manutenzione pianificata quando il valore accumulato per un contatore di cespiti raggiunge la frequenza del periodo definita sulla riga del piano di manutenzione.<p>Per ulteriori informazioni su come abilitare e utilizzare questa funzionalità, vedere la sezione [Miglioramenti alla manutenzione basata su contatore](#counter-based-maintenance). | Non applicabile | **Esempio:** un contatore delle ore è configurato per il cespite AK-101. Viene inoltre configurata una riga del piano di cespiti per il cespite. Il tipo di intervallo di questa riga è *Una volta sul valore aggregato (solo contatore)* e la frequenza del periodo è *1000*. Quando viene eseguito il piano di manutenzione, verrà generata una riga di manutenzione pianificata quando il valore aggregato per il contatore supera 1.000 ore. |

>[!NOTE]
>Quando le righe di programma di manutenzione vengono create per le righe di piano di manutenzione basate su tempo, l'ora prevista è sempre all'inizio del giorno. Per le righe di piano di manutenzione basate su contatore, l'ora prevista può essere in qualsiasi momento del giorno.

Di seguito sono riportati alcuni esempi dell'impostazione delle righe di piano di manutenzione basate su tempo e contatore:

**Esempio 1 - Riga di piano di manutenzione basata su tempo:** Un'attività di lubrificazione può essere impostata in un intervallo fisso e si verifica una volta alla settimana. A questo scopo, selezionare "Ripetuto dalla data di piano" nel campo **Tipo di intervallo**. Vedere l'esempio illustrato nella figura seguente.

![Un processo di servizio configurato in un intervallo fisso, che si verifica una volta alla settimana](media/02-preventive-maintenance.png "Un processo di servizio configurato in un intervallo fisso, che si verifica una volta alla settimana")

**Esempio 2 - Riga di piano di manutenzione basata su tempo:** Un'attività di ispezione può essere impostata per essere eseguita approssimativamente una volta alla settimana. A questo scopo, selezionare "Ripetuto dall'ultimo ordine di lavoro" nel campo **Tipo di intervallo**. Vedere l'esempio illustrato nella figura seguente.

![Un processo di ispezione da eseguire approssimativamente una volta alla settimana](media/03-preventive-maintenance.png "Un processo di ispezione da eseguire approssimativamente una volta alla settimana")

**Esempio 3 - Riga di piano di manutenzione basata su contatore:** La seguente illustrazione grafica mostra un contatore a ore per il quale una nuova riga di programma di manutenzione viene creata ogni volta che vengono superate le 250 ore. Il tipo di intervallo per questa riga basata su contatore è "Ripetuto dalla data di inizio". La data di inizio è la data di inizio dei cespiti associati nella visualizzazione dettagli **Tutti i cespiti** \> Scheda dettaglio **Piani di manutenzione cespiti** \> campo **Data di inizio** o nella visualizzazione dettagli **Unità funzionali** \> Scheda dettaglio **Piani di manutenzione** \> campo **Data di inizio**. Questo è un esempio di piano di manutenzione *preventiva* poiché la riga di programma di manutenzione viene creata automaticamente ogni volta che viene raggiunta la soglia (+ 250).

![Un contaore che crea periodicamente righe di programma di manutenzione](media/04-preventive-maintenance.png "Un contaore che crea periodicamente righe di programma di manutenzione")

**Esempio 4 - Riga di piano di manutenzione basata su contatore:** La seguente illustrazione grafica mostra una diminuzione del valore di contatore, che misura l'usura delle pastiglie dei freni. Una riga di programma di manutenzione viene creata quando una registrazione contatore inferiore a 20 mm viene creata per la pastiglia dei freni. Il tipo di intervallo per questa riga basata su contatore è "Quando inferiore" o "Una volta dall'ultima data di inizio". Questo è un esempio di piano di manutenzione *reattivo* poiché la riga di programma di manutenzione non viene creata fino a che non viene registrata una misura inferiore a 20 mm.

![Una diminuzione del valore del contatore, che misura l'usura delle pastiglie dei freni](media/05-preventive-maintenance.png "Una diminuzione del valore del contatore, che misura l'usura delle pastiglie dei freni")

**Esempio 5 - Riga di piano di manutenzione basata su contatore:** La seguente illustrazione grafica mostra un contatore con una soglia di -18 °C. Una riga di programma di manutenzione viene creata quando viene effettuata una registrazione contatore superiore a -18 °C. Il tipo di intervallo per questa riga basata su contatore è "Quando superiore". Questo è un esempio di piano di manutenzione *reattivo* poiché la riga di programma di manutenzione non viene creata fino a che non viene registrata una misura superiore a -18 °C.

![Un contatore con una soglia di -18 ° Celsius](media/06-preventive-maintenance.png "Un contatore con una soglia di -18 ° Celsius")

- Quando si crea un nuovo cespite e questo utilizza un tipo di cespite relativo a un piano di manutenzione, il piano di manutenzione viene automaticamente immesso in **Tutti gli oggetti \> Scheda dettaglio Piani di manutenzione cespiti**. Inoltre, in **Valori predefiniti tipo di cespite**, nella Scheda dettaglio **Piano di manutenzione**, verranno automaticamente inseriti i piani di manutenzione correlati.
- Se si aggiungono o rimuovono tipi di cespite o tipi di unità funzionale in **Piani di manutenzione**, tale modifica viene riflessa solo nei nuovi cespiti creati dopo la modifica.
- Se si aggiungono o rimuovono cespiti o unità funzionali in **Piani di manutenzione**, tale modifica verrà automaticamente aggiornata in **Tutti i cespiti \> Scheda dettaglio Piani di manutenzione cespiti** o in **Tutte le unità funzionali \> Scheda dettaglio Piani di manutenzione**.

Nella figura seguente è illustrato un esempio di un piano di manutenzione di "assistenza camion" nella pagina **Piani di gestione**.

![Un esempio di un piano di manutenzione del servizio di camion](media/07-preventive-maintenance.png "Un esempio di un piano di manutenzione del servizio di camion")

## <a name="add-a-maintenance-plan-to-an-asset"></a>Aggiungere un piano di manutenzione a un cespite

1. Passare a **Gestione cespiti \> Comune \> Cespiti \> Tutti i cespiti** o **Cespiti attivi**.

1. Selezionare il cespite per il quale si desidera impostare un piano di manutenzione e selezionare **Modifica**.

1. Nella Scheda dettaglio **Piani di manutenzione cespiti**, selezionare **Aggiungi riga** per aggiungere un piano di manutenzione al cespite.

1. Nel campo **Piano di manutenzione**, selezionare il piano di manutenzione pertinente.

1. Nel campo **Data di inizio**, selezionare la data a partire dalla quale è possibile eseguire la pianificazione dei processi di manutenzione preventiva. 

1. Selezionare **Salva**. Il campo **Attivo** viene aggiornato automaticamente.

Nella figura seguente è illustrato un esempio di un piano di manutenzione configurato per un cespite nella pagina **Tutti i cespiti**.

![Un esempio di piani di manutenzione configurati su un cespite](media/08-preventive-maintenance.png "Un esempio di piani di manutenzione configurati su un cespite")

<a id="counter-based-maintenance"></a>

## <a name="counter-based-maintenance-enhancements"></a>Miglioramenti alla manutenzione basati su contatore

> [!IMPORTANT]
> La funzionalità descritta in questa sezione è disponibile nell'ambito di una versione di anteprima. Il contenuto e la funzionalità sono soggetti a modifiche. Per ulteriori informazioni sui rilasci di anteprima, vedi [Domande frequenti aggiornamenti del servizio One version](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

La funzionalità *Miglioramenti alla manutenzione basata su contatore* introduce le seguenti funzionalità:

- L'opzione per inserire automaticamente un contatore che ha un valore pari a *0* (zero) quando viene creato un cespite. Questa opzione può essere utile quando si utilizza la manutenzione predittiva basata sui contatori. Quando la funzionalità *Miglioramenti alla manutenzione basata su contatore* non viene utilizzata, i contatori che hanno un valore pari a *0* (zero) devono essere inseriti manualmente.
- La possibilità di configurare un contatore in modo che venga reimpostato automaticamente al completamento di un ordine di lavoro. Questa funzionalità è utile quando si desidera pianificare la manutenzione in base al valore aggregato dal completamento dell'ultimo ordine di lavoro.
- Un nuovo tipo di intervallo del piano di manutenzione denominato *Ripetuto sul valore aggregato (solo contatore)*. Questo tipo attiva la manutenzione ogni volta che un contatore aggregato raggiunge un multiplo di un valore specifico. Ad esempio, la manutenzione può essere attivata ogni 10.000 ore. Per ulteriori informazioni, vedere la sezione [Panoramica dei tipi di intervallo](#interval-types) prima in questo argomento.
- Un altro tipo di intervallo del piano di manutenzione denominato *Una votla sul valore aggregato (solo contatore)*. Questo tipo attiva la manutenzione quando un contatore aggregato raggiunge un valore specifico, ad esempio 8.000 ore. Per ulteriori informazioni, vedere la sezione [Panoramica dei tipi di intervallo](#interval-types).

### <a name="turn-on-the-counter-based-maintenance-enhancements-feature"></a>Attivare la funzionalità di miglioramento della manutenzione basata su contatore

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione cespiti*
- **Nome funzionalità:** *(anteprima) Migliroamenti della manutenzione basata su contatore*

### <a name="create-and-initialize-counters-when-an-asset-is-created"></a>Creare e inizializzare i contatori quando viene creato un cespite

Ogni volta che si crea un cespite, i contatori dei cespiti correlati vengono inizializzati con un valore di *0* (zero) possono essere creati automaticamente, a condizione che tu abbia configurato il tuo sistema e crei il cespite correttamente.

1. Vai a **Gestione cespiti \> Imposta \> Tipi di cespiti**.
1. Assicurati di disporre di un tipo di cespite applicabile al nuovo cespite pianificato. Crea un tipo di cespite come richiesto. Assicurati che tutti i relativi contatori siano selezionati nella Scheda dettaglio **Contatori**.
1. Vai a **Gestione cespiti \> Imposta \> Tipi di cespiti \> Contatori**.
1. Per ogni contatore pertinente, assicurati che il campo **Aggregato totale** sia impostato su *Somma*.
1. Nella pagina **Tutti i cespiti**, crea il cespite.
1. Imposta il campo **Tipo di cespite** sul tipo di cespite che hai identificato o creato nel passaggio 2.
1. Completa la configurazione del nuovo cespite come richiesto.
1. Vai a **Gestione cespiti \> Informazioni \> Cespiti \> Contatori**. Dovresti essere in grado di trovare i contatori inizializzati configurati per il tuo nuovo cespite.

> [!NOTE]
> Quando vengono creati i contatori cespiti inizializzati, si presume che il cespite non sia mai stato utilizzato prima di essere aggiunto al sistema. Quando il programma di manutenzione viene eseguito per la prima volta, il calcolo utilizza la data e il valore del contatore *0* (zero) come base per il calcolo della manutenzione futura. Se il cespite non era nuovo quando è stato aggiunto al sistema, è possibile regolare manualmente il valore del contatore in modo che corrisponda al valore effettivo del contatore. Per modificare un valore del contatore, apri il relativo cespute nella pagina **Tutti i cespiti**, quindi, nel riquadro azioni, nella scheda **Cespite**, nel gruppo **Preventivo**, seleziona **Contatori**. Nella pagina **Contatori cespiti** per il cepsite selezionato, regola il valore nella colonna **Valore** per il record del contatore iniziale come richiesto.

### <a name="automatically-reset-a-counter-value"></a>Reimpostare automaticamente un valore del contatore

È possibile configurare il sistema per reimpostare automaticamente un contatore ogni volta che un ordine di lavoro rilevante raggiunge un valore di stato selezionato.

1. Passare a **Gestione cespiti \> Impostazione \> Manutenzione preventiva \> Piani di manutenzione**.
1. Nel riquadro dell'elenco selezionare un piano di manutenzione. Il ripristino del contatore si applicherà a tutti i cespiti che utilizzano questo piano.
1. Nella sezione **Righe**, trova una riga del contatore dei cespiti per cui desideri reimpostare un contatore e seleziona la casella di controllo **Reimposta contatore** per quella riga. Le righe del contatore dei cespiti includono un valore nella colonna **Contatore**. Il contatore specificato in quella colonna è il contatore che verrà reimpostato per il relativo cespite.)
1. Vai a **Gestione cespiti \> Imposta \> Ordini di lavoro \> Stati del ciclo di vita**.
1. Nel riquadro elenco selezionare lo stato del ciclo di vita dell'ordine di lavoro in cui reimpostare il contatore pertinente.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Reimposta contatore** su *Sì*.
