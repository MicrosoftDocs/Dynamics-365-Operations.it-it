---
title: Progettare un formato ER per generare un report in formato Excel con immagini incorporate nelle intestazioni o piè di pagina
description: Questo articolo spiega come usare Electronic reporting (ER) per generare documenti aziendali che hanno immagini e forme incorporate nelle intestazioni o nei piè di pagina.
author: NickSelin
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1cfde60459e440c851edb97276321216b1654e40
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854845"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>Progettare un formato ER per generare un report in formato Excel con immagini incorporate nelle intestazioni o piè di pagina

[!include[banner](../includes/banner.md)]

Questo articolo spiega come un utente con ruolo Amministratore di sistema o Consulente funzionale per Creazione di report elettronici può eseguire queste attività:

- Configurare parametri per il framework [Creazione di report elettronici (ER)](general-electronic-reporting.md).
- Importare [configurazioni](general-electronic-reporting.md#Configuration) ER [fornite](general-electronic-reporting.md#Provider) da Microsoft e utilizzate per generare [fatture a testo libero](../../../finance/accounts-receivable/create-free-text-invoice-new.md), in base a un [modello](er-fillable-excel.md#excel-file-component) in formato Microsoft Excel.
- Creare una versione [personalizzata (derivata)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) di una configurazione in formato ER standard fornita da Microsoft.
- Modificare la configurazione in formato ER personalizzato in modo che generi un report fattura a testo libero con un'immagine del logo dell'azienda nel piè di pagina.

Le procedure in questo articolo possono essere completate nella società **USMF**. Non è richiesta alcuna codifica. Prima di iniziare, scaricare e salvare il seguente file.

| descrizione        | Nome file |
|--------------------|-----------|
| Immagine del logo dell'azienda | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>Contenuto

- [Configurare la persona giuridica](#ConfigureLegalEntity)
- [Configurare il framework ER](#ConfigureFramework)

    - [Configurare i parametri ER](#ConfigureParameters)
    - [Attivare un provider di configurazioni ER](#ActivateProvider)

        - [Rivedere l'elenco dei provider di configurazione ER](#ReviewProvidersList)
        - [Aggiungere un nuovo provider di configurazione ER](#AddProvider)
        - [Attivare il nuovo provider di configurazioni ER](#ActivateAddedProvider)

- [Importare le configurazioni del formato ER standard](#ImportERSolution1)

    - [Importare le configurazioni ER standard](#ImportERFormat)
    - [Rivedere le configurazioni ER importate](#ReviewImportedERSolution)

- [Stampare una fattura a testo libero utilizzando il formato ER standard](#PrintInvoice1)

    - [Impostare la gestione stampa](#ConfigurePrintManagement1)
    - [Stampa una fattura a testo libero](#ProcessInvoice1)

- [Personalizzare il formato ER standard](#CustomizeProvidedFormat)

    - [Creare un formato personalizzato](#DeriveProvidedFormat)
    - [Modificare il formato personalizzato](#ConfigureDerivedFormat)
    - [Contrassegnare il formato personalizzato come eseguibile](#MarkFormatRunnable)

- [Stampare una fattura a testo libero utilizzando il formato ER personalizzato](#PrintInvoice2)

    - [Impostare la gestione stampa](#ConfigurePrintManagement2)
    - [Stampa una fattura a testo libero](#ProcessInvoice2)

- [Risorse aggiuntive](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>Configurare la persona giuridica

1. Andare ad **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche**.
2. Nella Scheda dettaglio **Immagine logo aziendale report** della pagina **Persone giuridiche** selezionare **Modifica**.
3. Nella finestra di dialogo **Seleziona file di immagine da caricare** selezionare **Sfoglia**, quindi selezionare **Company logo.png** scarico in precedenza.
4. Selezionare **Salva**, quindi chiudere la pagina **Persone giuridiche**.

![Immagine del logo aziendale selezionata nella pagina Persone giuridiche.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Configurare il framework ER

Come utente che dispone del ruolo di Consulente funzionale per la creazione di report elettronici, è necessario configurare il set minimo di parametri ER prima di poter iniziare a utilizzare il framework ER per progettare una versione personalizzata di un formato ER standard.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurare i parametri ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Parametri per la creazione di report elettronici**.
3. Nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
4. Nella scheda **Allegati**, imposta i seguenti parametri:

    - Nel campo **Configurazioni**, seleziona il tipo **File** per l'azienda **USMF**.
    - Nei campi **Archivio processi**, **Temporaneo**, **Base** e **Altri**, seleziona il tipo **File**.

Per ulteriori informazioni sui parametri ER, vedi [Configurare il framework ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Attivare un provider di configurazioni ER

Ogni configurazione ER aggiunta viene contrassegnata come di proprietà di un provider di configurazione ER. Il provider di configurazione ER che è attivato nell'area di lavoro **Creazione di report elettronici** viene utilizzato per questo scopo. Pertanto, è necessario attivare un provider di configurazione ER nell'area di lavoro **Creazione di report elettronici** prima di iniziare ad aggiungere o modificare le configurazioni ER.

> [!NOTE]
> Una configurazione ER può essere modificata solo dal proprietario della configurazione. Prima di poter modificare una configurazione ER, è necessario attivare il provider di configurazione ER appropriato nell'area di lavoro **Creazione di report elettronici**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Rivedere l'elenco dei provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Tabella del provider di configurazione**, ogni record del provider ha un nome e un URL univoci. Rivedi il contenuto della pagina. Se un record per **Litware, Inc.** (`https://www.litware.com`) esiste già, salta la procedura successiva, [Aggiungere un nuovo provider di configurazione ER](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Aggiungere un nuovo provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Provider di configurazione**, seleziona **Nuovo**.
4. Nel campo **Nome**, immetti **Litware, Inc.**
5. Nel campo **Indirizzo Internet** immetti `https://www.litware.com`.
6. Selezionare **Salva**.

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Attivare il nuovo provider di configurazioni ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Litware, Inc.**, quindi seleziona **Imposta attivo**.

Per ulteriori informazioni sui provider di configurazione ER, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importare le configurazioni del formato ER standard

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>Importare le configurazioni ER standard

Per aggiungere le configurazioni ER standard all'istanza corrente di Dynamics 365 Finance, è necessario importarle dal [repository](general-electronic-reporting.md#Repository) ER che era configurato per quell'istanza.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, selezionare il riquadro **Microsoft**, quindi selezionare **Archivi** per visualizzare l'elenco di repository per il provider **Microsoft**.
3. Nella pagina **Archivi di configurazione** seleziona l'archivio del tipo **Globale**, quindi seleziona **Apri**. Se viene richiesta l'autorizzazione per connettersi a [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md), seguire le istruzioni di autorizzazione.
4. Nella pagina **Archivio di configurazione**, nella struttura delle configurazioni del riquadro sinistro, seleziona la configurazione del formato **Fattura a testo libero (Excel)**.
5. Nella scheda dettaglio **Versioni** selezionare la versione più recente, ad esempio **240.112** della configurazione selezionata del formato ER.
6. Seleziona **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.

![Importazione di configurazioni ER standard nella pagina Archivio di configurazioni.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> In caso di problemi di accesso all'[archivio globale](er-download-configurations-global-repo.md), puoi invece [scaricare le configurazioni](download-electronic-reporting-configuration-lcs.md) da Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Rivedere le configurazioni ER importate

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di fattura**.
4. Oltre al formato ER **Fattura a testo libero (Excel)** selezionato, sono state importate altre configurazioni ER necessarie. Verifica che le seguenti configurazioni ER siano disponibili nella struttura di configurazione:

    - **Modello di fattura**: questa configurazione contiene il componente ER modello di dati che rappresenta la struttura dei dati del dominio aziendale di fatturazione.
    - **Mapping di modello di fattura**: questa configurazione contiene il componente ER mapping del modello che descrive in che modo il modello di dati viene compilato con i dati dell'applicazione in fase di esecuzione.
    - **Fattura a testo libero (Excel)**: questa configurazione contiene i componenti ER formato e mapping del formato. Il componente formato specifica il layout del report in base a un modello in formato Excel. Il componente di mapping del formato contiene l'origine dati del modello e specifica come questa origine dati viene usata per compilare il layout del report in fase di esecuzione.

![Configurazioni ER importate nella pagina Configurazioni.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>Stampare una fattura a testo libero utilizzando il formato ER standard

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>Impostare la gestione stampa

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Nella pagina **Fattura a testo libero** selezionare la fattura **FTI-00000002**, quindi, nel riquadro Azione della scheda **Fattura**, nel gruppo **Gestione stampa**, selezionare **Gestione stampa**.
3. Nella pagina **Impostazione Gestione stampa**, nella struttura sulla sinistra, espandere **Modulo - contabilità clienti \> Documenti \> Fattura a testo libero**, quindi selezionare l'elemento **Originale \<Default\>**.
4. Nel campo **Formato report** selezionare **Fattura a testo libero (Excel)**.
5. Selezionare **Esc** per chiudere la pagina **Impostazione Gestione stampa** e tornare alla pagina **Fattura a testo libero**.

![Impostazioni di gestione stampa per una fattura a testo libero nel formato ER standard nella pagina Impostazione Gestione stampa.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>Stampa una fattura a testo libero

1. Nella pagina **Fattura a testo libero** assicurarsi che la fattura **FTI-00000002** sia ancora selezionata, quindi, nel riquadro Azione, nella scheda **Fattura**, nel gruppo **Documento**, selezionare **Stampa** \> **Selezionato**.
2. Scaricare la fattura generata in formato Excel e aprila per l'anteprima.
3. Si noti che, in conformità alla struttura del modello Excel per il formato ER fornito, il piè di pagina della fattura generata contiene informazioni sul numero di pagina corrente e sul numero totale di pagine nel report.

![Fattura di testo libero generata.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personalizzare il formato ER standard

Per l'esempio in questa sezione, è possibile utilizzare le configurazioni ER fornite da Microsoft per generare una fattura a testo libero in formato Excel. È, tuttavia, necessario aggiungere una personalizzazione per inserire un'immagine del logo aziendale nel piè di pagina delle fatture generate.

In questo caso, il rappresentante di Litware, Inc. deve creare (derivare) una nuova configurazione del formato ER basata sulla configurazione **Fattura a testo libero (Excel)** fornita da Microsoft.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Creare un formato personalizzato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni nel riquadro sinistro, espandere **Modello di fattura**, quindi selezionare **Modello a testo libero (Excel)**. Litware, Inc. utilizzerà la versione importata, ad esempio **240.112**, di questa configurazione del formato ER come base per la versione personalizzato.
3. Seleziona **Crea configurazione** per aprire la finestra di dialogo a discesa. Utilizzare questa finestra di dialogo per creare una nuova configurazione per un formato pagamento personalizzato.
4. Nel gruppo di campi **Nuovo** selezionare l'opzione **Deriva da nome: fattura a testo libero (Excel), Microsoft**.
5. Nel campo **Nome** immettere **Fattura a testo libero (Excel) personalizzata**.
6. Selezionare **Crea configurazione**.

![Creazione di una configurazione per un formato pagamento personalizzato nella finestra di dialogo a discesa Crea configurazione.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

Viene creata la versione 240.112.1 della configurazione del formato ER **Fattura a testo libero (Excel)**. Questa versione ha uno [stato](general-electronic-reporting.md#component-versioning) di **Bozza** e può essere modificata. Il contenuto corrente del tuo formato ER personalizzato corrisponde al contenuto del formato fornito da Microsoft.

![Nuova versione della configurazione del formato ER creata nella pagina Configurazioni.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>Modificare il formato personalizzato

Configurare il formato personalizzato in modo che un'immagine del logo aziendale venga inserita nel piè di pagina di ogni pagina del report.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni nel riquadro sinistro, espandere **Modello di pagamento**, quindi selezionare **Fattura a testo libero (Excel)** personalizzata.
3. Nella scheda dettaglio **Versioni** seleziona la versione **240.112.1** della configurazione selezionata.
4. Selezionare **Progettazione**.
5. Nella pagina **Progettazione formati**, seleziona **Mostra dettagli** per visualizzare altre informazioni sugli elementi del formato.
6. Espandi e rivedi i seguenti elementi:

    - Elemento **Fattura a testo libero** del tipo **Excel**. Questo elemento viene utilizzato per generare una fattura in formato cartella di lavoro di Excel.
    - Elemento **Fattura a testo libero \\ Fattura** del tipo **Foglio**. Questo elemento viene utilizzato per generare un foglio di lavoro della cartella di lavoro Excel generata.
    - Elemento **Fattura a testo libero \\ Fattura \\ Piè di pagina** del tipo **Piè di pagina**. Questo elemento viene utilizzato per compilare un piè di pagina fattura.

7. Selezionare l'elemento **Fattura a testo libero \\ Fattura \\ Piè di pagina**.

    ![Elemento Piè di pagina nella finestra di progettazione Operazioni ER.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > Ogni piè di pagina di una fattura generata contiene informazioni sul numero di pagina corrente e sul numero totale di pagine nel report. Come si può vedere, l'elemento **Fattura a testo libero\\ Fattura \\ Piè di pagina** non contiene elementi figlio. Pertanto, il modello di Excel utilizzato viene configurato per mostrare i dettagli di paginazione al centro del piè di pagina di ogni report.

8. Seleziona **Aggiungi**, quindi seleziona il tipo **Excel \\ Immagine** dell'elemento formato che si intende aggiungere:

    1. Nel campo **Allineamento** seleziona **Destra**.
    2. Nel campo **Scala altezza** selezionare **Relativa**.
    3. Nel campo **Scala in percentuale** immettere **70**.
    4. Selezionare **OK**.

        > [!NOTE]
        > L'elemento **Excel \\ Immagine** viene utilizzato per aggiungere l'immagine del logo aziendale e di allinearlo a destra del piè di pagina.

    ![Proprietà dell'elemento Immagine nella finestra di dialogo Proprietà componente.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. Nella struttura dei formati a sinistra selezionare l'elemento **Immagine** appena aggiunto, quindi nella scheda **Mapping** espandere l'origine dei dati di **modello**.
10. Espandere **model.Payment** \> **model.InvoiceBase \> model.InvoiceBase.CompanyInfo**, quindi selezionare il campo origine dati **model.InvoiceBase.CompanyInfo.Logo**. Il campo origine dati del tipo [Contenitore](er-formula-supported-data-types-composite.md#container) espone l'immagine del logo aziendale come contenuto multimediale.
11. Selezionare **Associa**. L'elemento formato **Immagine** è ora vincolato al campo origine dati **model.InvoiceBase.CompanyInfo.Logo**. Pertanto, in fase di esecuzione, l'immagine del logo aziendale verrà inserita nel piè di pagina delle fatture generate.

    ![Elemento formato Immagine vincolato al campo origine dati model.InvoiceBase.CompanyInfo.Logo nella finestra di progettazione Operazioni ER.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. Selezionare **Salva** quindi chiudere la pagina di **progettazione**.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Contrassegnare il formato personalizzato come eseguibile

Poiché la prima versione del formato personalizzato è stata creata e presenta lo stato **Bozza**, è possibile eseguire il formato a scopo di test. Per eseguire il report, elaborare un pagamento fornitore utilizzando il metodo di pagamento che fa riferimento al formato ER personalizzato. Per impostazione predefinita, quando chiami un formato ER dall'applicazione, solo le versioni che hanno uno stato di **Completata** o **Condivisa** vengono [considerate](general-electronic-reporting.md#component-versioning). Questo comportamento consente di impedire l'utilizzo di formati ER con progettazioni incomplete. Tuttavia, per le esecuzioni di test, è possibile forzare l'applicazione a utilizzare la versione del formato ER con uno stato di **Bozza**. In questo modo, è possibile regolare la versione del formato corrente se sono necessarie modifiche. Per ulteriori informazioni, vedi [Applicabilità](electronic-reporting-destinations.md#applicability).

Per utilizzare la versione bozza di un formato ER, è necessario contrassegnare esplicitamente il formato ER.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, imposta l'opzione **Esegui impostazioni** su **Sì**, quindi seleziona **OK**.
4. Selezionare **Modifica** per rendere modificabile la pagina corrente, quindi, nell'albero di configurazione nel riquadro sinistro, selezionare **Fattura a testo libero (Excel) personalizzata**.
5. Imposta l'opzione **Esegui bozza** su **Sì**.

![Contrassegnare il formato personalizzato come eseguibile nella pagina Configurazioni.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>Stampare una fattura a testo libero utilizzando il formato ER personalizzato

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>Impostare la gestione stampa

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Nella pagina **Fattura a testo libero** selezionare la fattura **FTI-00000002**, quindi, nel riquadro Azione della scheda **Fattura**, nel gruppo **Gestione stampa**, selezionare **Gestione stampa**.
3. Nella pagina **Impostazione Gestione stampa**, nella struttura a sinistra, espandere **Modulo - contabilità clienti** \> **Documenti** \> **Fattura a testo libero**, quindi selezionare l'elemento **Originale** **\<Default\>**.
4. Nel campo **Formato report** selezionare **Fattura a testo libero (Excel)** personalizzata.
5. Selezionare **Esc** per chiudere la pagina **Impostazione Gestione stampa** e tornare alla pagina **Fattura a testo libero**.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>Stampa una fattura a testo libero

1. Nella pagina **Fattura a testo libero** assicurarsi che la fattura **FTI-00000002** sia ancora selezionata, quindi, nel riquadro Azione, nella scheda **Fattura**, nel gruppo **Documento**, selezionare **Stampa** \> **Selezionato**.
2. Scaricare la fattura generata in formato Excel e aprila per l'anteprima.
3. Si noti che, in conformità alla struttura del formato ER personalizzato, il piè di pagina della fattura generata contiene un'immagine del logo aziendale oltre alle informazioni sulla impaginazione del report.

![Fattura a testo libero generata con un'immagine del logo aziendale nel piè di pagina.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>Risorse aggiuntive

- [Progettare una configurazione per generare documenti in uscita in formato Excel](er-fillable-excel.md)
- [Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md)
