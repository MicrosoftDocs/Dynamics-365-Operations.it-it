---
title: Processi di importazione ed esportazione di dati
description: Utilizzare l'area di lavoro Gestione dati per creare e gestire i processi di importazione ed esportazione di dati.
author: Sunil-Garg
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 40bfc3f1f7c5fe1eec788d252cbe7be7d1c7536f
ms.openlocfilehash: 3bd6eaa0518bd4752704836c04457dccd486d692
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---

# <a name="data-import-and-export-jobs"></a>Processi di importazione ed esportazione di dati

[!include[banner](../includes/banner.md)]

Per creare e gestire i processi di importazione ed esportazione di dati in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition si utilizza l'area di lavoro **Gestione dati**. Per impostazione predefinita, il processo di importazione ed esportazione crea una tabella di gestione temporanea per ciascuna entità nel database di destinazione. Le tabelle di gestione temporanea consentono di verificare, pulire o convertire i dati prima di spostarli.

> [!NOTE]
> In questo argomento si presuppone di aver acquisito dimestichezza con l'argomento [entità di dati](data-entities.md).

## <a name="data-importexport-process"></a>Processo di importazione/esportazione di dati
Di seguito vengono riportati i passaggi per l'importazione o l'esportazione di dati.

1. Creare un processo di importazione o esportazione in cui completare le seguenti attività:

    - Definire la categoria del progetto.
    - Identificare le entità da importare o esportare.
    - Impostare il formato dei dati per il processo.
    - Sequenziare le entità di modo che vengano elaborate in gruppi logici e in un ordine significativo.
    - Determinare se utilizzare le tabelle di gestione temporanea.

2. Verificare che i dati di origine e i dati di destinazione siano mappati correttamente.
3. Verificare la protezione per il processo di importazione o esportazione.
4. Eseguire il processo di importazione o di esportazione.
5. Verificare che il processo sia stato eseguito come previsto esaminando lo storico processi.
6. Pulire le tabelle di gestione temporanea.

Le altre sezioni di questo argomento forniscono ulteriori dettagli su ogni fase del processo.

## <a name="create-an-import-or-export-job"></a>Creare un processo di importazione o di esportazione
Un processo di importazione o esportazione di dati può essere eseguito una sola volta oppure più volte.

### <a name="define-the-project-category"></a>Definire la categoria del progetto
Si consiglia di selezionare attentamente una categoria di progetto appropriata per il processo di esportazione o di importazione. Le categorie di progetto consentono di gestire i processi correlati.

### <a name="identify-the-entities-to-import-or-export"></a>Identificare le entità da importare o esportare
È possibile aggiungere specifiche entità a un processo di esportazione o di importazione oppure selezionare un modello da applicare. I modelli includono un elenco di entità in un processo. L'opzione **Applica modello** è disponibile dopo aver denominato e salvato il processo.

### <a name="set-the-data-format-for-the-job"></a>Impostare il formato dei dati per il processo
Quando si seleziona un'entità, è necessario selezionare il formato dei dati da esportare o importare. Si definiscono i formati utilizzando il riquadro **Impostazione origini dati**. Molte organizzazioni utilizzano i formati predefiniti inclusi nel set di dati dimostrativi. Di seguito è riportato un elenco di alcuni di questi formati:

- AX (per i dati da importare o esportare nello stesso formato utilizzato per Microsoft Dynamics 365 for Finance and Operations, Enterprise edition)
- ColonSeparated
- CSV
- Excel
- Pacchetto

### <a name="sequence-the-entities"></a>Sequenziare le entità
È possibile sequenziare le entità in un modello di dati o nei processi di importazione e esportazione. Quando si esegue un processo contenente più entità di dati, è necessario assicurarsi che le entità di dati siano sequenziate correttamente. Il sequenziamento delle entità deve essere eseguito in modo da poter risolvere qualsiasi dipendenza funzionale tra le entità. Se le entità non hanno dipendenze funzionali, possono essere programmate per l'importazione o l'esportazione parallela.

#### <a name="execution-units-levels-and-sequences"></a>Unità di esecuzione, livelli e sequenze
L'unità di esecuzione, il livello nell'unità di esecuzione e la sequenza di un'entità consentono di determinare l'ordine in cui i dati vengono esportati o importati.

- Le entità nelle differenti unità di esecuzione sono elaborate in parallelo.
- In ogni unità di esecuzione, le entità vengono elaborate in parallelo se hanno lo stesso livello.
- In ogni livello, le entità vengono elaborate in base al relativo numero di sequenza in tale livello.
- Dopo l'elaborazione di un livello, viene elaborato il livello successivo.

#### <a name="resequencing"></a>Risequenziamento
È possibile che si intenda sequenziare di nuovo le entità nelle situazioni seguenti:

- Se si utilizza un solo processo di dati per tutte le modifiche, è possibile utilizzare le opzioni di risequenziamento in modo da ottimizzare il tempo di esecuzione dell'intero processo. In questi casi, è possibile utilizzare l'unità di esecuzione per rappresentare il modulo, il livello per rappresentare l'area funzionale nel modulo e la sequenza per rappresentare l'entità. Utilizzando questo approccio, è possibile gestire i moduli in parallelo, ma anche in sequenza. Per assicurare una corretta esecuzione delle operazioni in parallelo, è necessario considerare tutte le dipendenze.
- Se si utilizzano più processi di dati (ad esempio un processo per ogni modulo), è possibile utilizzare il sequenziamento per modificare il livello e la sequenza delle entità per un'esecuzione ottimale.
- Se non vi sono dipendenze, è possibile sequenziare le entità in differenti unità di esecuzione per un'ottimizzazione massima.

Il menu **Risequenziamento** è disponibile quando si selezionano più entità. È possibile eseguire il risequenziamento in base alle opzioni relative a unità di esecuzione, livello o sequenza. È possibile impostare un incremento per il risequenziamento delle entità selezionate. L'unità, il livello e/o il numero di sequenza selezionato per ciascuna entità viene aggiornato in base all'incremento specificato.

#### <a name="sorting"></a>Ordinamento
È possibile utilizzare **Ordina per** per visualizzare l'elenco delle entità nell'ordine sequenziale.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Verificare che i dati di origine e i dati di destinazione siano mappati correttamente
Il mapping è una funzione disponibile per i processi di importazione e quelli di esportazione.

- Nel contesto di un processo di importazione, il mapping descrive quali colonne nel file di origine diventano colonne nella tabella di gestione temporanea. Di conseguenza, il sistema può determinare quale colonna di dati nel file di origine deve essere copiata in quale colonna della tabella di gestione temporanea.
- Nel contesto di un processo di esportazione, il mapping descrive quali colonne della tabella di gestione temporanea diventano le colonne nel file di origine.

Se i nomi di colonna nella tabella di gestione temporanea e nel file corrispondono, il sistema stabilisce automaticamente il mapping in base ai nomi. Tuttavia, se i nomi differiscono, le colonne non vengono mappate automaticamente. In questi casi, è necessario completare il mapping selezionando l'opzione **Visualizza mapping** per l'entità nel processo di dati.

Sono disponibili due visualizzazioni di mapping: **Visualizzazione mapping**, ovvero la visualizzazione predefinita, e **Dettagli mapping**. Un asterisco rosso (\*) identifica i campi obbligatori nell'entità. È necessario mappare questi campi per poter utilizzare l'entità. È possibile annullare il mapping di altri campi quando si utilizza l'entità. Per annullare il mapping di un campo, selezionare il campo nella colonna **Entità** o nella colonna **Origine** e quindi selezionare **Elimina la selezione**. Selezionare **Salva** per salvare le modifiche e chiudere la pagina per ritornare al progetto. È possibile utilizzare lo stesso processo per modificare il mapping da Origine a Gestione temporanea dopo l'importazione.

È possibile generare un mapping nella pagina selezionando **Genera mapping origine**. Il comportamento di un mapping generato è quello di un mapping automatico. Di conseguenza, è necessario mappare manualmente tutti i campi non mappati.

![Mapping dei dati](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Verificare la protezione per il processo di importazione o esportazione
L'accesso all'area di lavoro **Gestione dati** può essere limitato, di modo che gli utenti non amministratori possano accedere solo a specifici processi di dati. L'accesso a un processo di dati implica l'accesso completo allo storico esecuzione di quel processo e l'accesso alle tabelle di gestione temporanea. Di conseguenza, è necessario assicurarsi di aver implementato i controlli di accesso appropriati quando si crea un processo di dati.

### <a name="secure-a-job-by-roles-and-users"></a>Proteggere un processo in base a ruoli e utenti
Utilizzare il menu **Ruoli applicabili** per limitare l'accesso al processo a uno o più ruoli di sicurezza. Solo gli utenti con quei ruoli avranno accesso al processo.

È inoltre possibile limitare l'accesso a un processo a specifici utenti. Quando si protegge un processo in base agli utenti anziché ai ruoli, il livello di controllo è maggiore se molteplici utenti sono assegnati a un ruolo.

### <a name="secure-a-job-by-legal-entity"></a>Proteggere un processo in base alla persona giuridica
I processi di dati sono globali per natura. Di conseguenza, se un processo di dati è stato creato e utilizzato in una persona giuridica, il processo sarà visibile in altre persone giuridiche nel sistema. Questo comportamento predefinito potrebbe essere preferibile in alcuni scenari di applicazione. Ad esempio, un'organizzazione che importa fatture mediante entità di dati potrebbe fornire un team di elaborazione delle fatture centralizzato che è responsabile della gestione degli errori nelle fatture per tutti i reparti dell'organizzazione. In questo scenario, per il team di elaborazione delle fatture centralizzato è utile avere accesso a processi di importazione delle fatture di tutte le persone giuridiche. Di conseguenza, il comportamento predefinito soddisfa il requisito a livello di persona giuridica.

Tuttavia, un'organizzazione potrebbe necessitare di avere team di elaborazione delle fatture per entità giuridica. In tal caso, un team in una persona giuridica deve avere accesso solo al processo di importazione delle fatture nella relativa persona giuridica. Per soddisfare questo requisito, è possibile configurare il controllo dell'accesso basato sulle persone giuridiche nei processi di dati utilizzando il menu **Persone giuridiche applicabili** nel processo di dati. Dopo la configurazione, gli utenti possono visualizzare solo i processi disponibili nella persona giuridica a cui hanno correntemente accesso. Per visualizzare i processi di un'altra persona giuridica, gli utenti devono accedere a quella persona giuridica.

Un processo può essere protetto in base a ruoli, utenti e persone giuridiche contemporaneamente.

## <a name="run-the-import-or-export-job"></a>Eseguire il processo di importazione o di esportazione
È possibile eseguire un processo una volta facendo clic sul pulsante **Importa** o **Esporta** dopo aver definito il processo. Per impostare un processo ricorrente, selezionare **Crea processo dati ricorrente**.

## <a name="validate-that-the-job-ran-as-expected"></a>Verificare che il processo è stato eseguito come previsto
Lo storico processi è disponibile per la risoluzione dei problemi e l'analisi dei processi di importazione e di esportazione. Le esecuzioni dello storico processi sono organizzate in base a intervalli di tempo.

![Intervalli delle storico processi](./media/dixf-job-history.md.png)

Ogni esecuzione di processo fornisce i seguenti dettagli:

- Dettagli esecuzione
- Registro di esecuzione

I dettagli relativi all'esecuzione indicano lo stato di ciascuna entità di dati elaborata nel processo. Di conseguenza, è possibile trovare rapidamente le seguenti informazioni:

- Quali entità sono state elaborate
- Per un'entità, quanti record sono stati elaborati correttamente e quanti no
- I record di gestione temporanea per ogni entità

È possibile scaricare i dati di gestione temporanea in un file per i processi di esportazione, oppure scaricarlo come pacchetto per i processi di esportazione e importazione.

Dai dettagli di esecuzione è anche possibile aprire il registro di esecuzione.

## <a name="clean-up-the-staging-tables"></a>Pulire le tabelle di gestione temporanea
È possibile pulire le tabelle di gestione temporanea utilizzando la funzione **Pulizia gestione temporanea** nell'area di lavoro **Gestione dati**. È possibile utilizzare le seguenti opzioni per selezionare i record che devono essere eliminati dalla tabella di gestione temporanea:

- **Entità**: se si specifica una sola entità, vengono eliminati tutti i record della tabella di gestione temporanea di quell'entità. Selezionare questa opzione per pulire tutti i dati dell'entità in tutti i progetti di dati e in tutti i processi.
- **ID processo**: se si specifica un solo ID processo, vengono eliminati tutti i record di tutte le entità nel processo selezionato dalle tabelle di gestione temporanea appropriate.
- **Progetti dati**: se si seleziona un solo progetto di dati, vengono eliminati tutti i record di tutte le entità e in tutti i processi per il progetto di dati selezionato.

È anche possibile combinare le opzioni per definire ulteriormente il set di record da eliminare.

