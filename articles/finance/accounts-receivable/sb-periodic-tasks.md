---
title: Attività periodiche nella fatturazione del contratto ricorrente
description: Questo argomento descrive le attività periodiche disponibili in Fatturazione del contratto ricorrente.
author: JodiChristiansen
ms.date: 04/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 80f65d82881bb000f626c4225b3eac7dd1a2a44a
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786970"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>Attività periodiche nella fatturazione del contratto ricorrente

Questo argomento descrive le attività periodiche disponibili in Fatturazione del contratto ricorrente.

## <a name="generate-invoice"></a>Genera fattura

Utilizza la pagina **Genera fattura** per creare fatture mensili ricorrenti di massa in base alle informazioni impostate sulle pagine **Tutti i programmi di fatturazione** e **Visualizza i dettagli di fatturazione**. Quando viene creata una fattura, la descrizione dell'articolo per la riga di elaborazione dell'ordine cliente viene aggiornata con la descrizione dell'articolo e le date di inizio e fine fatturazione per la riga programmazione fatturata.

## <a name="generate-invoice-batch-processing"></a>Genera elaborazione batch fattura

Utilizza la pagina **Genera elaborazione batch fattura** per creare fatture ricorrenti tramite un processo batch ricorrente. I parametri disponibili sono gli stessi dei parametri della pagina **Genera fattura**, ma possono essere salvati in un processo batch che può essere eseguito più volte.

## <a name="price-update"></a>Aggiorna prezzo

Utilizza l'utilità di aggiornamento dei prezzi per aggiornare i prezzi di più articoli in più pianificazioni di fatturazione in un'unica azione. I prezzi possono essere aggiornati in base a una percentuale specificata o a un importo specifico. L'elenco delle righe mostra solo i prezzi unitari correnti degli articoli. Non mostra i prezzi dopo l'aggiornamento dei prezzi.

Tieni presente i seguenti punti sull'utilità di aggiornamento dei prezzi:

- Se l'ordine cliente per un anno specifico è già stato creato (ovvero gli articoli sono stati fatturati), il prezzo delle voci non viene influenzato.
- L'utilità di aggiornamento del prezzo può essere utilizzata per le voci con stato **Attivo** o **In attesa**. Per gli articoli in attesa, l'opzione **Regola la programmazione** deve essere stata impostata su **No** quando è stata impostata l'attesa.
- L'utilità di aggiornamento del prezzo non può essere utilizzata per le voci che sono articoli di utilizzo, che usano l'escalation, la fatturazione a fasi o la suddivisione dei ricavi.

### <a name="price-update-example"></a>Esempio di aggiornamento di prezzo

Viene creato un programma di fatturazione e viene aggiunto un articolo di rinnovo. Il prezzo unitario è 750 USD. Il primo anno dell'articolo viene pagato il 15 dicembre 2021. Il programma di fatturazione viene creato per il periodo di fatturazione dal 1 gennaio al 31 dicembre 2022.

Al momento del rinnovo, il processo **Genera fattura** crea l'ordine cliente per l'anno 2022. Dopo aver eseguito l'utilità di aggiornamento del prezzo, il prezzo viene aggiornato da 750 USD a 800 USD.

L'ordine cliente e il programma di fatturazione per il 2022 non sono interessati e il prezzo unitario rimane 750 USD, poiché il programma di fatturazione per il 2022 è già stato fatturato. La riga del programma di fatturazione e il dettaglio della riga per il 2023 vengono aggiornati a 800 USD, perché il programma di fatturazione per il 2023 non è stato ancora fatturato.

### <a name="update-prices--flat-pricing-method"></a>Aggiornare i prezzi: metodo di determinazione del prezzo forfettario

Quando aggiorni i prezzi per gli articoli che utilizzano il metodo di determinazione del prezzo forfettario, puoi specificare una percentuale o un importo per aumentare il prezzo.

Per eseguire l'utilità di aggiornamento del prezzo per gli articoli che utilizzano il metodo di determinazione del prezzo forfettario, attieniti alla seguente procedura.

1. Sulla pagina dell'utilità **Aggiornamento prezzi** seleziona il medoto di determinazione prezzi **Forfettario**.
2. Nel campo **Metodo incremento**, seleziona il metodo di incremento utilizzato per aggiornare il prezzo degli articoli.
3. A seconda del metodo di incremento selezionato, specifica la percentuale nel campo **Percentuale** o l'importo nel campo **Quantità**.
4. Sulla Scheda dettaglio **Record da includere** usa il pulsante **Filtro** per aggiungere filtri dati.
5. Seleziona **Visualizza anteprima** per visualizzare l'intervallo dei record.
6. Se non vuoi elaborare alcune delle righe, contrassegnale, quindi seleziona **Rimuovi**.
7. Seleziona **OK**.

### <a name="update-prices--standard-pricing-method"></a>Aggiornare i prezzi: metodo di determinazione del prezzo standard

Se il prezzo di un articolo è stato modificato nel record dell'articolo, può essere aggiornato per tutte le righe programma di fatturazione se l'articolo utilizza il metodo di determinazione del prezzo standard.

1. Sulla pagina dell'utilità **Aggiornamento prezzi** seleziona il medoto di determinazione prezzi **Standard**.
2. Sulla Scheda dettaglio **Record da includere** usa il pulsante **Filtro** per aggiungere filtri dati.
3. Seleziona **Visualizza anteprima** per visualizzare l'intervallo dei record.
4. Se non vuoi elaborare alcune delle righe, contrassegnale, quindi seleziona **Rimuovi**.
5. Seleziona **OK**.

## <a name="mass-hold-processing"></a>Elaborazione attesa di massa

Utilizza la pagina **attesa di massa** per applicare le opzioni di attesa a più programmazioni di fatturazione contemporaneamente.

Per mettere in attesa solo un programma di fatturazione o una riga del programma di fatturazione, apri la pagina **Tutti i programmi di fatturazione** e seleziona **Metti in attesa**. Per rimuovere un'attesa, utilizza la pagina **Rimuovi attesa**.

### <a name="put-billing-schedules-on-hold"></a>Mettere le programmazioni fatturazione in attesa

Per mettere in attesa diversi programmi di fatturazione, attieniti a questa procedura.

1. Sulla pagina **attesa di massa**, imposta il campo **Opzione di processo** su **Applica attesa**.
2. Seleziona un codice motivo nel campo **Codice motivo**.
3. Imposta l'opzione **Regola la programmazione**:

    - **Sì** – Se si imposta l'opzione su **sì**, specificauna data di attesa nel campo **Data di attesa**. Eventuali righe di programmazione di fatturazione successive alla data di sospensione vengono rimosse.
    - **No** – Le righe del programma di fatturazione non vengono modificate. Solo lo stato viene modificato. È aggiornato su **In attesa**.

4. Sulla Scheda dettaglio **Record da includere** usa il pulsante **Filtro** per aggiungere filtri dati.
5. Seleziona **Visualizza anteprima** per visualizzare l'intervallo dei record.
6. Se non vuoi elaborare alcune delle righe, contrassegnale, quindi seleziona **Rimuovi**.
7. Seleziona **OK**.

Quando torni all'elenco delle programmazioni di fatturazione, dovresti vedere che lo stato delle programmazioni di fatturazione è stato modificato su **In attesa**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>Rimuovere un'attesa da diverse programmazioni di fatturazione

1. Sulla pagina **attesa di massa**, imposta il campo **Opzione di processo** su **Rimuovi attesa**.
2. Immetti un codice motivo nel campo **Codice motivo**.
3. Nel campo **Data rimozione** seleziona la data in cui l'attesa deve essere rimossa.
4. Imposta i campi **Data di ripresa** e **Data di differimento** come richiesto. La data di differimento viene aggiunta in tutte le righe che sono differibili.
5. Sulla Scheda dettaglio **Record da includere** usa il pulsante **Filtro** per aggiungere filtri dati.
6. Seleziona **Visualizza anteprima** per visualizzare l'intervallo dei record.
7. Se non vuoi elaborare alcune delle righe, contrassegnale, quindi seleziona **Rimuovi**.
8. Seleziona **OK**.

> [!NOTE]
> Per rimuovere un'attesa, è necessario impostare il valore **Sostituzione gruppo di utenti rimozione attesa** della pagina **Parametri di fatturazione contratto ricorrente**.

Ad esempio, una riga di fatturazione ha una data di inizio del 1 febbraio 2022 e una data di fine del 28 febbraio 2022. L'importo di fatturazione è 200 USD. Il campo **Data di attesa** è fissato al 10 febbraio 2022. Pertanto, il periodo di febbraio viene rettificato per escludere qualsiasi data successiva al 10 febbraio. Il nuovo periodo va dal 1 febbraio al 9 febbraio e l'importo è 64,29 USD (tramite la ripartizione giornaliera). Tutte le righe del programma di fatturazione a partire dal 10 febbraio vengono rimosse.

Se il processo **Rimuovi attesa** è completato e il campo **Data rimozione** è impostato per il 10 febbraio 2022, ci saranno due periodi di fatturazione. Il primo periodo va dal 1 febbraio al 9 febbraio e l'importo è 64,29 USD. Il secondo periodo va dal 10 febbraio al 28 febbraio e l'importo è 135,71 USD.

## <a name="mass-termination-processing"></a>Elaborazione terminazione di massa

Utilizza la pagina **Terminazione di massa** per terminare le righe del programma di fatturazione attualmente visualizzate specificando una data di scadenza.

Se stai utilizzando differimenti di ricavi e spese, i programmi di fatturazione in cui il campo **Data di terminazione** è impostato su **Regola programmazione** sulla pagina **Tutte le programmazioni fatturazione** possono beneficiare di un rimborso.

Le programmazioni di fatturazione che utilizzano la funzionalità di allocazione di elementi multipli (MEA) non vengono visualizzate nella pagina **Terminazione di massa**. Puoi comunque terminare una singola programmazione di fatturazione utilizzando la funzionalità di terminazione nella programmazione di fatturazione.

> [!NOTE]
> Le righe programma di fatturazione attualmente incluse in un batch **Genera fattura** non sono disponibili per questo processo.

Per informazioni su ciascun campo e il processo, vedi [Terminare le programmazioni di fatturazione](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>Processo di archiviazione di massa

Utilizza la pagina **Archiviazione di massa** per archiviare più programmazioni di fatturazione. È possibile archiviare solo le programmazioni di fatturazione terminate.

Dopo che una programmazione di fatturazione è stata archiviata, si verificano i seguenti eventi:

- Lo stato viene impostato su **Archiviato**.
- Le programmazioni di fatturazione sono bloccate in modo permanente.
- Le righe programma di fatturazione non sono più disponibili nelle pagine di richiesta informazioni.

> [!NOTE]
> L'archiviazione di una programmazione di fatturazione è un'azione permanente e non può essere annullata.

Per archiviare le programmazioni di fatturazione, attieniti a questa procedura.

1. Sulla pagina **Archiviazione di massa** nel campo **Data di fine fatturazione** specifica una data di fine fatturazione. Per visualizzare tutte le programmazioni di fatturazione terminate, lascia vuoto questo campo.
2. Nella Scheda dettaglio **Record da includere**, utilizza il pulsante **Filtro** per limitare i record visualizzati.
3. Seleziona **Visualizza anteprima**.
4. Se non vuoi archiviare alcuni record, contrassegnali, quindi seleziona **Rimuovi**.
5. Seleziona **OK** per archiviare i record nella pagina.

## <a name="mass-stubbing-process"></a>Processo di stub di massa

Utilizza la pagina **Stub di massa** per contrassegnare tutte le righe del programma di fatturazione selezionate come fatturate (stub) o non fatturate (storna stub). Lo stub o lo storno stub vengono spesso eseguiti su righe di programmazione di fatturazione importate che erano state precedentemente fatturate in un altro sistema. Le righe programmazione di fatturazione stub vengono visualizzate come stub e non creeranno una fattura per il cliente.

### <a name="stub-records"></a>Record di stub

1. Sulla pagina **Stub di massa** nel campo **Opzioni di processo** seleziona **Stub**.
2. Nel campo **Data limite** imposta una data limite per specificare le righe a cui vuoi applicare il processo. Verranno mostrati solo i record in cui la data di inizio della fatturazione è uguale o anteriore alla data limite specificata.
3. Seleziona **Visualizza anteprima** per mostrare le righe che vuoi sottoporre a stub.
4. Per escludere una riga dal processo, contrassegnala e quindi seleziona **Rimuovi**.
5. Seleziona **Elabora** per avviare il processo di stub delle righe.

### <a name="reverse-stub-records"></a>Record di storno stub

1. Sulla pagina **Stub di massa** nel campo **Opzioni di processo** seleziona **Storna stub**.
2. Nel campo **Data limite** imposta una data limite per specificare le righe a cui vuoi applicare il processo. Verranno mostrati solo i record in cui la data di inizio della fatturazione è uguale o anteriore alla data limite specificata.
3. Seleziona **Visualizza anteprima** per mostrare le righe che vuoi sottoporre allo storno dello stub.
4. Per escludere una riga dal processo, contrassegnala e quindi seleziona **Rimuovi**.
5. Seleziona **Elabora** per avviare il processo di storno stub delle righe.

## <a name="update-completion-date-process"></a>Aggiorna processo data di completamento

Utilizza la pagina **Aggiorna data di completamento** per aggiornare la data di completamento per passaggi fondamentali specifici per più programmazioni di fatturazione o utenti. Puoi anche aggiornare la percentuale di completamento per gli articoli nei modelli di passaggio fondamentale che utilizzano il metodo **Percentuale completamento**.

1. Sulla pagina **Aggiorna data di completamento** vai a **Elaborazione fasi** e seleziona **Aggiorna percentuale di completamento**.
2. Nel campo **Importo percentuale** immetti la percentuale totale che è stata completata.
3. Seleziona il numero di articolo associato al modello di passaggio fondamentale.
4. Nella Scheda dettaglio **Record da includere** seleziona **Filtro** per selezionare uno specifico valore **Account utente finale**, **Numero programma di fatturazione**, o **Numeri di articolo** come criterio di filtro.
5. Seleziona **OK** per elaborare la modifica. Quando l'elaborazione è completata, una nuova riga viene aggiunta all'allocazione del passaggio fondamentale. Questa riga rappresenta la percentuale che è stata completata per il modello di passaggio fondamentale.

## <a name="unbilled-revenue-mass-processing"></a>Elaborazione di massa ricavi non fatturati

Utilizza la pagina **Elaborazione di massa ricavi non fatturati** per creare la scrittura contabile ricavi non fatturati o eseguire lo stub della scrittura contabile per uno o più programmi di fatturazione o righe dettagli fatturazione selezionati.

- **Crea una scrittura contabile** – Crea scritture contabili ricavi non fatturati per più righe programma di fatturazione. Utilizza il pulsante **Filtro** nella Scheda dettaglio **Record da includere** per selezionare l'intervallo di record visualizzati nell'elenco. L'elenco mostra solo le righe programma di fatturazione per le quali non sono state create scritture contabili ricavi non fatturati. Vengono create le scritture contabili iniziali. Per gli articoli di differimento vengono create anche le programmazioni differimento.
- **Scrittura contabile stub** – Contrassegna le righe del programma di fatturazione per le quali sono già state create le scritture contabili non fatturate. Questa opzione viene utilizzata se la scrittura contabile non fatturata è stata già registrata in un altro sistema. Contrassegna il giornale di registrazione ricavi non fatturati come stub e non registra una transazione nella contabilità generale.
- **Scrittura contabile storno stub** – Le scritture contabili storno stub che sono state elaborate. Se è stato commesso un errore durante l'elaborazione per **Scrittura contabile stub**, questa opzione deseleziona la casella di controllo **Sottoposto a stub** per la riga del programma di fatturazione.
- **Riga dettaglio fatturazione stub** – Utilizza questo processo quando i ricavi non fatturati sono stati elaborati in un sistema esterno e alcune righe dei dettagli di fatturazione sono già state fatturate. Questo processo garantirà che l'importo corretto appaia nei conti dei ricavi non fatturati.
- **Storna riga dettagli di fatturazione stub** – Storna qualsiasi azione **Riga dettagli di fatturazione stub**.

Il campo **Nome giornale di registrazione** viene utilizzato per registrare **Crea scrittura contabile** nella contabilità generale.

> [!NOTE]
> Il processo di stub non registra gli importi nella contabilità generale. Il campo **Nome giornale di registrazione** non è disponibile per tutti i processi di stub e storno stub.

### <a name="unbilled-revenue-stub-example"></a>Esempio di stub ricavi non fatturati

Un programma di fatturazione è impostato per un anno, da ottobre 2021 a settembre 2022. I ricavi non fatturati sono stati già elaborati in un sistema esterno. Nove mesi della programmazione di fatturazione sono già stati fatturati. L'importo per ogni periodo di fatturazione è di 250 USD. All'inizio dell'anno, l'importo totale registrato per i ricavi non fatturati è 3.000 USD. Dopo nove mesi, 2.250 USD sono già stati fatturati e 750 USD dei ricavi non fatturati è la rimanenza.

Per impostare la programmazione di fatturazione in cui rimangono solo tre mesi di ricavi non fatturati, attieniti alla seguente procedura.

1. Sulla pagina **Visualizza dettagli di fatturazione** crea una programmazione di fatturazione per il periodo da ottobre 2021 a settembre 2022, numero articolo S0001 e un importo di 250 USD al mese.
2. Seleziona **Crea scrittura contabile** per la programmazione di fatturazione. L'importo di 3.000 USD viene registrato nei ricavi non fatturati.
3. Seleziona **Riga dettagli di fatturazione stub** e specifica la data di transazione giugno 2022 (nove mesi). Le righe del programma di fatturazione non verranno visualizzate nell'anteprima. Le righe interessate si basano sulla data della transazione.
4. Seleziona **OK**.

I primi nove mesi che sono stati fatturati sono stati sottoposti a stub.

[![Visualizza righe dettagli di fatturazione stub.](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

L'importo di 3.000 USD viene stornato dai ricavi non fatturati e i 750 USD dei ricavi non fatturati rimanenti vengono registrati. Per visualizzare le registrazioni dei ricavi non fatturati, seleziona **Controllo scrittura contabile ricavi non fatturati** nella scheda **Rinnovi** della pagina dei dettagli della riga.

[![Controllo scrittura contabile ricavi non fatturati.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> La scrittura contabile ricavi non fatturati può essere creata per qualsiasi periodo di rinnovo, a condizione che tutte le righe dei dettagli di fatturazione del periodo precedente siano state fatturate. Ad esempio, una riga di pianificazione di fatturazione ha una frequenza di fatturazione mensile per un periodo di 12 mesi, da gennaio a dicembre 2021. La riga ha tre termini: il termine iniziale, un secondo termine (da gennaio a dicembre 2022) e un terzo termine (da gennaio a dicembre 2023). Dopo aver creato la fattura per tutte le righe dei dettagli di fatturazione dei primi 12 mesi nel 2021, è possibile creare la scrittura contabile per i ricavi non fatturati per il secondo termine.
>
> Per gli articoli di differimento che utilizzano la funzione ricavi non fatturati, vengono elaborate la riga di fatturazione e le righe di sconto. Per questi articoli vengono create la scrittura contabile ricavi non fatturati e la programmazione di differimento per la riga di fatturazione e la riga di sconto.
>
> Le scritture contabili create per gli articoli non differibili e gli articoli differibili registrano un credito in diversi conti ricavi.
