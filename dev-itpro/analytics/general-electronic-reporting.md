---
title: Panoramica sui report elettronici
description: Viene fornita una panoramica dello strumento di creazione di report elettronici. Sono incluse le informazioni sui concetti chiave e sugli scenari supportati da ER, oltre a un elenco di formati progettati e rilasciati come parte della soluzione.
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: caa9f4c73f4c6b5b7637b5b012bd9ed3b7dd6392
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="electronic-reporting-overview"></a>Panoramica sui report elettronici

[!include[banner](../includes/banner.md)]


Viene fornita una panoramica dello strumento di creazione di report elettronici. Sono incluse le informazioni sui concetti chiave e sugli scenari supportati da ER, oltre a un elenco di formati progettati e rilasciati come parte della soluzione.

Creazione di reporting elettronici (ER) è uno strumento che è possibile utilizzare per configurare i formati per i documenti elettronici conformemente ai requisiti legali di vari paesi. ER consente di gestire questi formati durante il ciclo di vita. Ad esempio, è possibile adottare nuovi requisiti normativi e generare documenti aziendali nel formato richiesto per scambiare elettronicamente informazioni con enti governativi, banche e altre parti. Il motore di ER è rivolto agli utenti aziendali anziché agli sviluppatori. Poiché si configurano formati, non il codice, i processi di creazione e modifica di formati per i documenti elettronici sono più veloci e semplici. ER attualmente supporta i formati di foglio di lavoro TEXT, XML e OPENXML. Tuttavia, un'interfaccia di estensione fornisce supporto per più formati.

## <a name="capabilities"></a>Capacità
Il motore ER presenta le seguenti funzionalità:

-   Rappresenta un unico strumento condiviso per la creazione di report elettronici in diversi domini e sostituisce più di 20 differenti motori impiegati in vari tipi di creazione di report elettronici per Microsoft Dynamics 365 for Operations.
-   Isola il formato di un report dall'implementazione corrente di Dynamics 365 for Operations. (In altre parole, il formato è applicabile per versioni diverse di Dynamics 365 for Operations).
-   Supporta la creazione di un formato personalizzato basato su un formato originale. Include funzionalità per aggiornare automaticamente il formato personalizzato quando vengono apportate modifiche al formato originale in quanto vengono introdotti requisiti di localizzazione/personalizzazione.
-   Diventa lo strumento standard principale per il supporto dei requisiti di localizzazione nella creazione di report elettronici, sia per Microsoft che per i partner Microsoft.
-   Supporta la possibilità di distribuire formati a partner e clienti tramite Microsoft Dynamics Lifecycle Services (LCS).

## <a name="concepts"></a>Concetti
### <a name="components"></a>Componenti

ER supporta due tipi di componenti: **Modello dati**e **Formato**.

#### <a name="data-model-components"></a>Componenti modello dati

Un componente modello dati è una rappresentazione astratta di una struttura dati e viene utilizzato per descrivere una specifica area di dominio aziendale con dettagli sufficienti a soddisfare i requisiti di report nel dominio. Un componente modello dati è costituito dalle seguenti parti:

-   Un modello dati come set di entità aziendali specifiche del dominio e una definizione con struttura gerarchica delle relazioni tra tali entità.
-   Un mapping di modello che collega determinate origini dati di Dynamics 365 for Operations a singoli elementi di un modello dati che specifica, in fase di esecuzione, il flusso di dati e le regole di inserimento dei dati aziendali in un componente modello dati.

Un'entità aziendale di un modello dati è rappresentata come contenitore (record). Le proprietà dell'entità aziendale sono rappresentate come elementi dati (campi). Ciascun elemento di dati dispone di un nome, un'etichetta, una descrizione e un valore univoci. Il valore di ogni elemento di dati può essere progettato in modo che venga riconosciuto come stringa, intero, reale, data, tipo di enumerazione, booleano e così via. Inoltre, può essere un altro record o elenco di record. Un singolo componente modello dati può contenere più gerarchie di entità aziendali specifiche del dominio nonché mapping di modello che supportano un flusso di dati specifico di un report in fase di esecuzione. Le gerarchie vengono differenziate da un singolo record che è stato selezionato come radice del mapping di modello. Ad esempio, il modello dati dell'area del dominio pagamenti può supportare i mapping seguenti:

-   Società -&gt; Fornitore -&gt; Transazioni di pagamento del dominio Contabilità fornitori
-   Cliente -&gt; Società -&gt; Transazioni di pagamento del dominio Contabilità clienti

Si noti che le entità aziendali (ad esempio Società e Transazioni di pagamento) vengono progettate una volta. Diversi mapping quindi le riutilizzano. Un mapping del modello presenta le seguenti funzionalità:

-   È possibile utilizzare diversi tipi di dati di Dynamics 365 for Operations come origini dati per un modello dati. Ad esempio, è possibile utilizzare le tabelle, le entità di dati, metodi o le enumerazioni.
-   Supporta parametri di input dell'utente che possono essere definiti ome origini dati del modello dati quando è necessario specificare alcuni dati in fase di esecuzione.
-   Supporta la trasformazione dei dati di Dynamics 365 for Operations in gruppi richiesti, filtrando, ordinando e riepilogando dati e anche aggiungendo con logica calcolata campi progettati mediante formule di tipo Microsoft Excel (per ulteriori informazioni, vedere [Designer formula in Creazione di report elettronici](general-electronic-reporting-formula-designer.md)).

[![Editor di formule di tipo Excel](./media/pic-formula-1024x615.png)](./media/pic-formula.png) Un componente modello dati è progettato per ciascun dominio aziendale da utilizzare come origine dati unificata per la creazione di report che isola la creazione di report dall'implementazione fisica delle origini dati di Dynamics 365 for Operations, e rappresenta i concetti e le funzionalità aziendali specifici del dominio in una forma che rende più efficiente la progettazione iniziale dei formati di report e la successiva manutenzione.

#### <a name="format-components"></a>Componenti formato

Un componente formato è lo schema dell'output della creazione di report che sarà generato in fase di esecuzione. Uno schema comprende i seguenti elementi:

-   Un formato che definisce la struttura e il contenuto del documento report elettronico generato in fase di esecuzione.
-   Origini dati come set di parametri di input dell'utente e un modello dati specifico del dominio che usa un mapping di modello selezionato
-   Un mapping di formato come set di associazioni di origini dati di formato che hanno singoli elementi di un formato che specificano in fase di esecuzione il flusso di dati e le regole di generazione dell'output del formato.
-   Una convalida di formato come set di regole configurabili che controllano la generazione di report in fase di esecuzione, a seconda del contesto di esecuzione (ad esempio, una regola che interrompe la generazione dell'output dei pagamenti di un fornitore e genera un'eccezione quando gli attributi specifici del fornitore selezionato sono mancanti, quali il numero di conto corrente bancario).

Un componente formato supporta le seguenti funzioni:

-   Creazione di output di report come singoli file in diversi formati: testo, XML o foglio di lavoro
-   Creazione di più file separatamente e incapsulamento di tali file in file zip

Un componente formato offre la possibilità di allegare file specifici che possono essere utilizzati nell'output di report:

-   Cartekke di lavoro di Excel che contengono un foglio di lavoro utilizzabile come modello per output nel formato foglio di lavoro OPENXML.
-   Altri file che è possibile incorporare nell'output del formato come file predefiniti.

#### <a name="component-versioning"></a>Controllo delle versioni del componente

Il controllo delle versioni è supportato per i componenti ER. Viene fornito il seguente flusso di lavoro per la gestione delle modifiche nei componenti ER:

-   La versione che viene creata in origine è contrassegnata come versione **BOZZA**. Questa versione può essere modificata ed è disponibile per le esecuzioni dei test.
-   La versione**BOZZA** può essere convertita in una versione **COMPLETATA**. Questa versione può essere utilizzata nei processi di creazione di report locali.
-   La versione **COMPLETATA** può essere convertita in una versione **CONDIVISA**. Questa versione viene pubblicata su LCS e può essere utilizzata nei processi globali di reporting.
-   La versione**CONDIVISA** può essere convertita in una versione **INTERROTTA**. Questa versione può quindi essere eliminata.

Le versioni nello stato** COMPLETATO** o **CONDIVISO** sono disponibili per un altro interscambio di dati. Su un componente che dispone di questi stati è possibile eseguire queste azioni:

-   Possono essere serializzati in formato XML ed esportati da Dynamics 365 for Operations in un file in formato XML.
-   Possono essere riserializzati da un file XML e importati in Dynamics 365 for Operations come nuova versione di un componente ER.

#### <a name="component-date-effectivity"></a>Validità delle date dei componenti

Le versioni dei componenti ER dipendono dalle date. È possibile definire la data di **Inizio validità** per un componente ER per specificare la data a partire dalla quale il componente diventa valido per i processi di creazione di report. La data della sessione di Dynamics 365 for Operations viene utilizzata per definire se un componente è valido per l'esecuzione. Se più di una versione è valida per una data particolare, la versione più recente viene utilizzata per i processi di creazione di report.

#### <a name="component-access"></a>Accesso ai componenti

L'accesso ai componenti di formato ER dipende dall'impostazione dei codici di paese ISO. Quando questa impostazione è vuota per la versione selezionata di una configurazione di formato, un componente di formato è accessibile da qualsiasi società di Dynamics 365 for Operations in fase di esecuzione. Quando questa impostazione contiene codici di regione/paese ISO, il componente formato è disponibile solo dalle società Dynamics 365 for Operations che hanno un indirizzo principale definito per uno dei codici di regione/paese ISO del componente formato. Versioni differenti di un componente formato dati possono avere impostazioni differenti per i codici di paese ISO.

#### <a name="configuration"></a>Configurazione

Una configurazione ER è il wrapper di un determinato componente ER, **Modello dati**o **Formato**. Una configurazione può includere versioni diverse di un particolare componente ER. Ciascuna configurazione viene contrassegnata come di proprietà di un provider di una determinata configurazione. La versione **BOZZA** di un componente di una configurazione può essere modificata quando il proprietario della configurazione è stato selezionato come provider attivo nelle impostazioni ER di Dynamics 365 for Operations. Ogni configurazione modello contiene un componente **modello dati**. Una nuova configurazione formato può derivare da una configurazione modello dati specifica. La configurazione formato che viene creata verrà presentata nella struttura della configurazione come elemento figlio della configurazione modello di dati originale. La configurazione formato creata contiene un componente **formato**. Il componente **modello dati** della configurazione modello originale viene inserito automaticamente nel componente **formato** della configurazione formato figlio creata come origine dati predefinita. Una configurazione ER è condivisa per le società Dynamics 365 for Operations.

#### <a name="provider"></a>Provider

Il provider ER è l'identificatore della parte che viene utilizzato per indicare l'autore (proprietario) di ciascuna configurazione ER. ER consente di gestire l'elenco di provider di configurazione. Le configurazioni formato rilasciate per documenti elettronici come parte della soluzione Dynamics 365 for Operations sono contrassegnate come di proprietà del provider di configurazione **Microsoft**.

#### <a name="repository"></a>Archivio

In un archivio ER sono archiviate le configurazioni di ER. Attualmente sono supportati i seguenti tipi di archivio ER: **Risorse Operations** e **Progetto LCS**. Un archivio** Risorse Operations** consente l'accesso all'elenco delle configurazioni che vengono rilasciate come parte della soluzione Dynamics 365 for Operations da Microsoft come provider di configurazioni ER. Tali configurazioni possono essere importate nell'istanza corrente di Dynamics 365 for Operations e utilizzate per la creazione di report elettronici. Possono inoltre essere utilizzate per altre localizzazioni/personalizzazioni. L'archivio **Progetto LCS**consente l'accesso all'elenco delle configurazioni di un determinato progetto LCS (raccolta risorse di progetto LCS) selezionato alla fase di registrazione archivio. ER consente di caricare le configurazioni condivise dall'istanza corrente di Dynamics 365 for Operations in un determinato archivio **Progetto LCS**. È anche possibile importare configurazioni da un determinato archivio **Progetto LCS** nell'istanza corrente di Dynamics 365 for Operations. È possibile registrare individualmente archivi **Progetto LCS** obbligatori per ciascun provider di configurazioni dell'istanza corrente di Dynamics 365 for Operations. Ogni archivio può essere dedicato a un provider di configurazioni specifico.

## <a name="supported-scenarios"></a>Scenari supportati
### <a name="building-a-data-model"></a>Generazione di un modello dati

ER offre una progettazione modello utilizzabile per creare un modello dati per un determinato dominio aziendale. Tutte le entità aziendali specifiche del dominio e le reciproche relazioni possono essere presentate in un modello dati sotto forma di una struttura gerarchica. Di seguito viene illustrato un esempio di questo tipo di modello dati (il modello dati del dominio pagamenti). [![Esempio di un modello dati](./media/pic-data-model-1024x550.png)](./media/pic-data-model.png) Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un modello dati specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="translating-data-model-content"></a>Traduzione del contenuto del modello dati

Il contenuto dei modelli dati (etichette e descrizioni) può essere tradotto in altre lingue supportate da Dynamics 365 for Operations. Si può decidere di tradurre il contenuto dei modelli dati per i seguenti motivi:

-   In fase di progettazione, per rendere il contenuto più comprensibile agli sviluppatori di formati che parlano altre lingue e che utilizzeranno un modello dati per il mapping dei dati di componenti formato.
-   In fase di esecuzione, per rendere il contenuto più semplice, presentando prompt e argomenti della Guida per parametri di runtime, nonché messaggi di convalida configurati (errori e avvisi) nella lingua preferita dall'utente di Dynamics 365 for Operations collegato.

Nella figura seguente viene riportato un esempio di come il contenuto del modello dati può essere tradotto dall'inglese al giapponese. [![Contenuto del modello dati in inglese](./media/pic-translate-en-1024x495.png)](./media/pic-translate-en.png) [![Contenuto del modello dati tradotto in giapponese](./media/pic-translate-ja-1024x495.png)](./media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Configurazione dei mapping del modello dati

ER fornisce una progettazione di mapping di modelli che consente agli utenti di eseguire il mapping di modelli di dati progettati per specifiche origini dati di Dynamics 365 for Operations. Nell'illustrazione riportata di seguito viene mostrato un esempio di questo tipo di mapping di modelli dati (mapping del modello **Bonifico SEPA** del modello dati del dominio pagamenti). [![Esempio di un mapping del modello dati ](./media/pic-model-mapping-1024x551.png)](./media/pic-model-mapping.png) Per familiarizzare con i dettagli di questo scenario, eseguire le guide attività **Definire con ER il mapping di modello e selezionare le origini dati** ed **Eseguire con ER il mapping del modello dati alle origini dati selezionate** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Archiviazione di un componente di modello progettato come configurazione modello

ER è in grado di archiviare un modello dati progettato insieme ai mapping di dati associati come configurazione di modello dell'istanza corrente di Dynamics 365 for Operations. Di seguito viene illustrato un esempio di questo tipo di configurazione modello dati (la configurazione modello dati del dominio pagamenti). [![Esempio di una configurazione del modello dati ](./media/pic-model-configuration-1024x585.png)](./media/pic-model-configuration.png) Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **ER Mappare il modello dati alle origini dati selezionate** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Creare un formato che utilizza un modello dati come base

ER supporta una progettazione formato utilizzabile per creare il formato di un determinato documento elettronico per un dominio aziendale selezionato scegliendo il componente modello come base. La stessa progettazione formato ER offre la possibilità di mappare un formato creato al mapping di modello dati di un dominio selezionato come origine dati. Di seguito viene illustrato un esempio di questo tipo di formato (la configurazione di formato che supporta il formato di pagamento **BACS** iper il Regno Unito). [![Esempio di un formato che ha un modello dati come base](./media/pic-format-1024x690.png)](./media/pic-format.png) Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **RE Progettare il formato specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Creazione di una configurazione per generare documenti elettronici in formato foglio di lavoro OPENXML

Progettazione formato ER è utilizzabile per creare un particolare documento elettronico in formato foglio di lavoro OPENXML. Nella figura seguente è illustrato un esempio di questo tipo di formato (una configurazione di formato per generare il foglio di lavoro di OPENXML con i dettagli di un giornale di registrazione pagamenti selezionato):[![Pic-ER-format-Excel](./media/pic-er-format-excel.jpg)](./media/pic-er-format-excel.jpg) Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Creare con ER una configurazione per report in OPENXML** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**). Utilizzare il file di Excel indicato sotto come modello di formato ER di progettazione per completare il passaggio dell'importazione del modello di formato di questa guida attività: [Modello di Report di pagamento (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Archiviazione di un componente formato progettato in una configurazione di formato

ER è in grado di archiviare un formato progettato insieme ai mapping di dati configurati come configurazione di formato dell'istanza corrente di Dynamics 365 for Operations. Nell'illustrazione precedente viene illustrato un esempio di questo tipo di configurazione di formato (**BACS (UK)**, che è figlio della configurazione **modello di pagamento**). Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Progettare con ER un formato specifico di dominio** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Configurazione di Dynamics 365 for Operations per utilizzare internamente un formato creato

È possibile configurare Dynamics 365 for Operations in modo da iniziare a utilizzare un formato creato per la generazione di report elettronici. Il riferimento alla configurazione di formato creata deve essere definito nelle impostazioni di uno specifico dominio. Ad esempio, per iniziare a utilizzare una configurazione di formato ER per i pagamenti elettronici ai fornitori in formato il BACS, occorre fare riferimento alla configurazione di formato in specifici metodi di pagamento, come mostrato nelle illustrazioni seguenti: 

[![Configurazione formato BACS (UK)](media/ger-bacs-uk-format-configuration.png) 

[![Riferimento al formato BACS (UK) in un metodo di pagamento](media/ger-bacs-uk-format-method.png) 

Per familiarizzare con i dettagli di questo scenario, eEseguire la guida attività **Utilizzare il formato ER per generare documenti elettronici per i pagamenti** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

## <a name="handling-er-components"></a>Gestione dei componenti ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Pubblicazione di un componente ER in LCS per offrirlo esternamente (localizzazione)

Il proprietario di un componente (modello o formato) creato può utilizzare ER per pubblicare la versione completata del componente in LCS. A tal fine è necessario avere un archivio di tipo **Progetto LCS** per il provider della configurazione ER corrente. Quando lo stato della versione completata di un componente viene modificato da **COMPLETATO** a **CONDIVISO**, questa versione viene pubblicata in LCS. Una volta che un componente è stato pubblicato in LCS, il proprietario del componente diventa un provider del servizio di supporto al componente. Ad esempio, se questo componente di formato è progettato per generare un documento elettronico legale necessario (ad esempio, in accordo con uno scenario di localizzazione), si presuppone che il formato venga mantenuto conforme alle modifiche legislative e che il provider emetterà nuove versioni del componente ogni volta che sorgono nuovi requisiti legislativi. Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Caricare con ER una configurazione in Lifecyle Services** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importazione di un componente ER da LCS per uso interno

ER consente di importare componenti ER da LCS all'istanza corrente di Dynamics 365 for Operations. È necessario disporre di un archivio di tipo **Progetto LCS**. Quando un componente ER è stato importato da LCS nell'istanza corrente di Dynamics 365 for Operations, il proprietario dell'istanza diventa un utente del servizio che viene fornito dal proprietario (autore) del componente importato. Ad esempio, se un componente di formato è progettato per generare uno specifico documento elettronico da Dynamics 365 for Operations in un formato specifico di paese (scenario di localizzazione), si presuppone che l'utente del servizio potrà ottenere tutti gli aggiornamenti fatti al formato per mantenerlo conforme ai requisiti legislativi. Per acquisire familiarità con i dettagli di questo scenario, eseguire la guida attività **Importare con ER una configurazione da Lifecyle Services** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Creazione di un formato selezionando un altro formato come base (personalizzazione)

ER consente di creare (derivare) un nuovo componente della versione corrente di un componente (base) che è stato importato da LCS. Ad esempio, un utente desidera derivare un nuovo formato per implementare alcuni requisiti speciali per un documento elettronico (ad esempio un campo aggiuntivo o una descrizione completa) per supportare uno scenario di personalizzazione. Per familiarizzare con i dettagli di questo scenario, eseguire la guida attività **Aggiornare con ER il formato tramite l'adozione di una nuova versione di base dello stesso formato** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Aggiornamento di un formato tramite la selezionare una nuova versione del formato di base (rebase)

ER consente di adottare automaticamente le modifiche alla versione più recente del componente di base nella versione bozza corrente del componente derivato. Questo processo è noto come *riassegnazione*. Ad esempio, le modifiche richieste da nuove normative introdotte nella versione più recente del componente di formato importato da LCS possono essere automaticamente unite nella versione personalizzata del formato del documento elettronico. Le modifiche che non possono essere unite automaticamente vengono considerate conflitti. Questi conflitti sono presentati per la risoluzione manuale nello strumento di progettazione per il componente appropriato. Per familiarizzare con i dettagli di questo scenario, eseguire la guida attività **Aggiornare con ER il formato tramite l'adozione di una nuova versione di base dello stesso formato** (parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**).

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Elenco delle configurazioni ER fornite nella soluzione Dynamics 365 for Operations
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



<a name="see-also"></a>Vedere anche
--------

[Requisiti di localizzazione: creare una configurazione ER](electronic-reporting-configuration.md)

[Gestire il ciclo di vita delle configurazioni dei report elettronici](general-electronic-reporting-manage-configuration-lifecycle.md)




