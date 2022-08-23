---
title: Progettare un formato ER per impaginare i documenti generati in Excel
description: In questo articolo viene illustrato come progettare un formato di report elettronico (ER) per impaginare un documento generato in Microsoft Excel.
author: kfend
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.form: EROperationDesigner
ms.openlocfilehash: e4a34dffda9e9b95f5d6c7ee382723663817ec6b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285003"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>Progettare un formato ER per impaginare i documenti generati in Excel

[!include [banner](../includes/banner.md)]

Questo articolo spiega come un utente con il ruolo di Amministratore di sistema o Consulente funzionale per la creazione di report elettronici può configurare un formato per la [creazione di report elettronici (ER)](general-electronic-reporting.md) per generare documenti in uscita in Microsoft Excel e gestire l'impaginazione dei documenti.

In questo esempio, modificherai il formato ER fornito da Microsoft utilizzato per stampare il report di controllo quando la dichiarazione Intrastat è [generata](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md). Questo report consente di osservare le transazioni Intrastat dichiarate. Le modifiche ti permetteranno di gestire l'impaginazione dei report di controllo che vengono generati.

Le procedure in questo articolo possono essere completate nella società **DEMF**. Non è richiesta alcuna codifica. Prima di inziare scarica e salva i file seguenti.

| descrizione       | Nome file |
|-------------------|-----------| 
| Modello di report 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| Modello di report 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>Configurare il framework ER

Segui i passaggi in [Configurare il framework ER](er-quick-start2-customize-report.md#ConfigureFramework) per impostare il set minimo di parametri ER. È necessario completare questa configurazione prima di iniziare a utilizzare il framework ER per progettare una versione personalizzata di un formato ER standard.

## <a name="import-the-standard-er-format-configuration"></a>Importare la configurazione del formato ER standard

Segui i passaggi in [Importare la configurazione del formato ER standard](er-quick-start2-customize-report.md#ImportERSolution1) per aggiungere le configurazioni ER standard alla tua attuale istanza di Dynamics 365 Finance. Importa la versione **1.9** della configurazione del formato **report Intrastat**. La versione di base 1 della configurazione di base del **Modello Intrastat** viene importata automaticamente dal repository.

## <a name="customize-the-standard-er-format"></a>Personalizzare il formato ER standard

### <a name="create-the-custom-er-format"></a>Creare il formato ER personalizzato

In questo scenario, sei il rappresentante di Litware, Inc., attualmente selezionato come provider di configurazione ER attivo. Devi creare una nuova configurazione del formato ER utilizzando la configurazione **report Intrastat** come base.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello Intrastat**, quindi seleziona **Report Intrastat**. Litware, Inc. utilizzerà la versione 1.9 di questa configurazione del formato ER come base per la versione personalizzata.
3. Seleziona **Crea configurazione** per aprire la finestra di dialogo a discesa. Puoi utilizzare questa finestra di dialogo per creare una nuova configurazione per un formato di pagamento personalizzato.
4. Nel gruppo di campi **Nuovo**, selezionare l'opzione **Deriva da nome: report Intrastat, Microsoft**.
5. Nel campo **Nome**, immettere **Report Intrastat Litware**.
6. Seleziona **Crea configurazione** per creare il nuovo formato.

Viene creata la versione 1.9.1 della configurazione del formato ER **Report Intrastat Litware**. Questa versione ha lo stato **Bozza** e può essere modificata. Il contenuto corrente del tuo formato ER personalizzato corrisponde al contenuto del formato fornito da Microsoft.

### <a name="make-the-custom-format-runnable"></a>Contrassegnare il formato personalizzato come eseguibile

Ora che la prima versione del tuo formato personalizzato è stata creata e ha uno stato di **Bozza**, puoi eseguire il formato a scopo di test. Per eseguire il report, elaborare un pagamento fornitore utilizzando il metodo di pagamento che fa riferimento al formato ER personalizzato. Per impostazione predefinita, quando chiami un formato ER dall'applicazione, solo le versioni che hanno lo stato **Completata** o **Condivisa** vengono prese in considerazione. Questo comportamento consente di impedire l'utilizzo di formati ER con progettazioni incomplete. Tuttavia, per le esecuzioni di test, è possibile forzare l'applicazione a utilizzare la versione del formato ER con uno stato di **Bozza**. In questo modo, è possibile regolare la versione del formato corrente se sono necessarie modifiche. Per ulteriori informazioni, vedi [Applicabilità](electronic-reporting-destinations.md#applicability).

Per utilizzare la versione bozza di un formato ER, è necessario contrassegnare esplicitamente il formato ER.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, imposta l'opzione **Esegui impostazioni** su **Sì**, quindi seleziona **OK**.
4. Seleziona **Modifica** per rendere la pagina modificabile come richiesto.
5. Nell'albero di configurazione nel riquadro sinistro, seleziona **Report Intrastat Litware**.
6. Imposta l'opzione **Esegui bozza** su **Sì**, quindi seleziona **Salva**.

    ![Opzione Esegui bozza nella pagina Configurazioni.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>Impostare i parametri del commercio estero per utilizzare il formato ER personalizzato

Segui questi passaggi per configurare i parametri del commercio estero in modo da poter utilizzare il formato personalizzato.

1. Vai a **Imposta** \> **Impostazione** \> **Commercio estero** \> **Parametri per il commercio estero**.
2. Nella pagina **Parametri per il commercio estero** nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file**, seleziona **Report Intrastat Litware**.
3. Nel campo **Mapping di formato report** seleziona **Report Intrastat Litware**.
4. Selezionare **Salva**.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>Configurare il formato personalizzato per utilizzare il modello di report scaricato

### <a name="review-the-first-downloaded-excel-template"></a>Rivedere il primo modello Excel scaricato

1. Nell'applicazione desktop Excel, apri il file del modello **ERIntrastatReportDemo1.xlsx** scaricato in precedenza.
2. Verifica che il modello contenga intervalli denominati per creare l'intestazione del report, i dettagli del report e le sezioni del piè di pagina del report nei documenti generati.

    ![Il layout del modello di Excel 1 nell'applicazione desktop.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>Sostituire il modello di Excel corrente nel formato ER personalizzato

È necessario aggiungere un nuovo modello di Excel al formato ER personalizzato.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello Intrastat** \> **Report Intrastat**, quindi seleziona la configurazione **Report Intrastat Litware**.
3. Selezionare **Progettazione**.
4. Nella pagina **Progettazione formati**, nel riquadro azioni, selezionare **Mostra dettagli**.
5. Assicurati che il componente del formato radice **Intrastat: Excel** sia selezionato, quindi, nel riquadro azioni, nella scheda **Importa** nel gruppo **Importa** seleziona **Aggiorna da Excel**.
6. Nella finestra di dialogo **Aggiorna da Excel** seleziona **Aggiorna modello**.
7. Nella finestra di dialogo **Apri** cerca o seleziona il file **ERIntrastatReportDemo1.xlsx** scaricato prima, quindi seleziona **Apri**.
8. Selezionare **OK**.
9. Selezionare **Salva**.

![Struttura del formato nella finestra di progettazione del formato ER dopo l'aggiunta del nuovo modello di Excel.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>Modificare l'associazione dati per mostrare la descrizione dell'articolo su un report generato

1. Nella pagina **Progettazione formati** selezionare la scheda **Mapping**.
2. Espandi **Intrastat** \> **Righe del report** e seleziona il componente **Codice voce doganale**.
3. Selezionare **Modifica formula**.
4. Cambia la formula di associazione da `@.CommodityCode` a `CONCATENATE(@.CommodityCode, " ", @.ProductName)`.
5. Selezionare **Salva**.

![Associazione configurata per mostrare la descrizione dell'elemento nella finestra di progettazione del formato ER.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Generare un report di controllo dichiarazione Intrastat

Innanzitutto, assicurati di disporre di transazioni Intrastat per la creazione di report nella pagina **Intrastat**.

![Le transazioni nella pagina Intrastat.](./media/er-paginate-excel-reports-transactions1.gif)

Utilizza quindi il formato ER personalizzato per generare il report di controllo della dichiarazione Intrastat.

1. Vai a **Imposta** \> **Dichiarazioni** \> **Commercio estero** \> **Intrastat**.
2. Nella pagina **Intrastat** nel riquadro azioni, seleziona **Output** \> **Report**.
3. Nella finestra di dialogo **Report Intrastat** segui questi passaggi per eseguire il report:

    1. Imposta i campi **Data iniziale** e **Data finale** per includere specifiche transazioni Intrastat nel report.
    2. Imposta l'opzione **Genera file** su **No**.
    3. Imposta l'opzione **Genera report** su **Sì**.
    4. Selezionare **OK**.

4. Scarica e salva il documento che viene generato.
5. Apri il documento in Excel ed esaminalo.

    ![Documento Excel generato nell'applicazione desktop.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>Configurare il formato personalizzato per impaginare i documenti generati

### <a name="review-the-second-downloaded-excel-template"></a>Rivedere il secondo modello Excel scaricato

1. In Excel, apri il file del modello **ERIntrastatReportDemo2.xlsx** scaricato in precedenza.
2. Confronta questo modello con il modello **ERIIntrastatReportDemo1.xlsx** e verifica che contenga diversi nuovi nomi di Excel per creare e compilare sezioni specifiche della pagina nei documenti generati:

    - L'intervallo **ReportPageHeader** viene aggiunto per creare le intestazioni di pagina.
    - L'intervallo **ReportPageFooter** viene aggiunto per creare i piè di pagina.
    - La cella **ReportPageFooter\_PageLines** è configurata per mostrare il numero di transazioni per pagina.
    - La cella **ReportPageFooter\_PageAmount** è configurata per mostrare il numero totale di transazioni per pagina.
    - La cella **ReportPageFooter\_PageWeight** è configurata per mostrare il peso totale di transazioni per pagina.
    - La cella **ReportPageFooter\_Running CounterLines** è configurata per mostrare il contatore parziale delle transazioni dall'inizio del report tramite la pagina corrente.
    - La cella **ReportPageFooter\_RunningTotalAmount** è configurata per mostrare il numero totale di tutte le transazioni dall'inizio del report tramite la pagina corrente.
    - La cella **ReportPageFooter\_RunningTotalWeight** è configurata per mostrare il peso totale di tutte le transazioni dall'inizio del report tramite la pagina corrente.

    ![Il layout del modello di Excel 2 nell'applicazione desktop.](./media/er-paginate-excel-reports-template2a.gif)

    La cella **CommodityCode** di questo modello è configurata per portare a capo il testo della cella. Poiché la riga dei dettagli della transazione è configurata in modo da adattarsi automaticamente all'altezza di una riga, l'altezza dell'intera riga deve cambiare automaticamente quando il testo nella cella **CommodityCode** è riportato a capo.

    ![Cella CommodityCode configurata per il ritorno a capo del testo della cella.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>Ripetere la sostituzione del modello di Excel corrente nel formato ER personalizzato

1. Segui i passaggi nella sezione [Sostituire il modello di Excel corrente nel formato ER personalizzato](#replace-template) di questo articolo. Tuttavia, al passaggio 7, seleziona il file **ERIIntrastatReportDemo2.xlsx**.
2. Nella pagina **Progettazione formati**, espandi **Intrastat**.
3. Denomina i componenti del formato [intervallo](er-fillable-excel.md#range-component) che sono stati aggiunti al formato ER modificabile per sincronizzare la struttura con la struttura del modello Excel applicato:

    1. Seleziona il componente **Intervallo** associato al nome Excel **ReportPageHeader**.
    2. Nella scheda **Formato** nel campo **Nome** immetti **Intestazione pagina report**.
    3. Seleziona il componente **Intervallo** associato al nome Excel **ReportPageFooter**.
    4. Nella scheda **Formato** nel campo **Nome** immetti **Piè di pagina report**.

4. Selezionare **Salva**.

![Struttura del formato nella finestra di progettazione del formato ER dopo la sostituzione del modello di Excel.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>Modificare la struttura del formato per implementare l'impaginazione del documento

1. Nella pagina **Progettazione formato** nell'albero dei formati nel riquadro di sinistra, seleziona il componente radice **Intrastat**.
2. Seleziona **Aggiungi**.
3. Nella finestra di dialogo **Aggiungi** seleziona il componente [Pagina](er-fillable-excel.md#page-component) nel gruppo **Excel** di componenti.
4. Nella finestra di dialogo **Proprietà componente**, nel campo **Nome**, immetti **Pagina report**. Selezionare **OK**.
5. Per usare il componente **Intestazione pagina report** come intestazione di pagina su ogni pagina generata, segui questi passaggi:

    1. Seleziona il componente **Intestazione pagina report** quindi seleziona **Taglia**.
    2. Seleziona il componente **Pagina report** quindi seleziona **Incolla**.
    3. Espandi **Pagina report**.
    4. Per forzare il componente **Pagina** a [tener conto di](er-fillable-excel.md#page-component-structure) questo intervallo un'intestazione di pagina, seleziona **Intestazione pagina report**, e poi, nella scheda **Formato** nel campo **Direzione replica** seleziona **Nessuna replica**.

6. Per impaginare un documento generato in modo che venga considerato il contenuto delle righe del report, attieniti alla seguente procedura:

    1. Seleziona il componente **Righe report** quindi seleziona **Taglia**.
    2. Seleziona il componente **Pagina report** quindi seleziona **Incolla**.

7. Per includere il piè di pagina del report dopo le righe del report ma prima del piè di pagina finale, attieniti alla seguente procedura:

    1. Seleziona il componente **Piè di pagina report** quindi seleziona **Taglia**.
    2. Seleziona il componente **Pagina report** quindi seleziona **Incolla**.

8. Per usare il componente **Piè di pagina report** come piè di pagina su ogni pagina generata, segui questi passaggi:

    1. Seleziona il componente **Piè di pagina report** quindi seleziona **Taglia**.
    2. Seleziona il componente **Pagina report** quindi seleziona **Incolla**.
    3. Per forzare il componente **Pagina** a [tener conto di](er-fillable-excel.md#page-component-structure) questo intervallo un piè di pagina, seleziona **Piè di pagina report**, e poi, nella scheda **Formato** nel campo **Direzione replica** seleziona **Nessuna replica**.

![Struttura del formato nella finestra di progettazione del formato ER dopo l'implementazione dell'impaginazione del documento.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>Aggiungere origini dati per calcolare i totali del piè di pagina

È necessario configurare nuove origini dati per calcolare il totale della pagina, il contatore parziale e i valori del totale parziale e per visualizzarli nella sezione piè di pagina. Ti consigliamo di utilizzare le origini dati [Raccolta dati](er-data-collection-data-sources.md) per questo scopo.

1. Nella pagina **Progettazione formati** selezionare la scheda **Mapping**.
2. Seleziona **Aggiungi radice** e quindi effettua le seguenti operazioni:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Generale** seleziona **Contenitore vuoto**.
    2. Nella finestra di dialogo **Proprietà origine dati "Contenitore vuoto"** nel campo **Nome** immetti **Totale**.
    3. Selezionare **OK**.

3. Seleziona l'origine dati **Totale** seleziona **Aggiungi**, quindi segui questi passaggi:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Generale** seleziona **Contenitore vuoto**.
    2. Nella finestra di dialogo **Proprietà origine dati "Contenitore vuoto"** nel campo **Nome** immetti **Pagina**.
    3. Selezionare **OK**.

4. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Generale** seleziona **Contenitore vuoto**.
    2. Nella finestra di dialogo **Proprietà origine dati "Contenitore vuoto"** nel campo **Nome** immetti **Parziale**.
    3. Selezionare **OK**.

5. Seleziona l'origine dati **Total.Page** seleziona **Aggiungi**, quindi segui questi passaggi:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Funzioni** seleziona **Raccolta dati**.
    2. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"** nel campo **Nome** immetti **Importo**.
    3. Nel campo **Tipo di articolo** selezionare **Reale**.
    4. Imposta l'opzione **Raccogli tutti i valori** su **Sì**.
    5. Selezionare **OK**.

6. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Funzioni** seleziona **Raccolta dati**.
    2. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"** nel campo **Nome** immetti **Peso**.
    3. Nel campo **Tipo di articolo** selezionare **Reale**.
    4. Imposta l'opzione **Raccogli tutti i valori** su **Sì**.
    5. Selezionare **OK**.

7. Seleziona l'origine dati **Total.Running** seleziona **Aggiungi**, quindi segui questi passaggi:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Funzioni** seleziona **Raccolta dati**.
    2. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"** nel campo **Nome** immetti **Importo**.
    3. Nel campo **Tipo di articolo** selezionare **Reale**.
    4. Imposta il campo **Raccogli tutti i valori** su **Sì**.
    5. Selezionare **OK**.

8. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Funzioni** seleziona **Raccolta dati**.
    2. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"** nel campo **Nome** immetti **Peso**.
    3. Nel campo **Tipo di articolo** selezionare **Reale**.
    4. Imposta il campo **Raccogli tutti i valori** su **Sì**.
    5. Selezionare **OK**.

9. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Funzioni** seleziona **Raccolta dati**.
    2. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"** nel campo **Nome** immetti **Righe**.
    3. Nel campo **Tipo di articolo** seleziona **Intero**.
    4. Imposta il campo **Raccogli tutti i valori** su **Sì**.
    5. Selezionare **OK**.

10. Selezionare **Salva**.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>Aggiungere origini dati per controllare la visibilità del piè di pagina

Se prevedi di controllare la visibilità del piè di pagina e non pensi di includere il piè di pagina nella pagina finale se contiene transazioni, configura una nuova origine dati per calcolare il contatore attivo richiesto.

1. Nella pagina **Progettazione formati** selezionare la scheda **Mapping**.
2. Seleziona l'origine dati **Total.Running** e seleziona **Aggiungi**.
3. Nella finestra di dialogo **Aggiungi origine dati** nella sezione **Funzioni** seleziona **Raccolta dati**.
4. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"** nel campo **Nome** immetti **Righe2**.
5. Nel campo **Tipo di articolo** seleziona **Intero**.
6. Imposta l'opzione **Raccogli tutti i valori** su **Sì**.
7. Selezionare **OK**.
8. Selezionare **Salva**.

![Origini dati aggiunte nella finestra di progettazione del formato ER.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>Configurare le associazioni per raccogliere i valori totali

1. Nella pagina **Progettazione formati**, nell'albero dei formati, espandi il componente **Righe report** e seleziona il componente nidificato **Valore fattura**.
2. Selezionare **Modifica formula**.
3. Cambia la formula di associazione da `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` a `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`.

    > [!NOTE]
    > Oltre a inserire il valore dell'importo in una cella di Excel per ogni transazione iterata, questa associazione raccoglie il valore nell'origine dati **Total.Page.Amount** della raccolta dati.

4. Seleziona il componente nidificato **Peso**.
5. Selezionare **Modifica formula**.
6. Cambia la formula di associazione da `@.'$RoundedWeight'` a `Total.Page.Weight.Collect(@.'$RoundedWeight')`.

    > [!NOTE]
    > Oltre a inserire il valore del peso in una cella di Excel per ogni transazione iterata, questa associazione raccoglie il valore nell'origine dati **Total.Page.Weight**.

![Associazioni configurate per la raccolta dei valori totali nella finestra di progettazione del formato ER.](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>Configurare le associazioni per compilare i totali del piè di pagina

1. Nella pagina **Progettazione formati** nell'albero dei formati, espandi il componente **Piè di pagina report** seleziona il componente nidificato **Intervallo** che fa riferimento alla cella di Excel **ReportPageFooter\_PageAmount**, quindi segui questi passaggi:

    1. Nell'albero delle origini dati nel riquadro di destra, seleziona l'elemento **Total.Page.Amount.Sum()**.
    2. Selezionare **Associa**.
    3. Selezionare **Modifica formula**.
    4. Aggiorna la formula a `Total.Page.Amount.Sum(false)`.

    > [!NOTE]
    > Devi specificare l'argomento di questa funzione come **Falso** per conservare i dati raccolti per la pagina corrente, poiché questi dati sono necessari per calcolare l'importo totale parziale delle righe, il numero totale di righe per pagina e il contatore parziale delle righe.

2. Nell'albero del formato, seleziona il componente nidificato **Intervallo** che fa riferimento alla cella di Excel **ReportPageFooter\_PageWeight**, quindi segui questi passaggi:

    1. Nell'albero delle origini dati nel riquadro di destra, seleziona l'elemento **Total.Page.Weight.Sum()**.
    2. Selezionare **Associa**.
    3. Selezionare **Modifica formula**.
    4. Aggiorna la formula a `Total.Page.Weight.Sum(false)`.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>Configurare le associazioni per compilare i totali parziali della pagina

1. Nella pagina **Progettazione formati** nell'albero dei formati, espandi il componente **Piè di pagina report** seleziona il componente nidificato **Intervallo** che fa riferimento alla cella di Excel **ReportPageFooter\_RunningTotalAmount**, quindi segui questi passaggi:

    1. Nell'albero delle origini dati nel riquadro di destra, seleziona l'elemento **Total.Running.Amount.Collect()**.
    2. Selezionare **Associa**.
    3. Selezionare **Modifica formula**.
    4. Aggiorna la formula a `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`.

    > [!NOTE]
    > L'operando `Total.Running.Amount.Sum(false)` restituisce il totale parziale dell'importo precedentemente raccolto. L'operando `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` restituisce l'importo totale della pagina corrente. Devi specificare l'argomento della funzione annidata del secondo operando come **Vero** per reimpostare la raccolta dati `Total.Page.Amount` non appena questo valore viene inserito nella raccolta totale parziale `Total.Running.Amount`. L'argomento specificato deve iniziare a raccogliere il totale della pagina successiva dal valore 0 (zero).
    >
    > La funzione `Total.Running.Amount.Sum(false)` viene chiamata per inserire l'importo totale parziale nella cella di Excel **ReportPageFooter\_RunningTotalAmount** nella pagina corrente.

2. Nell'albero del formato, seleziona il componente nidificato **Intervallo** che fa riferimento alla cella di Excel **ReportPageFooter\_RunningTotalWeight**, quindi segui questi passaggi:

    1. Nell'albero delle origini dati nel riquadro di destra, seleziona l'elemento **Total.Running.Weight.Collect()**.
    2. Selezionare **Associa**.
    3. Selezionare **Modifica formula**.
    4. Aggiorna la formula a `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>Configurare le associazioni per compilare il contatore parziale della pagina

1. Nella pagina **Progettazione formati** nell'albero dei formati, espandi il componente **Piè di pagina report** seleziona il componente nidificato **Intervallo** che fa riferimento alla cella di Excel **ReportPageFooter\_RunningCounterLines**.
2. Selezionare **Modifica formula**.
3. Aggiungi la formula `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`.

    > [!NOTE]
    > Questa formula restituisce il numero di valori degli importi raccolti per l'intero report. Questo numero è uguale al numero di transazioni che sono state iterate al momento corrente. Allo stesso tempo, la formula raccoglie il valore restituito nella raccolta **Total.Running.Lines**.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>Configurare le associazioni per compilare il contatore piè di pagina

1. Nella pagina **Progettazione formati** nell'albero dei formati, espandi il componente **Piè di pagina report** seleziona il componente nidificato **Intervallo** che fa riferimento alla cella di Excel **ReportPageFooter\_PageLines**.
2. Selezionare **Modifica formula**.
3. Aggiungi la formula `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`.

    > [!NOTE]
    > Questa formula calcola il numero di transazioni sulla pagina corrente come differenza tra il numero di transazioni raccolte in **Total.Page.Amount.Result** per l'intero report e il numero di transazioni che è stato memorizzato in questa fase in **Total.Running.Lines.Sum**. Poiché il numero di transazioni per la pagina corrente è memorizzato in **Total.Running.Lines** nell'associazione del componente **Intervallo** che fa riferimento alla cella di Excel **ReportPageFooter\_RunningCounterLines**, il numero di transazioni nella pagina corrente non è ancora incluso. Pertanto, questa differenza è uguale al numero di transazioni nella pagina corrente.

![Associazioni configurate per la compilazione del contatore del piè di pagina nella finestra di progettazione del formato ER.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>Configurare la visibilità del componente

È possibile modificare la visibilità dell'intestazione e del piè di pagina su una pagina specifica di un documento generato per nascondere i seguenti elementi:

- L'intestazione della pagina nella prima pagina, perché l'intestazione del report contiene già i titoli delle colonne
- L'intestazione della pagina su qualsiasi pagina che non ha transazioni che possono verificarsi per l'ultima pagina
- Il piè di pagina su qualsiasi pagina che non ha transazioni che possono verificarsi per l'ultima pagina

Per modificare la visibilità, aggiorna la proprietà **Abilitato** dei componenti **Intestazione pagina report** e **Piè di pagina report**.

1. Nella pagina **Progettazione formati**, nell'albero dei formati, espandi il componente **Pagina report** e seleziona il componente nidificato **Intestazione pagina report** quindi segui questi passaggi:

    1. Seleziona **Modifica** per il campo **Abilitato**.
    2. Nella pagina **Designer formula** nel campo **Formula** immetti la seguente espressione:

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. Nell'albero del formato, seleziona il componente nidificato **Piè di pagina report**, quindi segui questi passaggi:

    1. Seleziona **Modifica** per il campo **Abilitato**.
    2. Nella pagina **Designer formula** nel campo **Formula** immetti la seguente espressione:

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > La costruzione `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` viene utilizzata per calcolare il numero di transazioni nella pagina corrente. La costruzione `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` viene utilizzata per aggiungere alla raccolta il numero di transazioni della pagina corrente, per gestire correttamente la visibilità del piè di pagina successivo.
    >
    > La raccolta `Total.Running.Lines` non può essere riutilizzata qui, perché la proprietà **Abilitato** di un componente di base viene elaborata **dopo** le associazioni dei componenti nidificati. Quando la proprietà **Abilitato** viene elaborata, la raccolta `Total.Running.Lines` è già incrementata del numero di transazioni nella pagina corrente.

3. Selezionare **Salva**.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Generare un report di controllo dichiarazione Intrastat (aggiornamento)

1. Assicurati di disporre di 24 transazioni nella pagina **Intrastat**. Ripeti i passaggi nella sezione [Generare un report di controllo dichiarazione Intrastat](#generate-intrastat-control-report) di questo articolo per generare e rivedere il report di controllo.

    Tutte le transazioni sono presentate nella prima pagina. I totali e i contatori della pagina corrispondono ai totali e ai contatori del report. L'intervallo dell'intestazione della pagina è nascosto nella prima pagina, perché l'intestazione del report contiene già i titoli delle colonne. L'intestazione e il piè di pagina sono nascosti nella seconda pagina perché quella pagina non contiene transazioni.

    ![Documento Excel generato nell'applicazione desktop.](./media/er-paginate-excel-reports-document2.gif)

2. Aggiorna due transazioni nella pagina **Intrastat** cambiando il codice **Numero articolo** da **D00006** a **L0010**. Nota che il nome del prodotto del nuovo articolo, **Coppia di altoparlanti stereo attivi**, è più lungo del nome del prodotto dell'articolo originale, **Altoparlante standard**. Questa situazione forza il ritorno a capo del testo nella cella corrispondente del documento generato. L'impaginazione del documento e la somma e il conteggio relativi alle pagine devono ora essere aggiornati. Ripeti i passaggi nella sezione [Generare un report di controllo dichiarazione Intrastat](#generate-intrastat-control-report) per generare e rivedere il report di controllo.

    Ora, le transazioni vengono presentate su due pagine e i totali di pagina e i contatori vengono calcolati correttamente. L'intervallo dell'intestazione della pagina è nascosto correttamente nella prima pagina e visibile nella seconda pagina. Il piè di pagina è visibile su entrambe le pagine perché contengono transazioni.

    ![Documento Excel generato aggiornato nell'applicazione desktop.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>C'è un modo per riconoscere quando la pagina finale viene elaborata dal componente Pagina?

Il componente **Pagina** [non espone](er-fillable-excel.md#page-component-limitations) informazioni sul numero della pagina elaborata e sul numero totale di pagine in un documento generato. Tuttavia, puoi configurare [formule](er-formula-language.md) ER per riconoscere la pagina finale. Ecco un esempio:

- Calcola il numero totale di transazioni che sono già state elaborate utilizzando il componente **Pagina report**. È possibile effettuare questo calcolo utilizzando la formula `COUNT(Total.Page.Amount.Result)`. 
- Calcola il numero totale di transazioni che devono essere elaborate in base all'associazione `model.CommodityRecord` configurata per il componente **Righe report**. È possibile effettuare questo calcolo utilizzando la formula `COUNT(model.CommodityRecord)`.
- Confronta due numeri per riconoscere la pagina finale. Quando entrambi i valori sono uguali, viene generata la pagina finale.

> [!NOTE]
> Si consiglia di utilizzare questo approccio solo quando la proprietà **Abilitato** del componente **Righe report** non contiene una formula che potrebbe restituire [Falso](er-formula-supported-data-types-primitive.md#boolean) in fase di esecuzione per alcuni [record](er-formula-supported-data-types-composite.md#record) iterati dell'[elenco dei record](er-formula-supported-data-types-composite.md#record-list) associato.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Progettare una configurazione per generare documenti in uscita in formato Excel](er-fillable-excel.md)
- [Utilizzare le origini dati RACCOLTA DATI nei formati per la creazione di report elettronici (ER)](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
