---
title: Progettare una nuova soluzione ER per stampare un report personalizzato
description: Questo argomento spiega come progettare una soluzione di reporting elettronico (ER) per stampare un report personalizzato.
author: NickSelin
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a3e0e4a8389fdd6580f66004d86ef4b1980dd9f
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891795"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>Progettare una nuova soluzione ER per stampare un report personalizzato

[!include[banner](../includes/banner.md)]

I passaggi seguenti spiegano come un utente con il ruolo di amministratore di sistema, sviluppatore per la creazione di report elettronici o consulente funzionale per la creazione di report elettronici può configurare i parametri del framework ER, progettare le configurazioni ER richieste per una nuova soluzione ER per accedere ai dati di un particolare dominio aziendale e generare un report personalizzato in formato Microsoft Office. Queste operazioni possono essere completate nella società **USMF**.

- [Configurare il framework ER](#ConfigureFramework)

    - [Configurare i parametri ER](#ConfigureParameters)
    - [Attivare un provider di configurazioni ER](#ActivateProvider)

        - [Rivedere l'elenco dei provider di configurazione ER](#ReviewProvidersList)
        - [Aggiungere un nuovo provider di configurazione ER](#AddProvider)
        - [Attivare un provider di configurazioni ER](#ActivateAddedProvider)

- [Progettare un modello di dati specifici di un dominio](#DesignModel)

    - [Importare una nuova configurazione del modello di dati](#ImportDataModel)
    - [Creare una nuova configurazione del modello di dati](#DesignDataModel)

        - [Denominare il modello di dati](#NameDataModel)
        - [Aggiungere campi al modello di dati](#FieldsEntry)
        - [Completare la progettazione del modello di dati](#CompleteDataModel)

- [Progettare una mappatura del modello per il modello di dati configurato](#DesignMapping)

    - [Importare una nuova configurazione del mapping del modello](#ImportModelMapping)
    - [Creare una nuova configurazione del mapping del modello](#CreateModelMapping)

        - [Progettare un nuovo componente del mapping del modello](#DesignMappingComponent)
        - [Aggiungere origini dati per accedere alle tabelle dell'applicazione](#AddMmDataSource1)
        - [Aggiungere origini dati per accedere alle enumerazioni dell'applicazione](#AddMmDataSource2)
        - [Aggiungere etichette ER per generare un report in una lingua specificata](#AddMmLabels)
        - [Aggiungere un'origine dati per trasformare i risultati del confronto dei valori di enumerazione in un valore di testo](#AddMmDataSource3)
        - [Mappare le origini dati ai campi del modello di dati](#AddMmBindings1)
        - [Completare la progettazione del mapping del modello](#CompleteModelMapping)

- [Progettare un modello per un report personalizzato](#DesignReportTemplate)
- [Progettare un formato](#DesignFormat)

    - [Importare una configurazione in un formato progettato](#FormatImport)
    - [Creare una nuova configurazione di formato](#FormatCreate)

        - [Importare un modello di report](#ImportReportTemplate)
        - [Configurare un formato](#ConfigureFormat)
        - [Definire l'associazione dati per un titolo di report](#DefineFormatBindings)
        - [Esaminare l'origine dati del modello](#ReviewModelDataSource)
        - [Associare gli elementi di formato ai campi di un'origine dati](#BindFormatElements)

    - [Eseguire un formato progettato da ER](#RunFormatFromER)

- [Ottimizzare un formato progettato](#TuneFormat)

    - [Modificare un formato per cambiare il nome di un documento generato](#ModifyToChangeName)
    - [Modificare un formato per cambiare l'ordine delle domande](#ModifyToOrder)
    - [Eseguire un formato modificato da ER](#RunFormatFromER2)
    - [Completare la progettazione del formato](#CompleteFormat)

- [Sviluppare gli elementi dell'applicazione per chiamare il report progettato](#DevelopCustomCode)

    - [Modificare il codice sorgente](#ModifySourceCode)

        - [Aggiungere una categoria di contratto dati](#DataContractClass)
        - [Aggiungere una classe di creazione dell'interfaccia utente](#UIBuilderClass)
        - [Aggiungere una categoria di provider di dati](#DataProviderClass)
        - [Aggiungere un file di etichette](#LabelsFile)
        - [Aggiungere una classe di servizio dei report](#ServiceClass)
        - [Aggiungere una classe di controller dei report](#ControllerClass)
        - [Aggiungere una voce di menu](#MenuItem)
        - [Aggiungere una voce a un menu](#Menu)
        - [Costruire un progetto Visual Studio](#BuildVSProject)

    - [Eseguire un formato dall'applicazione](#RunFormatFromApp)

- [Ottimizzare una soluzione ER progettata](#TuneSolution)

    - [Modificare un mapping di modello](#ModifyModelMapping)

        - [Aggiungere origini dati per accedere a un oggetto di contratto dati](#AddDataSource1)
        - [Aggiungere un'origine dati per accedere ai record di mapping del formato ER](#AddDataSource2)
        - [Aggiungere un'origine dati per accedere al record di mapping di un formato ER in esecuzione](#AddDataSource3)
        - [Immettere il nome del formato ER in esecuzione nel modello di dati](#AddBinding)
        - [Completare la progettazione del mapping del modello](#CompleteModelMapping2)

    - [Modificare un formato](#ModifyFormat)

        - [Aggiungere un nuovo elemento di formato](#AddFormatElement)
        - [Associare l'elemento del formato aggiunto](#BindAddedFormatElement)
        - [Completare la progettazione del formato](#CompleteFormat2)

    - [Eseguire un formato dall'applicazione](#RunFormatFromApp2)
    - [Eseguire un formato da ER](#RunFormatFromER3)
    - [Configurare una destinazione del formato per l'anteprima su schermo](#ConfigureDestination)
    - [Eseguire un formato dall'applicazione per visualizzarlo in anteprima come documento PDF](#RunFormatFromApp3)

- [Risorse aggiuntive](#References)

In questo esempio, creerai una nuova soluzione ER per il modulo [Gestione questionari](../../../human-resources/hr-learning-questionnaires.md). Questa nuova soluzione ER consente di progettare un report utilizzando un foglio di lavoro Microsoft Excel come modello. È quindi possibile generare il report **Gestione questionari** in formato Excel o PDF, oltre a generare il report SQL Server Reporting Services (SSRS) esistente. È inoltre possibile modificare il nuovo report in un secondo momento, su richiesta. Non è richiesta alcuna codifica.

1. Per eseguire il report esistente, vai a **Gestione questionari** \> **Progettazione** \> **Report dei questionari**.

    ![Selezionando la voce di menu Report di questionario nel modulo Gestione questionari per eseguire il report SSRS esistente](./media/er-quick-start1-application-menu-origin.png)

2. Nella finestra di dialogo **Report dei questionari**, specifica i criteri di selezione. Applica un filtro in modo che il report includa solo il questionario **SBCCrsExam**.

    ![Impostazione dei criteri di selezione nella finestra di dialogo Report dei questionari](./media/er-quick-start1-ssrs-report-dialog.png)

La figura seguente mostra la versione generata del report SSRS per il questionario **SBCCrsExam**.

![Report SSRS generato](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>Configurare il framework ER

Come utente che dispone del ruolo di sviluppatore per la creazione di report elettronici, è necessario configurare il set minimo di parametri ER prima di poter iniziare a utilizzare il framework ER per progettare una nuova soluzione ER.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>Configurare i parametri ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Parametri per la creazione di report elettronici**.
3. Nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
4. Nella scheda **Allegati**, imposta i seguenti parametri:

    - Impostare il campo **Configurazioni** su **File** per l'azienda **USMF**.
    - Impostare i campi **Archivio processi**, **Temporaneo**, **Base** e **Altri** su **File**.

Per ulteriori informazioni sui parametri ER, vedi [Configurare il framework ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>Attivare un provider di configurazioni ER

Ogni configurazione ER viene contrassegnata come di proprietà di un provider di configurazione ER. Pertanto, è necessario attivare un provider di configurazione ER nell'area di lavoro **Creazione di report elettronici** prima di iniziare ad aggiungere o modificare qualsiasi configurazione ER.

> [!NOTE]
> Solo il proprietario di una configurazione ER può modificarla. Pertanto, prima di poter modificare una configurazione ER, è necessario attivare il provider di configurazione ER appropriato nell'area di lavoro **Creazione di report elettronici**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>Rivedere l'elenco dei provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Provider di configurazione**.
3. Nella pagina **Provider di configurazione**, ogni configurazione del provider ha un nome e un URL univoco. Rivedi il contenuto della pagina. Se un record per **Litware, Inc.** (`https://www.litware.com`) esiste già, salta la procedura successiva, [Aggiungere un nuovo provider di configurazione ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>Aggiungere un nuovo provider di configurazione ER

1. Nella pagina **Provider di configurazione**, seleziona **Nuovo**.
2. Nel campo **Nome**, immetti **Litware, Inc.**
3. Nel campo **Indirizzo Internet** immetti `https://www.litware.com`.
4. Selezionare **Salva**.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>Attivare un provider di configurazioni ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nell'area di lavoro **Creazione di report elettronici**, selezionare il provider di configurazioni **Litware, Inc.**.
3. Selezionare **Imposta come attivo**.

Per ulteriori informazioni sui provider di configurazione ER, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>Progettare un modello di dati specifici di un dominio

È necessario creare una nuova configurazione ER che contenga un componente [modello di dati](general-electronic-reporting.md#data-model-and-model-mapping-components) per il dominio aziendale **Gestione questionari**. Questo modello di dati verrà successivamente utilizzato come origine dati quando si progetta un formato ER per generare il report **Gestione questionari**.

Completando i passaggi nella sezione [Importare una nuova configurazione del modello di dati](#ImportDataModel), è possibile importare il modello di dati richiesto dal file XML fornito. In alternativa, puoi completare i passaggi nella sezione [Creare una nuova configurazione del modello di dati](#DesignDataModel) per progettare questo modello di dati da zero.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>Importare una nuova configurazione del modello di dati

1. Scaricare il file [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salvarlo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella riquadro Azioni, selezionare **Scambia** \> **Carica da file XML**.
5. Selezionare **Sfoglia**, quindi trovare e selezionare il file **Questionarios model.version.1.xml**.
6. Selezionare **OK** per importare la configurazione.

Per continuare, saltare la procedura successiva, [Creare una nuova configurazione del modello di dati](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>Creare una nuova configurazione del modello di dati

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
3. Selezionare **Crea configurazione**.
4. Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Modello del questionario**.
5. Selezionare **Crea configurazione** per creare la configurazione.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>Denominare il modello di dati

1. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Modello di questionario**.
2. Selezionare **Progettazione**.
3. Nella pagina **Progettazione del modello di dati**, nella scheda **Generale**, nel campo **Nome**, inserire <a name="DataModeName"></a>**Questionari**.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>Aggiungere nuovi campi al modello di dati

1. Nella pagina **Progettazione del modello di dati**, selezionare **Nuovo**.
2. Nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Selezionare **Radice modello** come tipo del nuovo nodo.
    2. Nel campo **Nome**, immettere <a name="RootDefinitionName"></a>**Root**.
    3. Per aggiungere un nuovo nodo, selezionare **Aggiungi**.

    Questo descrittore radice verrà utilizzato per fornire i dati per il report **Gestione questionari**. Un singolo modello di dati può avere più descrittori. Ciascun descrittore può essere specificato per un singolo formato ER, per identificare i dati necessari alla creazione del report.

3. Selezionare ancora **Nuovo** , quindi nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Selezionare **Elemento figlio di un nodo attivo** come tipo del nuovo nodo.
    2. Nel campo **Nome**, immettere **CompanyName**.
    3. Nel campo **Tipo di articolo** selezionare **Stringa**.
    4. Per aggiungere un nuovo campo, selezionare **Aggiungi**.

    Questo campo è necessario per passare il nome della società corrente a un report ER che utilizza questo modello di dati come origine dati.

4. Selezionare ancora **Nuovo** , quindi nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Selezionare **Elemento figlio di un nodo attivo** come tipo del nuovo nodo.
    2. Nel campo **Nome**, immettere **Gestione questionari**.
    3. Nel campo **Tipo di articolo** selezionare **Elenco di record**.
    4. Per aggiungere un nuovo campo, selezionare **Aggiungi**.

    Questo campo verrà utilizzato per passare l'elenco dei questionari a un report ER che utilizza questo modello di dati come origine dati.

5. Selezionare il nodo **Gestione questionari**.
6. Continuare ad aggiungere i campi obbligatori del modello di dati modificabile nello stesso modo fino a completare la seguente struttura del modello di dati.

    | Percorso campo                                                    | Tipo di dati   | Assegnazione del campo/valore restituito |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | Nodo principale                                                          |             | Il punto di riferimento per richiedere i dati del questionario. |
    | Root\\CompanyName                                             | String      | Il nome della società corrente. |
    | Root\\ExecutionContext                                        | Registra      | Dettagli esecuzione formato. |
    | Root\\ExecutionContext\\FormatName                            | String      | Il nome del formato ER in esecuzione. |
    | Root\\Questionario                                           | Elenco di record | L'elenco dei questionari |
    | Root\\Questionario\\Attivo                                   | String      | Lo stato del questionario corrente. |
    | Root\\Questionario\\Codice                                     | String      | Il codice del questionario corrente. |
    | Root\\Questionario\\Descrizione                              | String      | La descrizione del questionario corrente. |
    | Root\\Questionario\\QuestionarioType                        | String      | Il tipo di questionario corrente. |
    | Root\\Questionario\\QuestionOrder                            | String      | L'ordine numerico del questionario corrente. |
    | Root\\Questionario\\ResultsGroup                             | Registra      | I parametri dei risultati del questionario corrente. |
    | Root\\Questionario\\ResultsGroup\\Codice                       | String      | Il codice di identificazione del gruppo di risultati corrente. |
    | Root\\Questionario\\ResultsGroup\\Descrizione                | String      | La descrizione del gruppo di risultati corrente. |
    | Root\\Questionario\\ResultsGroup\\MaxNumberOfPoints          | Real        | Il numero massimo di punti che possono essere guadagnati. |
    | Root\\Questionario\\Domanda                                 | Elenco di record | L'elenco delle domande per il questionario corrente. |
    | Root\\Questionario\\Domanda\\CollectionSequenceNumber       | Integer     | Il numero di sequenza della raccolta di risposte corrente. |
    | Root\\Questionario\\Domanda\\Id                             | String      | Il codice di identificazione della domanda corrente. |
    | Root\\Questionario\\Domanda\\MustBeCompleted                | String      | Un flag che indica se è necessario rispondere alla domanda corrente. |
    | Root\\Questionario\\Domanda\\PrimaryQuestion                | String      | Un flag che indica se la domanda corrente è primaria. |
    | Root\\Questionario\\Domanda\\SequenceNumber                 | Integer     | Il numero di sequenza della domanda corrente. |
    | Root\\Questionario\\Domanda\\Testo                           | String      | Il testo della domanda corrente. |
    | Root\\Questionario\\Domanda\\Risposta                         | Elenco di record | L'elenco delle risposte alla domanda corrente. |
    | Root\\Questionario\\Domanda\\Risposta\\CorrectAnswer          | String      | Un flag che indica se la risposta corrente è corretta. |
    | Root\\Questionario\\Domanda\\Risposta\\Punti                 | Real        | I punti guadagnati quando viene selezionata la risposta corrente. |
    | Root\\Questionario\\Domanda\\Risposta\\SequenceNumber         | Integer     | Il numero di sequenza della risposta corrente. |
    | Root\\Questionario\\Domanda\\Risposta\\Testo                   | String      | Il testo della risposta corrente. |

    La figura seguente mostra il modello di dati modificabile completato nella pagina **Progettazione del modello di dati**.

    ![Modello di dati configurato nella progettazione del modello di dati ER](./media/er-quick-start1-model2.png)

7. Salvare le modifiche.
8. Chiudere la pagina **Progettazione del modello di dati**.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>Completare la progettazione del modello di dati

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Modello di questionario**.
3. Nella scheda **Versioni**, selezionare la versione della configurazione con stato **Bozza**.
4. Selezionare **Cambia stato** \> **Completato**.

Lo stato della versione 1 di questa configurazione viene modificato da **Bozza** a **Completato**. La versione 1 non può più essere modificata. Questa versione contiene il modello di dati configurato e può essere utilizzata come base per le altre configurazioni ER. La versione 2 di questa configurazione viene creata e ha stato **Bozza**. Puoi modificare questa versione per regolare il modello di dati **Gestione questionari**.

![Le versioni della configurazione ER modificabile nella pagina Configurazioni](./media/er-quick-start1-model-configuration.png)

Per ulteriori informazioni sul controllo delle versioni per le configurazioni ER, vedere [Panoramica dei report elettronici](general-electronic-reporting.md#component-versioning).

> [!NOTE]
> Il modello di dati configurato è la rappresentazione astratta del dominio aziendale **Gestione questionari** e non contiene relazioni con elementi specifici di Microsoft Dynamics 365 Finance.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>Progettare un mapping del modello per il modello di dati configurato

In qualità di utente nel ruolo di sviluppatore per la creazione di report elettronici, è necessario creare una nuova configurazione ER che contenga un componente del [mapping del modello](general-electronic-reporting.md#data-model-and-model-mapping-components) per il modello di dati **Gestione questionari**. Poiché questo componente implementa il modello di dati configurato per Finance, è specifico di Finance. È necessario configurare il componente di mapping del modello per specificare gli oggetti dell'applicazione che devono essere utilizzati per compilare il modello di dati configurato con i dati dell'applicazione in fase di runtime. Per completare questa attività, è necessario essere a conoscenza dei dettagli di implementazione della struttura dati del dominio aziendale **Gestione questionari** in Finance.

Completando i passaggi nella sezione [Importare una nuova configurazione del mapping del nuovo modello](#ImportModelMapping) seguente, è possibile importare la configurazione del mapping del modello richiesto dal file XML fornito. In alternativa, è possibile completare i passaggi nella sezione [Creare una nuova configurazione del mapping del modello](#CreateModelMapping) per progettare questo mapping del modello da zero.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>Importare una nuova configurazione del mapping del modello

1. Scaricare il file [Questionarios mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salvarlo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella riquadro Azioni, selezionare **Scambia** \> **Carica da file XML**.
5. Selezionare **Sfoglia**, quindi trovare e selezionare il file **Questionarios mapping.version.1.1.xml**.
6. Selezionare **OK** per importare la configurazione.

Per continuare, saltare la procedura successiva, [Creare una nuova configurazione del mapping del modello](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>Creare una nuova configurazione del mapping del modello

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Modello di questionario**.
3. Selezionare **Crea configurazione**.
4. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nel campo **Nuovo**, selezionare **Mapping del modello basato sul modello dati Questionarios**.
    2. Nel campo **Nome**, immettere **Mapping del questionario**.
    3. Nel campo **Definizione modello dati**, selezionare la definizione **Root**.
    4. Selezionare **Crea configurazione** per creare la configurazione.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>Progettare un nuovo componente del mapping del modello

1. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping del questionario**.
2. Selezionare **Progettazione** per aprire l'elenco dei mapping.
3. Selezionare il mapping **Mapping dei questionari** che è stato aggiunto automaticamente alla definizione **Root**
4. Selezionare **Progettazione** per iniziare a configurare il mapping selezionato.

Un nuovo mapping viene aggiunto automaticamente per la definizione **Root**. Questo mapping ha la direzione **A modello**. Pertanto, questo mapping può essere utilizzato per compilare un modello di dati con i dati richiesti.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>Aggiungere origini dati per accedere alle tabelle dell'applicazione

È necessario configurare le origini dati per accedere alle tabelle dell'applicazione che contengono i dettagli del questionario.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Tabella dei record**.
2. Aggiungere una nuova origine dati che verrà utilizzata per accedere alla tabella KMCollection, dove ogni record rappresenta un singolo questionario:

    1. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    2. Nella finestra di dialogo, nel campo **Nome**, immettere **Gestione questionari**.
    3. Nel campo **Tabella**, immettere **KMCollection**.
    4. Impostare l'opzione **Chiedi query** su **Sì**. Sarai quindi in grado di specificare le opzioni di [filtro](../../fin-ops/get-started/advanced-filtering-query-options.md) per questa tabella nella finestra di dialogo delle query di sistema in fase di esecuzione.
    5. Selezionare **OK** per aggiungere la nuova origine dati.

3. Nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Tabella dei record**.
4. Aggiungere una nuova origine dati che verrà utilizzata per accedere alla tabella KMQuestion, dove ogni record rappresenta una singola domanda di un questionario:

    1. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    2. Nella finestra di dialogo, nel campo **Nome**, immettere **Domanda**.
    3. Nel campo **Tabella**, immettere **KMQuestion**.
    4. Selezionare **OK** per aggiungere la nuova origine dati.

5. Nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Tabella dei record**.
6. Aggiungere una nuova origine dati che verrà utilizzata per accedere alla tabella KMAnswer, dove ogni record rappresenta una singola risposta a una domanda di un questionario:

    1. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    2. Nel campo **Nome**, immettere **Risposta**.
    3. Nel campo **Tabella**, immettere **KMAnswer**.
    4. Selezionare **OK** per aggiungere la nuova origine dati.

7. Nel riquadro **Tipi di origine dati**, selezionare **Funzioni\\Campo calcolato**.
8. Aggiungi un nuovo campo calcolato che verrà utilizzato per accedere a un record della tabella KMQuestionResultGroup da ogni record della tabella KMCollection padre:

    1. Selezionare **Gestione questionari** nel riquadro **Origini dati**.
    2. Selezionare **Aggiungi**.
    3. Nella finestra di dialogo, nel campo **Nome**, immettere **\$ResultGroup**.
    4. Selezionare **Modifica formula**.
    5. Nell'[editor di formule ER](general-electronic-reporting-formula-designer.md), nel campo **Formula**, immettere **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** per usare il [percorso](er-formula-language.md#paths) della relazione uno-a-molti tra le tabelle KMCollection e KMQuestionResultGroup.
    6. Selezionare **Salva**, quindi chiudere l'editor di formule.
    7. Selezionare **OK** per aggiungere il nuovo campo calcolato.

9. Nel riquadro **Tipi di origine dati**, selezionare **Funzioni\\Campo calcolato**.
10. Aggiungi un nuovo campo calcolato che verrà utilizzato per accedere ai record delle domande della tabella KMQuestion da ogni record della tabella KMCollectionQuestion padre:

    1. Selezionare **Gestione questionari** nel riquadro **Origini dati**.
    2. Espandere il nodo **\<Relations** che contiene le relazioni uno-a-molti della tabella KMCollection.
    3. Selezionare la relativa tabella **KMCollectionQuestion**, quindi selezionare **Aggiungi**.
    4. Nella finestra di dialogo, nel campo **Nome**, immettere **\$Domanda**.
    5. Selezionare **Modifica formula**.
    6. Nell'editor di formule, nel campo **Formula**, immettere **FIRSTORNULL (FILTER(Domanda, Domanda.kmQuestionId = \@.kmQuestionId))** per restituire i record delle domande appropriati dalla tabella KMQuestion.
    7. Selezionare **Salva**, quindi chiudere l'editor di formule.
    8. Selezionare **OK** per aggiungere il nuovo campo calcolato.

11. Nel riquadro **Tipi di origine dati**, selezionare **Funzioni\\Campo calcolato**.
12. Aggiungere un nuovo campo calcolato che verrà utilizzato per accedere ai record delle risposte della tabella KMAnswer da ogni record della tabella KMQuestion padre:

    1. Nel riquadro **Origini dati**, selezionare **Questionario.\<Relations.KMCollectionQuestion.\$Domanda**, quindi **Aggiungi**.
    2. Nella finestra di dialogo, nel campo **Nome**, immettere **\$Answer**.
    3. Selezionare **Modifica formula**.
    4. Nell'editor di formule, nel campo **Formula**, immettere **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** per restituire i record delle risposte appropriati dalla tabella KMAnswer.
    5. Selezionare **Salva**, quindi chiudere l'editor di formule.
    6. Selezionare **OK** per aggiungere il nuovo campo calcolato.

13. Nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Tabella**.
14. Aggiungere una nuova origine dati che verrà utilizzata per accedere ai metodi della tabella CompanyInfo. Notare che il metodo **find()** di questa tabella restituisce un record che rappresenta una società dell'istanza Finance corrente nel cui contesto viene chiamato questo mapping.

    1. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    2. Nella finestra di dialogo, nel campo **Nome**, immettere **CompanyInfo**.
    3. Nel campo **Tabella**, immettere **CompanyInfo**.
    4. Selezionare **OK** per aggiungere la nuova origine dati.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>Aggiungere origini dati per accedere alle enumerazioni dell'applicazione

È necessario configurare le origini dati per accedere alle enumerazioni dell'applicazione e confrontare i loro valori con i valori dei campi del tipo **Enumerazione** nelle tabelle dell'applicazione. È necessario utilizzare il risultato del confronto per compilare i campi appropriati del modello dati.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Enumerazione**.
2. Aggiungere una nuova origine dati che verrà utilizzata per accedere ai valori dell'enumerazione **EnumAppNoYes**:

    1. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    2. Nella finestra di dialogo, nel campo **Nome**, immettere **EnumAppNoYes**.
    3. Nel campo **Enumerazione**, immettere **NoYes**.
    4. Selezionare **OK** per aggiungere la nuova origine dati.

3. Nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Enumerazione**.
4. Aggiungere una nuova origine dati che verrà utilizzata per accedere ai valori dell'enumerazione **KMCollectionQuestionMode**:

    1. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    2. Nella finestra di dialogo, nel campo **Nome**, immettere **EnumAppQuestionOrder**.
    3. Nel campo **Enumerazione**, immettere **KMCollectionQuestionMode**.
    4. Selezionare **OK** per aggiungere la nuova origine dati.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>Aggiungere etichette ER per generare un report in una lingua specificata

È possibile aggiungere etichette ER per configurare alcune delle origini dati per restituire valori che dipendono dalla lingua definita nel contesto della chiamata del mapping del modello.

1. Nella pagina **Progettazione mapping modello** nel riquadro **Origini dati**, selezionare **Risposta**, quindi **Modifica**.
2. Attivare il campo **Etichetta**.
3. Selezionare **Traduci**.
4. Nella finestra di dialogo **Traduzione testo**, effettuare le seguenti operazioni:

    1. Nel campo **ID etichetta**, immettere **PositiveAnswer**.
    2. Nel campo **Testo in lingua predefinita**, immettere **Sì**.
    3. Selezionare **Traduci**.
    4. Nel campo **ID etichetta**, immettere **NegativeAnswer**.
    5. Nel campo **Testo in lingua predefinita**, immettere **No**.
    6. Selezionare **Traduci**.

5. Chiudere la finestra di dialogo **Traduzione testo**.
6. Selezionare **Annulla**.

![Aggiunta di etichette ER per il mapping del modello modificabile](./media/er-quick-start1-adding-labels.png)

Hai inserito le etichette ER solo per la lingua predefinita. Per informazioni su come tradurre le etichette ER in altre lingue, vedere [Progettare report multilingue](er-design-multilingual-reports.md).

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>Aggiungere un'origine dati per trasformare i risultati del confronto dei valori di enumerazione in un valore di testo

Poiché è necessario trasformare più volte i risultati del confronto tra valori di enumerazione e valori di testo per origini differenti, è consigliabile configurare questa logica come un'unica origine dati. Tuttavia, per rendere questa origine dati riutilizzabile, è necessario configurarla come origine dati parametrizzata. Per ulteriori informazioni, vedere [Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato](er-calculated-field-type.md).

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, selezionare **Generale\\Contenitore vuoto**.
2. Aggiungere una nuova origine dati contenitore:

    1. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    2. Nella finestra di dialogo, nel campo **Nome**, immettere **Helper**.
    3. Selezionare **OK** per aggiungere la nuova origine dati contenitore.

3. Nel riquadro **Tipi di origine dati**, selezionare **Funzioni\\Campo calcolato**.
4. Aggiungere una nuova origine dati:

    1. Nel riquadro **Origini dati**, selezionare **Helper**.
    2. Selezionare **Aggiungi**.
    3. Nella finestra di dialogo, nel campo **Nome**, immettere **NoYesEnumToString**.
    4. Selezionare **Modifica formula**.
    5. Nell'editor delle formule, selezionare **Parametri**.
    6. Seguire questi passaggi per specificare i parametri per l'espressione configurata:

        1. Selezionare **Nuovo**.
        2. Nella finestra di dialogo, nel campo **Nome**, immettere **Argomento**.
        3. Nel campo **Tipo** selezionare il tipo di dati **Booleano**.
        4. Selezionare **OK**.

    7. Nel campo **Formula**, immettere **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** per restituire il testo dell'etichetta ER appropriata, a seconda della lingua del contesto di esecuzione e del valore del parametro specificato.
    8. Selezionare **Salva**, quindi chiudere l'editor di formule.
    9. Selezionare **OK** per aggiungere la nuova origine dati.

![Mapping del modello configurato nella progettazione del mapping del modello ER](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>Associare le origini dati ai campi del modello di dati

È necessario associare le origini dati configurate ai campi del modello dati per specificare in che modo il modello dati verrà compilato con i dati dell'applicazione in fase di esecuzione.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Modello dati**, selezionare **CompanyName**.
2. Nel riquadro **Origine dati**, espandere **CompanyInfo**, quindi seguire questi passaggi:

    1. Espandere il nodo **CompanyInfo.find()** che rappresenta il metodo **find()** della tabella CompanyInfo.
    2. Selezionare **CompanyInfo.find().Name**.
    3. Selezionare **Associa** per inserire il nome dell'azienda nel cui contesto viene chiamato il mapping del modello configurato al runtime.

3. Selezionare **Gestione questionari** nel riquadro **Modello di dati**.
4. Nel riquadro **Origini dati**, selezionare **Gestione questionari**, quindi **Associa** per compilare i record dei questionari.
5. Nel riquadro **Modello di dati**, espandere **Gestione questionari**, quindi seguire questi passaggi:

    1. Selezionare **Attivo** nel riquadro **Modello di dati**.
    2. Selezionare **Modifica** nel riquadro **Modello di dati**.
    3. Nel campo **Formula**, immettere **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** per riempire il risultato dipendente dal testo e dalla lingua del confronto tra i valori di enumerazione.

6. Continuare ad associare le origini dati ai campi del modello di dati nello stesso modo finché non si ottiene il risultato seguente.

    | Percorso campo                                              | Tipo di dati   | Azione | Espressione di associazione |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | String      | Associa   | CompanyInfo.'find()'.Name |
    | Gestione questionari                                           | Elenco di record | Associa   | Gestione questionari |
    | Questionario\\Active                                   | String      | Modifica   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | Questionario\\Code                                     | String      | Associa   | \@.kmCollectionId |
    | Questionario\\Description                              | String      | Associa   | \@.Description |
    | Questionario\\QuestionarioType                        | String      | Associa   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | Questionario\\QuestionOrder                            | String      | Modifica   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Conditional",<br>EnumAppQuestionOrder.Random, "Casuale (percentuale nel questionario)",<br>EnumAppQuestionOrder.RandomGroup, "Casuale (percentuale nel questionario)",<br>EnumAppQuestionOrder.Sequence, "Sequenziale",<br>"") |
    | Questionario\\ResultsGroup                             | Registra      |        | |
    | Questionario\\ResultsGroup\\Code                       | String      | Associa   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | Questionario\\ResultsGroup\\Description                | String      | Associa   | \@.'\$ResultGroup'.description |
    | Questionario\\ResultsGroup\\MaxNumberOfPoints          | Real        | Associa   | \@.'\$ResultGroup'.maxPoint |
    | Questionario\\Domanda                                 | Elenco di record | Associa   | \@.'&lt;Relations'.KMCollectionQuestion |
    | Questionario\\Domanda\\CollectionSequenceNumber       | Integer     | Associa   | \@.answerCollectionSequenceNumber |
    | Questionario\\Domanda\\Id                             | String      | Associa   | \@.kmQuestionId |
    | Questionario\\Domanda\\MustBeCompleted                | String      | Modifica   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | Questionario\\Domanda\\PrimaryQuestion                | String      | Associa   | \@.parentQuestionId |
    | Questionario\\Domanda\\SequenceNumber                 | Integer     | Associa   | \@.SequenceNumber |
    | Questionario\\Domanda\\Text                           | String      | Associa   | \@.'\$Domanda'.text |
    | Questionario\\Domanda\\Answer                         | Elenco di record | Associa   | \@.'\$Domanda'.'\$Answer' |
    | Questionario\\Domanda\\Answer\\CorrectAnswer          | String      | Modifica   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | Questionario\\Domanda\\Answer\\Points                 | Real        | Associa   | \@.point |
    | Questionario\\Domanda\\Answer\\SequenceNumber         | Integer     | Associa   | \@.sequenceNumber |
    | Questionario\\Domanda\\Answer\\Text                   | String      | Associa   | \@.text |

    La figura seguente mostra lo stato finale del mapping del modello configurato nella pagina **Progettazione mapping modello**.

    ![Mapping del modello completamente configurato nella progettazione del mapping del modello ER](./media/er-quick-start1-mapping2.png)

7. Salvare le modifiche.
8. Chiudere la pagina **Progettazione mapping modello**.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>Completare la progettazione del mapping del modello

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping del questionario**.
3. Nella scheda **Versioni**, selezionare la versione della configurazione con stato **Bozza**.
4. Selezionare **Cambia stato** \> **Completato**.

Lo stato della versione 1.1 di questa configurazione viene modificato da **Bozza** a **Completato**. La versione 1.1 non può più essere modificata. Questa versione contiene il mapping del modello configurato e può essere utilizzata come base per le altre configurazioni ER. La versione 1.2 di questa configurazione viene creata e ha stato **Bozza**. Puoi modificare questa versione per regolare la configurazione del **mapping del questionario**.

![Le versioni della configurazione ER modificabile nella pagina Configurazioni](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> Il mapping del modello configurato è l'implementazione specifica di Finance del modello di dati astratto che rappresenta il dominio aziendale **Gestione questionari**.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>Progettare un modello per un report personalizzato

Il framework ER usa modelli predefiniti per creare report nei formati Microsoft Office (cartelle di lavoro di Excel o documenti di Word). Durante la generazione del report richiesto, viene compilato un modello con i dati richiesti in base al flusso di dati configurato. Pertanto, è necessario prima progettare un modello per il report personalizzato. Questo modello deve essere progettato come una cartella di lavoro Excel, la cui struttura rappresenta il layout di un report personalizzato. È necessario denominare ogni elemento di Excel che si prevede di compilare con i dati richiesti.

1. Scaricare il file [Questionarios report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) e salvarlo sul computer locale.
2. Aprire il file in Excel e rivedere la struttura della cartella di lavoro.

Come mostra l'illustrazione seguente, il modello scaricato è stato progettato per stampare questionari specifici che presentano le domande di un questionario insieme alle risposte appropriate.

![Modello Excel per stampare questionari specifici](./media/er-quick-start1-template-layout.png)

I nomi Excel sono stati aggiunti a questo modello per compilare i dettagli del questionario. È possibile utilizzare Responsabile nomi per rivedere i nomi di Excel.

![Utilizzo di Responsabile nomi per rivedere i nomi Excel nel modello Excel fornito](./media/er-quick-start1-template-names.png)

Le etichette dei report sono state aggiunte come testo fisso in lingua inglese. È possibile sostituire le etichette dei report con nuovi nomi di Excel che riempiono le etichette con testo dipendente dalla lingua utilizzando il formato ER per le [etichette](#AddMmLabels), come fatto per le espressioni dipendenti dalla lingua nel mapping del modello configurato. In questo caso, le etichette ER devono essere aggiunte nel formato ER modificabile.

Come mostra la figura seguente, l'intestazione del report personalizzato è stata specificata per consentire a Excel di eseguire il paging.

![Intestazione del report personalizzato nel modello Excel fornito](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>Progettare un formato

In qualità di utente nel ruolo di consulente funzionale per la creazione di report elettronici, è necessario creare una nuova configurazione ER che contenga un componente di [formato](general-electronic-reporting.md#FormatComponentOutbound). È necessario configurare il componente del formato per specificare come un modello di report verrà compilato con i dati richiesti in fase di esecuzione.

Completando i passaggi nella sezione [Importare una configurazione in un formato progettato](#FormatImport), è possibile importare il formato richiesto dal file XML fornito. In alternativa, puoi completare i passaggi nella sezione [Creare una nuova configurazione di formato](#FormatCreate) per progettare questo formato da zero.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>Importare una configurazione in un formato progettato

1. Scaricare il file [Questionarios format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salvarlo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella riquadro Azioni, selezionare **Scambia** \> **Carica da file XML**.
5. Selezionare **Sfoglia**, quindi trovare e selezionare il file **Questionarios format.version.1.1.xml**.
6. Selezionare **OK** per importare la configurazione.

Per continuare, saltare la procedura successiva, [Creare una nuova configurazione di formato](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>Creare una nuova configurazione di formato
 
1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Modello di questionario**.
3. Selezionare **Crea configurazione**.
4. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nel campo **Nuovo**, selezionare **Formato basato sul modello dati Questionarios**.
    2. Nel campo **Nome**, immettere **Report dei questionari**.
    3. Nel campo **Versione modello dati**, selezionare **1**.

        > [!NOTE]
        > - Se si seleziona una versione specifica del modello di dati di base, la struttura della versione corrispondente del modello di dati verrà presentata come struttura dell'origine dati **Modello** nel formato creato.
        > - È possibile lasciare vuoto questo campo. In tal caso, la struttura della versione **Bozza** del modello di dati verrà presentata come la struttura dell'origine dati **Modello** nel formato creato. È quindi possibile regolare il modello e visualizzare immediatamente tali regolazioni nel formato. Questo approccio potrebbe migliorare l'efficienza della progettazione della soluzione ER quando si configurano contemporaneamente il modello di dati, il mapping del modello e il formato.
        > - Se selezioni una versione specifica del modello di dati di base, puoi passare all'utilizzo della versione **Bozza** in un secondo momento, quando inizi a modificare un formato.

    4. Nel campo **Definizione modello dati**, selezionare la definizione **Root**.

5. Selezionare **Crea configurazione** per creare la configurazione.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>Importare un modello di report

1. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Report dei questionari**.
2. Selezionare **Progettazione** per iniziare a configurare un formato personalizzato.
3. Nella pagina **Progettazione formati**, nel riquadro Azioni, selezionare **Importa** \> **Importa da Excel**.
4. Nella finestra di dialogo, effettuare le seguenti operazioni:

    1. Selezionare **Aggiungi modello**.
    2. Trovare e selezionare il file salvato localmente **Questionarios report template.xslx**, quindi selezionare **Apri**.
    3. Selezionare **OK** per importare il modello.

    ![Importazione di un modello di report](./media/er-quick-start1-template-import.png)

L'elemento formato **Excel\\File** viene aggiunto automaticamente al formato modificabile come elemento radice. Inoltre, l'elemento di formato **Excel\\Intervallo** o **Excel\\Cella** viene aggiunto automaticamente per ogni nome Excel riconosciuto del modello importato. Il formato **Excel\\Intestazione** con l'elemento **Stringa** viene aggiunto automaticamente per riflettere le impostazioni dell'intestazione del modello importato.

![Struttura del formato che include elementi aggiunti automaticamente nella finestra di progettazione delle operazioni ER](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>Configurare un formato

1. Nella pagina **Progettazione formati**, nella struttura ad albero del formato, selezionare l'elemento radice **Excel**.
2. Nella scheda **Formato** sul lato destro della pagina, nel campo **Nome**, immettere <a name="AddFormatRootElement"></a>**Report**.
3. Nel campo **Preferenza lingua**, selezionare **Preferenza utente** per eseguire il report nella lingua preferita dall'utente.
4. Nel campo **Preferenza cultura**, selezionare **Preferenza utente** per eseguire il report nella cultura preferita dall'utente.

    Per informazioni su come specificare i contesti di lingua e cultura per un processo ER, vedere [Progettare report multilingue](er-design-multilingual-reports.md).

    ![Configurazione delle impostazioni di lingua e cultura per il report progettato nella progettazione dell'operazione ER](./media/er-quick-start1-template-format-structure1.png)

5. Nella struttura ad albero del formato, espandere il nodo radice e quindi selezionare **ResultsGroup**.
6. Nella scheda **Formato**, nel campo **Direzione replica**, selezionare **Nessuna replica**, perché non ti aspetti di avere più gruppi di risultati per un singolo questionario.

    ![Definizione della direzione della replica per gli elementi del formato Intervallo nella finestra di progettazione dell'operazione ER](./media/er-quick-start1-template-format-structure2.png)

7. Selezionare **Salva**.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>Definire l'associazione dati per un titolo di report

È necessario specificare un'associazione dati per un elemento di formato utilizzato per compilare il titolo di un report generato.

1. Nella pagina **Progettazione formati**, nella scheda **Mapping** sulla destra, selezionare l'elemento **Report\\ReportTitle**.
2. Selezionare **Modifica formula**.
3. Nell'editor delle formule, selezionare **Traduci**.
4. Nella finestra di dialogo **Traduzione testo**, effettuare le seguenti operazioni:

    1. Nel campo **ID etichetta**, immettere **ReportTitle**.
    2. Nel campo **Testo in lingua predefinita**, immettere **Report dei questionari**.
    3. Selezionare **Traduci** e quindi selezionare **Salva**.
    4. Selezionare **Traduci** per chiudere la finestra di dialogo **Traduzione testo**.

5. Chiudere l'editor delle formule.

    ![Configurazione dell'associazione per inserire il titolo di un report generato](./media/er-quick-start1-add-report-title-label.png)

È possibile utilizzare questa tecnica per rendere tutte le altre etichette del modello corrente dipendenti dalla lingua. Per informazioni su come tradurre le etichette aggiunte di una singola configurazione ER in tutte le lingue supportate, vedere [Progettare report multilingue](er-design-multilingual-reports.md).

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>Esaminare l'origine dati del modello

1. Nella pagina **Progettazione formati**, nella scheda **Mapping**, selezionare l'origine dati <a name="ModelDSName"></a>**modello** che rappresenta il modello di dati di base di questo formato ER.
2. Selezionare **Modifica**.
3. Rivedi le informazioni nella finestra di dialogo **Proprietà dell'origine dati**. Questa origine dati rappresenta la versione 1 del componente del modello di dati **Questionari** che risiede nella configurazione ER **Modello questionario**.

![Proprietà dell'origine dati del modello nella pagina della progettazione dell'operazione ER](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>Associare gli elementi di formato ai campi di un'origine dati

Per specificare la modalità di compilazione di un modello in fase di esecuzione, è necessario associare ogni elemento di formato a un nome Excel appropriato a un singolo campo dell'origine dati di questo formato.

1. Nella pagina **Progettazione formati**, nella struttura ad albero del formato, selezionare l'elemento di formato **Report\\CompanyName**.
2. Nella scheda **Mapping**, selezionare il campo dell'origine dati **model.CompanyName** del tipo **Stringa**.
3. Selezionare **Associa** per inserire un nome di società in un modello.
4. Nella struttura ad albero del formato, selezionare l'elemento **Report\\Questionario**.
5. Nella scheda **Mapping**, selezionare il campo dell'origine dati **model.Questionario** del tipo **Elenco di record**.
6. Selezionare **Associa**.
7. Selezionare **Mostra dettagli** per visualizzare maggiori dettagli per gli elementi di formato.

    L'elemento di formato dell'intervallo **Questionario** è configurato come replicato verticalmente. Quando è associato a un'origine dati del tipo **Elenco di record**, l'intervallo **Gestione questionari** appropriato del modello Excel viene ripetuto per ogni record dell'origine dati associata.
 
    ![Associazione dell'elemento di formato dell'intervallo del questionario alle origini dati dell'elenco di record appropriate nella progettazione dell'operazione ER](./media/er-quick-start1-bindings1.png)

    Poiché l'intervallo **Gestione questionari** del modello Excel è definito tra le righe 5 e 14, queste righe vengono ripetute per ogni questionario segnalato.

    ![Righe nel modello Excel che verranno ripetute in un report generato per ogni record delle origini dati dell'elenco dei record](./media/er-quick-start1-template-questionnaire-range.png)

8. Configurare associazioni simili per gli elementi di formato rimanenti, come descritto nella tabella seguente.

    > [!NOTE]
    > In questa tabella, le informazioni nella colonna "Percorso origine dati" presuppongono che la funzionalità ER del [percorso relativo](relative-path-data-bindings-er-models-format.md) sia abilitata.

    | Formatta percorso elemento                                      | Percorso origine dati |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Questionario                                     | **model.Questionario** |
    | Excel\\Questionario\\Active                             | **\@.Active**, dove **\@** è **model.Questionario** |
    | Excel\\Questionario\\Code                               | **\@.Code** |
    | Excel\\Questionario\\Description                        | **\@.Description** |
    | Excel\\Questionario\\QuestionarioType                  | **\@.QuestionarioType** |
    | Excel\\Questionario\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Questionario\\ResultsGroup\\Code\_               | **\@.ResultsGroup.Code** |
    | Excel\\Questionario\\ResultsGroup\\Description\_        | **\@.ResultsGroup.Description** |
    | Excel\\Questionario\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Questionario\\Domanda                           | **\@.Domanda** |
    | Excel\\Questionario\\Domanda\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, dove **\@** è **model.Questionario.Domanda** |
    | Excel\\Questionario\\Domanda\\Id                       | **\@.Id** |
    | Excel\\Questionario\\Domanda\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Questionario\\Domanda\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Questionario\\Domanda\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Questionario\\Domanda\\Text                     | **\@.Text** |
    | Excel\\Questionario\\Domanda\\Answer                   | **\@.Answer** |
    | Excel\\Questionario\\Domanda\\Answer\\CorrectAnswer    | **\@.CorrectAnswer**, dove **\@** è **model.Questionario.Answer** |
    | Excel\\Questionario\\Domanda\\Answer\\Points           | **\@.Points** |
    | Excel\\Questionario\\Domanda\\Answer\\Text             | **\@.Text** |

9. Al termine, selezionare **Salva**.

La figura seguente mostra lo stato finale delle associazioni di dati configurate nella pagina **Progettazione formato**.

![Associazioni di dati configurate nella progettazione delle operazioni ER](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> L'intera raccolta di origini dati e associazioni specificate rappresenta un componente di mapping del formato configurato. Questo mapping del formato viene chiamato quando si esegue il formato configurato per la generazione di report.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>Eseguire un formato progettato da ER

È ora possibile eseguire un formato progettato a scopo di verifica dalla pagina **Configurazioni**.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazione**, nella struttura delle configurazioni, espandere **Modello di questionario**, quindi selezionare **Report questionario**.
3. Selezionare **Progettazione** per la versione del formato con stato **Bozza**.
4. Nella pagina **Progettazione formati**, selezionare **Esegui**.
5. Nella finestra di dialogo **Parametri ER**, nella scheda **Record da includere**, configurare l'opzione di filtro in modo che solo il questionario **SBCCrsExam** sia incluso.
6. Selezionare **OK** per confermare l'opzione di filtro.
7. Selezionare **OK** per eseguire il report.
8. Esaminare il report generato.

Per [impostazione predefinita](electronic-reporting-destinations.md#default-behavior), un report generato viene consegnato come file Excel da poter scaricare. Le seguenti illustrazioni mostrano due pagine del report generato in formato Excel.

![Esempio di un report generato in formato Excel, pagina 1](./media/er-quick-start1-report1a.png)

![Esempio di un report generato in formato Excel, pagina 2](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>Ottimizzare un formato progettato

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>Modificare un formato per cambiare il nome di un documento generato

Per impostazione predefinita, un documento generato viene denominato utilizzando l'alias dell'utente corrente. Modificando il formato, è possibile modificare questo comportamento in modo che un documento generato venga denominato in base alla logica personalizzata. Ad esempio, il nome di un documento generato può essere basato sulla data e l'ora della sessione corrente e sul titolo del report.

1. Nella pagina **Progettazione formati** selezionare l'elemento radice **Report**.
2. Nella scheda **Mapping**, selezionare **Modifica nome file**.
3. Nel campo **Formula**, immettere **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW() "yyyy-MM-dd hh-mm-ss"))**.
4. Selezionare **Salva**, quindi chiudere l'editor di formule.
5. Selezionare **Salva**.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>Modificare un formato per cambiare l'ordine delle domande

Le domande non sono ordinate correttamente in un report generato. Puoi cambiare l'ordine modificando il formato.

1. Nella pagina **Progettazione formati** selezionare l'elemento radice **Report**.
2. Nella scheda **Mapping**, nella struttura ad albero del formato, espandere **Report\\Questionario\\Domanda**.

    ![Elemento formato domanda del tipo Intervallo nella progettazione delle operazioni ER](./media/er-quick-start1-bindings3.png)

3. Nella scheda **Mapping**, selezionare **model.Questionario**.
4. Selezionare **Aggiungi** \> **Funzioni\\Campo calcolato**, quindi nel campo **Nome**, immettere **OrderedQuestions**.
5. Selezionare **Modifica formula**.
6. Nell'editor di formule, nel campo **Formula**, immettere **ORDERBY (model.Questionario.Domanda, model.Questionario.Domanda.SequenceNumber)** per ordinare l'elenco delle domande del questionario corrente in base al numero di sequenza.
7. Selezionare **Salva**, quindi chiudere l'editor di formule.
8. Selezionare **OK** per completare l'inserimento di un nuovo campo calcolato.
9. Nella scheda **Mapping**, selezionare **model.Questionario.OrderedQuestions**.
10. Nella struttura ad albero del formato, selezionare **Excel\\Questionario\\Domanda**.
11. Selezionare **Associa**, quindi confermare che il percorso **model.Questionario.Questions** corrente è sostituito dal nuovo percorso **model.Questionario.OrderedQuestions** in tutte le associazioni di elementi nidificati.
12. Selezionare **Salva**.

![Associazione dell'elemento di formato Domanda all'origine dati OrderedQuestions configurata nella finestra di progettazione delle operazioni ER](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>Eseguire un formato modificato da ER

È ora possibile eseguire un formato modificato a scopo di test dal framework ER.

1. Nella pagina **Progettazione formati**, selezionare **Esegui**.
2. Nella finestra di dialogo **Parametri ER**, nella scheda **Record da includere**, configurare l'opzione di filtro in modo che solo il questionario **SBCCrsExam** sia incluso.
3. Selezionare **OK** per confermare l'opzione di filtro.
4. Selezionare **OK** per eseguire il report.
5. Esaminare il report generato.

La figura seguente mostra un report generato in formato Excel in cui le domande sono ordinate correttamente.

![Report generato in formato Excel che ha correttamente ordinato le domande](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>Completare la progettazione del formato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di questionario**, quindi selezionare **Report questionario**.
3. Nella scheda **Versioni**, selezionare la versione della configurazione con stato **Bozza**.
4. Selezionare **Cambia stato** \> **Completato**.

Lo stato della versione 1.1 di questa configurazione viene modificato da **Bozza** a **Completato**. La versione 1.1 non può più essere modificata. Questa versione contiene il formato configurato e può essere utilizzata per stampare il report personalizzato. La versione 1.2 di questa configurazione viene creata e ha stato **Bozza**. Puoi modificare questa versione per regolare il formato del tuo report **Gestione questionari**.

![Le versioni della configurazione ER modificabile nella pagina Configurazioni](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> Il formato configurato è la progettazione del report **Gestione questionari** e non contiene alcuna relazione con gli elementi specifici di Finance.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>Sviluppare gli elementi dell'applicazione per chiamare il report progettato

In qualità di utente nel ruolo Amministratore di sistema, è necessario sviluppare una nuova logica in modo che il formato ER configurato possa essere chiamato dall'interfaccia utente dell'applicazione per generare il report personalizzato. Attualmente, ER non offre alcuna capacità per configurare questo tipo di logica. Pertanto, è necessario un lavoro di ingegneria. 

Per sviluppare la nuova logica, è necessario distribuire una topologia che supporti la compilazione continua. Per ulteriori informazioni, vedere [Distribuire topologie che supportano la compilazione continua e l'automazione dei test](../perf-test/continuous-build-test-automation.md). È inoltre necessario avere accesso all'ambiente di sviluppo per questa topologia. Per ulteriori informazioni sulle API ER disponibili, vedere [API framework report elettronici](er-apis-app73.md).

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>Modificare il codice sorgente

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>Aggiungere una categoria di contratto dati

Aggiungere la nuova categoria **QuestionariosErReportContract** al tuo progetto Microsoft Visual Studio e scrivere il codice che specifica il contratto dati da utilizzare per eseguire il formato ER configurato.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>Aggiungere una classe di creazione dell'interfaccia utente

Aggiungere la nuova classe **QuestionariosErReportUIBuilder** al progetto Visual Studio e scrivere il codice per generare una finestra di dialogo di runtime che verrà utilizzata per cercare l'ID di mapping del formato del formato ER che deve essere eseguito. Il codice fornito cerca solo i formati ER che contengono un'origine dati del tipo **Modello di dati** che fa riferimento al modello di dati **[Gestione questionari](#DataModeName)** utilizzando la definizione **[Radice](#RootDefinitionName)**.

> [!NOTE]
> In alternativa, puoi utilizzare i punti di integrazione ER per filtrare i formati ER. Per ulteriori informazioni, vedere [API per mostrare una ricerca di mapping del formato](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>Aggiungere una categoria di provider di dati

Aggiungere la nuova classe **QuestionariosErReportDP** al tuo progetto Visual Studio e scrivere il codice che introduce il provider di dati da utilizzare per eseguire il formato ER configurato. Il codice fornito include solo il contratto dati per questo provider di dati.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>Aggiungere un file di etichette

Aggiungere il nuovo file di etichette **QuestionariosErReportLabels\_en-US** nel progetto Visual Studio e specificare le seguenti etichette per le nuove risorse dell'interfaccia utente:

- L'atichetta **\@QuestionariosReport** per una nuova voce di menu che contiene il seguente testo in inglese americano (en-US): **Report sui questionari (fornito da ER)**
- L'etichetta **\@QuestionariosReportBatchJobDescription** per una posizione di lavoro se un formato ER selezionato è pianificato per l'esecuzione come processo batch

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>Aggiungere una classe di servizio dei report

Aggiungere la nuova classe **QuestionariosErReportService** al progetto Visual Studio e scrivere il codice che chiama un formato ER, lo identifica tramite un ID di mapping del formato e fornisce un contratto dati come parametro.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

Quando è necessario utilizzare un formato ER che esegue i dati dell'applicazione, è necessario configurare un'origine dati del tipo **Modello di dati** nel mapping del formato. Questa origine dati fa riferimento a una parte specifica del modello dati specificato utilizzando un'unica definizione radice. Quando il formato ER viene eseguito, chiama questa origine dati per accedere al mapping del modello ER appropriato configurato per un determinato modello e definizione di radice.

Tutte le informazioni che potresti preparare nel codice sorgente e archiviare come parte del contratto dati possono essere passate al formato ER in esecuzione utilizzando un mapping del modello ER di questo tipo. Nel mapping del modello ER, è necessario configurare un'origine dati del tipo **Oggetto** che fa riferimento alla classe **[QuestionariosErReportContract](#DataContractClass)**. Per identificare un mapping del modello, è necessario specificare un'origine dati che richiami questo mapping del modello. Nel codice fornito, questa origine dati specificata dalla costante **ERModelDataSourceName** che ha il valore del **[modello](#ModelDSName)**. Per identificare quale origine dati viene utilizzata per esporre il contratto dati nella mappatura del modello, è necessario specificare un nome dell'origine dati. Nel codice fornito, questo nome viene specificato dalla costante **ParametersDataSourceName** che ha il valore <a name="DataContractDSName"></a>**RunTimeParameters**.

> [!NOTE]
> In un nuovo ambiente, potrebbe essere necessario aggiornare i metadati ER in modo che questo tipo di classe sia disponibile nella finestra di progettazione del mapping del modello ER. Per ulteriori informazioni, vedere [Configurare il framework ER](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>Aggiungere una classe di controller dei report

Aggiungere la nuova classe **QuestionariosErReportController** al progetto Visual Studio e scrivere codice che esegue un formato ER in modalità sincrona o in batch, come preferito, nella finestra di dialogo costruita in base alla logica della classe **QuestionariosErReportUIBuilder**.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>Aggiungere una voce di menu

Aggiungere la nuova voce di menu **QuestionariosErReport** al progetto Visual Studio. Nella proprietà **Oggetto**, questa voce di menu si riferisce alla classe **QuestionariosErReportController** e viene utilizzato per specificare un'autorizzazione utente per selezionare ed eseguire un formato ER. Nella proprietà **Etichetta**, questa voce di menu si riferisce all'etichetta **\@QuestionariosReport** creata in precedenza, in modo che il testo corretto venga visualizzato nell'interfaccia utente dell'applicazione.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>Aggiungere una voce a un menu

Aggiungere il menu **KM** esistente al progetto Visual Studio. È necessario aggiungere una nuova voce **QuestionariosErReport** del tipo **Output** a questo menu. Questa voce di menu deve fare riferimento alla voce di menu **QuestionariosErReport** descritta nella sezione precedente.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Costruire un progetto Visual Studio

Creare il progetto per rendere disponibile agli utenti una nuova voce di menu.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>Eseguire un formato dall'applicazione

1. Andare a **Questionario** \> **Progettazione** \> **Report sui questionari (fornito da ER)**.

    ![Selezionando la voce di menu Report sui questionari (fornito da ER) nel modulo Gestione questionari per eseguire il formato ER configurato](./media/er-quick-start1-application-menu-modified.png)

2. Nella finestra di dialogo, nel campo **Mapping formato**, selezionare **Report sui questionari**.
3. Selezionare **OK**.
4. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, nella scheda **Record da includere**, configurare l'opzione di filtro in modo che solo il questionario **SBCCrsExam** sia incluso.
5. Selezionare **OK** per confermare l'opzione di filtro.
6. Selezionare **OK** per eseguire il report.

    ![Impostazione dei criteri di selezione nella finestra di dialogo Report elettronici](./media/er-quick-start1-report-run-dialog-page.png)

7. Esaminare il report generato.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>Ottimizzare una soluzione ER progettata

È possibile modificare la soluzione ER configurata in modo che utilizzi la classe del fornitore di dati sviluppata per accedere ai dettagli del formato ER in esecuzione e in modo che inserisca il nome di questo formato ER in un report generato.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>Modificare un mapping di modello

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>Aggiungere origini dati per accedere a un oggetto di contratto dati

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di questionario**, quindi selezionare **Mapping questionario**.
3. Selezionare **Progettazione** per aprire la pagina **Modello per mapping origine dati**.
4. Selezionare **Progettazione** per aprire il mapping selezionato nella progettazione del mapping del modello.
5. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Oggetto**.
6. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
7. Nella finestra di dialogo, nel campo **Nome**, immettere **[RunTimeParameters](#DataContractDSName)**, come definito nel codice sorgente della classe **QuestionariosErReportService**.
8. Nel campo **Classe**, immettere **[QuestionariosErReportContract](#DataContractClass)**, che è stato codificato in precedenza.
9. Selezionare **OK**.
10. Espandere **RunTimeParameters**.

L'origine dati aggiunta fornisce informazioni sull'ID record del mapping del formato ER in esecuzione.

![Origine dati aggiunta nella finestra di progettazione del mapping del modello ER](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>Aggiungere un'origine dati per accedere ai record di mapping del formato ER

Continuare a modificare il mapping del modello selezionato aggiungendo un'origine dati per accedere ai record di mapping in formato ER.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Tabella dei record**.
2. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
3. Nella finestra di dialogo, nel campo **Nome**, immettere **ER1**.
4. Nel campo **Tabella**, immettere **ERFormatMappingTable**.
5. Selezionare **OK**.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>Aggiungere un'origine dati per accedere al record di mapping di un formato ER in esecuzione

Continuare a modificare il mapping del modello selezionato aggiungendo un'origine dati per accedere al record di mapping del formato ER in esecuzione.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, selezionare **Funzioni\\Campo calcolato**.
2. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
3. Nella finestra di dialogo, nel campo **Nome**, immettere **ER2**.
4. Selezionare **Modifica formula**.
5. Nell'editor di formule, nel campo **Formula**, immettere **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.
6. Selezionare **Salva**, quindi chiudere l'editor di formule.
7. Selezionare **OK**.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>Immettere il nome del formato ER in esecuzione nel modello di dati

Continuare a modificare il mapping del modello selezionato in modo che il nome del formato ER in esecuzione venga immesso nel modello di dati.

1. Nella pagina **Progettazione mapping modello** nel riquadro **Modello di dati**, espandere **ExecutionContext**, quindi selezionare **ExecutionContext\\FormatName**.
2. Nel riquadro **Modello di dati**, selezionare **Modifica** per configurare un'associazione di dati per il campo del modello di dati selezionato.
3. Nell'editor di formule, nel campo **Formula**, immettere **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.
4. Selezionare **Salva**, quindi chiudere l'editor di formule.

Poiché hai usato il campo **FormatName**, il mapping del modello configurato ora espone il nome di un formato ER che chiama questo mapping del modello durante l'esecuzione.

![Associazione del campo del modello di dati al metodo dell'origine dati aggiunta nella progettazione di mapping del modello ER](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>Completare la progettazione del mapping del modello

1. Nella pagina **Progettazione mapping modello**, selezionare **Salva**.
2. Chiudere la pagina.
3. Chiudere la pagina Mapping modello.
4. Nella pagina **Configurazioni**, nella struttura delle configurazioni, assicurarsi che la configurazione **Mapping del questionario** sia ancora selezionata. Quindi, nella scheda **Versioni**, selezionare la versione della configurazione con stato **Bozza**.
5. Selezionare **Cambia stato** \> **Completato**.

Lo stato della versione 1.2 di questa configurazione viene modificato da **Bozza** a **Completato**. La versione 1.2 non può più essere modificata. Questa versione contiene il mapping del modello configurato e può essere utilizzata come base per le altre configurazioni ER. La versione 1.3 di questa configurazione viene creata e ha stato **Bozza**. Puoi modificare questa versione per regolare il mapping del modello di dati **Gestione questionari**.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>Modificare un formato

È possibile modificare il formato ER configurato in modo che il suo nome venga visualizzato nel piè di pagina di un report generato quando viene eseguito il formato ER.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>Aggiungere un nuovo elemento di formato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di questionario**, quindi selezionare **Report questionario**.
3. Selezionare **Progettazione**.
4. Nella pagina **Progettazione formati** selezionare l'elemento radice **Report**.
5. Selezionare **Aggiungi** per aggiungere un nuovo elemento di formato nidificato per l'elemento radice **Report** selezionato.
6. Selezionare **Excel\\Piè di pagina**.
7. Nel campo **Nome**, immettere **Piè di pagina**.
8. Selezionare **Report\Piè di pagina**, quindi selezionare **Aggiungi**.
9. Selezionare **Testo\\Stringa**.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>Associare l'elemento del formato aggiunto

1. Nella pagina **Progettazione formati**, nella scheda **Mapping**, nella struttura ad albero del formato, per l'elemento attivo **Piè di pagina\\Stringa**, selezionare **Modifica formula**.
2. Nell'editor di formule, nel campo **Formula**, immettere **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.
3. Selezionare **Salva**, quindi chiudere l'editor di formule.
4. Selezionare **Salva**.

Il formato configurato è stato ora modificato in modo che il suo nome venga inserito nel piè di pagina di un report generato utilizzando l'elemento **Piè di pagina\\Stringa**.

![Aggiunta dell'elemento del formato Piè di pagina al formato configurato nella finestra di progettazione delle operazioni ER](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>Completare la progettazione del formato

1. Chiudere la pagina **Progettazione formati**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni, assicurarsi che la configurazione **Report questionario** sia ancora selezionata. Quindi, nella scheda **Versioni**, selezionare la versione della configurazione con stato **Bozza**.
3. Selezionare **Cambia stato** \> **Completato**.

Lo stato della versione 1.2 di questa configurazione viene modificato da **Bozza** a **Completato**. La versione 1.2 non può più essere modificata. Questa versione contiene il formato configurato e può essere utilizzata come base per le altre configurazioni ER. La versione 1.3 di questa configurazione viene creata e ha stato **Bozza**. È possibile modificare questa versione per regolare il report **Gestione questionari**.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>Eseguire un formato dall'applicazione

1. Andare a **Questionario** \> **Progettazione** \> **Report sui questionari (fornito da ER)**.
2. Nella finestra di dialogo, nel campo **Mapping formato**, selezionare **Report sui questionari**.
3. Selezionare **OK**.
4. Nella finestra di dialogo **Parametri ER**, nella scheda **Record da includere**, configurare l'opzione di filtro in modo che solo il questionario **SBCCrsExam** sia incluso.
5. Selezionare **OK** per confermare l'opzione di filtro.
6. Selezionare **OK** per eseguire il report.
7. Verificare il report generato in formato Excel.

Si noti che il piè di pagina del report generato contiene il nome del formato ER utilizzato per generarlo.

![Report generato in formato Excel](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>Eseguire un formato da ER

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di questionario**, quindi selezionare **Report questionario**.
3. Nel Riquadro azioni selezionare **Esegui**.
4. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, nella scheda **Record da includere**, configurare l'opzione di filtro in modo che solo il questionario **SBCCrsExam** sia incluso.
5. Selezionare **OK** per confermare l'opzione di filtro.
6. Selezionare **OK** per eseguire il report.
7. Verificare il report generato in formato Excel.

Si noti che il piè di pagina del report generato non contiene il nome del formato ER utilizzato per generarlo, perché l'oggetto del contratto dati non è stato passato al mapping del modello in esecuzione quando è stato chiamato dal formato ER da cui è stato eseguito dal report elettronico.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>Configurare una destinazione del formato per l'anteprima su schermo

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Destinazione report elettronici**.
2. Nella pagina **Destinazione report elettronici**, aggiungere un record di destinazione per il formato ER **Report del questionario**.
3. Nella scheda **Destinazione file**, configurare la [destinazione](er-destination-type-screen.md) **Schermo** per il componente del formato **Report** che è stato [aggiunto](#AddFormatRootElement) come elemento radice del formato ER **Rapporto del questionario** configurato.
4. Nella scheda **Impostazioni di conversione PDF**, configurare la destinazione in cui convertire un report in [formato PDF](electronic-reporting-destinations.md#OutputConversionToPDF) che utilizza l'orientamento della pagina **Orizzontale**.

![Configurazione della destinazione Schermo personalizzata per il formato ER nella pagina Destinazione report elettronici](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>Eseguire un formato dall'applicazione per visualizzarlo in anteprima come documento PDF

1. Andare a **Questionario** \> **Progettazione** \> **Report sui questionari (fornito da ER)**.
2. Nella finestra di dialogo, nel campo **Mapping formato**, selezionare **Report sui questionari**.
3. Selezionare **OK**.
4. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, nella scheda **Record da includere**, configurare l'opzione di filtro in modo che solo il questionario **SBCCrsExam** sia incluso.
5. Selezionare **OK** per confermare l'opzione di filtro.

    Nella scheda **Destinazioni**, notare che il campo **Output** è impostato su **Schermo**. Se si desidera modificare la destinazione configurata, selezionare **Modifica**.

    ![Finestra di dialogo Runtime report ER in cui è possibile modificare la destinazione configurata](./media/er-quick-start1-run-settings.png)

6. Selezionare **OK** per eseguire il report.
7. Verificare il report generato in formato PDF.

    ![Anteprima su schermo del report generato in formato PDF](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
- [Progettare report multilingue](er-design-multilingual-reports.md)
- [API framework report elettronici](er-apis-app73.md)
- [Funzione CASO](er-functions-logical-case.md)
- [Funzione CONCATENATE](er-functions-text-concatenate.md)
- [Funzione DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [Funzione FILTER](er-functions-list-filter.md)
- [Funzione FIRSTORNULL](er-functions-list-firstornull.md)
- [Funzione FORMAT](er-functions-text-format.md)
- [Funzione IF](er-functions-logical-if.md)
- [Funzione ORDERBY](er-functions-list-orderby.md)
- [Funzione SESSIONNOW](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]