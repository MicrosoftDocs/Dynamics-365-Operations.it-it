---
title: Panoramica dello strumento di creazione di report elettronici
description: Viene fornita una panoramica dello strumento di creazione di report elettronici. Descrive concetti chiave, scenari supportati e formati che fanno parte della soluzione.
author: NickSelin
ms.date: 11/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "58941"
- intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b772acd4a8d0849803cefa8fc14ae3dd6e18831
ms.sourcegitcommit: ac23a0a1f0cc16409aab629fba97dac281cdfafb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/29/2021
ms.locfileid: "7867282"
---
# <a name="electronic-reporting-er-overview"></a>Panoramica dei report elettronici

[!include [banner](../includes/banner.md)]

Viene fornita una panoramica dello strumento di creazione di report elettronici. Sono incluse le informazioni sui concetti chiave e sugli scenari supportati da ER, oltre a un elenco di formati progettati e rilasciati come parte della soluzione.

ER è uno strumento configurabile che ti aiuta a creare e mantenere report e pagamenti elettronici normativi. Si basa sui seguenti tre concetti:

- Configurazione invece di codifica:

    - La configurazione può essere eseguita da un utente aziendale e non richiede uno sviluppatore.
    - Il modello di dati è definito in termini di azienda.
    - Gli editor visivi vengono utilizzati per creare tutti i componenti della configurazione ER.
    - Il linguaggio utilizzato per la trasformazione dei dati è simile al linguaggio utilizzato in Microsoft Excel.

- Una configurazione per più versioni di Dynamics 365 Finance:

    - Gestisci un modello di dati specifico del dominio definito in termini aziendali.
    - Isola i dettagli della versione dell'applicazione nei mapping del modello di dati dipendente dalla versione.
    - Mantieni una configurazione di formato per più rilasci della versione corrente, in base al modello di dati.

- Aggiornamento facile o automatico:

    - il controllo delle versioni delle configurazioni ER è supportato.
    - La libreria dei cespiti Microsoft Dynamics Lifecycle Services (LCS) può essere utilizzata come repository per le configurazioni ER, per lo scambio di versioni.
    - Le localizzazioni basate sulle configurazioni ER originali possono essere introdotte come versioni figlio.
    - Viene fornito un albero di configurazione ER come strumento che aiuta a controllare le dipendenze per le versioni.
    - Le differenze di localizzazione, o configurazione delta, vengono registrate per consentire l'aggiornamento automatico a una nuova versione della configurazione ER originale.
    - È facile risolvere manualmente i conflitti rilevati durante l'aggiornamento automatico delle versioni di localizzazione.

Lo strumento ER ti consente di definire le strutture dei formati elettronici e descrivere come le strutture devono essere riempite usando dati e algoritmi. È possibile utilizzare un linguaggio di formula simile al linguaggio di Excel per la trasformazione dei dati. Per rendere il mapping dal database al formato più gestibile, riutilizzabile e indipendente dalle modifiche al formato, viene introdotto un concetto di modello di dati intermedio. Questo concetto consente di nascondere i dettagli di implementazione dal mapping di formato e consente di riutilizzare un singolo modello di dati per più mapping di formato.

Puoi utilizzare ER per configurare i formati sia dei documenti elettronici in entrata che di quelli in uscita in conformità con i requisiti legali di vari paesi ed aree. ER consente di gestire questi formati durante il ciclo di vita. Ad esempio, è possibile adottare nuovi requisiti normativi e generare documenti aziendali nel formato richiesto per scambiare elettronicamente informazioni con enti governativi, banche o più parti.

Il motore di ER è rivolto agli utenti aziendali anziché agli sviluppatori. Poiché si configurano formati, non il codice, i processi di creazione e modifica di formati per i documenti elettronici sono più veloci e semplici.

ER attualmente supporta i formati di foglio di lavoro TEXT, XML, JSON, PDF, Microsoft Word, Microsoft Excel e OPENXML.

## <a name="capabilities"></a>Capacità

Il motore ER presenta le seguenti funzionalità:

- Rappresenta un unico strumento condiviso per la creazione di report elettronici in diversi domini e sostituisce più di 20 differenti motori impiegati in vari tipi di creazione di report elettronici per Finance and Operations.
- Isola il formato di un report dall'implementazione corrente. (In altre parole, il formato è applicabile per le diverse versioni).
- Supporta la creazione di un formato personalizzato basato su un formato originale. Include inoltre funzionalità per aggiornare automaticamente il formato personalizzato quando vengono apportate modifiche al formato originale a causa dei requisiti di localizzazione/personalizzazione.
- Diventa lo strumento standard principale per il supporto dei requisiti di localizzazione nella creazione di report elettronici, sia per Microsoft che per i partner Microsoft.
- Supporta la possibilità di distribuire formati a partner e clienti tramite Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Concetti chiave

### <a name="main-data-flow"></a>Flusso di dati principale

[![Flusso di dati principale ER.](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="components"></a>Componenti

ER supporta i seguenti tipi di componenti:

- Modello dati
- Mapping modello
- Formattazione
- Metadati

Per ulteriori informazioni, vedere [Componenti di Creazione di report elettronici](er-overview-components.md).


#### <a name="component-versioning"></a>Controllo delle versioni del componente

Il controllo delle versioni è supportato per i componenti ER. Viene fornito il seguente flusso di lavoro per gestire le modifiche nei componenti ER:

1. La versione che viene creata in origine è contrassegnata come versione **Bozza**. Questa versione può essere modificata ed è disponibile per le esecuzioni dei test.
2. La versione **Bozza** può essere convertita in una versione **Completata**. Questa versione può essere utilizzata nei processi di creazione di report locali.
3. La versione **Completata** può essere convertita in una versione **Condivisa**. Questa versione viene pubblicata su LCS e può essere utilizzata nei processi globali di reporting.
4. La versione **Condivisa** può essere convertita in una versione **Interrotta**. Questa versione può quindi essere eliminata.

Le versioni nello stato **Completata** o **Condivisa** sono disponibili per un altro interscambio di dati: Su un componente che dispone di questi stati è possibile eseguire queste azioni:

- Il componente può essere serializzato in formato XML ed esportato come file in formato XML.
- Il componente può essere nuovamente serializzato da un file XML e importato nell'applicazione come nuova versione di un componente di Creazione di report elettronici.

#### <a name="component-date-effectivity"></a>Validità delle date dei componenti

Le versioni dei componenti ER dipendono dalle date. È possibile impostare la data di **Inizio validità** per un componente ER per specificare la data a partire dalla quale il componente diventa valido per i processi di creazione di report. La data della sessione dell'applicazione viene utilizzata per definire se un componente è valido per l'esecuzione. Se più di una versione è valida per una data particolare, la versione più recente viene utilizzata per i processi di creazione di report.

#### <a name="component-access"></a>Accesso ai componenti

L'accesso ai componenti di formato ER dipende dall'impostazione dei codici di paese ISO. Quando questa impostazione è vuota per la versione selezionata di una configurazione di formato, un componente formato è accessibile da qualsiasi società in fase di esecuzione. Quando questa impostazione contiene codici di paese/area ISO, il componente formato è disponibile solo dalle società che hanno un indirizzo principale definito per uno dei codici di paese/area ISO del componente formato.

Versioni differenti di un componente formato dati possono avere impostazioni differenti per i codici di paese ISO.

#### <a name="configuration"></a><a name="Configuration"></a>Configurazione

Una configurazione ER corrisponde al wrapper di un componente ER specifico. Tale componente può essere un componente del modello dati o un componente di formato. Una configurazione può includere versioni diverse di un componente ER. Ciascuna configurazione viene contrassegnata come di proprietà di un provider di una specifica configurazione. La versione **Bozza** di un componente di una configurazione può essere modificata quando il proprietario della configurazione è stato selezionato come provider attivo nelle impostazioni ER dell'applicazione.

Ogni configurazione modello contiene un componente modello dati. Una nuova configurazione formato può derivare da una configurazione modello dati specifica. La configurazione formato che viene creata verrà presentata nella struttura della configurazione come elemento figlio della configurazione modello di dati originale.

La configurazione formato creata contiene un componente formato. Il componente modello dati della configurazione modello originale viene inserito automaticamente nel componente formato della configurazione formato figlio creata come origine dati predefinita.

Una configurazione ER è condivisa per le società dell'applicazione.

#### <a name="provider"></a><a name="Provider"></a>Provider

Il provider ER è l'identificatore della parte che viene utilizzato per indicare l'autore (proprietario) di ciascuna configurazione ER. ER consente di gestire l'elenco di provider di configurazione. Le configurazioni formato rilasciate per documenti elettronici come parte della soluzione Finance and Operations sono contrassegnate come di proprietà del provider di configurazione **Microsoft**.

Per informazioni sulla modalità di registrazione di un nuovo provider ER, riprodurre la Guida attività, **Creazione di report elettronici: creare e attivare un provider di configurazione** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)** ).

#### <a name="repository"></a><a name="Repository"></a>Archivio

In un archivio ER sono archiviate le configurazioni di ER. Attualmente sono supportati i seguenti tipi di archivio di ER: 

- Libreria condivisa LCS
- Progetto LCS
- File system
- RCS
- Risorse Operations
- Archivio globale

Un archivio **Libreria condivisa LCS** consente di accedere all'elenco di configurazioni nella libreria di risorse condivise in Lifecycle Services. Questo tipo di archivio ER può essere registrato solo per i fornitori di Microsoft. Nella libreria di risorse condivise LCS è possibile importare le ultime versioni delle configurazioni ER nell'istanza corrente.

L'archivio **Progetto LCS** consente l'accesso all'elenco delle configurazioni di un determinato progetto LCS (raccolta risorse di progetto LCS) selezionato durante la registrazione dell'archivio. Creazione report elettronici (ER) consente di caricare le configurazioni condivise dall'istanza corrente in uno specifico archivio **Progetto LCS**. È possibile importare configurazioni anche da un archivio **Progetto LCS** nell'istanza corrente delle app Finance and Operations.

Un archivio **File system** consente di accedere all'elenco delle configurazioni presenti come file xml nella cartella specifica del file system locale del computer in cui il servizio AOS è ospitato. La cartella richiesta viene selezionata durante la fase di registrazione dell'archivio. È possibile importare configurazioni da un archivio **File system** nell'istanza corrente. 

Da notare che questo tipo di archivio è accessibile negli ambienti seguenti:

- Gli ambienti ospitati nel cloud distribuiti per scopi di sviluppo (contenenti dei modelli di test di suite incluse)
- Ambienti distribuiti localmente (locali)

Per ulteriori informazioni, vedere [Importare le configurazioni di creazione di report elettronici](./electronic-reporting-import-ger-configurations.md).

L'archivio **RCS** consente l'accesso all'elenco delle configurazioni di una determinata istanza di [Regulatory Configuration Services (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) selezionata nella fase di registrazione dell'archivio. ER consente di importare configurazioni completate o condivise dall'istanza RCS selezionata nell'istanza corrente in modo da poterle utilizzare per la creazione di report elettronici.

Per ulteriori informazioni, vedere [Importare le configurazioni di creazione di report elettronici da RCS](./rcs-download-configurations.md).

Un archivio **Archivio globale** fornisce l'accesso all'elenco di configurazioni all'interno dell'archivio globale in [Regulatory Configuration Service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration). Questo tipo di archivio ER può essere registrato solo per i fornitori di Microsoft. Nell'archivio globale, è possibile importare le ultime versioni delle configurazioni ER nell'istanza corrente.

Per ulteriori informazioni, vedere [Importare le configurazioni di creazione di report elettronici dall'archivio globale di Regulatory Configuration Service (RCS)](./er-download-configurations-global-repo.md).

Un archivio **Risorse operative** consente di accedere all'elenco di configurazioni che Microsoft rilascia inizialmente come parte della soluzione dell'applicazione in qualità di provider di configurazioni ER. Queste configurazioni possono essere importate nell'istanza corrente e utilizzate per la creazione di report elettronici o la riproduzione di guide attività di esempio. Possono inoltre essere utilizzate per altre localizzazioni e personalizzazioni. Tenere presente che le ultime versioni fornite dalle configurazioni ER di Microsoft devono essere importate dalla libreria di risorse condivise LCS utilizzando l'archivio ER corrispondente.

È possibile registrare individualmente gli archivi **Progetto LCS**, **File system** e **Regulatory Configuration Service** richiesti per ciascun provider di configurazioni dell'istanza corrente. Ogni archivio può essere dedicato a un provider di configurazioni specifico.

## <a name="supported-scenarios"></a>Scenari supportati

### <a name="building-a-data-model"></a>Generazione di un modello dati

ER offre una progettazione modello utilizzabile per creare un modello dati per un determinato dominio aziendale. Tutte le entità aziendali specifiche del dominio e le reciproche relazioni possono essere presentate in un modello dati sotto forma di una struttura gerarchica. 

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un modello dati specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="translating-data-model-content"></a>Traduzione del contenuto del modello dati

Il contenuto dei modelli dati (etichette e descrizioni) può essere tradotto in altre lingue che le applicazioni supportano. Si può decidere di tradurre il contenuto dei modelli dati per i seguenti motivi:

- In fase di progettazione, per rendere il contenuto più comprensibile agli sviluppatori di formati che parlano altre lingue e che utilizzeranno un modello dati per il mapping dei dati di componenti formato.
- In fase di esecuzione, per rendere il contenuto più semplice, presentando prompt e assistenza di parametri di runtime e messaggi di convalida configurati (errori e avvisi) nella lingua preferita dall'utente collegato.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configurazione dei mapping del modello dati per i documenti in uscita

ER fornisce una progettazione di mapping di modelli che consente agli utenti di eseguire il mapping di modelli di dati progettati per specifiche origini dati dell'applicazione. In base al mapping, i dati vengono importati in fase di esecuzione da origini dati selezionate nel modello dati. Il modello dati viene quindi utilizzato come origine dati astratta di formati ER che generano i documenti elettronici in uscita. 

Per familiarizzare con i dettagli di questo scenario, eseguire le guide attività **Definire con ER il mapping di modello e selezionare le origini dati** e **Eseguire con ER il mapping del modello dati alle origini dati selezionate** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configurazione dei mapping del modello dati per i documenti in entrata

ER fornisce una progettazione di mapping di modelli che consente agli utenti di eseguire il mapping di modelli di dati progettati per specifiche destinazioni. Ad esempio, i modelli di dati possono essere mappati ai componenti dati aggiornabili (tabelle, entità di dati e visualizzazioni). In base al mapping, i dati vengono aggiornati in fase di esecuzione utilizzando i dati del modello dati. Come archiviazione astratta del formato ER, il modello dati viene compilato con i dati importati da un documento elettronico in entrata. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Archiviazione di un componente di modello progettato come configurazione modello

ER è in grado di archiviare un modello dati progettato insieme ai mapping di dati associati come configurazione di modello dell'istanza corrente. Di seguito viene illustrato un esempio di questo tipo di configurazione modello dati (la configurazione modello dati del dominio pagamenti).

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Eseguire con ER il mapping del modello dati alle origini dati selezionate** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Creare un formato che utilizza un modello dati come base

ER supporta una progettazione formato utilizzabile per creare il formato di un documento elettronico per un dominio aziendale selezionato scegliendo il componente modello come base. La stessa progettazione formato ER offre la possibilità di mappare un formato creato al mapping di modello dati di un dominio selezionato come origine dati. 

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un formato specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Creazione di una configurazione per generare documenti elettronici in formato foglio di lavoro OPENXML

Progettazione formato ER è utilizzabile per creare un documento elettronico in formato foglio di lavoro OPENXML. 

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Creare con ER una configurazione per report in OPENXML** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**). Durante il passaggio della Guida di attività per importare un modello, utilizzare il file di Excel [Modello di Report di pagamento (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) come modello.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Creazione di una configurazione per generare documenti elettronici in formato documento di Word

Progettazione formato ER è utilizzabile per creare un documento elettronico in formato documento di Word. Di seguito viene illustrato un esempio di questo tipo di formato. Questo formato riutilizza la configurazione ER esistente che era originariamente progettata per generare l'output del report in formato OPENXML.

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività ER Progettare una configurazione per la creazione di report nel formato Microsoft WORD (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)). Durante il passaggio della Guida di attività per importare un modello, utilizzare i seguenti file di Word come modelli per il formato ER:

- [Modello di Report di pagamento (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Modello associato di Report di pagamento (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Sviluppo di una configurazione per importare i dati dai documenti elettronici in entrata

Progettazione formato ER può essere utilizzato per descrivere un documento elettronico appositamente progettato per l'importazione di dati in formato XML o testo. Il formato progettato viene utilizzato per analizzare un documento in entrata. Progettazione mapping di formato ER può essere utilizzato per definire l'associazione degli elementi del formato progettato al modello dati. 

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività Creare le configurazioni richieste per importare dati da un file esterno (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)). Utilizzare i seguenti file per riprodurre questa guida:

- [Configurazione del modello dati ER (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [Configurazione del formato ER (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Esempio di documento in entrata in formato XML (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Esempio di cartella di lavoro per la gestione dei dati del documento in entrata (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Archiviazione di un componente formato progettato in una configurazione di formato

ER è in grado di archiviare un formato progettato insieme ai mapping di dati configurati come configurazione di formato dell'istanza corrente. Nell'illustrazione precedente viene illustrato un esempio di questo tipo di configurazione di formato (**BACS (UK)**, che è figlio della configurazione **modello di pagamento**). Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un formato specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>Configurazione di Finance per utilizzare internamente un formato creato

È possibile configurare l'applicazione in modo da iniziare a utilizzare un formato creato per la generazione di report elettronici. Il riferimento alla configurazione di formato creata deve essere definito nelle impostazioni di uno specifico dominio. Ad esempio, per iniziare a utilizzare una configurazione di formato ER per i pagamenti elettronici ai fornitori in formato il BACS, occorre fare riferimento alla configurazione di formato in specifici metodi di pagamento.

Per familiarizzare con i dettagli di questo scenario, eEseguire la guida attività **Utilizzare il formato ER per generare documenti elettronici per i pagamenti** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

## <a name="handling-er-components"></a>Gestione dei componenti ER

### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Pubblicazione di un componente ER in LCS per offrirlo esternamente (localizzazione)

Il proprietario di un componente (modello o formato) creato può utilizzare ER per pubblicare la versione completata del componente in LCS. A tal fine è necessario avere un archivio di tipo **Progetto LCS** per il provider della configurazione ER corrente. Quando lo stato della versione completata di un componente viene modificato da **COMPLETATO** a **CONDIVISO**, questa versione viene pubblicata in LCS. Una volta che un componente è stato pubblicato in LCS, il proprietario del componente diventa un provider del servizio di supporto al componente. Ad esempio, se questo componente di formato è progettato per generare un documento elettronico legale necessario (ad esempio, in accordo con uno scenario di localizzazione), si presuppone che il formato venga mantenuto conforme alle modifiche legislative e che il provider emetterà nuove versioni del componente ogni volta che sorgono nuovi requisiti legislativi. Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Caricare con ER una configurazione in Lifecyle Services** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importazione di un componente ER da LCS per uso interno

ER consente di importare componenti ER da LCS all'istanza corrente. È necessario disporre di un archivio di tipo **Progetto LCS**. Quando un componente ER è stato importato da LCS nell'istanza corrente, il proprietario dell'istanza diventa un utente del servizio che viene fornito dal proprietario (autore) del componente importato. Ad esempio, se un componente di formato è progettato per generare uno specifico documento elettronico dall'applicazione in un formato specifico di paese (scenario di localizzazione), si presuppone che l'utente del servizio potrà ottenere tutti gli aggiornamenti fatti al formato per mantenerlo conforme ai requisiti legislativi. Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Importare con ER una configurazione da Lifecyle Services** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Creazione di un formato selezionando un altro formato come base (personalizzazione)

ER consente di creare (derivare) un nuovo componente della versione corrente di un componente (base) che è stato importato da LCS. Ad esempio, un utente desidera derivare un nuovo formato per implementare alcuni requisiti speciali per un documento elettronico (ad esempio un campo aggiuntivo o una descrizione completa) per supportare uno scenario di personalizzazione. Per familiarizzare con i dettagli di questo scenario, eseguire la guida attività **Aggiornare con ER il formato tramite l'adozione di una nuova versione di base dello stesso formato** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Aggiornamento di un formato tramite la selezionare una nuova versione del formato di base (rebase)

ER consente di adottare automaticamente le modifiche alla versione più recente del componente di base nella versione bozza corrente del componente derivato. Questo processo è noto come *riassegnazione*. Ad esempio, le modifiche richieste da nuove normative introdotte nella versione più recente del componente di formato importato da LCS possono essere automaticamente unite nella versione personalizzata del formato del documento elettronico. Le modifiche che non possono essere unite automaticamente vengono considerate conflitti. Questi conflitti sono presentati per la risoluzione manuale nello strumento di progettazione per il componente appropriato. Per familiarizzare con i dettagli di questo scenario, eseguire la guida attività **Aggiornare con ER il formato tramite l'adozione di una nuova versione di base dello stesso formato** (parte del processo aziendale **7.5.5.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10683)**).

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Elenco delle configurazioni ER che sono state rilasciate in Finance

L'elenco delle configurazioni di report elettronici per Finance viene costantemente aggiornato. Apri il [repository globale](er-download-configurations-global-repo.md) per rivedere l'elenco delle configurazioni di report elettronici attualmente supportate. Nella Scheda dettaglio **Dettagli di interruzione**, è possibile rivedere le informazioni sulle configurazioni che sono state interrotte o che non vengono più mantenute. 

![Contenuto dell'archivio globale nella pagina Archivio di configurazione.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Creare configurazioni per la creazione di report elettronici](electronic-reporting-configuration.md)
- [Gestire il ciclo di vita della configurazione per la creazione di report elettronici (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
