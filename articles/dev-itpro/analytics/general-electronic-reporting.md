---
title: Creazione di report elettronici (ER)
description: Viene fornita una panoramica dello strumento di creazione di report elettronici. Sono incluse le informazioni sui concetti chiave e sugli scenari supportati da ER, oltre a un elenco di formati progettati e rilasciati come parte della soluzione.
author: NickSelin
manager: AnnBe
ms.date: 03/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc544211891c19104b2b3cb704b55a074784d608
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1505986"
---
# <a name="electronic-reporting-er"></a>Creazione di report elettronici (ER)

[!include [banner](../includes/banner.md)]

Viene fornita una panoramica dello strumento di creazione di report elettronici. Sono incluse le informazioni sui concetti chiave e sugli scenari supportati da ER, oltre a un elenco di formati progettati e rilasciati come parte della soluzione.

Creazione di report elettronici è uno strumento che è possibile utilizzare per configurare i formati sia dei documenti elettronici in entrata che di quelli in uscita in conformità con i requisiti legali di vari paesi o aree. ER consente di gestire questi formati durante il ciclo di vita. Ad esempio, è possibile adottare nuovi requisiti normativi e generare documenti aziendali nel formato richiesto per scambiare elettronicamente informazioni con enti governativi, banche e altre parti.

Il motore di ER è rivolto agli utenti aziendali anziché agli sviluppatori. Poiché si configurano formati, non il codice, i processi di creazione e modifica di formati per i documenti elettronici sono più veloci e semplici.

ER attualmente supporta i formati di foglio di lavoro TEXT, XML, documento di Microsoft Word e OPENXML. Tuttavia, un'interfaccia di estensione fornisce supporto per formati aggiuntivi.

## <a name="capabilities"></a>Capacità
Il motore ER presenta le seguenti funzionalità:

- Rappresenta un unico strumento condiviso per la creazione di report elettronici in diversi domini e sostituisce più di 20 differenti motori impiegati in vari tipi di creazione di report elettronici per Microsoft Dynamics 365 for Finance and Operations.
- Isola il formato di un report dall'attuale implementazione di Finance and Operations. In altre parole, il formato è applicabile a versioni diverse di Finance and Operations.
- Supporta la creazione di un formato personalizzato basato su un formato originale. Include inoltre funzionalità per aggiornare automaticamente il formato personalizzato quando vengono apportate modifiche al formato originale a causa dei requisiti di localizzazione/personalizzazione.
- Diventa lo strumento standard principale per il supporto dei requisiti di localizzazione nella creazione di report elettronici, sia per Microsoft che per i partner Microsoft.
- Supporta la possibilità di distribuire formati a partner e clienti tramite Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Concetti chiave
### <a name="components"></a>Componenti

ER supporta due tipi di componenti: **Modello dati** e **Formato**.

#### <a name="data-model-components"></a>Componenti modello dati

Il componente modello dati è una rappresentazione astratta di una struttura dati. È utilizzata per descrivere un'area specifica del dominio aziendale con sufficienti dettagli per soddisfare le esigenze di reporting del dominio. Un componente modello dati è costituito dalle seguenti parti:

- Un modello dati come set di entità aziendali specifiche del dominio e una definizione con struttura gerarchica delle relazioni tra tali entità.
- Un mapping di modelli che collega specifiche origini dati di Finance and Operations a singoli elementi di un modello dati che specifica, in fase di esecuzione, il flusso di dati e le regole di inserimento dei dati aziendali in un componente modello dati.

Un'entità aziendale di un modello dati è rappresentata come contenitore (record). Le proprietà dell'entità aziendale sono rappresentate come elementi dati (campi). Ciascun elemento di dati dispone di un nome, un'etichetta, una descrizione e un valore univoci. Il valore di ogni elemento di dati può essere progettato in modo che venga riconosciuto come stringa, intero, reale, data, enumerazione, booleano e così via. Inoltre, può essere un altro record o elenco di record.

Un singolo componente modello dati può contenere più gerarchie di entità aziendali specifiche del dominio. Può inoltre contenere i mapping di modello che supportano un flusso di dati specifico di un report in fase di esecuzione. Le gerarchie vengono differenziate da un singolo record che è stato selezionato come radice del mapping di modello. Ad esempio, il modello dati dell'area del dominio pagamenti può supportare i mapping seguenti:

- Società \> Fornitore -\> Transazioni di pagamento del dominio Contabilità fornitori
- Cliente \> Società -\> Transazioni di pagamento del dominio Contabilità clienti

Si noti che le entità aziendali (ad esempio società e transazioni di pagamento) vengono progettate una volta. Diversi mapping quindi le riutilizzano.

Un mapping di modello che supporta documenti elettronici in uscita ha le seguenti funzionalità:

- È possibile utilizzare tipi diversi di dati di Finance and Operations come origini dati per un modello dati. Ad esempio, è possibile utilizzare le tabelle, le entità di dati, metodi o le enumerazioni.
- Supporta parametri di input dell'utente che possono essere definiti ome origini dati del modello dati quando è necessario specificare alcuni dati in fase di esecuzione.
- Supporta la trasformazione di dati di Finance and Operations in gruppi richiesti. È inoltre possibile filtrare, ordinare e sommare i dati e aggiungere i campi calcolati logici progettati tramite formule simili alle formule di Microsoft Excel, come illustrato nella figura seguente. Per ulteriori informazioni, vedere [Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md).

[![Designer formula](./media/ER-overview-01.png)](./media/ER-overview-01.png)

Un mapping di modello che supporta documenti elettronici in entrata ha le seguenti funzionalità:

- Può includere elementi di dati aggiornabili diversi come obiettivi. Questi elementi dati includono tabelle, entità di dati e visualizzazioni. I dati possono essere aggiornati utilizzando i dati dei documenti elettronici in entrata. Diverse destinazioni possono essere utilizzate in un singolo mapping di modelli.
- Supporta parametri di input dell'utente che possono essere definiti ome origini dati del modello dati quando è necessario specificare alcuni dati in fase di esecuzione.

Un componente del modello dati è progettato per ciascun dominio aziendale da utilizzare come origine dati unificata per la creazione di report che isola la creazione di report dall'implementazione fisica delle origini dati. Rappresenta i concetti e le funzionalità aziendali specifici del dominio in una forma che rende più efficiente la progettazione iniziale dei formati di report e la successiva manutenzione.

#### <a name="format-components-for-outgoing-electronic-documents"></a>Componenti di formato per i documenti elettronici in uscita

Un componente formato è lo schema dell'output della creazione di report che sarà generato in fase di esecuzione. Uno schema comprende i seguenti elementi:

- Un formato che definisce la struttura e il contenuto del documento elettronico in uscita generato in fase di esecuzione.
- Origini dati come set di parametri di input dell'utente e un modello dati specifico del dominio che usa un mapping di modello selezionato
- Un mapping di formato come set di associazioni di origini dati di formato che hanno singoli elementi di un formato che specificano in fase di esecuzione il flusso di dati e le regole per la generazione dell'output del formato.
- Una convalida del formato come set di regole configurabili che controllano la creazione di report in fase di esecuzione a seconda del contesto di esecuzione. Ad esempio, una regola che interrompe la generazione dell'output dei pagamenti di un fornitore e genera un'eccezione quando gli attributi specifici del fornitore selezionato sono mancanti, quali il numero di conto corrente bancario.

Un componente formato supporta le seguenti funzioni:

- Creazione di output di report come singoli file in diversi formati, ad esempio testo, XML, documento di Microsoft Word o foglio di lavoro.
- Creazione di più file separatamente e incapsulamento di tali file in file zip.

Un componente formato consente di allegare file specifici che possono essere utilizzati nell'output di report:

- Cartekke di lavoro di Excel che contengono un foglio di lavoro utilizzabile come modello per output nel formato foglio di lavoro OPENXML.
- I file di Word che contengono un documento utilizzabile come modello per output nel formato documento di Microsoft Word.
- Altri file che è possibile incorporare nell'output del formato come file predefiniti.

Nella figura seguente viene illustrato il flusso dei dati per questi formati.

[![Flusso di dati per i componenti di formato in uscita](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Per eseguire una singola configurazione di formato ER e generare un documento elettronico in uscita, è necessario identificare il mapping della configurazione di formato.

#### <a name="format-components-for-incoming-electronic-documents"></a>Componenti di formato per i documenti elettronici in entrata
Un componente di formato è lo schema del documento in entrata importato in fase di esecuzione. Uno schema comprende i seguenti elementi:

- Un formato che definisce la struttura e il contenuto del documento elettronico in entrata contenente i dati importati in fase di esecuzione. Un componente di formato viene utilizzato per analizzare un documento in entrata in vari formati, ad esempio testo e XML.
- Un mapping di formato che associa i singoli elementi di formato agli elementi di un modello dati specifico del dominio. In fase di esecuzione, gli elementi del modello dati specificano il flusso di dati e le regole per importare i dati da un documento in entrata e quindi archiviare i dati in un modello dati.
- Una convalida del formato come set di regole configurabili che controllano l'importazione dei dati in fase di esecuzione a seconda del contesto di esecuzione. Ad esempio, una regola che interrompe l'importazione dati di un rendiconto bancario con pagamenti di un fornitore e genera un'eccezione quando gli attributi di uno specifico fornitore sono mancanti, quali il codice di identificazione del fornitore.

Nella figura seguente viene illustrato il flusso dei dati per questi formati.

[![Flusso di dati per i componenti di formato in entrata](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Per eseguire una singola configurazione di formato ER per importare i dati di un documento elettronico in entrata, è necessario identificare il mapping desiderato di una configurazione di formato e il punto di integrazione di un mapping di modello. È possibile utilizzare lo stesso mapping di modello e le destinazioni con i diversi formati per tipi diversi di documenti in entrata.

#### <a name="component-versioning"></a>Controllo delle versioni del componente

Il controllo delle versioni è supportato per i componenti ER. Viene fornito il seguente flusso di lavoro per gestire le modifiche nei componenti ER:

1. La versione che viene creata in origine è contrassegnata come versione **Bozza**. Questa versione può essere modificata ed è disponibile per le esecuzioni dei test.
2. La versione **Bozza** può essere convertita in una versione **Completata**. Questa versione può essere utilizzata nei processi di creazione di report locali.
3. La versione **Completata** può essere convertita in una versione **Condivisa**. Questa versione viene pubblicata su LCS e può essere utilizzata nei processi globali di reporting.
4. La versione **Condivisa** può essere convertita in una versione **Interrotta**. Questa versione può quindi essere eliminata.

Le versioni nello stato **Completata** o **Condivisa** sono disponibili per un altro interscambio di dati: Su un componente che dispone di questi stati è possibile eseguire queste azioni:

- Il componente può essere serializzato in formato XML ed esportato come file in formato XML.
- Il componente può essere nuovamente serializzato da un file XML e importato in Finance and Operations come nuova versione di un componente di Creazione di report elettronici.

#### <a name="component-date-effectivity"></a>Validità delle date dei componenti

Le versioni dei componenti ER dipendono dalle date. È possibile impostare la data di **Inizio validità** per un componente ER per specificare la data a partire dalla quale il componente diventa valido per i processi di creazione di report. La data della sessione di Finance and Operations viene utilizzata per definire se un componente è valido per l'esecuzione. Se più di una versione è valida per una data particolare, la versione più recente viene utilizzata per i processi di creazione di report.

#### <a name="component-access"></a>Accesso ai componenti

L'accesso ai componenti di formato ER dipende dall'impostazione dei codici di paese ISO. Quando questa impostazione è vuota per la versione selezionata di una configurazione di formato, un componente formato è accessibile da qualsiasi società in fase di esecuzione. Quando questa impostazione contiene codici di paese/area ISO, il componente formato è disponibile solo dalle società che hanno un indirizzo principale definito per uno dei codici di paese/area ISO del componente formato.

Versioni differenti di un componente formato dati possono avere impostazioni differenti per i codici di paese ISO.

#### <a name="configuration"></a>Configurazione

Una configurazione ER corrisponde al wrapper di un componente ER specifico. Tale componente può essere un componente del modello dati o un componente di formato. Una configurazione può includere versioni diverse di un componente ER. Ciascuna configurazione viene contrassegnata come di proprietà di un provider di una specifica configurazione. La versione **Bozza** di un componente di una configurazione può essere modificata quando il proprietario della configurazione è stato selezionato come provider attivo nelle impostazioni di Creazione di report elettronici in Finance and Operations.

Ogni configurazione modello contiene un componente modello dati. Una nuova configurazione formato può derivare da una configurazione modello dati specifica. La configurazione formato che viene creata verrà presentata nella struttura della configurazione come elemento figlio della configurazione modello di dati originale.

La configurazione formato creata contiene un componente formato. Il componente modello dati della configurazione modello originale viene inserito automaticamente nel componente formato della configurazione formato figlio creata come origine dati predefinita.

Una configurazione di Creazione di report elettronici è condivisa per le società Finance and Operations.

#### <a name="provider"></a>Provider

Il provider ER è l'identificatore della parte che viene utilizzato per indicare l'autore (proprietario) di ciascuna configurazione ER. ER consente di gestire l'elenco di provider di configurazione. Le configurazioni di formato rilasciate per documenti elettronici come parte della soluzione Finance and Operations sono contrassegnate come di proprietà del provider di configurazione **Microsoft**.

Per informazioni sulla modalità di registrazione di un nuovo provider ER, riprodurre la Guida attività, **Creazione di report elettronici: creare e attivare un provider di configurazione** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)** ).

#### <a name="repository"></a>Archivio

In un archivio ER sono archiviate le configurazioni di ER. Attualmente sono supportati i seguenti tipi di archivio di ER: 

- Libreria condivisa LCS
- Progetto LCS
- File system
- Regulatory Configuration Services (RCS)
- Risorse operative


Un archivio **Libreria condivisa LCS** consente di accedere all'elenco di configurazioni nella libreria di risorse condivise in Lifecycle Services. Questo tipo di archivio ER può essere registrato solo per i fornitori di Microsoft. Nella libreria di risorse condivise LCS è possibile importare le ultime versioni delle configurazioni ER nell'istanza di Finance and Operations.

L'archivio **Progetto LCS** consente l'accesso all'elenco delle configurazioni di un determinato progetto LCS (raccolta risorse di progetto LCS) selezionato alla fase di registrazione archivio. Creazione report elettronici (ER) consente di caricare le configurazioni condivise dall'istanza corrente di Finance and Operations in uno specifico archivio **Progetto LCS**. È possibile importare configurazioni anche da un archivio **Progetto LCS** nell'istanza corrente di Finance and Operations.

Un archivio **File system** consente di accedere all'elenco delle configurazioni presenti come file xml nella cartella specifica del file system locale del computer in cui il servizio AOS è ospitato. La cartella richiesta viene selezionata durante la fase di registrazione dell'archivio. È possibile importare configurazioni da un archivio **File system** nell'istanza corrente di Finance and Operations. 

Da notare che questo tipo di archivio è accessibile negli ambienti Dynamics 365 for Finance and Operations seguenti:

- Gli ambienti ospitati nel cloud distribuiti per scopi di sviluppo (contenenti dei modelli di test di suite incluse)
- Ambienti distribuiti localmente (locali)

Per ulteriori informazioni, vedere [Importare le configurazioni di creazione di report elettronici](./electronic-reporting-import-ger-configurations.md).

L'archivio **Istanza LCS** consente l'accesso all'elenco delle configurazioni di una determinata istanza RCS selezionata nella fase di registrazione dell'archivio. ER consente di importare configurazioni completate o condivise dall'istanza RCS selezionata nell'istanza di Finance and Operations corrente in modo da poterle utilizzare per la creazione di report elettronici.

Per ulteriori informazioni, vedere [Importare le configurazioni di creazione di report elettronici da Regulatory Configuration Service (RCS)](./rcs-download-configurations.md).

Un archivio **Risorse operative** consente di accedere all'elenco di configurazioni che Microsoft rilascia inizialmente come parte della soluzione Finance and Operations in qualità di provider di configurazioni ER. Queste configurazioni possono essere importate nell'istanza corrente di Finance and Operations e utilizzate per la creazione di report elettronici o la riproduzione di guide di attività di esempio. Possono inoltre essere utilizzate per altre localizzazioni e personalizzazioni. Tenere presente che le ultime versioni fornite dalle configurazioni ER di Microsoft devono essere importate dalla libreria di risorse condivise LCS utilizzando l'archivio ER corrispondente.

È possibile registrare individualmente gli archivi **Progetto LCS**, **File system** e **Servizi di configurazione normativa (RCS)** richiesti per ciascun provider di configurazioni dell'istanza corrente di Finance and Operations. Ogni archivio può essere dedicato a un provider di configurazioni specifico.

## <a name="supported-scenarios"></a>Scenari supportati
### <a name="building-a-data-model"></a>Generazione di un modello dati

ER offre una progettazione modello utilizzabile per creare un modello dati per un determinato dominio aziendale. Tutte le entità aziendali specifiche del dominio e le reciproche relazioni possono essere presentate in un modello dati sotto forma di una struttura gerarchica. Di seguito viene illustrato un esempio di questo tipo di modello dati (il modello dati del dominio pagamenti).

[![Modello dati del dominio di pagamento](./media/ER-overview-04.png)](./media/ER-overview-04.png)

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un modello dati specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="translating-data-model-content"></a>Traduzione del contenuto del modello dati

Il contenuto dei modelli dati (etichette e descrizioni) può essere tradotto in altre lingue supportate da Finance and Operations. Si può decidere di tradurre il contenuto dei modelli dati per i seguenti motivi:

- In fase di progettazione, per rendere il contenuto più comprensibile agli sviluppatori di formati che parlano altre lingue e che utilizzeranno un modello dati per il mapping dei dati di componenti formato.
- In fase di esecuzione, per rendere il contenuto più semplice, presentando prompt e assistenza di parametri di runtime e messaggi di convalida configurati (errori e avvisi) nella lingua preferita dall'utente collegato.

Nella figura seguente viene riportato un esempio di come il contenuto del modello dati può essere tradotto dall'inglese al giapponese.

[![Contenuto del modello dati in inglese](./media/ER-overview-05.png)](./media/ER-overview-05.png)

[![Contenuto del modello dati tradotto in giapponese](./media/ER-overview-06.png)](./media/ER-overview-06.png)

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configurazione dei mapping del modello dati per i documenti in uscita

ER fornisce una progettazione di mapping di modelli che consente agli utenti di eseguire il mapping di modelli di dati progettati per specifiche origini dati di  Finance and Operations. In base al mapping, i dati vengono importati in fase di esecuzione da origini dati selezionate nel modello dati. Il modello dati viene quindi utilizzato come origine dati astratta di formati ER che generano i documenti elettronici in uscita. Nell'illustrazione riportata di seguito viene mostrato un esempio di questo tipo di mapping di modelli dati (mapping del modello **Bonifico SEPA** del modello dati del dominio pagamenti).

[![Esempio di mapping di modello dati](./media/ER-overview-07.png)](./media/ER-overview-07.png)

Per familiarizzare con i dettagli di questo scenario, eseguire le guide attività **Definire con ER il mapping di modello e selezionare le origini dati** e **Eseguire con ER il mapping del modello dati alle origini dati selezionate** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configurazione dei mapping del modello dati per i documenti in entrata
ER fornisce una progettazione di mapping di modelli che consente agli utenti di eseguire il mapping di modelli di dati progettati per specifiche destinazioni. Ad esempio, i modelli di dati possono essere mappati ai componenti dati aggiornabili di Finance and Operations (tabelle, entità di dati e visualizzazioni). In base al mapping, i dati di Finance and Operations vengono aggiornati in fase di esecuzione utilizzando i dati del modello dati. Come archiviazione astratta del formato ER, il modello dati viene compilato con i dati importati da un documento elettronico in entrata. Di seguito viene illustrato un esempio di questo tipo di mapping di modello dati. In questo esempio, il mapping di modello **Importazione mapping per NETS** del modello dati del dominio di pagamento viene utilizzato per supportare l'importazione dei rendiconti bancari nel formato della banca NETS per la Norvegia.

[![Importazione mapping per il modello dati NETS di esempio](./media/ER-overview-08.png)](./media/ER-overview-08.png)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Archiviazione di un componente di modello progettato come configurazione modello

ER è in grado di archiviare un modello dati progettato insieme ai mapping di dati associati come configurazione di modello dell'istanza corrente di Finance and Operations. Di seguito viene illustrato un esempio di questo tipo di configurazione modello dati (la configurazione modello dati del dominio pagamenti).

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Eseguire con ER il mapping del modello dati alle origini dati selezionate** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Creare un formato che utilizza un modello dati come base

ER supporta una progettazione formato utilizzabile per creare il formato di un documento elettronico per un dominio aziendale selezionato scegliendo il componente modello come base. La stessa progettazione formato ER offre la possibilità di mappare un formato creato al mapping di modello dati di un dominio selezionato come origine dati. Di seguito viene illustrato un esempio di questo tipo di formato (la configurazione di formato che supporta il formato di pagamento **BACS** iper il Regno Unito).

[![Esempio di un formato che ha un modello dati come base](./media/ER-overview-09.png)](./media/ER-overview-09.png)

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un formato specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Creazione di una configurazione per generare documenti elettronici in formato foglio di lavoro OPENXML

Progettazione formato ER è utilizzabile per creare un documento elettronico in formato foglio di lavoro OPENXML. Di seguito viene illustrato un esempio di questo tipo di formato (una configurazione di formato per generare foglio di lavoro OPENXML con dettagli del giornale di registrazione pagamenti selezionato).

[![Pic-ER-format-Excel](./media/ER-overview-10.png)](./media/ER-overview-10.png)

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Creare con ER una configurazione per report in OPENXML** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**). Durante il passaggio della Guida di attività per importare un modello, utilizzare il file di Excel [Modello di Report di pagamento (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) come modello.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Creazione di una configurazione per generare documenti elettronici in formato documento di Word
Progettazione formato ER è utilizzabile per creare un documento elettronico in formato documento di Word. Di seguito viene illustrato un esempio di questo tipo di formato. Questo formato riutilizza la configurazione ER esistente che era originariamente progettata per generare l'output del report in formato OPENXML.

[![Pic-ER-format-Word](./media/ER-overview-11.png)](./media/ER-overview-11.png)

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività ER Progettare una configurazione per la creazione di report nel formato Microsoft WORD (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)). Durante il passaggio della Guida di attività per importare un modello, utilizzare i seguenti file di Word come modelli per il formato ER:

- [Modello di Report di pagamento (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Modello associato di Report di pagamento (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Sviluppo di una configurazione per importare i dati dai documenti elettronici in entrata
Progettazione formato ER può essere utilizzato per descrivere un documento elettronico appositamente progettato per l'importazione di dati in formato XML o testo. Il formato progettato viene utilizzato per analizzare un documento in entrata. Progettazione mapping di formato ER può essere utilizzato per definire l'associazione degli elementi del formato progettato al modello dati. Di seguito viene illustrato un esempio di questo tipo di formato e mapping di formato. In questo esempio, vengono importati i rendiconti bancari di NETS che includono i datti dei pagamenti fornitore in formato testo.

[![ER-format-designer](./media/ER-overview-12.png)](./media/ER-overview-12.png)

[![ER-model-mapping-designer](./media/ER-overview-13.png)](./media/ER-overview-13.png)

Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività Creare le configurazioni richieste per importare dati da un file esterno (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)). Utilizzare i seguenti file per riprodurre questa guida:

- [Configurazione del modello dati ER (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Configurazione del formato ER (1099format.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Esempio di documento in entrata in formato XML (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Esempio di cartella di lavoro per la gestione dei dati del documento in entrata (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Archiviazione di un componente formato progettato in una configurazione di formato

ER è in grado di archiviare un formato progettato insieme ai mapping di dati configurati come configurazione di formato dell'istanza corrente di Finance and Operations. Nell'illustrazione precedente viene illustrato un esempio di questo tipo di configurazione di formato (**BACS (UK)**, che è figlio della configurazione **modello di pagamento**). Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un formato specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="configuring-finance-and-operations-to-start-to-use-a-created-format-internally"></a>Configurazione di Finance and Operations per utilizzare internamente un formato creato

È possibile configurare Finance and Operations in modo da iniziare a utilizzare un formato creato per la generazione di report elettronici. Il riferimento alla configurazione di formato creata deve essere definito nelle impostazioni di uno specifico dominio. Ad esempio, per iniziare a utilizzare una configurazione di formato ER per i pagamenti elettronici ai fornitori in formato il BACS, occorre fare riferimento alla configurazione di formato in specifici metodi di pagamento, come mostrato nelle illustrazioni seguenti:

[![Configurazione formato BACS (UK)](./media/ER-overview-14.png)](./media/ER-overview-14.png)

[![Riferimento al formato BACS (UK) in un metodo di pagamento](./media/ER-overview-15.png)](./media/ER-overview-15.png)

Per familiarizzare con i dettagli di questo scenario, eEseguire la guida attività **Utilizzare il formato ER per generare documenti elettronici per i pagamenti** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

## <a name="handling-er-components"></a>Gestione dei componenti ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Pubblicazione di un componente ER in LCS per offrirlo esternamente (localizzazione)

Il proprietario di un componente (modello o formato) creato può utilizzare ER per pubblicare la versione completata del componente in LCS. A tal fine è necessario avere un archivio di tipo **Progetto LCS** per il provider della configurazione ER corrente. Quando lo stato della versione completata di un componente viene modificato da **COMPLETATO** a **CONDIVISO**, questa versione viene pubblicata in LCS. Una volta che un componente è stato pubblicato in LCS, il proprietario del componente diventa un provider del servizio di supporto al componente. Ad esempio, se questo componente di formato è progettato per generare un documento elettronico legale necessario (ad esempio, in accordo con uno scenario di localizzazione), si presuppone che il formato venga mantenuto conforme alle modifiche legislative e che il provider emetterà nuove versioni del componente ogni volta che sorgono nuovi requisiti legislativi. Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Caricare con ER una configurazione in Lifecyle Services** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importazione di un componente ER da LCS per uso interno

ER consente di importare componenti ER da LCS all'istanza corrente di Finance and Operations. È necessario disporre di un archivio di tipo **Progetto LCS**. Quando un componente ER è stato importato da LCS nell'istanza corrente di Finance and Operations, il proprietario dell'istanza diventa un utente del servizio che viene fornito dal proprietario (autore) del componente importato. Ad esempio, se un componente di formato è progettato per generare uno specifico documento elettronico da Finance and Operations in un formato specifico di paese (scenario di localizzazione), si presuppone che l'utente del servizio potrà ottenere tutti gli aggiornamenti fatti al formato per mantenerlo conforme ai requisiti legislativi. Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Importare con ER una configurazione da Lifecyle Services** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Creazione di un formato selezionando un altro formato come base (personalizzazione)

ER consente di creare (derivare) un nuovo componente della versione corrente di un componente (base) che è stato importato da LCS. Ad esempio, un utente desidera derivare un nuovo formato per implementare alcuni requisiti speciali per un documento elettronico (ad esempio un campo aggiuntivo o una descrizione completa) per supportare uno scenario di personalizzazione. Per familiarizzare con i dettagli di questo scenario, eseguire la guida attività **Aggiornare con ER il formato tramite l'adozione di una nuova versione di base dello stesso formato** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Aggiornamento di un formato tramite la selezionare una nuova versione del formato di base (rebase)

ER consente di adottare automaticamente le modifiche alla versione più recente del componente di base nella versione bozza corrente del componente derivato. Questo processo è noto come *riassegnazione*. Ad esempio, le modifiche richieste da nuove normative introdotte nella versione più recente del componente di formato importato da LCS possono essere automaticamente unite nella versione personalizzata del formato del documento elettronico. Le modifiche che non possono essere unite automaticamente vengono considerate conflitti. Questi conflitti sono presentati per la risoluzione manuale nello strumento di progettazione per il componente appropriato. Per familiarizzare con i dettagli di questo scenario, eseguire la guida attività **Aggiornare con ER il formato tramite l'adozione di una nuova versione di base dello stesso formato** (parte del processo aziendale **7.5.5.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10683)**).

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-and-operations-solution"></a>Elenco delle configurazioni ER fornite nella soluzione Finance and Operations

| Configurazioni modello dati specifiche di dominio: titolo | Dominio                | Configurazioni formato dipendenti da modello dati: titolo | Descrizione                                                        |
|--------------------------------------------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------|
| Modello file di controllo                                 | Revisione contabile       |                                                   |                                                                    |
|                                                  |                       | File di controllo (NL)                                   | Formato file di controllo per i Paesi Bassi                                  |
| Modello BAS                                        | Dichiarazione imposte         |                                                   |                                                                    |
|                                                  |                       | BAS (AU)                                          | Formato BAS per l'Australia                                           |
| Modello CIS               | Dichiarazione imposte         |                                                   |                                                                    |
|                                                  |                       | Dichiarazione mensile CIS (UK)                           | Formato dichiarazione mensile CIS per il Regno Unito                   |
| Modello lettera di sollecito                          | Fatture elettroniche  |                                                   |                                                                    |
|                                                  |                       | Lettera di sollecito OIOUBL (DK)                     | Formato di lettera di sollecito OIOUBL per la Danimarca                        |
| Modello conto CoGe elettronico (MX)          | Dichiarazione imposte         |                                                   |                                                                    |
|                                                  |                       | Contabilità generale ausiliaria XML (MX)                         | Formato di report per transazioni di contabilità ausiliaria per singolo conto per il Messico |
|                                                  |                       | Piano dei conti XML (MX)                         | Formato di report piano dei conti per il Messico                          |
|                                                  |                       | Giornali di registrazione XML (MX)                                 | Formato di report giornale di registrazione transazioni per il Messico                      |
|                                                  |                       | Bilancio di verifica XML (MX)                            | Formato di report bilancio di verifica per il Messico                             |
| Modello ELSTER                                     | Dichiarazione imposte         |                                                   |                                                                    |
|                                                  |                       | Elster (DE)                                       | Formato ELSTER per la Germania                                          |
| Modello elenco vendite UE                              | Notifica scambi commerciali       |                                                   |                                                                    |
|                                                  |                       | Elenco vendite UE (DE)                                | Formato TXT elenco vendite UE per la Germania                               |
|                                                  |                       | Elenco vendite UE (DK)                                | Formato TXT elenco vendite UE per la Danimarca                               |
|                                                  |                       | Elenco vendite UE (FR)                                | Formato XML elenco vendite UE per la Francia                                |
|                                                  |                       | Elenco vendite UE (NL)                                | Formato XML elenco vendite UE per i Paesi Bassi                           |
|                                                  |                       | Elenco vendite UE TXT (UK)                            | Formato TXT elenco vendite UE per il Regno Unito                    |
|                                                  |                       | Elenco vendite UE XML (UK)                            | Formato XML elenco vendite UE per il Regno Unito                    |
|                                                  |                       | Report elenco vendite UE per colonne                   | Report elenco vendite UE per colonne                                    |
|                                                  |                       | Report elenco vendite UE per righe                      | Report elenco vendite UE per righe                                       |
| Modello contabilità FEC (FR)                        | Dichiarazione imposte         |                                                   |                                                                    |
|                                                  |                       | Data contabili FEC XML (FR)                      | Formato XML esportazione dati contabili FEC per la Francia                   |
| File di controllo tedesco                                | Revisione contabile       |                                                   |                                                                    |
|                                                  |                       | Output file di controllo tedesco                          | Output file di controllo per la Germania e l'Austria                          |
| Modello Intrastat                                  | Notifica scambi commerciali       |                                                   |                                                                    |
|                                                  |                       | Intrastat (DE)                                    | Formato Intrastat per la Germania                                       |
|                                                  |                       | Intrastat (DK)                                    | Formato Intrastat per la Danimarca                                       |
|                                                  |                       | INTRACOM Intrastat (FR)                           | Formato INTRACOM Intrastat per la Francia                               |
|                                                  |                       | SAISUNIC Intrastat (FR)                           | Formato SAISUNIC Intrastat per la Francia                               |
|                                                  |                       | Intrastat (NL)                                    | Formato Intrastat per i Paesi Bassi                               |
|                                                  |                       | Intrastat (UK)                                    | Formato Intrastat per il Regno Unito                            |
|                                                  |                       | Report Intrastat                                  | Report controllo Excel Intrastat                                     |
| Modello fattura cliente                           | Fatture elettroniche  |                                                   |                                                                    |
|                                                  |                       | Nota di accredito progetto OIOUBL (DK)                   | Formato di nota di accredito progetto OIOUBL per la Danimarca                      |
|                                                  |                       | Fattura progetto OIOUBL (DK)                       | Formato fattura progetto OIOUBL per la Danimarca                          |
|                                                  |                       | Nota di accredito vendite OIOUBL (DK)                     | Formato di nota di accredito vendite OIOUBL per la Danimarca                        |
|                                                  |                       | Fattura vendita OIOUBL (DK)                         | Formato fattura vendita OIOUBL per la Danimarca                            |
| Modello dichiarazione OB                             | Dichiarazione imposte         |                                                   |                                                                    |
|                                                  |                       | Dichiarazione OB (NL)                               | Formato di dichiarazione OB per i Paesi Bassi                          |
| Modello di pagamento                                    | Pagamenti              |                                                   |                                                                    |
|                                                  |                       | Betalingsservice (DK)                             | Formato di pagamento Betalingsservice per la Danimarca                        |
|                                                  |                       | Rimessa dell'effetto attivo (FR)                  | Formato di rimessa effetto attivo per la Francia                      |
|                                                  |                       | BTL91 (NL)                                        | Formato di pagamento fornitore BTL91 per i Paesi Bassi                    |
|                                                  |                       | Prelievi CFONB (FR)                           | Formato di pagamento in addebito diretto CFONB per la Francia                       |
|                                                  |                       | Bonifici CFONB (FR)                              | Formato di pagamento fornitori nazionali CFONB per la Francia                    |
|                                                  |                       | Fornitore Nordea (DK)                                | Formato di pagamento fornitore Netbank aziendale Nordea per la Danimarca         |
|                                                  |                       | Servizio di credito diretto ANZ (AU)                    | Formato per servizio di credito diretto ANZ per l'Australia                 |
|                                                  |                       | Servizio di credito diretto CBA (AU)                    | Formato per servizio di credito diretto CBA per l'Australia                 |
|                                                  |                       | Servizio di credito diretto NAB (AU)                    | Formato per servizio di credito diretto NAB per l'Australia                 |
|                                                  |                       | Servizio di credito diretto STG (AU)                    | Formato per servizio di credito diretto STG per l'Australia                 |
|                                                  |                       | Sistema di inserimento diretto WBC (AU)                      | Formato per sistema di inserimento diretto WBC per l'Australia                   |
|                                                  |                       | DirectLink (NZ)                                   | Formato per DirectLink per la Nuova Zelanda                              |
|                                                  |                       | File di pagamento JBA (JP)                             | Formato di pagamento JBA per il Giappone                                       |
|                                                  |                       | Bonifico ISO20022                          | Formato di bonifico SEPA per l'Europa                             |
|                                                  |                       | Bonifico ISO20022 (FR)                     | Formato di bonifico SEPA per la Francia                             |
|                                                  |                       | Bonifico ISO20022 (DE)                     | Formato di bonifico SEPA per la Germania                            |
|                                                  |                       | Bonifico ISO20022 (NL)                     | Formato di bonifico SEPA per i Paesi Bassi                    |
|                                                  |                       | Addebito diretto ISO20022                             | Formato di addebito diretto SEPA per l'Europa                                |
|                                                  |                       | Addebito diretto ISO20022 (FR)                        | Formato di addebito diretto SEPA per la Francia                                |
|                                                  |                       | Addebito diretto ISO20022 (DE)                        | Formato di addebito diretto SEPA per la Germania                               |
|                                                  |                       | Addebito diretto ISO20022 (NL)                        | Formato di addebito diretto SEPA per i Paesi Bassi                       |
|                                                  |                       | BACS (UK)                                         | Formato di pagamento fornitori BACS per il Regno Unito                  |
| Reverse charge                                   | Dichiarazione imposte         |                                                   |                                                                    |
|                                                  |                       | Elenco vendite reverse charge                         | Formato di elenco vendite reverse charge                                   |
| Modello di integrazione XBRL olandese                     | Reporting XBRL        |                                                   |                                                                    |
|                                                  |                       | Semansys XBRL (NL)                                | Formato di esportazione Semansys XBRL per i Paesi Bassi                    |
| Modello GAF (MY)                                   | Revisione contabile       |                                                   |                                                                    |
|                                                  |                       | File GAF (MY)                                     | Formato di GAF per la Malaysia                                         |
| Report di aging fornitori (CN)                         | Analisi dei dati di fornitori |                                                   |                                                                    |
|                                                  |                       | Formato di report di aging fornitori (CN)                   | Formato di report di aging fornitori per la Cina                               |
| Modello di dichiarazione fattura fornitore                 | Analisi dei dati di fornitori |                                                   |                                                                    |
|                                                  |                       | Dichiarazione fattura fornitore (IS)                   | Formato di dichiarazione fattura fornitore per l'Islanda                      |
|                                                  |                       | Report dichiarazione fattura fornitore (IS)            | Report di dichiarazione fattura fornitore per l'Islanda                      |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Requisiti di localizzazione: creare una configurazione ER](electronic-reporting-configuration.md)
- [Gestire il ciclo di vita delle configurazioni dei report elettronici](general-electronic-reporting-manage-configuration-lifecycle.md)
