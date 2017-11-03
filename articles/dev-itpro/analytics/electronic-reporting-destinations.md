---
title: Destinazione report elettronici
description: "È possibile configurare una destinazione per ciascuna configurazione di formato per la creazione di report elettronici (ER) e del relativo componente di output (una cartella o un file). Gli utenti che dispongono di diritti di accesso appropriati anche possono modificare le impostazioni di destinazione in fase di esecuzione. Questo articolo illustra la gestione delle destinazioni ER, i tipi di destinazioni supportati e considerazioni sulla sicurezza."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dedabf13044be30a67a945ff4ca2ecfb1eea8150
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="electronic-reporting-destinations"></a>Destinazione report elettronici

[!include[banner](../includes/banner.md)]


È possibile configurare una destinazione per ciascuna configurazione di formato per la creazione di report elettronici (ER) e del relativo componente di output (una cartella o un file). Gli utenti che dispongono di diritti di accesso appropriati anche possono modificare le impostazioni di destinazione in fase di esecuzione. Questo articolo illustra la gestione delle destinazioni ER, i tipi di destinazioni supportati e considerazioni sulla sicurezza.

Le configurazioni del formato di creazione di report elettronici (ER) in genere contengono almeno un componente di output: un file. In genere, le configurazioni contengono più componenti di output di file di tipo diverso (ad esempio, XML, TXT o XLSX) che vengono raggruppati in una cartella singola o più cartelle. La gestione di destinazione ER consente di preconfigurare quello che si verifica durante l'esecuzione di ogni componente. Per impostazione predefinita, quando si esegue una configurazione, verrà visualizzata una finestra di dialogo che consente all'utente di salvare o aprire il file. Lo stesso comportamento viene utilizzato anche quando si importa una configurazione ER e non si configura nessuna destinazione specifica. Dopo aver creata una destinazione per un componente di output principale, tale destinazione ha la precedenza sul comportamento predefinito e la cartella o il file viene inviato in base alle impostazioni della destinazione.

## <a name="availability-and-general-prerequisites"></a>Disponibilità e prerequisiti generali
La funzionalità di destinazioni ER non è disponibile in Microsoft Dynamics AX 7.0 (febbraio 2016). Di conseguenza, è necessario installare Microsoft Dynamics 365 for Operations versione 1611 (novembre 2016) per utilizzare tutte le funzioni descritte in questo argomento. In alternativa, è possibile installare uno dei seguenti prerequisiti. Tuttavia, tenere presente che queste alternative forniscono un'esperienza di destinazione ER più limitata.

-   Microsoft Dynamics AX versione applicazione 7.0.1 (maggio 2016)
-   [Aggiornamento rapido dell'applicazione](https://fix.lcs.dynamics.com/issue/results/?q=3160213) per la gestione delle destinazioni ER

È possibile impostare le destinazioni solo per le configurazioni ER che sono state importate e per i formati disponibili nella pagina **Configurazioni creazione di report elettronici**.

## <a name="overview"></a>Panoramica
La funzionalità di gestione di destinazione ER è disponibile in **Amministrazione organizzazione** &gt; **Creazione di report elettronici**. In questo caso, è possibile ignorare il comportamento predefinito per una configurazione. Le configurazioni importate non vengono mostrate qui fino a quando non si fa clic su **Nuovo** e, quindi, nel campo **Riferimento** si seleziona una configurazione per cui creare le impostazioni di destinazione.

[![Selezione di una configurazione nel campo Riferimento](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

Dopo aver creato un riferimento, è possibile creare una destinazione di file per ogni cartella o un file. 

[![Creazione di una destinazione di file](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

**Nota:** È possibile creare una destinazione del file per ciascun componente di output dello stesso formato, ad esempio una cartella o un file selezionato nel campo **Nome campo**. È quindi possibile abilitare e disabilitare singole destinazioni per la destinazione di file nella finestra di dialogo **Impostazioni destinazione**. Il pulsante **Impostazioni** consente di controllare tutte le destinazioni per una destinazione di file selezionata. Nella finestra di dialogo **Impostazioni destinazione** è possibile controllare separatamente ogni destinazione impostando la relativa opzione **Abilitato**.

[![Finestra di dialogo Impostazioni di destinazione](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Tipi di destinazione
Sono supportati vari tipi di destinazioni. È possibile disabilitare o abilitare tutti i tipi contemporaneamente. In questo modo, è possibile non eseguire alcuna operazione o inviare il componenente a tutte le destinazioni configurate. Le sezioni seguenti descrivono le destinazioni che sono supportate.

### <a name="email-destination"></a>Destinazione posta elettronica

Impostare **Abilitato** su **Sì** per inviare un file di output tramite posta elettronica. Dopo aver abilitato questa opzione, è possibile specificare i destinatari del messaggio di posta elettronica e modificare l'oggetto e il corpo del messaggio. È possibile impostare testi costanti per l'oggetto e il corpo del messaggio di posta elettronica oppure utilizzare le formule ER per creare in modo dinamico i testi del messaggio di posta elettronica. È possibile configurare gli indirizzi di posta elettronica per ER in due modi. La configurazione può essere completata in modo analogo alla funzionalità Gestione stampa in Finance and Operations. In alternativa, è possibile risolvere un indirizzo di posta elettronica utilizzando un riferimento diretto alla configurazione ER mediante una formula.

### <a name="email-address-types"></a>Tipi di indirizzo di posta elettronica

Quando si fa clic su **Modifica** per il campo **A** o **Cc**, viene visualizzata la finestra di dialogo **Destinatario messaggio di posta elettronica**. È quindi possibile selezionare il tipo di indirizzo di posta elettronica da utilizzare.

[![Finestra di dialogo Destinatario messaggio di posta elettronica](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gestione stampa

Se si seleziona il tipo **Gestione stampa posta elettronica**, è possibile immettere indirizzi di posta elettronica fissi nel campo **A**. Per utilizzare indirizzi di posta elettronica non fissi, è necessario selezionare il tipo di origine di posta elettronica per la destinazione di un file. I valori seguenti sono supportati: **Cliente**, **Fornitore**, **Prospect**, **Contatto**, **Concorrente**, **Lavoratore**, **Candidato**, **Fornitore potenziale** e **Fornitore non autorizzato**. Dopo avere selezionato un tipo di origine della posta elettronica, utilizzare il pulsante accanto al campo **Conto di origine posta elettronica** per aprire il modulo **Designer formula**. È possibile utilizzare questo modulo per collegare una formula che rappresenta l'account parte selezionato alla destinazione di posta elettronica.

[![Configurare il tipo di Gestione stampa posta elettronica](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Si noti che le formule sono specifiche per la configurazione ER. Nel campo **Formula** immettere un riferimento specifico per il documento a un tipo di parte del cliente o del fornitore. Anziché digitare, è possibile cercare il nodo di origine dati che rappresenti il conto cliente o fornitore e fare clic sul pulsante **Aggiungi origine dati** per aggiornare la formula. Ad esempio, se si utilizza la configurazione bonifico ISO 20022, il nodo che rappresenta un conto fornitore è **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. In caso contrario, immettere qualsiasi valore di stringa, ad esempio **DE-001**, per salvare una formula.

[![Designer formula](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

Nella finestra di dialogo **Destinatario messaggio di posta elettronica**, fare clic sul cestino accanto al campo **Conto di origine posta elettronica** per eliminare in modo permanente la formula per il conto di origine posta elettronica. In alternativa, aprire Designer formula per modificare una formula precedentemente salvata. Per assegnare gli indirizzi di posta elettronica, fare clic su **Modifica** per aprire la finestra di dialogo **Assegna indirizzi di posta elettronica**.

[![Assegnazione di indirizzi di posta elettronica per una destinazione posta elettronica](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Posta elettronica configurazione

Usano questo tipo di messaggio di posta elettronica se la configurazione da utilizzare è un nodo nelle origini dati che rappresenta un indirizzo di posta elettronica. È possibile utilizzare le origini dati e le funzioni in Designer formula per ottenere un indirizzo di posta elettronica formattato correttamente.

[![Assegnazione di un'origine dati di indirizzo di posta elettronica per una destinazione posta elettronica](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Nota:** un server SMTP (Simple Mail Transfer Protocol) deve essere configurato e disponibile. È possibile specificare il server SMTP in Finance and Operations in **Amministrazione sistema** &gt; **Impostazioni** &gt; **Posta elettronica** &gt; **Parametri posta elettronica**.

### <a name="archive-destination"></a>Destinazione archivio

È possibile utilizzare questa opzione per inviare l'output a una cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure. Impostare **Abilitato** su **Sì** per inviare l'output a una destinazione definita dal tipo di documento selezionato. Solo tipi di documento in cui il gruppo è impostato su **File** sono disponibili per la selezione. I tipi di documento vengono definiti in **Amministrazione organizzazione** &gt; **Gestione documenti** &gt; **Tipi di documento**. La configurazione per le destinazioni ER è lo stessa della configurazione del sistema di gestione documenti.

[![Pagina Tipi di documento](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

Il percorso posizione determina dove viene salvato il file. Una volta abilitata la destinazione **Archivio**, i risultati dell'esecuzione della configurazione possono essere salvati nell'archivio processi. È possibile visualizzare i risultati in **Amministrazione organizzazione** &gt; **Creazione di report elettronici** &gt; **Processi archiviati di creazione report elettronici**. **Nota:** è possibile selezionare un tipo di documento per l'archivio processi in Finance and Operations in **Amministrazione organizzazione** &gt; **Aree di lavoro** &gt; **Creazione di report elettronici** &gt; **Parametri per la creazione di report elettronici**.

#### <a name="sharepoint"></a>SharePoint

È possibile salvare un file in una cartella designata di SharePoint. Il server SharePoint predefinito viene definito in **Amministrazione organizzazione** &gt; **Gestione documenti** &gt; **Parametri di gestione documenti** nella scheda **SharePoint**. Dopo aver configurato la cartella SharePoint, è possibile selezionarla come cartella in cui l'output di ER verrà salvato per il tipo di documento. 

[![Selezione di una cartella SharePoint](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Archiviazione di Azure

Quando il percorso del tipo di documento è impostato su **Directory archivio**, è possibile salvare un file nell'Archiviazione di Azure.

### <a name="file-destination"></a>Destinazione file

Se si imposta **Abilitato** su **Sì**, viene visualizzata una finestra di dialogo Apri o Salva al termine dell'esecuzione della configurazione.

### <a name="screen-destination"></a>Destinazione schermata

Se si imposta **Abilitato** su **Sì**, viene creata un'anteprima dell'output. È possibile visualizzare alcuni tipi di file, ad esempio XML, TXT o PDF, direttamente in una finestra del browser. Per altri tipi di file, ad esempio Microsoft Excel o Word, viene utilizzato il servizio Microsoft Office Online.

### <a name="power-bi-destination"></a>Destinazione Power BI

Impostare **Abilitato** su **Sì** per utilizzare la configurazione ER per definire il trasferimento di dati dall'istanza di Finance and Operations ai servizi Microsoft Power BI. I file trasferiti sono archiviati in un'istanza di Microsoft SharePoint Server che deve essere configurata a tale scopo. Per ulteriori informazioni, vedere [Utilizzare la configurazione di creazione report elettronici per fornire a Power BI i dati da Finance and Operations](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Suggerimento:** per ignorare il comportamento predefinito (ovvero, la finestra di dialogo per una configurazione), è possibile creare un riferimento di destinazione e una destinazione di file per il componente di output principale e quindi disattivare tutte le destinazioni.

## <a name="security-considerations"></a>Considerazioni sulla sicurezza
Vengono utilizzati due tipi di compiti e privilegi per le destinazioni ER. Un tipo controlla la possibilità di gestire le destinazioni generali che sono configurate per una persona giuridica (ovvero, controlla l'accesso alla pagina **Destinazione report elettronici**). L'altro tipo controlla la possibilità dell'utente di un'applicazione di ignorare, in fase di esecuzione, le impostazioni di destinazione configurate da uno sviluppatore ER o consulente funzionale ER.

| Ruolo (nome AOT)                     | Nome ruolo                                  | Compito (nome AOT)                     | Nome compito                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Sviluppatore per la creazione di report elettronici             | ERFormatDestinationConfigure        | Configura destinazione formato di report elettronici                |
| ERFunctionalConsultant              | Consulente funzionale per la creazione di report elettronici | ERFormatDestinationConfigure        | Configura destinazione formato di report elettronici                |
| PaymAccountsPayablePaymentsClerk    | Addetto pagamenti contabilità fornitori            | ERFormatDestinationRuntimeConfigure | Configura destinazione formato di report elettronici in fase di esecuzione |
| PaymAccountsReceivablePaymentsClerk | Addetto pagamenti contabilità clienti         | ERFormatDestinationRuntimeConfigure | Configura destinazione formato di report elettronici in fase di esecuzione |

**Nota:** vengono utilizzati due privilegi nei compiti precedenti. Questi privilegi hanno gli stessi nomi dei compiti corrispondenti: **ERFormatDestinationConfigure** e **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Ho importato configurazioni elettroniche e le vedo nella pagina Configurazioni creazione di report elettronici. Perché non vengono visualizzate nella pagina Destinazione report elettronici?

Assicurarsi di fare clic su **Nuovo** e quindi selezionare una configurazione nel campo **Riferimento**. Nella pagina **Destinazione report elettronici**, è possibile visualizzare solo le configurazioni per cui sono state configurate le destinazioni.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>È disponibile un metodo per definire quali account di Archiviazione di Azure e Archivio BLOB di Azure vengono utilizzati?

N. Viene utilizzato l'Archivio BLOB di Azure definito e utilizzato per il sistema di gestione documenti.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Qual è lo scopo della Destinazione file nelle impostazioni di destinazione? Cosa fa questa impostazione?

La destinazione **File** viene utilizzata per controllare una finestra di dialogo. Se si abilita questa destinazione, o se per una configurazione non è definita alcuna destinazione, verrà visualizzata una finestra di dialogo Apri o Salva dopo la creazione di un file di output.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>È possibile ottenere un esempio della formula che fa riferimento a un conto fornitore a cui inviare messaggi di posta elettronica?

La formula è specifica per la configurazione ER. Ad esempio, se si utilizza la configurazione bonifico ISO 20022, è possibile utilizzare **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** o **model.Payments.Creditor.Identification.SourceID** per ottenere un conto fornitore associato.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Una delle configurazioni formato contiene più file raggruppati in un'unica cartella (ad esempio, Folder1 contiene File1 e File2 e File3). Come impostare le destinazioni in modo che Folder1.zip non viene creata, File1 viene inviato tramite posta elettronica, File2 viene inviato a SharePoint e sia possibile aprire File3 immediatamente dopo aver eseguito la configurazione?

Il prerequisito è che il formato deve essere disponibile nelle configurazioni ER. Se si dispone del formato, aprire la pagina **Destinazione report elettronici** e creare un nuovo riferimento a questa configurazione. È quindi necessario avere quattro destinazioni file, una per ogni componente di output. Creare la prima destinazione file, assegnare un nome quale **Folder** e selezionare un nome di file che rappresenta una cartella nella configurazione. Quindi fare clic su **Impostazioni** e assicurarsi che tutte le destinazioni siano disabilitate. Per questa destinazione del file, non verrà creata la cartella. Per impostazione predefinita, a causa delle dipendenze gerarchiche tra i file e cartelle padre, i file si comporteranno nello stesso modo. In altre parole, non saranno inviati da nessuna parte. Per ignorare il comportamento predefinito, è necessario creare tre ulteriori destinazioni file, una per ogni file. Nelle impostazioni di destinazione per ciascuno, è necessario abilitare la destinazione a cui il file deve essere inviato.

# <a name="see-also"></a>Vedere anche

[Panoramica sui report elettronici](general-electronic-reporting.md)




