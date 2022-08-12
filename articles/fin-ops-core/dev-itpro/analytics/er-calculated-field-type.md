---
title: Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato
description: In questo articolo vengono fornite informazioni su come utilizzare il tipo Campo calcolato per le origini dati ER.
author: NickSelin
ms.date: 01/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5a4eb70144957ecdbeba4246fb8c7cd6a20cb08c
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108331"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a>Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come progettare un'origine dati ER utilizzando il tipo **Campo calcolato**. Questa origine dati può contenere un'espressione ER che, quando eseguita, può essere controllata con i valori degli argomenti dei parametri configurati in un'associazione che chiama questa origine dati. Mediante la configurazione delle chiamate parametrizzate di un'origine dati simile, è possibile riutilizzare una singola origine dati in molte associazioni, riducendo quindi il numero totale di origini dati che devono essere configurate nei mapping di modello ER o nei formati ER. Semplifica inoltre il componente ER configurato, riducendo di conseguenza i costi di manutenzione e il costo di utilizzo da parte di altri clienti.

## <a name="prerequisites"></a>Prerequisiti
Per completare gli esempi in questo articolo, è necessario disporre del seguente accesso:

- Accesso a uno di questi ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- Accesso ai servizi RCS (Regulatory Configuration Services) di cui è stato eseguito il provisioning per lo stesso tenant di Finanza e operazioni per uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

È inoltre necessario scaricare e archiviare localmente i file seguenti.

| **Contenuto**                           | **Nome file**                                        |
|---------------------------------------|------------------------------------------------------|
| Configurazione del modello di dati ER di esempio    | [Model to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/e/5/c/e5c0d3f9-1818-47c7-ae75-46efcbb1314f/Modeltolearnparameterizedcallsversion.1.xml)     |
| Configurazione dei metadati ER di esempio      | [Metadata to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/8/3/a/83a910a5-bf65-4509-bec4-6737a81ecc45/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Configurazione del mapping di modello ER di esempio | [Mapping to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/b/f/d/bfd8cbd8-0370-44d1-a1b1-66d021c580ca/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Configurazione di formato ER di esempio        | [Format to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/8/1/d/81deb6d8-a768-4fcf-bbbe-8f84d2dac3eb/Formattolearnparameterizedcalls.version.1.1.xml)  |

## <a name="sign-in-to-your-rcs-instance"></a>Accedere all'istanza RCS
In questo esempio si creerà una configurazione per la società di esempio Litware, Inc. Innanzitutto, in RCS, completare i passaggi nella procedura [Creare fornitori di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1. Nel dashboard predefinito, selezionare **Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Importare le configurazioni scaricate in RCS nel seguente ordine: modello di dati, metadati, mapping di modello, formato. Completare i passaggi seguenti per ogni configurazione ER:

    1. Selezionare **Scambia**.
    2. Selezionare **Carica da file XML**.
    3. Selezionare **Sfoglia** quindi selezionare la configurazione ER necessaria in formato XML.
    4. Selezionare **OK**.

## <a name="review-the-provided-er-solution"></a>Esaminare la soluzione ER fornita

### <a name="review-model-mapping"></a>Esaminare il modello di mapping

1. Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.
2. Selezionare **Mapping per ottenere chiamate parametrizzate**.
3. Selezionare **Progettazione**.
4. Selezionare **Progettazione**.  
   
    Questo mapping di modello ER esegue le operazioni seguenti:

    - Recuperare l'elenco di codici imposta (origine dati **Imposta**) presenti nella tabella **TaxTable**.
    - Recuperare l'elenco di transazioni fiscali (origine dati **Trans**) presenti nella tabella **TaxTrans**.
    
        - Raggruppare l'elenco di transazioni recuperate (origine dati **Gr**) per codice imposta.
        - Calcolare le transazioni raggruppate in base ai valori aggregati per codice imposta:

            - Somma dei valori di imposta di base.
            - Somma dei valori di imposta.
            - Valore minimo dell'aliquota fiscale applicata.

    Il mapping di modello in questa configurazione implementa il modello di dati di base per qualsiasi formato ER creato per questo modello ed eseguito in Finanza e operazioni. Di conseguenza, il contenuto delle origini dati **Imposta** e **Gr** viene esposto per i formati ER, ad esempio origini dati astratte.

    ![Pagina Progettazione mapping modello con le origini dati Imposta e Gr.](media/er-calculated-field-type-01.png)

5.  Chiudere la pagina **Progettazione mapping modello**.
6.  Chiudere la pagina **Mapping modello**.

### <a name="review-format"></a>Esaminare il formato

1. Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.
2. Selezionare **Formato per ottenere chiamate parametrizzate**.
3. Selezionare **Progettazione**. Questo formato ER esegue le operazioni seguenti:

    - Generare una dichiarazione fiscale in formato XML.
    - Presentare i seguenti livelli di tassazione nella dichiarazione fiscale: Normale, Ridotto e Nessuno.
    - Presentare molteplici dettagli a ogni livello di tassazione, avendo un numero differente di dettagli in ogni livello.

    ![Pagina Progettazione formati.](media/er-calculated-field-type-02.png)

4. Selezionare **Mapping**.
5. Espandere gli elementi **Modello**, **Dati** e **Riepilogo**. 

    Il campo calcolato **Model.Data.Summary.Level** contiene l'espressione che restituisce il codice del livello di tassazione (**Normale**, **Ridotto**, **Nessuno** o **Altro**) come valore di testo per qualsiasi codice imposta che è possibile recuperare dall'origine dati **Model.Data.Summary** in fase di esecuzione.

    ![Pagina Progettazione formati con dettagli del modello di dati Modello per ottenere chiamate parametrizzate.](media/er-calculated-field-type-03.png)

6. Espandere l'elemento **Model**.**Data2**.
7. Espandere l'elemento **Model**.**Data2Data2.Summary2**.
   
    L'origine dati **Model**.**Data2.Summary2** è configurata per raggruppare i dettagli delle transazioni dell'origine dati **Model.Data.Summary** per livello di tassazione (restituito dal campo calcolato **Model.Data.Summary.Level** ) e calcolare le aggregazioni.

    ![Pagina Progettazione formati con i dettagli dell'origine dati Model.Data2.Summary2.](media/er-calculated-field-type-04.png)

8. Esaminare i campi calcolati. **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**. Questi campi calcolati sono utilizzati per filtrare l'elenco di record **Model**.**Data2.Summary2** e restituire solo i record che rappresentano un particolare livello di tassazione.
9. Chiudere la pagina **Progettazione formati**.

## <a name="create-a-derived-format"></a>Creare un formato derivato
È possibile migliorare il formato fornito aggiungendo un campo calcolato per filtrare il livello di tassazione necessario anziché utilizzare i tre campi esistenti: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** e **Model**.**Data2.Level3**. Il livello di tassazione necessario può essere specificato nella posizione in cui questo nuovo campo calcolato verrà chiamato.

1. Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.
2. Selezionare **Formato per ottenere chiamate parametrizzate**.
3. Selezionare **Crea configurazione**.
4. Selezionare **Deriva da nome: Formato per ottenere chiamate parametrizzate, Microsoft**.
5. Nel campo **Nome**, immettere **Formato per ottenere chiamate parametrizzate (personalizzato)**.
6. Selezionare **Crea configurazione**.

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a>Configurare un campo calcolato parametrizzato che restituisce un elenco di record

### <a name="start-adding-a-new-calculated-field"></a>Aggiungere un nuovo campo calcolato

1. Selezionare **Progettazione**.
2. Selezionare **Espandi/Comprimi** per espandere tutti gli elementi di formato.
3. Selezionare **Mapping**.
4. Espandere l'elemento **Model**.
5. Selezionare l'elemento **Model.Data2**.
6. Selezionare **Aggiungi**.
7. Selezionare **Funzioni\\Campo calcolato**.
8. Nel campo **Nome** immettere **Livelli**.
9. Selezionare **Modifica formula**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definire un parametro per aggiungere un campo calcolato

1. Selezionare **Parametri**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome**, immettere **Livello di tassazione**.
4. Nel campo **Tipo** selezionare **Stringa**.

    Solo i tipi di dati primitivi possono essere utilizzati per specificare il tipo di argomento del parametro. Di conseguenza, i tipi **Elenco di record**, **Record** e **Enum** non sono utilizzabili per tale scopo.

    Il numero massimo di parametri che è possibile specificare per un singolo campo calcolato è 8.

    ![Elenco delle origini dati dei parametri.](media/er-calculated-field-type-05.png)

5. Selezionare **OK**.

Aggiungendo questo parametro, si specifica la condizione necessaria per chiamare questo campo calcolato. Quando si chiama questo campo calcolato, è necessario specificare l'argomento del parametro **Livello di tassazione** come valore con formato **Stringa**.

   Assicurarsi di definire i parametri solo per quei campi calcolati che si trovano in un contenitore ( **Elenco record**, **Record** o **Contenitore**).

   Il parametro configurato è disponibile nell'elenco delle origini dati per questo campo calcolato. È possibile aggiungere il parametro all'espressione configurata selezionando **Aggiungi origine dati**.

   ![Campi dell'origine dati.](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definire un'espressione per aggiungere un campo calcolato

1. Nel campo **Formula'**, immettere: 

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level =**
    
2. Selezionare il parametro **Livello di tassazione** nell'elenco delle origini dati.
3. Selezionare **Aggiungi origine dati**.
4. Nel campo **Formula**, finalizzare l'espressione come segue:  

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Livello di tassazione')**

5. Selezionare **Salva**.

    ![Informazioni sui campi dell'origine dati.](media/er-calculated-field-type-07.png)

6. Chiudere la pagina **Designer formula**.

### <a name="finish-adding-a-new-calculated-field"></a>Completare l'aggiunta di un nuovo campo calcolato

- Selezionare **OK**.

Nella pagina **Progettazione formati**, il campo calcolato parametrizzato configurato **Livelli** richiede un argomento **Stringa**.

![Elenco espanso dei livelli del campo calcolato.](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a>Utilizzare il campo calcolato configurato per associare elementi di formato

1. Selezionare **Model.Data2.Levels** per selezionare il campo calcolato configurato.
2. Selezionare l'elemento di formato **Statement.Taxation.Regular**.
3. Selezionare **Associa**.
4. Selezionare **Sì** per confermare la sostituzione dell'origine dati attualmente utilizzata, **Level1**, con la nuova origine dati, **Livelli**, in tutti gli elementi di formato nidificati dell'elemento di formato selezionato.

    L'associazione applicata è stata generata come chiamata del campo calcolato parametrizzato. Per impostazione predefinita, il nome dell'elemento di formato associato viene utilizzato come argomento per il campo calcolato parametrizzato nelle seguenti condizioni:

      - Il campo calcolato è configurato per utilizzare un singolo parametro.
      - Il tipo di dati di questo parametro è definito come **Stringa**.

    Quando il nome dell'elemento di formato associato è vuoto, il nome dell'origine dati di questo elemento viene utilizzato nell'associazione applicata.

5. Selezionare l'elemento di formato **Statement.Taxation.Reduced**.
6. Selezionare **Associa**.
7. Selezionare **Sì** per confermare la sostituzione dell'origine dati attualmente utilizzata, **Level2**, con la nuova origine dati, **Livelli**, in tutti gli elementi di formato nidificati sotto l'elemento di formato selezionato.
8. Selezionare l'elemento di formato **Statement.Taxation.None**.
9. Selezionare **Associa**.
10. Selezionare **Sì** per confermare la sostituzione dell'origine dati attualmente utilizzata, **Level3**, con la nuova origine dati, **Livelli**, in tutti gli elementi di formato nidificati sotto l'elemento di formato selezionato.

   Quando si specifica l'argomento del campo calcolato parametrizzato per l'elemento XML che rappresenta il livello di tassazione (ad esempio **Model.Data2.Levels("Ridotto")** come valore di testo) non è necessario effettuare la stessa operazione per gli attributi XML nidificati: le relative associazioni erediteranno automaticamente il valore dell'argomento definito nel livello principale (**Model.Data2.Levels.aggregated.Base**, non **Model.Data2.Levels("Reduced").aggregated.Base**).

Le chiamate ricorrenti di qualsiasi campo calcolato parametrizzato non sono supportate.

È possibile selezionare **Modifica formula** e modificare l'argomento applicato per impostazione predefinita del campo calcolato parametrizzato nell'associazione selezionata. Se questo argomento non è presente, può causare errori in fase di esecuzione: gli utenti vengono informati di tale situazione quando il formato corrente viene convalidato.

![Notifica dell'avviso di convalida.](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a>Configurare un campo calcolato parametrizzato per restituire un record
Quando un campo calcolato parametrizzato restituisce un record, è necessario supportare l'associazione di singoli campi di tale record con elementi di formato. In tali casi un'associazione padre contenente il valore di un argomento per chiamare un campo calcolato parametrizzato non sarà disponibile; questo valore deve essere definito nell'associazione del campo di un singolo record.

### <a name="start-adding-a-new-calculated-field"></a>Aggiungere un nuovo campo calcolato

1. Selezionare l'elemento **Model.Data2**.
2. Selezionare **Aggiungi**.
3. Selezionare **Funzioni\\Campo calcolato**.
4. Nel campo **Nome** immettere **LevelRecord**.
5. Selezionare **Modifica formula**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definire un parametro per aggiungere un campo calcolato

1. Selezionare **Parametri**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome**, immettere **Livello di tassazione**.
4. Nel campo **Tipo** selezionare **Stringa**.
5. Selezionare **OK**.

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definire un'espressione per aggiungere un campo calcolato

1. Nel campo **Formula**, immettere quanto segue:  
    
    **FIRSTORNULL(\@.Levels(**

2. Selezionare il parametro **Livello di tassazione**.
3. Selezionare **Aggiungi origine dati**.
4. Nel campo **Formula**, aggiungere **'Livello di tassazione'))** a quanto immesso nel passaggio 1 per ottenere l'espressione finale:  
    
    **FIRSTORNULL(\@.Levels('Livello di tassazione'))**

5. Selezionare **Salva**.
6. Chiudere la pagina **Designer formula**.

### <a name="finish-adding-a-new-calculated-field"></a>Completare l'aggiunta di un nuovo campo calcolato

-   Selezionare **OK**.

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a>Utilizzare il campo calcolato configurato per associare elementi di formato

1. Espandere **Model.Data2.LevelRecord** per selezionare il campo calcolato configurato.
2. Espandere il contenitore **Model.Data2.LevelRecord.aggregated** del campo calcolato configurato.
3. Selezionare il campo **Model.Data2.LevelRecord.aggregated.Base**.
4. Selezionare l'elemento di formato **Statement.Taxation.None**.
5. Selezionare **Separa**.
6. Selezionare l'elemento di formato **Statement.Taxation.None.Base**.
7. Selezionare **Associa**.
8. Selezionare **Modifica formula**.
9. Modificare l'espressione in **Model.Data2.LevelRecord("Nessuno").aggregated.Base**.

![Espressione aggiornata.](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a>Rimuovere i campi calcolati non utilizzati

1. Selezionare **Model.Data2.Level1**.
2. Selezionare **Elimina**.
3. Selezionare **Model.Data2.Level2**.
4. Selezionare **Elimina**.
5. Selezionare **Model.Data2.Level3**.
6. Selezionare **Elimina**.
7. Selezionare **Salva**.

  > [!NOTE]
  > Lo stesso campo calcolato **Model.Data2.Levels** è stato utilizzato più volte in associazioni di formato. È molto più semplice utilizzare e gestire un singolo campo calcolato anziché ripetere tale procedura per più campi simili.

8. Chiudere la pagina **Progettazione formati**.

## <a name="complete-adjusted-version-of-a-derived-format"></a>Completare la versione rettificata di un formato derivato

1. Nella Scheda dettaglio **Versioni**, selezionare **Cambia stato**.
2. Selezionare **Completa**.

## <a name="export-completed-version-of-a-derived-format"></a>Esportare la versione completata di un formato derivato

1. Selezionare il formato **Formato per ottenere chiamate parametrizzate (personalizzato)** nella struttura delle configurazioni.
2. Nella Scheda dettaglio **Versioni**, selezionare la versione 1.1.1 completata.
3. Selezionare **Scambia**.
4. Selezionare **Esporta come file XML**.
5. Archiviare la configurazione scaricata localmente in formato XML.

## <a name="test-er-formats"></a>Verificare i formati ER 
È possibile eseguire formati ER iniziali e migliorati per assicurarsi che i campi calcolati parametrizzati configurati funzionino correttamente.

### <a name="import-er-configurations"></a>Importare configurazioni ER
È possibile importare le configurazioni esaminate da RCS utilizzando il repository ER del tipo **RCS**. Se hai già letto la procedura nell'articolo [Importare configurazioni di creazione di report elettronici da Regulatory Configuration Services](rcs-download-configurations.md), utilizza il repository ER configurato per importare le configurazioni descritte in precedenza in questo articolo nel tuo ambiente. In caso contrario, procedere come segue:

1. Selezionare la società **DEMF** e nel dashboard predefinito selezionare **Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Importare le configurazioni dall'Area download Microsoft nel seguente ordine: modello di dati, mapping di modello, formato. Completare i passaggi seguenti per ogni configurazione ER:

    1. Selezionare **Scambia**.
    2. Selezionare **Carica da file XML**.
    3. Selezionare **Sfoglia** per selezionare la configurazione ER necessaria in formato XML.
    4. Selezionare **OK**.

4. Importare la versione 1.1.1 completata del formato **Formato per ottenere chiamate parametrizzate (personalizzato)** che è stata esportata da RCS:

    1. Selezionare **Scambia**.
    2. Selezionare **Carica da file XML**.
    3. Selezionare **Sfoglia** per selezionare il file **Formato per ottenere chiamate parametrizzate (personalizzato)** in formato XML archiviato localmente.
    4. Selezionare **OK**.

### <a name="run-er-formats"></a>Eseguire formati ER

1. Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.
2. Selezionare **Formato per ottenere chiamate parametrizzate**.
3. Selezionare **Esegui** nella barra multifunzione superiore.
4. Salvare l'output generato localmente.
5. Selezionare l'elemento **Formato per ottenere chiamate parametrizzate (personalizzato)**.
6. Selezionare **Esegui** nella barra multifunzione superiore.
7. Salvare l'output generato localmente. 
8. Confrontare il contenuto degli output generati.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Designer formula nella creazione di report elettronici (ER)](general-electronic-reporting-formula-designer.md)
- [Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

