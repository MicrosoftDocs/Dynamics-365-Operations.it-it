---
title: Modificare un formato ER per generare un documento elettronico personalizzato
description: Questo argomento spiega come modificare un formato di report elettronico (ER) fornito da Microsoft in modo che generi un documento elettronico personalizzato.
author: NickSelin
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14976aab474b6571c2a25907f04fd4d7ae053e74
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323819"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>Modificare un formato ER per generare un documento elettronico personalizzato

[!include[banner](../includes/banner.md)]

Le procedure in questo argomento spiegano come un utente con il ruolo Amministratore di sistema o Consulente funzionale per la creazione di report elettronici può eseguire queste attività:

- Configura i parametri per il [framework di report elettronico](general-electronic-reporting.md).
- Importa le configurazioni di report elettronico fornite da Microsoft e utilizzate per generare un file di pagamento mentre un [pagamento del fornitore](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) è in fase di elaborazione.
- Crea una versione personalizzata di una configurazione di formato ER standard fornita da Microsoft.
- Modifica la configurazione del formato ER personalizzato in modo che generi file di pagamento che soddisfino i requisiti di una banca specifica.
- Adotta le modifiche apportate alla configurazione del formato ER standard nella configurazione del formato ER personalizzato.

Tutte le seguenti procedure possono essere eseguite nell'azienda **GBSI**. Non è richiesta alcuna codifica.

- [Configurare il framework ER](#ConfigureFramework)

    - [Configurare i parametri ER](#ConfigureParameters)
    - [Attivare un provider di configurazioni ER](#ActivateProvider)

        - [Rivedere l'elenco dei provider di configurazione ER](#ReviewProvidersList)
        - [Aggiungere un nuovo provider di configurazione ER](#ActivateProvider)
        - [Attivare un provider di configurazioni ER](#ActivateAddedProvider)

- [Importare le configurazioni del formato ER standard](#ImportERSolution1)

    - [Importare le configurazioni ER standard](#ImportERFormat1)
    - [Rivedere le configurazioni ER importate](#ReviewImportedERSolution)

- [Preparare un pagamento fornitore per l'elaborazione](#PrepareVendorPayment)

    - [Aggiungere le informazioni bancarie per un conto fornitore](#AddBankAccount)
    - [Immettere un pagamento fornitore](#EnterVendorPayment)

- [Elaborare un pagamento fornitore utilizzando il formato ER standard](#ProcessVendorPayment1)

    - [Configurare il metodo di pagamento elettronico](#ConfigureMethodOfPayment1)
    - [Elaborare un pagamento fornitore](#ProcessPayment1)

- [Personalizzare il formato ER standard](#CustomizeProvidedFormat)

    - [Creare un formato personalizzato](#DeriveProvidedFormat)
    - [Modificare un formato personalizzato](#ConfigureDerivedFormat)
    - [Contrassegnare un formato personalizzato come eseguibile](#MarkFormatRunnable)

- [Elaborare un pagamento fornitore utilizzando il formato ER personalizzato](#ProcessVendorPayment2)

    - [Configurare il metodo di pagamento elettronico](#ConfigureMethodOfPayment2)
    - [Elaborare un pagamento fornitore](#ProcessPayment2)

- [Importare nuove versioni delle configurazioni del formato ER standard](#ImportERSolution2)

    - [Importare nuove versioni delle configurazioni ER standard](#ImportERFormat2)
    - [Rivedere le configurazioni del formato ER importate](#ReviewImportedERFormat)

- [Adottare le modifiche nella nuova versione di un formato importato in un formato personalizzato](#AdoptNewBaseVersion)

    - [Completare la versione in bozza corrente di un formato personalizzato](#CompleteDerivedFormat)
    - [Riassegnare un formato personalizzato su una nuova versione di base](#RebaseDerivedFormat)
    - [Elaborare un pagamento fornitore utilizzando un formato ER riassegnato](#ProcessPayment3)

- [Risorse aggiuntive](#References)

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
> Solo il proprietario di una configurazione ER può modificarla. Pertanto, prima di poter modificare una configurazione ER, è necessario attivare il provider di configurazione ER appropriato nell'area di lavoro **Creazione di report elettronici**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Rivedere l'elenco dei provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Tabella del provider di configurazione**, ogni record del provider ha un nome e un URL univoci. Rivedi il contenuto della pagina. Se un record per **Litware, Inc.** (`https://www.litware.com`) esiste già, salta la procedura successiva, [Aggiungere un nuovo provider di configurazione ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Aggiungere un nuovo provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Provider di configurazione**, seleziona **Nuovo**.
4. Nel campo **Nome**, immetti **Litware, Inc.**
5. Nel campo **Indirizzo Internet** immetti `https://www.litware.com`.
6. Selezionare **Salva**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Attivare un provider di configurazioni ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Litware, Inc.**, quindi seleziona **Imposta attivo**.

Per ulteriori informazioni sui provider di configurazione ER, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importare le configurazioni del formato ER standard

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>Importare le configurazioni ER standard

Per aggiungere le configurazioni ER standard all'istanza corrente di Microsoft Dynamics 365 Finance, è necessario importarle dall'[archivio](general-electronic-reporting.md#Repository) ER che era configurato per quell'istanza.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**, quindi seleziona **Archivi** per visualizzare l'elenco dei repository per il provider Microsoft.
3. Nella pagina **Archivi di configurazione** seleziona l'archivio del tipo **Globale**, quindi seleziona **Apri**. Se viene richiesta l'autorizzazione per connettersi a Regulatory Configuration Service, segui le istruzioni di autorizzazione.
4. Nella pagina **Archivio di configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona la configurazione del formato **BACS (Regno Unito)**.
5. Nella scheda dettaglio **Versioni** seleziona la versione **1.1** della configurazione del formato ER selezionata.
6. Seleziona **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.

![Pagina Archivio di configurazione.](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> In caso di problemi di accesso all'[archivio globale](er-download-configurations-global-repo.md), puoi invece [scaricare le configurazioni](download-electronic-reporting-configuration-lcs.md) da Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Rivedere le configurazioni ER importate

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**.
4. Si noti che, oltre al formato ER **BACS (Regno Unito)** selezionato, sono state importate altre configurazioni ER necessarie. Verifica che le seguenti configurazioni ER siano disponibili nella struttura di configurazione:

    - **Modello di pagamento**: questa configurazione contiene il componente ER modello di dati che rappresenta la struttura dei dati del dominio aziendale di pagamento.
    - **Mapping di modello di pagamento 1611**: questa configurazione contiene il componente ER mapping del modello che descrive in che modo il modello di dati viene compilato con i dati dell'applicazione in fase di esecuzione.
    - **BACS (Regno Unito)**: questa configurazione contiene i componenti ER formato e mapping del formato. Il componente di formato specifica il layout del report. Il componente di mapping del formato contiene l'origine dati del modello e specifica come viene compilato il layout del report utilizzando questa origine dati in fase di esecuzione.

![Pagina delle configurazioni con le configurazioni ER specificate disponibili nell'albero.](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>Preparare un pagamento fornitore per l'elaborazione

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>Aggiungere le informazioni bancarie per un conto fornitore

È necessario aggiungere le informazioni bancarie per un conto fornitore a cui si farà riferimento in seguito in un pagamento registrato.

1. Andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**.
2. Nella pagina **Tutti i fornitori**, seleziona il conto fornitore **GB_SI_000001**, quindi, nel riquadro Azioni, nella scheda **Fornitore** del gruppo **Imposta**, seleziona **Conti bancari**.
3. Nella pagina **Conti bancari fornitore**, seleziona **Nuovo**, quindi immetti le seguenti informazioni:

    1. Nel campo **Conto bancario** immetti **GBP OPER**.
    2. Nel campo **Gruppi bancari**, seleziona **BankGBP**.
    3. Nel campo **Numero conto bancario**, immetti **202015**.
    4. Nel campo **Codice SWIFT**, immetti <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.
    5. Nel campo **IBAN**, immetti **GB33BUKB20201555555555**.
    6. Nel campo **Numero di registrazione**, mantieni il valore predefinito, <a id="DefineRoutingNumber"></a>**123456**.

    ![Pagina Conti bancari fornitore.](./media/er-quick-start2-bank-account.png)

4. Selezionare **Salva**.
5. Chiudere la pagina.
6. Nella pagina **Tutti i fornitori**, apri il conto fornitore **GB_SI_000001**.
7. Nella pagina dei dettagli del fornitore, seleziona **Modifica** per rendere modificabile la pagina, se necessario.
8. Nella scheda dettaglio **Pagamento**, nel campo **Conto bancario**, seleziona **GBP OPER**.

    ![Pagina Dettagli fornitore.](./media/er-quick-start2-bank-account-reference.png)

9. Selezionare **Salva**.
10. Chiudere la pagina.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>Immettere un pagamento fornitore

È necessario immettere un nuovo pagamento fornitore utilizzando una [proposta di pagamento](../../../finance/accounts-payable/create-vendor-payments-payment-proposal.md).

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.
2. Nella pagina **Giornale di registrazione pagamenti fornitore**, seleziona **Nuovo**.
3. Nel campo **Nome**, seleziona **VendPay**.
4. Selezionare **Righe**.
5. Seleziona **Proposta di pagamento** \> **Crea proposta di pagamento**.
6. Nella finestra di dialogo **Proposta di pagamento fornitore**, configura le condizioni per filtrare i record per il conto fornitore **GB_SI_000001**, quindi seleziona **OK**.
7. Seleziona la riga per la fattura **00000007_Inv**, quindi seleziona **Crea pagamento**.

    ![Finestra di dialogo Proposta di pagamento fornitore.](./media/er-quick-start2-payment-proposal.png)

8. Verifica che il pagamento immesso sia configurato per l'utilizzo del metodo di pagamento **Elettronico**.

    ![Pagina Pagamenti fornitore.](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>Elaborare un pagamento fornitore utilizzando il formato ER standard

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>Configurare il metodo di pagamento elettronico

È necessario configurare il metodo di pagamento elettronico in modo che utilizzi la configurazione del formato ER importato.

1. Andare a **Contabilità fornitori** \> **Impostazione pagamenti** \> **Metodi di pagamento**.
2. Nella pagina **Metodi di pagamento - Fornitori**, seleziona il metodo di pagamento **Elettronico** nel riquadro a sinistra.
3. Selezionare **Modifica**.
4. Nella scheda dettaglio **Formati file**, imposta l'opzione **Formato esportazione elettronica generica** su **Sì**.
5. Nel campo **Esporta configurazione formato** seleziona la configurazione del formato **BACS (Regno Unito)**.

    ![Metodi di pagamento: pagina dei fornitori per impostare il metodo di pagamento elettronico per elaborare i pagamenti dei fornitori utilizzando un formato standard.](./media/er-quick-start2-method-of-payment1.png)

6. Selezionare **Salva**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>Elaborare un pagamento fornitore

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.
2. Nella pagina **Giornale di registrazione pagamenti fornitore** selezionare il giornale di registrazione pagamenti aggiunti in precedenza, quindi selezionare **Righe**.
3. Nella pagina **Pagamenti fornitore**, seleziona **Genera pagamenti**.
4. Nella finestra di dialogo **Genera pagamenti** immetti le seguenti informazioni:

    - Nel campo **Metodo di pagamento** seleziona **Elettronico**.
    - Nel campo **Conto bancario** selezionare **GBSI OPER**.

5. Selezionare **OK**.
6. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, imposta l'opzione **Stampa report di controllo** su **Sì**, quindi seleziona **OK**.

    ![Pagina Parametri Creazione di report elettronici.](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > Oltre al file di pagamento, è ora possibile generare il report di controllo.

7. Scarica il file zip, quindi estrai i seguenti file:

    - Il report di controllo in formato Excel
    - Il file di pagamento in formato TXT

        Si noti che, in conformità con la [struttura](#PositionRoutingNumber) del formato ER fornito, la riga di pagamento nel file generato inizia con il numero di registrazione che era [definito](#DefineRoutingNumber)per il conto bancario configurato.

        ![File di pagamento in formato TXT.](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personalizzare il formato ER standard

Nell'esempio mostrato in questa sezione, vuoi utilizzare le configurazioni ER fornite da Microsoft per generare file di pagamento del fornitore in formato BACS, ma è necessario aggiungere una personalizzazione per supportare i requisiti di una banca specifica. Vuoi anche essere in grado di aggiornare il tuo formato personalizzato quando saranno disponibili nuove versioni delle configurazioni ER. Tuttavia, desideri anche poter eseguire l'aggiornamento al minor costo.

In questo caso, in qualità di rappresentante di Litware, Inc., devi creare (derivare) una nuova configurazione del formato ER utilizzando la configurazione **BACS (Regno Unito)** fornita da Microsoft come base.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Creare un formato personalizzato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito)**. Litware, Inc. utilizzerà la versione 1.1 di questa configurazione del formato ER come base per la versione personalizzata.
3. Seleziona **Crea configurazione** per aprire la finestra di dialogo a discesa. Puoi utilizzare questa finestra di dialogo per creare una nuova configurazione per un formato di pagamento personalizzato.
4. Nel gruppo di campi **Nuovo**, selezionare l'opzione **Deriva da nome: BACS (Regno Unito), Microsoft**.
5. Nel campo **Nome**, immetti **BACS (Regno Unito, personalizzato)**.

    ![Finestra di dialogo a discesa Crea configurazione.](./media/er-quick-start2-add-derived-format.png)

6. Selezionare **Crea configurazione**.

Viene creata la versione 1.1.1 della configurazione del formato ER **BACS (Regno Unito, personalizzato)**. Questa versione ha uno [stato](general-electronic-reporting.md#component-versioning) di **Bozza** e può essere modificata. Il contenuto corrente del tuo formato ER personalizzato corrisponde al contenuto del formato fornito da Microsoft.

![Pagina delle configurazioni con versione 1.1.1 della configurazione del formato ER BACS (Regno Unito, personalizzato).](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>Modificare un formato personalizzato

È necessario configurare il formato personalizzato in modo che soddisfi i requisiti specifici della banca. Ad esempio, una banca potrebbe richiedere che i file di pagamento generati includano il codice SWIFT (Society for Worldwide Interbank Financial Telecommunication) di una banca a cui è assegnato il ruolo di agente nel pagamento del fornitore elaborato. I codici SWIFT sono codici bancari internazionali che identificano banche specifiche in tutto il mondo. Sono anche noti come codici identificativi bancari (BIC). Il codice SWIFT deve contenere 11 caratteri e deve essere inserito all'inizio di ogni riga di pagamento in un file di pagamento generato.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito, personalizzato)**.
3. Nella scheda dettaglio **Versioni** seleziona la versione **1.1.1** della configurazione selezionata.
4. Selezionare **Progettazione**.
5. Nella pagina **Progettazione formati**, seleziona **Mostra dettagli** per visualizzare altre informazioni sugli elementi del formato.
6. Espandi e rivedi i seguenti elementi:

    - L'elemento **BACSReportsFolder** del tipo **Cartella**. Questo elemento viene utilizzato per generare output in formato ZIP.
    - L'elemento **file** del tipo **File**. Questo elemento viene utilizzato per generare un file di pagamento in formato TXT.
    - L'elemento **transazioni** del tipo **Sequenza**. Questo elemento viene utilizzato per generare una riga di pagamento singola in un file di pagamento.
    - L'elemento **transazione** del tipo **Sequenza**. Questo elemento viene utilizzato per generare campi singoli di una riga di pagamento singola.

7. Seleziona l'elemento **transazione**.

    ![Elemento transazione nella finestra di progettazione Operazioni ER.](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > Il report fornito è configurato in modo tale che <a id="PositionRoutingNumber"></a>ogni riga di pagamento inizi con il numero di registrazione bancario. L'elemento di formato **vendBankRouteNum** viene utilizzato per questo scopo. 

8. Seleziona **Aggiungi**, quindi seleziona il tipo **Testo\\Stringa** dell'elemento di formato che stai aggiungendo:

    1. Nel campo **Nome**, immetti **vendBankSWIFT**.
    2. Nel campo **Lunghezza minima** immetti **11**.
    3. Nel campo **Lunghezza massima** immetti **11**.
    4. Selezionare **OK**.

    > [!NOTE]
    > L'elemento **vendBankSWIFT** verrà utilizzato per inserire il codice SWIFT di una banca del fornitore nei file generati.

9. Nell'albero della struttura del formato, seleziona **vendBankSWIFT**.
10. Seleziona **Sposta su** per spostare l'elemento del formato selezionato di un livello superiore. Ripeti questo passaggio fino a quando l'elemento **vendBankSWIFT** è il <a id="PositionSWIFTCode"></a>primo elemento sotto l'elemento padre **transazione**.

    ![VendBankSWIFT come primo elemento in transazione nella finestra di progettazione Operazioni ER.](./media/er-quick-start2-derived-format1.png)

11. Mentre **vendBankSWIFT** è ancora selezionato nella struttura ad albero del formato, seleziona la scheda **Mapping**, quindi espandi l'origine dati **modello**.
12. Espandi **model.Payment**\>**model.Payment.CreditorAgent** e seleziona il campo dell'origine dati **model.Payment.CreditorAgent.BICFI**. Questo campo dell'origine dati espone il codice SWIFT di una banca del fornitore a cui è assegnato il ruolo di agente nel pagamento del fornitore elaborato.
13. Selezionare **Associa**. L'elemento di formato **vendBankSWIFT** è ora associato al campo dell'origine dati **model.Payment.CreditorAgent.BICFI**, in modo che i codici SWIFT vengano inseriti nei file di pagamento generati.

    ![Elemento di formato vendBankSWIFT associato al campo dell'origine dati model.Payment.CreditorAgent.BICFI nella finestra di progettazione Operazioni ER.](./media/er-quick-start2-derived-format2.png)

14. Selezionare **Salva**.
15. Chiudi la pagina della finestra di progettazione.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Contrassegnare un formato personalizzato come eseguibile

Ora che la prima versione del tuo formato personalizzato è stata creata e ha uno stato di **Bozza**, puoi eseguirla a scopo di test. Per eseguire il report, è necessario elaborare un pagamento fornitore utilizzando il metodo di pagamento che fa riferimento al formato ER personalizzato. Per impostazione predefinita, quando chiami un formato ER dall'applicazione, solo le versioni che hanno uno stato di **Completata** o **Condivisa** vengono [considerate](general-electronic-reporting.md#component-versioning). Questo comportamento consente di impedire l'utilizzo di formati ER con progettazioni incomplete. Tuttavia, per le esecuzioni di test, è possibile forzare l'applicazione a utilizzare la versione del formato ER con uno stato di **Bozza**. In questo modo, è possibile regolare la versione del formato corrente se sono necessarie modifiche. Per ulteriori informazioni, vedi [Applicabilità](electronic-reporting-destinations.md#applicability).

Per utilizzare la versione bozza di un formato ER, è necessario contrassegnare esplicitamente il formato ER.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, imposta l'opzione **Esegui impostazioni** su **Sì**, quindi seleziona **OK**.
4. Seleziona **Modifica** per rendere la pagina modificabile come richiesto.
5. Nell'albero di configurazione nel riquadro sinistro, seleziona **BACS (Regno Unito, personalizzato)**.
6. Imposta l'opzione **Esegui bozza** su **Sì**.

    ![Opzione Esegui bozza nella pagina Configurazioni.](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>Elaborare un pagamento fornitore utilizzando il formato ER personalizzato

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>Configurare il metodo di pagamento elettronico

È necessario configurare il metodo di pagamento elettronico in modo che il formato ER personalizzato venga utilizzato per elaborare i pagamenti del fornitore.

1. Andare a **Contabilità fornitori** \> **Impostazione pagamenti** \> **Metodi di pagamento**.
2. Nella pagina **Metodi di pagamento - Fornitori**, seleziona il metodo di pagamento **Elettronico** nel riquadro a sinistra.
3. Selezionare **Modifica**.
4. Nella scheda dettaglio **Formatofile**, imposta l'opzione **Formato esportazione elettronica generica** su **Sì**.
5. Nel campo **Esporta configurazione formato** seleziona la configurazione del formato **BACS (Regno Unito, personalizzato)**.

    ![Metodi di pagamento: pagina dei fornitori per impostare il metodo di pagamento elettronico per elaborare i pagamenti dei fornitori utilizzando un formato personalizzato.](./media/er-quick-start2-method-of-payment2.png)

6. Selezionare **Salva**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>Elaborare un pagamento fornitore

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.
2. Nella pagina **Giornale di registrazione pagamenti fornitore** seleziona il giornale di registrazione pagamenti creato in precedenza.
3. Selezionare **Righe**.
4. Nella pagina **Pagamenti fornitore**, sopra la griglia, seleziona e **Stato pagamenti**\>**Nessuno**.
5. Seleziona **Genera pagamento**.
6. Nella finestra di dialogo **Genera pagamenti** immetti le seguenti informazioni:

    - Nel campo **Metodo di pagamento** seleziona **Elettronico**.
    - Nel campo **Conto bancario** selezionare **GBSI OPER**.

7. Selezionare **OK**.
8. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, imposta l'opzione **Stampa report di controllo** su **Sì**, quindi seleziona **OK**.

    > [!NOTE]
    > Oltre al file di pagamento, è ora possibile generare solo il report di controllo.

9. Scarica il file zip, quindi estrai i seguenti file:

    - Il report di controllo in formato Excel
    - Il file di pagamento in formato TXT

        Si noti che, in conformità con la struttura del formato ER personalizzato, la riga di pagamento nel file generato ora [inizia](#PositionSWIFTCode) con il codice SWIFT [immesso](#DefineSWIFTCode) per il conto bancario del fornitore il cui pagamento è stato elaborato.

        ![File di pagamento in formato TXT utilizzato per elaborare il pagamento del fornitore.](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>Importare nuove versioni delle configurazioni del formato ER standard

Nell'esempio mostrato in questa sezione, ricevi una notifica sull'articolo della Knowledge Base [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046). Questa notifica ti informa sulla nuova versione del formato ER **BACS (Regno Unito)** che è stato pubblicato da Microsoft. Oltre al report di controllo, questa nuova versione consente agli utenti di generare il report di avviso di pagamento e il report della nota di partecipazione durante l'elaborazione di un pagamento fornitore. Vuoi iniziare a usare quella funzionalità.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>Importare nuove versioni delle configurazioni ER standard

Per aggiungere le nuove versioni delle configurazioni ER standard all'istanza corrente di Finance , è necessario importarle dall'[archivio](general-electronic-reporting.md#Repository) ER che hai configurato.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**, quindi seleziona **Archivi** per visualizzare l'elenco dei repository per il provider Microsoft.
3. Nella pagina **Archivi di configurazione** seleziona l'archivio del tipo **Globale**, quindi seleziona **Apri**. Se viene richiesta l'autorizzazione per connettersi a Regulatory Configuration Service, segui le istruzioni di autorizzazione.
4. Nella pagina **Archivio di configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona la configurazione del formato **BACS (Regno Unito)**.
5. Nella scheda dettaglio **Versioni** seleziona la versione **3.3** della configurazione del formato ER selezionata.
6. Seleziona **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.

![Pagina archivio di configurazione, scheda dettaglio Versioni, pulsante Importa.](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> In caso di problemi di accesso all'[archivio globale](er-download-configurations-global-repo.md), puoi invece [scaricare le configurazioni](download-electronic-reporting-configuration-lcs.md) da LCS.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>Rivedere le configurazioni del formato ER importate

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito)**.
4. Nella scheda dettaglio **Versioni**, selezionare la versione **3.3**.
5. Selezionare **Progettazione**.
6. Nella pagina **Progettazione formati**, espandi l'elemento di formato **BACSReportsFolder**.
7.  Si noti che la versione 3.3 contiene l'elemento di formato **PaymentAdviceReport** utilizzato per generare un report di avviso di pagamento quando viene elaborato un pagamento fornitore.

    ![Elemento di formato PaymentAdviceReport nella finestra di progettazione Operazioni ER.](./media/er-quick-start2-imported-solution2.png)

8. Chiudi la pagina della finestra di progettazione.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>Adottare le modifiche nella nuova versione di un formato importato in un formato personalizzato

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>Completare la versione in bozza corrente di un formato personalizzato

Se desideri mantenere lo stato corrente del formato personalizzato, completa la versione della bozza 1.1.1 modificandone lo stato da **Bozza** a **Completato**.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, espandi **BACS (Regno Unito)** quindi seleziona **BACS (Regno Unito, personalizzato)**.
4. Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.

Lo stato della versione 1.1.1 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura. Una nuova versione modificabile, 1.1.2, è stata aggiunta e ha uno stato di **Bozza**. Puoi utilizzare questa versione per apportare ulteriori modifiche al tuo formato ER personalizzato.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>Riassegnare un formato personalizzato su una nuova versione di base

Per iniziare a utilizzare la nuova funzionalità della versione 3.3 del formato **BACS (Regno Unito)** nella personalizzazione, è necessario modificare la versione della configurazione di base per la configurazione personalizzata, **BACS (Regno Unito, personalizzazione)**. Questo processo è noto come [riassegnazione](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase). Anziché la versione 1.1 di **BACS (Regno Unito)**, utilizza la versione 3.3.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito, personalizzato)**.
3. Nella Scheda Dettaglio **Versioni**, seleziona la versione **1.1.2**, quindi seleziona **Riassegna**.
4. Nella finestra di dialogo **Riassegna**, nel campo **Versione destinazione**, seleziona la versione **3.3** della configurazione di base per applicarla come nuova base e utilizzarla per aggiornare la configurazione.

    ![Finestra di dialogo Riassegna.](./media/er-quick-start2-rebase1.png)

5. Selezionare **OK**.
6. Si noti che il numero della versione bozza è stato modificato da **1.1.2** a **3.3.2** per riflettere la modifica nella versione base.

    Quando la versione personalizzata e la nuova versione di base vengono unite, alcuni conflitti potrebbero essere individuati a causa di modifiche di formato che non possono essere unite automaticamente.

    ![Configurazione riassegnata con conflitti nella pagina Configurazioni.](./media/er-quick-start2-rebase2.png)

    Se vengono rilevati conflitti, devono essere risolti manualmente nella finestra di progettazione del formato.

7. Nella scheda dettaglio **Versioni**, selezionare la versione **3.3.2**.
8. Selezionare **Progettazione**.
9. Nella pagina **Progettazione formato**, sulla Scheda Dettaglio **Dettagli**, seleziona un record di conflitto di riassegnazione e quindi seleziona **Applica valore base**.

    ![Record di conflitto riassegnazione nella finestra di progettazione Operazioni ER.](./media/er-quick-start2-rebase3.png)

10. Selezionare **Salva**.

    Il record di conflitto di riassegnazione non dovrebbe più apparire nella scheda Dettaglio **Dettagli**.

    ![Conflitto risolto nella finestra di progettazione Operazioni ER.](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > Hai risolto il conflitto confermando che la versione 3 del modello base deve essere utilizzata in questo formato ER.

11. Espandi **BACSReportsFolder** \> **file** \> **transazioni** \> **transazione**.
12. Nella scheda **Mapping**, tieni presente che la versione 3.3.2 del tuo formato ER personalizzato contiene sia la tua personalizzazione (l'elemento di formato **vendBankSWIFT** ed è vincolante) e la nuova funzionalità della versione 3.3 del formato ER di base fornito da Microsoft (l'elemento di formato **PaymentAdviceReport** insieme ai suoi elementi nidificati e ai binding configurati). In pochi clic del mouse, hai adottato le modifiche di una nuova versione di base unendole alla tua personalizzazione.

    ![Formato unito nella finestra di progettazione Operazioni ER.](./media/er-quick-start2-rebase5.png)

13. Chiudi la pagina della finestra di progettazione.

> [!NOTE]
> L'azione di riassegnazione è reversibile. Per annullare questa riassegnazione, seleziona la versione **1.1.1** del formato **BACS (Regno Unito personalizzato)** nella Scheda Dettaglio **Versioni**, quindi seleziona **Ottieni questa versione**. La versione 3.3.2 verrà quindi rinumerata 1.1.2 e il contenuto della bozza della versione 1.1.2 corrisponderà al contenuto della versione 1.1.1.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>Elaborare un pagamento fornitore utilizzando un formato ER riassegnato

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.
2. Nella pagina **Giornale di registrazione pagamenti fornitore** seleziona il giornale di registrazione pagamenti creato in precedenza.
3. Selezionare **Righe**.
4. Nella pagina **Pagamenti fornitore**, sopra la griglia, seleziona e **Stato pagamenti**\>**Nessuno**.
5. Seleziona **Genera pagamento**.
6. Nella finestra di dialogo **Genera pagamenti** immetti le seguenti informazioni:

    - Nel campo **Metodo di pagamento** seleziona **Elettronico**.
    - Nel campo **Conto bancario** selezionare **GBSI OPER**.

7. Selezionare **OK**.
8. Nella finestra di dialogo **Parametri per la creazione di report elettronici** immetti le seguenti informazioni:

    - Impostare l'opzione **Stampa report controllo** su **Sì**.
    - Imposta l'opzione **Stampa avviso di pagamento** su **Sì**.

    ![Finestra di dialogo parametri Creazione di report elettronici.](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > Oltre al file di pagamento, è ora possibile generare sia il report di controllo sia il report dell'avviso di pagamento.

9. Selezionare **OK**.
10. Scarica il file zip, quindi estrai i seguenti file:

    - Il report di controllo in formato Excel
    - Il report di avviso di pagamento in formato Excel

        ![Report di avviso di pagamento in formato Excel.](./media/er-quick-start2-payment-advice-report.png)

    - Il file di pagamento in formato TXT

        Si noti che la riga di pagamento nel file generato ora inizia con il codice SWIFT immesso per il conto bancario del fornitore il cui pagamento è stato elaborato.

        ![File di pagamento in formato TXT utilizzato per elaborare il pagamento del fornitore utilizzando un formato ER riassegnato.](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Scaricare configurazioni ER da Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
