---
title: Sopprimere i controlli del contenuto di Word nei report generati
description: In questo argomento viene descritto come configurare un formato di creazione di report elettronici (ER) per generare report come file Microsoft Word in cui i controlli del contenuto sono stati eliminati.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: cfabd6f544dca6f48448da4ef9ff8383c6583f8488a718a7c971ff7b39c1f2cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737977"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>Sopprimere i controlli del contenuto di Word nei report generati

[!include [banner](../includes/banner.md)]

Per generare report come documenti Microsoft Word, è necessario progettare un modello per i report come documento Word. Questo modello deve contenere controlli del contenuto di Word come segnaposto per i dati che verranno compilati in fase di esecuzione. Per utilizzare il documento Word creato come modello per i report, è possibile [configurare](er-design-configuration-word.md) una nuova [soluzione](er-quick-start1-new-solution.md) di [Creazione di report elettronici (ER)](general-electronic-reporting.md). La soluzione deve includere una [configurazione](general-electronic-reporting.md#Configuration) ER che contiene un componente in [formato](general-electronic-reporting.md#FormatComponentOutbound) ER. Questo formato ER deve essere configurato per utilizzare il modello progettato per la generazione di report.

Nella versione 10.0.6 e successive di Dynamics 365 Finance, è possibile configurare formule nel formato ER per sopprimere alcuni controlli del contenuto di Word nei documenti generati.

I passaggi seguenti spiegano come un utente assegnato al ruolo di amministratore di sistema o di consulente funzionale per la creazione di report elettronici può configurare un formato ER che genera report come file Word e sopprime alcuni dei controlli del contenuto nei report generati che sono stati configurati utilizzando un modello Word.

Questi passaggi possono essere completati nella società GBSI.

## <a name="prerequisites"></a>Prerequisiti

Per effettuare questi passaggi, è necessario completare quelli nelle seguenti guide attività:

- [Progettare una configurazione per la creazione di report nel formato OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Riutilizzare le configurazioni per la creazione di report elettronici con modelli di Excel per generare report in formato Word](./tasks/er-design-configuration-word-2016-11.md)

Dopo aver completato i passaggi di queste guide attività, vengono preparati i seguenti elementi:

- Un formato ER **Report foglio di lavoro di esempio** configurato per generare un documento in formato Word
- Una versione [bozza](general-electronic-reporting.md#component-versioning) del formato ER **Report del foglio di lavoro di esempio** contrassegnato come **Eseguibile**
- Un metodo di pagamento **Elettronico** configurato per utilizzare il formato ER **Report del foglio di lavoro di esempio** per l'elaborazione dei pagamenti del fornitore

È inoltre necessario scaricare e salvare il seguente modello per il report di esempio:

- [Modello associato 2 di Report di pagamento (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>Rivedere il modello di Word scaricato

1. Nell'applicazione desktop Word, aprire il file del modello **SampleVendPaymDocReportBounded2.docx** scaricato in precedenza.
2. Verificare che il file del modello contenga una sezione di riepilogo che mostra gli importi totali dei pagamenti per ogni codice valuta che è stato soddisfatto nei pagamenti elaborati.

    - La sezione di riepilogo risiede in una tabella separata del documento Word.
    - La prima riga di questa tabella contiene le intestazioni delle colonne della tabella come intestazione di sezione.
    - La seconda riga di questa tabella contiene il controllo del contenuto ripetuto come dettagli della sezione.
    - Questo controllo del contenuto è mappato al campo **SummaryLines** della parte XML personalizzata **Report**.
    - In base a questo mapping, il controllo del contenuto è associato all'elemento **SummaryLines** del formato ER modificabile.

    > [!NOTE]
    > Il controllo del contenuto ripetuto è contrassegnato con la chiave **SummaryLines** che corrisponde al campo della parte XML personalizzata a cui è stata mappata.

    ![Layout del modello Word.](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>Selezionare la configurazione esistente del report ER

Per i passaggi seguenti, si riutilizzerà la configurazione ER esistente configurata quando sono stati completati i passaggi nelle guide attività menzionate in precedenza.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di pagamento**, quindi selezionare **Report foglio di lavoro di esempio**.
4. Selezionare **Designer** per modificare la versione bozza del formato ER selezionato.

## <a name="replace-the-current-template-with-the-new-template"></a>Sostituire il modello corrente con il nuovo modello

Attualmente, il file SampleVendPaymDocReportBounded.docx viene utilizzato come modello per generare l'output nel formato Word. Nei passaggi seguenti, questo modello di Word verrà sostituito con il nuovo modello di Word, SampleVendPaymDocReportBounded2.docx caricato in precedenza.

1. Nella pagina **Progettazione formati**, selezionare **Allegati**.
2. Nella pagina **Allegati**, selezionare **Elimina** per rimuovere il modello esistente.
3. Selezionare **Sì** per confermare l'eliminazione.
4. Seleziona **Nuovo** \> **File**.
5. Selezionare **Sfoglia** e individuare e selezionare il file **SampleVendPaymDocReportBounded2.docx** scaricato in precedenza.
6. Selezionare **OK**.
7. Chiudere la pagina **Allegati**.
8. Nella pagina **Progettazione formati** nel campo **Modello**, immettere o selezionare il file **SampleVendPaymDocReportBounded2.docx**.

## <a name="run-the-format-to-create-word-output"></a>Eseguire il formato per creare l'output di Word

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti**.
2. Nella pagina **Pagamenti fornitore**, nella scheda **Elenco**, selezionare tutti i pagamenti.
3. Selezionare **Stato del pagamento** \> **Nessuno**.
4. Selezionare **Genera pagamenti**.
5. Nel campo **Metodo di pagamento** seleziona **Elettronico**.
6. Nel campo **Conto bancario** selezionare **GBSI OPER**.
7. Selezionare **OK**.
8. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, selezionare **OK** e analizzare l'output generato.

    ![Pagamenti per l'elaborazione nella pagina Pagamenti fornitore.](./media/er-design-configuration-word-suppress-controls-image2.gif)

    L'output viene presentato in formato Word e contiene la sezione di riepilogo.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>Configurare il formato modificabile per sopprimere la sezione di riepilogo

Se si desidera sopprimere la sezione di riepilogo in un documento generato, in base alla richiesta di un utente che esegue questo formato ER, è necessario modificare il formato ER modificabile.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici** e aprire la versione bozza del formato ER da modificare.
2. Selezionare **Configurazioni report**. 
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di pagamento** \> **Report foglio di lavoro di esempio**.
4. Selezionare **Progettazione**.
5. Nella pagina **Progettazione formati**, espandere **Word** e selezionare **SummaryLines**.
6. Nella scheda **Mapping**, aggiungere una nuova origine dati per chiedere all'utente, in fase di runtime, se la sezione di riepilogo deve essere soppressa:

    1. Selezionare **Aggiungi radice**.
    2. Nella finestra di dialogo **Aggiungi origine dati**, selezionare **Generale\Parametro di input utente** per aprire la finestra di dialogo **Proprietà origine dati "Parametro di input utente"**.
    3. Nel campo **Nome** immettere **uipSuppress**.
    4. Nel campo **Etichetta**, immettere **Sopprimere la sezione di riepilogo**.
    5. Nel campo **Nome del tipo di dati delle operazioni**, selezionare o immettere **NoYes**.
    6. Selezionare **OK**.

7. Aggiungere una nuova origine dati di tipo enumerazione applicazione **NoYes**:

    1. Selezionare **Aggiungi radice**.
    2. Nella finestra di dialogo **Aggiungi origine dati**, selezionare **Dynamics 365 for Operations\Enumerazione** per aprire la finestra di dialogo **Proprietà origine dati "Enumerazione"**.
    3. Nel campo **Nome** immettere **enumNoYes**.
    4. Nel campo **Etichetta**, immettere **Opzioni di soppressione**.
    5. Nel campo **Nome del tipo di dati delle operazioni**, selezionare o immettere **NoYes**.
    6. Selezionare **OK**.

8. Per l'elemento di formato **SummaryLines** selezionato, configurare la formula per specificare quando il controllo del contenuto di Word associato all'elemento di formato selezionato deve essere soppresso:

    1. Nella scheda **Mapping**, nella sezione **Rimosso**, selezionare **Modifica** per aprire la pagina **[Designer formula](general-electronic-reporting-formula-designer.md)**.
    2. Nel campo **Formula**, immettere la formula `uipSuppress = enumNoYes.Yes`.
    3. Selezionare **Salva** e chiudere la pagina **Designer formula**.

        > [!NOTE]
        > Questa formula verrà applicata a un documento generato **dopo l'esecuzione di tutti gli altri elementi di formato**. Per applicare questa formula, un controllo del contenuto di Word contrassegnato come elemento di formato per cui la formula è configurata (**SummaryLines** in questo caso) si trova in un documento generato. Quel controllo del contenuto viene quindi completamente rimosso, insieme alla riga nella tabella di Word che lo contiene. La riga dei dettagli della sezione di riepilogo viene rimossa dal documento generato.
        >
        > In fase di progettazione, si potrebbe configurare la formula **Rimosso** per un elemento di formato, anche se nessun controllo del contenuto nel modello di Word che si sta utilizzando ha un tag che corrisponde al nome di un elemento di formato per cui la proprietà **Rimosso** è configurata. Quando si convalida il formato in fase di progettazione, viene visualizzato un [avviso](er-components-inspections.md#i14) su questa incoerenza.
        >
        > In fase di runtime, viene generata un'eccezione se nessun controllo del contenuto nel modello di Word che si sta utilizzando ha un tag che corrisponde al nome di un elemento di formato per cui la proprietà **Rimosso** è configurata.

    4. Nella scheda **Mapping**, nella sezione **Rimosso**, impostare l'opzione **Con padre** su **Sì**.

        > [!NOTE]
        > È necessario impostare questa opzione su **Sì** per rimuovere l'intera tabella di Word come oggetto padre della riga che contiene i dettagli della sezione di riepilogo. Se si imposta questa opzione su **No**, la riga di intestazione della sezione rimane nel documento generato.

9. Selezionare **Salva** per salvare le modifiche al formato modificabile.

    ![Output generato in formato Word.](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>Eseguire il formato modificato per creare l'output di Word

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti**.
2. Selezionare il giornale di registrazione pagamenti creato, quindi selezionare **Righe**.
3. Nella pagina **Pagamenti fornitore**, selezionare tutte le righe, quindi selezionare **Stato pagamenti** \> **Nessuno**.
4. Selezionare **Genera pagamenti**.
5. Nel campo **Metodo di pagamento** seleziona **Elettronico**.
6. Nel campo **Conto bancario** selezionare **GBSI OPER**.
7. Selezionare **OK**.
8. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, nel campo **Sopprimi sezione di riepilogo**, selezionare **Sì**.
9. Selezionare **OK** e analizzare l'output generato.

    ![Output generato in formato Word.](./media/er-design-configuration-word-suppress-controls-image4.gif)

    Si noti che l'output non contiene la sezione di riepilogo poiché è stata soppressa.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Progettare una configurazione per la creazione di report nel formato OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Progettare una configurazione per la generazione di report in formato Word](er-design-configuration-word.md)
- [Riutilizzare le configurazioni per la creazione di report elettronici con modelli di Excel per generare report in formato Word](./tasks/er-design-configuration-word-2016-11.md)
- [Ispezionare il componente ER configurato per evitare problemi di runtime](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]