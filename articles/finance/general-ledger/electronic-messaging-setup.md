---
title: Impostare i messaggi elettronici
description: Questo argomento fornisce informazioni su come impostare la funzionalità dei messaggi elettronici (EM).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 947170d1db132ca5a6b7caed0e47ee814b9148cc
ms.sourcegitcommit: 73d320d2103f2b0c6ecbb2b9df746469bc544ea2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "6433794"
---
# <a name="set-up-electronic-messages"></a>Impostare i messaggi elettronici

[!include [banner](../includes/banner.md)]

La funzionalità **Messaggi elettronici** consente la gestione di processi di creazione di reporting elettronici differenti per vari tipi di documento. In alcuni scenari complessi, che supportano [funzionalità di creazione di report specifiche per paese](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality), la messaggistica elettronica viene configurata in modo da avere una combinazione di molti stati del messaggio, stati di elementi del messaggio, azioni, campi aggiuntivi e classi eseguibili. Per questi scenari, sono disponibili pacchetti di entità di dati per l'importazione. Se si utilizzano questi pacchetti di entità di dati, importarli in un'entità legale usando lo strumento di gestione dati. Per ulteriori informazioni su come utilizzare lo strumento di gestione dati, vedere [Gestione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Se non si importa un pacchetto di entità di dati, è possibile configurare manualmente la funzionalità EM. In tal caso, è necessario configurare i seguenti elementi.

- [Sequenze numeriche](#sequences)
- [Tipi di elementi del messaggio](#types)
- [Stati elementi dei messaggi](#item)
- [Stati del messaggio](#statuses)
- [Campi aggiuntivi](#additional)
- [Impostazioni classe eseguibile](#executable)
- [Azioni di popolamento record](#populate)
- [Applicazioni Web](#applications)
- [Impostazioni servizio Web](#settings)
- [Azioni di elaborazione messaggi](#actions)
- [Elaborazione messaggio elettronico](#processing)

Nelle sezioni seguenti vengono fornite altre informazioni su ognuno di tali elementi.

## <a name="number-sequences"></a><a id="sequences"></a>Sequenze numeriche

Configurare sequenze numeriche per messaggi ed elementi del messaggio. Le sequenze numeriche sono quindi utilizzate per numerare automaticamente i messaggi e gli elementi dei messaggii. I numeri assegnati vengono utilizzati come identificatori univoci per i messaggi e gli elementi dei messaggi nel sistema. È possibile configurare sequenze numeriche per la messaggistica elettronica andando **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.

## <a name="message-item-types"></a><a id="types"></a>Tipi di elementi del messaggio

I tipi di elementi del messaggio identificano i tipi di record che vengono utilizzati nei messaggi elettronici. È possibile configurare tipi di elementi del messaggio andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Tipi di elementi del messaggio**.

## <a name="message-item-statuses"></a><a id="item"></a>Stati elementi dei messaggi

Gli stati degli elementi del messaggio identificano gli stati si applicano agli elementi del messaggio nell'elaborazione che si sta configurando. È possibile configurare stati di elementi del messaggio andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Stati elementi dei messaggi**.

Il parametro **Consenti eliminazione** di uno stato di elementi del messaggio definisce se è possibile eliminare elementi dei messaggi che hanno questo stato nella pagina **Messaggi elettronici** o **Elementi del messaggio elettronico**.

## <a name="message-statuses"></a><a id="statuses"></a>Stati del messaggio

Configurare gli stati del messaggio che devono essere disponibili nell'elaborazione dei messaggi. È possibile configurare stati del messaggio andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Stati messaggi**.

Nella tabella seguente sono descritti i campi della pagina **Stati del messaggio**.

| Nome campo          | Descrizione |
|---------------------|-------------|
| Stato messaggio      | Immettere un nome univoco per lo stato del messaggio. Gli stati dei messaggi sono utilizzati per caratterizzare lo stato di un messaggio elettronico in qualsiasi momento. Il nome immesso viene visualizzato nella pagina **Messaggi elettronici** e in un registro correlato ai messaggi elettronici. |
| Descrizione         | Immettere una descrizione dello stato del messaggio. |
| Tipo di risposta       | Selezionare il tipo di risposta per lo stato del messaggio. Alcune azioni in un elaborazione possono generare più tipi di risposta. Ad esempio, un'azione di tipo **Servizio Web** può generare risposte di tipo **Eseguito correttamente** o **Errore tecnico** a seconda del risultato della relativa esecuzione. In questo caso definire gli stati del messaggio per entrambi i tipi di risposta. Per ulteriori informazioni sui tipi di azioni e i tipi di risposta ad essi correlati, vedere la sezione [Tipi di azioni di elaborazione messaggi](#action-types) più avanti in questo argomento. |
| Stato elemento del messaggio | A volte, lo stato di un messaggio elettronico deve influenzare lo stato degli elementi del messaggio correlati. Selezionare lo stato di un articolo di messaggio in questo campo per associarlo allo stato del messaggio. |
| Consenti eliminazione        | Selezionare questa casella di controllo se gli utenti devono poter eliminare i messaggi elettronici con questo stato nella pagina **Messaggi elettronici**. |

## <a name="additional-fields"></a><a id="additional"></a>Campi aggiuntivi

La funzionalità EM ti consente di raccogliere record da tabelle transazionali in Microsoft Dynamics 365 Finance come elementi del messaggio. In questo modo, è possibile preparare i record per il reporting e quindi includerli nei report. Tuttavia, le tabelle transazionali talvolta non hanno informazioni sufficienti per completare i record in un modo che soddisfa i requisiti di reporting. Per immettere tutte le informazioni che devono essere incluse in un report per un record, è possibile configurare ulteriori campi. Ulteriori campi possono essere associati a messaggi e a elementi del messaggio. È possibile configurare campi aggiuntivi andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Campi aggiuntivi**.

Nella seguente tabella sono descritti i campi generali della pagina **Campi aggiuntivi**.

| Campo       | descrizione |
|-------------|-------------|
| Nome campo  | Immettere il nome di un campo aggiuntivo per i messaggi elettronici o gli elementi del messaggio correlati al processo. Questo nome viene visualizzato nell'interfaccia utente durante il processo. Il nome può anche essere utilizzato nelle configurazioni Creazione di report elettronici ER correlate al processo. |
| descrizione | Immettere una descrizione del campo aggiuntivo. |
| Modifica utente   | Impostare questa opzione su **Sì** se gli utenti devono poter modificare il valore del campo aggiuntivo dell'interfaccia utente. |
| Contatore     | Impostare questa opzione su **Sì** se il campo aggiuntivo deve contenere una sequenza numerica in un messaggio elettronico. Il valore del campo aggiuntivo viene immesso automaticamente durante l'esecuzione di un'azione di tipo **Esportazione creazione di report elettronici**. |
| Nascosto      | Impostare questa opzione su **Sì** se il campo aggiuntivo deve essere nascosto nell'interfaccia utente della pagina **Messaggi elettronici** o della pagina **Elementi del messaggio elettronico**. |

Sulla Scheda dettaglio **Valori** è possibile predefinire i valori che può avere un campo aggiuntivo. Questi valori sono quindi disponibili per la selezione da parte degli utenti. Pertanto, non devono essere compilati manualmente durante l'elaborazione. Nella seguente tabella vengono descritti i campi.

| Campo                | descrizione |
|----------------------|-------------|
| Valore campo          | Immettere il valore del campo da utilizzare per un messaggio o elemento del messaggio durante il reporting. |
| Descrizione          | Immettere una descrizione del valore del campo. |
| Tipo di account         | Alcuni valori dei campi potrebbero essere limitati a specifici tipi di conto. Selezionare uno dei seguenti valori: **Tutto**, **Cliente** o **Fornitore**. |
| Codice conto         | Se si è selezionato **Cliente** o **Fornitore** nel campo **Tipo di conto**, è possibile limitare ulteriormente l'utilizzo del valore del campo a uno specifico gruppo o tabella. |
| Numero conto/gruppo | Se si è selezionato **Cliente** o **Fornitore** nel campo **Tipo di conto** e si è immesso un gruppo o una tabella nel campo **Codice conto**, è possibile immettere uno specifico gruppo o agente doganale in questo campo. |
| Valido            | Specificare la data alla quale si deve iniziare a considerare il valore. |
| Scadenza           | Specificare la data alla quale il valore non deve più considerare il valore. |

Per impostazione predefinita, le combinazioni di criteri definiti dai campi **Numero conto/gruppo**, **Codice conto**, **Validità** e **Scadenza** non influiscono sulla selezione dei valori di campi aggiuntivi. Tuttavia, queste combinazioni possono essere utilizzate in una classe eseguibile per implementare una logica specifica che calcola i valori dei campi aggiuntivi.

## <a name="executable-class-settings"></a><a id="executable"></a>Impostazioni classe eseguibile

Una classe eseguibile è un metodo o classe X++ che l'elaborazione del messaggio elettronico può chiamare in relazione a un'azione se una valutazione viene richiesta per il processo.

È possibile impostare manualmente una classe eseguibile che deve essere chiamata durante l'elaborazione andando su **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Impostazioni classe eseguibile**. Nella pagina **Impostazioni classe eseguibile** creare una riga e impostare i seguenti campi.

| Campo                 | descrizione |
|-----------------------|-------------|
| Classe eseguibile      | Immettere il nome che verrà utilizzato durante la configurazione di un'azione di elaborazione messaggi in relazione alla quale questa classe viene chiamata. |
| Descrizione           | Immettere una descrizione della classe eseguibile. |
| Nome classe eseguibile | Selezionare una classe eseguibile X++. |
| Livello di esecuzione       | Questo campo viene impostato automaticamente, in quanto il valore è predefinito per la classe eseguibile selezionata. Questo campo limita il livello di esecuzione della valutazione correlata. |
| Descrizione classe     | Questo campo viene impostato automaticamente, in quanto il valore è predefinito per la classe eseguibile selezionata. |
| Tipo di azione           | Questo campo è disponibile quando la funzionalità **\[ EM\] Tipo di azione di classe eseguibile** è attivata nell'area di lavoro **Gestione funzionalità**. Utilizzare questo campo per specificare il tipo di azione per la classe eseguibile. Questo campo offre un controllo più preciso sulle prossime azioni disponibili per il messaggio elettronico nella pagina **Messaggi elettronici**. |

Alcune classi eseguibili potrebbero avere parametri obbligatori che devono essere definiti prima della prima esecuzione della classe eseguibile. Per definire questi parametri, nel riquadro Azioni selezionare **Parametri**. Nella finestra di dialogo visualizzata impostare i campi, quindi selezionare **OK**. È importante selezionare **OK**. In caso contrario, i parametri non verranno salvati nel database e la classe eseguibile non verrà chiamata correttamente.

## <a name="populate-records-actions"></a><a id="populate"></a>Azioni di popolamento record

Le azioni di popolamento record sono utilizzate per configurare azioni che aggiungono record alla tabella Elementi del messaggio affinché possano essere aggiunti a un messaggio elettronico. Ad esempio, se il messaggio elettronico deve includere fatture cliente, è necessario configurare un'azione Popola record che è collegata al campo **Origine dati** nella tabella Giornale di registrazione fatture cliente.

È possibile configurare azioni di popolamento record andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Azioni di popolamento record**. Creare un nuovo record per ogni azione che deve aggiungere record alla tabella e impostare i campi seguenti.

| Campo       | Descrizione |
|-------------|-------------|
| Nome        | Immettere un nome per l'azione che completa i record nel processo. |
| Descrizione | Immettere una descrizione dell'azione Popola record. |

Nella scheda Dettaglio **Impostazione origini dati**, aggiungere una riga per ogni origine dati utilizzata per il processo e impostare i seguenti campi.

| Campo                  | Descrizione |
|------------------------|-------------|
| Nome                   | Immettere un nome per l'origine dati. |
| Tipo di elemento del messaggio      | Selezionare il tipo di elemento del messaggio da utilizzare durante la creazione dei record per l'origine dati. |
| Tipo di account           | Selezionare il tipo di conto da associare ai record dell'origine dati. |
| Nome tabella master      | Selezionare la tabella che sarà un'origine dati. |
| Campo Numero documento  | Selezionare il campo da cui verrà ottenuto il numero di documento nella tabella master specificata. Il valore di questo campo viene utilizzato come valore del campo **Numero documento** per l'elemento del messaggio. |
| Campo Data documento    | Selezionare il campo da cui verrà ottenuto la data del documento nella tabella master specificata. Il valore di questo campo viene utilizzato come valore del campo **Data elemento del messaggio** per l'elemento del messaggio. |
| Campo Conto documento | Selezionare il campo da cui verrà ottenuto il conto del documento nella tabella master specificata. Il valore di questo campo viene utilizzato come valore del campo **Numero conto** per l'elemento del messaggio. |
| Società                | Questo campo è disponibile quando la funzionalità **Query interaziendali per le azioni di popolamento dei record** è attivata nell'area di lavoro **Gestione funzionalità**. Utilizzare questa funzionalità per impostare origini dati interaziendali per le azioni di popolamento dei record. I dati possono essere recuperati da più aziende. |
| Query utente             | <p>Se imposti una query scegliendo **Modifica query** sopra la griglia e si specificano i criteri che devono essere applicati alla tabella master selezionata da cui vengono compilati i dati, questa casella di controllo viene selezionata automaticamente. In caso contrario, tutti i record vengono completati a partire dall'origine tabella master.</p><p>Quando la funzionalità **Query interaziendali per le azioni di popolamento dei record** è attivata nell'area di lavoro **Gestione funzionalità** e i record devono essere raccolti da diverse società, aggiungere una riga per ogni ulteriori persona giuridica che deve essere inclusa nella creazione di report. Per ogni nuova riga, selezionare **Modifica query** e indicare un criterio correlato che è specifico per la persona giuridica che riportata nel campo **Società** sulla riga. Al termine, la griglia **Impostazione origini dati** conterrà le righe per tutte le persone giuridiche che devono essere incluse nella creazione di report.</p> |

## <a name="web-applications"></a><a id="applications"></a>Applicazioni Web

Per configurare un'applicazione Web di modo che supporti Open Authorization (OAuth) 2.0, utilizzare le impostazioni dell'applicazione Web. OAuth è lo standard aperto che consente agli utenti di concedere l'"accesso delegato protetto" all'applicazione per loro conto, senza condividere le loro credenziali di accesso. È anche possibile eseguire il processo di autorizzazione ottenendo un codice di autorizzazione e un token di accesso. È possibile configurare le impostazioni dell'applicazione Web andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Applicazioni Web**.

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
| Il token di accesso scadrà tra  | Il tempo rimanente prima della scadenza del token di accesso. Questo campo viene aggiornato automaticamente. | 
| Conferma                       | Specificare la proprietà **Accetta** della richiesta Web. Ad esempio, immettere **application/vnd.hmrc.1.0+json**. |
| Tipo di contenuto                 | Specificare il tipo di contenuto. Ad esempio,, immettere **application/json**. |

Inoltre, i seguenti pulsanti sono disponibili nel Riquadro azioni della pagina **Applicazioni Web** per supportare il processo di autorizzazione:

- **Ottieni codice di autorizzazione** - Inizializzare l'autorizzazione dell'applicazione Web. Questa funzione utilizza il formato ER specificato nel campo **Mapping formato autorizzazione** per generare una richiesta di autorizzazione.
- **Ottieni token di accesso** - Inizializzare il processo di acquisizione di un token di accesso.
- **Aggiorna token di accesso** - Aggiornare un token di accesso. Questa funzione utilizza il formato ER specificato nel campo **Importa mapping modello token** per importare informazioni sul token di accesso ricevuto.

Quando un token di accesso per un'applicazione Web viene archiviato nel database del sistema in formato crittografato, può essere utilizzato per le richieste a un servizio Web. Per scopi di sicurezza l'accesso al token deve essere limitato ai ruoli di sicurezza a cui deve essere consentita l'elaborazione di tali richieste. Se qualcuno all'esterno del gruppo di sicurezza tenta di elaborare una richiesta, viene generato un errore indicante che questi non sono autorizzati a interagire tramite l'applicazione Web selezionata. Per impostare i ruoli di sicurezza che devono avere accesso al token di accesso, utilizzare la Scheda dettaglio **Ruoli di sicurezza** della pagina **Applicazioni Web**. Se i ruoli di sicurezza non vengono definiti per un'applicazione Web, solo un amministratore di sistema può interagire tramite questa applicazione Web.

Per ogni azione con l'applicazione Web selezionata, la Scheda dettaglio **Registro azioni** salva le informazioni sull'utente e la data e l'ora.

Alcuni servizi Web potrebbero richiedere l'inclusione di intestazioni diverse nelle richieste. L'amministratore di sistema può impostare intestazioni aggiuntive e i loro valori sulla Scheda dettaglio **Intestazioni supplementari**, quindi utilizzarli durante la generazione della richiesta.

## <a name="web-service-settings"></a><a id="settings"></a>Impostazioni servizio Web

Utilizzare le impostazioni del servizio Web per configurare la trasmissione di dati diretta a un servizio Web. È possibile configurare le impostazioni del servizio Web andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Impostazioni servizio Web**.

Nella seguente tabella sono descritti i campi della pagina **Impostazioni servizio Web**.

| Campo                          | Descrizione |
|--------------------------------|-------------|
| Servizio Web                    | Immettere un nome per il servizio Web. |
| Descrizione                    | Immettere una descrizione del servizio Web. |
| Indirizzo Internet               | <p>Immettere l'indirizzo Internet del servizio Web. Se un'applicazione Web viene specificata per il servizio Web e se l'indirizzo Internet del servizio Web deve essere uguale a quello definito per quell'applicazione Web, selezionare **Copia URL di base**. L'URL di base dell'applicazione Web viene quindi copiato in questo campo.</p><p>**Avvertimento:** i servizi di terze parti o altri servizi configurati qui non richiedono la certificazione e potrebbero non soddisfare gli standard di privacy di Microsoft. Si dovrebbe rivedere la documentazione sulla privacy di ciascun servizio e collaborare con ciascun provider di servizi per saperne di più sul livello di conformità fornito dal suo servizio. Si ha la responsabilità di garantire che questi servizi soddisfino i propri standard di sicurezza, privacy e legali. L'utilizzo dei servizi è a proprio rischio. Non vengono fornite garanzie né condizioni esplicite. Si consiglia vivamente di utilizzare solo servizi che forniscono connessioni sicure e autorizzate, come HTTPS.</p> |
| Certificato                    | Selezionare un certificato Azure Key Vault configurato in precedenza. |
| Applicazione Web                | Selezionare un'applicazione Web configurata in precedenza. |
| Tipo di risposta – XML        | Impostare questa opzione su **Sì** se il tipo di risposta è XML. |
| Metodo di richiesta                 | Specificare il metodo della richiesta. HTTP definisce un set di metodi di richiesta che indicano l'azione che dovrà essere eseguita per una risorsa data. Il metodo di richiesta può essere **GET**, **POST** o un altro metodo HTTP. |
| Intestazioni richieste                | Specificare le intestazioni di richieste. Un'intestazione di richiesta è un'intestazione HTTP che può essere utilizzata in una richiesta HTTP. Non è correlata al contenuto del messaggio. |
| Conferma                         | Specificare la proprietà accept della richiesta Web. |
| Accetta codifica                | Specificare il valore accept-encoding. L'intestazione HTTP della richiesta Accept-Encoding annuncia la codifica del contenuto che il client può comprendere. Questa codifica del contenuto è in genere un algoritmo di compressione. |
| Tipo di contenuto                   | Specificare il tipo di contenuto. L'intestazione HTTP dell'entità Content-Type indica il tipo di media della risorsa. |
| Codice di risposta operazione riuscita       | Specificare il codice di stato HTTP indicante che la richiesta è riuscita. |
| Mapping formato intestazioni richiesta | Selezionare il formato di ER utilizzato per generare intestazioni di richieste Web. |

## <a name="message-processing-actions"></a><a id="actions"></a>Azioni di elaborazione messaggi

Le azioni di elaborazione messaggi consentono di creare azioni per i processi e configurare i relativi parametri. È possibile configurare azioni di elaborazione messaggi andando a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Azioni di elaborazione messaggi**.

Nelle tabelle seguenti vengono descritti i campi della pagina **Azioni di elaborazione messaggi**.

### <a name="general-fasttab"></a>Scheda dettaglio Generale

| Campo                                     | Descrizione |
|-------------------------------------------|-------------|
| Tipo di azione                               | Selezionare il tipo di azione. Per informazioni sulle opzioni disponibili, vedere la sezione [Tipi di azioni di elaborazione messaggi](#action-types) più avanti in questo argomento. |
| Mapping formato                            | Selezionare il formato ER che deve essere chiamato per l'azione. Questo campo è disponibile solo per le azioni **Esportazione creazione di report elettronici**, **Importazione creazione di report elettronici** e **Messaggio esportazione creazione di report elettronici**. |
| Mapping formato per percorso URL               | Selezionare il formato ER che deve essere chiamato per l'azione. Questo formato viene utilizzato per comporre il percorso dell'indirizzo URL che verrà aggiunto all'indirizzo Internet di base specificato per il server Web selezionato. Questo campo è disponibile solo per le azioni di tipo **Servizio Web**. |
| Tipo di elemento del messaggio                         | Selezionare il tipo di record per il quale l'azione deve essere valutata. Questo campo è disponibile per le azioni di tipo **Livello di esecuzione dell'elemento del messaggio**, **Esportazione creazione di report elettronici**, **Importazione creazione di report elettronici**, **Servizio Web** e altri tipi. Se si lascia vuoto questo campo, vengono valutati tutti i tipi di elementi del messaggio definiti per l'elaborazione del messaggio. |
| Classe eseguibile                          | Selezionare un'impostazione di classe eseguibile esistente. Questo campo è disponibile solo per le azioni **Livello di esecuzione dell'elemento del messaggio** e **Livello di esecuzione dell'elemento del messaggio**. |
| Azione di popolamento record                   | Selezionare un'azione di popolamento record esistente. Questo campo è disponibile solo per le azioni **Popola record**. |
| Servizio Web                               | Selezionare un servizio Web esistente. Questo campo è disponibile solo per le azioni di tipo **Servizio Web**. |
| Nome file                                 | Specificare il nome del file creato a seguito dell'azione. Questo file può essere la risposta dal server Web o dal report generato. Questo campo è disponibile solo per le azioni di tipo **Servizio Web** e **Messaggio esportazione creazione di report elettronici**. |
| Collega file ai documenti di origine          | Selezionare questa casella di controllo per allegare i file generati ai record in una tabella master di riferimento per gli elementi EM. Questo campo è disponibile solo per le azioni dei tipi **Esportazione creazione di report elettronici** e **Servizio Web**. |
| Allega file dall'archivio di output agli elementi | Selezionare questa casella di controllo per estrarre file XML separati dal file di archivio di output e allegarli agli elementi corrispondenti del messaggio elettronico. Questo campo è disponibile solo per le azioni di tipo **Esportazione creazione di report elettronici**. |
| Numero di elementi di messaggi per esportazione        | Specificare il limite al numero di elementi del messaggio che devono essere inclusi in un file (messaggio). Questo campo è disponibile solo per le azioni di tipo **Esportazione creazione di report elettronici**. |
| Utilizzare origine ER                             | Selezionare questa casella di controllo per utilizzare i parametri di origine ER per l'importazione. In caso contrario, viene utilizzato l'allegato del messaggio elettronico. Questo campo è disponibile solo per le azioni del tipo **Importazione creazione di report elettronici**. |
| Mostra finestra dialogo                               | Impostare questa opzione su **Sì** se una finestra di dialogo deve essere visualizzata agli utenti prima della generazione del report. Questo campo è disponibile solo per le azioni di tipo **Messaggio esportazione creazione di report elettronici**. |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>Tipi di azioni di elaborazione messaggi

Nel campo **Tipo di azione** sono disponibili le seguenti opzioni:

- **Crea messaggio** - Utilizzare questo tipo di azione per consentire agli utenti di creare manualmente messaggi nella pagina **Messaggio elettronico**. Uno stato iniziale non può essere configurato per un'azione di questo tipo.
- **Popola record** - Questo tipo di azione deve essere già impostato. Associarlo a un'azione di popolamento di record affinché sia inclusa nell'elaborazione. Si presuppone che questo tipo di azione sia utilizzato per la prima azione nell'elaborazione del messaggio (quando nessun messaggio elettronico è stato creato in anticipo) o per un'azione che aggiunge elementi del messaggio a un messaggio creato in precedenza (mediante un tipo di azione **Crea messaggio**). Di conseguenza, per le azioni di questo tipo, uno stato di risultati dei soli può essere configurato solo per elementi del messaggio. Uno stato iniziale può essere configurato solo per i messaggi.
- **Livello di esecuzione del messaggio** - Utilizzare questo tipo di azione per configurare una classe eseguibile che deve essere valutata a livello del messaggio.
- **Livello di esecuzione dell'elemento del messaggio** - Utilizzare questo tipo di azione per configurare una classe eseguibile che deve essere valutata a livello dell'elemento del messaggio.
- **Esportazione creazione di report elettronici** - Utilizzare questo tipo di azione per le azioni che devono generare un report basato su una configurazione ER di esportazione a livello dell'elemento del messaggio.
- **Messaggio esportazione creazione di report elettronici** - Utilizzare questo tipo di azione per le azioni che devono generare un report basato su una configurazione ER di esportazione a livello del messaggio (ad esempio, quando un messaggio non ha elementi).
- **Importazione creazione di report elettronici** - Utilizzare questo tipo di azione per le azioni che devono generare un report basato su una configurazione ER di importazione.
- **Elaborazione utente livello del messaggio** - Utilizzare questo tipo di azione per le azioni che presuppongono azioni manuali da parte dell'utente a livello del messaggio. Ad esempio, l'utente potrebbe aggiornare lo stato dei messaggi.
- **Elaborazione utente** - Utilizzare questo tipo di azione per le azioni che presuppongono azioni manuali da parte dell'utente a livello dell'elemento del messaggio. Ad esempio, l'utente potrebbe aggiornare lo stato degli elementi del messaggio.
- **Servizio Web** - Utilizzare questo tipo di azione per le azioni che devono trasmettere un report generato a un servizio Web. Questo tipo di azione non viene utilizzato per il reporting relativo alla comunicazione di fatture di vendita e di acquisto per l'Italia. Per questo tipo di azione, la pagina **Azioni di elaborazione messaggi** include una Scheda dettaglio **Dettagli vari** dove è possibile specificare un testo di conferma. Questo testo di conferma viene visualizzato agli utenti prima dell'elaborazione delle richieste al servizio Web selezionato.
- **Verifica richiesta** - Utilizzare questo tipo di azione per la verifica della richiesta da un server.

### <a name="initial-statuses-fasttab"></a>Scheda Dettaglio Stati iniziali

> [!NOTE]
> La scheda dettagli **Stati iniziali** non è disponibile per le azioni con un tipo di azione **Crea messaggio** iniziale.

| Campo               | Descrizione |
|---------------------|-------------|
| Stato elemento del messaggio | Selezionare lo stato dell'elemento del messaggio per il quale l'azione di elaborazione messaggi selezionata deve essere valutata. |
| Descrizione         | Una descrizione dello stato dell'articolo del messaggio selezionato. |

### <a name="result-statuses-fasttab"></a>Scheda Dettaglio Stati di risultati

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

## <a name="electronic-message-processing"></a><a id="processing"></a>Elaborazione messaggio elettronico

L'elaborazione del messaggio elettronico è un concetto di base della funzionalità EM. Aggrega le azioni che devono essere valutate per il messaggio elettronico. Le azioni possono essere collegate tramite uno stato iniziale e uno stato di risultato. In alternativa, le azioni **Elaborazione utente** possono essere avviate indipendentemente. Per impostare l'elaborazione dei messaggi elettronici, andare a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Elaborazione messaggio elettronico**.

La scheda Dettaglio **Azione** consente di aggiungere azioni predefinite all'elaborazione. È possibile specificare se un'azione deve essere eseguita separatamente o se può essere avviata dall'elaborazione. Per specificare che un'azione nell'elaborazione può essere inizializzata solo da un utente, impostare il campo **Esegui separatamente** su **Sì** per quell'azione. Se l'azione deve essere avviata elaborando i messaggi o gli elementi del messaggio nello stato definito come stato iniziale per l'azione, impostare **Esegui separatamente** su **No**. Le azioni di tipo **Azione utente** devono sempre essere eseguite separatamente.

Talvolta, più azioni devono essere aggregate in una sequenza, anche se la prima azione è configurata per essere eseguita separatamente. Ad esempio, un utente deve inizializzare la generazione di report. Tuttavia, subito dopo la generazione del report questo deve essere inviato a un servizio Web e la riposta del servizio Web deve essere riflessa nel sistema. In questo caso, è possibile creare una sequenza inseparabile per le azioni che devono essere sempre eseguite insieme. Nella Scheda dettaglio **Azione**, selezionare **Sequenza inseparabile** sopra la griglia e creare una sequenza. Quindi, per tutte le azioni da eseguire insieme in una sequenza, selezionare la sequenza nel campo **Sequenza inseparabile**. Per questo esempio, il campo **Esegui separatamente** può essere impostato su **Sì** per la prima azione nella sequenza e su **No** per tutte le altre azioni.

Le azioni dei tipi **Esportazione creazione di report elettronici** e **Messaggio esportazione creazione di report elettronici** eseguono un formato ER con parametri di input. Se l'elaborazione del messaggio elettronico include azioni di uno di questi tipi, è necessario specificare i valori per i parametri di input prima della generazione del report. In questo modo, il sistema può utilizzare un regime batch per generare il report. È possibile selezionare **Parametri** sopra la griglia per impostare i parametri per il tipo di azione selezionato (**Esportazione creazione di report elettronici** o **Messaggio esportazione creazione di report elettronici**). Selezionare la casella di controllo **Usa parametri** per l'azione che deve essere eseguita con i parametri specificati in un regime batch.

Utilizzare la Scheda dettaglio **Campi aggiuntivi dell'elemento del messaggio** per aggiungere ulteriori campi predefiniti correlati agli elementi del messaggio. È necessario aggiungere ulteriori campi per ogni tipo di elemento del messaggio a cui i campi sono correlati. È possibile specificare un valore predefinito che verrà assegnato al campo aggiuntivo durante l'elaborazione.

Utilizzare la Scheda dettaglio **Campi aggiuntivi del messaggio** per aggiungere ulteriori campi predefiniti correlati ai messaggi. È possibile specificare un valore predefinito che verrà assegnato al campo aggiuntivo durante l'elaborazione.

Utilizzare la Scheda dettaglio **Ruoli di sicurezza** per configurare i ruoli di sicurezza che sono predefiniti nel sistema per una specifica elaborazione. Gli utenti con un ruolo specifico avranno accesso solo all'elaborazione definita per tale ruolo.

Utilizzare la Scheda dettaglio **Batch** per configurare l'elaborazione per l'utilizzo in un regime batch. Si consiglia di impostare un regime batch per l'elaborazione direttamente nella pagina **Messaggi elettronici** o **Elementi di messaggi elettronici**, quando si seleziona **Esegui elaborazione** nel riquadro Azioni per avviare l'elaborazione.
