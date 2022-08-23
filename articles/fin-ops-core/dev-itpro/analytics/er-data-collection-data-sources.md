---
title: Utilizzare le origini dati RACCOLTA DATI nei formati per la creazione di report elettronici
description: In questo articolo viene descritto come utilizzare le origini dati RACCOLTA DATI nei formati per la creazione di report elettronici (ER).
author: kfend
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: 221cefc1880cdd88a952140424daf24975a575aa
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286181"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>Utilizzare le origini dati RACCOLTA DATI nei formati per la creazione di report elettronici

[!include [banner](../includes/banner.md)]

È possibile utilizzare Designer operazioni del framework di [Creazione di report elettronici (ER)](general-electronic-reporting.md) per configurare il componente di formato di una soluzione ER utilizzata per generare documenti in uscita in diversi formati. La struttura gerarchica del componente di formato configurato è costituita da vari tipi di elementi di formato. Questi elementi di formato vengono utilizzati per riempire i documenti generati con le informazioni necessarie in fase di esecuzione. Per impostazione predefinita, quando si esegue un formato ER, gli elementi del formato vengono eseguiti nello stesso ordine in cui sono presentati nella gerarchia dei formati: uno per uno, dall'alto verso il basso.

Quando ER esegue un elemento di formato che contiene un'associazione, viene eseguita la formula di tale associazione e l'elemento di formato aggiunge il valore a un documento generato. Ad esempio, l'associazione può passare il valore di un campo modello di dati a un elemento di formato. È possibile configurare un'origine dati RACCOLTA DATI per raccogliere i valori dei campi del modello di dati al runtime, eseguire la somma dei valori e compilare un documento generato con i valori raccolti. Per utilizzare questo approccio, modifica l'associazione iniziale in modo che l'origine dati RACCOLTA DATI configurata venga utilizzata per passare il valore di un campo del modello di dati a un elemento di formato. Passando i valori attraverso l'origine dati RACCOLTA DATI, è possibile raccogliere i dettagli richiesti per un ulteriore utilizzo.

Quando configuri un'origine dati RACCOLTA DATI, specifica un tipo di valore che verrà gestito nell'origine dati. I seguenti [tipi di dati](er-formula-supported-data-types-primitive.md) sono attualmente supportati per la raccolta di valori:

- Boolean
- Data
- Data/Ora
- GUID
- Int64
- Integer
- Real
- String
- Tempo

Puoi usare il metodo `Collect(Value)` di un'origine dati RACCOLTA DATI per passare un valore a un'origine dati per la raccolta. In questo metodo, l'argomento `Value` è una costante o il percorso valido di un campo dell'origine dati del tipo di dati rilevante.

Utilizza la proprietà `Result` di un'origine dati RACCOLTA DATI per accedere all'elenco dei valori raccolti. Questa proprietà restituisce un [elenco di record](er-formula-supported-data-types-composite.md#record-list). I record dell'elenco di record contengono il campo `Value` che può essere utilizzato per accedere ai valori raccolti.

Per impostazione predefinita, un'origine dati RACCOLTA DATI raccoglie solo valori univoci.

Per raccogliere tutti i valori, imposta il campo **Raccogli tutti i valori** dell'origine dati RACCOLTA DATI configurata su **Sì**. Quando il campo **Raccogli tutti i valori** è impostato su **Sì**, la proprietà parametrizzata `Sum(Flag)` diventa disponibile. È possibile utilizzare questa proprietà per ottenere l'importo totale di tutti i valori attualmente raccolti. In questa proprietà, l'argomento `Flag` è un valore [booleano](er-formula-supported-data-types-primitive.md#boolean) che viene utilizzato per indicare se il valore totale deve essere ripristinato.

- Quando viene fornito il valore **Falso**, la somma continua dall'importo precedentemente raccolto.
- Quando viene fornito il valore **Vero**, viene avviata una nuova somma.

I seguenti tipi di dati sono attualmente supportati per la somma:

- Int64
- Integer
- Real

Per ulteriori informazioni su questa funzionalità, completa l'esempio riportato di seguito.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>Esempio: configurare un formato ER per eseguire il conteggio e la somma utilizzando un'origine dati RACCOLTA DATI

Questo esempio mostra come un utente con il ruolo di amministratore di sistema o consulente funzionale per la creazione di report elettronici può configurare un formato ER con un'origine dati RACCOLTA DATI utilizzata per calcolare i totali correnti e raccogliere i valori sommati.

Le procedure in questo esempio possono essere completate nella società USMF in Microsoft Dynamics 365 Finance.

### <a name="upload-and-use-the-provided-er-solution"></a>Caricare e utilizzare la soluzione ER fornita

1. [Importare le configurazioni ER di esempio](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [Attivare un provider di configurazioni](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [Esaminare il mapping di modello importato](er-defer-sequence-element.md#review-the-imported-model-mapping).
4. [Esaminare il formato importato](er-defer-sequence-element.md#review-the-imported-format).
5. [Eseguire il formato importato](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>Eseguire il formato della soluzione ER fornita

1. Nella pagina **Progettazione formati**, selezionare **Esegui**.
2. Nella finestra di dialogo **Parametri per la creazione di report elettronici** selezionare **OK**.
3. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato che contiene i risultati dell'esecuzione del formato iniziale](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>Modificare il formato della soluzione ER per calcolare il totale corrente delle imposte

Se il volume delle transazioni è molto più grande del volume nell'esempio corrente, il tempo necessario per effettuare la somma potrebbe aumentare e causare problemi di prestazioni. Modificando le impostazioni del formato, è possibile prevenire questi problemi di prestazioni. Poiché si accede ai valori di imposta per includerli nel report generato, è possibile riutilizzare queste informazioni per sommare i valori di imposta.

1. Nella pagina **Progettazione formati** nella scheda **Mapping** seleziona **Aggiungi radice**.
2. Nella finestra di dialogo **Aggiungi origine dati**, seleziona **Funzioni** \> **Raccolta dati**.
3. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"**, segui questi passaggi:

    1. Nel campo **Nome**, immetti **CollectedTaxValues**.
    2. Nel campo **Tipo di articolo** selezionare **Reale**.
    3. Nel campo **Raccogli tutti i valori**, seleziona **Sì**.
    4. Selezionare **OK**.

4. Seleziona l'elemento di formato numerico **Report\\Lines\\Record\\TaxAmount**.

    > [!NOTE]
    > Attualmente, l'associazione `@.Value` è configurata per questo elemento. Pertanto, un documento generato è compilato con i valori di imposta del campo `model.Data.List.Value`.

5. Selezionare **Modifica formula**.
6. Nella pagina **Designer formula** effettua i seguenti passaggi:

    1. Nel campo **Formula**, sostituisci `@.Value` con `CollectedTaxValues.Collect(@.Value)`.
    2. Salva le modifiche e chiudi la pagina.

    > [!NOTE]
    > La nuova associazione passerà gli stessi valori di imposta a un documento generato. Tuttavia, tali valori verranno raccolti anche nell'origine dati **CollectedTaxValues**.

7. Seleziona l'elemento di formato numerico **Report\\Lines\\Record\\RunningTotal**.
8. Selezionare **Modifica formula**.
9. Nella pagina **Designer formula** effettua i seguenti passaggi:

    1. Nel campo **Formula**, immetti `CollectedTaxValues.Sum(false)`.
    2. Salva le modifiche e chiudi la pagina.

    > [!NOTE]
    > La nuova associazione passerà, a un documento generato, l'importo totale dei valori di imposta già inseriti.

    ![Elementi numerici con associazioni aggiornate nella pagina Progettazione formati](./media/er-data-collection-data-sources-02.png)

10. Selezionare **Salva** e quindi selezionare **Esegui**.
11. Nella finestra di dialogo **Parametri per la creazione di report elettronici** selezionare **OK**.
12. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato che contiene i risultati dell'esecuzione del formato modificato](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>Modificare il formato per valutare l'elenco dei valori di imposta raccolti

1. Nella pagina **Progettazione formati**, nella scheda **Formato**, seleziona l'elemento di formato numerico **Report\\Lines\\Record\\RunningTotal**, quindi segui questi passaggi:

    1. Nel campo **Tipo numerico** modifica il valore da **Reale** a **Intero**.
    2. Nel campo **Formato numerico**, modifica il valore da **F2** a **F0**.

3. Nella scheda **Mapping**, seleziona **Modifica formula**.
4. Nella pagina **Designer formula** effettua i seguenti passaggi:

    1. Nel campo **Formula**, immetti `COUNT(CollectedTaxValues.Result)`.
    2. Salva le modifiche e chiudi la pagina.

    > [!NOTE]
    > La nuova associazione passerà, a un documento generato, il numero di record nell'elenco in cui vengono raccolti i valori di imposta.

5. Selezionare **Salva** e quindi selezionare **Esegui**.
6. Nella finestra di dialogo **Parametri per la creazione di report elettronici** selezionare **OK**.
7. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato che contiene i risultati di un'altra esecuzione del formato modificato](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>Se devo calcolare i totali correnti e raccogliere dati, qual è la differenza tra l'utilizzo di un'origine dati RACCOLTA DATI e l'utilizzo delle funzioni RACCOLTA DATI integrate?

Sia un'origine dati RACCOLTA DATI che le funzioni [RACCOLTA DATI](er-functions-category-data-collection.md) possono essere utilizzate per la raccolta, la somma e il conteggio dei dati, in base alle informazioni passate a un documento in uscita generato. Tuttavia, quando vuoi decidere quale tecnica utilizzare, devi considerare i seguenti punti.

| Origine dati | Funzioni integrate |
|-------------| ------------------ |
| Vengono raccolti solo i valori. | <p>Vengono raccolti i valori con nome. Pertanto, i totali possono essere calcolati per gruppi separati di valori.</p><p>Inoltre, i gruppi possono essere estratti come elenco.</p><p>È possibile raccogliere anche valori di testo.</p> |
| I valori univoci vengono raccolti automaticamente. | Sono necessarie impostazioni aggiuntive per estrarre un elenco di valori univoci dai valori raccolti. |
| Le prestazioni dipendono dal volume dei valori raccolti. | In pratica, le prestazioni non dipendono dal volume dei valori raccolti. |
| Questa tecnica funziona con tutti i tipi di documenti in uscita. | Questa tecnica funziona solo per documenti di testo e XML. |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare il formato per eseguire il conteggio e la sommatoria](./tasks/er-format-counting-summing-1.md)
- [Differire l'esecuzione di elementi di sequenza in formati ER](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
