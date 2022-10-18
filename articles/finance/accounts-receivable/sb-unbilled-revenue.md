---
title: Ricavi non fatturati
description: Questo articolo spiega come impostare gli articoli e i conti per utilizzare la funzione dei ricavi non fatturati nella fatturazione abbonamento.
author: JodiChristiansen
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: adf6f06ee454f368fa194315a87cfdec9e5e13da
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644170"
---
# <a name="unbilled-revenue"></a>Ricavi non fatturati

In questo articolo viene descritta la funzione dei ricavi non fatturati che consente di includere gli importi per intere programmazioni fatturazione nello stato patrimoniale. Questi importi sono inclusi in un conto ricavi non fatturati e in un conto di contropartita ricavi non fatturati e il contratto viene fatturato a rate.

## <a name="set-up-unbilled-revenue"></a>Impostare ricavi non fatturati

Per impostare i ricavi non fatturati, effettua le seguenti operazioni.

- Imposta i campi della sezione **Ricavi non fatturati** della pagina **Parametri di fatturazione contratto ricorrente**.
- La funzione ricavi non fatturati può essere utilizzata per gli articoli in cui il campo **Tipo di articolo** è impostato su **Standard**. Può essere utilizzato anche per gli articoli di differimento. Per utilizzare i ricavi non fatturati con la funzionalità a breve termine, imposta le opzioni a breve termine nella pagina **Parametri di fatturazione contratto ricorrente**.

Per impostare gli articoli e usare i ricavi non fatturati, effettua le seguenti operazioni.

1. Nella pagina **Configurazione ricavi non fatturati** nella scheda **Articoli** seleziona **Aggiungi**.
2. Sulla nuova riga, in **Codice articolo**, seleziona il codice articolo.
3. Nel campo **Relazione articolo** seleziona la relazione dell'articolo.
4. Ripeti questi passaggi per aggiungere altre righe.
5. Seleziona **Salva**.

Per impostare gli articoli e i conti ricavi non fatturati, effettua le seguenti operazioni.

1. Nella pagina **Configurazione ricavi non fatturati** nella scheda **Conti** seleziona **Aggiungi**.
2. Sulla nuova riga, in **Codice articolo**, seleziona il codice articolo.
3. Nel campo **Relazione articolo** seleziona la relazione dell'articolo.
4. Seleziona i conti per i ricavi non fatturati, lo sconto non fatturato e la contropartita ricavi non fatturati. Per utilizzare i conti a breve termine, è necessario impostare il campo **Metodo non fatturato a breve termine** su **Periodi operativi continui** o **Anno fisso** nella pagina **Parametri di fatturazione contratto ricorrente**.
5. Ripeti questi passaggi per aggiungere altre righe.
6. Seleziona **Salva**.

## <a name="use-unbilled-revenue"></a>Usare i ricavi non fatturati

1. Nella pagina **Tutti i programmi di fatturazione** crea un programma di fatturazione.
2. Se l'articolo non è ancora configurato per utilizzare i ricavi non fatturati, seleziona la casella di controllo **Ricavi non fatturati** nella riga del programma di fatturazione.
3. Imposta l'opzione **Ricavi non fatturati** su **Sì**. Quindi rivedi e modifica i conti ricavi non fatturati, sconti e contropartita ricavi non fatturati come richiesto.
4. Nel programma di fatturazione, sotto **Elaborazione ricavi non fatturati**, seleziona **Crea scrittura contabile** per creare la scrittura contabile iniziale per i ricavi non fatturati. Questo passaggio deve essere completato prima della fatturazione del programma di fatturazione.
5. Dopo aver creato la scrittura contabile iniziale seleziona **Genera fattura** per creare ordini cliente e registrare le fatture per i programmi di fatturazione.
6. Dopo che le fatture sono state registrate, è possibile rivedere le informazioni di controllo nella scheda **Rinnovi** della pagina **Tutti i programmi di fatturazione**.

### <a name="milestone-billing"></a>Fatturazione a fasi

La fatturazione a fasi funziona con i ricavi non fatturati alle seguenti condizioni:

- Se l'articolo padre della fatturazione a fasi non è fatturato (la casella di controllo **Ricavi non fatturati** è selezionata) e gli articoli figlio della fatturazione a fasi vengono fatturati (la casella di controllo **Ricavi non fatturati** è deselezionata), è necessario specificare le date di inizio e fine per l'articolo padre. Queste date vengono utilizzate per creare la scrittura contabile iniziale.
- Se l'articolo padre della fatturazione a fasi non è fatturato (la casella di controllo **Ricavi non fatturati** è deselezionata) e gli articoli figlio della fatturazione a fasi vengono fatturati (la casella di controllo **Ricavi non fatturati** è selezionata), la data di fine deve essere specificata solo per gli articoli figlio per i quali vuoi creare la scrittura contabile iniziale.

Ogni articolo figlio della fatturazione a fasi può essere elaborato separatamente. Le date di fine possono essere specificate quando sei pronto per creare la scrittura contabile iniziale.

> [!NOTE]
> Se la scrittura contabile iniziale per l'articolo padre o gli articoli figlio è già stata creata oppure è stata creata una fattura, le date di inizio e di fine non possono essere modificate.

### <a name="unbilled-revenue-with-straight-line-deferrals"></a>Ricavi non fatturati con differimenti a quote costanti

Per utilizzare i ricavi non fatturati con programmi di differimento a quote costanti, attieniti alla seguente procedura.

1. Nella pagina **Tutti i programmi di fatturazione** crea un programma di fatturazione.
2. Aggiungi un articolo alle righe programma di fatturazione.
3. Seleziona **Differimenti** per riga.
4. Nella pagina **Differimento transazione** esegui i passaggi indicati di seguito:

    1. Imposta l'opzione **Differito** su **Sì**.
    2. Modifica i conti in base alle esigenze.
    3. Nella sezione **Programma** seleziona **A quote costanti** e modifica altri valori come richiesto.
    4. Seleziona **OK**.

5. Seleziona **Ricavi non fatturati** per la riga, quindi attieniti alla seguente procedura:

    1. Imposta l'opzione **Ricavi non fatturati** su **Sì**.
    2. Seleziona i conti da usare per i ricavi, lo sconto e la contropartita ricavi.

6. Nel programma di fatturazione, sotto **Elaborazione ricavi non fatturati**, seleziona **Crea scrittura contabile**. In alternativa, utilizza la pagina **Elaborazione di massa ricavi non fatturati** per creare la scrittura contabile.
7. Il programma di differimento viene creato. Puoi rivedere i dettagli nella pagina **Tutti i programmi di differimento**. Dopo aver creato il programma di differimento, è possibile modificare vari valori per la voce del programma di fatturazione. Ad esempio, puoi modificare il prezzo unitario, la quantità o le date.

### <a name="unbilled-revenue-with-event-based-deferrals"></a>Ricavi non fatturati con differimenti basati su eventi

Per utilizzare i ricavi non fatturati con programmi di differimento basati su eventi, attieniti alla seguente procedura.

1. Nella pagina **Tutti i programmi di fatturazione** crea un programma di fatturazione.
2. Aggiungi un articolo alle righe programma di fatturazione.
3. Seleziona **Differimenti** per riga.
4. Nella pagina **Differimento transazione** esegui i passaggi indicati di seguito:

    1. Imposta l'opzione **Differito** su **Sì**.
    2. Modifica i conti in base alle esigenze.
    3. Nella sezione **Programma** seleziona **Basato su eventi**, **Modello**, **Tipo di allocazione**, e **Conto scadenza**.
    4. Seleziona **OK**.

5. Seleziona **Ricavi non fatturati** per la riga, quindi attieniti alla seguente procedura:

    - Imposta l'opzione **Ricavi non fatturati** su **Sì**.
    - Seleziona i conti da usare per i ricavi, lo sconto e la contropartita ricavi.

6. Nel programma di fatturazione, sotto **Elaborazione ricavi non fatturati**, seleziona **Crea scrittura contabile**. In alternativa, utilizza la pagina **Elaborazione di massa ricavi non fatturati** per creare la scrittura contabile.
7. Il programma di differimento viene creato. Puoi rivedere i dettagli nella pagina **Tutti i programmi di differimento**. Dopo aver creato il programma di differimento, è possibile modificare vari valori per la voce del programma di fatturazione. Ad esempio, puoi modificare il prezzo unitario, la quantità o le date. Il programma di differimento viene ricalcolato in base ai nuovi valori.

Le distribuzioni vengono ricalcolate in base al tipo di allocazione selezionato (**Percentuale**, **Completamento percentuale**, o **Pari importi**). Per il tipo di allocazione **Importi variabili**, la distribuzione viene ricalcolata in base all'equivalente percentuale del valore iniziale dell'evento. Ad esempio, il prezzo unitario originale è $100,00 e la percentuale del valore iniziale è $55,00 (55%). Se il prezzo unitario viene modificato in $200,00, l'importo variabile dell'evento diventa $110,00 (ancora 55%).

> [!NOTE]
> Se le righe programma di differimento sono state riconosciute, la voce del programma di fatturazione non può essere modificata. Per modificare la voce, devi prima stornare le righe riconosciute. La riga programmazione fatturazione può quindi essere aggiornata.

### <a name="unbilled-revenue-and-top-billing"></a>Ricavi non fatturati e fatturazione principale

Viene inserito un programma di fatturazione per tre anni e le fatture vengono fatturate ogni anno per un periodo di tre anni. L'intero importo del contratto viene registrato nel conto ricavi non fatturati da cui vengono create le fatture annuali. Il conto di contropartita è il conto dei ricavi o dei ricavi differiti.

La fatturazione principale e i ricavi non fatturati non funzionano insieme, perché nella contabilità generale possono verificarsi problemi di riconciliazione. Ad esempio, sulla pagina **Impostazione gruppo di articoli**, il gruppo di articoli A è impostato in modo che il campo **Numero di righe principali** è impostato su **2**. Sulla pagina **Programmi di fatturazione** vengono aggiunti tre articoli. Tutti e tre gli articoli appartengono al gruppo di articoli A. Quando viene creata la scrittura contabile iniziale per la funzione ricavi non fatturati, l'importo per tutti e tre gli articoli viene elaborato nel conto non fatturato. Quando viene creata la fattura per il programma di fatturazione, vengono inclusi solo gli importi dei primi due articoli. Pertanto, l'importo della fattura non corrisponde all'importo elaborato nel conto ricavi non fatturati e nella contabilità generale si verificano problemi di riconciliazione.

Se desideri utilizzare i ricavi non fatturati, lascia il campo **Impostazione gruppo di articoli** vuoto o imposta tutti i gruppi di articoli in modo che il campo **Numero di righe principali** sia impostato su **0** (zero). Se desideri utilizzare la fatturazione principale, non sono disponibili azioni relative ai ricavi non fatturati.

### <a name="examples"></a>Esempi

A partire dalla versione 10.0.29, viene aggiunto un nuovo parametro ai parametri di fatturazione contratto ricorrente. Quando è impostato su Sì, il parametro **Utilizza conti di contropartita non fatturati** abilita due nuovi conti in **Impostazione ricavi non fatturati**. I conti di contropartita ricavi non fatturati e di contropartita sconti non fatturati diventano disponibili e vengono utilizzati al meglio quando i programmi di fatturazione vengono creati in una valuta diversa da quella contabile. L'utilizzo dei conti di contropartita garantisce che i conti relativi ai ricavi non fatturati e agli sconti non fatturati vengano stornati utilizzando gli stessi tassi di cambio dei movimenti iniziali. Il processo iniziale **Crea scrittura contabile** è lo stesso con l'addebito sui ricavi non fatturati e l'accredito sui ricavi. Se si utilizza uno sconto, la scrittura contabile iniziale è la stessa con un addebito su sconto e un accredito su sconto non fatturato. 

Questo esempio mostra come utilizzare i ricavi non fatturati per rilevare l'intero importo di un contratto nello stato patrimoniale come ricavi non fatturati. L'altro lato della voce è il ricavo o il ricavo differito. Quando si fattura al cliente, i ricavi non fatturati vengono stornati. Il riconoscimento dei ricavi avverrà al momento della fatturazione o secondo la programmazione di riconoscimento del differimento che è stata impostata.

#### <a name="assumptions"></a>Presupposti

- Il 1 gennaio dell'anno in corso, un cliente firma un contratto triennale per $390.
- Il contratto comprende due parti: licenze e un contratto di manutenzione.
- Il prezzo di vendita della commissione di licenza è $300 e al cliente verrà fatturato $100 il 1 gennaio di ogni anno contrattuale. La commissione di licenza di $300 sarà considerata come ricavi al momento della firma del contratto.
- Il prezzo di vendita della commissione di manutenzione è $90 e al cliente verrà fatturato $30 il 1 gennaio di ogni anno contrattuale. La commissione di manutenzione di $90 verrà differita e $2,50 verrà riconosciuto ogni mese di vita del contratto.
- Al cliente verrà fatturato $130 all'inizio (1 gennaio) di ciascuno dei tre anni di contratto.

#### <a name="steps"></a>Gradi

1. Imposta i due articoli rilasciati come articoli non fatturati. Usa la pagina **Impostazione ricavi non fatturati** per impostare gli articoli e i conti che utilizzano i ricavi non fatturati.
2. In questo esempio, la commissione di manutenzione è differita. L'articolo richiede un modello di differimento, che è impostato sulla pagina **Modelli di differimento**. Il modello ha una frequenza del periodo **Mensile** e una durata del periodo di riconoscimento di 36 mesi. Di conseguenza, i ricavi per mese sono $2,50.
3. Sulla pagina **Articoli differiti per impostazione predefinita** imposta il campo **Commissione manutenzione** su **Articolo differibile**. Questo passaggio e il successivo comporteranno il differimento dell'articolo commissione di manutenzione quando viene venduto o incluso in un programma di fatturazione.
4. Seleziona **Valori predefiniti di differimento** \> **Modello** e aggiungi l'articolo per la commissione di manutenzione e il modello a quote costanti del passaggio 2. L'articolo commissione di manutenzione sarà collegato a un programma di differimento di 36 mesi.
5. Crea un programma di fatturazione che includa i due articoli non fatturati. Il programma di fatturazione per il contratto è impostato con i seguenti articoli.

    | Elemento | Data di inizio | Data di fine | Importo | Frequenza di fatturazione | Articolo di differimento | Ricavi non fatturati | Description |
    |---|---|---|---|---|---|---|---|
    | Licenza | 01 gennaio 2022 | 31 dicembre 2024 | $100,00 | Annuale | Numero | Sì | Al cliente verrà fatturato $100,00 ogni anno. Il totale $300,00 sarà registrato in anticipo come ricavi non fatturati nello stato patrimoniale e come ricavi in profitti e perdite. Ogni fattura ridurrà l'importo non fatturato. |
    | Gestione | 01 gennaio 2022 | 31 dicembre 2024 | $30,00 | Annuale | Sì | Sì | Al cliente verrà fatturato $30,00 ogni anno. Il totale $90,00 sarà registrato in anticipo come ricavi non fatturati e come ricavi differiti nello stato patrimoniale. Ogni fattura ridurrà l'importo non fatturato. Il ricavo differito sarà riconosciuto mensilmente in 36 mesi. |

6. Sulla pagina **Tutti i programmi di fatturazione** utilizza il processo **Crea scrittura contabile** per registrare il valore del contratto nello stato patrimoniale come ricavi non fatturati.

Vengono create due scritture contabili, una per ogni riga del programma di fatturazione.

| Conto | Importo in Dare | Importo in Avere |
|---|---|---|
| Conto ricavi non fatturati | $300,00 | |
| Conto ricavi | | $300,00 |

| Conto | Importo in Dare | Importo in Avere |
|---|---|---|
| Conto ricavi non fatturati | $90,00 | |
| Ricavi differiti | | $90,00 |

Il contratto prevede che la fattura per il cliente sia creata all'inizio di ogni anno. Usa il processo **Genera fattura** per creare la fattura. Quando viene creata la fattura, viene registrato il seguente giustificativo fattura.

| Conto| Importo in Dare | Importo in Avere |
|---|---|---|
| Conto ricavi non fatturati | | $130,00 |
| Contabilità clienti | $130,00 | |

Questa stessa scrittura contabile verrà creata dalle fatture registrate all'inizio dei due anni successivi. Il conto dei ricavi non fatturati viene ridotto ogni anno durante il processo **Genera fattura**. Il conto di contropartita ricavi non fatturati viene utilizzato per bilanciare il conto ricavi non fatturati quando vengono utilizzati tassi di cambio diversi. 

Nell'ultimo passaggio, la scrittura contabile di riconoscimento viene creata ogni mese per riconoscere i ricavi della commissione di manutenzione differiti. La scrittura contabile può essere creata utilizzando la pagina **Elaborazione riconoscimento**. In alternativa, può essere creata selezionando **Riconosci** per le righe sulle pagine **Programma di differimento**.

| Conto principale | Importo in Dare | Importo in Avere |
|---|---|---|
| Ricavi differiti | $2,50 | |
| Ricavi | | $2,50 |

Questa scrittura contabile verrà creata ogni volta che viene eseguito il processo di riconoscimento per questo articolo differito (per un totale di 36 volte).

#### <a name="short-term-fixed-year"></a>Breve termine: anno fisso

Puoi utilizzare i ricavi non fatturati con la funzionalità a breve termine impostando il campo **Metodo non fatturato a breve termine** nella pagina **Parametri di fatturazione contratto ricorrente**. L'esempio seguente mostra i calcoli che vengono eseguiti quando i ricavi non fatturati vengono utilizzati insieme al metodo non fatturato a breve termine **Anno fisso**.

Viene creato un programma di fatturazione con i seguenti criteri:

- **Data di inizio:** 1 giugno 2020
- **Data di fine:** 31 dicembre 2021
- **Prezzo unitario:** $100
- **Frequenza:** Mensile

Sulla pagina **Tutti i programmi di fatturazione** la scrittura contabile iniziale viene creata dal processo **Crea scrittura contabile**. Gli importi correnti a breve e a lungo termine sono calcolati nel modo seguente:

- **Importo corrente dei ricavi non fatturati a breve termine:** $700
- **Importo corrente dei ricavi non fatturati a lungo termine:** $1.200

La fattura viene creata per il periodo di fatturazione dal 1 giugno 2020 al 30 novembre 2020. Gli importi correnti a breve e a lungo termine sono calcolati nel modo seguente:

- **Importo corrente dei ricavi non fatturati a breve termine:** $100
- **Importo corrente dei ricavi non fatturati a lungo termine:** $1.200

La fattura viene creata per il periodo di fatturazione dal 1 dicembre 2020 al 31 dicembre 2020. Gli importi correnti a breve e a lungo termine sono calcolati nel modo seguente:

- **Importo corrente dei ricavi non fatturati a breve termine:** $1.200
- **Importo corrente dei ricavi non fatturati a lungo termine:** $0

#### <a name="short-term-rolling-periods"></a>A breve termine: Periodi operativi continui

Puoi utilizzare i ricavi non fatturati con la funzionalità a breve termine impostando il campo metodo non fatturato a breve termine nella pagina **Parametri di fatturazione contratto ricorrente**. L'esempio seguente mostra i calcoli che vengono eseguiti quando i ricavi non fatturati vengono utilizzati insieme al metodo non fatturato a breve termine **Periodi operativi continui**.

Viene creato un programma di fatturazione con i seguenti criteri:

- **Data di inizio:** 1 giugno 2020
- **Data di fine:** 31 dicembre 2021
- **Prezzo unitario:** $100
- **Frequenza:** Mensile

Sulla pagina **Tutti i programmi di fatturazione** la scrittura contabile iniziale viene creata dal processo **Crea scrittura contabile**. Gli importi correnti a breve e a lungo termine sono calcolati nel modo seguente:

- **Importo corrente dei ricavi non fatturati a breve termine:** $1.200
- **Importo corrente dei ricavi non fatturati a lungo termine:** $700

La fattura viene creata per il periodo di fatturazione dal 1 giugno 2020 al 30 novembre 2020. Gli importi correnti a breve e a lungo termine sono calcolati nel modo seguente:

- **Importo corrente dei ricavi non fatturati a breve termine:** $1.200
- **Importo corrente dei ricavi non fatturati a lungo termine:** $100

La fattura viene creata per il periodo di fatturazione dal 1 dicembre 2020 al 31 dicembre 2020. Gli importi correnti a breve e a lungo termine sono calcolati nel modo seguente:

- **Importo corrente dei ricavi non fatturati a breve termine:** $1.200
- **Importo corrente dei ricavi non fatturati a lungo termine:** $0

### <a name="items-with-revenue-allocation"></a>Articoli con allocazione dei ricavi

Due articoli con frequenze di fatturazione diverse vengono aggiunti a un programma di fatturazione. Entrambi utilizzano ricavi non fatturati e sono articoli differibili.

- **Numero articolo 1000:** Surface Pro 128 GB

    - **Frequenza di fatturazione:** Una volta
    - **Prezzo unitario:** $1.500
    - **Prezzo di vendita autonomo:** $1.600
    - **Ricavi di contratto:** $1.465,26

- **Numero articolo S0021:** Assicurazione venduta insieme all'articolo numero 1000

    - **Frequenza di fatturazione:** Mensile per 12 mesi
    - **Prezzo unitario:** $20 al mese
    - **Prezzo di vendita autonomo:** $25
    - **Ricavi di contratto:** $264,74

Poiché entrambi gli articoli utilizzano i ricavi non fatturati e l'allocazione dei ricavi, l'importo totale del contratto nella riga di rinnovo è 0 (zero). La colonna **Ricavi di contratto** viene aggiunta e mostra l'importo dei ricavi del contratto.

La tabella seguente mostra la scrittura contabile iniziale per gli articoli e la fattura.

| Conto principale | Importo in Dare | Importo in Avere |
|---|---|---|
| **Scrittura contabile articolo 1000** | | | 
| Conto ricavi non fatturati (401250) | $1.465,26 | |
| Conto ricavi differiti (250600) | | $1.465,26 |
| **Scrittura contabile articolo 0021** | | | 
| Conto ricavi non fatturati (401250) | $274,74 | |
| Conto ricavi differiti (250600) | | $274,74 |
| **Fattura** | | |
| Conto ricavi non fatturati | | $1.465,26 |
| Conto ricavi non fatturati | | $274,74 |
| Conto contabilità clienti (130100) | $1.488,16 | |

#### <a name="changes-to-the-billing-schedule-line-billing-detail-line-or-revenue-allocation"></a>Modifiche alla riga del programma di fatturazione, alla riga dei dettagli di fatturazione o all'allocazione dei ricavi

Quando si modifica il prezzo unitario o la quantità, è necessario aggiornare l'importo dei ricavi di contratto per ogni articolo che fa parte dell'allocazione dei ricavi. Pertanto, la scrittura contabile viene ricalcolata.

Ad esempio, il prezzo unitario dell'articolo 1000 viene modificato da $1.500 a $1.600. In questo caso, l'importo dei ricavi del contratto viene ricalcolato automaticamente come $1.549,47. Il ricavo di contratto per l'articolo S0021 viene ricalcolato come $290,53.

Quando la modifica viene confermata, le scritture contabili iniziali per entrambi gli articoli vengono stornate e vengono create nuove scritture contabili:

- **Articolo 1000:** La scrittura contabile iniziale originale di $1.465,26 è stornata. Viene creata una nuova scrittura contabile per $1.549,47.
- **Articolo S0021:** La scrittura contabile iniziale originale di $274,74 è stornata. Viene creata una nuova scrittura contabile per $290,53.

#### <a name="termination"></a>Fine

L'articolo S0021 ha una data di inizio a gennaio 2020 e una data di fine a dicembre 2020, ma è terminato a giugno 2020. L'importo dei ricavi di contratto per entrambi gli articoli deve essere ricalcolato:

- **Articolo 1000:** Il ricavo di contratto viene ricalcolato come $1.567,67.
- **Articolo S0021:** Il ricavo di contratto viene ricalcolato come $124,00.

Viene creata una scrittura contabile di rettifica per la riga terminata. La scrittura contabile per la riga che appartiene allo stesso numero MEA (Multiple Element Arrangement) viene stornata e viene creata una nuova scrittura contabile:

- **Articolo 1000:** La scrittura contabile iniziale originale di $1.465,26 è stornata. Viene creata una scrittura contabile di modifica per $1.549,47.
- **Articolo S0021:** La scrittura contabile iniziale originale di $274,74 è stornata. Viene creata una nuova scrittura contabile per $124,00.
