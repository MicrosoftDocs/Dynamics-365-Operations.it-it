---
title: Migliorare le prestazioni di pianificazione generale
description: In questo argomento vengono illustrate le varie opzioni che consentono di migliorare le prestazioni di pianificazione generale o risolvere i problemi.
author: t-benebo
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 45e77ee43f6f96edb29924fc420172525e95e46f98f19177ba7253a2119db9ec
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717294"
---
# <a name="improve-master-planning-performance"></a>Migliorare le prestazioni di pianificazione generale

[!include [banner](../includes/banner.md)]

In questo argomento vengono illustrate le varie opzioni che consentono di migliorare le prestazioni di pianificazione generale o risolvere i problemi. Sono incluse informazioni su parametri e impostazioni, nonché su configurazioni e azioni consigliate. Inoltre è incluso un riepilogo di tutti i parametri importanti che è opportuno considerare in caso di processi di pianificazione generale a esecuzione prolungata.

Questo argomento è destinato agli amministratori di sistema o agli utenti IT che dispongono dei privilegi per risolvere i problemi. È inoltre destinato ai responsabili pianificazione forniture o produzione poiché include informazioni sui parametri correlati ai requisiti di pianificazione aziendale. 

## <a name="parameters-related-to-master-planning-performance"></a>Parametri relativi alle prestazioni di pianificazione generale

Diversi parametri influiscono sul tempo di esecuzione della pianificazione generale e devono quindi essere presi in considerazione.

### <a name="number-of-threads"></a>Numero di thread

Il parametro **Numero di thread** consente di rettificare il processo di programmazione generale per migliorare le prestazioni in relazione al set di dati specifico. Questo parametro indica il numero totale di thread che verranno utilizzati per eseguire la pianificazione generale. Provoca la parallelizzazione dell'esecuzione della pianificazione generale, che consente di diminuire il tempo di esecuzione. 

È possibile impostare il parametro **Numero di thread** nella finestra di dialogo **Esecuzione della pianificazione generale**. Per aprire questa finestra di dialogo, accedere a **Pianificazione generale \> Pianificazione generale \> Esegui \> Pianificazione generale** o selezionare **Esegui** nell'area di lavoro **Pianificazione generale** Per determinare il valore migliore per questo parametro, sarà necessario effettuare una serie di tentativi. Tuttavia, è possibile utilizzare le seguenti formule per calcolare un valore iniziale:

- **Se il proprio settore è quello manifatturiero:** (Numero di thread) = (Numero di ordini pianificati ÷ 1.000)
- **In caso contrario:** (Numero di thread) = (Numero di articoli ÷ 1.000)

Il numero di helper utilizzati durante la pianificazione generale deve essere inferiore o uguale al numero massimo di thread consentiti nel server batch. Se il numero di helper supera il numero di thread sul server batch, i thread in eccesso non eseguiranno alcun lavoro.

> [!NOTE]
> L'impostazione del parametro **Numero di thread** su **0** (zero) aumenta il tempo di esecuzione della pianificazione generale. Di conseguenza, è consigliabile impostare sempre un valore maggiore di 0.

### <a name="number-of-tasks-in-helper-task-bundle"></a>Numero di attività nell'aggregazione helper

Modificando l'impostazione **Numero di attività nell'aggregazione helper** (ovvero la dimensione di aggregazione), è possibile ridurre il tempo di esecuzione. Questa impostazione determina il numero di articoli pianificati da un unico helper.

È possibile impostare il parametro **Numero di attività nell'aggregazione helper** nella sezione **Prestazioni** della scheda **Generale** della pagina **Parametri di pianificazione generale** (**Pianificazione generale \> Impostazioni \> Parametri di pianificazione generale**). Il valore migliore per questo parametro dipende dai dati. Pertanto, si consiglia di iniziare con il valore **1** e quindi effettuare vari tentativi per determinare il miglior valore per l'impostazione.

In genere, è consigliabile aumentare il numero di attività quando il numero di articoli è molto grande (centinaia di migliaia). In caso contrario, è necessario ridurre il numero di attività. Per i seguenti specifici settori, considerare questi suggerimenti:

- Nei settori della vendita al dettaglio e della distribuzione, in cui sono presenti molti articoli indipendenti, utilizzare numerosi helper in quanto non vi sono dipendenze tra gli articoli. 
- Nel settore manifatturiero, in cui sono presenti numerose distinte base (DBA) e sottocomponenti condivisi, utilizzare meno helper, poiché le dipendenze tra gli articoli potrebbero generare tempi di attesa.

> [!TIP]
> In caso di problemi relativi alle prestazioni, è consigliabile impostare **Numero di attività nell'aggregazione helper** su **1**. È quindi possibile effettuare vari tentativi per determinare il migliore valore da impostare. In genere, i problemi relativi alle prestazioni si verificano quando l'elaborazione di un articolo richiede più tempo rispetto agli articoli rimanenti. In questo caso, si osserverà che l'esecuzione di due attività successive il cui stato è **Copertura** nell'esecuzione della pianificazione generale comporterà tempi significativamente differenti. In casi estremi, questa differenza può anche essere di 30 minuti. È possibile dedurre il tempo di esecuzione di quelle attività osservando la durata di ogni attività.

### <a name="use-of-cache"></a>Uso della cache

Il parametro **Uso della cache** consente di rettificare il processo di programmazione generale per migliorarne le prestazioni in relazione al set di dati specifico. Ad esempio, è possibile modificarlo per ottenere i seguenti risultati:

- Se si esegue una maggiore memorizzazione nella cache, più dati vengono raccolti nella memoria di dati. L'aspettativa è che i dati saranno utilizzati di nuovo in un secondo momento. Se i dati sono in memoria, si potrebbero salvare alcune richieste di database. Tuttavia, se si esegue una maggiore memorizzazione nella cache, i requisiti di memoria aumentano.
- Se si esegue una minore memorizzazione nella cache, è possibile che gli stessi dati debbano essere recuperati più spesso dal database. Inoltre, Server oggetti applicativi (AOS) archivia pochi dati in memoria durante il processo.

È difficile prevedere quale opzione sarà più appropriata poiché ogni caso non dipende solo dai dati ma anche dall'hardware. Ad esempio, poiché una minore memorizzazione nella cache genera un carico aggiuntivo sul server di database, probabilmente non è una buona idea utilizzare tale opzione se il server di database è già sovraccarico.

È possibile impostare il parametro **Uso della cache** nella sezione **Prestazioni** della scheda **Generale** della pagina **Parametri di pianificazione generale** (**Pianificazione generale \> Impostazioni \> Parametri di pianificazione generale**). L'efficacia della memorizzazione nella cache dipende fortemente dai dati del cliente. Ad esempio, se i dati nella cache non sono mai necessari, si ha uno spreco di memoria se si archiviano i dati fino alla fine del processo di programmazione. In tal caso, se si configura una minore memorizzazione nella cache, le prestazioni potrebbero migliorare poiché AOS richiede meno memoria e le risorse del server vengono liberate per altre attività.

> [!TIP]
> In genere è consigliabile impostare il parametro **Uso della cache** su **Massimo**, in quanto viene utilizzato per migliorare le prestazioni. Si consiglia di impostare il parametro su **Minimo** se si effettua l'esecuzione on premises e si dispone di memoria limitata (all'incirca 2 gigabyte \[GB\]).

### <a name="number-of-orders-in-firming-bundle"></a>Numero di ordini nell'aggregazione di stabilizzazione

Il parametro **Numero di ordini nell'aggregazione di stabilizzazione** specifica il numero totale di ordini che verranno elaborati contemporaneamente da ciascun thread/batch. Questo parametro genera la parallelizzazione del processo di stabilizzazione automatica.

È possibile impostare il parametro **Numero di ordini nell'aggregazione di stabilizzazione** nella sezione **Prestazioni** della scheda **Generale** della pagina **Parametri di pianificazione generale** (**Pianificazione generale \> Impostazioni \> Parametri di pianificazione generale**). La parallelizzazione del processo di stabilizzazione automatica si basa sugli ordini che devono essere elaborati insieme. Ad esempio, se questo parametro è **50**, ogni attività batch o thread selezionerà 50 ordini contemporaneamente e li elaborerà insieme. Si consiglia di effettuare vari tentativi per individuare il valore migliore. È tuttavia possibile utilizzare la seguente formula per calcolare un valore iniziale:

(Numero di ordini per aggregazione) = (Numero di articoli della domanda ÷ Numero di thread)

> [!NOTE]
> Se si imposta il parametro **Numero di ordini nell'aggregazione di stabilizzazione** su **0** (zero), non si verificherà la parallelizzazione del processo di stabilizzazione automatica. L'intero processo verrà eseguito su un'unica attività batch e avrà un tempo di esecuzione cumulativo. Di conseguenza, il tempo di esecuzione della pianificazione generale aumenterà. Per questo motivo, è consigliabile impostare questo parametro su un valore superiore a **0** (zero).

### <a name="time-fences"></a>Intervalli temporali

Gli intervalli temporali specificano fino a quando i calcoli e altri fabbisogni devono essere definiti mediante la pianificazione generale. Maggiore è l'intervallo temporale, più lunga sarà l'esecuzione della pianificazione generale. Di conseguenza, impostare gli intervalli temporali in base ai requisiti aziendali. Per ulteriori informazioni sugli intervalli temporali, vedere [Impostazione della pianificazione generale](master-planning-setup.md).

### <a name="actions"></a>Azioni

Tra gli intervalli temporali è anche possibile trovare il parametro **Messaggio d'azione**. Il calcolo dei messaggi d'azione genera un tempo di esecuzione più lungo per la pianificazione generale. Se i messaggi d'azione non sono analizzati e applicati regolarmente (giornalmente, settimanalmente e così via), valutare l'opportunità di disattivare il calcolo durante l'esecuzione della pianificazione generale. Per disattivare il calcolo, nella pagina **Piani generali** (**Pianificazione generale \> Imposta \> Piani \> Piani generali**), impostare l'intervallo temporale **Messaggio d'azione** su **0** (zero). Assicurarsi inoltre che l'impostazione **Messaggio d'azione** sia disattivata per tutti i gruppi di copertura.

### <a name="futures"></a>Ritardi

Il calcolo dei ritardi genera un tempo di esecuzione più lungo per la pianificazione generale. Se non si pianificano DBA, o se i ritardi non devono essere propagati dall'offerta alla domanda durante la pianificazione, valutare l'opportunità di disattivare i calcoli dei ritardi durante la pianificazione generale. Per disattivare i calcoli, impostare l'intervallo temporale **Ritardo** su **0** (zero) per il piano generale in esecuzione. Assicurarsi inoltre che l'impostazione **Ritardo** sia disattivata per tutti i gruppi di copertura.

## <a name="one-heavy-routine-at-a-time"></a>Una routine pesante alla volta

Quando si programma la pianificazione generale, non programmare un qualsiasi altro processo batch contemporaneamente. Prestare attenzione in particolare a non programmare contemporaneamente altre routine pesanti, ad esempio la chiusura inventario.

## <a name="review-the-session-log"></a>Esaminare il registro sessioni

Il sistema può raccogliere ulteriori informazioni sulle attività eseguite durante la pianificazione generale. Per consentire al sistema di raccogliere queste informazioni, attivare l'impostazione **Traccia ora di elaborazione** nella finestra di dialogo **Esecuzione della pianificazione generale**. Le informazioni raccolte sono utili per individuare colli di bottiglia nell'esecuzione. Ad esempio, quando il parametro **Numero di attività nell'aggregazione helper** è impostato su **1**, è possibile identificare l'articolo con il tempo di esecuzione più lungo. È inoltre possibile confrontare i tempi di esecuzione dei vari thread il cui stato è **Copertura** e confrontare la durata per ogni attività.

Per esaminare le esecuzioni della pianificazione generale del sistema, effettuare uno dei passaggi riportati di seguito.

- Nell'area di lavoro **Pianificazione generale**, selezionare un piano generale nel campo a discesa, quindi nel riquadro **Pianificazione generale** selezionare **Storico**. Selezionare un processo, selezionare **Informazioni** nella scheda dettaglio e selezionare **Durata attività di processo**.
- Nella pagina **Piani generali**, selezionare un piano nel riquadro sinistro e quindi **Storico** nella scheda dettaglio. Selezionare un processo, selezionare **Informazioni** nella scheda dettaglio e selezionare **Durata attività di processo**.

Quando si esamina il registro sessioni, considerare quanto segue:

- L'**aggiornamento** non dovrebbe richiedere molto tempo (non più di 30 minuti), tuttavia è un'operazione a thread singolo.
- La **copia del piano** non dovrebbe richiedere molto tempo (all'incirca un minuto).
- La **stabilizzazione automatica** in genere richiede all'incirca 30 minuti. Tuttavia, può durare varie ore, a seconda del numero di ordini e della complessità degli articoli.
- La **stabilizzazione automatica** dovrebbe richiedere meno tempo della **copertura**.
- L'esecuzione della **copertura** dovrebbe essere la più lunga rispetto al resto.
- L'**azione** e il **messaggio di ritardo** possono richiedere parecchio tempo, a seconda dei dati e del numero di DBA.

## <a name="filtering-of-items"></a>Filtro degli articoli

I filtri applicati nella finestra di dialogo **Esecuzione della pianificazione generale** influiscono sulla durata dell'esecuzione della pianificazione generale. Accedere a **Pianificazione generale \> Pianificazione generale \> Esegui \> Pianificazione generale** o selezionare **Esegui** nell'area di lavoro. **Pianificazione generale** Per escludere articoli dall'esecuzione, si consiglia di filtrare in base allo stato del ciclo di vita dell'articolo (e non per numero di articolo). Quando si filtra in base allo stato del ciclo di vita, il processo di aggiornamento richiederà meno tempo rispetto a quando si filtra in base al numero di articolo.

## <a name="automatically-filter-by-items-with-direct-demand"></a>Filtra automaticamente in base ad articoli con domanda diretta

Per migliorare il tempo di esecuzione della pianificazione generale, è possibile scegliere di includere solo articoli con domanda diretta. Questo filtro può essere utilizzato solo per un'esecuzione di pianificazione generale completa senza altri filtri applicati nel campo **Record da includere**. Un'esecuzione di pianificazione generale con filtri ignorerà l'impostazione **Filtra automaticamente in base ad articoli con domanda diretta**.

Il campo **Filtra automaticamente in base ad articoli con domanda diretta** si trova nella pagina **Parametri di pianificazione generale** e può essere utilizzato con entrambe le impostazioni di pre-elaborazione e post-elaborazione.

### <a name="pre-processing"></a>Pre-elaborazione
Il parametro **Pre-elaborazione. Filtra automaticamente in base ad articoli con domanda diretta** garantisce che la fase di pre-elaborazione della pianificazione generale includa solo gli articoli che soddisfano almeno una delle seguenti condizioni:
  - L'articolo presenta un problema o un'entrata prevista, ad esempio un ordine fornitore, un ordine cliente, un'offerta, un ordine di trasferimento o un ordine di produzione. 
  - L'articolo ha una copertura dell'articolo con scorte di sicurezza (livello minimo di scorte disponibili).
  - Esiste una previsione della domanda successiva alla data odierna per l'articolo.
  - Esiste una previsione dell'offerta successiva alla data odierna per l'articolo.
  - L'articolo include delle righe di continuità dal modulo servizio clienti ancora da creare.

> [!NOTE]
> Un articolo che ha scorte fisiche disponibili non mostrerà una transazione di fabbisogno poiché non c'è domanda per l'articolo.

### <a name="post-processing"></a>Post-elaborazione
L'opzione **Post-elaborazione. Filtra automaticamente in base ad articoli con domanda diretta** è rilevante solo se è stato impostato **Fabbisogno versione DBA** nei gruppi di copertura. Altrimenti, non è necessario abilitare il parametro. 

Prima dell'inizio della fase di copertura, è presente una fase di pre-copertura durante la quale gli articoli con l'impostazione di copertura **Fabbisogno versione DBA** abilitata verranno rielaborati. Questo viene fatto per garantire che siano pianificati gli articoli della versione DBA richiesta. Gli articoli che sono considerati con domanda durante la pre-elaborazione non hanno più alcuna domanda e pertanto devono essere esclusi dall'esecuzione della pianificazione.

## <a name="performance-checklist-summary"></a>Riepilogo dell'elenco di controllo delle prestazioni

- **Numero di thread** - Impostare un valore maggiore di **0** (zero).
- **Numero di attività nell'aggregazione helper** - Impostare un valore maggiore di **0** (zero) (utilizzare le formule fornite in precedenza in questo argomento).
- **Uso della cache** - Impostare su **Massimo** a meno che la memoria del sistema non sia quasi esaurita.
- **Numero di ordini nell'aggregazione di stabilizzazione** - Impostare su un valore maggiore di **0** (zero) (utilizzare la formula fornita in precedenza in questo argomento).
- **Intervalli temporali** - Regolare in base alle esigenze aziendali.
- **Azioni e ritardo** - Disabilitare le azioni e il ritardo se non vengono utilizzati.
- **Una routine pesante alla volta** - Non eseguire la pianificazione generale insieme a qualsiasi altra routine pesante.
- **Esaminare il registro sessioni**
- **Filtrare articoli** - Utilizzare lo stato del ciclo di vita per escludere articoli dall'esecuzione della pianificazione generale (non utilizzare numeri di articolo).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]