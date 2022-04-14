---
title: Impostazione della previsione della domanda
description: In questo argomento vengono descritte le attività di impostazione che è necessario eseguire per la preparazione delle previsioni della domanda.
author: t-benebo
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b52b970a8040dcba5a1fc59d297dc9ce1a3c53
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470011"
---
# <a name="demand-forecasting-setup"></a>Impostazione della previsione della domanda

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come impostare la previsione della domanda.  

## <a name="item-allocation-keys"></a>Chiavi di allocazione articoli

Le chiavi di allocazione articoli stabiliscono gruppi di articoli. Una previsione della domanda viene calcolata per un articolo e le relative dimensioni solo se l'articolo fa parte di una chiave di allocazione articolo. Questa regola viene applicata per raggruppare numerosi articoli, in modo da consentire una creazione più rapida delle previsioni della domanda. Le previsioni vengono create solo in base ai dati storici.

Un articolo e le relative dimensioni devono essere parte solo di una chiave di allocazione articolo se la chiave di allocazione articolo viene utilizzata durante la creazione della previsione.

Per creare chiavi di allocazione articoli e aggiungervi un'unità di stockkeeping, segui questi passaggi.

1. Vai a **Pianificazione generale \> Impostazioni \> Previsione della domanda \> Chiavi di allocazione articoli**.
1. Seleziona una chiave di allocazione articoli nel riquadro dell'elenco oppure seleziona **Nuovo** nel riquadro azioni per crearne una nuova. Nell'intestazione della chiave nuova o selezionata, imposta i seguenti campi:

    - **Chiave di allocazione articoli** – Immetti un nome univoco per la chiave.
    - **Nome** – Immettere un nome descrittivo per la chiave.

1. Segui uno di questi passaggi per aggiungere articoli alla chiave di allocazione articoli selezionata o rimuovere articoli:

    - Nella scheda dettaglio **Allocazione articoli**, utilizza i pulsanti **Nuovo** ed **Elimina** nella barra degli strumenti per aggiungere o rimuovere articoli come necessario. Per ogni riga, seleziona il numero dell'articolo, quindi assegna i valori delle dimensioni nelle altre colonne in base alle tue esigenze. Seleziona **Visualizza dimensioni** sulla barra degli strumenti per modificare il set di colonne delle dimensioni visualizzato nella griglia. Il valore della colonna **Percentuale** viene ignorata quando vengono generate le previsioni della domanda.
    - Se desideri aggiungere un numero elevato di articoli alla chiave, seleziona **Assegna articoli** nel riquadro azioni per aprire una pagina in cui è possibile trovare e assegnare più articoli alla chiave selezionata.

> [!IMPORTANT]
> Fai attenzione a includere solo gli articoli rilevanti in ciascuna chiave di allocazione articoli. Gli articoli non necessari possono determinare un aumento nei costi quando si utilizza Microsoft Azure Machine Learning.

## <a name="intercompany-planning-groups"></a>Gruppi di pianificazione interaziendale

Le previsioni della domanda possono generare previsioni interaziendali. In Dynamics 365 Supply Chain Management, le società pianificate insieme vengono raggruppate nello stesso gruppo di pianificazione interaziendale. Per specificare, per società, quali chiavi di allocazione articoli devono essere considerate per la previsione della domanda, associa una chiave di allocazione articoli al membro del gruppo di pianificazione interaziendale.

> [!IMPORTANT]
> Ottimizzazione pianificazione attualmente non supporta i gruppi di pianificazione interaziendali. Per eseguire la pianificazione interaziendale che utilizza Ottimizzazione pianificazione, imposta i processi batch di pianificazione generale che includano piani principali per tutte le società rilevanti.

Per configurare i gruppi di pianificazione interaziendali procedi come descritto di seguito.

1. Vai a **Pianificazione generale \> Impostazioni \> Gruppi di pianificazione interaziendale**.
1. Seleziona un gruppo di pianificazione nel riquadro dell'elenco oppure seleziona **Nuovo** nel riquadro azioni per creare uno nuovo. Nell'intestazione del gruppo nuovo o selezionato, imposta i seguenti campi:

    - **Nome** - Immetti un nome univoco per il gruppo di pianificazione.
    - **Descrizione** - Immetti una breve descrizione del gruppo di pianificazione.

1. Nella scheda dettaglio **Membri del gruppo di pianificazione interaziendale** utilizza i pulsanti sulla barra degli strumenti per aggiungere una riga per ogni società (persona giuridica) che deve far parte del gruppo. Per ciascuna riga, imposta i seguenti campi:

    - **Persona giuridica** – Seleziona il nome di una società (persona giuridica) membro del gruppo selezionato.
    - **Sequenza di pianificazione** – Assegna l'ordine in cui la società deve essere elaborata rispetto ad altre società. I valori bassi vengono elaborati per primi. Questo ordine può essere importante quando la domanda di una società interessa altre società. In questi casi, l'azienda che fornisce la domanda dovrebbe essere elaborata per ultima.
    - **Piano generale** - Seleziona il piano generale da attivare per la società corrente.
    - **Copia automatica su piano statico** – Seleziona questa casella di controllo per copiare il risultato del piano nel piano statico.
    - **Copia automatica su piano dinamico** – Seleziona questa casella di controllo per copiare il risultato del piano nel piano dinamico.

1. Per impostazione predefinita, se nessuna chiave di allocazione articolo è assegnata ai membri del gruppo di pianificazione interaziendale, una previsione della domanda viene calcolata per tutti gli articoli assegnati a tutte le chiavi di allocazione articolo da tutte le società. Ulteriori opzioni di filtro per le aziende e le chiavi di allocazione articoli sono disponibili nella finestra di dialogo **Genera previsione di base statistica** (**Pianificazione generale \> Previsione \> Previsione della domanda \> Genera previsione di base statistica**). Per assegnare chiavi di allocazione articoli a una società nel gruppo di pianificazione interaziendale selezionato, seleziona la società, quindi, nella scheda dettaglio **Membri del gruppo di pianificazione interaziendale** seleziona **Chiavi di allocazione articoli** sulla barra degli strumenti.

> [!IMPORTANT]
> Fai attenzione a includere solo le chiavi di allocazione articoli rilevanti in ciascun gruppo di pianificazione interaziendale. Gli articoli non necessari possono determinare un aumento nei costi quando si utilizza Azure Machine Learning.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>Impostare i parametri della previsione della domanda

Utilizza la pagina **Parametri di previsione della domanda** per impostare diverse opzioni che controllano come funziona la previsione della domanda nel tuo sistema.

### <a name="open-the-demand-forecasting-parameters-page"></a>Aprire la pagina dei parametri della previsione della domanda

Per impostare i parametri di previsione della domanda, vai a **Pianificazione generale \> Impostazioni \> Previsione della domanda \> Parametri di previsione della domanda**. Poiché le previsioni della domanda vengono eseguite a livello interaziendale, l'impostazione è globale. Ovvero si applica a tutte le persone giuridiche (società).

### <a name="general-settings"></a>Impostazioni generali

Utilizza la scheda **Generale** della pagina **Parametri di previsione della domanda** per definire le impostazioni generali per la previsione della domanda.

#### <a name="demand-forecast-unit"></a>Unità previsione domanda

La previsione della domanda genera la previsione in quantità. Di conseguenza, l'unità di misura in cui la quantità deve essere espressa deve essere specificata nel campo **Unità previsione domanda**. Questo campo definisce l'unità che verrà utilizzata per tutte le previsioni della domanda, indipendentemente dalle solite unità di magazzino per ogni prodotto. L'uso di un'unità di previsione coerente garantisce che l'aggregazione e la percentuale di distribuzione siano appropriate. Per ulteriori informazioni su aggregazione e percentuale di distribuzione, vedere [Effettuare correzioni manuali alla previsione di base](manual-adjustments-baseline-forecast.md).

Per ciascuna unità di misura utilizzata per le SKU incluse nella previsione della domanda, assicurati che sia presente una regola di conversione per l'unità di misura e l'unità di misura della previsione generale selezionata. Durante la generazione della previsione, viene registrato l'elenco di articoli che non dispongono di una conversione dell'unità di misura. Pertanto, è possibile correggere facilmente l'impostazione. Per altre informazioni su come creare unità di misura e come convertirle, vedi [Gestire unità di misura](../pim/tasks/manage-unit-measure.md).

#### <a name="transaction-types"></a>Tipi di transazione

Usa i campi della scheda dettaglio **Tipi di transazione** per selezionare i tipi di transazione utilizzati quando viene generata la previsione di base statistica.

Le previsioni della domanda possono essere utilizzate per prevedere la domanda dipendente e indipendente. Ad esempio, se solo l'opzione **Ordine cliente** è impostata su *Sì* e tutti gli articoli che vengono considerati per la previsione della domanda sono articoli venduti, il sistema calcolerà la domanda indipendente. Tuttavia, i sottocomponenti critici possono essere aggiunti alle chiavi di allocazione articolo e inclusi nelle previsioni della domanda. In questo caso, se l'opzione **Riga produzione** è impostata su *Sì*, viene calcolata una previsione dipendente.

È possibile sostituire i tipi di transazione per una o più chiavi di allocazione articoli specifiche utilizzando la scheda **Chiavi di allocazione articoli**. Questa scheda fornisce campi simili.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>Scegliere come creare la previsione di base

Il campo **Strategia di generazione delle previsioni** consente di selezionare il metodo utilizzato per creare una previsione di base. Sono disponibili tre metodi:

- *Copia della domanda storica* – Crea previsioni semplicemente copiando i dati storici.
- *Servizio Azure Machine Learning* – Usa un modello di previsione che utilizza il servizio Azure Machine Learning. Il servizio Azure Machine Learning è l'attuale soluzione di Machine Learning per Azure. Pertanto, ti consigliamo di utilizzarlo se vuoi usare un modello di previsione.
- *Azure Machine Learning* – Usa un modello di previsione che utilizza Azure Machine Learning Studio (classico). Azure Machine Learning Studio (classico) è stato deprecato e verrà presto rimosso da Azure. Pertanto, ti consigliamo di selezionare *Servizio Azure Machine Learning* se stai impostando la previsione della domanda per la prima volta. Se stai usando Azure Machine Learning Studio (classico), dovresti pianificare di passare al servizio Azure Machine Learning il prima possibile.

È possibile sostituire il metodo di generazione della previsione per una o più chiavi di allocazione articoli specifiche utilizzando la scheda **Chiavi di allocazione articoli**. Questa scheda fornisce campi simili.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>Sostituire i parametri dell'algoritmo di previsione predefinito a livello globale

I parametri e i valori predefiniti dell'algoritmo di previsione sono assegnati nella pagina **Parametri di previsione della domanda** (**Pianificazione generale \> Impostazioni \> Previsione della domanda \> Parametri di previsione della domanda**). Tuttavia, puoi sostituirli globalmente usando la scheda dettaglio **Parametri dell'algoritmo di previsione** nella scheda **Generale** della pagina **Parametri di previsione della domanda**. Puoi anche sostituirli per chiavi di allocazione specifiche usando la scheda **Chiavi di allocazione articoli** della pagina **Parametri di previsione della domanda**.

Utilizza i pulsanti **Aggiungi** e **Rimuovi** sulla barra degli strumenti per stabilire la raccolta di parametri sostituiti. Per ogni parametro nell'elenco, seleziona un valore nel campo **Nome** e quindi immetti un valore appropriato nel campo **Valore**. Tutti i parametri che non sono elencati qui prenderanno i loro valori dalle impostazioni della pagina **Parametri di previsione della domanda**. Per ulteriori informazioni su come utilizzare il set di parametri standard e selezionarne i valori, vedi la sezione [Parametri e valori predefiniti per i modelli di previsione della domanda](#model-parameters).

### <a name="set-forecast-dimensions"></a>Impostare le dimensioni di previsione

Una dimensione di previsione indica il livello di dettaglio per cui la previsione è definita. Società, sito e chiave di allocazione articoli sono dimensioni di previsione obbligatorie. Puoi anche generare le previsioni a livello di dimensioni di magazzino, stato inventario, gruppo clienti, conto cliente, paese/area geografica, stato e/o articolo oltre a tutti i livelli di dimensione articolo. Usa la scheda **Dimensioni previsione** della pagina **Parametri di previsione della domanda** per selezionare il set di dimensioni di previsione da utilizzare quando la previsione della domanda viene generata.

In qualsiasi momento, è possibile aggiungere le dimensioni di previsione all'elenco delle dimensioni utilizzate per previsione della domanda. È anche possibile eliminare una dimensione previsione dall'elenco. Tuttavia, le correzioni manuali vengono perse se si aggiunge o rimuove una dimensione previsione.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>Impostare sostituzioni per chiavi di allocazione articoli specifiche

Non tutti gli articoli si comportano nello stesso modo da un punto di vista della previsione della domanda. Pertanto, è possibile stabilire sostituzioni specifiche della chiave di allocazione per la maggior parte delle impostazioni definite nella scheda **Generale**. L'eccezione è l'unità di previsione della domanda. Per impostare le sostituzioni per una chiave di allocazione articoli specifica, segui questi passaggi.

1. Nella pagina **Parametri di previsione della domanda** nella scheda **Chiavi di allocazione articoli** utilizza i pulsanti della barra degli strumenti per aggiungere le chiavi di allocazione articoli alla griglia a sinistra o per rimuoverle, come necessario. Quindi seleziona la chiave di allocazione per la quale desideri impostare le sostituzioni.
1. Nella scheda dettaglio **Tipi di transazione** abilita i tipi di transazioni che vuoi utilizzare per generare la previsione di base statistica per i prodotti che appartengono alla chiave di allocazione selezionata. Le impostazioni funzionano come nella scheda **Generale** ma si applicano solo alla chiave di allocazione articolo selezionata. Tutte le impostazioni qui (entrambi i valori *sì* e *no*) sostituiscono tutte le impostazioni **Tipi di transazione** della scheda **Generale**.
1. Nella scheda dettaglio **Parametri dell'algoritmo di previsione** seleziona la strategia di generazione della previsione e le sostituzioni dei parametri dell'algoritmo di previsione per i prodotti che appartengono alla chiave di allocazione selezionata. Queste impostazioni funzionano come nella scheda **Generale** ma si applicano solo alla chiave di allocazione articolo selezionata. Utilizza i pulsanti **Aggiungi** e **Rimuovi** sulla barra degli strumenti per definire la raccolta di parametri sostituiti. Per ogni parametro nell'elenco, seleziona un valore nel campo **Nome** e quindi immetti un valore appropriato nel campo **Valore**. Per ulteriori informazioni su come utilizzare il set di parametri standard e selezionarne i valori, vedi la sezione [Parametri e valori predefiniti per i modelli di previsione della domanda](#model-parameters).

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Configurare la connessione al servizio Azure Machine Learning

Utilizza la scheda **Servizio Azure Machine Learning** per configurare la connessione al servizio Azure Machine Learning. Questa soluzione è una delle opzioni per creare la previsione di base. Le impostazioni in questa scheda hanno effetto solo quando il campo **Strategia di generazione delle previsioni** è impostato su *Servizio Azure Machine Learning*.

Per ulteriori informazioni su come configurare il servizio Azure Machine Learning e quindi utilizzare le impostazioni per connettersi, vedi la sezione [Configurare il servizio Azure Machine Learning](#setup-amls).

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Configurare la connessione a Azure Machine Learning Studio (classico)

> [!IMPORTANT]
> Azure Machine Learning Studio (classico) è stato deprecato. Pertanto, non è più possibile creare nuove aree di lavoro in Azure. È stato sostituito dal servizio Azure Machine Learning, che fornisce funzionalità simili e altre ancora. Se non usi già Azure Machine Learning, dovresti iniziare a usare il servizio Azure Machine Learning. Se disponi già di un'area di lavoro creata per Azure Machine Learning Studio (classico), puoi continuare a usarla finché la funzionalità non viene completamente rimossa da Azure. Tuttavia, ti consigliamo di eseguire l'aggiornamento al servizio Azure Machine Learning il prima possibile. Anche se l'applicazione continuerà ad avvisare che Azure Machine Learning Studio (classico) è stato deprecato, il risultato della previsione non sarà interessato. Per ulteriori informazioni sul nuovo servizio Azure Machine Learning e su come configurarlo, vedi la sezione [Configurare il servizio Azure Machine Learning](#setup-amls).
>
> È possibile passare liberamente dall'uso delle soluzioni di Machine Learning nuove a quelle precedenti con Supply Chain Management finché l'area di lavoro precedente di Azure Machine Learning Studio (classico) rimane disponibile.

Se disponi già di un'area di lavoro di Azure Machine Learning Studio (classico), puoi usarla per generare previsioni connettendola a Supply Chain Management. È possibile stabilire questa connessione utilizzando la scheda **Azure Machine Learning** della pagina **Parametri di previsione della domanda**. Le impostazioni di questa scheda hanno effetto solo quando il campo **Strategia di generazione delle previsioni** è impostato su *Azure Machine Learning*. Immetti i dettagli seguenti per l'area di lavoro di Azure Machine Learning Studio (classico):

- Chiave dell'API del servizio Web
- URL dell'endpoint del servizio Web
- Nome account di archiviazione Azure
- Chiave account di archiviazione Azure

> [!NOTE]
> Il nome account e la chiave di archiviazione Azure sono necessari solo se si utilizza un account di archiviazione personalizzato. Se distribuisci la versione locale, devi avere un account di archiviazione personalizzato in Azure, in modo che il servizio Machine Learning possa accedere ai dati storici.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>Parametri e valori predefiniti per i modelli di previsione della domanda

Quando utilizzi Machine Learning per generare i modelli di pianificazione delle previsioni, controlli le opzioni di Machine Learning impostando i valori per i *parametri dell'algoritmo di previsione*. Questi valori vengono inviati da Supply Chain Management ad Azure Machine Learning. Utilizza la pagina **Parametri dell'algoritmo di previsione** per controllare quali tipi di valori devono essere forniti e quali valori devono avere ciascuno.

Per impostare i parametri e i valori predefiniti usati per i modelli di previsione della domanda, vai a **Pianificazione generale \> Impostazioni \> Previsione della domanda \> Parametri dell'algoritmo di previsione**. Viene fornito un set standard di parametri. Ogni parametro ha i seguenti campi:

- **Nome** – Il nome del parametro, come usato da Azure. In genere, non devi modificare questo nome a meno che tu non abbia personalizzato l'esperimento in Azure Machine Learning.
- **Descrizione** – Un nome comune per il parametro. Questo nome viene utilizzato per identificare il parametro in altri punti del sistema (ad esempio, nella pagina **Parametri di previsione della domanda**).
- **Valore** – Il valore predefinito del parametro. Il valore da inserire dipende dal parametro che stai modificando. 
- **Spiegazione** – Una breve descrizione del parametro e come utilizzarlo. Questa descrizione in genere include consigli sui valori validi per il campo **Valore**.

I seguenti parametri sono forniti per impostazione predefinita. Se devi tornare a questo elenco standard, seleziona **Ripristina** nel riquadro azioni.

- **Percentuale livello di fiducia** - Un intervallo di fiducia è costituito da una gamma di valori che rappresentano una buona stima per la previsione della domanda. Un livello di fiducia del 95% indica che è presente una percentuale di rischio del 5% che la domanda futura non sia compresa nell'intervallo di fiducia.
- **Forza stagionalità** - Specifica se forzare il modello a utilizzare uno specifico tipo di stagionalità. Questo parametro si applica solo ad ARIMA ed ETS. Opzioni: *AUTO (predefinita)*, *NESSUNO*, *ADDITIVO*, *MOLTIPLICATIVO*.
- **Modello di previsione** – Specifica quale modello di previsione utilizzare. Opzioni: *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *TUTTI*. Per selezionare il modello più adatto, utilizza *TUTTI*.
- **Valore previsto massimo** - Specifica il valore massimo da utilizzare per le previsioni. Formato: +1E[n] o costante numerica.
- **Valore previsto minimo** - Specifica il valore minimo da utilizzare per le previsioni. Formato: -1E[n] o costante numerica.
- **Sostituzione di valore mancante** - Specifica la modalità di riempimento dei vuoti nei dati storici. Opzioni: *(valore numerico)*, *MEDIA*, *PRECEDENTE*, *INTERPOLAZIONE LINEARE*, *INTERPOLAZIONE POLINOMIALE*.
- **Sostituzione di valore mancante** - Specifica se la sostituzione del valore si applica solo all'intervallo di date di ogni singolo attributo di granularità oppure all'intero gruppo di dati. Sono disponibili le seguenti opzioni per stabilire l'intervallo di date che il sistema utilizza per colmare le lacune nei dati cronologici:

    - *GLOBAL* – Il sistema utilizza l'intero intervallo di date di tutti gli attributi di granularità.
    - *HISTORY_DATE_RANGE* - Il sistema utilizza un intervallo di date specifico definito dai campi **Dal** e **Al** nella sezione **Orizzonte storico** nella finestra di dialogo **Genera previsione di base statistica**.
    - *GRANULARITY_ATTRIBUTE* - Il sistema utilizza l'intervallo di date dell'attributo di granularità attualmente elaborato.

    > [!NOTE]
    > Un attributo di granularità è una combinazione di dimensioni di previsione rispetto alle quali viene eseguita la previsione. È possibile definire le dimensioni della previsione nella pagina **Parametri di previsione della domanda**.

- **Suggerimento stagionalità** - Per i dati stagionali, fornire un suggerimento al modello previsionale per migliorare la precisione della previsione. Formato: numero intero che rappresenta il periodo di ripetizione di un modello di domanda. Utilizzare ad esempio *6* per dati che si ripetono ogni sei mesi.
- **Percentuale dimensione set di test** - Percentuale di dati storici da utilizzare come set di test per il calcolo della precisione della previsione.

È possibile sostituire i valori di questi parametri andando su **Pianificazione generale \> Impostazione \> Previsione della domanda \> Parametri di previsione della domanda**. Puoi sovrascrivere i parametri nella pagina **Parametri di previsione della domanda** nei seguenti modi:

- Utilizza la scheda **Generale** per sovrascrivere i parametri globalmente.
- Utilizza la scheda **Chiavi di allocazione articoli** per sovrascrivere i parametri per chiavi di allocazione articolo specifiche. I parametri che vengono sovrascritti per una chiave di allocazione articolo specifica hanno effetto solo sulla previsione degli articoli associati alla chiave di allocazione articolo.

> [!NOTE]
> Nella pagina **Parametri dell'algoritmo di previsione** puoi utilizzare i pulsanti nel riquadro azioni per aggiungere parametri all'elenco o rimuovere parametri dall'elenco. Tuttavia in genere non devi usare questo approccio a meno che tu non abbia personalizzato l'esperimento in Azure Machine Learning.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>Configurare il servizio Azure Machine Learning

Supply Chain Management calcola le previsioni della domanda usando il servizio Azure Machine Learning, che deve essere configurato ed eseguito nella propria sottoscrizione di Azure. Questa sezione descrive come configurare il servizio Azure Machine Learning in Azure e quindi connetterlo all'ambiente Supply Chain Management.

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>Abilitare il servizio Azure Machine Learning in Gestione funzionalità

Prima di poter usare il servizio Azure Machine Learning per la previsione della domanda, è necessario attivare una funzionalità in Supply Chain Management per abilitare l'integrazione. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Pianificazione generale*
- **Nome funzione:** *Servizio Azure Machine Learning per la previsione della domanda*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>Configurare Machine Learning in Azure

Per consentire ad Azure di usare Machine Learning per elaborare le previsioni, è necessario configurare un'area di lavoro di Azure Machine Learning per questo scopo. Sono disponibili due opzioni:

- Per configurare l'area di lavoro eseguendo uno script fornito da Microsoft, segui le istruzioni nella sezione [Opzione 1: eseguire uno script per configurare automaticamente l'area di lavoro di Machine Learning](#ml-workspace-script), quindi passa alla sezione [Configurare i parametri di connessione del servizio Azure Machine Learning in Supply Chain Management](#demand-forecast-parameters).
- Per configurare manualmente l'area di lavoro segui le istruzioni nella sezione [Opzione 2: configurare manualmente l'area di lavoro di Machine Learning](#ml-workspace-manual), quindi passa alla sezione [Configurare i parametri di connessione del servizio Azure Machine Learning in Supply Chain Management](#demand-forecast-parameters). Questa opzione richiede più tempo, ma ti offre più controllo.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>Opzione 1: eseguire uno script per configurare automaticamente l'area di lavoro di Machine Learning

Questa sezione descrive come configurare l'area di lavoro di Machine Learning utilizzando uno script automatico fornito da Microsoft. Se preferisci, puoi impostare manualmente tutte le risorse seguendo le istruzioni nella sezione [Opzione 2: configurare manualmente l'area di lavoro di Machine Learning](#ml-workspace-manual). Non è necessario completare entrambe le opzioni.

1. Su GitHub, apri il repository (repo) [Modelli per previsione della domanda di Dynamics 365 Supply Chain Management con Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) e scarica i seguenti file:

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Apri una finestra di PowerShell ed esegui lo script **quick_setup.ps1** che hai scaricato nel passaggio precedente. Seguire le istruzioni visualizzate. Lo script imposterà l'area di lavoro, l'archiviazione, l'archivio dati predefinito e le risorse di calcolo richiesti. Tuttavia, è comunque necessario creare le pipeline richieste seguendo i passaggi rimanenti di questa procedura. Le pipeline forniscono un modo per avviare gli script di previsione da Supply Chain Management.
1. In Azure Machine Learning Studio carica il file **sampleInput.csv** che hai scaricato nel passaggio 1 nel contenitore denominato *demplan-azureml*. Lo script quick_setup.ps1 ha creato questo contenitore. Questo file è necessario per pubblicare la pipeline e generare una previsione di test. Per le istruzioni, vedi [Caricare un BLOB in blocchi](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).
1. In Azure Machine Learning Studio seleziona **Notebook** nella barra di spostamento.
1. Trova la seguente posizione nella struttura **File**: **Utenti/\[utente corrente\]/src**.
1. Carica i restanti quattro file che hai scaricato nel passaggio 1 nella posizione che hai trovato nel passaggio precedente.
1. Seleziona il file **api_trigger.py** che hai appena caricato ed eseguilo. Creerà una pipeline che può essere attivata tramite l'API.
1. La tua area di lavoro è ora configurata. Passa alla sezione [Configurare i parametri di connessione del servizio Azure Machine Learning in Supply Chain Management](#demand-forecast-parameters).

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>Opzione 2: configurare manualmente l'area di lavoro di Machine learning

Questa sezione descrive come configurare manualmente l'area di lavoro di Machine Learning. È necessario completare le procedure in questa sezione solo se hai deciso di non eseguire lo script di installazione automatica, come descritto nella sezione [Opzione 1: eseguire uno script per configurare l'area di lavoro di Machine Learning](#ml-workspace-script).

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>Passaggio 1: creare una nuova area di lavoro

Per creare una nuova area di lavoro di Machine Learning, attieniti alla procedura indicata di seguito.

1. Accedi al tuo portale di Azure.
1. Apri il servizio **Machine Learning**.
1. Seleziona **Crea** sulla barra degli strumenti per aprire la **Creazione guidata**.
1. Completa la procedura guidata seguendo le istruzioni sullo schermo. Tieni a mente i seguenti punti mentre lavori:

    - Utilizzare le impostazioni predefinite a meno che altri punti in questo elenco non suggeriscano impostazioni diverse.
    - Assicurati di selezionare l'area geografica che corrisponde all'area in cui è distribuita la tua istanza di Supply Chain Management. In caso contrario, alcuni dei tuoi dati potrebbero attraversare i confini regionali. Per ulteriori informazioni, vedi la sezione [Informativa sulla privacy](#privacy) più avanti in questo argomento.
    - Usa le risorse dedicate, ad esempio gruppi di risorse, account di archiviazione, registri contenitori, Azure Key Vault e risorse di rete.
    - Nella pagina **Configurare i parametri di connessione del servizio Azure Machine Learning** della procedura guidata, è necessario fornire un nome per l'account di archiviazione. Utilizza un account dedicato alla previsione della domanda. I dati di input e output della previsione della domanda verranno archiviati in questo account di archiviazione.

Per ulteriori informazioni, vedi [Creare l'area di lavoro](/azure/machine-learning/quickstart-create-resources#create-the-workspace).

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>Passaggio 2: configurare lo spazio di archiviazione

Per impostare lo spazio di archiviazione attieniti alla seguente procedura.

1. In GitHub, apri il repository [Modelli per previsione della domanda di Dynamics 365 Supply Chain Management con Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) e scarica il file **sampleInput.csv**.
1. Apri l'account di archiviazione che hai creato nella sezione [Passaggio 1: creare una nuova area di lavoro](#create-workspace).
1. Segui le istruzioni in [Creare un contenitore](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) per creare un contenitore denominato *demplan-azureml*.
1. Carica il file **sampleInput.csv** scaricato nel passaggio 1 nel contenitore appena creato. Questo file è necessario per pubblicare la pipeline e generare una previsione di test. Per le istruzioni, vedi [Caricare un BLOB in blocchi](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).

##### <a name="step-3-configure-a-default-datastore"></a>Passaggio 3: configurare un archivio dati predefinito

Per impostare l'archivio dati predefinito attieniti alla seguente procedura.

1. In Azure Machine Learning Studio seleziona **Archivi dati** nella barra di spostamento.
1. Crea un nuovo archivio dati di tipo *Archiviazione BLOB di Azure* che punta al contenitore di archiviazione BLOB *demplan-azureml* creato nella sezione [Passaggio 2: configurare lo spazio di archiviazione](#config-storage). Se il tipo di autenticazione del nuovo archivio dati è *Chiave dell'account*, fornisci una chiave dell'account per l'account di archiviazione creato. Per le istruzioni, vedi [Gestire le chiavi di accesso all'account di archiviazione](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).
1. Rendi il tuo nuovo archivio dati come predefinito aprendo i dettagli e selezionando **Imposta come archivio dati predefinito**.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>Passaggio 4: configurare le risorse di calcolo

Usa la procedura seguente per configurare una risorsa di calcolo in Azure Machine Learning Studio per eseguire gli script di generazione delle previsioni.

1. Apri la pagina dei dettagli per l'area di lavoro di Machine Learning che hai creato nella sezione [Passaggio 1: creare una nuova area di lavoro](#create-workspace). Trova il valore **URL Web di Studio** e seleziona il collegamento per aprirlo.
1. Seleziona **Calcolo** nel riquadro di spostamento.
1. Nella scheda **Istanze di calcolo** seleziona **Nuovo** per aprire una procedura guidata che ti aiuterà a creare una nuova istanza di calcolo. Seguire le istruzioni visualizzate. L'istanza di calcolo verrà usata per creare la pipeline di previsione della domanda (può essere eliminata dopo la pubblicazione della pipeline). Usa le impostazioni predefinite.
1. Nella scheda **Cluster di calcolo** seleziona **Nuovo** per aprire una procedura guidata che ti aiuterà a creare un nuovo cluster di calcolo. Seguire le istruzioni visualizzate. Il cluster di calcolo verrà utilizzato per generare previsioni della domanda. Le sue impostazioni influiscono sulle prestazioni e sul livello massimo di parallelizzazione dell'esecuzione. Imposta i seguenti campi, ma usa le impostazioni predefinite per tutti gli altri campi:

    - **Nome** - Immetti *e2ecpucluster*.
    - **Dimensioni macchina virtuale** – Modifica questa impostazione in base al volume di dati che si prevede di utilizzare come input per la previsione della domanda. Il conteggio dei nodi non deve superare 11, poiché è necessario un nodo per attivare la generazione della previsione della domanda e il numero massimo di nodi che possono essere utilizzati per generare una previsione è 10. Imposterai anche il conteggio dei nodi nel file parameters.py nella sezione [Passaggio 5: creare le pipeline](#create-pipelines). Su ogni nodo, ci saranno diversi processi di lavoro che eseguono script di previsione in parallelo. Il numero totale di processi di lavoro nel tuo processo sarà *Numero di core di un nodo* × *Conteggio nodi*. Ad esempio, se il cluster di calcolo è di tipo *Standard\_D4* (otto core) e un massimo di 11 nodi, e se il valore `nodes_count` è impostato su *10* nel file parameters.py, il livello effettivo di parallelismo è 80.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>Passaggio 5: creare le pipeline

Le pipeline forniscono un modo per avviare gli script di previsione da Supply Chain Management. Utilizza la seguente procedura per creare le pipeline richieste.

1. Su GitHub, apri il repository [Modelli per previsione della domanda di Dynamics 365 Supply Chain Management con Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) e scarica i seguenti file:

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. In Azure Machine Learning Studio seleziona **Notebook** nella barra di spostamento.
1. Trova la seguente posizione nella struttura **File**: **Utenti/\[utente corrente\]/src**.
1. Carica i quattro file che hai scaricato nel passaggio 1 nella posizione che hai trovato nel passaggio precedente.
1. In Azure, apri e rivedi il file **parameters.py** che hai appena caricato. Assicurati che il valore di `nodes_count` sia uno in meno del valore configurato per il cluster di calcolo nella sezione [Passaggio 4: configurare le risorse di calcolo](#config-compute-resources). Se il valore di `nodes_count` è maggiore o uguale al numero di nodi nel cluster di calcolo, l'esecuzione della pipeline può essere avviata. Tuttavia, smetterà di rispondere mentre attende le risorse richieste. Per ulteriori informazioni sul conteggio dei nodi, vedi la sezione [Passaggio 4: configurare le risorse di calcolo](#config-compute-resources).
1. Seleziona il file **api_trigger.py** che hai appena caricato ed eseguilo. Creerà una pipeline che può essere attivata tramite l'API.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>Configurare una nuova applicazione Active Directory

È necessaria un'applicazione Active Directory per l'autenticazione delle risorse dedicate alla previsione della domanda tramite l'entità servizio. Pertanto, l'applicazione deve disporre del livello di privilegio più basso necessario per generare la previsione.

1. Accedi al tuo portale di Azure.
1. Registra una nuova applicazione in Azure Active Directory (Azure AD) del tenant. Per istruzioni, vedi [Usare il portale per creare un'applicazione Azure AD e un'entità servizio che possano accedere alle risorse](/azure/active-directory/develop/howto-create-service-principal-portal).
1. Completa la procedura guidata seguendo le istruzioni sullo schermo. Usa le impostazioni predefinite.
1. Concedi alla tua nuova applicazione Active Directory l'accesso alle seguenti risorse che hai creato nella sezione [Configurare Machine Learning in Azure](#ml-workspace). Per le istruzioni, vedi [Assegnare ruoli di Azure tramite il portale di Azure](/azure/role-based-access-control/role-assignments-portal?tabs=current). Questo passaggio consentirà al sistema di importare ed esportare i dati di previsione e di attivare le esecuzioni della pipeline di Machine Learning da Supply Chain Management.

    - Ruolo di collaboratore nell'area di lavoro di machine learning
    - Ruolo di collaboratore per l'account di archiviazione dedicato
    - Ruolo di collaboratore dei dati del BLOB di archiviazione per l'account di archiviazione dedicato

1. Nella sezione **Certificati e segreti** dell'applicazione che hai creato, crea un segreto per l'applicazione. Per le istruzioni, vedi [Aggiungere un segreto client](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
1. Prendi nota dell'ID applicazione e del relativo segreto. Avrai bisogno dei dettagli di questa applicazione in seguito, quando configuri la pagina **Parametri di previsione della domanda** in Supply Chain Management.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>Configurare i parametri di connessione del servizio Azure Machine Learning in Supply Chain Management

Usa la procedura seguente per connettere l'ambiente Supply Chain Management al servizio di Machine Learning appena configurato in Azure.

1. Accedere a Supply Chain Management.
1. Vai a **Pianificazione generale \> Impostazioni \> Previsione della domanda \> Parametri di previsione della domanda**.
1. Nella scheda **Generale** assicurati che il campo **Strategia di generazione delle previsioni** sia impostato su *Servizio Azure Machine Learning*.
1. Nella scheda **Chiavi di allocazione articoli** assicurati che il campo **Strategia di generazione delle previsioni** sia impostato su *Servizio Azure Machine Learning* per ogni chiave di allocazione che deve usare il servizio Azure Machine Learning per la previsione della domanda.
1. Nella scheda **Servizio Azure Machine Learning** imposta i seguenti campi:

    - **ID tenant** - Immetti l'ID del tenant di Azure. Supply Chain Management userà questo ID per l'autenticazione con il servizio Azure Machine Learning. Puoi trovare il tuo ID tenand nella pagina **Panoramica** per Azure AD nel portale di Azure.
    - **ID applicazione entità servizio** – Inserisci l'ID dell'applicazione che hai creato nella sezione [Applicazione Active Directory](#aad-app). Questo valore viene usato per autorizzare le richieste API al servizio Azure Machine Learning.
    - **Segreto entità servizio** – Inserisci il segreto applicazione entità servizio dell'applicazione che hai creato nella sezione [Applicazione Active Directory](#aad-app). Questo valore viene usato per acquisire il token di accesso per l'entità di sicurezza creata per eseguire operazioni autorizzate su Archiviazione di Azure e l'area di lavoro Azure Machine Learning.
    - **Nome dell'account di archiviazione** – Immetti il nome dell'account di archiviazione di Azure specificato durante l'esecuzione dell'installazione guidata nell'area di lavoro di Azure. Per ulteriori informazioni, vedi la sezione [Configurare Machine Learning in Azure](#ml-workspace).
    - **Indirizzo dell'endpoint della pipeline** – Immetti l'URL dell'endpoint REST della pipeline per il servizio Azure Machine Learning. Hai creato questa pipeline come ultimo passaggio per [configurare Machine Learning in Azure](#ml-workspace). Per ottenere l'URL della pipeline, accedi al portale di Azure, seleziona **Pipeline** sulla barra di navigazione. Nella scheda **Pipeline** seleziona l'endpoint della pipeline denominato **TriggerDemandForecastGeneration**. Quindi copia l'endpoint REST mostrato.

    ![Parametri nella scheda Servizio Azure Machine Learning della pagina Parametri di previsione della domanda.](media/azure-ml-service-parameters.png "Parametri nella scheda Servizio Azure Machine Learning della pagina Parametri di previsione della domanda")

## <a name="privacy-notice"></a><a name="privacy"></a>Informativa sulla privacy

Quando selezioni *Servizio Azure Machine Learning* come strategia di generazione delle previsioni, Supply Chain Management invia automaticamente i dati dei clienti per la domanda storica, come quantità aggregate, nomi di prodotti e relative dimensioni del prodotto, località di spedizione e ricezione, identificatori dei clienti e anche parametri di previsione, all'area geografica in cui si trovano l'area di lavoro di Machine Learning e l'account di archiviazione collegato allo scopo di prevedere le richieste future. Il servizio Azure Machine Learning potrebbe trovarsi in un'area geografica diversa dall'area geografica in cui è distribuito Supply Chain Management. Alcuni utenti possono controllare se questa funzionalità è abilitata selezionando la strategia di generazione delle previsioni nella pagina **Parametri di previsione della domanda**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica previsioni della domanda](introduction-demand-forecasting.md)
- [Generare una previsione di base statistica](generate-statistical-baseline-forecast.md)
- [Implementare correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
