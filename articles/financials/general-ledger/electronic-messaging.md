---
title: Messaggistica elettronica
description: In questo argomento vengono fornite informazioni sulla messaggistica elettronica in Microsoft Dynamics 365 for Finance and Operations e sulla relativa configurazione.
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: 232398a6c4193d0074881e26fff361deb9784bf2
ms.openlocfilehash: 082ad886f40a52457900523f44158da3ed939458
ms.contentlocale: it-it
ms.lasthandoff: 12/04/2018

---

# <a name="electronic-messaging"></a>Messaggistica elettronica

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sulla messaggistica elettronica in Microsoft Dynamics 365 for Finance and Operations e sulla relativa configurazione.

Recentemente, governi e autorità legislative di vari paesi hanno implementato requisiti di reporting per le società registrate in tali paesi. Lo scopo dei requisiti è di consentire di ottenere i dati di tali società in formato elettronico, direttamente dai sistemi in cui sono stati valutati, archiviati ed elaborati.

La funzionalità Messaggi elettronici in Finance and Operations supporta vari processi per l'interoperazione elettronica tra Finance and Operations e i sistemi che governi e autorità legislative forniscono per il reporting, la presentazione e la ricezione di informazioni ufficiali.

La funzionalità Messaggi elettronici è integrata con il modulo **Creazione di report elettronici** (ER). Di conseguenza, è possibile configurare formati ER per messaggi elettronici. Per ulteriori informazioni, vedere [Creazione di report elettronici (ER)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

La messaggistica elettronica è basata sulle seguenti entità:

- **Messaggio elettronico** - Un report o una dichiarazione che deve essere inclusa nel report e/o trasmessa internamente. Un esempio è un report che viene inviato a un ufficio imposte.
- **Elementi del messaggio elettronico** - Record da includere nel messaggio incluso nel report.
- **Elaborazione messaggio elettronico** - Una catena di azioni, associate o meno, che devono essere eseguite per raccogliere i dati richiesti, generare report, archiviare dati nell'archiviazione BLOB di Microsoft Azure, trasmettere report al di fuori del sistema, ottenere risposte esternamente al sistema e aggiornare il database, in base alle informazioni ricevute.

L'illustrazione seguente mostra il flusso di dati per la messaggistica elettronica.

![Flusso di dati della messaggistica elettronica](media/electronic-messaging-data-flow.png)

La funzionalità Messaggi elettronici supporta i seguenti scenari:

- Creare messaggi e generare report manualmente basati su formati ER di esportazione associati di vari tipi: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, testo e Microsoft Word.
- Creare ed elaborare automaticamente messaggi basati sulle informazioni richieste e ottenute da un'autorità tramite un formato ER di importazione associato.
- Raccogliere ed elaborare informazioni da un'origine dati (tabella di Finance and Operations) come elementi del messaggio.
- Archiviare ulteriori informazioni e valutare diversi valori chiamando classi eseguibili definite in modo specifico in relazione a messaggi o elementi del messaggio.
- Aggregare informazioni raccolte in elementi del messaggio, dividere quelle informazioni per messaggio e generare report in formati ER di esportazione associati.
- Trasmettere report generati a un servizio Web utilizzando informazioni di protezione che vengono archiviate in Azure Key Vault.
- Ottenere una risposta da un servizio Web, interpretare la risposta e aggiornare dati in Finance and Operations come appropriato.
- Archiviare ed esaminare tutti i report generati.
- Archiviare ed esaminare tutte le informazioni di registro correlate ad azioni eseguite per un messaggio o un elemento del messaggio.
- Controllare l'elaborazione mediante vari stati del messaggio e stati di elementi del messaggio.

## <a name="set-up-electronic-messaging"></a>Configurazione della messaggistica elettronica

La messaggistica elettronica può consentire la gestione di processi di reporting elettronico differenti per vari tipi di documento. In alcuni scenari complessi, la messaggistica elettronica viene configurata per disporre di una combinazione di molti stati del messaggio, stati di elementi del messaggio, azioni, campi aggiuntivi e classi eseguibili. Per questi scenari, sono disponibili pacchetti di entità di dati per l'importazione. Se si utilizzano questi pacchetti di entità di dati, è necessario importarli in un'entità legale usando lo strumento di gestione dati. Per ulteriori informazioni su come utilizzare lo strumento di gestione dati, vedere [Gestione dei dati](../../dev-itpro/data-entities/data-entities-data-packages.md).

Se non si importa un pacchetto di entità di dati, è possibile configurare manualmente la funzionalità Messaggi elettronici. In tal caso, è necessario configurare i seguenti elementi. 

- [Sequenze numeriche](#number-sequences)
- [Stati e tipi di elementi del messaggio](#message-item-types-and-statuses)
- [Stati del messaggio](#message-statuses)
- [Campi aggiuntivi](#additional-fields)
- [Impostazioni classe eseguibile](#executable-class-settings)
- [Azioni di popolamento record](#populate-records-actions)
- [Impostazioni servizio Web](#web-service-settings)
- [Azioni di elaborazione messaggi](#message-processing-actions)
- [Elaborazione messaggio elettronico](#electronic-message-processing)

Nelle sezioni seguenti vengono fornite altre informazioni su ognuno di tali elementi.

### <a name="number-sequences"></a>Sequenze numeriche

Configurare sequenze numeriche per messaggi ed elementi del messaggio. Le sequenze numeriche sono utilizzate per numerare automaticamente i messaggi e gli elementi del messaggio; i numeri assegnati saranno utilizzati come identificatori univoci per i messaggi e gli elementi del messaggio nel sistema. È possibile configurare sequenze numeriche per la messaggistica elettronica nella pagina **Parametri di contabilità generale** (**Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**).

### <a name="message-item-types-and-statuses"></a>Stati e tipi di elementi del messaggio

I tipi di elementi del messaggio identificano i tipi di record che verranno utilizzati nei messaggi elettronici. È possibile configurare tipi di elementi del messaggio nella pagina **Tipi di elementi del messaggio** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Tipi di articolo del messaggio**).

Gli stati degli elementi del messaggio identificano gli stati che saranno applicati agli elementi del messaggio nell'elaborazione che si sta configurando. È possibile configurare tipi di elementi del messaggio nella pagina **Stati elementi dei messaggi** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Stati elementi dei messaggi**).

### <a name="message-statuses"></a>Stati del messaggio

Configurare gli stati del messaggio che devono essere disponibili nell'elaborazione dei messaggi. È possibile configurare stati del messaggio nella pagina **Stati del messaggio** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Stati del messaggio**).

### <a name="additional-fields"></a>Campi aggiuntivi

La funzionalità Messaggi elettronici consente di popolare record da una tabella transazionale. In questo modo, è possibile preparare i record per il reporting e quindi includerli nei report. A volte, non sono disponibili informazioni sufficienti nella tabella transazionale per includere un record nei report in base ai requisiti di report. È possibile immettere tutte le informazioni che devono essere incluse in un report per un record configurando ulteriori campi. Ulteriori campi possono essere associati a messaggi e elementi del messaggio. È possibile configurare ulteriori campi nella pagina **Campi aggiuntivi** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Campi aggiuntivi**).

Nella seguente tabella sono descritti i campi della pagina **Campi aggiuntivi**.

| Campo                | descrizione |
|----------------------|-------------|
| Nome campo           | Immettere il nome di un ulteriore attributo degli elementi del messaggio correlati al processo. Questo nome viene visualizzato nell'interfaccia utente durante il processo. Può anche essere utilizzato nelle configurazioni ER correlate al processo. |
| descrizione          | Immettere una descrizione dell'attributo aggiuntivo degli elementi del messaggio correlati al processo. |
| Valore campo          | Immettere il valore del campo da utilizzare in relazione a un elemento del messaggio durante il reporting. |
| Descrizione campo    | Immettere una descrizione del valore del campo da utilizzare in relazione a un elemento del messaggio durante il reporting. |
| Tipo di conto         | Alcuni valori dei campi aggiuntivi possono essere limitati a specifici tipi di conto. Selezionare uno dei seguenti valori: **Tutto**, **Cliente** o **Fornitore**. |
| Codice conto         | Se si è selezionato **Cliente** o **Fornitore** nel campo **Tipo di conto**, è possibile limitare ulteriormente l'utilizzo dei valori del campo a uno specifico gruppo o tabella. |
| Numero conto/gruppo | Se si è selezionato **Cliente** o **Fornitore** nel campo **Tipo di conto** e si è immesso un gruppo o una tabella nel campo **Codice conto**, è possibile immettere uno specifico gruppo o agente doganale in questo campo. |
| Valido            | Specificare la data alla quale si deve iniziare a considerare il valore. |
| Scadenza           | Specificare la data alla quale il valore non deve più considerare il valore. |

### <a name="executable-class-settings"></a>Impostazioni classe eseguibile

Una classe eseguibile è un metodo o classe X++ che l'elaborazione del messaggio elettronico può chiamare in relazione a un'azione se una valutazione viene richiesta per il processo.

È possibile configurare manualmente una classe eseguibile nella pagina **Impostazioni classe eseguibile** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Impostazioni classe eseguibile**). Creare una riga e impostare i seguenti campi.

| Campo                 | descrizione |
|-----------------------|-------------|
| Classe eseguibile      | Immettere il nome che verrà utilizzato durante la configurazione di un'azione di elaborazione messaggi in relazione alla quale questa classe viene chiamata. |
| descrizione           | Immettere una descrizione della classe eseguibile. |
| Nome classe eseguibile | Selezionare una classe eseguibile X++. |
| Livello di esecuzione       | Questo campo viene impostato automaticamente, in quanto il valore deve essere predefinito per la classe eseguibile selezionata. Questo campo limita il livello di esecuzione della valutazione correlata. |
| Descrizione classe     | Questo campo viene impostato automaticamente, in quanto il valore deve essere predefinito per la classe eseguibile selezionata. |

### <a name="populate-records-actions"></a>Azioni di popolamento record

Le azioni di popolamento record sono utilizzate per configurare azioni che aggiungono record alla tabella Elementi del messaggio affinché possano essere aggiunti a un messaggio elettronico. Ad esempio, se il messaggio elettronica deve includere fatture cliente, è necessario configurare un'azione **Popola record** che è collegata alla tabella **Giornale di registrazione fatture cliente** (nel campo **Origine dati** ). È possibile configurare azioni di popolamento record nella pagina **Azione di popolamento record** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Azioni di popolamento record**). Creare un nuovo record per ogni azione che deve aggiungere record alla tabella e impostare i campi seguenti.

| Campo       | descrizione                                                               |
|-------------|---------------------------------------------------------------------------|
| Nome        | Immettere un nome per l'azione che popola record nel processo.       |
| descrizione | Immettere una descrizione dell'azione che popola record nel processo. |

Nella scheda Dettaglio **Impostazione origini dati**, aggiungere una riga per ogni origine dati utilizzata per il processo e impostare i seguenti campi.

| Campo                  | descrizione |
|------------------------|-------------|
| Nome                   | Immettere un nome per l'origine dati. |
| Tipo di elemento del messaggio      | Selezionare il tipo di elemento del messaggio da utilizzare durante la creazione dei record per l'origine dati. |
| Tipo di conto           | Selezionare il tipo di conto da associare ai record dell'origine dati. |
| Nome tabella master      | In Finance and Operations selezionare la tabella che deve essere un'origine dati. |
| Campo Numero documento  | Selezionare il campo da cui deve essere ottenuto il numero di documento nella tabella selezionata. |
| Campo Data documento    | Selezionare il campo da cui deve essere ottenuta la data del documento nella tabella selezionata. |
| Campo Conto documento | Selezionare il campo da cui deve essere ottenuto il conto del documento nella tabella selezionata. |
| Query utente             | Se questa casella di controllo è selezionata, è possibile impostare una query selezionando **Modifica query** sopra la griglia. In caso contrario, tutti i record saranno popolati a partire dall'origine dati. |

### <a name="web-service-settings"></a>Impostazioni servizio Web

Le impostazioni del servizio Web consentono di configurare la trasmissione di dati diretta a un servizio Web. È possibile configurare le impostazioni del servizio Web nella pagina **Impostazioni servizio Web** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Impostazioni servizio Web**).

Nella seguente tabella sono descritti i campi della pagina **Impostazioni servizio Web**.

| Campo                   | descrizione |
|-------------------------|-------------|
| Servizio Web             | Immettere un nome per il servizio Web. |
| descrizione             | Immettere una descrizione del servizio Web. |
| Indirizzo Internet        | Immettere l'indirizzo Internet del servizio Web. |
| Certificato             | Selezionare un certificato Key Vault configurato in precedenza. |
| Tipo di risposta – XML | Impostare questa opzione su **Sì** se il tipo di risposta è XML. |
| Metodo di richiesta          | Specificare il metodo della richiesta. HTTP definisce un set di metodi di richiesta che indicano l'azione che dovrà essere eseguita per una risorsa data. Il metodo può essere **GET**, **POST** o un altro metodo HTTP. |
| Intestazioni richieste         | Specificare le intestazioni di richieste. Un'intestazione di richiesta è un'intestazione HTTP utilizzabile in una richiesta HTTP e non correlata al contenuto del messaggio. |
| Accetta codifica         | Specificare Accept-Encoding. L'intestazione HTTP della richiesta Accept-Encoding annuncia la codifica del contenuto che il client può comprendere. Questa codifica del contenuto è in genere un algoritmo di compressione. |
| Tipo di contenuto            | Specificare il tipo di contenuto. L'intestazione dell'entità Content-Type indica il tipo di media della risorsa. |

### <a name="message-processing-actions"></a>Azioni di elaborazione messaggi

Le azioni di elaborazione messaggi consentono di creare azioni per i processi e configurare i relativi parametri. È possibile configurare azioni di elaborazione messaggi nella pagina **Azioni di elaborazione messaggi** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Azioni di elaborazione messaggi**).

Nelle tabelle seguenti vengono descritti i campi della pagina **Azioni di elaborazione messaggi**.

#### <a name="general-fasttab"></a>Scheda dettaglio Generale

| Campo                   | descrizione |
|-------------------------|-------------|
| Tipo di azione             | Selezionare il tipo di azione. Per informazioni sulle opzioni disponibili, vedere la sezione [Tipi di azioni di elaborazione messaggi](#message-processing-action-types). |
| Mapping formato          | Selezionare il formato ER che deve essere chiamato per l'azione. Questo campo è disponibile solo per le azioni **Esportazione creazione di report elettronici**, **Importazione creazione di report elettronici** e **Messaggio esportazione creazione di report elettronici**. |
| Tipo di elemento del messaggio       | Selezionare il tipo di record per il quale l'azione deve essere valutata. Questo campo è disponibile per le azioni **Livello di esecuzione dell'elemento del messaggio**, **Esportazione creazione di report elettronici** e **Importazione creazione di report elettronici** nonché alcuni altri tipi di azioni Se si lascia vuoto questo campo, vengono valutati tutti i tipi di elementi del messaggio definiti per l'elaborazione del messaggio. |
| Classe eseguibile        | Selezionare le impostazioni della classe eseguibile create in precedenza. Questo campo è disponibile solo per le azioni **Livello di esecuzione dell'elemento del messaggio** e **Livello di esecuzione dell'elemento del messaggio**. |
| Azione di popolamento record | Selezionare un'azione di popolamento di record configurata in precedenza. Questo campo è disponibile solo per le azioni **Popola record**. |

##### <a name="message-processing-action-types"></a>Tipi di azioni di elaborazione messaggi

Nel campo **Tipo di azione** sono disponibili le seguenti opzioni:

- **Popola record** - Un'azione **Popola record** deve essere configurata in precedenza. Associarla a un'azione **Popola record** affinché sia inclusa nell'elaborazione. Si presuppone che questo tipo di azione sia utilizzato per la prima azione nell'elaborazione del messaggio. Di conseguenza, solo uno stato di risultato può essere configurato per un'azione di questo tipo. Uno stato iniziale non può essere impostato.
- **Crea messaggio** - Utilizzare questo tipo per consentire agli utenti di creare manualmente messaggi nella pagina **Messaggio elettronico**. Uno stato iniziale non può essere configurato per un'azione di questo tipo.
- **Livello di esecuzione del messaggio** - Utilizzare questo tipo per configurare una classe eseguibile che deve essere valutata a livello del messaggio.
- **Livello di esecuzione dell'elemento del messaggio** - Utilizzare questo tipo per configurare una classe eseguibile che deve essere valutata a livello dell'elemento del messaggio.
- **Esportazione creazione di report elettronici** - Utilizzare questo tipo per le azioni che devono generare un report basato su una configurazione ER di esportazione a livello dell'elemento del messaggio.
- **Messaggio esportazione creazione di report elettronici** - Utilizzare questo tipo per le azioni che devono generare un report basato su una configurazione ER di esportazione a livello del messaggio (ad esempio, quando un messaggio non ha elementi).
- **Importazione creazione di report elettronici** - Utilizzare questo tipo per le azioni che devono generare un report basato su una configurazione ER di importazione a livello dell'elemento del messaggio.
- **Elaborazione utente livello del messaggio** - Utilizzare questo tipo per le azioni che presuppongono azioni manuali da parte dell'utente. Ad esempio, l'utente potrebbe aggiornare lo stato dei messaggi.
- **Elaborazione utente** - Utilizzare questo tipo per le azioni che presuppongono azioni manuali da parte dell'utente. Ad esempio, l'utente potrebbe aggiornare lo stato degli elementi del messaggio.
- **Servizio Web** - Utilizzare questo tipo per le azioni che devono trasmettere un report generato a un servizio Web. Questo tipo di azione non viene utilizzato per il reporting relativo alla comunicazione di fatture di vendita e di acquisto per l'Italia.
- **Verifica richiesta** - Utilizzare questo tipo per la verifica della richiesta da un server.

#### <a name="initial-statuses-fasttab"></a>Scheda Dettaglio Stati iniziali

> [!NOTE]
> La scheda Dettaglio **Stati iniziali** non è disponibile per le azioni con un tipo iniziale **Popola record** o **Crea messaggio**.

| Campo               | descrizione                                                                                         |
|---------------------|-----------------------------------------------------------------------------------------------------|
| Stato elemento del messaggio | Selezionare lo stato dell'elemento del messaggio per il quale l'azione di elaborazione messaggi selezionata deve essere valutata. |
| descrizione         | Una descrizione dello stato dell'articolo del messaggio selezionato.                                                  |

#### <a name="result-statuses-fasttab"></a>Scheda Dettaglio Stati di risultati

| Campo               | descrizione |
|---------------------|-------------|
| Stato messaggio      | Selezionare gli stati del messaggio per il quale l'azione di elaborazione messaggi selezionata deve essere valutata. Questo campo è disponibile solo per le azioni di elaborazione messaggi che vengono valutate a livello del messaggio. Ad esempio, è disponibile per le azioni **Esportazione creazione di report elettronici** e **Importazione creazione di report elettronici**. Non è disponibile per le azioni **Elaborazione utente** e **Livello di esecuzione dell'elemento del messaggio**. |
| descrizione         | Una descrizione dello stato del messaggio selezionato. |
| Tipo di risposta       | Il tipo di risposta dello stato del messaggio dello stato. |
| Stato elemento del messaggio | Selezionare gli stati risultanti che devono essere disponibili dopo la valutazione dell'azione di elaborazione messaggi selezionata. Questo campo è disponibile solo per le azioni di elaborazione messaggi che vengono valutate a livello dell'elemento del messaggio. Ad esempio, è disponibile per le azioni **Elaborazione utente** e **Livello di esecuzione dell'elemento del messaggio**. Per le azioni di elaborazione messaggi che vengono valutate a livello del messaggio, questo campo mostra lo stato dell'elemento del messaggio configurato per lo stato del messaggio selezionato. |

### <a name="electronic-message-processing"></a>Elaborazione messaggio elettronico

L'elaborazione del messaggio elettronico è un concetto di base della funzionalità Messaggi elettronici. Aggrega le azioni che devono essere valutate per il messaggio elettronico. Le azioni possono essere collegate tramite uno stato iniziale e uno stato di risultato. In alternativa, le azioni **Elaborazione utente** possono essere avviate indipendentemente. Nella pagina **Elaborazione messaggio elettronico** (**Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Elaborazione messaggio elettronico**), è anche possibile selezionare campi aggiuntivi che devono essere supportati per l'elaborazione.

La scheda Dettaglio **Azione** consente di aggiungere azioni predefinite all'elaborazione. È possibile specificare se un'azione deve essere eseguita separatamente o se può essere avviata dall'elaborazione. Le azioni utente devono essere eseguite separatamente.

La scheda Dettaglio **Campi aggiuntivi dell'elemento del messaggio** consente di aggiungere ulteriori campi predefiniti correlati agli elementi del messaggio. È necessario aggiungere ulteriori campi per ogni tipo di elemento del messaggio a cui i campi sono correlati.

La scheda Dettaglio **Campi aggiuntivi del messaggio** consente di aggiungere ulteriori campi predefiniti correlati ai messaggi.

La scheda dettaglio **Ruoli di sicurezza** consente di configurare i ruoli di sicurezza che sono predefiniti nel sistema per una specifica elaborazione. Gli utenti con un ruolo specifico avranno accesso solo all'elaborazione definita per tale ruolo.

La scheda Dettaglio **Batch** consente di configurare l'elaborazione per l'utilizzo in un regime batch.

## <a name="work-with-electronic-messages-functionality"></a>Utilizzo della funzionalità Messaggi elettronici

Se si lavora a livello del messaggio, la pagina **Messaggi elettronici** (**Imposta** \> **Richieste di informazioni e report** \> **Messaggi elettronici** \> **Messaggi elettronici**) è più utile. Se si lavora a livello della raccolta di dati (elemento del messaggio), la pagina **Elementi del messaggio elettronico** (**Imposta** \> **Richieste di informazioni e report** \> **Messaggi elettronici** \> **Elementi del messaggio elettronico**) è più utile.

### <a name="electronic-messages"></a>Messaggi elettronici

La pagina **Messaggi elettronici** presenta l'elaborazione disponibile, in base al ruolo. I ruoli di sicurezza sono associati all'elaborazione nella configurazione dell'elaborazione. Per ogni elaborazione disponibile, la pagina mostra i messaggi elettronici e le informazioni ad essi correlate.

La scheda Dettaglio **Messaggi** visualizza i messaggi elettronici per l'elaborazione selezionata. A seconda dello stato del messaggio selezionato e dell'elaborazione predefinita, è possibile eseguire alcune azioni selezionando i pulsanti sopra la griglia:

- **Nuovo** - Questo pulsante è associato alle azioni **Crea messaggio**.
- **Elimina** - Questo pulsante è disponibile se la casella di controllo **Consente eliminazione** è selezionata per lo stato corrente del messaggio selezionato.
- **Genera report** - Questo pulsante è associato alle azioni **Messaggio esportazione creazione di report elettronici**.
- **Invia report** - Questo pulsante è associato alle azioni **Servizio Web**.
- **Aggiorna stato** - Questo pulsante è associato alle azioni **Elaborazione utente livello del messaggio**.
- **Elementi del messaggio** - Apre la pagina **Elementi del messaggio elettronico**.

La scheda Dettaglio **Registro azioni** visualizza le informazioni su tutte le azioni eseguite per il messaggio selezionato.

La scheda Dettaglio **Campi aggiuntivi del messaggio** visualizza tutti i campi aggiuntivi definiti per i messaggi nella configurazione dell'elaborazione. Visualizza inoltre i valori di quei campi aggiuntivi.

La scheda Dettaglio **Elementi del messaggio** visualizza tutti gli elementi del messaggio correlati al messaggio selezionato.

È possibile esaminare tutti gli allegati per il messaggio selezionato. Questi allegati sono report che sono già stati generati e ricevuti. Selezionare il messaggio di cui esaminare gli allegati, quindi selezionare il pulsante **Allegato** nel riquadro azioni.

![Pulsante Allegato](media/attachment-icon.png)

La pagina **Allegati** visualizza tutti gli allegati correlati al messaggio. Per visualizzare un file, selezionarlo nell'elenco a sinistra, quindi selezionare **Apri** nel riquadro azioni.

![Pulsante Apri](media/open-button.png)

Per esaminare un allegato correlato a un'azione specifica che sia già stata eseguita per un messaggio, selezionare il messaggio nella pagina **Messaggi elettronici**, quindi, nella scheda Dettaglio **Registro azioni**, selezionare l'azione. Quindi selezionare il pulsante **Allegato** nel riquadro azioni.

È inoltre possibile eseguire l'intera elaborazione o solo una specifica azione selezionando **Esegui elaborazione** nel riquadro azioni.

### <a name="electronic-message-items"></a>Elementi del messaggio elettronico

La pagina **Elementi del messaggio elettronico** presenta tutti gli elementi del messaggio e un registro delle azioni che sono state eseguite per ogni elemento del messaggio. Visualizza inoltre i campi aggiuntivi definiti per gli elementi del messaggio nonché i valori di questi campi aggiuntivi.

Nella tabella seguente sono descritti i campi della scheda **Elementi del messaggio**.

<table>
<thead>
<tr>
<th>Campo</th>
<th>descrizione</th>
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
<td>Il numero di conto di un cliente o di un fornitore (o un altro valore del campo, a seconda del campo specificato nell'azione <strong>Popola record</strong>. Questo campo può essere compilato automaticamente solo quando una fattura viene aggiunta alla tabella Elementi del messaggio.</td>
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

Selezionare **Esegui elaborazione** nel riquadro azioni per eseguire l'elaborazione per gli elementi del messaggio. Per eseguire un'azione specifica, nella finestra di dialogo **Esegui elaborazione**, impostare l'opzione **Seleziona azione** su **Sì**, quindi selezionare un'azione. Per eseguire l'intera elaborazione, lasciare l'opzione **Seleziona azione** su **No**.

#### <a name="generate-report"></a>Genera report

Selezionare **Genera report** nel riquadro azioni per generare un report. Questo pulsante è associato alle azioni **Esportazione creazione di report elettronici**.

#### <a name="update-status"></a>Aggiorna stato

Selezionare **Aggiorna stato** nel riquadro azioni per aggiornare lo stato di uno o più degli elementi del messaggio. Nella finestra di dialogo **Aggiorna stato**, utilizzare la scheda dettaglio **Record da includere** per selezionare gli elementi del messaggio per l'aggiornamento. Assicurarsi di definire correttamente i criteri di selezione, poiché gli stati dell'elemento del messaggio verranno aggiornati in base a questi criteri, lo stato iniziale dell'azione selezionata e il valore **Nuovo stato** impostato. Dopo il completamento di un aggiornamento dello stato, risulterà difficile determinare quali elementi sono stati aggiornati. Di conseguenza, sarà difficile eseguire il rollback degli aggiornamenti dello stato.

#### <a name="electronic-messages"></a>Messaggi elettronici

Selezionare **Messaggio elettronico** nel riquadro azioni per esaminare un messaggio elettronico correlato all'articolo del messaggio selezionato.

È anche possibile esaminare tutti i file corrispondenti a un elemento del messaggio. Selezionare il campo **Messaggio** dell'articolo del messaggio o **Messaggio elettronico** nel riquadro azioni. Nella pagina **Messaggio elettronico**, selezionare il messaggio per il quale esaminare un report, quindi selezionare il pulsante **Allegato** nel riquadro azioni.

![Pulsante Allegato](media/attachment-icon.png)

La pagina **Allegati** visualizza tutti gli allegati correlati al messaggio. Per visualizzare un file, selezionarlo nell'elenco a sinistra, quindi selezionare **Apri** nel riquadro azioni.

![Pulsante Apri](media/open-button.png)

#### <a name="original-document"></a>Documento originale

Selezionare **Documento originale** nel riquadro azioni per aprire il documento originale per l'elemento del messaggio selezionato.

## <a name="example"></a>Esempio

Dopo aver creato il formato ER, averlo mappato alle origini dati e completato, è possibile eseguirlo utilizzando l'area di lavoro **Crazione di report elettronici**. Viene generato un report che può essere salvato localmente.

Per controllare i seguenti aspetti del processo di reporting, è necessario configurare l'elaborazione della messaggistica elettronica:

- Registrare informazioni sull'utente che ha generato il report.
- Registrare la data in cui il report è stato generato.
- Salva i report generati per i periodi precedenti.

In questa sezione è riportato un esempio che mostra come è possibile configurare la funzionalità Messaggi elettronici per creare un processo di reporting.

### <a name="set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Configurare ed eseguire l'elaborazione per chiamare un formato di esportazione ER semplice con cui generare un report di Excel

In questa sezione è riportato un esempio che mostra come è possibile impostare la messaggistica elettronica per generare un report basato su un formato ER di esportazione per Excel. Per utilizzare questo esempio, il formato di esportazione ER di Excel deve essere già stato creato, mappato alle origini dati e completato. Una sequenza numerica deve essere già stata configurata per i messaggi elettronici.

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
    - Nella scheda Dettaglio **Stati di risultati**, nel campo **Stato messaggio**, selezionare **Preparato** o (e) **Nuovo**. Nel campo **Tipo di risposta**, immettere **Esecuzione completata**.

#### <a name="electronic-message-processing"></a>Elaborazione messaggio elettronico

In questo esempio, tutte le azioni devono essere configurate di modo che possano essere eseguite separatamente. Si presuppone che ogni azione sarà inizializzata dall'utente.

1. Accedere a **Imposta \> Impostazione \> Messaggi elettronici \> Elaborazione messaggio elettronico**.
2. Aggiungere un record per l'elaborazione, tutte le azioni definite in precedenza e un campo aggiuntivo.
3. Facoltativo: nella scheda Dettaglio **Ruoli di sicurezza**, definire i ruoli di sicurezza per l'elaborazione per limitare l'accesso a specifico reporting.
4. Accedere a **Imposta \> Richieste di informazioni e report \> Messaggi elettronici \> Messaggi elettronici**.
5. Selezionare **Nuovo** per creare un messaggio. A questo punto, è possibile aggiungere date e una descrizione. È anche possibile aggiornare il valore del campo aggiuntivo come necessario.

    ![Creare un messaggio elettronico](media/create-electronic-message.png)

La griglia nella scheda Dettaglio **Registro azioni** viene automaticamente riempita con un registro di tutte le azioni eseguite sul messaggio.

È ora possibile eliminare o aggiornare lo stato del messaggio. Per aggiornare lo stato del messaggio, selezionare **Aggiorna stato**, quindi nel campo **Nuovo stato**, selezionare **Preparato**. Selezionare **OK**.

![Aggiornare lo stato del messaggio](media/update-status.png)

Lo stato del messaggio viene aggiornato a **Preparato** ed è possibile generare il report selezionando **Genera report**. Il report viene generato e lo stato del messaggio e il registro delle azioni del vengono aggiornati. Per visualizzare il report generato, selezionare il pulsante **Allegato** nel riquadro azioni.

