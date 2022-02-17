---
title: Raggruppare i record e aggregare i calcoli utilizzando le origini dati GROUPBY
description: In questo argomento viene descritto come utilizzare le origini dati di tipo GROUPBY nella creazione di report elettronici (ER).
author: NickSelin
ms.date: 01/31/2022
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a6cdc486c5f799bdedafa38e90be989fd328c96
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075622"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Raggruppare i record e aggregare i calcoli utilizzando le origini dati GROUPBY

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Durante la configurazione di mapping o formati del modello di [report elettronici (ER)](general-electronic-reporting.md), è possibile [aggiungere](#AddMmDataSource2) le origini dati obbligatorie del tipo **GroupBy**.

In fase di progettazione, un'origine dati **GroupBy** viene configurata per identificare i seguenti elementi:

- Un'[origine dati di base](#BaseDataSource) che contiene record che verranno raggruppati in fase di esecuzione
- [Raggruppamento dei campi](#GroupingFields) dell'origine dati di base, che verrà utilizzata per il raggruppamento dei record in fase di esecuzione
- [Funzioni aggregate](#AggregateFunctions) che specificano i calcoli aggregati che verranno eseguiti per ogni gruppo individuato in fase di esecuzione

In fase di esecuzione, un'origine dati **GroupBy** configurata raggruppa i record che hanno gli stessi valori nei campi di raggruppamento, quindi restituisce un elenco di record. Ogni record rappresenta un singolo gruppo. Per ogni gruppo, l'origine dati presenta i valori dei campi in base ai quali sono stati raggruppati i record iniziali, i valori delle funzioni di aggregazione calcolate e l'elenco di record dell'origine dati di base che appartiene al gruppo.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>Funzione di aggregazione

In fase di esecuzione, ogni calcolo aggregato viene eseguito per ciascun gruppo di record. Questo calcolo viene eseguito utilizzando il valore di un singolo campo o un'espressione nei record di un'origine dati che è stata selezionata per il raggruppamento nell'origine dati modificabile del tipo **GroupBy**. Attualmente sono supportate le seguenti funzioni di aggregazione:

- **AVG**: questa funzione restituisce la media dei valori in un gruppo. Può essere utilizzato solo con campi numerici.
- **COUNT**: questa funzione restituisce il numero di elementi trovati in un gruppo.
- **Min**: questa funzione restituisce il valore minimo tra i valori in un gruppo.
- **Max**: questa funzione restituisce il valore massimo tra i valori in un gruppo.
- **SUM**: questa funzione restituisce la somma di tutti i valori in un gruppo. Può essere utilizzato solo con campi numerici.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Ubicazione di esecuzione

Quando modifichi un'origine dati **GroupBy** e specifichi l'origine dati di base che contiene i record che devono essere raggruppati, il sistema rileva automaticamente la [posizione](#ExecutionLocation) più efficiente per l'esecuzione di tale origine dati **GroupBy**. Se l'origine dati di base è [interrogabile](er-functions-list-filter.md#usage-notes) (ovvero, se può essere eseguita a livello di database), il database dell'applicazione viene specificato anche come posizione di esecuzione dell'origine dati **GroupBy** modificabile. In caso contrario, la memoria del server delle applicazioni viene specificata come posizione di esecuzione.

È possibile modificare manualmente il percorso di esecuzione rilevato automaticamente selezionando il percorso applicabile all'origine dati configurata. Se il percorso di esecuzione selezionato non è applicabile, viene visualizzato un [errore di convalida](er-components-inspections.md#i5) in fase di progettazione.

> [!TIP]
> È consigliabile utilizzare il percorso del database per raggruppare origini dati che presentano un numero elevato di record.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>Utilizzo di memoria

Per impostazione predefinita, se un'origine dati **GroupBy** viene eseguita in memoria, la memoria del server delle applicazioni viene utilizzata per archiviare i record dell'origine dati di base che appartiene a ciascun gruppo rilevato come record di un singolo gruppo. Per ridurre il consumo di memoria, puoi eliminare l'archiviazione dei record per le origini dati **GroupBy** se sono state configurate per calcolare solo funzioni aggregate e i record del relativo gruppo non vengono utilizzati in fase di esecuzione. Per ridurre il consumo di memoria in questo modo, abilita la funzionalità **Riduce l'utilizzo della memoria nella creazione di report elettronici quando il raggruppamento dei record viene utilizzato solo per calcolare le aggregazioni** nell'area di lavoro **Gestione funzionalità**.

## <a name="alternatives"></a><a name="Alternatives"></a>Alternative

Aggregazioni simili possono essere calcolate utilizzando [diversi](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) tipi di origini dati o funzioni integrate per i report elettronici.

Per ulteriori informazioni su questa funzionalità, completa l'esempio riportato di seguito.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>Esempio: utilizza un'origine dati GROUPBY per calcoli aggregati e ragruppamenti di record

Questo esempio mostra come un utente con il ruolo di amministratore di sistema o consulente funzionale per la creazione di report elettronici può configurare un mapping di modelli ER con un'origine dati **GROUPBY** utilizzata per calcolare funzioni di aggregazione e record di raggruppamento. Questo mapping di modelli viene utilizzato per stampare il report di controllo quando viene generata la dichiarazione Intrastat. Tale report consente di rivedere le transazioni Intrastat dichiarate.

Le procedure in questo esempio possono essere completate nella società **DEMF** in Microsoft Dynamics 365 Finance. 

### <a name="prepare-sample-data"></a>Preparare dati di esempio

Assicurati di disporre di transazioni Intrastat per la creazione di report nella pagina **Intrastat**. Devi avere transazioni per codici di trasporto diversi, perché raggrupperai le transazioni in base al campo **Trasporto** in questo esempio.

![Preparazione delle transazioni Intrastat nella pagina Intrastat.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>Configurare il framework ER

Segui i passaggi in [Configurare il framework ER](er-quick-start2-customize-report.md#ConfigureFramework) per impostare il set minimo di parametri ER. È necessario completare questa configurazione prima di iniziare a utilizzare il framework ER per progettare un mapping di modelli ER.

### <a name="import-the-standard-er-format-configuration"></a>Importare la configurazione del formato ER standard

Segui i passaggi in [Importare la configurazione del formato ER standard](er-quick-start2-customize-report.md#ImportERSolution1) per aggiungere le configurazioni ER standard alla tua attuale istanza di Dynamics 365 Finance. Importa la versione 1 della configurazione del **modello Intrastat** dal repository.

### <a name="create-a-custom-data-model-configuration"></a>Creare una configurazione del modello dati personalizzata

Segui i passaggi in [Aggiungere una configurazione del modello dati personalizzata](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) per aggiungere manualmente una nuova configurazione del modello di dati ER **Modello Intrastat (Litware)** derivata dalla configurazione **Modello Intrastat** importata.

### <a name="configure-a-custom-data-model-component"></a>Configurare un componente modello dati personalizzato

Attieniti alla seguente procedura per apportare le modifiche al modello di dati **Modello Intrastat (Litware)** derivato, in modo che possa essere utilizzato per presentare i codici di trasporto con i dettagli obbligatori.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nell'albero di configurazione, seleziona **Modello Intrastat (Litware)**.
3. Selezionare **Progettazione**.
4. Nella pagina **Progettazione modello di dati**, nell'albero dei modelli, seleziona **Intrastat**.
5. Seleziona **Nuovo** per aggiungere un nuovo nodo annidato per il nodo **Intrastat** selezionato. Nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Nel campo **Nome** immettere **Trasporto**.
    2. Nel campo **Tipo di articolo** selezionare **Elenco di record**.
    3. Per aggiungere un nuovo nodo, selezionare **Aggiungi**.

6. Seleziona **Nuovo** per aggiungere un nuovo nodo annidato per il nodo **Trasporto** appena aggiunto. Nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Nel campo **Nome** immetti **Codice**.
    2. Nel campo **Tipo di articolo** selezionare **Stringa**.
    3. Per aggiungere un nuovo nodo, selezionare **Aggiungi**.

7. Seleziona **Nuovo** per aggiungere un altro nuovo nodo annidato per il nodo **Trasporto**. Nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Nel campo **Nome**, immetti **TotalInvoicedAmount**.
    2. Nel campo **Tipo di articolo** selezionare **Reale**.
    3. Per aggiungere un nuovo nodo, selezionare **Aggiungi**.

8. Seleziona **Nuovo** per aggiungere un altro nuovo nodo annidato per il nodo **Trasporto**. Nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Nel campo **Nome**, immetti **NumberOfTransactions**.
    2. Nel campo **Tipo di articolo** seleziona **Intero**.
    3. Per aggiungere un nuovo nodo, selezionare **Aggiungi**.

9. Seleziona **Nuovo** per aggiungere un altro nuovo nodo annidato per il nodo **Trasporto**. Nella finestra di dialogo a discesa per l'aggiunta di un nodo al modello di dati, seguire questi passaggi:

    1. Nel campo **Nome**, immetti **Transazione**.
    2. Nel campo **Tipo di articolo** selezionare **Elenco di record**.
    3. Per aggiungere un nuovo nodo, selezionare **Aggiungi**.

10. Per il nodo **Transazione** che hai appena aggiunto, nella Scheda dettaglio **Nodo**, seleziona **Cambia riferimento articolo**.
11. Nella finestra di dialogo **Cambia riferimento articolo**, nell'albero del modello di dati, seleziona **CommodityRecord**. Selezionare **OK**.

![Modello di dati configurato nella finestra di progettazione modello di dati ER.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Completare la progettazione di un modello di dati personalizzato

Segui i passaggi in [Completare la progettazione del modello di dati](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) per completare la progettazione del modello di dati **Modello Intrastat (Litware)** derivato.

### <a name="create-a-new-model-mapping-configuration"></a>Creare una nuova configurazione del mapping del modello

Segui i passaggi in [Creare una nuova configurazione del mapping del modello](er-quick-start1-new-solution.md#CreateModelMapping) per aggiungere manualmente una nuova configurazione del mapping del modello ER **Mapping di esempio Intrastat** per la configurazione **Modello Intrastat (Litware)** derivata.

### <a name="add-a-new-model-mapping-component"></a>Aggiungere un nuovo component del mapping di modello

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi la configurazione **Modello Intrastat**.
3. Seleziona la configurazione **Mapping di esempio Intrastat**.
4. Selezionare **Progettazione** per aprire l'elenco dei mapping.
5. Seleziona **Elimina** per rimuovere il componente di mapping esistente.
6. Seleziona **Nuovo** per aggiungere un nuovo componente di mapping.
7. Nel campo **Definizione**, seleziona **Intrastat**.
8. Nel campo **Nome**, immetti **Mapping Intrastat**.
9. Seleziona **Progettazione** per configurare il nuovo mapping.

### <a name="design-the-added-model-mapping-component"></a>Progettare il componente del mapping del modello aggiunto

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>Aggiungere un'origine dati per accedere alla tabella dell'applicazione

Configura un'origine dati per accedere alle tabelle dell'applicazione che contengono i dettagli delle transazioni Intrastat.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, selezionare **Dynamics 365 for Operations\\Tabella dei record**.
2. Nel riquadro **Origini dati**, seleziona **Aggiungi radice** per aggiungere una nuova origine dati che verrà utilizzata per accedere alla tabella **Intrastat**. Ogni record nella tabella **Intrastat** rappresenta una singola transazione Intrastat.
3. Nella finestra di dialogo **Proprietà origine** nel campo **Nome** immetti **Transazione**.
4. Nel campo **Tabella**, immetti **Intrastat**.
5. Selezionare **OK** per aggiungere la nuova origine dati.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>Aggiungere un'origine dati per raggruppare le transazioni Intrastat

Configura un'origine dati **GroupBy** per raggruppare le transazioni Intrastat e calcolare le funzioni aggregate.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Tipi di origine dati**, seleziona **Funzioni\\Raggruppa per**.
2. Nel riquadro **Origini dati**, seleziona **Aggiungi radice** per aggiungere una nuova origine dati che verrà utilizzata per raggruppare le transazioni Intrastat e calcolare le funzioni aggregate.
3. Nella finestra di dialogo **Proprietà origine** nel campo **Nome** immetti **TransportRecord**.
4. Seleziona **Modifica gruppo per** per configurare le condizioni di raggruppamento.
5. Nella pagina **Modifica parametri "Raggruppa per"**, nell'elenco delle origini dati nel riquadro di destra, seleziona l'origine dati **Transazione** ed espandila.
6. Seleziona **Aggiungi campo a\> Cosa raggruppare** per indicare che l'origine dati **Transazione** è selezionata come <a name="BaseDataSource">origine dati di base</a> per l'origine dati **GroupBy** configurata. I record dell'origine dati **Transazione** verranno raggruppati e i valori dei campi di questa origine dati verranno utilizzati per i calcoli nelle funzioni aggregate.
7. Seleziona il campo **Transazione\Trasporto**, quindi seleziona **Aggiungi campo a \> Campo raggruppato** per indicare che il campo **Trasporto** dell'origine dati di base è selezionato come <a name="GroupingFields">criterio di raggruppamento</a> per l'origine dati **GroupBy** configurata. In altre parole, i record dell'origine dati **Transazione** verranno raggruppati in base al valore del campo **Trasporto**. Ogni record dell'origine dati **GroupBy** configurata rappresenterà un unico codice di trasporto che è stato trovato nei record dell'origine dati di base.
8. Seleziona il campo **Transazione\AmountMST**, quindi attieniti alla seguente procedura:

    1. Seleziona **Aggiungi campo a \> Campi aggregati** per indicare che una <a name="AggregateFunctions">funzione aggregata</a> sarà calcolata per questo campo.
    2. Nel riquadro **Aggregazioni**, nel record che è stato aggiunto per il campo **Transazione\AmountMST** selezionato, nel campo **Metodo**, seleziona la funzione **Somma**.
    3. Nel campo facoltativo **Nome**, immetti **TotalInvoicedAmount**.

    Queste impostazioni specificano che, per ogni gruppo di trasporto, l'importo totale del campo **Transazione\AmountMST** verrà calcolato.

9. Seleziona il campo **Transazione\RecId**, quindi attieniti alla seguente procedura:

    1. Seleziona **Aggiungi campo a \> Campi aggregati** per indicare che una funzione aggregata sarà calcolata per questo campo.
    2. Nel riquadro **Aggregazioni**, nel record che è stato aggiunto per il campo **Transazione\RecId** selezionato, nel campo **Metodo**, seleziona la funzione **Conteggio**.
    3. Nel campo facoltativo **Nome**, immetti **NumberOfTransactions**.

    Queste impostazioni specificano che, per ogni gruppo di trasporto, verrà calcolato il numero di transazioni nel gruppo.

10. Seleziona **Salva**.
11. Rivedi i parametri di <a name="ExecutionLocation">esecuzione</a> dell'origine dati modificabile. Tieni presente che **Rilevamento automatico** è stato selezionato automaticamente nel campo **Percorso di esecuzione** e il campo **Esecuzione in** contiene il valore **SQL**. Queste impostazioni specificano che l'origine dati di base **Transazione** selezionata è attualmente interrogabile ed è possibile eseguire l'origine dati **GroupBy** modificabile a livello di database.
12. Apri la ricerca per il campo **Percorso di esecuzione** per rivedere l'elenco dei valori disponibili. Tieni presente che puoi selezionare **Query** o **In memoria** per forzare l'esecuzione di questa origine dati **GroupBy** a livello di database o nella memoria del server delle applicazioni.
13. Seleziona **Salva**, quindi chiudi la pagina **Modifica parametri "Raggruppa per".**.
14. Seleziona **OK** per completare le impostazioni dell'origine dati **GroupBy**.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>Associare l'origine dati GroupBy ai campi del modello di dati

Associa l'origine dati configurata ai campi del modello dati per specificare in che modo il modello dati verrà compilato con i dati dell'applicazione in fase di esecuzione.

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Modello dati**, espandi il nodo **Trasporto**.
2. Nel riquadro **Origini dati**, espandi l'origine dati **TransportRecord**.
3. Aggiungi un'associazione per presentare l'elenco dei gruppi di trasporto rilevati:

    1. Nel riquadro **Modello di dati**, seleziona l'elemento **Trasporto**.
    2. Nel riquadro **Origini dati**, seleziona l'origine dati **TransportRecord**.
    3. Selezionare **Associa**.

4. Aggiungi un'associazione per presentare il codice di trasporto di ogni gruppo di trasporto rilevato:

    1. Seleziona l'elemento del modello di dati **Codice trasporto**.
    2. Seleziona il campo raggruppato **TransportRecord.grouped.TransportMode**.
    3. Selezionare **Associa**.

5. Aggiungi un'associazione per presentare i valori delle funzioni aggregate calcolate per ogni gruppo di trasporto individuato:

    1. Seleziona l'elemento del modello di dati **Transport.NumberOfTransactions**.
    2. Seleziona il campo aggregato **TransportRecord.aggregated.NumberOfTransactions**.
    3. Selezionare **Associa**.
    4. Seleziona l'elemento del modello di dati **Transport.TotalInvoicedAmount**.
    5. Seleziona il campo aggregato **TransportRecord.aggregated.TotalInvoicedAmount**.
    6. Selezionare **Associa**.

6. Aggiungi un'associazione per presentare i record di transazione che appartengono a ciascun gruppo di trasporto rilevato:

    1. Seleziona l'elemento del modello di dati **Transport.Transaction**.
    2. Seleziona il campo **TransportRecord.lines**.
    3. Selezionare **Associa**.

    Puoi continuare a configurare le associazioni per gli elementi nidificati della voce del modello di dati **Transport.Transaction** e il campo dell'origine dati **TransportRecord.lines** per presentare, in fase di esecuzione, i dettagli delle transazioni Intrastat che appartengono a ciascun gruppo di trasporto individuato.

![Mapping modello configurato nella finestra di progettazione mapping modello ER.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>Eseguire il debug del componente del mapping del modello aggiunto

Utilizza il [debugger dell'origine dati ER](er-debug-data-sources.md) per testare il mapping modello configurato.

1. Nella pagina **Progettazione mapping modello**, seleziona **Avvia debugging**.
2. Nella pagina **Debug origini dati**, nel riquadro sinistro, seleziona l'origine dati **TransportRecord**, quindi seleziona **Leggi tutti i record**.
3. Espandi l'origine dati **TransportRecord**, quindi segui questi passaggi:

    1. Seleziona l'origine dati **TransportRecord.grouped.TransportMode**.
    2. Selezionare **Ottieni valore**.
    3. Seleziona l'origine dati **TransportRecord.grouped.NumberOfTransactions**.
    4. Selezionare **Ottieni valore**.
    5. Seleziona l'origine dati **TransportRecord.grouped.TotalInvoicedAmount**.
    6. Selezionare **Ottieni valore**.

4. Nel riquadro di destra, seleziona **Espandi tutto**.

L'origine dati **TransportRecord** presenta due record e due codici di trasporto. Per ogni codice di trasporto viene calcolato il numero di transazioni e l'importo totale fatturato.

> [!NOTE]
> L'approccio della "lettura pigra" viene utilizzato quando un'origine dati **GroupBy** viene chiamata per ottimizzare le chiamate al database. Pertanto, alcuni dei valori di campo in un'origine dati **GroupBy** vengono calcolati nel debugger dell'origine dati ER solo quando è associata ai campi del modello dati.

![Risultati del debug dell'origine dati nella pagina Debug origini dati.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>Esiste un modo per calcolare i totali generali quando vengono calcolati i totali di gruppo?

Sì. Per calcolare i totali complessivi, configura un'altra origine dati **GroupBy** in cui l'origine dati **GroupBy** configurata in precedenza viene utilizzata come origine dati di base. L'illustrazione seguente mostra l'origine dati **Totali** del tipo **GroupBy** utilizzata per calcolare la funzione **SUM** aggregata, in base all'aggregazione **SUM** dell'origine dati **TransportRecord** del tipo **GroupBy**.

![Origine dati dei totali nella finestra di progettazione mapping modello ER.](./media/er-groupby-data-sources-configure-model-mapping2.png)

L'illustrazione seguente mostra i risultati del debug dell'origine dati **Totali**.

![Risultati del debug dell'origine dati Totali nella pagina Debug origini dati.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Eseguire il debug delle origini dati di un formato ER eseguito per analizzare il flusso e la trasformazione dei dati](er-debug-data-sources.md)
- [Utilizzare le origini dati RACCOLTA DATI nei formati per la creazione di report elettronici](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
