---
title: Destinazione report elettronici
description: "È possibile configurare una destinazione per ciascuna configurazione di formato per la creazione di report elettronici (ER) e del relativo componente di output (una cartella o un file). Gli utenti che dispongono di diritti di accesso appropriati anche possono modificare le impostazioni di destinazione in fase di esecuzione. Questo articolo illustra la gestione delle destinazioni ER, i tipi di destinazioni supportati e considerazioni sulla sicurezza."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: d38d05fe445bf0326d408038dff84ccf8c0ff64c
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-destinations"></a>Destinazione report elettronici

È possibile configurare una destinazione per ciascuna configurazione di formato per la creazione di report elettronici (ER) e del relativo componente di output (una cartella o un file). Gli utenti che dispongono di diritti di accesso appropriati anche possono modificare le impostazioni di destinazione in fase di esecuzione. Questo articolo illustra la gestione delle destinazioni ER, i tipi di destinazioni supportati e considerazioni sulla sicurezza.

Le configurazioni del formato di creazione di report elettronici (ER) in genere contengono almeno un componente di output: un file. In genere, le configurazioni contengono più componenti di output di file di tipo diverso (ad esempio, XML, TXT o XLSX) che vengono raggruppati in una cartella singola o più cartelle. La gestione di destinazione ER consente di preconfigurare quello che si verifica durante l'esecuzione di ogni componente. Per impostazione predefinita, quando una configurazione, viene eseguita una finestra di dialogo in modo che l'utente aprire o salvare il file. Lo stesso comportamento viene utilizzato anche quando si importa una configurazione ER e non si configura nessuna destinazione specifica. Dopo aver creata una destinazione per un componente di output principale, tale destinazione ha la precedenza sul comportamento predefinito e la cartella o il file viene inviato in base alle impostazioni della destinazione.

## <a name="availability-and-general-prerequisites"></a>Disponibilità e prerequisiti generali
La funzionalità delle destinazioni di ER non è disponibile in Microsoft Dynamics 365 per la versione delle operazioni 7.0 (febbraio 2016). Di conseguenza, è necessario impostare Microsoft Dynamics 365 per le operazioni novembre 2016 (versione) da utilizzare tutte le funzioni descritte in questo argomento. In alternativa, è possibile impostare uno dei seguenti prerequisiti. Tuttavia, tenere presente che questo un sistema alternativo immette una esperienza più limitata di destinazione di ER.

-   Microsoft Dynamics 365 per la versione 7.0.1 dell'applicazione di operazioni (maggio 2016)
-   [Aggiornamento rapido dell'applicazione](https://fix.lcs.dynamics.com/issue/results/?q=3160213) per la gestione delle destinazioni ER

È possibile impostare le destinazioni solo per le configurazioni ER che sono state importate e per i formati disponibili nella pagina **Configurazioni creazione di report elettronici**.

## <a name="overview"></a>Panoramica
La funzionalità di gestione della destinazione di ER è disponibile ** Amministrazione organizzazione ** &gt; ** alla dichiarazione ** elettronica. In questo caso, è possibile ignorare il comportamento predefinito per una configurazione. Le configurazioni importate non vengono mostrate qui fino a quando non si fa clic su **Nuovo** e, quindi, nel campo **Riferimento** si seleziona una configurazione per cui creare le impostazioni di destinazione.

[![che selezionare una configurazione nel campo Riferimento (]. /media/ger-destinations-2-1611-1024x574.jpg)](. /media/ger-destinations-2-1611.jpg) 

Dopo aver creato un riferimento, è possibile creare una destinazione del file per ciascuna cartella, un file. 

[![per la creazione di una destinazione del file (]. /media/ger-destinations-1611-1024x586.jpg)](. /media/ger-destinations-1611.jpg)

**Note:** È possibile creare una destinazione del file per ciascun componente di output dello stesso formato, ad esempio una cartella o un file selezionato nel campo **Nome campo**. È quindi possibile abilitare o disabilitare singole destinazioni per la destinazione del file ** impostazioni di destinazione ** nella finestra di dialogo. Il pulsante **Impostazioni** consente di controllare tutte le destinazioni per una destinazione di file selezionata. Nella finestra di dialogo **Impostazioni destinazione** è possibile controllare separatamente ogni destinazione impostando la relativa opzione **Abilitato**.

[finestra di dialogo Impostazioni di destinazione![(]. /media/ger-destinations-settings-1611-1024x589.jpg)](. /media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Tipi di destinazione
Sono supportati vari tipi di destinazioni. È possibile disabilitare o abilitare tutti i tipi contemporaneamente. In questo modo, è possibile non eseguire alcuna operazione o inviare il componenente a tutte le destinazioni configurate. Le sezioni seguenti descrivono le destinazioni che sono supportate.

### <a name="email-destination"></a>Destinazione posta elettronica

Impostare **Abilitato **su **Sì** per inviare un file di output tramite posta elettronica. Una volta eseguita questa opzione è attivata, è possibile specificare i destinatari di posta elettronica e modificare l'oggetto e il corpo del messaggio di posta elettronica. È possibile impostare testi costanti per l'oggetto e il corpo del messaggio di posta elettronica, è possibile utilizzare le formule di ER per creare in modo dinamico i testi di posta elettronica. È possibile configurare gli indirizzi di posta elettronica per il ER in due modi. Configurazione può essere completata in modo analogo alla funzionalità di gestione stampa in Dynamics 365 per le operazioni il completamento. In alternativa, è possibile risolvere un indirizzo di posta elettronica utilizzando un riferimento nella configurazione di ER a una formula.

### <a name="email-address-types"></a>Tipi di indirizzo di posta elettronica

Quando si fa clic su ** modifica ** per ** ** o ** cc ** sistemi, ** posta elettronica ** la finestra di dialogo. È quindi possibile selezionare il tipo di indirizzo di posta elettronica da utilizzare.

[posta elettronica![alla finestra di dialogo (]. /media/ger-destinations-email-1-1611-1024x588.jpg)](. /media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gestione stampa

Se si seleziona ** stampare il messaggio di posta elettronica di gestione ** tipo, è possibile immettere gli indirizzi di posta elettronica fissi in ** ** campo. Per utilizzare gli indirizzi di posta elettronica che non sono fissi, è necessario selezionare il tipo di fonte di posta elettronica per una destinazione del file. I valori seguenti sono supportati: ** Cliente **, ** ** fornitore, prospect ** **, ** ** contatto, ** concorrente **, ** ** lavoratore, ** ** candidato, ** fornitore potenziale ** e ** fornitore non autorizzato **. Dopo avere selezionato un tipo di fonte di posta elettronica, utilizzare il pulsante ** accanto al conto di origine di posta elettronica ** il campo per aprire ** Designer formula ** il modulo. È possibile utilizzare questo modulo per collegare una formula che rappresenta il conto parte selezionato alla destinazione di posta elettronica.

[![configurare il tipo di messaggio di posta elettronica di Gestione stampa (]. /media/ger-destinations-email-2-1611-1024x588.jpg)](. /media/ger-destinations-email-2-1611.jpg) 

Si noti che le formule sono specifiche per la configurazione ER. Nel campo **Formula** immettere un riferimento specifico per il documento a un tipo di parte del cliente o del fornitore. Anziché digitare, è possibile cercare il nodo di origine dati che rappresenti il conto cliente o fornitore e fare clic sul pulsante **Aggiungi origine dati** per aggiornare la formula. Ad esempio, se si utilizza la configurazione bonifico ISO 20022, il nodo che rappresenta un conto fornitore è **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. In caso contrario, immettere qualsiasi valore di stringa, ad esempio **DE-001**, per salvare una formula.

[![Formula designer](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

** Inviare ** nella finestra di dialogo, fare clic sul contenitore di riciclaggio accanto ** conto di origine di posta elettronica ** il campo per eliminare definitivamente la formula per il conto di origine di posta elettronica. In alternativa, aprire il Designer formula per modificare una formula precedentemente salvata. Per assegnare gli indirizzi di posta elettronica, fare clic su ** modifica ** per aprire ** assegnare gli indirizzi di posta elettronica ** la finestra di dialogo.

[![per assegnare gli indirizzi di posta elettronica per una destinazione di posta elettronica (]. /media/ger-destinations-email-3-1611-1024x587.jpg)](. /media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Posta elettronica configurazione

Usano questo tipo di messaggio di posta elettronica se la configurazione da utilizzare è un nodo nelle origini dati che rappresenta un indirizzo di posta elettronica. È possibile utilizzare le origini dati e funzioni in Designer formula per ottenere un indirizzo di posta elettronica formattato correttamente.

[![in base a un'origine dati Indirizzo di posta elettronica per una destinazione di posta elettronica (]. /media/ger-destinations-email-4-1611-1024x587.jpg)](. /media/ger-destinations-email-4-1611.jpg) 

**Nota:** un server SMTP (Simple Mail Transfer Protocol) deve essere configurato e disponibile. È possibile specificare il server SMTP in Dynamics 365 per le operazioni, ** Amministrazione sistema ** &gt; ** all'impostazione ** &gt; ** posta elettronica ** &gt; ** parametri di posta elettronica **.

### <a name="archive-destination"></a>Destinazione archivio

È possibile utilizzare questa opzione per inviare l'output a una cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure. Impostare **Abilitato** su **Sì **per inviare l'output a una destinazione definita dal tipo di documento selezionato. Solo tipi di documento in cui il gruppo è impostato su **File** sono disponibili per la selezione. Definire i tipi di documento ** Amministrazione organizzazione ** &gt; ** alla gestione documenti ** &gt; ** tipi di documento **. La configurazione per le destinazioni ER è lo stessa della configurazione del sistema di gestione documenti.

[![Document types page](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

Il percorso posizione determina dove viene salvato il file. Dopo ** archivio ** la destinazione è attivata, i risultati di configurazione può essere salvato nell'archivio di processo. È possibile visualizzare i risultati ** Amministrazione organizzazione ** &gt; ** alla dichiarazione elettronica ** &gt; ** processi o reporting ** elettronica. ** Nota: ** È possibile selezionare un tipo di documento per l'archivio di processo in Dynamics 365 per le operazioni, ** Amministrazione organizzazione ** &gt; ** ad aree di lavoro ** &gt; ** reporting elettronica ** &gt; ** parametri di reporting **.

#### <a name="sharepoint"></a>SharePoint

È possibile salvare un file in una cartella designata di SharePoint. Definire il server di SharePoint predefinito ** Amministrazione organizzazione ** &gt; ** alla gestione documenti ** &gt; ** parametri di gestione documenti **, ** SharePoint ** nella scheda. Dopo che la cartella di SharePoint è configurata, è possibile selezionarlo come la cartella in cui il risultato di ER verrà salvato per il tipo di documento. 

[![per selezionare una cartella di SharePoint (]. /media/ger_sharepointfolderselection-1024x543.jpg)](. /media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Archiviazione di Azure

Quando il percorso del tipo di documento è impostato su **Directory archivio**, è possibile salvare un file nell'Archiviazione di Azure.

### <a name="file-destination"></a>Destinazione file

Se impostaste ** abilitato ** ** Sì **, un aperte o la finestra di dialogo Salva viene visualizzato quando la configurazione il termine dell'esecuzione.

### <a name="screen-destination"></a>Destinazione della schermata

Se impostaste ** abilitato ** ** Sì **, una previsione di output viene creata. È possibile visualizzare alcuni tipi di file, ad esempio il codice XML, il TXT, o il PDF, direttamente in una finestra del browser. Per altri tipi di file, ad esempio Microsoft Excel o Word, il servizio Microsoft Office Online utilizzato.

### <a name="power-bi-destination"></a>La destinazione Power BI

Insieme ** abilitato ** ** Sì ** da utilizzare nella configurazione di ER per liquidare il trasferimento di dati dall'istanza di Microsoft Dynamics 365 per le operazioni nei servizi di potenza di Microsoft BI. I file trasferire sono archiviati in un'istanza del server di Microsoft SharePoint che deve essere configurata per questo scopo. Per ulteriori informazioni, vedere [utilizzare una configurazione elettronica di reporting per immettere potenza dati BI da Dynamics 365 per le operazioni general-electronic-reporting-report-configuration-get-data-powerbi.md] (). **Suggerimento:** per ignorare il comportamento predefinito (ovvero, la finestra di dialogo per una configurazione), è possibile creare un riferimento di destinazione e una destinazione di file per il componente di output principale e quindi disattivare tutte le destinazioni.

## <a name="security-considerations"></a>Considerazioni sulla sicurezza
Vengono utilizzati due tipi di compiti e privilegi per le destinazioni ER. Il tipo determina la possibilità di gestire le destinazioni globali configurate per una persona giuridica (ovvero controllano l'accesso ** destinazioni dichiarazioni elettroniche ** nella pagina). L'altro tipo controlla la possibilità dell'utente di un'applicazione di ignorare, in fase di esecuzione, le impostazioni di destinazione configurate da uno sviluppatore ER o consulente funzionale ER.

| Ruolo (nome AOT)                     | Nome ruolo                                  | Compito (nome AOT)                     | Nome compito                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Sviluppatore per la creazione di report elettronici             | ERFormatDestinationConfigure        | Configura destinazione formato di report elettronici                |
| ERFunctionalConsultant              | Consulente funzionale per la creazione di report elettronici | ERFormatDestinationConfigure        | Configura destinazione formato di report elettronici                |
| PaymAccountsPayablePaymentsClerk    | Addetto pagamenti contabilità fornitori            | ERFormatDestinationRuntimeConfigure | Configura destinazione formato di report elettronici in fase di esecuzione |
| PaymAccountsReceivablePaymentsClerk | Addetto pagamenti contabilità clienti         | ERFormatDestinationRuntimeConfigure | Configura destinazione formato di report elettronici in fase di esecuzione |

**Nota:** vengono utilizzati due privilegi nei compiti precedenti. Questi privilegi hanno gli stessi nomi dei compiti corrispondenti: **ERFormatDestinationConfigure** e **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Ho importato configurazioni elettroniche e le vedo nella pagina Configurazioni creazione di report elettronici. Se tuttavia in quanto non le vedo nella pagina elettronica le destinazioni di report?

Assicurarsi che si fa clic su ** nuovo ** quindi selezionare una configurazione ** riferimento ** nel campo. Nella pagina **Destinazione report elettronici**, è possibile visualizzare solo le configurazioni per cui sono state configurate le destinazioni.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Consente di definire il modo in cui azzurrata archiviazione di chiazza di conto e di azzurro di archiviazione viene utilizzata?

N. In azzurrata di archiviazione di chiazza standard definita utilizzata per il sistema di gestione documenti vengono utilizzate.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Cosa si lo scopo di destinazione del file nelle impostazioni di destinazione? Cosa fa questa impostazione?

La destinazione **File** viene utilizzata per controllare una finestra di dialogo. Se si attiva la destinazione, ovvero se non è definita destinazione per una configurazione, verrà visualizzata una finestra di dialogo Salva aperta o dopo un file di output viene creato.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>È possibile ottenere un esempio della formula che fa riferimento a un conto fornitore a cui inviare messaggi di posta elettronica?

La formula è specifica per la configurazione ER. Ad esempio, se si utilizza la configurazione bonifico ISO 20022, è possibile utilizzare **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** o **model.Payments.Creditor.Identification.SourceID** per ottenere un conto fornitore associato.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Una delle configurazioni formato contiene più file raggruppati in un'unica cartella (ad esempio, Folder1 contiene File1 e File2 e File3). Come impostare le destinazioni in modo che Folder1.zip non viene creata, File1 viene inviato tramite posta elettronica, File2 viene inviato a SharePoint e sia possibile aprire File3 immediatamente dopo aver eseguito la configurazione?

Tale presupposto che è il formato deve essere disponibile nelle configurazioni di ER. Se si dispone del formato, aprire la pagina **Destinazione report elettronici** e creare un nuovo riferimento a questa configurazione. È quindi necessario avere quattro destinazioni file, una per ogni componente di output. Creare la prima destinazione file, assegnare un nome quale **Folder**e selezionare un nome di file che rappresenta una cartella nella configurazione. Quindi fare clic su **Impostazioni**e assicurarsi che tutte le destinazioni siano disabilitate. Per questa destinazione del file, non verrà creata la cartella. Per impostazione predefinita, a causa delle dipendenze gerarchiche tra i file e cartelle padre, i file si comporteranno nello stesso modo. In altre parole, non saranno inviati da nessuna parte. Per ignorare il comportamento predefinito, è necessario creare tre ulteriori destinazioni file, una per ogni file. Nelle impostazioni di destinazione per ciascuno, è necessario abilitare la destinazione a cui il file deve essere inviato.

# <a name="see-also"></a>Vedere anche

[Panoramica sui report elettronici](general-electronic-reporting.md)


