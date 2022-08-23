---
title: Riutilizzare le configurazioni ER con i modelli Escel per generare report nel formato Word
description: In questo articolo viene descritto come i formati di report progettati per generare report come cartelle di lavoro di Excel possono essere configurati per generare report come documenti Word.
author: kfend
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
ms.openlocfilehash: eea037751bc7ae4cb5e45fcaa0166d1f2f0b8292
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291176"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>Riutilizzare le configurazioni ER con i modelli Escel per generare report nel formato Word

[!include [banner](../../includes/banner.md)]

Per generare report come documenti di Microsoft Word, puoi [configurare](../er-design-configuration-word.md) un nuovo formato di [Creazione di report elettronici (ER)](../general-electronic-reporting.md). In alternativa, puoi riutilizzare un formato ER originariamente progettato per generare report come cartelle di lavoro di Excel. In questo caso, è necessario sostituire il modello Excel con un modello Word.

Le procedure seguenti mostrano come un utente con il ruolo di amministratore di sistema o il ruolo di sviluppatore per la creazione di report elettronici può configurare un formato ER per generare report come file Word riutilizzando un formato ER progettato per generare report come file Excel.

Queste procedure possono essere completate nella società GBSI.

## <a name="prerequisites"></a>Prerequisiti

Per completare queste procedure, è innanzitutto necessario seguire i passaggi nella guida attività [Progettare una configurazione per la creazione di report nel formato OPENXML](er-design-reports-openxml-2016-11.md).

È inoltre necessario scaricare e salvare i seguenti modelli localmente per il report di esempio:

- [Modello di Report di pagamento (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Modello associato di Report di pagamento (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

Queste procedure riguardano una funzionalità aggiunta in Dynamics 365 for Operations versione 1611 (novembre 2016).

## <a name="select-the-existing-er-report-configuration"></a>Selezionare la configurazione esistente del report ER

1. In Dynamics 365 Finance, vai ad **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Assicurarsi che il provider di configurazione **Litware, Inc.** sia selezionato come **attivo**. In caso contrario, segui i passaggi nella guida attività [Creare fornitori di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).
3. Selezionare **Configurazioni report**. Verrà riutilizzata la configurazione ER esistente progettata per generare l'output del report in formato OPENXML.
4. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **Report foglio di lavoro di esempio**.

    > [!NOTE]
    > La versione bozza del formato ER selezionato può essere modificata nella scheda dettaglio **Versioni**.

5. Selezionare **Progettazione**.
6. Nella pagina **Progettazione formati** il titolo dell'elemento di formato radice indica che un modello di Excel è attualmente utilizzato.

![Selezione della configurazione esistente.](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>Rivedere il modello di Word scaricato

1. Nell'applicazione desktop Word, apri il file del modello **SampleVendPaymDocReport.docx** scaricato in precedenza.
2. Verificare che il modello contenga solo il layout di documento che si desidera generare come output ER.

![Il layout del modello di Word nell'applicazione desktop.](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Sostituire il modello Excel con il modello Word e aggiungere una parte XML personalizzata

Attualmente, il documento di Excel viene utilizzato come modello per generare l'output nel formato OPENXML. Questo modello verrà sostituito con il file modello di Word SampleVendPaymDocReport.docx caricato in precedenza. Il modello di Word verrà inoltre esteso aggiungendo una parte XML personalizzata.

1. In Finance, nella pagina **Progettazione formati**, nella scheda **Formato** selezionare **Allegati**.
2. Nella pagina **Allegati**, selezionare **Elimina** per rimuovere il modello Excel esistente. Selezionare **Sì** per confermare la modifica.
3. Seleziona **Nuovo** \> **File**.

    > [!NOTE]
    > È necessario selezionare un tipo di documento [configurato](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nei parametri ER per archiviare i modelli dei formati ER.

4. Selezionare **Sfoglia**, quindi individuare e selezionare il file **SampleVendPaymDocReport.docx** scaricato in precedenza.
5. Selezionare **OK**.
6. Chiudere la pagina **Allegati**.
7. Nella pagina **Progettazione formati**, nel campo **Modello**, immetti o seleziona il file **SampleVendPaymDocReport.docx** per utilizzare quel modello di Word invece del modello di Excel utilizzato in precedenza.
8. Selezionare **Salva**.

    Oltre ad archiviare le modifiche apportate alla configurazione, l'azione **Salva** aggiorna anche il modello di Word associato. La struttura gerarchica del formato progettato viene aggiunta al documento Word associato come nuova parte XML personalizzata con il nome **Report**. Il modello di Word associato contiene il layout del documento che verrà generato come output ER e la struttura dei dati che ER inserisce nel modello in fase di esecuzione.

9. Il titolo dell'elemento di formato radice indica che un modello di Word è attualmente utilizzato.

    ![Sostituzione del modello Excel con il modello Word e aggiunta di una parte XML personalizzata.](../media/er-design-configuration-word-2016-11-image03.gif)

10. Nella scheda **Formato**, selezionare **Allegati**.

È possibile eseguire ora il mapping degli elementi della parte XML personalizzata **Report** ai controlli di contenuto del documento Word.

Se hai dimestichezza con il processo di progettazione dei documenti Word in formati che contengono [controli di contenuto](/office/client-developer/word/content-controls-in-word) mappati agli elementi di [parti XML personalizzate](/visualstudio/vsto/custom-xml-parts-overview), completa tutti i passaggi della procedura successiva per creare il documento. Per ulteriori informazioni, vedere [Creare moduli che gli utenti completano o stampano in Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b). In caso contrario, ignora la procedura successiva.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>Ottenere un documento di Word che abbia una parte XML personalizzata ed eseguire il mapping dei dati

1. In Finance, nella pagina **Allegati**, selezionare **Apri** per scaricare il modello selezionato da Finance e archiviarlo localmente come documento Word.
3. Nell'applicazione desktop di Word, apri il documento che hai appena scaricato.
4. Nella scheda **Sviluppatore**, seleziona **Riquadro di mapping XML**.

    > [!NOTE]
    > Se la scheda **Sviluppatore** non viene visualizzata sulla barra multifunzione, personalizzare la barra multifunzione per aggiungerla.

5. Nel riquadro **Mapping XML**, nel campo **Parte XML personalizzata** selezionare la parte XML personalizzata **Report**.
6. Eseguire il mapping degli elementi della parte XML personalizzata **Report** selezionata ai controlli di contenuto del documento Word.
7. Salvare localmente il documento Word aggiornato come **SampleVendPaymDocReportBounded.docx**.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Rivedere il modello di Word in cui la parte XML personalizzata è mappata ai controlli del contenuto

1. Nell'applicazione desktop Word, aprire il file del modello **SampleVendPaymDocReportBounded.docx**.
2. Verificare che il modello contenga il layout di documento che si desidera generare come output ER. I controlli del contenuto utilizzati come segnaposto per i dati che ER inserirà in questo modello in fase di esecuzione si basano sui mapping configurati tra gli elementi della parte XML personalizzata **Report** e i controlli del contenuto del documento di Word.

![Anteprima del modello di Word nell'applicazione desktop.](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Caricare il modello di Word in cui la parte XML personalizzata è mappata ai controlli del contenuto

1. In Finance, nella pagina **Allegati**, selezionare **Elimina** per rimuovere il modello di Word che non ha mapping tra gli elementi della parte XML personalizzata **Report** e i controlli del contenuto. Selezionare **Sì** per confermare la modifica.
2. Selezionare **Nuovo** \> **File** per aggiungere un nuovo file modello che contiene i mapping tra gli elementi della parte XML personalizzata **Report** e i controlli del contenuto.

    > [!NOTE]
    > È necessario selezionare un tipo di documento [configurato](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nei parametri ER per archiviare i modelli dei formati ER.

3. Selezionare **Sfoglia**, quindi individuare e selezionare il file **SampleVendPaymDocReportBounded.docx** che hai scaricato o preparato completando la procedura nella sezione [Ottenere un documento di Word che abbia una parte XML personalizzata ed eseguire il mapping dei dati](#get-word-doc).
4. Selezionare **OK**.
5. Chiudere la pagina **Allegati**.
6. Nella pagina **Progettazione formati** nel campo **Modello** selezionare il documento appena scaricato.
7. Selezionare **Salva**.
8. Chiudere la pagina **Progettazione formati**.

## <a name="mark-the-configured-format-as-runnable"></a>Contrassegnare il formato configurato come eseguibile

Per eseguire la versione bozza del formato modificabile, è necessario renderla [eseguibile](../er-quick-start2-customize-report.md#MarkFormatRunnable).

1. In Finance, nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
2. Nella finestra di dialogo **Parametri utente**, imposta l'opzione **Esegui impostazioni** su **Sì**, quindi seleziona **OK**.
3. Seleziona **Modifica** per rendere la pagina modificabile come richiesto.
4. Per la configurazione **Report foglio di lavoro di esempio** attualmente selezionata, imposta l'opzione **Esegui bozza** su **Sì**.
5. Selezionare **Salva**.

## <a name="run-the-format-to-create-output-in-word-format"></a>Eseguire il formato per creare l'output in formato Word

1. In Finance, andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti**.
2. In un giornale di registrazione pagamenti immesso in precedenza, selezionare **Righe**.
3. Nella pagina **Pagamenti fornitore**, seleziona tutte le righe nella griglia.
4. Selezionare **Stato del pagamento** \> **Nessuno**.

    ![Pagamenti per l'elaborazione nella pagina Pagamenti fornitore.](../media/er-design-configuration-word-2016-11-image05.png)

5. Nel riquadro azioni, seleziona **Genera pagamenti**.
6. Nella finestra di dialogo che viene visualizzata, effettuare le seguenti operazioni:

    1. Nel campo **Metodo di pagamento** seleziona **Elettronico**.
    2. Nel campo **Conto bancario** selezionare **GBSI OPER**.
    3. Selezionare **OK**.

7. Nella finestra di dialogo **Parametri per la creazione di report elettronici** selezionare **OK**.
8. L'output generato viene visualizzato nel formato di Word e contiene i dettagli dei pagamenti elaborati. Analizzare l'output generato.

    ![Output generato in formato Word.](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Progettare una configurazione per la generazione di report in formato Word](../er-design-configuration-word.md)
- [Incorporare immagini e forme nei documenti generati utilizzando ER](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
