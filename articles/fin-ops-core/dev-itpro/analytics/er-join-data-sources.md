---
title: Utilizzare le origini dati JOIN nei mapping del modello ER per ottenere i dati da più tabelle dell'applicazione
description: In questo argomento viene descritto come utilizzare le origini dati di tipo JOIN nella creazione di report elettronici (ER).
author: NickSelin
ms.date: 04/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: be5646eaf395310c8b34586ef1274a41b5b97029
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944728"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Utilizzare le origini dati JOIN per ottenere i dati da più tabelle dell'applicazione nei mapping del modello di report elettronici (ER)

[!include[banner](../includes/banner.md)]

Durante la configurazione di mapping o formati del modello di report elettronici (ER), è possibile [aggiungere](#review) le origini dati richiesti di tipo **Join**. In fase di progettazione, un'origine dati **Join** è configurata come un set di diverse origini dati, ognuna delle quali restituisce un elenco di record. Per ogni origine dati tranne la prima, è necessario definire le condizioni necessarie per unire i record delle origini dati correnti e precedenti. In fase di esecuzione, un'origine dati configurata di tipo **Join** [restituisce](#executeERformat) un unico elenco di record uniti contenente campi dai record di origini dati nidificate.

Attualmente sono supportati i seguenti tipi di join:

- Left outer join:
    - Unire tutti i record della prima origine dati (all'estrema sinistra) e quindi qualsiasi corrispondenza in base ai record delle condizioni configurate della seconda origine (all'estrema destra).
- Right inner join:
    - Unire solo i record della prima origine dati (all'estrema sinistra) e quindi solo i record della seconda origine (all'estrema destra) corrispondenti tra loro in base alle condizioni configurate.

Nell'origine dati configurata **Join**, quando tutte le origini dati sono di tipo **Record di tabella**, l'esecuzione dell'origine dati Join può essere [effettuata a livello di database](#analyze) utilizzando una singola istruzione SQL. Questo rendiconto riduce il numero di chiamate al database, migliorando le prestazioni di mapping del modello. In caso contrario, l'esecuzione dell'origine dati **Join** viene eseguita in memoria.

> [!NOTE]
> L'utilizzo della funzione **VALUEIN** nelle espressioni ER che specificano le condizioni per il join dei record delle origini dati di tipo Join non è ancora supportato. Consultare la pagina [Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md) per altri dettagli su questa funzione.

Per ulteriori informazioni su questa funzionalità, completare l'esempio in questo argomento.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Esempio: Utilizzare le origini dati JOIN in mapping del modello ER

I seguenti passaggi spiegano come l'amministratore di sistema o lo sviluppatore di report elettronici può configurare un mapping del modello di report elettronici (ER) per ottenere dati da più tabelle di applicazioni contemporaneamente utilizzando origini dati di tipo **Join** per migliorare le prestazioni di accesso ai dati. Queste operazione possono essere eseguite per qualsiasi società di Dynamics 365 Finance o Regulatory Configuration Service (RCS).

### <a name="prerequisites"></a>Prerequisiti

Per completare gli esempi in questo argomento, è necessario avere accesso a una delle seguenti opzioni a seconda del servizio utilizzato per completare questi passaggi:

**Accesso a Finance per uno dei seguenti ruoli:**

- Sviluppatore per la creazione di report elettronici
- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

**Accesso a RCS per uno dei seguenti ruoli:**

- Sviluppatore per la creazione di report elettronici
- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

È necessario dapprima completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

In anticipo, è inoltre necessario scaricare e salvare i seguenti file di configurazione ER di esempio:

| **Descrizione contenuto**  | **Nome file**   |
|--------------------------|-----------------|
| File di configurazione **Modello di dati ER** di esempio, utilizzato come origine dati per gli esempi.| [Model to learn JOIN data sources.version.1.1.xml](https://download.microsoft.com/download/5/c/1/5c1d8a57-6ebd-425b-bc5d-c71dde92c6af/ModeltolearnJOINdatasources.version.1.xml) |
| File di configurazione **Mapping del modello ER** di esempio che implementa il modello di dati ER per gli esempi. | [Mapping to learn JOIN data sources.version.1.1.xml](https://user-images.githubusercontent.com/19827601/115923048-86b10400-a432-11eb-9e57-c37a02effcb4.png)|
| File di configurazione **Formato ER** di esempio. Questo file descrive i dati per popolare il componente del formato ER per gli esempi. | [Format to learn JOIN data sources.version.1.1.xml](https://download.microsoft.com/download/f/f/8/ff8f1b48-14d0-4c73-9145-bcdf8b5265bc/FormattolearnJOINdatasources.version.1.1.xml) |

### <a name="activate-a-configurations-provider"></a>Attivare un provider di configurazioni

1. Accedere a Finance o RCS nella prima sessione del Web browser.
2. Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.
3. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, verificare che il provider di configurazione per la società di esempio [Litware, Inc.](http://www.litware.com) sia elencato e contrassegnato come **Attivo**. Se il provider di configurazione non è visualizzato, seguire i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Area di lavoro Creazione di report elettronici](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>Importare i file di configurazione ER di esempio

1. Selezionare **Configurazioni report**.
2. Importare il file di configurazione del modello di dati ER.
    1. Selezionare **Scambia**.
    2. Selezionare **Carica da file XML**.
    3. Selezionare **Sfoglia** per trovare il file **Model to learn JOIN data sources.version.1.1.xml**.
    4. Selezionare **OK**.
3. Importare il file di configurazione del mapping del modello ER.
    1. Selezionare **Scambia**.
    2. Selezionare **Carica da file XML**.
    3. Selezionare **Sfoglia** per trovare il file **Mapping to learn JOIN data sources.version.1.1.xml**.
    4. Selezionare **OK**.
4. Importare il file di configurazione del formato ER.
    1. Selezionare **Scambia**.
    2. Selezionare **Carica da file XML**.
    3. Selezionare **Sfoglia** per trovare il file **Format to learn JOIN data sources.version.1.1.xml**.
    4. Selezionare **OK**.
5. Nell'albero delle configurazioni, espandere l'elemento **Model to learn JOIN data sources** nonché altri elementi di modello (se disponibili).
6. Osservare l'elenco delle configurazioni ER nell'albero, nonché i dettagli della versione nella scheda dettaglio **Versioni**: verranno utilizzati come origine dati per il report di esempio.

    ![Pagina delle configurazioni per la creazione di report elettronici](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Attivare le opzioni di traccia dell'esecuzione

1. Selezionare **CONFIGURAZIONI**.
2. Selezionare **Parametri utente**.
3. Impostare i parametri di traccia dell'esecuzione come riportato nella schermata di seguito.

    ![Pagina dei parametri utente per la creazione di report elettronici](./media/GER-JoinDS-Parameters.PNG)

    Con questi parametri attivi, per ogni esecuzione del file di formato ER importato, verrà generata la traccia dell'esecuzione. Utilizzando i dettagli della traccia dell'esecuzione generata, è possibile analizzare l'esecuzione del formato ER e dei componenti di mapping del modello ER. Visitare la pagina [Generare la traccia dell'esecuzione del formato ER per risolvere problemi relativi alle prestazioni](trace-execution-er-troubleshoot-perf.md) per altri dettagli sulla funzionalità di traccia dell'esecuzione ER.

### <a name="review-er-model-mapping-part-1"></a>Esaminare il mapping del modello ER (parte 1)

Esaminare le impostazioni del componente di mapping del modello ER. Il componente è configurato per accedere alle informazioni sulle versioni delle configurazioni ER, i dettagli delle configurazioni e dei provider di configurazione senza utilizzare origini dati di tipo **Join**.

1. Selezionare la configurazione **Mapping to learn JOIN data sources**.
2. Selezionare **Progettazione** per aprire l'elenco dei mapping.
3. Selezionare **Progettazione** per esaminare i dettagli dei mapping.
4. Selezionare **Mostra dettagli**.
5. Nell'albero delle configurazioni, espandere gli elementi del modello dati **Set1** e **Set1.Details**:

    1. L'associazione **Details: Record list = Versions** indica che l'elemento **Set1.Details** è associato all'origine dati **Versions** che restituisce i record della tabella **ERSolutionVersionTable**. Ciascun record della tabella rappresenta una singola versione della configurazione ER. Il contenuto della tabella è presentato nella scheda dettaglio **Versioni** della pagina **Configurazioni**.
    2. L'associazione **ConfigurationVersion: String = @.PublicVersionNumber** indica che il valore della versione pubblica della versione di ciascuna configurazione ER è ricavato dal campo **PublicVersionNumber** della tabella **ERSolutionVersionTable** e inserito nell'elemento **ConfigurationVersion**.
    3. L'associazione **ConfigurationTitle: String = @.'>Relations'.Solution.Name** indica che il nome di una configurazione ER e ricavato dal campo **Name** della tabella **ERSolutionTable** tramite la relazione molti-a-uno (**'>Relations'**) tra le tabelle **ERSolutionVersionTable** e **ERSolutionTable**. I nomi delle configurazioni ER dell'istanza dell'applicazione corrente sono presentati nell'albero delle configurazioni nella pagina **Configurazioni**.
    4. L'associazione **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** indica che il nome del provider di configurazione che fornisce la configurazione corrente è ricavato dal campo **Name** della tabella **ERVendorTable** tramite la relazione molti-a-uno tra le tabelle **ERSolutionTable** e **ERVendorTable** tables. I nomi dei provider di configurazione ER sono presentati nell'albero delle configurazioni nella pagina **Configurazioni** dell'intestazione di pagina per ogni configurazione. L'intero elenco dei provider di configurazione ER è disponibile nella pagina della tabella **Amministrazione organizzazione \> Creazione di report elettronici \> Provider di configurazione**.

    ![Pagina della progettazione mapping modello di ER, elenco di elementi del modello di dati associati](./media/GER-JoinDS-Set1Review.PNG)

6. Nell'albero delle configurazioni, espandere l'elemento del modello dati **Set1.Summary**:

    1. L'associazione **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** indica che l'elemento **Set1.Summary.VersionsNumber** è associato al campo di aggregazione **VersionsNumber** dell'origine dati **VersionsSummary** del tipo **GroupBy** configurato per restituire il numero di record della tabella **ERSolutionVersionTable** tramite l'origine dati **Versions**.

    ![Modificare la pagina dei parametri "Raggruppa per"](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. Chiudere la pagina.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a> Esaminare il mapping del modello ER (parte 2)

Esaminare le impostazioni del componente di mapping del modello ER. Il componente è configurato per accedere alle informazioni sulle versioni delle configurazioni ER, i dettagli delle configurazioni e dei provider di configurazione utilizzando un'origine dati di tipo **Join**.

1. Nell'albero delle configurazioni, espandere gli elementi del modello dati **Set2** e **Set2.Details**. L'associazione **Details: Record list = Details** indica che l'elemento **Set2.Details** è associato all'origine dati **Details** configurata come origine dati di tipo **Join**.

    ![Pagina della progettazione mapping modello di ER che mostra gli elementi del modello di dati Set2:Record espanso](./media/GER-JoinDS-Set2Review.PNG)

    L'origine dati **Join** può essere aggiunta selezionando l'origine dati **Funzioni\Join**:

    ![Pagina della progettazione mapping modello di ER, tipo di origine dati Join](./media/GER-JoinDS-AddJoinDS.PNG)

2. Selezionare l'origine dati **Dettagli**.
3. Selezionare **Modifica** nel riquadro **Origini dati**.
4. Selezionare **Modifica join**.
5. Selezionare **Mostra dettagli**.

    ![Pagina dei parametri dell'origine dati JOIN](./media/GER-JoinDS-JoinDSEditor.PNG)

    Questa pagina viene utilizzata per progettare l'origine dati richiesta di tipo **Join**. In fase di esecuzione, questa origine dati creerà un unico elenco unito di record dalle origini dati della griglia dell'**elenco unito**. Il join dei record inizia dall'origine dati **ConfigurationProviders** presente nella griglia come prima (la colonna **Tipo** è vuota). I record di ogni altra origine dati verranno uniti di conseguenza ai record dell'origine dati padre in base all'ordine in questa griglia. Ogni origine dati di join deve essere configurata come origine dati nidificata in un'origine dati di destinazione (l'origine dati `1Versions` è nidificata in `1Configurations`; l'origine dati `1Configurations` è nidificata in **ConfigurationProviders**). Ogni origine dati configurata deve contenere le condizioni per il join. Nell'origine dati per questo particolare **Join**, sono definiti i seguenti join:

    - Ogni record dell'origine dati **ConfigurationProviders** (a cui si fa riferimento nella tabella **ERVendorTable**) è unito solo ai record di **1Configurations** (a cui si fa riferimento nella tabella **ERSolutionTable**) che hanno lo stesso valore nei campi **SolutionVendor** e **RecId**. Il tipo **Inner join** viene utilizzato per questo join, nonché le seguenti condizioni per la corrispondenza dei record:

    FILTER (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Ogni record dell'origine dati **1Configurations** (a cui si fa riferimento nella tabella **ERSolutionTable**) è unito solo ai record di **1Versions** (a cui si fa riferimento nella tabella **ERSolutionVersionTable**) che hanno lo stesso valore nei campi **Solution** e **RecId**. Il tipo **Inner join** viene utilizzato per questo join, nonché le seguenti condizioni per la corrispondenza dei record:

    FILTER (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - L'opzione **Esegui** è configurata come **Query** indicando che questa origine dati di join verrà eseguita in fase di esecuzione a livello di database come chiamata SQL diretta.

    Per unire i record di origini dati che rappresentano le tabelle dell'applicazione, è possibile specificare le condizioni di join utilizzando coppie di campi diversi da quelli che descrivono le relazioni AOT esistenti tra queste tabelle. Questo tipo di join può essere configurato per essere eseguito anche a livello di database.

6. Chiudere la pagina.
7. Selezionare **Annulla**.
8. Nell'albero delle configurazioni, espandere l'elemento del modello dati **Set2.Summary**:

    - L'associazione **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** indica che l'elemento **Set2.Summary.VersionsNumber** è associato al campo di aggregazione **VersionsNumber** dell'origine dati **DetailsSummary** del tipo **GroupBy** configurato per restituire il numero di record uniti dell'origine dati **Details** di tipo **Join**.
    - L'opzione dell'ubicazione dell'**esecuzione** è configurata come **Query** indicando che questa origine dati **GroupBy** verrà eseguita in fase di esecuzione come chiamata SQL diretta a livello di database. Questo comportamento è possibile perché l'origine dati di base **Details** del tipo **Join** è configurata come eseguita a livello di database.

    ![Pagina dei parametri dell'origine dati GROUPBY](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. Chiudere la pagina.
10. Selezionare **Annulla**.

### <a name="execute-er-format"></a><a name="executeERformat"></a> Eseguire il formato ER

1. Accedere a Finance o RCS nella seconda sessione del browser Web utilizzando le stesse credenziali e società della prima sessione.
2. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
3. Espandere la configurazione **Model to learn JOIN data sources**.
4. Selezionare la configurazione **Format to learn JOIN data sources**.
5. Selezionare **Progettazione**.
6. Selezionare **Mostra dettagli**.
7. Selezionare **Mapping**.
8. Selezionare **Espandi/Comprimi**.

    Questo formato è progettato per popolare un file di testo generato con una nuova riga per ogni versione di configurazione ER (sequenza **Versione**). Ogni riga generata conterrà il nome di un provider di configurazione proprietario della configurazione corrente, il nome della configurazione e la versione della configurazione separati da un punto e virgola. L'ultima riga del file generato conterrà il numero di versioni rilevate delle configurazioni ER (sequenza **Riepilogo**).

    ![Pagina della progettazione del formato ER, scheda Formato](./media/GER-JoinDS-FormatReview.PNG)

    Le origini dati **Riepilogo** e **Dati** vengono utilizzate per popolare i dettagli della versione di configurazione nel file generato:

    - Le informazioni del modello dati **Set1** vengono utilizzate quando si sceglie **No** per l'origine dati **Selettore** in fase di esecuzione nella finestra di dialogo utente durante l'esecuzione del formato ER.
    - Le informazioni del modello dati **Set2** vengono utilizzate quando si sceglie **Sì** per l'origine dati **Selettore** in fase di esecuzione nella finestra di dialogo utente.

    ![Pagina della progettazione del formato ER, scheda Mapping](./media/GER-JoinDS-FormatMappingReview.PNG)

9. Selezionare **Esegui**.
10. Nella finestra di dialogo, selezionare **No** nel campo **Utilizza origine dati JOIN**.
11. Selezionare **OK**.
12. Esaminare il file generato.

    ![File generato dei parametri ER che non utilizza l'origine dati JOIN](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analizzare la traccia dell'esecuzione ER

1. Nella prima sessione di Finance o RCS, selezionare **Progettazione**.
2. Selezionare **Traccia delle prestazioni**.
3. Nella griglia **Traccia delle prestazioni**, selezionare il primo record dell'ultima traccia dell'esecuzione di un formato ER che ha utilizzato il componente di mapping di modello corrente.
4. Selezionare **OK**.

    Le statistiche di esecuzione informano sulle chiamate duplicate alle tabelle delle applicazioni:

    - **ERSolutionTable** è stato chiamato tante volte quanti sono i record della versione di configurazione nella tabella **ERSolutionVersionTable**, mentre il numero delle volte delle chiamate potrebbe essere ridotto per migliorare le prestazioni.
    - **ERVendorTable** è stato chiamato due volte per ogni record della versione di configurazione rilevato nella tabella **ERSolutionVersionTable**, mentre il numero delle chiamate potrebbe essere ridotto.

    ![Statistiche di esecuzione nella pagina della progettazione mapping modello ER](./media/GER-JoinDS-Set1Run2.PNG)

5. Chiudere la pagina.

### <a name="execute-er-format"></a>Eseguire il formato ER

1. Passare alla scheda del Web browser con la seconda sessione di Finance o RCS.
2. Selezionare **Esegui**.
3. Nella finestra di dialogo, selezionare **Sì** nel campo **Utilizza origine dati JOIN**.
4. Selezionare **OK**.
5. Esaminare il file generato.

    ![File generato dei parametri ER che utilizza l'origine dati JOIN](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> Analizzare la traccia dell'esecuzione ER

1. Nella prima sessione di Finance o RCS, selezionare **Progettazione**.
2. Selezionare **Traccia delle prestazioni**.
3. Nella griglia **Traccia delle prestazioni**, selezionare il primo record che rappresenta l'ultima traccia dell'esecuzione di un formato ER che ha utilizzato il componente di mapping di modello corrente.
4. Selezionare **OK**.

    Le statistiche ti informano su quanto segue:

    - Il database dell'applicazione è stato chiamato una volta per ottenere i record delle tabelle **ERVendorTable**, **ERSolutionTable** e **ERSolutionVersionTable** per accedere ai campi obbligatori.

    ![Dettagli statistiche di prestazioni nella pagina della progettazione mapping modello ER](./media/GER-JoinDS-Set2Run2.PNG)

    - Il database dell'applicazione è stato chiamato una volta per calcolare il numero di versioni di configurazione utilizzando i join configurati nell'origine dati **Details**.

    ![Pagina della progettazione mapping modello ER che mostra le chiamate al database dell'applicazione](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>Limiti

Come illustrato nell'esempio di questo argomento, l'origine dati **JOIN** può essere creata da diverse origini dati che descrivono i singoli set di dati dei record che devono essere uniti. È possibile configurare tali origini dati utilizzando la funzione [FILTER](er-functions-list-filter.md) ER integrata. Quando si configura l'origine dati in modo che venga chiamata all'esterno dell'origine dati **JOIN**, è possibile utilizzare intervalli di società come parte della condizione per la selezione dei dati. L'implementazione iniziale dell'origine dati **JOIN** non supporta origini dati di questo tipo. Ad esempio, quando si chiama un'origine dati basata su [FILTER](er-functions-list-filter.md) nell'ambito di esecuzione di un'origine dati **JOIN**, se l'origine dati chiamata contiene intervalli di società come parte della condizione per la selezione dati, si verifica un'eccezione.

In Microsoft Dynamics 365 Finance versione 10.0.12 (agosto 2020) è possibile utilizzare gli intervalli di società come parte della condizione per la selezione dei dati nelle origini dati basate su [FILTER](er-functions-list-filter.md) chiamate nell'ambito di esecuzione di un'origine dati **JOIN**. A causa delle limitazioni del configuratore di [query](../dev-ref/xpp-library-objects.md#query-object-model) dell'applicazione, gli intervalli di società sono supportati solo per la prima origine dati di un'origine dati **JOIN**.

### <a name="example"></a>Esempio

È ad esempio necessario effettuare una singola chiamata al database dell'applicazione per ottenere l'elenco delle transazioni commerciali estere di più società e i dettagli dell'articolo di magazzino a cui si fa riferimento in tali transazioni.

In questo caso, configurare i seguenti elementi nel mapping di modello ER:

- Origine dati radice **Intrastat** che rappresenta la tabella **Intrastat**.
- Origine dati radice **ARticoli** che rappresenta la tabella **InventTable**.
- Origine dati radice **Società** che restituisce l'elenco delle società (in questo esempio **DEMF** e **GBSI**) in cui è necessario accedere alle transazioni. Il codice società è disponibile nel campo **Companies.Code**.
- Origine dati radice **X1** che ha l'espressione `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))`. Come parte della condizione per la selezione dei dati, questa espressione contiene la definizione di intervalli di società `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`.
- Origine dati radice **X2** come articolo annidato dell'origine dati radice **X1**. Include l'espressione `FILTER (Items, Items.ItemId = X1.ItemId)`.

È infine possibile configurare un'origine dati **JOIN** dove **X1** è la prima origine dati e **X2** è la seconda origine dati. È possibile specificare **Query** come opzione **Esegui** per forzare ER a eseguire questa origine dati a livello di database come una chiamata SQL diretta.

Quando l'origine dati configurata viene eseguita mentre l'esecuzione ER è [tracciata](trace-execution-er-troubleshoot-perf.md), la seguente istruzione viene mostrata nella pagina della progettazione mapping modello ER come parte della traccia delle prestazioni ER.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> Si verifica un errore se si esegue un'origine dati **JOIN** che è stata configurata in modo da contenere le condizioni di selezione dei dati con intervalli di società per ulteriori origini dati dell'origine dati **JOIN** eseguita.

## <a name="additional-resources"></a>Risorse aggiuntive

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Generare la traccia dell'esecuzione del formato ER per risolvere problemi relativi alle prestazioni](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
