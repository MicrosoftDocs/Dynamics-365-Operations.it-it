---
title: Messaggistica elettronica
description: In questo argomento vengono fornite informazioni sulla messaggistica elettronica in Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 214d5cc2c3670b22fb4c28e5868fd9aade12ce84
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236772"
---
# <a name="electronic-messaging"></a>Messaggi elettronici

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sulla messaggistica elettronica.

Recentemente, governi e autorità legislative di vari paesi hanno implementato requisiti di reporting per le società registrate in tali paesi. Lo scopo dei requisiti è di consentire di ottenere i dati di tali società in formato elettronico, direttamente dai sistemi in cui sono stati valutati, archiviati ed elaborati.

La funzionalità Messaggi elettronici in Finance supporta vari processi per l'interoperazione elettronica tra Finance e i sistemi che governi e autorità legislative forniscono per il reporting, la presentazione e la ricezione di informazioni ufficiali.

La funzionalità Messaggi elettronici è integrata con il modulo **Creazione di report elettronici** (ER). Di conseguenza, è possibile configurare formati ER per messaggi elettronici. Per ulteriori informazioni, vedere [Creazione di report elettronici (ER)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

La messaggistica elettronica è basata sulle seguenti entità:

- **Messaggio elettronico** - Un report o una dichiarazione che deve essere inclusa nel report e/o trasmessa internamente. Un esempio è un report che viene inviato a un ufficio imposte.
- **Elementi del messaggio elettronico** - Record da includere nel messaggio incluso nel report.
- **Elaborazione messaggio elettronico** - Una catena di azioni che devono essere eseguite per raccogliere i dati richiesti, generare report, archiviare dati nell'archiviazione BLOB di Microsoft Azure, trasmettere report al di fuori del sistema, ricevere risposte esternamente al sistema e, in base alle informazioni ricevute, aggiornare il database. Le azioni nella catena possono essere associate o meno.

L'illustrazione seguente mostra il flusso di dati per la messaggistica elettronica.

![Flusso di dati della messaggistica elettronica](media/electronic-messaging-data-flow.png)

La funzionalità Messaggi elettronici supporta i seguenti scenari:

- Creare messaggi e generare report manualmente basati su formati ER di esportazione associati di vari tipi: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, testo e Microsoft Word.
- Creare ed elaborare automaticamente messaggi basati sulle informazioni richieste e ricevute da un'autorità tramite un formato ER di importazione associato.
- Raccogliere ed elaborare informazioni da un'origine dati come elementi del messaggio. L'origine dati è una tabella di Finance.
- Archiviare ulteriori informazioni e valutare diversi valori chiamando classi eseguibili definite in modo specifico in relazione a messaggi o elementi del messaggio.
- Aggregare informazioni raccolte in elementi del messaggio, dividere quelle informazioni per messaggio e generare report in formati ER di esportazione associati.
- Trasmettere i report generati a un servizio Web utilizzando informazioni di protezione che vengono archiviate in Azure Key Vault.
- Ricevere una risposta da un servizio Web, interpretare la risposta e aggiornare dati in Finance come appropriato.
- Archiviare ed esaminare tutti i report generati.
- Archiviare ed esaminare tutte le informazioni di registro correlate ad azioni eseguite per un messaggio o un elemento del messaggio.
- Controllare l'elaborazione mediante vari stati del messaggio e stati di elementi del messaggio.

## <a name="set-up-electronic-messaging"></a>Configurazione della messaggistica elettronica

La messaggistica elettronica può consentire la gestione di processi di reporting elettronico differenti per vari tipi di documento. In alcuni scenari complessi, la messaggistica elettronica viene configurata in modo da avere una combinazione di molti stati del messaggio, stati di elementi del messaggio, azioni, campi aggiuntivi e classi eseguibili. Per questi scenari, sono disponibili pacchetti di entità di dati per l'importazione. Se si utilizzano questi pacchetti di entità di dati, è necessario importarli in un'entità legale usando lo strumento di gestione dati. Per ulteriori informazioni su come utilizzare lo strumento di gestione dati, vedere [Gestione dei dati](../../dev-itpro/data-entities/data-entities-data-packages.md).

Se non si importa un pacchetto di entità di dati, è possibile configurare manualmente la funzionalità Messaggi elettronici. In tal caso, è necessario configurare i seguenti elementi.

- [Sequenze numeriche](#number-sequences)
- [Stati e tipi di elementi del messaggio](#message-item-types-and-statuses)
- [Stati del messaggio](#message-statuses)
- [Campi aggiuntivi](#additional-fields)
- [Impostazioni classe eseguibile](#executable-class-settings)
- [Azioni di popolamento record](#populate-records-actions)
- [Applicazioni Web](#web-applications)
- [Impostazioni servizio Web](#web-service-settings)
- [Azioni di elaborazione messaggi](#message-processing-actions)
- [Elaborazione messaggio elettronico](#electronic-message-processing)

Nelle sezioni seguenti vengono fornite altre informazioni su ognuno di tali elementi.

### <a name="number-sequences"></a>Sequenze numeriche

Configurare sequenze numeriche per messaggi ed elementi del messaggio. Le sequenze numeriche sono utilizzate per numerare automaticamente i messaggi e gli elementi dei messaggii. I numeri assegnati saranno utilizzati come identificatori univoci per i messaggi e gli elementi dei messaggi nel sistema. È possibile configurare sequenze numeriche per la messaggistica elettronica nella pagina **Parametri di contabilità generale** (**Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**).

### <a name="message-item-types-and-statuses"></a>Stati e tipi di elementi del messaggio

I tipi di elementi del messaggio identificano i tipi di record che verranno utilizzati nei messaggi elettronici. È possibile configurare tipi di elementi del messaggio nella pagina **Tipi di elementi del messaggio** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Tipi di articolo del messaggio**).

Gli stati degli elementi del messaggio identificano gli stati che saranno applicati agli elementi del messaggio nell'elaborazione che si sta configurando. È possibile configurare tipi di elementi del messaggio nella pagina **Stati elementi dei messaggi** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Stati elementi dei messaggi**).

Il parametro **Consenti eliminazione** di uno stato di elementi del messaggio definisce se gli utenti possono eliminare elementi dei messaggi che hanno questo stato nella pagina **Messaggi elettronici** o **Elementi del messaggio elettronico**.

### <a name="message-statuses"></a>Stati del messaggio

Configurare gli stati del messaggio che devono essere disponibili nell'elaborazione dei messaggi. È possibile configurare stati del messaggio nella pagina **Stati del messaggio** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Stati del messaggio**).

Nella tabella seguente sono descritti i campi della pagina **Stati del messaggio**.

| Nome campo          | Descrizione |
|---------------------|-------------|
| Stato messaggio      | Immettere un nome univoco per lo stato del messaggio. Gli stati dei messaggi sono utilizzati per caratterizzare lo stato di un messaggio elettronico in qualsiasi momento. Il nome immesso viene visualizzato nella pagina **Messaggi elettronici** e in un registro correlato ai messaggi elettronici. |
| Descrizione         | Immettere una descrizione dello stato del messaggio. |
| Tipo di risposta       | Selezionare il tipo di risposta per lo stato del messaggio. Alcune azioni in un elaborazione possono generare più tipi di risposta. Ad esempio, le azioni di tipo **Servizio Web** possono generare risposte di tipo **Eseguito correttamente** o **Errore tecnico** a seconda del risultato della relativa esecuzione. In questo caso, è necessario definire gli stati del messaggio per entrambi i tipi di risposta. Per ulteriori informazioni sui tipi di azioni e i tipi di risposta ad essi correlati, vedere [Tipi di azioni di elaborazione messaggi](#message-processing-action-types). |
| Stato elemento del messaggio | A volte, lo stato di un messaggio elettronico deve influenzare lo stato degli elementi del messaggio correlati. Selezionare lo stato di un articolo di messaggio in questo campo per associarlo allo stato del messaggio. |
| Consenti eliminazione        | Selezionare questa casella di controllo se gli utenti devono poter eliminare i messaggi elettronici con questo stato nella pagina **Messaggi elettronici**. |

### <a name="additional-fields"></a>Campi aggiuntivi

La funzionalità Messaggi elettronici consente di completare i record da una tabella transazionale. In questo modo, è possibile preparare i record per il reporting e quindi includerli nei report. Tuttavia, le tabelle transazionali talvolta non hanno informazioni sufficienti per completare i record in un modo che soddisfa i requisiti di reporting. Per immettere tutte le informazioni che devono essere incluse in un report per un record, è possibile configurare ulteriori campi. Ulteriori campi possono essere associati a messaggi e elementi del messaggio. È possibile configurare ulteriori campi nella pagina **Campi aggiuntivi** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Campi aggiuntivi**).

Nella seguente tabella sono descritti i campi generali della pagina **Campi aggiuntivi**.

| Campo       | Descrizione |
|-------------|-------------|
| Nome campo  | Immettere il nome di un ulteriore attributo degli elementi del messaggio correlati al processo. Questo nome viene visualizzato nell'interfaccia utente durante il processo. Può anche essere utilizzato nelle configurazioni ER correlate al processo. |
| Descrizione | Immettere una descrizione del campo aggiuntivo. |
| Modifica utente   | Impostare questa opzione su **Sì** se gli utenti devono poter modificare il valore del campo aggiuntivo dall'interfaccia utente. |
| Contatore     | Impostare questa opzione su **Sì** se il campo aggiuntivo deve contenere una sequenza numerica in un messaggio elettronico. Il valore del campo aggiuntivo verrà immesso automaticamente durante l'esecuzione di un'azione di tipo **Esportazione creazione di report elettronici**. |
| Nascosto      | Impostare questa opzione su **Sì** se il campo aggiuntivo deve essere nascosto nell'interfaccia utente. |

Ogni campo supplementare può avere valori diversi per l'elaborazione. È possibile definire questi valori nella Scheda dettaglio **Valori**. Nella seguente tabella vengono descritti i campi.

| Campo                | Descrizione |
|----------------------|-------------|
| Valore campo          | Immettere il valore del campo da utilizzare per un messaggio o elemento del messaggio durante il reporting. |
| Descrizione          | Immettere una descrizione del valore del campo. |
| Tipo di account         | Alcuni valori dei campi potrebbero essere limitati a specifici tipi di conto. Selezionare uno dei seguenti valori: **Tutto**, **Cliente** o **Fornitore**. |
| Codice conto         | Se si è selezionato **Cliente** o **Fornitore** nel campo **Tipo di conto**, è possibile limitare ulteriormente l'utilizzo del valore del campo a uno specifico gruppo o tabella. |
| Numero conto/gruppo | Se si è selezionato **Cliente** o **Fornitore** nel campo **Tipo di conto** e si è immesso un gruppo o una tabella nel campo **Codice conto**, è possibile immettere uno specifico gruppo o agente doganale in questo campo. |
| Valido            | Specificare la data alla quale si deve iniziare a considerare il valore. |
| Scadenza           | Specificare la data alla quale il valore non deve più considerare il valore. |

Per impostazione predefinita, le combinazioni di criteri definiti dai campi **Numero conto/gruppo**, **Codice conto**, **Validità** e **Scadenza** non influiscono sulla selezione dei valori di campi aggiuntivi. Tuttavia, queste combinazioni possono essere utilizzate in una classe eseguibile per implementare una logica specifica che calcola i valori dei campi aggiuntivi.

### <a name="executable-class-settings"></a>Impostazioni classe eseguibile

Una classe eseguibile è un metodo o classe X++ che l'elaborazione del messaggio elettronico può chiamare in relazione a un'azione se una valutazione viene richiesta per il processo.

È possibile configurare manualmente una classe eseguibile nella pagina **Impostazioni classe eseguibile** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Impostazioni classe eseguibile**). Creare una riga e impostare i seguenti campi.

| Campo                 | Descrizione |
|-----------------------|-------------|
| Classe eseguibile      | Immettere il nome che verrà utilizzato durante la configurazione di un'azione di elaborazione messaggi in relazione alla quale questa classe viene chiamata. |
| Descrizione           | Immettere una descrizione della classe eseguibile. |
| Nome classe eseguibile | Selezionare una classe eseguibile X++. |
| Livello di esecuzione       | Questo campo viene impostato automaticamente, in quanto il valore deve essere predefinito per la classe eseguibile selezionata. Questo campo limita il livello di esecuzione della valutazione correlata. |
| Descrizione classe     | Questo campo viene impostato automaticamente, in quanto il valore deve essere predefinito per la classe eseguibile selezionata. |

Alcune classi eseguibili potrebbero avere parametri obbligatori che devono essere definiti prima della prima esecuzione della classe eseguibile. Per definire questi parametri, selezionare **Parametri** nel riquadro azioni, impostare i campi nella finestra di dialogo visualizzata e selezionare **OK**. È importante selezionare **OK**. In caso contrario, i parametri non verranno salvati nel database e la classe eseguibile non verrà chiamata correttamente.

### <a name="populate-records-actions"></a>Azioni di popolamento record

Le azioni di popolamento record sono utilizzate per configurare azioni che aggiungono record alla tabella Elementi del messaggio affinché possano essere aggiunti a un messaggio elettronico. Ad esempio, se il messaggio elettronico deve includere fatture cliente, è necessario configurare un'azione Popola record che è collegata al campo **Origine dati** nella tabella Giornale di registrazione fatture cliente. È possibile configurare azioni di popolamento record nella pagina **Azione di popolamento record** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Azioni di popolamento record**). Creare un nuovo record per ogni azione che deve aggiungere record alla tabella e impostare i campi seguenti.

| Campo       | Descrizione |
|-------------|-------------|
| Nome        | Immettere un nome per l'azione che completa i record nel processo. |
| Descrizione | Immettere una descrizione dell'azione Popola record. |

Nella scheda Dettaglio **Impostazione origini dati**, aggiungere una riga per ogni origine dati utilizzata per il processo e impostare i seguenti campi.

| Campo                  | Descrizione |
|------------------------|-------------|
| Nome                   | Immettere un nome per l'origine dati. |
| Tipo di elemento del messaggio      | Selezionare il tipo di elemento del messaggio da utilizzare durante la creazione dei record per l'origine dati. |
| Tipo di conto           | Selezionare il tipo di conto da associare ai record dell'origine dati. |
| Nome tabella master      | Selezionare la tabella che deve essere un'origine dati. |
| Campo Numero documento  | Selezionare il campo da cui deve essere ottenuto il numero di documento nella tabella selezionata. |
| Campo Data documento    | Selezionare il campo da cui deve essere ottenuta la data del documento nella tabella selezionata. |
| Campo Conto documento | Selezionare il campo da cui deve essere ottenuto il conto del documento nella tabella selezionata. |
| Query utente             | Se questa casella di controllo è selezionata, è possibile impostare una query selezionando **Modifica query** sopra la griglia. In caso contrario, tutti i record saranno completati a partire dall'origine dati selezionata. |

### <a name="web-applications"></a>Applicazioni Web

Per configurare un'applicazione Web di modo che supporti Open Authorization (OAuth) 2.0, si utilizzano le impostazioni dell'applicazione Web.  OAuth è lo standard aperto che consente agli utenti di concedere l'"accesso delegato protetto" all'applicazione per loro conto, senza condividere le loro credenziali di accesso. È anche possibile eseguire il processo di autorizzazione ottenendo un codice di autorizzazione e un token di accesso. È possibile configurare le impostazioni dell'applicazione Web nella pagina **Applicazioni Web** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Applicazioni Web**).

Nella tabella seguente sono descritti i campi della pagina **Applicazioni Web**.

| Campo                        | Descrizione |
|------------------------------|-------------|
| Nome applicazione             | Immettere un nome per l'applicazione Web. |
| Descrizione                  | Immettere una descrizione dell'applicazione Web. |
| URL di base                     | Immettere l'indirizzo Internet di base dell'applicazione Web. |
| Percorso URL autorizzazione       | Specificare il percorso utilizzato per comporre l'URL per l'autorizzazione. |
| Percorso URL token               | Specificare il percorso utilizzato per comporre l'URL per il token. |
| Reindirizza URL                 | Immettere l'URL di reindirizzamento. |
| ID client                    | Immettere l'ID client dell'applicazione Web. |
| Segreto client                | Immettere il segreto client dell'applicazione Web. |
| Token server                 | Immettere il token server dell'applicazione Web. |
| Mapping formato autorizzazione | Selezionare il formato di ER utilizzato per generare la richiesta per l'autorizzazione. |
| Importa mapping modello token   | Selezionare un mapping di modelli di importazione ER utilizzato per archiviare il token di accesso. |
| Ambito concesso                | L'ambito concesso per le richieste all'applicazione. Questo campo viene aggiornato automaticamente. |
| Il token di accesso scadrà tra  | Il tempo rimanente prima della scadenza del token di accesso. | 
| Conferma                       | Specificare la proprietà **Accetta** della richiesta Web. Ad esempio, immettere **application/vnd.hmrc.1.0+json**. |
| Tipo di contenuto                 | Specificare il tipo di contenuto. Ad esempio,, immettere **application/json**. |

Inoltre, i seguenti pulsanti sono disponibili nel Riquadro azioni della pagina **Applicazioni Web** per supportare il processo di autorizzazione:

- **Ottieni codice di autorizzazione** - Inizializzare l'autorizzazione dell'applicazione Web.
- **Ottieni token di accesso** - Inizializzare il processo di acquisizione di un token di accesso.
- **Aggiorna token di accesso** - Aggiornare un token di accesso.

Quando un token di accesso per un'applicazione Web viene archiviato nel database del sistema in formato crittografato, può essere utilizzato per le richieste a un servizio Web. Per scopi di sicurezza l'accesso al token di accesso deve essere limitato ai ruoli di sicurezza a cui deve essere consentita l'elaborazione di tali richieste. Se gli utenti all'esterno del gruppo di sicurezza tentano di elaborare una richiesta, viene generato un errore indicante che questi non sono autorizzati a interagire tramite l'applicazione Web selezionata. Per impostare i ruoli di sicurezza che devono avere accesso al token di accesso, utilizzare la scheda dettaglio **Ruoli di sicurezza** della pagina **Applicazioni Web**. Se i ruoli di sicurezza non vengono definiti per un'applicazione Web, solo un amministratore di sistema può interagire tramite questa applicazione Web.

### <a name="web-service-settings"></a>Impostazioni servizio Web

Le impostazioni del servizio Web consentono di configurare la trasmissione di dati diretta a un servizio Web. È possibile configurare le impostazioni del servizio Web nella pagina **Impostazioni servizio Web** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Impostazioni servizio Web**).

Nella seguente tabella sono descritti i campi della pagina **Impostazioni servizio Web**.

| Campo                          | Descrizione |
|--------------------------------|-------------|
| Servizio Web                    | Immettere un nome per il servizio Web. |
| Descrizione                    | Immettere una descrizione del servizio Web. |
| Indirizzo Internet               | Immettere l'indirizzo Internet del servizio Web. Se un'applicazione Web viene specificata per il servizio Web e se l'indirizzo Internet del servizio Web deve essere uguale a quello definito per quell'applicazione Web, selezionare **Copia URL di base** per copiare l'URL di base dall'applicazione Web in questo campo. |
| Certificato                    | Selezionare un certificato Key Vault configurato in precedenza. |
| Applicazione Web                | Selezionare un certificato Key Vault configurato in precedenza. |
| Tipo di risposta – XML        | Impostare questa opzione su **Sì** se il tipo di risposta è XML. |
| Metodo di richiesta                 | Specificare il metodo della richiesta. HTTP definisce un set di metodi di richiesta che indicano l'azione che dovrà essere eseguita per una risorsa data. Il metodo di richiesta può essere **GET**, **POST** o un altro metodo HTTP. |
| Intestazioni richieste                | Specificare le intestazioni di richieste. Un'intestazione di richiesta è un'intestazione HTTP utilizzabile in una richiesta HTTP e non correlata al contenuto del messaggio. |
| Conferma                         | Specificare la proprietà **Accetta** della richiesta Web. |
| Accetta codifica                | Specificare il valore **Accept-Encoding**. L'intestazione HTTP della richiesta Accept-Encoding annuncia la codifica del contenuto che il client può comprendere. Questa codifica del contenuto è in genere un algoritmo di compressione. |
| Tipo di contenuto                   | Specificare il tipo di contenuto. L'intestazione HTTP dell'entità Content-Type indica il tipo di media della risorsa. |
| Codice di risposta operazione riuscita       | Specificare il codice di stato HTTP indicante che la richiesta è riuscita. |
| Mapping formato intestazioni richiesta | Selezionare il formato di ER utilizzato per generare intestazioni di richieste Web. |

### <a name="message-processing-actions"></a>Azioni di elaborazione messaggi

Le azioni di elaborazione messaggi consentono di creare azioni per i processi e configurare i relativi parametri. È possibile configurare azioni di elaborazione messaggi nella pagina **Azioni di elaborazione messaggi** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Azioni di elaborazione messaggi**).

Nelle tabelle seguenti vengono descritti i campi della pagina **Azioni di elaborazione messaggi**.

#### <a name="general-fasttab"></a>Scheda dettaglio Generale

| Campo                       | Descrizione |
|-----------------------------|-------------|
| Tipo di azione                 | Selezionare il tipo di azione. Per informazioni sulle opzioni disponibili, vedere la sezione [Tipi di azioni di elaborazione messaggi](#message-processing-action-types). |
| Mapping formato              | Selezionare il formato ER che deve essere chiamato per l'azione. Questo campo è disponibile solo per le azioni **Esportazione creazione di report elettronici**, **Importazione creazione di report elettronici** e **Messaggio esportazione creazione di report elettronici**. |
| Mapping formato per percorso URL | Selezionare il formato ER che deve essere chiamato per l'azione. Questo campo è disponibile solo per le azioni di tipo **Servizio Web**. Viene utilizzato per comporre il percorso dell'indirizzo URL che verrà aggiunto all'indirizzo Internet di base specificato per il server Web selezionato. |
| Tipo di elemento del messaggio           | Selezionare il tipo di record per il quale l'azione deve essere valutata. Questo campo è disponibile per le azioni di tipo **Livello di esecuzione dell'elemento del messaggio**, **Esportazione creazione di report elettronici**, **Importazione creazione di report elettronici**, **Servizio Web** e altri tipi. Se si lascia vuoto questo campo, vengono valutati tutti i tipi di elementi del messaggio definiti per l'elaborazione del messaggio. |
| Classe eseguibile            | Selezionare le impostazioni della classe eseguibile create in precedenza. Questo campo è disponibile solo per le azioni **Livello di esecuzione dell'elemento del messaggio** e **Livello di esecuzione dell'elemento del messaggio**. |
| Azione di popolamento record     | Selezionare un'azione di popolamento di record configurata in precedenza. Questo campo è disponibile solo per le azioni **Popola record**. |
| Servizio Web                 | Selezionare un servizio Web configurato in precedenza. Questo campo è disponibile solo per le azioni di tipo **Servizio Web**. |
| Nome file                   | Specificare il nome del file creato a seguito dell'azione. Questo file può essere la risposta dal server Web o dal report generato. Questo campo è disponibile solo per le azioni di tipo **Servizio Web** e **Messaggio esportazione creazione di report elettronici**. |
| Mostra finestra dialogo                 | Impostare questa opzione su **Sì** se una finestra di dialogo deve essere visualizzata agli utenti prima della generazione del report. Questo campo è disponibile solo per le azioni di tipo **Messaggio esportazione creazione di report elettronici**. |

##### <a name="message-processing-action-types"></a>Tipi di azioni di elaborazione messaggi

Nel campo **Tipo di azione** sono disponibili le seguenti opzioni:

- **Crea messaggio** - Utilizzare questo tipo di azione per consentire agli utenti di creare manualmente messaggi nella pagina **Messaggio elettronico**. Uno stato iniziale non può essere configurato per un'azione di questo tipo.
- **Popola record** - Un'azione di tipo **Popola record** deve essere configurata in precedenza. Associare questo tipo di azione a un'azione Popola record affinché sia inclusa nell'elaborazione. Si presuppone che questo tipo di azione sia utilizzato per la prima azione nell'elaborazione del messaggio (quando nessun messaggio elettronico è stato creato in anticipo) o per un'azione che aggiunge elementi del messaggio a un messaggio creato in precedenza (mediante un'azione di tipo **Crea messaggio**). Di conseguenza, per le azioni di questo tipo, uno stato di risultati dei soli può essere configurato solo per elementi del messaggio. Uno stato iniziale può essere configurato solo per i messaggi.
- **Livello di esecuzione del messaggio** - Utilizzare questo tipo di azione per configurare una classe eseguibile che deve essere valutata a livello del messaggio.
- **Livello di esecuzione dell'elemento del messaggio** - Utilizzare questo tipo di azione per configurare una classe eseguibile che deve essere valutata a livello dell'elemento del messaggio.
- **Esportazione creazione di report elettronici** - Utilizzare questo tipo di azione per le azioni che devono generare un report basato su una configurazione ER di esportazione a livello dell'elemento del messaggio.
- **Messaggio esportazione creazione di report elettronici** - Utilizzare questo tipo di azione per le azioni che devono generare un report basato su una configurazione ER di esportazione a livello del messaggio (ad esempio, quando un messaggio non ha elementi).
- **Importazione creazione di report elettronici** - Utilizzare questo tipo di azione per le azioni che devono generare un report basato su una configurazione ER di importazione a livello dell'elemento del messaggio.
- **Elaborazione utente livello del messaggio** - Utilizzare questo tipo di azione per le azioni che presuppongono azioni manuali da parte dell'utente a livello del messaggio. Ad esempio, l'utente potrebbe aggiornare lo stato dei messaggi.
- **Elaborazione utente** - Utilizzare questo tipo di azione per le azioni che presuppongono azioni manuali da parte dell'utente a livello dell'elemento del messaggio. Ad esempio, l'utente potrebbe aggiornare lo stato degli elementi del messaggio.
- **Servizio Web** - Utilizzare questo tipo di azione per le azioni che devono trasmettere un report generato a un servizio Web. Questo tipo di azione non viene utilizzato per il reporting relativo alla comunicazione di fatture di vendita e di acquisto per l'Italia. Per le azioni di tipo **Servizio Web**, la pagina **Azioni di elaborazione messaggi** include una Scheda dettaglio **Dettagli vari** dove è possibile specificare un testo di conferma. Questo testo di conferma sarà visualizzato agli utenti prima dell'elaborazione delle richieste al servizio Web selezionato.
- **Verifica richiesta** - Utilizzare questo tipo di azione per la verifica della richiesta da un server.

#### <a name="initial-statuses-fasttab"></a>Scheda Dettaglio Stati iniziali

> [!NOTE]
> La scheda dettagli **Stati iniziali** non è disponibile per le azioni con un tipo di azione **Crea messaggio** iniziale.

| Campo               | Descrizione |
|---------------------|-------------|
| Stato elemento del messaggio | Selezionare lo stato dell'elemento del messaggio per il quale l'azione di elaborazione messaggi selezionata deve essere valutata. |
| Descrizione         | Una descrizione dello stato dell'articolo del messaggio selezionato. |

#### <a name="result-statuses-fasttab"></a>Scheda Dettaglio Stati di risultati

| Campo               | Descrizione |
|---------------------|-------------|
| Stato messaggio      | Selezionare gli stati del messaggio per il quale l'azione di elaborazione messaggi selezionata deve essere valutata. Questo campo è disponibile solo per le azioni di elaborazione messaggi che vengono valutate a livello del messaggio. Ad esempio, è disponibile per le azioni di tipo **Esportazione creazione di report elettronici** e **Importazione creazione di report elettronici**, ma non per le azioni di tipo **Elaborazione utente** e **Livello di esecuzione dell'elemento del messaggio**. |
| Descrizione         | Una descrizione dello stato del messaggio selezionato. |
| Tipo di risposta       | Il tipo di risposta dello stato del messaggio dello stato. |
| Stato elemento del messaggio | Selezionare gli stati risultanti che devono essere disponibili dopo la valutazione dell'azione di elaborazione messaggi selezionata. Questo campo è disponibile solo per le azioni di elaborazione messaggi che vengono valutate a livello dell'elemento del messaggio. Ad esempio, è disponibile per le azioni **Elaborazione utente** e **Livello di esecuzione dell'elemento del messaggio**. Per le azioni di elaborazione messaggi che vengono valutate a livello del messaggio, questo campo mostra lo stato dell'elemento del messaggio configurato per lo stato del messaggio selezionato. |

La tabella seguente illustra gli stati di risultati che devono essere configurati per differenti tipi di azioni e tipi di risposte:

| Tipo di azione messaggio elettronico/Tipo di risposta | Esecuzione completata | Errore aziendale | Errore tecnico | Definiti dall'utente | Annulla |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| Crea messaggio                               | X                     |                |                 |              |        |
| Esportazione creazione di report elettronici                  | X                     |                |                 |              |        |
| Importazione creazione di report elettronici                  |                       |                |                 |              |        |
| Servizio Web                                  | X                     |                | X               |              |        |
| Elaborazione utente                              |                       |                |                 |              |        |
| Livello di esecuzione del messaggio                      |                       |                |                 |              |        |
| Popola record                             |                       |                |                 |              |        |
| Livello di esecuzione dell'elemento del messaggio                 |                       |                |                 |              |        |
| Verifica richiesta                         | X                     | X              | X               |              |        |
| Messaggio esportazione creazione di report elettronici          | X                     |                |                 |              |        |
| Elaborazione utente livello del messaggio                |                       |                |                 |              |        |

### <a name="electronic-message-processing"></a>Elaborazione messaggio elettronico

L'elaborazione del messaggio elettronico è un concetto di base della funzionalità Messaggi elettronici. Aggrega le azioni che devono essere valutate per il messaggio elettronico. Le azioni possono essere collegate tramite uno stato iniziale e uno stato di risultato. In alternativa, le azioni **Elaborazione utente** possono essere avviate indipendentemente. Nella pagina **Elaborazione messaggio elettronico** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Elaborazione messaggio elettronico**), è anche possibile selezionare campi aggiuntivi che devono essere supportati per l'elaborazione a livello del messaggio o degli elementi del messaggio.

La scheda Dettaglio **Azione** consente di aggiungere azioni predefinite all'elaborazione. È possibile specificare se un'azione deve essere eseguita separatamente o se può essere avviata dall'elaborazione. Per specificare che un'azione nell'elaborazione può essere inizializzata solo da un utente, impostare il campo **Esegui separatamente** su **Sì** per quell'azione. Se l'azione deve essere avviata elaborando i messaggi o gli elementi del messaggio nello stato definito come stato iniziale per l'azione, impostare **Esegui separatamente** su **No**. Le azioni di tipo **Azione utente** devono sempre essere eseguite separatamente.

Talvolta, più azioni devono essere aggregate in una sequenza, anche se la prima azione è configurata di modo che venga eseguita separatamente. Ad esempio, un utente deve inizializzare la generazione del report, ma subito dopo la generazione del report, questo deve essere inviato a un servizio Web e la riposta del servizio Web deve essere riflessa nel sistema. In questo caso, è possibile creare una sequenza inseparabile per le azioni che devono essere sempre eseguite insieme. Nella Scheda dettaglio **Azione**, selezionare **Sequenza inseparabile** sopra la griglia e creare una sequenza. Quindi, per tutte le azioni da eseguire insieme, selezionare la sequenza nel campo **Sequenza inseparabile**. In questo caso, il campo **Esegui separatamente** può essere impostato su **Sì** per la prima azione nella sequenza ma su **No** per tutte le altre azioni.

La scheda Dettaglio **Campi aggiuntivi dell'elemento del messaggio** consente di aggiungere ulteriori campi predefiniti correlati agli elementi del messaggio. È necessario aggiungere ulteriori campi per ogni tipo di elemento del messaggio a cui i campi sono correlati.

La scheda Dettaglio **Campi aggiuntivi del messaggio** consente di aggiungere ulteriori campi predefiniti correlati ai messaggi.

La scheda dettaglio **Ruoli di sicurezza** consente di configurare i ruoli di sicurezza che sono predefiniti nel sistema per una specifica elaborazione. Gli utenti con un ruolo specifico avranno accesso solo all'elaborazione definita per tale ruolo.

La scheda Dettaglio **Batch** consente di configurare l'elaborazione per l'utilizzo in un regime batch.

## <a name="work-with-the-electronic-messages-functionality"></a>Utilizzo della funzionalità Messaggi elettronici

Se si lavora a livello del messaggio, la pagina **Messaggi elettronici** (**Imposta** \> **Richieste di informazioni e report** \> **Messaggi elettronici** \> **Messaggi elettronici**) è più utile. Se si lavora a livello della raccolta di dati (elemento del messaggio), la pagina **Elementi del messaggio elettronico** (**Imposta** \> **Richieste di informazioni e report** \> **Messaggi elettronici** \> **Elementi del messaggio elettronico**) è più utile.

### <a name="electronic-messages"></a>Messaggi elettronici

La pagina **Messaggi elettronici** presenta l'elaborazione disponibile, in base al ruolo. I ruoli di sicurezza sono associati all'elaborazione nella configurazione dell'elaborazione. Per ogni elaborazione disponibile, la pagina mostra i messaggi elettronici e le informazioni ad essi correlate.

La scheda Dettaglio **Messaggi** visualizza i messaggi elettronici per l'elaborazione selezionata. A seconda dello stato del messaggio selezionato e dell'elaborazione predefinita, è possibile eseguire alcune azioni utilizzando i pulsanti sopra la griglia:

- **Nuovo** - Questo pulsante è associato alle azioni **Crea messaggio**.
- **Elimina** - Questo pulsante è disponibile se la casella di controllo **Consenti eliminazione** è selezionata per lo stato corrente del messaggio selezionato.
- **Raccogli dati** - Questo pulsante è associato alle azioni di tipo **Popola record**.
- **Genera report** - Questo pulsante è associato alle azioni **Messaggio esportazione creazione di report elettronici**.
- **Invia report** - Questo pulsante è associato alle azioni **Servizio Web**.
- **Importa risposta** - Questo pulsante è associato alle azioni di tipo **Importazione creazione di report elettronici**.
- **Aggiorna stato** - Questo pulsante è associato alle azioni **Elaborazione utente livello del messaggio**.
- **Elementi del messaggio** - Apre la pagina **Elementi del messaggio elettronico**.

La scheda Dettaglio **Registro azioni** visualizza le informazioni su tutte le azioni eseguite per il messaggio selezionato. Se un'azione ha causato un errore, le informazioni sull'errore sono associate alla riga correlata nella griglia. Per esaminare le informazioni sull'errore, selezionare la riga nella griglia quindi selezionare il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.

La scheda Dettaglio **Campi aggiuntivi del messaggio** visualizza tutti i campi aggiuntivi definiti per i messaggi nella configurazione dell'elaborazione. Visualizza inoltre i valori di quei campi aggiuntivi.

La scheda Dettaglio **Elementi del messaggio** visualizza tutti gli elementi del messaggio correlati al messaggio selezionato. A seconda dello stato dell'elemento del messaggio selezionato, è possibile eseguire alcune azioni utilizzando i pulsanti sopra la griglia:

- **Elimina** - Questo pulsante è disponibile se la casella di controllo **Consenti eliminazione** è selezionata per lo stato corrente dell'elemento del messaggio selezionato.
- **Aggiorna stato** - Questo pulsante è associato alle azioni di tipo **Elaborazione utente**.
- **Documento originale** - Aprire una pagina che visualizza il documento originale per l'elemento del messaggio selezionato.

Tutti i report che sono già stati generati e ricevuti per un messaggio sono collegati a tale messaggio. Per esaminare gli allegati correlati al messaggio, selezionare il messaggio e quindi selezionare il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.

![Pulsante Allegato](media/attachment-icon.png)

La pagina **Allegati** visualizza tutti gli allegati correlati al messaggio selezionato. Per visualizzare un file, selezionarlo nell'elenco a sinistra, quindi selezionare **Apri** nel riquadro azioni.

![Pulsante Apri](media/open-button.png)

È inoltre possibile esaminare gli allegati correlati a un'azione specifica eseguita in preedenza per un messaggio. Nella pagina **Messaggi elettronici**, selezionare il messaggio nella Scheda dettaglio **Messaggi**, selezionare l'azione nella Scheda dettaglio **Registro azioni** e selezionare il pulsante **Allegato** nella parte superiore destra della pagina.

È inoltre possibile eseguire l'intera elaborazione o solo una specifica azione selezionando **Esegui elaborazione** nel riquadro azioni.

### <a name="electronic-message-items"></a>Elementi del messaggio elettronico

La pagina **Elementi del messaggio elettronico** presenta tutti gli elementi del messaggio e un registro delle azioni che sono state eseguite per ogni elemento del messaggio. Visualizza inoltre i campi aggiuntivi definiti per gli elementi del messaggio nonché i valori di questi campi aggiuntivi.

Nella tabella seguente sono descritti i campi della scheda **Elementi del messaggio**.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr>
<td>Elaborazione in corso</td>
<td>Il nome dell'elaborazione utilizzata per creare l'elemento del messaggio.</td>
</tr>
<tr>
<td>Elemento del messaggio</td>
<td>L'ID dell'elemento del messaggio. Questo ID viene assegnato automaticamente in base alla sequenza numerica <strong>Elemento del messaggio</strong> definita nella pagina <strong>Parametri di contabilità generale</strong>.</td>
</tr>
<tr>
<td>Data elemento del messaggio</td>
<td>La data di creazione dell'elemento del messaggio.</td>
</tr>
<tr>
<td>Tipo di elemento del messaggio</td>
<td>Il tipo di elemento del messaggio. Diversi tipi di elementi del messaggio possono essere configurati per la stessa elaborazione (ad esempio, <strong>Fatture in entrata</strong> e <strong>Fatture in uscita</strong>). Questo campo può essere compilato automaticamente solo quando una fattura viene aggiunta alla tabella Elementi del messaggio.</td>
</tr>
<tr>
<td>Stato elemento del messaggio</td>
<td>Lo stato effettivo dell'elemento del messaggio. Gli stati disponibili variano a seconda del tipo di elemento del messaggio. Di seguito sono riportati alcuni esempi.
<ul>
<li><strong>Popolato</strong> - Un record è stato aggiunto alla tabella Elementi del messaggio.</li>
<li><strong>Valutato</strong> - Ulteriori attributi sono stati calcolati per l'elemento del messaggio.</li>
<li><strong>Dichiarato</strong> - L'elemento del messaggio è stato aggiunto correttamente a un report.</li>
<li><strong>Escluso</strong> - Questo stato può risultare utile se è necessario escludere alcuni elementi del messaggio da un report prima che venga esportato.</li>
</ul>
</td>
</tr>
<tr>
<td>Data di trasmissione</td>
<td>Per l'elaborazione che trasmette automaticamente un report generato al di fuori del sistema, la data in cui l'elemento del messaggio è stato trasmesso.</td>
</tr>
<tr>
<td>Numero documento</td>
<td>Questo campo viene riempito automaticamente in base alla configurazione dell'azione di popolamento record. Questo campo può essere compilato automaticamente solo quando una fattura viene aggiunta alla tabella Elementi del messaggio.</td>
</tr>
<tr>
<td>Numero di conto</td>
<td>Il numero di conto di un cliente o di un fornitore (o un altro valore del campo, a seconda del campo specificato nell'azione Popola record). Questo campo può essere compilato automaticamente solo quando una fattura viene aggiunta alla tabella Elementi del messaggio.</td>
</tr>
<tr>
<td>Messaggio</td>
<td>Il numero del messaggio. Questo numero viene assegnato automaticamente in base alla sequenza numerica <strong>Messaggio</strong> definita nella pagina <strong>Parametri di contabilità generale</strong>.</td>
</tr>
<tr>
<td>Stato messaggio</td>
<td>Lo stato effettivo del messaggio elettronico.</td>
</tr>
<tr>
<td>Azione successiva</td>
<td>Le azioni successive che possono essere avviate per lo stato corrente dell'elemento del messaggio.</td>
</tr>
</tbody>
</table>

Nella scheda **Campi aggiuntivi** sono visualizzati i campi aggiuntivi per l'elemento del messaggio selezionato e i relativi valori.

#### <a name="run-processing"></a>Esegui elaborazione

Selezionare **Esegui elaborazione** nel riquadro azioni per eseguire l'elaborazione per gli elementi del messaggio. Per eseguire un'azione specifica, nella finestra di dialogo **Esegui elaborazione**, impostare l'opzione **Scegli azione** su **Sì**, quindi selezionare un'azione. Per eseguire l'intera elaborazione, lasciare l'opzione **Scegli azione** su **No**.

#### <a name="generate-report"></a>Genera report

Selezionare **Genera report** nel riquadro azioni per generare un report. Questo pulsante è associato alle azioni **Esportazione creazione di report elettronici**.

#### <a name="update-status"></a>Aggiorna stato

Selezionare **Aggiorna stato** nel riquadro azioni per aggiornare lo stato di uno o più degli elementi del messaggio. Nella finestra di dialogo **Aggiorna stato**, utilizzare la scheda dettaglio **Record da includere** per selezionare gli elementi del messaggio da aggiornare. Assicurarsi di definire correttamente i criteri di selezione, poiché gli stati dell'elemento del messaggio verranno aggiornati in base a questi criteri, lo stato iniziale dell'azione selezionata e il valore **Nuovo stato** impostato. Dopo il completamento di un aggiornamento dello stato, risulterà difficile determinare quali elementi sono stati aggiornati. Di conseguenza, sarà difficile eseguire il rollback dell'aggiornamento dello stato.

#### <a name="electronic-messages"></a>Messaggi elettronici

Selezionare **Messaggi elettronici** nel Riquadro azioni per esaminare un messaggio elettronico correlato all'elemento del messaggio selezionato.

È anche possibile esaminare tutti i file correlati a uno specifico elemento del messaggio. Selezionare il campo **Messaggio** per l'elemento del messaggio o **Messaggi elettronici** nel Riquadro azioni. Quindi, nella pagina **Messaggio elettronico**, selezionare il messaggio per esaminare i file e il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.

![Pulsante Allegato](media/attachment-icon.png)

La pagina **Allegati** visualizza tutti gli allegati correlati al messaggio. Per visualizzare un file, selezionarlo nell'elenco a sinistra, quindi selezionare **Apri** nel riquadro azioni.

![Pulsante Apri](media/open-button.png)

#### <a name="original-document"></a>Documento originale

Selezionare **Documento originale** nel riquadro azioni per aprire il documento originale per l'elemento del messaggio selezionato.

## <a name="example-set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Esempio: configurare ed eseguire l'elaborazione per chiamare un formato di esportazione ER semplice con cui generare un report di Excel

Dopo aver creato il formato ER, averlo mappato alle origini dati e completato, è possibile eseguirlo utilizzando l'area di lavoro **Crazione di report elettronici**. Viene generato un report che può essere salvato localmente.

Per controllare i seguenti aspetti del processo di reporting, è necessario configurare l'elaborazione della messaggistica elettronica:

- Registrare informazioni sull'utente che ha generato il report.
- Registrare informazioni su quando il report è stato generato.
- Salva i report generati per i periodi precedenti.

In questa sezione è riportato un esempio che mostra come è possibile impostare la messaggistica elettronica per generare un report basato su un formato ER di esportazione per Excel. Se si intende seguire questo esempio, il formato di esportazione ER di Excel deve essere già stato creato, mappato alle origini dati e completato. Inoltre, una sequenza numerica deve essere già stata configurata per i messaggi elettronici.

Quando si crea l'elaborazione, è utile definire dapprima gli stati e le azioni di elaborazione che verranno impostati. L'illustrazione seguente mostra l'elaborazione per questo esempio.

![Schema di elaborazione](media/processing-scheme.png)

#### <a name="create-message-statuses"></a>Creare stati del messaggio

1. Accedere a **Imposta \> Impostazione \> Messaggi elettronici \> Stati del messaggio**.
2. Creare i seguenti stati del messaggio:

    - Nuovo
    - Preparato
    - Generato

    ![Stati del messaggio](media/message-statuses.png)

3. Nella riga dello stato **Nuovo**, selezionare la casella di controllo **Consenti eliminazione** per consentire agli utenti di eliminare i messaggi con tale stato.

#### <a name="create-additional-fields"></a>Creare campi aggiuntivi

1. Accedere a **Imposta \> Impostazione \> Messaggi elettronici \> Campi aggiuntivi**.
2. Aggiungere un campo aggiuntivo e i relativi valori. Ecco un esempio.

    ![Campi aggiuntivi](media/additional-fields.png)

3. Impostare **Modifica utente** su **Sì** per consentire agli utenti di modificare il campo.

#### <a name="create-message-processing-actions"></a>Creare azioni di elaborazione messaggi

Per questo esempio, creeremo le seguenti azioni:

- **Crea messaggio**
- **Aggiorna a preparato**
- **Genera report**
- **Aggiorna a stato iniziale** (facoltativo)

1. Accedere a **Imposta \> Impostazione \> Messaggi elettronici \> Azioni di elaborazione messaggi**.
2. Creare un'azione denominata **Crea messaggio**. Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Crea messaggio**.
3. Creare un'azione denominata **Aggiorna a preparato** e impostare i seguenti campi:

    - Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Elaborazione utente livello del messaggio**.
    - Nella scheda Dettaglio **Stati iniziali**, nel campo **Stato messaggio**, selezionare **Nuovo**.
    - Nella scheda Dettaglio **Stati di risultati**, nel campo **Stato messaggio**, selezionare **Preparato**. Nel campo **Tipo di risposta**, immettere **Esecuzione completata**.

4. Creare un'azione denominata **Genera report** e impostare i seguenti campi:

    - Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Esportazione creazione di report elettronici**. Nel campo **Mapping formato**, selezionare il formato ER di esportazione. Le opzioni sono **Excel**, **XML**, **JSON**, **Testo** e **Altro**.
    - Nella scheda Dettaglio **Stati iniziali**, nel campo **Stato messaggio**, selezionare **Preparato**.
    - Nella scheda Dettaglio **Stati di risultati**, nel campo **Stato messaggio**, selezionare **Generato**. Nel campo **Tipo di risposta**, immettere **Esecuzione completata**.

    ![Azione Genera report](media/generate-report-action.png)

5. Facoltativo: per consentire agli utenti di generare un report più volte, è possibile creare un'azione **Aggiorna a stato iniziale** e impostare i seguenti campi:

    - Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Elaborazione utente livello del messaggio**.
    - Nella scheda Dettaglio **Stati iniziali**, nel campo **Stato messaggio**, selezionare **Generato**.
    - Nella Scheda dettaglio **Stati di risultati**, aggiungere una riga distinta per ognuno dei due stati (**Preparato** e **Nuovo**). Per entrambe le righe, impostare il campo **Tipo di risposta** su **Eseguito correttamente**.

#### <a name="electronic-message-processing"></a>Elaborazione messaggio elettronico

In questo esempio, tutte le azioni devono essere configurate di modo che possano essere eseguite separatamente. Si presuppone che l'utente inizializzerà ogni azione.

1. Accedere a **Imposta \> Impostazione \> Messaggi elettronici \> Elaborazione messaggio elettronico**.
2. Aggiungere un record per l'elaborazione, tutte le azioni definite in precedenza e un campo aggiuntivo.
3. Facoltativo: nella scheda Dettaglio **Ruoli di sicurezza**, definire i ruoli di sicurezza per l'elaborazione per limitare l'accesso a specifico reporting.
4. Accedere a **Imposta \> Richieste di informazioni e report \> Messaggi elettronici \> Messaggi elettronici**.
5. Selezionare **Nuovo** per creare un messaggio. A questo punto, è possibile aggiungere date e una descrizione. È anche possibile aggiornare il valore del campo aggiuntivo come necessario.

    ![Creare un messaggio elettronico](media/create-electronic-message.png)

La griglia nella scheda Dettaglio **Registro azioni** viene automaticamente riempita con un registro di tutte le azioni eseguite sul messaggio.

È ora possibile eliminare o aggiornare lo stato del messaggio. Per aggiornare lo stato del messaggio, selezionare **Aggiorna stato**. Nel campo **Nuovo stato** selezionare **Preparato** e selezionare **OK**.

![Aggiornare lo stato del messaggio](media/update-status.png)

Lo stato del messaggio viene aggiornato a **Preparato** ed è possibile generare il report selezionando **Genera report**. Il report viene generato e lo stato del messaggio e il registro delle azioni del vengono aggiornati. Per visualizzare il report generato, selezionare il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]