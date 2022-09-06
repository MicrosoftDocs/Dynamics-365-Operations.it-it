---
title: Destinazioni dei report elettronici
description: Questo articolo fornisce informazioni sulla gestione delle destinazioni di report elettronici, i tipi di destinazioni supportati e le considerazioni sulla sicurezza.
author: kfend
ms.date: 08/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: DocuType, ERSolutionTable
ms.openlocfilehash: b1bf6289e80769dfe8858f307cbb9b217b42dbb4
ms.sourcegitcommit: f2edc193003564c5bee1747f9c2b800feee342bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2022
ms.locfileid: "9360981"
---
# <a name="electronic-reporting-er-destinations"></a>Destinazioni dei report elettronici

[!include [banner](../includes/banner.md)]

È possibile configurare una destinazione per ciascuna configurazione di formato per la creazione di report elettronici (ER) e del relativo componente di output (una cartella o un file). Gli utenti che dispongono di diritti di accesso appropriati anche possono modificare le impostazioni di destinazione in fase di esecuzione. Questo articolo illustra la gestione delle destinazioni ER, i tipi di destinazioni supportati e considerazioni sulla sicurezza.

Le configurazioni del formato ER in genere contengono almeno un componente di output: un file. In genere, le configurazioni contengono più componenti di output di file di tipo diverso (ad esempio, XML, TXT o XLSX, DOCX, o PDF) che vengono raggruppati in una cartella singola o più cartelle. La gestione di destinazione ER consente di preconfigurare quello che si verifica durante l'esecuzione di ogni componente. Per impostazione predefinita, quando si esegue una configurazione, verrà visualizzata una finestra di dialogo che consente all'utente di salvare o aprire il file. Lo stesso comportamento si ha anche quando si importa una configurazione ER e non si configura nessuna destinazione specifica. Dopo aver creata una destinazione per un componente di output principale, tale destinazione ha la precedenza sul comportamento predefinito e la cartella o il file viene inviato in base alle impostazioni della destinazione.

## <a name="availability-and-general-prerequisites"></a>Disponibilità e prerequisiti generali

La funzionalità per le destinazioni ER non è disponibile in Microsoft Dynamics AX 7.0 (febbraio 2016). Di conseguenza, è necessario installare Microsoft Dynamics 365 for Operations versione 1611 (novembre 2016) o successiva per utilizzare i seguenti tipi di destinazioni:

- [Indirizzo di posta elettronica](er-destination-type-email.md)
- [Archivia](er-destination-type-archive.md)
- [File](er-destination-type-file.md)
- [Schermo](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

In alternativa, è possibile installare uno dei seguenti prerequisiti. Tuttavia, tenere presente che queste alternative forniscono un'esperienza di destinazione ER più limitata.

- Microsoft Dynamics AX versione applicazione 7.0.1 (maggio 2016)
- [Aggiornamento rapido per la gestione delle destinazioni ER](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

È presente anche un tipo di destinazione [Stampa ](er-destination-type-print.md). Per usarlo, è necessario installare Microsoft Dynamics 365 Finance versione 10.0.9 (aprile 2020).

## <a name="overview"></a>Panoramica

È possibile impostare le destinazioni solo per le configurazioni ER che sono state [importate](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) nell'istanza corrente di Finance e per i formati disponibili nella pagina **Configurazioni creazione di report elettronici**. La funzionalità per la gestione di destinazioni ER è disponibile in **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Destinazione report elettronici**.

### <a name="default-behavior"></a>Comportamento predefinito

Il comportamento predefinito per una configurazione di formato ER dipende dal tipo di esecuzione specificato all'avvio di un formato ER.

Nella finestra di dialogo **Report Intrastat**, nella Scheda dettaglio **Esecuzione in background**, se si imposta l'opzione **Elaborazione batch** su **No**, un formato ER viene eseguito immediatamente in modalità interattiva. Quando questa esecuzione viene completata correttamente, un documento in uscita generato viene reso disponibile per il download.

Se si imposta l'opzione **Elaborazione batch** su **Sì**, un formato ER viene eseguito in modalità [batch](../sysadmin/batch-processing-overview.md). Il processo batch appropriato viene creato in base ai parametri specificati nella scheda **Esecuzione in background** della finestra di dialogo **Parametri ER**.

> [!NOTE]
> La descrizione mansione informa l'utente dell'esecuzione di un mapping di formato ER. Include inoltre il nome del componente ER eseguito.

[![Esecuzione di un formato ER.](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

È possibile trovare informazioni su questo processo in diversi luoghi:

- Andare a **Comune** \> **Informazioni** \> **Processi batch** \> **Processi batch dell'utente** per verificare lo stato del processo programmato.
- Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi di creazione report elettronici** per verificare lo stato del processo programmato e i risultati dell'esecuzione del processo completato. Al termine dell'esecuzione del processo, selezionare **Mostra file** nella pagina **Processi di creazione report elettronici** per ottenere un documento in uscita generato.

    > [!NOTE]
    > Questo documento è archiviato come allegato del record del processo corrente ed è controllato dal framework [Gestione documenti](../../fin-ops/organization-administration/configure-document-management.md). Il [tipo di documento](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) che viene utilizzato per memorizzare gli elementi ER di questo tipo è configurato in [Parametri ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

- Nella pagina **Processi di creazione report elettronici** selezionare **Mostra file** per visualizzare l'elenco di eventuali errori e avvisi generati durante l'esecuzione del lavoro.

    [![Revisione dell'elenco dei processi ER.](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>Comportamento configurato dall'utente

Nella pagina **Destinazione report elettronici**, è possibile ignorare il comportamento predefinito per una configurazione. Le configurazioni importate non sono visualizzate in questa pagina fino a quando non si seleziona **Nuovo** e, quindi, nel campo **Riferimento** si seleziona una configurazione per cui creare le impostazioni di destinazione.

[![Selezione di una configurazione nel campo Riferimento.](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

Dopo aver creato un riferimento, è possibile creare una destinazione del file per ogni componente di output **Cartella** o **File** del formato ER a cui si fa riferimento.

[![Creazione di una destinazione file.](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Successivamente, è possibile abilitare e disabilitare singole destinazioni per la destinazione file nella finestra di dialogo **Impostazioni destinazione**. Il pulsante **Impostazioni** consente di controllare tutte le destinazioni per una destinazione file selezionata. Nella finestra di dialogo **Impostazioni destinazione** è possibile controllare separatamente ogni destinazione impostando la relativa opzione **Abilitato**.

Nelle versioni di Finance **antecedenti alla versione 10.0.9**, è possibile creare **una destinazione file** per ciascun componente di output dello stesso formato, ad esempio una cartella o un file selezionato nel campo **Nome campo**. Tuttavia, nella **versione 10.0.9 e successive**, è possibile creare **più destinazioni di file** per ogni componente di output dello stesso formato.

Ad esempio, è possibile utilizzare questa funzionalità per configurare destinazioni di file per un componente di file utilizzato per generare un documento in uscita in formato Excel. Una destinazione ( [Archivio](er-destination-type-archive.md)) può essere configurata per memorizzare il file Excel originale nell'archivio dei processi ER e un'altra destinazione ([E-mail ](er-destination-type-email.md)) può essere configurata per [convertire](#OutputConversionToPDF) simultaneamente il file Excel in formato PDF e inviare il file PDF via posta elettronica.

[![Configurazione di più destinazioni per un singolo elemento di formato.](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

Quando si esegue un formato ER, vengono sempre eseguite tutte le destinazioni configurate per i componenti del formato. Inoltre, in Finance **versione 10.0.17 e successive**, la funzionalità delle destinazioni ER è stata migliorata e ora consente di configurare diversi set di destinazioni per un unico formato ER. Questa configurazione contrassegna ogni set come configurato per una particolare azione utente. L'API ER è stata [estesa](er-apis-app10-0-17.md) in modo che possa essere fornita un'azione che l'utente esegue eseguendo un formato ER. Il codice azione fornito viene passato alle destinazioni ER. È possibile eseguire diverse destinazioni di un formato ER, a seconda del codice azione fornito. Per ulteriori informazioni, vedere [Configurare destinazioni ER dipendenti dall'azione](er-action-dependent-destinations.md).

## <a name="destination-types"></a>Tipi di destinazione

Le seguenti destinazioni sono attualmente supportate per i formati ER. È possibile disabilitare o abilitare tutti i tipi contemporaneamente. In questo modo, è possibile non eseguire alcuna operazione o inviare il componenente a tutte le destinazioni configurate.

- [Indirizzo di posta elettronica](er-destination-type-email.md)
- [Archivia](er-destination-type-archive.md)
- [File](er-destination-type-file.md)
- [Schermo](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Stampa](er-destination-type-print.md)

## <a name="applicability"></a>Applicabilità

È possibile impostare le destinazioni solo per le configurazioni ER che sono state importate e per i formati disponibili nella pagina **Configurazioni creazione di report elettronici**.

> [!NOTE]
> Le destinazioni configurate sono specifiche dell'azienda. Se si prevede di utilizzare un formato ER in diverse società dell'istanza Finance corrente, è necessario configurare le destinazioni per quel formato ER per ciascuna di tali società.

Quando si configurano destinazioni di file per un formato selezionato, le si configura per l'intero formato.

[![Collegamento Configurazione.](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

Allo stesso tempo, si potrebbero avere più versioni  del formato che è stato importato nell'istanza corrente di Finance. È possibile visualizzarle selezionando il collegamento **Configurazione** che risulta disponibile quando si seleziona il campo **Riferimento**.

[![Versioni di configurazione.](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Per impostazione predefinita, le destinazioni configurate vengono applicate quando si esegue una versione del formato ER il cui stato è **Completato** o **Condiviso**. Tuttavia, a volte è necessario utilizzare destinazioni configurate quando viene eseguita la versione bozza di un formato ER. Ad esempio, si modifica una versione bozza del proprio formato e si desidera utilizzare destinazioni configurate per testare la modalità di consegna dell'output generato. Seguire questi passaggi per applicare le destinazioni per un formato ER quando viene eseguita la versione bozza.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Impostare l'opzione **Usa destinazioni per lo stato bozza** su **Sì**.

[![Opzione Usa destinazioni per lo stato bozza.](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Per utilizzare la versione bozza di un formato ER, è necessario contrassegnare il formato ER di conseguenza.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Impostare l'opzione **Esegui impostazione** su **Sì**.

[![Opzione Esegui impostazione.](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Dopo aver completato questa configurazione, l'opzione **Esegui bozza** diventa disponibile per i formati ER modificati. Impostare questa opzione su **Sì** per iniziare a utilizzare la versione bozza del formato quando questo viene eseguito.

[![Opzione Esegui bozza.](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>Gestione degli errori di destinazione

Di solito, un formato ER viene eseguito nell'ambito di un processo aziendale specifico. Tuttavia, la consegna di un documento in uscita generato durante l'esecuzione di un formato ER deve talvolta essere considerata parte di tale processo aziendale. In questo caso, se la consegna di un documento in uscita generato a una destinazione configurata non ha esito positivo, l'esecuzione del processo aziendale deve essere annullata. Per configurare la destinazione ER appropriata, selezionare l'opzione **Interrompi elaborazione in caso di errore**.

Ad esempio, si configura l'elaborazione dei pagamenti fornitore in modo che il formato ER **Bonifico ISO20022** venga eseguito per generare il file di pagamento e documenti supplementari (ad esempio, la lettera di accompagnamento e il report di controllo). Se un pagamento deve essere considerato come correttamente elaborato solo se la lettera di accompagnamento viene recapitata correttamente tramite posta elettronica, è necessario selezionare la casella di controllo **Interrompi elaborazione in caso di errore** per il componente **CoveringLetter** nella destinazione file appropriata, come mostrato nella figura seguente. In questo caso, lo stato del pagamento selezionato per l'elaborazione passerà da **Nessuno** a **Inviato** solo quando la lettera di accompagnamento generata viene accettata correttamente per la consegna da un provider di posta elettronica configurato nell'istanza di Finance.

[![Configurazione della gestione dei processi per le destinazioni di file con errori.](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Se si disabilita la casella di controllo **Interrompi elaborazione in caso di errore** per il componente **CoveringLetter** nella destinazione, un pagamento verrà considerato come elaborato correttamente anche se la lettera di accompagnamento non è stata consegnata correttamente tramite posta elettronica. Lo stato del pagamento passerà da **Nessuno** a **Inviato** anche se la lettera di accompagnamento non può essere inviata perché, ad esempio, l'indirizzo e-mail del destinatario o del mittente risulta mancante o è errato.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>Conversione dell'output in PDF

È possibile utilizzare l'opzione di conversione PDF per convertire in PDF l'output in formato Microsoft Office (Excel o Word).

### <a name="make-pdf-conversion-available"></a>Rendere disponibile la conversione PDF

Per rendere disponibile l'opzione di conversione PDF nell'istanza corrente, di Finance, aprire l'area di lavoro **Gestione funzionalità** e attivare la funzionalità **Converti documenti in uscita ER da formati Microsoft Office in PDF**.

[![Attivazione della funzionalità di conversione PDF di documenti in uscita in Gestione funzionalità.](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Applicabilità

Nelle versioni di Finance **antecedenti alla versione 10.0.18**, l'opzione di conversione PDF può essere abilitata solo per i componenti **Excel\\File** utilizzati per generare output in formato Office (Excel o Word). Quando questa opzione è attivata, l'output generato in formato Office viene automaticamente convertito in formato PDF. Tuttavia, nella **versione 10.0.18 e successive**, è anche possibile attivare questa opzione per i componenti di tipo **Comune\\File**.

> [!NOTE]
> Prestare attenzione al messaggio di avviso visualizzato quando si attiva l'opzione di conversione PDF per un componente ER di tipo **Comune\\File**. Questo messaggio indica che non esiste alcun modo di garantire, in fase di progettazione, che il componente file selezionato esporrà il contenuto in formato PDF o il contenuto convertibile in PDF in fase di runtime. Pertanto, è necessario attivare l'opzione solo se si è certi che il componente file selezionato è stato configurato per esporre il contenuto in formato PDF o il contenuto convertibile in PDF in fase di runtime.
> 
> Se si attiva l'opzione di conversione PDF per un componente di formato, se quel componente espone il contenuto in un formato diverso da PDF e se il contenuto esposto non può essere convertito in formato PDF, si verificherà un'eccezione in fase di runtime. Il messaggio che si riceve indica che il contenuto generato non può essere convertito in formato PDF.

### <a name="limitations"></a>Limiti

A partire da Finance **versione 10.0.9** l'opzione di conversione PDF è disponibile solo per le distribuzioni cloud. A partire dalla versione Finance **10.0.27**, l'opzione di conversione PDF è disponibile per qualsiasi distribuzione locale che abbia la [connettività Internet](../user-interface/client-disconnected.md) abilitata.

Il documento PDF generato è limitato a un numero massimo di 300 pagine.

A partire da Finance **versione 10.0.9**, nel documento PDF prodotto da un output Excel è supportato solo l'orientamento orizzontale della pagina. A partire da Finance **versione 10.0.10**, è possibile [specificare l'orientamento della pagina](#SelectPdfPageOrientation) nel documento PDF prodotto da un output di Excel mentre si configura una destinazione ER.

Solo i caratteri di sistema comuni del sistema operativo Windows vengono utilizzati per la conversione di un output che non contiene caratteri incorporati.

### <a name="resources"></a>Risorse

Prima della versione 10.0.29 di Finance, la conversione in PDF poteva essere eseguita solo al di fuori dell'istanza Finance corrente. Un file generato era inviato da Finance al servizio di conversione e quindi tale servizio restituiva il documento convertito. Tuttavia, nella versione **10.0.29 e successive**, oltre alla funzionalità **Convertire documenti in uscita per la creazione di report elettronici da formati Microsoft Office in PDF**, è possibile abilitare la funzionalità **Utilizzare le risorse dell'applicazione per eseguire la conversione dei documenti aziendali configurabili da Word al formato PDF**. Questa funzionalità consente di convertire i documenti di Word generati in formato PDF in locale utilizzando le risorse del server delle applicazioni nell'istanza Finance corrente. 

Di seguito sono descritti i vantaggi della conversione in PDF locale quando la funzionalità **Utilizzare le risorse dell'applicazione per eseguire la conversione dei documenti aziendali configurabili da Word al formato PDF** è abilitata:

- Il documento PDF generato non è [limitato](#limitations) a un numero massimo di pagine.
- Il documento di Word convertito può contenere un [gran numero di controlli del contenuto](https://fix.lcs.dynamics.com/Issue/Details?bugId=647877&dbType=3).
- La connettività Internet non è richiesta nelle distribuzioni locali.

### <a name="use-the-pdf-conversion-option"></a>Utilizzare l'opzione di conversione PDF

Per attivare la conversione PDF per una destinazione file, selezionare la casella di controllo **Converti in PDF**.

[![Attivazione della conversione PDF per una destinazione file.](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">Selezionare un orientamento di pagina per la conversione PDF</a>

Se si genera una configurazione ER in formato Excel e si desidera convertirla in formato PDF, è possibile specificare esplicitamente l'orientamento della pagina del documento PDF. Quando si seleziona la casella di controllo **Converti in PDF** per attivare la conversione PDF per una destinazione di file che produce un file di output in formato Excel, il campo **Orientamento pagina** diventa disponibile nella scheda dettaglio **Impostazioni di conversione PDF**. Nel campo **Orientamento pagina**, selezionare l'orientamento preferito.

[![Selezione di un orientamento di pagina per la conversione PDF.](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

Per avere la possibilità di selezionare l'orientamento della pagina PDF, installare Finance versione 10.0.10 o successiva. Nelle versioni di Finance **prima della versione 10.0.23**, questa opzione offre le seguenti opzioni di orientamento della pagina:

- Verticale
- Orizzontale

L'orientamento della pagina selezionato viene applicato a tutte le pagine di un documento in uscita che vengono generate in formato Excel e quindi convertite in formato PDF.

Tuttavia, nella **versione 10.0.23 e successive**, l'elenco delle opzioni di orientamento della pagina è stato ampliato come segue:

- Verticale
- Orizzontale
- Specifico del foglio di lavoro

Quando si seleziona l'opzione **Specifico del foglio di lavoro**, ogni foglio di lavoro di una cartella di lavoro Excel generato viene convertito in PDF utilizzando l'orientamento della pagina che è stato configurato per questo foglio di lavoro nel modello Excel utilizzato. Quindi, potresti avere un documento PDF finale contenente pagine verticali e orizzontali. 

Se una configurazione ER in formato Word viene convertita in formato PDF, l'orientamento della pagina del documento PDF viene sempre preso dal documento Word.

## <a name="output-unfolding"></a>Apertura dell'output

Quando si configura una destinazione per il componente **Cartella** del formato ER, è possibile specificare come l'output di quel componente viene recapitato alla destinazione configurata.

### <a name="make-output-unfolding-available"></a>Rendere disponibile l'apertura dell'output

Per rendere disponibile l'opzione di apertura dell'output nell'istanza corrente di Finance, apri l'area di lavoro **Gestione funzionalità** e attiva la funzionalità **Consenti la configurazione delle destinazioni ER per inviare il contenuto delle cartelle come file separati**.

### <a name="applicability"></a>Applicabilità

L'opzione di apertura dell'output può essere configurata solo per i componenti di formato di tipo **Cartella**. Quando inizi a configurare un componente **Cartella**, la scheda Dettaglio **Generale** diventa disponibile nella pagina **Destinazione di creazione di report elettronici**. 

### <a name="use-the-output-unfolding-option"></a>Utilizzare l'opzione di apertura dell'output

Nella Scheda dettaglio **Generale**, nel campo **Invia cartella come**, seleziona uno dei seguenti valori:

- **Archivio ZIP**: recapita un file generato come file zip.
- **File separati**: recapita ogni file di un file zip generato come un singolo file.

    > [!NOTE]
    > Quando selezioni **File separati**, l'output generato viene raccolto in memoria in uno stato compresso. Pertanto, il [limite di dimensione del file](er-compress-outbound-files.md) massimo viene applicato per l'output compresso quando la dimensione reale del file potrebbe superare questo limite. Si consiglia di selezionare questo valore quando si prevede che anche la dimensione dell'output generato sarà abbastanza grande.

[![Configurazione di una destinazione per un componente formato cartella.](./media/er_destinations-set-unfolding-option.png)](./media/er_destinations-set-unfolding-option.png)

### <a name="limitations"></a>Limiti

Se imposti il campo **Invia cartella come** su **File separati** per un componente **Cartella** che contiene altri componenti **Cartella**, l'impostazione non viene applicata in modo ricorsivo ai componenti **Cartella**.

## <a name="change-page-layout-properties-of-a-template"></a><a name="change-page-layout-properties-of-a-template"></a>Modificare le proprietà del layout di pagina di un modello

Puoi configurare una destinazione ER per un componente in formato ER progettato per utilizzare un modello in un formato Microsoft Office (Excel o Word) per la generazione di report. Se non sei il proprietario di questo formato e devi modificare le proprietà del layout di pagina del modello del formato, nelle versioni di Finance precedenti alla versione 10.0.29, devi creare un formato derivato e modificare le proprietà del modello. Quindi, devi mantenere la configurazione del formato derivato. Tuttavia, nella versione 10.0.29 e successive, puoi modificare le proprietà del layout di pagina del modello al runtime per evitare di creare e mantenere la configurazione del formato derivato. A tale scopo, configura le proprietà desiderate come parte delle impostazioni della destinazione ER configurata. Quando esegui un formato ER ed esegui una destinazione ER configurata per utilizzare determinate proprietà del layout di pagina, i valori delle proprietà del layout di pagina della destinazione eseguita vengono applicati al modello che stai utilizzando, sostituendo le proprietà del modello originale. Puoi configurare destinazioni diverse per il componente dello stesso formato configurando proprietà del layout di pagina differenti per il modello in uso.

Le seguenti proprietà possono essere configurate in una destinazione ER per un componente di formato progettato per utilizzare un modello in formato Excel o Word.

- Orientamento
    - Verticale
    - Orizzontale
- Dimensioni
    - A3
    - A4
    - A5
    - B4
    - B5
    - Executive
    - Note legali
    - Lettera
    - Rendiconto
    - Tabloid
- Margini pagina
    - Superiore
        - Intestazione
    - Inferiore
        - Piè di pagina
    - Sinistro
    - Destro

> [!NOTE]
> L'orientamento della pagina del modello configurato in questo modo deve essere allineato all'[orientamento della pagina per la conversione PDF](#select-a-page-orientation-for-pdf-conversion) se la conversione PDF è configurata.

Devi selezionare l'unità di lunghezza per impostare i margini della pagina:

- Pollici
- Centimetri
- Millimetri

![Imposta le proprietà del layout di pagina nella pagina Destinazione report elettronici.](./media/er_destinations-set-page-layout-properties.png)

> [!TIP]
> Quando un valore di margine viene nominato in centimetri e specificato con più decimali, viene arrotondato al runtime al valore più vicino con 1 punto decimale.
>
> Quando un valore di margine viene nominato in millimetri e specificato con decimali, viene arrotondato al runtime per Excel al valore intero più vicino con nessun punto decimale.
>
> Quando un valore di margine viene nominato in millimetri e specificato con più decimali, viene arrotondato al runtime per Word al valore intero più vicino con un punto decimale.

## <a name="security-considerations"></a>Considerazioni sulla sicurezza

Vengono utilizzati due tipi di compiti e privilegi per le destinazioni ER. Un tipo controlla la possibilità globale di un utente di gestire le destinazioni configurate per una persona giuridica (ovvero, controlla l'accesso alla pagina **Destinazione report elettronici**). L'altro tipo controlla la possibilità dell'utente di un'applicazione di ignorare, in fase di esecuzione, le impostazioni di destinazione configurate da uno sviluppatore ER o consulente funzionale ER.

| Ruolo (nome AOT)                     | Nome ruolo                                  | Compito (nome AOT)                     | Nome compito                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Sviluppatore per la creazione di report elettronici             | ERFormatDestinationConfigure        | Configura destinazione formato di report elettronici                |
| ERFunctionalConsultant              | Consulente funzionale per la creazione di report elettronici | ERFormatDestinationConfigure        | Configura destinazione formato di report elettronici                |
| PaymAccountsPayablePaymentsClerk    | Addetto pagamenti contabilità fornitori            | ERFormatDestinationRuntimeConfigure | Configura destinazione formato di report elettronici in fase di esecuzione |
| PaymAccountsReceivablePaymentsClerk | Addetto pagamenti contabilità clienti         | ERFormatDestinationRuntimeConfigure | Configura destinazione formato di report elettronici in fase di esecuzione |

> [!NOTE]
> Vengono utilizzati due privilegi nei compiti precedenti. Questi privilegi hanno gli stessi nomi dei compiti corrispondenti: **ERFormatDestinationConfigure** e **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Ho importato configurazioni elettroniche e le vedo nella pagina Configurazioni creazione di report elettronici. Perché non vengono visualizzate nella pagina Destinazione report elettronici?

Assicurarsi di selezionare **Nuovo** e quindi selezionare una configurazione nel campo **Riferimento**. La pagina **Destinazione report elettronici** visualizza solo le configurazioni per cui sono state configurate le destinazioni.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>È disponibile un metodo per definire quali account di Archiviazione di Microsoft Azure e Archivio BLOB di Azure vengono utilizzati?

N. Viene utilizzato l'Archivio BLOB di Microsoft Azure definito e utilizzato per il sistema di gestione documenti.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Qual è lo scopo della Destinazione file nelle impostazioni di destinazione? Cosa fa questa impostazione?

La destinazione **File** viene utilizzata per controllare una finestra di dialogo del Web browser quando si esegue un formato ER in modalità interattiva. Se si abilita questa destinazione, o se per una configurazione non è definita alcuna destinazione, viene visualizzata una finestra di dialogo Apri o Salva nel Web browser dopo la creazione di un file di output.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>È possibile ottenere un esempio della formula che fa riferimento a un conto fornitore a cui inviare messaggi di posta elettronica?

La formula è specifica per la configurazione ER. Ad esempio, se si utilizza la configurazione bonifico ISO 20022, è possibile utilizzare **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** o **model.Payments.Creditor.Identification.SourceID** per ottenere un conto fornitore associato.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Una delle configurazioni formato contiene più file raggruppati in un'unica cartella (ad esempio, Folder1 contiene File1 e File2 e File3). Come impostare le destinazioni in modo che Folder1.zip non viene creata, File1 viene inviato tramite posta elettronica, File2 viene inviato a SharePoint e sia possibile aprire File3 immediatamente dopo aver eseguito la configurazione?

Il formato deve essere disponibile dapprima nelle configurazioni ER. Se questo prerequisito viene soddisfatto, aprire la pagina **Destinazione report elettronici** e creare un nuovo riferimento alla configurazione. È quindi necessario avere quattro destinazioni file, una per ogni componente di output. Creare la prima destinazione file, assegnare un nome quale **Folder** e selezionare un nome di file che rappresenta una cartella nella configurazione. Quindi selezionare **Impostazioni** e assicurarsi che tutte le destinazioni siano disabilitate. Per questa destinazione del file, non verrà creata la cartella. Per impostazione predefinita, a causa delle dipendenze gerarchiche tra i file e cartelle padre, i file si comporteranno nello stesso modo. In altre parole, non saranno inviati da nessuna parte. Per ignorare il comportamento predefinito, è necessario creare tre ulteriori destinazioni file, una per ogni file. Nelle impostazioni di destinazione per ciascuno, è necessario abilitare la destinazione a cui il file deve essere inviato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei report elettronici](general-electronic-reporting.md)

[Configurare destinazioni ER dipendenti dall'azione](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
