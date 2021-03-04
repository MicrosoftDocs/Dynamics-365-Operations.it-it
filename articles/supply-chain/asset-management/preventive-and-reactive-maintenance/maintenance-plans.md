---
title: Piani di manutenzione
description: In questo argomento vengono descritti i piani di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 28c00b5a2485ffcc01a316d2a39e7259fb563d1d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431183"
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

Innanzitutto, si creano i piani di manutenzione necessari per i processi di manutenzione preventiva e si selezionano i tipi di cespite, i cespiti, i tipi di unità funzionali e le unità funzionali che devono essere associate a ogni piano di manutenzione. Successivamente, se necessario, è anche possibile aggiungere piani di manutenzione a un cespite o un'unità funzionale selezionando **Tutti i cespiti** > selezionare il cespite > Scheda dettaglio **Piani di manutenzione cespiti** o **Tutte le unità funzionali** > selezionare l'unità funzionale > Scheda dettaglio **Piani di manutenzione**.

Se si aggiunge un piano di manutenzione ai tipi di cespite o ai tipi di unità funzionale, quando si creano nuovi cespiti o unità funzionali con tali tipi di cespite o tipi di unità funzionali, il cespite o l'unità funzionale viene automaticamente aggiunto al piano di manutenzione. La data di inizio della relazione con un piano di manutenzione sarà la data corrente, che può essere necessario rettificare.

## <a name="set-up-maintenance-plans"></a>Imposta i piani di manutenzione

In questa sezione viene descritto come impostare le righe di piano di manutenzione e sono riportati esempi di come possono essere utilizzate.

1. Fare clic su **Gestione cespiti** > **Impostazione** > **Manutenzione preventiva** > **Piani di manutenzione**.

2. Fare clic su **Nuovo** per creare una nuova sequenza.

3. Immettere un ID nel campo **Sequenza manutenzione** e un nome nel campo **Nome**.

4. Nel campo **Data piano**, immettere la data di inizio a partire dalla quale è possibile eseguire la pianificazione per il piano di manutenzione. Da notare che le righe di piano di manutenzione basate su tempo possono avere altre date di piano.

5. Impostare l'interruttore **Attivo** su "Sì" per attivare il piano di manutenzione.

>[!NOTE]
>Se si disattiva un piano di manutenzione, non verranno create registrazioni di programmazione nel programma di manutenzione quando si esegue un processo di piano di manutenzione di programmazione.

6. I campi **Giorni di tolleranza prima** e **Giorni di tolleranza dopo** sono relativi alle righe di piano di manutenzione in cui la casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** è selezionata (vedere il passaggio 17). I campi "Tolleranza" vengono utilizzati per estendere l'intervallo in giorni nel quale, se vi sono più piani di manutenzione che si sovrappongono, il processo più completo/più grande viene creato come riga di programma di manutenzione durante la programmazione del piano di manutenzione, mentre i processi che si sovrappongono più frequenti vengono omessi durante la programmazione del piano di manutenzione. Immettere il numero di giorni nel campo **Giorni di tolleranza prima**, ad esempio "2".

7. Se è stato immesso un valore in **Giorni di tolleranza prima**, inserire anche il numero di giorni nel campo **Giorni di tolleranza dopo**, ad esempio "2".

>[!NOTE]
>L'esempio descritto in questo passaggio e in quello precedente significa che se varie righe di piano di manutenzione si sovrappongono e la casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** è selezionata per una o più righe, il periodo di omissione delle righe di programma di manutenzione viene esteso fino a un totale di cinque giorni (la data di inizio prevista nella riga di programma di manutenzione *e* due giorni prima *e* due giorni dopo quella data).

8. I campi nel gruppo **Dettagli** nella Scheda dettaglio **Dettagli** visualizzano il numero di righe di piano di manutenzione impostate nel piano di manutenzione e il numero di cespiti e unità funzionali associati al piano di manutenzione.

9. Nella Scheda dettaglio **Righe**, fare clic su **Aggiungi riga tempo** o **Aggiungi riga contatore cespiti** per creare una nuova riga di piano di manutenzione.

10. Immettere una descrizione per la riga nel campo **Descrizione ordine di lavoro**. La descrizione viene trasferita agli ordini di lavoro correlati.

11. Selezionare il tipo di processo al quale la riga di piano di manutenzione è associata nel campo **Tipo di processo di manutenzione**.

12. Nei campi **Variante tipi di processo di manutenzione** e **Settore** selezionare la variante e il settore associato al tipo di processo di manutenzione.

13. Nei campi **Termina entro giorni** e **Termina entro ore**, è possibile immettere la data di fine prevista in giorni o ore. La data di fine prevista viene immessa in relazione alla data di inizio prevista, che viene calcolata quando vengono create le righe di programma di manutenzione. Ad esempio, è possibile immettere "7" nel campo **Termina entro giorni** per indicare che il processo associato deve essere completato entro una settimana dalla data di inizio prevista.

14. Nel campo **Tipo di intervallo**, selezionare il tipo di intervallo da utilizzare nella riga di piano di manutenzione, ad esempio "Ripetuto" o "Una volta". Fare riferimento alla tabella [Panoramica dei tipi di intervallo](## Interval types overview) sotto per una descrizione della relazione tra i tipi dell'intervallo e i tipi di riga.

15. Il campo **Periodo** si riferisce solo ai tipi di riga basati su tempo. Selezionare il tipo di periodo associato alla frequenza del periodo.

16. Nel campo **Frequenza periodo**, immettere il numero di volte che la riga deve essere utilizzata per la pianificazione dei processi di manutenzione preventiva. Esempio: se è stata creata una riga di tipo "Contatore", il contatore in uso designa la quantità di produzione e si inserisce "20000" in questo campo, le nuove righe di sequenza di manutenzione vengono create durante la programmazione di manutenzione preventiva ogni volta che è prevista una produzione di altri 20.000 articoli.

17. La casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** si riferisce a tipi di riga basati su tempo e su contatore. Selezionare la casella di controllo per eliminare le voci di programma di manutenzione create alla stessa data. Ciò è utile se, ad esempio, è stata creata una riga di ispezione di 1 mese, una riga di ispezione di 6 mesi e una riga di ispezione di 1 anno. Per l'ispezione di 1 anno, si desidera eseguire solo tale ispezione e non le altre due, che rientrerebbero anch'esse nell'intervallo di tempo indicato. Per impostare correttamente questo esempio, si imposta la riga di ispezione di 1 anno come prima riga, la riga di 6 mesi come seconda riga e la riga di 1 mese come terza riga e si seleziona la casella di controllo **Sopprimi processi di manutenzione che si sovrappongono** per le righe di 1 mese e di 6 mesi. In tal modo si garantisce che quando si raggiunge il limite di un anno, le ispezioni per un mese e sei mesi vengono omesse e una riga di programma di manutenzione viene creata solo per la riga di ispezione di 1 anno.

>[!NOTE]
>L'esempio descritto in questo passaggio mostra che il processo più completo, che contiene il maggior numero di attività e che non viene eseguito spesso, deve essere sempre inserito come prima riga. I processi più frequenti sono quindi immessi come righe distinte nell'ordine di frequenza, posizionando il processo più frequente nella parte inferiore dell'elenco.

18. Il campo **Contatore** si riferisce solo ai tipi di riga basati su contatore. Selezionare il tipo di contatore da utilizzare nella riga. Se un tipo di contatore non è attivo in un cespite associato, la riga di piano di manutenzione viene omessa.

19. Il campo **Intervallo temporale contatore cespiti in giorni** fa riferimento solo ai tipi di riga basati su contatore. Immettere un numero che definisce fino a quanti giorni a ritroso le registrazioni contatore vengono controllate quando si esegue la programmazione del piano di manutenzione. Ovvero fino a quale data passata i dati (registrazioni contatore esistenti) vengono utilizzati come base per il calcolo della tendenza che determina il numero di righe di programma di manutenzione che vengono create.

>*Esempio:* se le registrazioni contatore sono previste una volta al mese, è possibile immettere "365" in questo campo in quanto la programmazione del piano di manutenzione sarà sempre basata sugli ultimi 12 mesi e quindi creerà righe di programma di manutenzione basate silla tendenza dell'anno precedente. D'altra parte, se si immette il numero "10" in questo campo, si prevedono registrazioni contatore più frequenti, ad esempio, su base giornaliera. Ciò significa che quando si programma il piano di manutenzione, le registrazioni contatore per gli ultimi 10 giorni vengono utilizzate come base per la programmazione delle righe di programma di manutenzione.

20. Il campo **Data piano** si riferisce solo ai tipi di riga basati su tempo. Se la riga di piano di manutenzione ha un'altra data di pianificazione rispetto all'intero piano di manutenzione, selezionare una data nel campo **Data piano** nella riga.

21. Nel campo **Livello servizio**, è possibile selezionare un livello di servizio di ordine di lavoro come ulteriori delimitazione nella riga di piano di manutenzione, da utilizzare come livello di servizio negli ordini di lavoro.

22. Selezionare la casella di controllo **Crea automaticamente** se un ordine di lavoro deve essere creato automaticamente in base alla riga di piano di manutenzione selezionata quando si programmano piani di manutenzione.

23. Se è stata selezionata la casella di controllo **Crea automaticamente**, è possibile selezionare un tipo di ordine di lavoro per l'ordine di lavoro creato automaticamente nel campo **Tipo di ordine di lavoro**. Se è stata selezionata la casella di controllo **Crea automaticamente** e non si seleziona un tipo di ordine di lavoro in questo campo, viene utilizzato il tipo di ordine di lavoro selezionato in **Gestione cespiti** > **Impostazione** > **Parametri di gestione cespiti** > collegamento **Ordini di lavoro** > campo **Tipo di ordine di lavoro preventivo**.

24. Utilizzare i campi **Stagione da** e **Stagione a** per creare una riga di piano di manutenzione basata su tempo ripetuta entro un periodo di 12 mesi. *Esempio:* l'attrezzatura utilizzata per la gestione delle aree verdi richiede un intervento ogni primavera entro un periodo predefinito. Immettere la data di inizio del periodo da ripetere nel campo **Stagione da**.

25. Immettere la data di fine del periodo da ripetere nel campo **Stagione a**.

26. Nel campo **Periodo risultante**, viene visualizzato il periodo corrente da ripetere. Quando il periodo corrente è trascorso e si inizia un nuovo anno, il periodo visualizzato in questo campo verrà aggiornato per riflettere il periodo successivo nella sequenza di ripetizione.

27. Nella Scheda dettaglio **Cespiti**, selezionare i cespiti che devono essere associati al piano di manutenzione.

28. Nella Scheda dettaglio **Tipi di cespite**, selezionare i tipi di cespite che devono essere associati al piano di manutenzione.

29. Nella Scheda dettaglio **Unità funzionali**, selezionare le unità funzionali che devono essere associate al piano di manutenzione. Se necessario, è possibile rendere l'impostazione più specifica selezionando un tipo, un produttore e un modello di cespite associati.

30. Nella Scheda dettaglio **Tipi di unità funzionali**, selezionare i tipi di unità funzionali che devono essere associati al piano di manutenzione.

>[!NOTE]
>Quando gli ordini di lavoro vengono creati manualmente nei cespiti coperti da un garanzia fornitore, viene visualizzata una finestra di dialogo per informare l'utente della garanzia. La creazione dell'ordine di lavoro può quindi essere annullata. La verifica di una relazione di garanzia viene omessa per gli ordini di lavoro creati automaticamente.

## <a name="interval-types-overview"></a>Panoramica dei tipi di intervallo

| Tipo e descrizione dell'intervallo                                                                                                                                                                                                                                                                                                                                                                                                       | Tipo di riga: tempo                                                                                                                                                                                                                                                                                                                                                           | Tipo di riga: contatore                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Tipo di intervallo: ripetuto dalla data del piano** Il conteggio inizia dalla data del piano utilizzata. Quando si programmano piani di manutenzione, le righe del programma di manutenzione vengono create quando si raggiunge l'intervallo.                                                                                                                                                                                                                | Viene utilizzata la **Data di piano** nella riga di piano di manutenzione. Se nessuna data di piano viene selezionata nella riga, viene utilizzata la **Data di piano** per il piano di manutenzione. Esempio: se si immette "3" nel campo **Frequenza periodo** e "Anno" è selezionato nel campo **Periodo**, una nuova riga di programma di manutenzione viene creata una volta ogni 3 anni.                             | Viene utilizzata la **Data di piano** per il piano di manutenzione. Se il contatore è stato sostituito, l'ultima data di sostituzione viene utilizzata come data di piano.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Tipo di intervallo: ripetuto dalla data di inizio** Il conteggio inizia dalla data di inizio nella relazione cespite. La data viene selezionata nella visualizzazione dettagli **Tutto i cespiti** > Scheda dettaglio **Piani di manutenzione cespiti** > campo **Data di inizio** o nella visualizzazione dettagli **Tutte le aree funzionali** > Scheda dettaglio **Piani di manutenzione** > campo **Data di inizio**. Quando si programmano piani di manutenzione, una riga di programma di manutenzione viene creata quando si raggiunge l'intervallo. | Viene utilizzata la data di inizio della riga di piano di manutenzione nel cespite o nell'unità funzionale. Se tale campo è vuoto, viene utilizzata la **Data di piano** per il piano di manutenzione.                                                                                                                                                                                                 | Viene utilizzata la data di inizio della riga di piano di manutenzione nel cespite o nell'unità funzionale. Se tale campo è vuoto, viene utilizzata la **Data di piano** per il piano di manutenzione.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **ITipo di intervallo: ripetuto dall'ultimo ordine di lavoro** Il conteggio inizia dalla data e dall'ora di fine effettive dell'ultimo ordine di lavoro completato per il cespite con il tipo di processo di manutenzione specifico/la combinazione di settore/variante di tipi di processo di manutenzione. Quella data e quell'ora sono visualizzate nel campo **Fine effettiva** nella visualizzazione dettagli **Tutti gli ordini di lavoro**.                                                                                                                                 | Viene utilizzata la data e l'ora di fine effettive dell'ordine di lavoro completato per il cespite con la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione specifica. Se non viene trovato un ordine di lavoro completato, viene invece utilizzata una delle date usate nel tipo di intervallo "Ripetuto da data di inizio" descritto sopra.                                                                                             | Viene utilizzata la data e l'ora di fine effettive dell'ordine di lavoro completato per il cespite *e* la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione . Se la data e l'ora di fine non sono state specificate nell'ordine di lavoro, viene invece utilizzata una delle date usate nel tipo di intervallo "Ripetuto da data di inizio" descritto sopra.                                                                                                                                                                                                                                                                                                                                                                           |
| **Tipo di intervallo: una volta dalla data di piano** Vedere la descrizione del tipo di intervallo "Ripetuto dalla data di piano" visto sopra. La sola differenza è che questo tipo di intervallo deve essere utilizzato una sola volta.                                                                                                                                                                                                                                                   | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di piano" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico.                                                                                                                                                                                                                             | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di piano" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico. **Nota: 1** Il tipo di intervallo è pertinente solo se il contatore viene sostituito ogni volta che si esegue un processo di manutenzione o di assistenza. Se, per un qualsiasi motivo, un contatore è stato sostituito prima della fine dell'intervallo pianificato, un nuovo periodo viene calcolato per il processo dal momento della sostituzione del contatore. **Nota 2:** se il contatore viene sostituito durante il completamento del processo di manutenzione o di assistenza, questo tipo di intervallo funziona come tipo di intervallo "Ripetuto dalla data di piano" visto sopra.                                             |
| **Tipo di intervallo: una volta dalla data di inizio** Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di inizio" visto precedentemente. La sola differenza è che questo tipo di intervallo deve essere utilizzato una sola volta.                                                                                                                                                                                                                                                 | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di inizio" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico.                                                                                                                                                                                                                            | Vedere la descrizione per il tipo di intervallo "Ripetuto dalla data di inizio" visto precedentemente. Questo intervallo viene in genere utilizzato per un processo di manutenzione o di assistenza unico. La **Nota 1** è valida anche per questo tipo di intervallo. **Nota 3:** se il contatore viene sostituito durante il completamento del processo di manutenzione o di assistenza, questo tipo di intervallo funziona come tipo di intervallo "Ripetuto dalla data di inizio" visto sopra.                                                                                                                                                                                                                                                                                                |
| **Tipo di intervallo: quando superiore** Questo tipo di intervallo si riferisce solo ai contatori e viene utilizzato per indicare un limite superiore impostato nella riga di piano di manutenzione. Le voci del programma di manutenzione avranno la data e l'ora di inizio previste della registrazione contatore, ovvero tali voci verranno create con una data di inizio prevista uguale o antecedente alla data di sistema.                                                | N/D                                                                                                                                                                                                                                                                                                                                                                       | L'intervallo contatore indica un limite superiore. Se tale limite viene superato quando si crea una registrazione contatore, viene creata una riga di programma di manutenzione quando si programma la manutenzione preventiva.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Tipo di intervallo: quando inferiore** Questo tipo di intervallo si riferisce solo ai contatori e viene utilizzato per indicare un limite inferiore impostato nella riga di piano di manutenzione. Le voci del programma di manutenzione avranno la data e l'ora di inizio previste della registrazione contatore, ovvero tali voci verranno create con una data di inizio prevista uguale o antecedente alla data di sistema.                                                 | N/D                                                                                                                                                                                                                                                                                                                                                                       | L'intervallo contatore indica un limite inferiore. Se tale limite viene superato quando si crea una registrazione contatore, viene creata una riga di programma di manutenzione quando si programma la manutenzione preventiva.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Tipo di intervallo: Collegato alla data di inizio** Questo tipo di intervallo crea una riga del programma di manutenzione una sola volta. Un piano di manutenzione può contenere più righe del piano di manutenzione utilizzando questo tipo di intervallo e tali righe sono collegate. In genere, si crea un piano di manutenzione che contiene righe soltanto di questo tipo di intervallo. Le righe di programma di manutenzione vengono create identificando la riga di piano di manutenzione che ha la prima data e ora di inizio previste.                                                                                                                                                                                                                                                                                                                                                                                           | Vedere la descrizione di "Una volta dalla data di inizio" esposta precedentemente. Esempio: si creano due righe in un piano di manutenzione per un processo di assistenza per un auto: una riga basata su tempo con un periodo di un anno e una basata su contatore con un limite di 25.000 km. Una riga di programma di manutenzione viene creata per il limite che viene raggiunto per primo. Per questo tipo di riga si crea la riga con il periodo di un anno.                                                                                                                                                                                   | Vedere la descrizione di "Una volta dalla data di inizio" esposta precedentemente. Esempio: si creano due righe in un piano di manutenzione per un processo di assistenza per un auto: una riga basata su tempo con un periodo di un anno e una basata su contatore con un limite di 25.000 km. Una riga di programma di manutenzione viene creata per il limite che viene raggiunto per primo. Per questo tipo di riga si crea la riga con il limite di 25.000 km. Esempio che crea due righe contatore: è anche possibile impostare un piano di manutenzione con due righe basate su contatore collegate in cui la prima riga ha un limite di 10.000 articoli prodotti e la seconda riga è relativa alla macchina o al centro di lavoro che richiede un intervento dopo 3.000 ore.                                                                                                                                                           |
| **Tipo di intervallo: Collegato dall'ultimo ordine di lavoro** Questo tipo di intervallo crea nuove righe del programma di manutenzione dopo ogni ordine di lavoro completato. Un piano di manutenzione può contenere più righe utilizzando questo tipo di intervallo e tali righe sono collegate. In genere, si crea un piano di manutenzione che contiene righe del piano di manutenzione soltanto di questo tipo di intervallo. Le righe di programma di manutenzione vengono create identificando la riga di piano di manutenzione che ha la prima data e ora di inizio previste.                                                                                                                                                                                                                                                                        | In pratica questo tipo di intervallo funziona come "Collegato dalla data di inizio" descritto sopra. La sola differenza è la data su cui il tipo di intervallo è basato. La data utilizzata è la data e l'ora effettive nell'ultimo ordine di lavoro completato nel cespite *e* la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione.                                                                                                                                                                                                                                                           | In pratica questo tipo di intervallo funziona come "Collegato dalla data di inizio" descritto sopra. La sola differenza è la data su cui il tipo di intervallo è basato. La data utilizzata è la data e l'ora effettive nell'ultimo ordine di lavoro completato nel cespite *e* la combinazione di settore/tipo di processo di manutenzione/variante di tipi di processo di manutenzione.                                                                                                                   |


>[!NOTE]
>Quando le righe di programma di manutenzione vengono create per le righe di piano di manutenzione basate su tempo, l'ora prevista è sempre all'inizio del giorno. Per le righe di piano di manutenzione basate su contatore, l'ora prevista può essere in qualsiasi momento del giorno.

Di seguito sono riportati alcuni esempi dell'impostazione delle righe di piano di manutenzione basate su tempo e contatore:

**Esempio 1 - Riga di piano di manutenzione basata su tempo:** Un'attività di lubrificazione può essere impostata in un intervallo fisso e si verifica una volta alla settimana. A questo scopo, selezionare "Ripetuto dalla data di piano" nel campo **Tipo di intervallo**. Vedere l'esempio illustrato nella figura seguente.

![Figura 1](media/02-preventive-maintenance.png)

**Esempio 2 - Riga di piano di manutenzione basata su tempo:** Un'attività di ispezione può essere impostata per essere eseguita approssimativamente una volta alla settimana. A questo scopo, selezionare "Ripetuto dall'ultimo ordine di lavoro" nel campo **Tipo di intervallo**. Vedere l'esempio illustrato nella figura seguente.

![Figura 2](media/03-preventive-maintenance.png)

**Esempio 3 - Riga di piano di manutenzione basata su contatore:** La seguente illustrazione grafica mostra un contatore a ore per il quale una nuova riga di programma di manutenzione viene creata ogni volta che vengono superate le 250 ore. Il tipo di intervallo per questa riga basata su contatore è "Ripetuto dalla data di inizio". La data di inizio è la data di inizio dei cespiti associati nella visualizzazione dettagli **Tutto i cespiti** > Scheda dettaglio **Piani di manutenzione cespiti** > campo **Data di inizio** o nella visualizzazione dettagli **Unità funzionali** > Scheda dettaglio **Piani di manutenzione** > campo **Data di inizio**. Questo è un esempio di piano di manutenzione *preventiva* poiché la riga di programma di manutenzione viene creata automaticamente ogni volta che viene raggiunta la soglia (+ 250).

![Figura 3](media/04-preventive-maintenance.png)


**Esempio 4 - Riga di piano di manutenzione basata su contatore:** La seguente illustrazione grafica mostra una diminuzione del valore di contatore, che misura l'usura delle pastiglie dei freni. Una riga di programma di manutenzione viene creata quando una registrazione contatore inferiore a 20 mm viene creata per la pastiglia dei freni. Il tipo di intervallo per questa riga basata su contatore è "Quando inferiore" o "Una volta dall'ultima data di inizio". Questo è un esempio di piano di manutenzione *reattivo* poiché la riga di programma di manutenzione non viene creata fino a che non viene registrata una misura inferiore a 20 mm.

![Figura 4](media/05-preventive-maintenance.png)


**Esempio 5 - Riga di piano di manutenzione basata su contatore:** La seguente illustrazione grafica mostra un contatore con una soglia di -18 °C. Una riga di programma di manutenzione viene creata quando viene effettuata una registrazione contatore superiore a -18 °C. Il tipo di intervallo per questa riga basata su contatore è "Quando superiore". Questo è un esempio di piano di manutenzione *reattivo* poiché la riga di programma di manutenzione non viene creata fino a che non viene registrata una misura superiore a -18 °C.

![Figura 5](media/06-preventive-maintenance.png)

- Quando si crea un nuovo cespite e questo utilizza un tipo di cespite relativo a un piano di manutenzione, il piano di manutenzione viene automaticamente immesso in **Tutti gli oggetti** > Scheda dettaglio **Piani di manutenzione cespiti**. Inoltre, in **Valori predefiniti tipo di cespite**, nella Scheda dettaglio **Piano di manutenzione**, verranno automaticamente inseriti i piani di manutenzione correlati.  
- Se si aggiungono o rimuovono tipi di cespite o tipi di unità funzionale in **Piani di manutenzione**, tale modifica viene riflessa solo nei nuovi cespiti creati dopo la modifica.  
- Se si aggiungono o rimuovono cespiti o unità funzionali in **Piani di manutenzione**, tale modifica verrà automaticamente aggiornata in **Tutti i cespiti** > , Scheda dettaglio **Piani di manutenzione cespiti** o in **Tutte le unità funzionali** > Scheda dettaglio **Piani di manutenzione**.  

Nella figura seguente è illustrato un esempio di un piano di manutenzione di "assistenza camion" nella pagina **Piani di gestione**.

![Figura 6](media/07-preventive-maintenance.png)


## <a name="add-a-maintenance-plan-to-an-asset"></a>Aggiungere un piano di manutenzione a un cespite

1. Fare clic su **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti** o **Cespiti attivi**.

2. Selezionare il cespite per il quale si desidera impostare un piano di manutenzione e fare clic su **Modifica**.

3. Nella Scheda dettaglio **Piani di manutenzione cespiti**, fare clic su **Aggiungi riga** per aggiungere un piano di manutenzione al cespite.

4. Nel campo **Piano di manutenzione**, selezionare il piano di manutenzione pertinente.

5. Nel campo **Data di inizio**, selezionare la data a partire dalla quale è possibile eseguire la pianificazione dei processi di manutenzione preventiva. 

6. Fare clic su **Salva**. Il campo **Attivo** viene aggiornato automaticamente.

Nella figura seguente è illustrato un esempio di un piano di manutenzione configurato per un cespite nella pagina **Tutti i cespiti**.

![Figura 7](media/08-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]