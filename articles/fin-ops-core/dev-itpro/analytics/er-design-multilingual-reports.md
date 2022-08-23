---
title: Progettare report multilingue nella creazione di report elettronici
description: Questo articolo spiega come utilizzare le etichette della creazione di report elettronici (ER) per progettare e generare report multilingue.
author: kfend
ms.date: 05/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
ms.openlocfilehash: 5575ba3154521e3855ce6b97c5b37d3c4868e3e9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285487"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Progettare report multilingue nella creazione di report elettronici

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

In qualità di utente aziendale, è possibile utilizzare il framework [Creazione di report elettronici ER](general-electronic-reporting.md) per configurare i formati per documenti in uscita che devono essere generati in base ai requisiti legali dei vari paesi o aree geografiche. Quando questi requisiti richiedono che i documenti in uscita vengano generati in lingue diverse per paesi o aree geografiche diversi, è possibile configurare un singolo formato ER che contiene le risorse dipendenti dalla lingua. In questo modo, è possibile riutilizzare il formato per generare documenti in uscita per vari paesi o aree geografiche. È possibile anche utilizzare un unico formato ER per generare un documento in uscita in diverse lingue per i clienti, i fornitori, le filiali o altre parti corrispondenti.

È possibile configurare i modelli di dati ER e i mapping del modello come origini dati dei formati ER configurati per definire il flusso di dati che specifica quali dati dell'applicazione vengono inseriti nei documenti generati. In qualità di [provider](general-electronic-reporting.md#Provider) di configurazione ER, è possibile [pubblicare](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) modelli di dati, mapping del modello e formati configurati come componenti di una soluzione ER per generare documenti in uscita specifici. È inoltre possibile consentire ai clienti di [caricare](general-electronic-reporting-manage-configuration-lifecycle.md) la soluzione ER pubblicata in modo che possa essere utilizzata e personalizzata. Se si prevede che i clienti possano parlare altre lingue, è possibile configurare i componenti ER in modo che contengano risorse dipendenti dalla lingua. In questo modo, il contenuto di un componente ER modificabile può essere presentato nella lingua preferita dall'utente in fase di progettazione.

È possibile configurare le risorse dipendenti dalla lingua come etichette ER. È quindi possibile utilizzare tali etichette per configurare i componenti ER per i seguenti scopi:

- In fase di progettazione:

    - Presentare il contenuto dei componenti ER configurati nella lingua preferita dall'utente.

- In fase di esecuzione:

    - Generare il contenuto dipendente dalla lingua per i documenti in uscita.
    - Fornire messaggi di avviso e di errore nella lingua preferita dall'utente.
    - Richiedere i campi obbligatori nella lingua preferita dall'utente.

Le etichette ER possono essere configurate in ogni [configurazione](general-electronic-reporting.md#Configuration) ER che contiene diversi componenti. Le etichette possono essere gestite indipendentemente dalla logica configurata dei modelli di dati ER, i mapping del modello ER e i componenti del formato ER.

Ogni etichetta ER è identificata da un ID univoco nell'ambito della configurazione ER che contiene quell'etichetta. Ogni etichetta può contenere il testo dell'etichetta per ogni lingua supportata nell'istanza corrente di Microsoft Dynamics 365 Finance. Queste lingue supportate includono le lingue delle personalizzazioni distribuite.

## <a name="entry"></a>Immissione

Quando si progetta un modello di dati ER, un mapping del modello ER o un formato ER, l'opzione **Traduci** viene visualizzata ogni volta che si seleziona un campo che potrebbe contenere il contesto traducibile. Quando si seleziona questa opzione, è possibile collegare il campo selezionato a un'etichetta ER nel riquadro <a name="TextTranslationPane">riquadro</a> **Traduzione testo**. È possibile selezionare un'etichetta ER esistente oppure aggiungere una nuova etichetta ER se non è ancora disponibile. Quando si seleziona o si aggiunge un'etichetta ER, è possibile aggiungere del testo correlato per ogni lingua supportata nell'istanza di Finance corrente.

La seguente illustrazione mostra come la traduzione viene eseguita in un modello di dati ER modificabile. In questo esempio, l'attributo **Descrizione** del campo **PurchaseOrder** per il **modello di fattura** modificabile è tradotto in tedesco austriaco (DE-AT) e giapponese (JA).

![Fornitura della traduzione di un'etichetta ER nella finestra di progettazione del modello di dati ER.](./media/er-multilingual-labels-refer.png)

È possibile tradurre solo il testo per le etichette che risiedono in un componente ER modificabile. Ad esempio, se si seleziona **Traduci** per l'attributo etichetta di un'origine dati di mapping del modello ER, quindi si seleziona un'etichetta ER che risiede nel modello di dati ER padre, verrà visualizzato il contenuto dell'etichetta, ma non è possibile modificarlo. In questi casi, il campo **Testo tradotto** non è disponibile, come mostrato nella figura seguente.

![Revisione della traduzione fornita di un'etichetta ER nella finestra di progettazione del mapping del modello ER.](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> Non è possibile utilizzare le pagine della progettazione per eliminare l'etichetta immessa in un componente ER modificabile.

## <a name="scope"></a>Ambito

È possibile fare riferimento alle etichette ER in diversi attributi traducibili dei componenti ER.

### <a name="data-model-component"></a>Componente modello dati

Quando si configura un modello di dati ER, è possibile aggiungere etichette ER. Gli attributi **Etichetta** e **Descrizione** dell'elemento del modello, del campo di ogni modello e del <a id="LinkModelEnum"></a>valore di enumerazione di ogni modello può essere collegato a un'etichetta ER che viene aggiunta al modello di dati ER.

![Fornitura della traduzione per l'attributo Descrizione nella finestra di progettazione del modello di dati ER.](./media/er-multilingual-labels-refer.png)

Quando un modello di dati ER viene configurato in questo modo, il contenuto verrà presentato agli utenti della pagina della progettazione del modello di dati ER nella lingua preferita di ciascun utente. Pertanto, la manutenzione del modello è semplificata. Le seguenti illustrazioni mostrano come questa funzionalità funziona per gli utenti che hanno DE-AT e JA impostati come lingua preferita.

![Layout della finestra di progettazione del modello di dati ER per un utente con DE-AT impostato come lingua preferita.](./media/er-multilingual-labels-refer-de.png)

![Layout della finestra di progettazione del modello di dati ER per un utente con JA impostato come lingua preferita.](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Componente di mapping del modello

Poiché il mapping del modello ER si basa su un modello di dati ER, le etichette degli elementi del modello di dati a cui viene fatto riferimento vengono visualizzate nella lingua preferita dell'utente nella pagina della progettazione del mapping del modello. La seguente illustrazione mostra come il significato del campo **PurchaseOrder** è espresso nel mapping del modello modificabile usando l'etichetta dell'attributo **Descrizione** che è stato aggiunto al modello di dati configurato. Si noti che questa etichetta è presentata nella lingua preferita dell'utente (DE-AT in questo esempio).

![Layout della finestra di progettazione del mapping del modello ER per un utente con DE-AT impostato come lingua preferita.](./media/er-multilingual-labels-show-mapping.png)

Quando l'attributo **Etichetta** dell'origine dati **Parametro di input utente** è configurato come collegato a un'etichetta ER, il campo del parametro che corrisponde a questa origine dati viene presentato nella finestra di dialogo in fase di esecuzione agli utenti nella loro lingua preferita.

### <a name="format-component"></a>Componente formato

Quando si configura un formato ER, è possibile aggiungere etichette ER. Gli attributi **Etichetta** e **Testo guida** di ogni origine dati configurata possono essere collegati a un'etichetta ER che viene aggiunta al formato ER. Gli attributi **Etichetta** e **Descrizione** del <a id="LinkFormatEnum"></a>valore di ogni enumerazione del formato possono essere collegati a un'etichetta ER accessibile dal formato ER modificabile.

> [!NOTE]
> È inoltre possibile collegare questi attributi a un'etichetta ER del modello di dati ER padre che riutilizza le etichette del modello in ogni formato ER configurato per questo modello di dati ER.

Quando un formato ER viene configurato in questo modo, il contenuto del formato verrà presentato agli utenti della pagina della progettazione dell'operazione ER nella lingua preferita di ciascun utente. Pertanto, la manutenzione del formato e l'analisi della logica configurata sono semplificate.

Poiché il formato ER si basa su un modello di dati ER, le etichette a cui si fa riferimento negli elementi del modello di dati vengono visualizzate nella pagina della progettazione del formato ER nella lingua preferita dell'utente.

Quando l'attributo **Etichetta** dell'origine dati **Parametro di input utente** è configurato come collegato a un'etichetta ER, il campo che corrisponde al parametro nella finestra di dialogo in fase di esecuzione viene presentato all'utente come richiesta. Le seguenti illustrazioni mostrano come è possibile collegare l'attributo **Etichetta** dell'origine dati **Parametro di input utente** in fase di progettazione a un'etichetta ER, in modo che agli utenti venga richiesto il parametro in diverse lingue preferite dall'utente (mostrate per le lingue inglese Stati Uniti (EN-US) e DE-AT) in fase di esecuzione.

![Fornitura della traduzione degli attributi di un parametro di input utente nella finestra di progettazione dell'operazione ER.](./media/er-multilingual-labels-refer-format.png)

![Elaborazione del pagamento fornitore ER in fase di esecuzione per la lingua preferita dall'utente EN-US.](./media/er-multilingual-labels-show-runtime-en.png)

![Elaborazione del pagamento fornitore ER in fase di esecuzione per la lingua preferita dall'utente DE-AT.](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Espressioni

Per utilizzare un'etichetta in un'[espressione](er-formula-language.md) ER, è necessario utilizzare la sintassi **@"GER\_LABEL:X"**, dove il prefisso **@** indica che l'operando si riferisce a un'etichetta, **GER\_LABEL** indica che è coinvolta un'etichetta ER e **X** è l'ID dell'etichetta ER.

![Configurazione di un'espressione ER contenente un riferimento a un'etichetta ER nella finestra di progettazione della formula ER.](./media/er-multilingual-labels-expression1.png)

Per fare riferimento a un'etichetta di sistema (applicazione), utilizzare la sintassi **@"X"**, dove il prefisso **@** indica che l'operando si riferisce a un'etichetta e **X** è l'ID dell'etichetta di sistema.

![Configurazione di un'espressione ER contenente un riferimento a un'etichetta dell'applicazione nella finestra di progettazione della formula ER.](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Mapping modello

Un'espressione di un mapping del modello ER può essere configurata utilizzando un'etichetta. Quando questo mapping viene chiamato da un formato ER che viene eseguito per generare un documento in uscita, il contesto dell'esecuzione include un codice di lingua. Un'etichetta di espressione configurata viene compilata con il testo dell'etichetta che è stato configurato per la lingua di quel contesto.

Se un'etichetta a cui si fa riferimento non ha una traduzione per la lingua del contesto di esecuzione del formato che chiama il mapping del modello, al suo posto viene utilizzato il testo dell'etichetta nella lingua EN-US.

#### <a name="format"></a>Formatta

Un'espressione ER di un formato ER può essere configurata utilizzando le etichette. Quando questo formato viene eseguito per generare un documento in uscita, il contesto dell'esecuzione include un codice di lingua. Un'etichetta di espressione configurata viene compilata con il testo dell'etichetta che è stato configurato per la lingua di quel contesto.

![Fornitura della traduzione di un'etichetta ER dell'espressione ER modificabile nella finestra di progettazione della formula ER.](./media/er-multilingual-labels-refer-in-expression.png)

![Esempio di associazione dati che fa riferimento a un'etichetta ER nella finestra di progettazione dell'operazione ER.](./media/er-multilingual-labels-refer-in-binding.png)

È possibile configurare il componente **FILE** di un formato ER per generare il report nella lingua preferita dell'utente.

![Impostare il componente FILE nella finestra di progettazione dell'operazione ER per generare il report nella lingua preferita dell'utente.](./media/er-multilingual-labels-language-context-user.png)

Se si configura un formato ER in questo modo, il report viene generato utilizzando il testo corrispondente delle etichette ER. Le seguenti illustrazioni mostrano esempi di report per le lingue dell'utente EN-US e DE-AT.

![Anteprima del report generato nella lingua preferita dell'utente EN-US.](./media/er-multilingual-labels-report-preview-en.png)

![Anteprima del report generato nella lingua preferita dell'utente DE-AT.](./media/er-multilingual-labels-report-preview-de.png)

Se un'etichetta a cui si fa riferimento non ha una traduzione per la lingua del contesto di esecuzione del formato, al suo posto viene utilizzato il testo dell'etichetta nella lingua EN-US.

> [!TIP]
> Puoi usare la **CARTELLA** e tipi distinti di componenti **FILE** nel formato ER modificabile per specificare come viene generato un file in uscita. Per denominare un file generato, configura l'[espressione](er-formula-language.md) ER per il parametro **Nome file** del componente. Puoi utilizzare le etichette nell'espressione configurata. Poiché il parametro **Nome file** è indipendente dalla lingua per impostazione predefinita, il testo di tutte le etichette a cui si fa riferimento in questa espressione viene esposto nella lingua EN-US predefinita in fase di esecuzione. Tuttavia, nella versione 10.0.28 e successive, puoi abilitare la funzionalità **Applica il parametro "Preferenza lingua" all'espressione "Nome file"**. L'espressione **Nome file** quindi prende il parametro **Preferenze lingua** in considerazione quando viene calcolata.

## <a name="language"></a>Lingua

ER supporta diversi modi per specificare una lingua per un report generato. Nel campo **Preferenze lingua** della scheda **Formato** è possibile selezionare i seguenti valori:

- **Preferenza società** - Genera un report in una lingua specificata dalla società.

    ![Specificare nella finestra di progettazione dell'operazione ER una lingua preferita della società come lingua di un report generato.](./media/er-multilingual-labels-language-context-company.png)

- **Preferenza utente** - Genera un report nella lingua preferita dell'utente.
- **Definito esplicitamente** - Genera un report in una lingua specificata in fase di progettazione.

    ![Specificare nella finestra di progettazione dell'operazione ER una lingua definita in fase di progettazione come lingua di un report generato.](./media/er-multilingual-labels-language-context-fixed.png)

- **Definito in fase di esecuzione** - Genera un report in una lingua specificata in fase di esecuzione. Se si seleziona questo valore nel campo **Lingua**, configurare un'espressione ER che restituisce il codice per la lingua, ad esempio la lingua del cliente corrispondente.

    ![Specificare nella finestra di progettazione dell'operazione ER una lingua definita in fase di esecuzione come lingua di un report generato.](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="culture-specific-formatting"></a>Formattazione specifica della lingua

ER supporta diversi modi per specificare la lingua per un report generato. Pertanto, è possibile utilizzare la formattazione specifica della lingua corretta per i valori di data, ora e numerici. Quando si progetta un formato ER, nella scheda **Formato**, nel campo **Preferenze cultura** è possibile selezionare uno dei seguenti valori per ogni componente di formato del tipo **Comune\\File**, **Excel\\File**, **PDF\\File**, o **Unione\\PDF**:

- **Preferenza utente** - Formatta i valori in base alla lingua preferita dell'utente. La lingua è definita nel campo **Formato data, ora e numero** nella scheda **Preferenze** della pagina **Opzioni utente**.

    ![Definizione della lingua preferita dell'utente come lingua di un report generato nella finestra di progettazione delle operazioni ER.](./media/er-multilingual-labels-culture-context-user-preferred.png)

- **Definito esplicitamente** - Formatta i valori in base alla lingua specificata in fase di progettazione.

    ![Definizione della lingua specificata in fase di progettazione come lingua di un report generato nella finestra di progettazione delle operazioni ER.](./media/er-multilingual-labels-culture-context-fixed.png)

- **Definito in fase di esecuzione** - Formatta i valori in base alla lingua specificata in fase di esecuzione. Se selezioni questo valore, nella scheda **Mapping**, nel campo **Formato data, ora e numero**, configurare un'espressione ER che restituisca il codice lingua per la cultura, ad esempio la lingua del cliente corrispondente.

    ![Definizione della lingua definita in fase di esecuzione come lingua di un report generato nella finestra di progettazione delle operazioni ER.](./media/er-multilingual-labels-culture-context-runtime.png)

> [!NOTE]
> Un componente ER per cui si definisce una lingua specifica potrebbe contenere componenti ER figlio che sono stati configurati per inserire un valore di testo. Per impostazione predefinita, la lingua del componente padre viene utilizzata per formattare i valori di tali componenti. È possibile utilizzare le seguenti funzioni ER incorporate per configurare le associazioni per quei componenti e applicare una lingua alternativa per la formattazione del valore:
>
> - [DATEFORMAT](er-functions-datetime-dateformat.md#syntax-2)
> - [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md#syntax-2)
> - [NUMBERFORMAT](er-functions-text-numberformat.md#syntax-2)
>
> Nella versione 10.0.20 e successive, le impostazioni locali dei componenti di formato di tipo **Comune\\File** e **Excel\\File** vengono utilizzate per formattare i valori durante la [conversione PDF](electronic-reporting-destinations.md#OutputConversionToPDF) di un documento generato.

## <a name="translation"></a>Traduzione

È possibile aggiungere le etichette ER richieste a un componente ER modificabile. Quando viene aggiunta un'etichetta ER, può essere tradotta in due modi: manualmente e automaticamente.

### <a name="manual-translation"></a>Traduzione manuale

Quando si aggiunge un'etichetta ER nel [riquadro](#TextTranslationPane) **Traduzione testo**, è possibile tradurla manualmente in tutte le lingue supportate nell'istanza di Finance corrente. È possibile selezionare la lingua preferita nel campo **Lingua** nella sezione **Lingua di sistema** o **Lingua dell'utente**, inserire il testo appropriato nella corrispondente campo **Testo tradotto**, quindi selezionare **Traduci**. Questo processo deve essere ripetuto per ogni lingua richiesta e per ogni etichetta aggiunta.

### <a name="automatic-translation"></a>Traduzione automatica

La configurazione di un componente ER viene eseguita nella versione bozza della configurazione ER in cui risiede il componente ER modificabile.

![Pagina Configurazioni ER che offre l'accesso alla versione della configurazione nello stato bozza.](./media/er-multilingual-labels-configurations.png)

Come descritto in precedenza in questo articolo, è possibile aggiungere le etichette ER richieste a un componente ER modificabile. In questo modo, è possibile specificare il testo delle etichette ER nella lingua EN-US. È quindi possibile esportare le etichette del componente ER utilizzando la funzione ER integrata. Selezionare la versione bozza di una configurazione ER che contiene il componente ER modificabile, quindi selezionare **Scambio \> Esporta etichette**.

![Pagina Configurazioni ER che consente di esportare le etichette ER dalla versione di configurazione selezionata.](./media/er-multilingual-labels-export.png)

È possibile esportare tutte le etichette o le etichette per una singola lingua specificata all'inizio dell'esportazione. Le etichette vengono esportate come file zip che contiene file XML. Ogni file XML contiene le etichette per una singola lingua.

![Esempio del file esportato contenente etichette ER per la lingua DE-AT.](./media/er-multilingual-labels-in-xml.png)

Questo formato viene utilizzato per la traduzione automatica di etichette da parte di servizi di traduzione esterni come [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). Quando si ricevono le etichette tradotte, è possibile importarle nuovamente nella versione bozza di una configurazione ER che contiene i componenti ER che includono tali etichette. Selezionare la versione bozza di una configurazione ER che contiene il componente ER modificabile, quindi selezionare **Scambio \> Carica etichette**.

![Pagina Configurazioni ER che consente di importare le etichette ER nella versione di configurazione selezionata.](./media/er-multilingual-labels-load.png)

Le etichette tradotte vengono importate nella configurazione ER selezionata. Le etichette tradotte che esistono in questa configurazione ER vengono sostituite. Se nella configurazione ER manca un'etichetta tradotta, viene aggiunta.

## <a name="lifecycle"></a>Ciclo di vita

Le etichette di un componente ER che possono essere modificate vengono conservate, insieme ad altri contenuti per il componente, nella versione appropriata di una configurazione ER.

È possibile fare riferimento alle etichette di un componente ER di base in una versione derivata del componente ER creata per introdurre le modifiche.

> [!TIP]
> Quando si progetta una soluzione ER, è possibile derivare il componente del [modello di dati](er-overview-components.md#data-model-component) ER da quello fornito. In questo modello di dati derivato, puoi introdurre le tue etichette ER e usarle in tutti i formati ER che utilizzeranno il modello di dati come origine dati. È possibile derivare il componente del [formato](er-overview-components.md#format-component) ER da quello fornito selezionando il modello di dati ER derivato anziché quello fornito. Nella versione 10.0.28 e successive, puoi abilitare la funzione **Accesso avanzato alle etichette del modello di dati ER ascendente** per accedere alle etichette di un modello di dati ER ascendente in componenti di formato ER derivati, anche quando il modello di dati ER selezionato per il componente ER derivato è diverso da quello utilizzato nel componente ER di base.
>
> Quando lo stesso nome dell'etichetta viene utilizzato nel componente derivato e nei suoi componenti ascendenti, la traduzione di tale etichetta viene utilizzata come quella più pertinente.

Il controllo delle versioni ER controlla l'assegnazione delle etichette a qualsiasi attributo in un componente ER. Le modifiche all'assegnazione dell'etichetta vengono registrate nell'elenco delle modifiche (delta) di un componente ER modificabile che è stato creato come versione derivata del componente ER fornito. Queste modifiche vengono convalidate quando una versione derivata viene riassegnata a una nuova versione di base.

## <a name="functions"></a>Funzioni

La funzione ER [LISTOFFIELDS](er-functions-list-listoffields.md) incorporata può accedere alle etichette ER che sono state configurate per alcuni elementi dei componenti ER.

Come descritto in precedenza in questo articolo, gli attributi **Etichetta** e **Descrizione** del valore dell'enumerazione ER di ciascun [modello](#LinkModelEnum) o [formato](#LinkFormatEnum) possono essere collegati a un'etichetta ER accessibile nel componente ER appropriato. È possibile configurare un'espressione ER in cui si chiama la funzione **LISTOFFIELDS** utilizzando l'enumerazione ER come argomento. Questa espressione restituisce un elenco che contiene un record per ogni valore di un'enumerazione ER che è stata definita come argomento di questa funzione. Ogni record contiene il valore di un'etichetta ER collegata a un valore di enumerazione ER:

- Il valore di un'etichetta ER collegata agli attributi **Etichetta** sono memorizzati nel campo **Etichetta** del record restituito.
- Il valore di un'etichetta ER collegata agli attributi **Descrizione** sono memorizzati nel campo **Descrizione** del record restituito.

## <a name="performance"></a><a name=performance></a>Prestazioni

Quando si configura un componente in formato ER per generare un report nella [lingua](#language) preferita o per importare un documento in entrata in cui il contenuto viene analizzato dalla lingua preferita, consigliamo di abilitare la funzionalità **Memorizza nella cache la lingua preferita dell'utente corrente per esecuzioni ER** nell'area di lavoro [Gestione funzionalità](../../fin-ops/get-started/feature-management/feature-management-overview.md). Questa funzionalità aiuta a migliorare le prestazioni, in particolare per i componenti in formato ER che contengono più riferimenti a etichette in formule e associazioni ER e molte regole di [convalida](general-electronic-reporting-formula-designer.md#TestFormula) per generare messaggi utente nella lingua preferita.

Quando si modifica lo stato di una versione della configurazione ER da **Bozza** a **Completato**, se la versione di configurazione contiene etichette ER, tali etichette vengono archiviate nel database dell'applicazione. Lo schema di archiviazione dipende dallo stato della funzionalità **Accelera l'archiviazione delle etchette ER**:

- Se la funzione non è abilitata, tutte le etichette vengono archiviate nel campo **LABELXML** della tabella **ERSOLUTIONVERSIONTABLE** come un singolo frammento XML.
- Se la funzionalità è abilitata, viene creato un record separato per ogni lingua nella tabella **ERSOLUTIONVERSIONLABELSTABLE**. Il campo **CONTENTS** di questa tabella archivia le etichette per lingua come frammento XML compresso.

È consigliabile abilitare la funzionalità **Accelera l'archiviazione delle etichette ER** nell'area di lavoro **Gestione funzionalità**. Questa funzionalità consente di migliorare l'utilizzo della larghezza di banda della rete e le prestazioni complessive del sistema poiché, nella maggior parte dei casi, vengono utilizzate etichette ER di una singola lingua quando si lavora con una configurazione ER singola.

Per applicare lo schema di archiviazione selezionato per mantenere le etichette di tutte le configurazioni ER nell'istanza corrente di Finance, completa i passaggi seguenti.

1. Vai a **Amministrazione organizzazione** > **Periodico** > **Applica le etichette selezionate che archiviano lo schema per tutte le configurazioni ER**.
2. Seleziona **OK**.


## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Funzioni di creazione di report elettronici](er-formula-language.md#Functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
