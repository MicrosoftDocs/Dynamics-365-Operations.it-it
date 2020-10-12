---
title: Configurare il componente aggiuntivo per la fatturazione elettronica
description: Questo argomento spiega come configurare il componente aggiuntivo per la fatturazione elettronica in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 92ffd2076497325fb986478328c4b2584929881d
ms.sourcegitcommit: 025561f6a21fe8705493daa290f3f6bfb9f1b962
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "3835982"
---
# <a name="set-up-the-electronic-invoicing-add-on"></a>Configurare il componente aggiuntivo per la fatturazione elettronica

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La configurazione della funzionalità del componente aggiuntivo per la fatturazione elettronica consiste nel processo di creazione della configurazione obbligatoria tramite l'ambiente Regulatory Configuration Services (RCS) e la pubblicazione di tale configurazione sul server del componente aggiuntivo per la fatturazione elettronica. La configurazione consente di creare le regole configurabili che consentono al componente aggiuntivo per la fatturazione elettronica di utilizzare un protocollo sicuro su Internet per comunicare e scambiare dati con un'entità di terze parti tramite servizi Web.

La configurabilità si basa sulla configurazione del formato di creazione dei rapporti elettronici (ER) come mezzo per creare contenuti inviati e ricevuti tramite file digitali. Si basa inoltre sull'orchestrazione delle azioni di comunicazione per inviare richieste e ricevere risposte da servizi Web di terze parti senza richiedere la scrittura di codice.

## <a name="overview"></a>Panoramica

"La funzionalità del componente aggiuntivo per la fatturazione elettronica" è il nome generico della risorsa configurata e pubblicata per utilizzare il server del componente aggiuntivo per la fatturazione elettronica. La configurazione della funzionalità di fatturazione elettronica combina, tra le altre cose, l'uso di formati di configurazione per la creazione di report elettronici (ER) per creare file di esportazione e importazione configurabili e l'uso di azioni e flussi di azioni per consentire la creazione di regole configurabili per inviare richieste, importare le risposte e analizzare il contenuto della risposta.

La figura seguente mostra i componenti principali di una funzionalità del componente aggiuntivo per la fatturazione elettronica.

![Panoramica della funzionalità del componente aggiuntivo per la fatturazione elettronica](media/e-Invoicing-services-feature-setup-Overview-e-Invoicing-feature.png)

A causa delle variazioni nei formati delle fatture e nei flussi di azioni, la configurazione della funzionalità potrebbe variare in base al paese o all'area geografica o in base ai requisiti aziendali.

## <a name="set-up-the-electronic-invoicing-add-on-feature"></a>Configurare la funzionalità del componente aggiuntivo per la fatturazione elettronica

Il processo di configurazione deve essere completato nel proprio ambiente RCS. Segui questi passaggi per creare una nuova funzionalità del componente aggiuntivo per la fatturazione elettronica.

1. Accedi al tuo ambiente RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Componente aggiuntivo per la fatturazione elettronica**.
3. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, seleziona **Importa** per importare la configurazione del modello dati ER dal repository globale.
4. Seleziona **Aggiungi** per creare una funzionalità del componente aggiuntivo per la fatturazione elettronica. È possibile creare la funzionalità da zero o derivarla da una funzionalità del componente aggiuntivo per la fatturazione elettronica esistente.

    ![Aggiunta di una funzionalità del componente aggiuntivo per la fatturazione elettronica](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature.png)

> [!NOTE]
> Quando crei una nuova funzionalità del componente aggiuntivo per la fatturazione elettronica, ha un numero di versione e il suo stato predefinito è impostato su **Bozza**.

### <a name="configurations"></a>Configurazioni

Le configurazioni contengono le configurazioni del formato di creazione di report elettronici necessarie per le trasformazioni e per creare i file che verranno scambiati durante la comunicazione con i servizi Web di terze parti. Una funzionalità del componente aggiuntivo per la fatturazione elettronica può avere tutte le configurazioni del formato di file di creazione di report elettronici richieste, in base alla specifica tecnica di integrazione fornita dal provider di servizi Web.

Segui questi passaggi per aggiungere formati ER alla funzionalità del componente aggiuntivo per la fatturazione elettronica.

1. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi** per aggiungere configurazioni del formato di file ER per la funzionalità del componente aggiuntivo per la fatturazione elettronica.

    ![Aggiunta di configurazioni della funzionalità del componente aggiuntivo per la fatturazione elettronica](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Quando crei da zero una funzionalità del componente aggiuntivo per la fatturazione elettronica, è necessario aggiungere manualmente tutte le configurazioni del formato di file ER. Quando si ricava una funzionalità del componente aggiuntivo per la fatturazione elettronica da una funzionalità esistente, le configurazioni del formato di file ER vengono create automaticamente, poiché vengono ereditate dalla funzionalità del componente aggiuntivo della fatturazione elettronica originale.

2. Seleziona **Modifica** per aprire la pagina **Progettazione formati**, in cui è possibile modificare la configurazione del formato di file ER.

    ![Modifica di configurazioni della funzionalità del componente aggiuntivo per la fatturazione elettronica](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Durante la modifica del formato, lo stato della versione di configurazione è impostato su **Bozza**.

3. Utilizza la pagina **Progettazione formati** per modificare la configurazione del formato di file. Per ulteriori informazioni, vedi [Creare configurazioni di creazione di report elettronici (ER)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Pagina Progettazione formati](media/e-Invoicing-services-feature-setup-ER-Format-designer.png)

### <a name="feature-setups"></a>Configurazioni della funzionalità

Le configurazioni della funzionalità incorporano le regole per la comunicazione e la sicurezza con un servizio Web di terze parti. Una funzionalità del componente aggiuntivo per la fatturazione elettronica può avere tutte le configurazioni di funzionalità necessarie, in base alla regola aziendale che si desidera realizzare.

Segui questi passaggi per aggiungere configurazioni della funzionalità alla funzionalità del componente aggiuntivo per la fatturazione elettronica.

1. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi** per aggiungere configurazioni della funzionalità alla funzionalità del componente aggiuntivo per la fatturazione elettronica.

    ![Aggiunta di configurazioni della funzionalità del componente aggiuntivo per la fatturazione elettronica](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Setups.png)

    > [!NOTE]
    > Quando crei da zero una funzionalità del componente aggiuntivo per la fatturazione elettronica, è necessario aggiungere manualmente tutte le configurazioni della funzionalità necessarie. Quando si ricava una funzionalità del componente aggiuntivo per la fatturazione elettronica da una funzionalità esistente, tutte le configurazioni della funzionalità vengono create automaticamente, poiché vengono ereditate dalla funzionalità del componente aggiuntivo della fatturazione elettronica originale.

2. Seleziona **Modifica** per modificare la configurazione della versione della funzionalità.

    ![Modifica di configurazioni della funzionalità del componente aggiuntivo per la fatturazione elettronica](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Setups.png)

3. Utilizza la pagina **Configurazione versioni funzionalità** per configurare azioni, regole di applicabilità e variabili.

    ![Azioni, regole di applicabilità e variabili](media/e-Invoicing-services-feature-setup-View-Actions-Applicability-Rules-Variables.png)

### <a name="actions"></a>Azioni

Le azioni sono un elenco predefinito di operazioni eseguite in ordine sequenziale. Questo elenco rappresenta la suddivisione dei passaggi necessari per l'esecuzione completa della funzionalità del componente aggiuntivo per la fatturazione elettronica. Le azioni possono incorporare nella stessa funzionalità del componente aggiuntivo per la fatturazione elettronica, la comunicazione in entrambe le direzioni: invio di una richiesta per una destinazione e ricezione di una risposta e analisi del suo contenuto.

Ciascuna azione contiene un elenco predefinito di parametri necessari affinché l'azione raggiunga il suo scopo. Opzionalmente possono essere forniti parametri aggiuntivi.

#### <a name="actions-fasttab"></a>Scheda dettaglio Azioni

Nella pagina **Configurazione versioni funzionalità**, nella scheda **Azioni**, nella Scheda dettaglio **Azioni**, segui uno o entrambi questi passaggi per gestire le azioni:

- Seleziona **Nuovo** o **Elimina** per aggiungere nuove azioni o eliminare azioni esistenti.
- Seleziona **Su** o **Giù** per spostare le azioni selezionate in alto o in basso nella griglia e quindi modificare l'ordine in cui vengono eseguite. Le azioni vengono eseguite nell'ordine in cui appaiono nella griglia, dall'alto verso il basso.

![Gestione delle azioni](media/e-Invoicing-services-feature-setup-Manage-Actions.png)

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Azioni**.

| Campo        | descrizione |
|--------------|-------------|
| Azione       | Esistono otto azioni predefinite:<ul><li><strong>Firma documento</strong></li><li><strong>FileStoreActionName</strong></li><li><strong>Trasforma documento</strong></li><li><strong>Elabora risposta</strong></li><li><strong>Chiama servizio web REST</strong></li><li><strong>Chiama servizio PAC messicano</strong></li><li><strong>Chiama servizio SEFAZ brasiliano</strong></li><li><strong>Chiama servizio SDI italiano</strong></li></ul> |
| Nome azione  | Il nome dell'azione e il relativo ordine di esecuzione. |
| descrizione  | Una descrizione dell'azione. |
| Abilita nuovo tentativo | Una casella di controllo selezionata indica che l'azione può essere ripetuta se il tentativo precedente non ha avuto successo. |
| Azione nuovo tentativo | In caso di nuovo tentativo, l'azione da cui viene avviato il nuovo tentativo. Il nuovo tentativo termina quindi con l'azione corrente (tentativo inclusivo). Per le azioni che includono tali parametri, il parametro **Backoff minimo** e **Backoff massimo** specificano il numero minimo e il numero massimo di tentativi. |

#### <a name="parameters-fasttab"></a>Scheda dettaglio Parametri

La Scheda dettaglio **Parametri** elenca i parametri per l'azione selezionata nella Scheda dettaglio **Azioni**.

![Scheda dettaglio Parametri](media/e-Invoicing-services-feature-setup-View-Actions-Parameters.png)

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Parametri**.

| Campo       | descrizione |
|-------------|-------------|
| Nome        | Un elenco predefinito di parametri. Per ulteriori informazioni, vedi la sezione [Elenco dei parametri per azione](#list-of-parameters-by-action). |
| descrizione | Descrizione del parametro. |
| Valore       | Valore del parametro. |

#### <a name="list-of-parameters-by-action"></a>Elenco dei parametri per azione

I parametri disponibili variano a seconda dell'azione selezionata nella Scheda dettaglio **Azioni**.

###### <a name="action-sign-document"></a>Azione: firma documento

| Parametro                             | descrizione |
|---------------------------------------|-------------|
| File di input                            | Il file del documento XML di input che deve essere firmato utilizzando una firma elettronica. |
| Nome certificato                      | Il nome del certificato in archivio. |
| Tipo di firma                        | Il tipo di firma da utilizzare. |
| Nome del metodo di firma                 | Il nome del metodo di firma utilizzato per generare una firma elettronica. |
| Nome del metodo digest                    | Il metodo digest utilizzato per generare una stringa digest nella firma digitale. |
| Nome del metodo di canonizzazione          | Il metodo di canonizzazione utilizzato per calcolare l'hash di firma. |
| Nome attributo di riferimento              | Il nome dell'attributo che indica dove inserire l'ID di riferimento nell'elemento firma. |
| Nome dell'elemento da firmare               | Il nome dell'elemento XML nel documento che deve essere firmato utilizzando una firma elettronica. Se non viene specificato alcun elemento, viene firmata la radice del documento. |
| Nome dell'elemento per inserire la firma   | Il nome dell'elemento XML in cui deve essere inserita una firma digitale generata. Se non viene specificato alcun elemento, la firma viene inserita nella radice del documento. |
| File XLST con trasformazione digest       | Il file XSLT (Extensible Stylesheet Language Transformations) che contiene le regole di trasformazione digest per generare la stringa digest per una firma elettronica. |
| Percorso per inserire la stringa digest          | Il percorso in formato **\<elementName\>.\<Attribute.Path\>** della posizione in cui deve essere inserita la stringa digest generata. |
| Posizione del numero di certificato           | Il nome dell'elemento e dell'attributo in cui inserire il numero del certificato. |
| Posizione dei dati del certificato          | Il nome dell'elemento e dell'attributo in cui i dati del certificato (Base64) devono essere inseriti. |
| Il numero del certificato è in formato ASCII | Un valore che specifica se il numero del certificato è codificato in formato ASCII. |

###### <a name="action-filestoreactionname"></a>Azione: FileStoreActionName

| Parametro  | descrizione |
|------------|-------------|
| File di input | Il file di input da memorizzare. |

###### <a name="action-transform-document"></a>Azione: trasforma il documento

| Parametro                       | descrizione |
|---------------------------------|-------------|
| File di input                      | Il file di origine che fornisce i dati che devono essere eseguiti per l'azione. |
| Direzione                       | Un valore che indica se deve essere utilizzato il formato di importazione o il formato di esportazione. |
| ID configurazione                | Il formato che dovrebbe essere eseguito. |
| Versione di configurazione           | Se non viene specificata alcuna versione di configurazione, verrà utilizzata la versione più recente. |
| Punto di integrazione della configurazione | Il file di origine che fornisce i dati al runtime di creazione di report. |

###### <a name="action-process-response"></a>Azione: elabora risposta

| Parametro                    | descrizione |
|------------------------------|-------------|
| File di input                   | La risposta da analizzare. |
| Elenco di configurazioni report | Un elenco di configurazioni utilizzate per analizzare le risposte. |

###### <a name="action-call-rest-web-service"></a>Azione: chiama servizio web REST

| Parametro                   | descrizione |
|-----------------------------|-------------|
| URL servizio Web             | L'URL a cui inviare le richieste. |
| Timeout richiesta Web         | La quantità massima di tempo (in millisecondi) di attesa per una risposta del servizio Web. |
| Tipo di operazione richiesta      | Il tipo di operazione di richiesta HTTP (ad esempio, **GET**, **POST** o **DELETE**). |
| Nomi certificati           | I nomi dei certificati. |
| Codifica del corpo della risposta      | La codifica prevista del corpo della risposta HTTP, in modo che possa essere decodificato correttamente. |
| Tipo di contenuto della richiesta HTTP   | L'input dell'intestazione del tipo di contenuto della richiesta HTTP. |
| Corpo del contenuto della richiesta HTTP   | Corpo della richiesta HTTP. (Il corpo può essere vuoto). |
| Valori di query dei parametri HTTP | Valori di query dei parametri utilizzati per riempire l'URL con parametri variabili. |
| Percorso richiesta               | Il percorso di distribuzione per la richiesta HTTP. È possibile scrivere i parametri delle variabili nella notazione **\{paramName\}**. Ecco un esempio: **"api/{id}/submit"**. |
| Elenco dei parametri del percorso        | I parametri del percorso, in notazione valore-chiave, utilizzati per inserire variabili nel percorso. |
| Intestazioni HTTP personalizzate         | Le intestazioni HTTP personalizzate da inserire nella richiesta. |
| Cookie di richiesta HTTP        | Un elenco di cookie, in notazione valore-chiave, da inserire nella richiesta di intestazione dei cookie HTTP. |
| Protocollo di sicurezza           | Il protocollo di sicurezza da utilizzare per le richieste HTTP per comunicare con il server. (Per impostazione predefinita, viene utilizzato Transport Layer Security \[TLS\] 1.2). |

###### <a name="action-call-mexican-pac-service"></a>Azione: chiama servizio PAC messicano

| Parametro                | descrizione |
|--------------------------|-------------|
| File di input               | Il file che contiene i dati XML che verranno inviati al servizio Web come parametro di input del metodo. |
| Indirizzo URL              | L'indirizzo del servizio Web (endpoint). |
| Nome del metodo (azione) Web | Il nome del metodo Web (azione) che deve essere eseguito. |
| Attestati             | La catena di certificati richiesta per l'autenticazione del client dal servizio Web. Il certificato client dovrebbe essere l'ultimo certificato della catena. I certificati radice e intermedi dovrebbero essere i primi. |
| Timeout richiesta Web      | La quantità massima di tempo (in millisecondi) di attesa per una risposta del servizio Web. |
| Intervallo di ripetizione           | L'intervallo tra i tentativi di chiamata e la ricezione di una risposta dal servizio Web. Se non viene specificato alcun intervallo, non verranno effettuati ulteriori tentativi dopo che la prima chiamata non è riuscita. |
| Conteggio tentativi              | Il numero massimo di tentativi di ripetizione per chiamare e recuperare una risposta dal servizio Web. |
| Riprova fino a               | Il tempo massimo (in millisecondi) in cui è possibile ritentare le chiamate. |
| Backoff minimo         | Il tasso di backoff minimo per il calcolo esponenziale degli intervalli di tentativi. |
| Backoff massimo         | Il tasso di backoff massimo per il calcolo esponenziale degli intervalli di tentativi. |
| Protocollo di sicurezza        | Il protocollo di sicurezza da utilizzare per le richieste HTTP per comunicare con il server. (Per impostazione predefinita, viene utilizzato TLS 1.2). |

###### <a name="action-call-brazilian-sefaz-service"></a>Azione: chiama servizio SEFAZ brasiliano

| Parametro                | descrizione |
|--------------------------|-------------|
| File di input               | Il file che contiene i dati XML che verranno inviati al servizio Web come parametro di input del metodo. |
| Indirizzo URL              | L'indirizzo del servizio Web (endpoint). |
| Nome del metodo (azione) Web | Il nome del metodo Web (azione) che deve essere eseguito. |
| Attestati             | La catena di certificati richiesta per l'autenticazione del client dal servizio Web. Il certificato client dovrebbe essere l'ultimo certificato della catena. I certificati radice e intermedi dovrebbero essere i primi. |
| Timeout richiesta Web      | La quantità massima di tempo (in millisecondi) di attesa per una risposta del servizio Web. |
| Intervallo di ripetizione           | L'intervallo tra i tentativi di chiamata e la ricezione di una risposta dal servizio Web. Se non viene specificato alcun intervallo, non verranno effettuati ulteriori tentativi dopo che la prima chiamata non è riuscita. |
| Conteggio tentativi              | Il numero massimo di tentativi di ripetizione per chiamare e recuperare una risposta dal servizio Web. |
| Riprova fino a               | Il tempo massimo (in millisecondi) in cui è possibile ritentare le chiamate. |
| Backoff minimo         | Il tasso di backoff minimo per il calcolo esponenziale degli intervalli di tentativi. |
| Backoff massimo         | Il tasso di backoff massimo per il calcolo esponenziale degli intervalli di tentativi. |
| Protocollo di sicurezza        | Il protocollo di sicurezza da utilizzare per le richieste HTTP per comunicare con il server. (Per impostazione predefinita, viene utilizzato TLS 1.2). |

###### <a name="action-call-italian-sdi-service"></a>Azione: chiama servizio SDI italiano

| Parametro                | descrizione |
|--------------------------|-------------|
| File di input               | Il file che contiene i dati XML che verranno inviati al servizio Web come parametro di input del metodo. |
| Indirizzo URL              | L'indirizzo del servizio Web (endpoint). |
| Nome del metodo (azione) Web | Il nome del metodo Web (azione) che deve essere eseguito. |
| Attestati             | La catena di certificati richiesta per l'autenticazione del client dal servizio Web. Il certificato client dovrebbe essere l'ultimo certificato della catena. I certificati radice e intermedi dovrebbero essere i primi. |
| Timeout richiesta Web      | La quantità massima di tempo (in millisecondi) di attesa per una risposta del servizio Web. |
| Intervallo di ripetizione           | L'intervallo tra i tentativi di chiamata e la ricezione di una risposta dal servizio Web. Se non viene specificato alcun intervallo, non verranno effettuati ulteriori tentativi dopo che la prima chiamata non è riuscita. |
| Conteggio tentativi              | Il numero massimo di tentativi di ripetizione per chiamare e recuperare una risposta dal servizio Web. |
| Riprova fino a               | Il tempo massimo (in millisecondi) in cui è possibile ritentare le chiamate. |
| Backoff minimo         | Il tasso di backoff minimo per il calcolo esponenziale degli intervalli di tentativi. |
| Backoff massimo         | Il tasso di backoff massimo per il calcolo esponenziale degli intervalli di tentativi. |
| Protocollo di sicurezza        | Il protocollo di sicurezza da utilizzare per le richieste HTTP per comunicare con il server. (Per impostazione predefinita, viene utilizzato TLS 1.2). |

### <a name="applicability-rules"></a>Regole di applicabilità

Le regole di applicabilità consentono di creare regole logiche che determinano il contesto di utilizzo per la configurazione della funzionalità. Pertanto, la corrispondenza tra il contesto fornito dal documento aziendale inviato per l'elaborazione, insieme ai criteri della regola di applicabilità, determinano quale funzionalità del componente aggiuntivo di fatturazione elettronica viene utilizzata per elaborare tale invio.

#### <a name="set-up-applicability-rules"></a>Configurare le regole di applicabilità

1. Nella pagina **Configurazione versioni funzionalità**, nella scheda **Regole di applicabilità**, seleziona **Nuovo** per aggiungere una regola di applicabilità.

    ![Gestione delle regole di applicabilità](media/e-Invoicing-services-feature-setup-Manage-Actions-Applicability-rules.png)

2. Nella griglia, seleziona le clausole che dovrebbero essere raggruppate.
3. Seleziona **Raggruppa clausola**.

    ![Raggruppamento delle clausole](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-clause.png)

    Quando le clausole sono raggruppate, una nuova colonna viene aggiunta alla griglia. Questa colonna specifica l'operatore logico per le clausole raggruppate.

    ![Operatore logico per clausole raggruppate](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-criterias.png)

Per separare le clausole, seleziona le clausole raggruppate da separare, quindi selezionare **Separa clausola**.

![Separazione delle clausole](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-UnGroup-criterias.png)

> [!NOTE]
> Quando si separa una clausola, inizia sempre dal livello di raggruppamento più interno.

Nella seguente tabella vengono illustrati i campi disponibili nella scheda **Regole di applicabilità**.

| Campo         | descrizione |
|---------------|-------------|
| E/O        | Operatore logico. |
| Campo         | Il campo da utilizzare per costruire la regola. |
| Tipo di operatore | Il tipo di operatore:<ul><li>Uguale</li><li>Non uguale</li><li>Maggiore di/Minore di</li><li>Maggiore di o uguale a/Minore di o uguale a</li><li>Contiene</li><li>Inizia con</li></ul> |
| Valore         | Il criterio per la regola. |

### <a name="variables"></a>Variabili

È possibile creare variabili e quindi utilizzarle come valore di input per un parametro di un'azione specifica. È inoltre possibile utilizzarli per scambiare, tra i servizi del componente aggiuntivo di fatturazione elettronica e il client, informazioni che sono il risultato dell'esecuzione di un'azione specifica come parte del flusso degli invii.

#### <a name="set-up-variables"></a>Imposta variabili

- Nella pagina **Configurazione versioni funzionalità**, nella scheda **Variabili**, seleziona **Nuovo** o **Elimina** per gestire le variabili.

    ![Gestione delle variabili](media/e-Invoicing-services-feature-setup-Manage-Variables.png)

Nella seguente tabella vengono illustrati i campi disponibili nella scheda **Variabili**.

| Campo       | descrizione |
|-------------|-------------|
| Nome        | Nome della variabile. |
| descrizione | Breve descrizione della variabile. |
| Tipo        | Il tipo di variabile:<ul><li><strong>Costante</strong>: il contenuto della variabile è fisso.</li><li><strong>Dal client</strong>: il contenuto della variabile viene acquisito dal client Microsoft Dynamics 365 durante l'esecuzione del processo di invio.</li><li><strong>Al client</strong>: il contenuto della variabile viene reso disponibile per l'importazione dal client Microsoft Dynamics 365 durante l'esecuzione del processo di invio.</li></ul> |
| Tipo di dati   | Tipo di dati della variabile:<ul><li>Boolean</li><li>Data</li><li>Numero</li><li>UUID</li><li>String</li><li>File</li></ul> |
| Valore       | Il valore della variabile o il nome dell'azione che imposta il valore della variabile. |

### <a name="validate-the-feature-setup"></a>Convalidare la configurazione della funzionalità

- Nella pagina **Configurazione versione funzionalità**, nel riquadro azioni seleziona **Convalida** per convalidare la configurazione della versione della funzionalità.

   ![Selezione del pulsante Convalida](media/e-Invoicing-services-feature-setup-Select-Validate-Button.png)

La convalida verifica la coerenza dell'intera configurazione. Ad esempio, se un parametro specifico per un'azione è obbligatorio ma il suo valore rimane vuoto, la convalida rileva questa incoerenza e viene visualizzato un avviso.

## <a name="environments"></a>Ambienti

Un del componente aggiuntivo per la fatturazione elettronica deve essere associato alla funzionalità del componente aggiuntivo per la fatturazione elettronica e abilitato per essa. Gli ambienti del componente aggiuntivo per la fatturazione elettronica devono essere creati e pubblicati in anticipo, tramite la configurazione delle funzionalità di globalizzazione nell'account RCS della tua organizzazione.

Segui questi passaggi per abilitare un ambiente del componente aggiuntivo per la fatturazione elettronica per la funzionalità del componente aggiuntivo per la fatturazione elettronica.

1. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, nella scheda **Ambienti**, seleziona **Abilita** per aggiungere un ambiente del componente aggiuntivo per la fatturazione elettronica.
2. Nel campo **Valido da**, immetti la data in cui il nuovo ambiente diventa effettivo.

![Abilitazione di un ambiente del componente aggiuntivo per la fatturazione elettronica](media/e-Invoicing-services-feature-setup-Select-Enable-e-Invoicing-feature-Environment.png)

## <a name="organizations"></a>Organizzazioni

La funzionalità del componente aggiuntivo per la fatturazione elettronica può essere condivisa tra più organizzazioni.

- Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, nella scheda **Organizzazioni**, seleziona **Condividi con** per aggiungere l'organizzazione con cui vuoi condividere la funzionalità del componente aggiuntivo per la fatturazione elettronica.

Per interrompere la condivisione della funzionalità del componente aggiuntivo per la fatturazione elettronica con l'organizzazione, seleziona **Annulla condivisione**.

## <a name="versions"></a>Versioni

Le versioni aiutano a controllare il ciclo di vita della funzionalità del componente aggiuntivo per la fatturazione elettronica gestendone lo stato. È possibile creare una nuova versione di una funzionalità del componente aggiuntivo per la fatturazione elettronica esistente oppure, una volta completata tutta la configurazione per la funzionalità del componente aggiuntivo per la fatturazione elettronica, è possibile modificare lo stato della funzionalità in **Completa** e poi in **Pubblica**.

### <a name="create-a-new-version-of-an-existing-electronic-invoicing-add-on-feature"></a>Creare una nuova versione di una funzionalità del componente aggiuntivo per la fatturazione elettronica esistente

1. Nella pagina Funzionalità **del componente aggiuntivo per la fatturazione elettronica**, nella griglia a sinistra, seleziona la funzionalità del componente aggiuntivo per la fatturazione elettronica.
2. Nella scheda **Versioni**, seleziona **Nuovo** per aggiungere una nuova versione della funzionalità del componente aggiuntivo per la fatturazione elettronica.

### <a name="change-the-status-of-the-electronic-invoicing-add-on-feature"></a>Modificare lo stato della funzionalità del componente aggiuntivo per la fatturazione elettronica

Segui questi passaggi per gestire il ciclo di vita della funzionalità del componente aggiuntivo per la fatturazione elettronica.

1. Nella pagina Funzionalità **del componente aggiuntivo per la fatturazione elettronica**, nella griglia a sinistra, seleziona la funzionalità del componente aggiuntivo per la fatturazione elettronica.
2. Nella scheda **Versioni**, seleziona **Cambia stato** e quindi modifica lo stato da **Bozza** a **Completo**.
3. Ti viene chiesto di confermare se desideri completare la funzionalità del componente aggiuntivo per la fatturazione elettronica e tutti i suoi componenti. Seleziona **Sì** per confermare l'azione o **No** per annullare.

    > [!NOTE]
    > Quando selezioni **Sì**, lo stato delle versioni di configurazione, che sono componenti della funzionalità del componente aggiuntivo per la fatturazione elettronica, viene modificato automaticamente da **Bozza** a **Completato**.

4. Seleziona **Cambia stato** e quindi modifica lo stato da **Completo** a **Pubblica**.
5. Ti viene chiesto di confermare se desideri pubblicare la funzionalità del componente aggiuntivo per la fatturazione elettronica e tutti i suoi componenti sul repository globale. Seleziona **Sì** per confermare l'azione o **No** per annullare.

    > [!NOTE]
    > Quando selezioni **Sì**, lo stato delle versioni di configurazione viene modificato automaticamente da **Completato** a **Condiviso**.
